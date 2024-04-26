---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
L ^hooIKVKy

o ^dFeyfUTB

w ^fvSfja5C

D ^nHPLtCXx

i ^Ih3BF7eL

m ^JJTfTgrP

e ^pBglTV49

n ^fQARXgX0

s ^LVpqh3yJ

i ^bdJ04JeJ

o ^xTLIdmNW

n ^pVUPz6S7

a ^mas8bOpt

l ^adMtCD5L

( ^bxYAVmOc

L ^xt13692B

o ^C0LdeWQb

c ^9y7XH5SM

a ^9hNjkfm1

l ^ZcfjP7Gz

L ^IePxxiug

i ^C56Npyo3

n ^5dHslA1h

e ^73qMqUYa

a ^DHYx3E36

r ^wYDFDFqB

E ^osAs2sNh

m ^xozyZV0w

b ^tA4VCGrO

e ^hwcM2Pt5

d ^DM3DflSv

d ^pjVKLCam

i ^5vtgCcFw

n ^ifblJc5K

g ^K0To2aoH

) ^kfr1KfXt

h ^zYsvMf2q

a ^rursOLfo

h ^f4j2kREJ

a ^ppIKGMXR

  ^xaXve5jT

f ^hc6cHLnO

u ^rBZCW1hr

n ^AZbxzvjA

  ^DP3B24fa

s ^daLz2kNx

w ^L0NYNHev

i ^3QzREgJE

r ^ooQFJALz

l ^XqybOaP9

y ^GzgLDQ8t

  ^IB4NAqHr

s ^fsWqlcQB

t ^iqgi5OOP

u ^Mhz05AUg

f ^rusUotT8

f ^pj1r5kk1

We have previously discussed motivation
behind wanting to do low dimensional
embedding in order to get all the
important details of the data without
losing much in cases that
have very high dimensional data like
high resolution images.
Refresh on this by reading PCA ^lNSh8Qkr

E ^sWo8zyCe

m ^3lQ48qMM

b ^tmHCm9Ag

e ^OVEWTv5c

d ^8SLjonbF

d ^Vyg8mZ9e

i ^uHzlBGNn

n ^klsH1tTv

g ^j1XFZDx6

General goals ^TMdTvZVe

1. Visualization:
High dimensional structures and relations are often intriguing yet not
intuitive to our problems, being able to visualize a structure of sorts that
is not in 1000th dimension can be quite useful to draw insights from it.

2. Better Generalization:
Fewer dimensions in some cases mean less chances of overfitting and for your
model to obsess over little "noise" details and attributes, which results in a
more general result.

3. Speed Up:
Most algorithms scale horribly with dimensionality, it would be useful to have data
that produces similar results but is much easier to compute.

4. Data compression:
For larger datasets, its useful to minimize on storage usage as it can quickly get
out of hand ^DckulMmW

Okay but we
already know
PCA, Why not
just use that? ^737N6O29

Well PCA is a linear
transformation so if data lies on a
non-linear manifold PCA results
will not be logical Also PCA
assumes a Gaussian ^ewjcllJo

Okay but why not
just use Kernel PCA
Which we also know and
is not Linear? ^uOw3MsWD

.
.
.
.
Shut up nerd ^mmUzWlMJ

Silly Linear
Model moment

 ^fXt7YmJs

(PCA) ^mhdZMIZg

(LLE) ^PJhY6UGG

We want to
preserve
neighbourhood
relations  ^F5BjUosa

Local Linear Embedding
(LLE) ^7p17SETG

The Main idea behind LLE is to narrow our scope on local regions (neighborhood) of the data, learn its structure
and the neighborhood relations it has, reduce it to lower dimensions while keeping the sale relations we originally observed

Note that this concept inherently gives us a bit of leeway with some Affine transformations. 
For example if we take 5 points representing a pyramid, no matter if it was rotated, scaled
or translated, it will still be a pyramid ^BkjbjkYS

Original ^UHrfjz8g

Rotated ^VcghQnI5

Scaled ^hOAs39B8

Translated ^oHJixLW1

Lets Address the algorithm and how it works step by step ^gfDTH0bO

1. Compute the neighbors:
When we pick a specific point that we want to map from high dimensions
to low dimensions, we must have a criteria that optimally decides which are its
neighbors, one method of doing this is by choosing an optimal radius, and every datapoint
that lies inside of it is its neighbor. Another Method is by choosing K nearest neighbors
i.e K nearest points to our datapoint.



2. Compute the weights:
Next we Want to take our point that we have computed the neighbors Ni for and try
to find the closest reconstruction of it using its neighbors, what this means is
we are practically finding the most "accurate" place for this point to lie in such
that it becomes linearly dependent on its neighbors and no longer goes in a different
dimension.
The following is the Cost function we are trying to minimize such that the weights
are the variables in this case: ^JXEao6F6

You have to take into account the fact that
if the parameters of the neighbor choosing function
is either too low or too high, it will fail and properly
addressing the structure of the neighborhood.

Too big of a neighborhood means it will assume other
areas next to it that are not part of the neighborhood

Too little of a neighborhood means it will not really
reduce the dimensionality of the manifold at all

Remember we want to take regions in the manifold that
are close to locally linear and fit them in a global structure ^TL0GAojh

just right ^lHMmKczW

too small ^Ic5a7qvc

too big ^37Z35Aft

and ^ZuDWkMuY

This Equation shows invariance to
translation because if we translate
one point by a constant and the weights
dont sum up to one (dont describe ratios)
the reconstruction will also be influenced by
the translation ^4J7aVyrt

The weights wij summarize the contribution of the j th data point to
the i th reconstruction ^bvxz85OL

This form gives invariance to Rotations
and Scaling because even if all the xj points
were twice as far apart or upside down, the
weights still describe the ratios of their contribution
(Barycentric coordinates) which will not change the
solution ^arg16uaX

"A consequence of this symmetry is that the reconstruction weights
characterize intrinsic geometric properties of each neighborhood, as opposed to
properties that depend on a particular frame of reference." ^vd1aG4LI

3. Map the point:
Now that we have computed the more optimal weights according to out point through
an optimization problem, we now freeze the weights (Basically memorize the structure of
the neighborhood and its effects on our datapoint) and find the best low dimensional mapping
that still holds this relation as close as possible.
Note that W is a constant here and Y (which is our low dimensional vector representing
the possible new mapping for our points) is variable and we iterate and find the best coordinates
in low dimensions that keep the same angles and ratio of lengths and other intrinsic properties preserved
by the weights. ^gGYRzBAL

Note that the weights of the neighbors of a singular point is independent
from the weights of other datapoints, each datapoint has K amount of weights
describing its neighborhood and we do this exact method for every single point ^lMcOcL5g

We can Derive the following Using the Lagrangian: ^5WGtozXR

because ^5nIRJCyt

matrix of inner
products between
neighbors of i ^8CJcUzda

Comes from the identity that ^DS06XCWW

The solution consists of the p eigenvectors of M orthogonal to 1 ^jTCXa5FI

corresponding to the smallest eigenvalues. ^iFEoDfVR

The columns of Y are these eigenvectors and the new locations (in p
dimensions) are the corresponding rows ^9F4sQLNZ

Limitations of LLE ^Xi8qjB3x

1. Sensitivity to noise:
The weights vectors that capture the high dimensional structure are highly
sensitive to noise which means small perturbation of the input may yield an entirely
different embedding


2. Sensitivity to non-uniform sampling of the manifold:
If sampling from the manifold focuses a lot on one area but draws little to no samples
from another neighborhood/idea then the local structure of that area is not preserved
nor embedded.


3. No mapping:
While we do map points from high dimensions to low, we do not actually get the mapping
in explicit form (though one can be learned in a supervised fashion from the pairs {𝑋𝑖,𝑌𝑖})


4. Complexity:
Quadratic complexity on the training set size O(dn^2)


5. intrinsic dimensionality
Unlike ISOMAP, no robust method to compute the intrinsic dimensionality
which I THINK means that we dont actually know the best low dimensional structure's dimensionality
that best represents this high dimensional manifold??


6. No robust method to define the neighborhood size K, its mostly heuristics ^RLgAtltW

# Element Links
lNSh8Qkr: [[PCA]]

# Embedded files
9175afb22dedfbe72de64655fdb099091ecd3e7b: $$R(X,W) = \sum_{i=1}^n \| x_i - \sum_{j \in N_i} w_{ij} x_j \|^2$$
86673082c71a6297fc53dbc0571481afb457d338: $$\sum_{j \in N_i} w_{ij} = 1$$
4283264771835b4fb41cb96b1bc697618a2c89b6: $$\Phi(Y) = \sum_{i=1}^n \| y_i - \sum_{ j \in N_i} w_{ij} y_j \|^2$$
4e1e6f8654d9a715b5805948854d40e9dfb09fe8: $$\mathcal{L}(W) = \sum_{i=1}^n \| x_i - \sum_{j \in N_i} w_{ij} x_j \|^2 - \lambda_i (1^T w_i - 1)$$
7fef613491413afe444fe6b8914351273d96a3c3: $$R_i(x_i,w_i) = \sum_{i=1}^n \| x_i - \sum_{j \in N_i} w_{ij} x_j \|^2$$
9c16ff432f82627a7cc7502084df1528430e23c9: $$R_i(x_i,w_i) = (x_i - X_i^T w_i)^T (x_i - X_i^T w_i)$$
0df694bf2875206f404258b4bbf8efe42d373ff2: $$R_i(x_i,w_i) = w_i^T (1 x_i^T x_i 1^T - 1 x_i^T X_i^T - X_i x_i 1^T + X_i X_i^T ) w_i$$
0a425e606aa649c42e535f76bff5c71f43453749: $$R_i(x_i,w_i) = w_i^T C w_i$$
5501674b407f17e5695d25ecc168d9a25b5746ca: $$\color{red} w_i^T \cdot \hat{1} = 1$$
1aa1069c00d6d5a01b7aa8d4ee2d9de3b4e39e40: $$\color{red} \sum_1^n w_i = 1$$
17093277e75f7eba6c16b90f952a358c8a544029: $$\frac{\partial \mathcal{L}}{\partial w_i} = 2C w_i - \lambda_i 1$$
29abfe972251be29677c979b05d3303e28d6097a: $$w_i = \frac{ C^{-1} 1 }{1^T C^{-1} 1 }$$
fc53746f0a2516596212dccc83d2c599bfd42c3a: [[Pasted Image 20240419185856_139.png]]
0b2167364772b18c6bad69ace0711b492c028665: [[Pasted Image 20240419185956_150.png]]
63ac52b94a00a31dc1bd7f5998616a22c5b81528: [[Pasted Image 20240419190810_914.png]]
3173027f47d81c54653bd215c48e233de035a2be: [[Pasted Image 20240420161734_778.png]]
830189619a6246c10211a66319c2b5ca4d17ecb2: [[Pasted Image 20240420161819_781.png]]
357bde7fb1a7de684ad70b6b66c198cdd083a550: [[Pasted Image 20240420161834_783.png]]
3a0e5b5d004eac7c67fd838a68b79e17ed8d86a2: [[Pasted Image 20240420161942_798.png]]
5f1490bcb48131c7c4efae1850bdeddfdef95b59: [[Pasted Image 20240420162038_812.png]]
f3d82e26b04fa79ae0d195ccf594e914c513b4fd: [[Pasted Image 20240420162038_818.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.1.4",
	"elements": [
		{
			"type": "freedraw",
			"version": 203,
			"versionNonce": 415568363,
			"isDeleted": false,
			"id": "2BLaZAdEr75uIv6r8cLnO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -851.4522829491448,
			"y": 70.82827105026468,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c07912",
			"width": 1143.6142906697457,
			"height": 2.4332218950420383,
			"seed": 22634232,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097376,
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
					1143.6142906697457,
					-2.4332218950420383
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 1581,
			"versionNonce": 255694405,
			"isDeleted": false,
			"id": "BtFxuOL2-kSvRbTRIYcQJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -571.9355458473484,
			"y": -570.4144186578449,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 330.95299527827603,
			"height": 329.9700644266226,
			"seed": 410267528,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097376,
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
					-31.88958340870537
				],
				[
					10.98599154450709,
					-95.34536502920972
				],
				[
					61.10957796632068,
					-156.56153082781387
				],
				[
					102.99367072975394,
					-184.92999790521583
				],
				[
					160.67012633841614,
					-201.35384726581702
				],
				[
					212.85358617482478,
					-199.1142314439168
				],
				[
					278.08291097033555,
					-159.54768525701405
				],
				[
					311.7275100753886,
					-102.06421249491015
				],
				[
					330.95299527827603,
					-31.143044801405242
				],
				[
					309.6676366607935,
					51.72274060890044
				],
				[
					245.12493633681433,
					113.68544501480464
				],
				[
					186.07523178508873,
					128.6162171608056
				],
				[
					116.72616016038778,
					113.68544501480464
				],
				[
					63.169451380915724,
					60.681203896501
				],
				[
					43.94396617802836,
					-13.972656833504105
				],
				[
					69.34907162470095,
					-93.10574920730946
				],
				[
					123.59240487570469,
					-133.4188340015123
				],
				[
					188.82172967121554,
					-137.15152703801252
				],
				[
					242.37843845068755,
					-100.57113528031006
				],
				[
					267.78354389736023,
					-36.36881505250572
				],
				[
					252.677805523663,
					21.114657709598273
				],
				[
					198.4344722726592,
					59.18812668190084
				],
				[
					140.758016663997,
					53.96235643080049
				],
				[
					111.23316438813421,
					6.93042417089722
				],
				[
					114.66628674579268,
					-52.04612580580668
				],
				[
					162.72999975301119,
					-72.2026682029081
				],
				[
					199.12109674419094,
					-52.79266441310683
				],
				[
					202.55421910184944,
					-10.986502404303936
				],
				[
					183.32873389896207,
					6.93042417089722
				],
				[
					162.72999975301119,
					3.197731134397012
				],
				[
					155.8637550376943,
					-15.465734048104265
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
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 975,
			"versionNonce": 1036098699,
			"isDeleted": false,
			"id": "hooIKVKy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.423931235765323,
			"x": -540.441122891837,
			"y": -728.8860419386674,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 28.929855346679688,
			"height": 60.378554072439954,
			"seed": 25894,
			"groupIds": [
				"I4j9Vyuh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 48.30284325795196,
			"fontFamily": 1,
			"text": "L",
			"rawText": "L",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "L",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 975,
			"versionNonce": 773621157,
			"isDeleted": false,
			"id": "dFeyfUTB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.623597831224306,
			"x": -517.545852914258,
			"y": -749.8158767379402,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 26.756500244140625,
			"height": 60.378554072439954,
			"seed": 37322,
			"groupIds": [
				"I4j9Vyuh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 48.30284325795196,
			"fontFamily": 1,
			"text": "o",
			"rawText": "o",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "o",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 975,
			"versionNonce": 873714475,
			"isDeleted": false,
			"id": "fvSfja5C",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.8082642740954,
			"x": -493.33676344855724,
			"y": -766.1543397011675,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 29.412826538085938,
			"height": 60.378554072439954,
			"seed": 15904,
			"groupIds": [
				"I4j9Vyuh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 48.30284325795196,
			"fontFamily": 1,
			"text": "w",
			"rawText": "w",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "w",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 640059653,
			"isDeleted": false,
			"id": "nHPLtCXx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.103913689486739,
			"x": -434.60045152334095,
			"y": -777.4471283787788,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 32.10191345214844,
			"height": 51.45242550773686,
			"seed": 84135,
			"groupIds": [
				"5O95QWKl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 41.16194040618949,
			"fontFamily": 1,
			"text": "D",
			"rawText": "D",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "D",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 472266187,
			"isDeleted": false,
			"id": "Ih3BF7eL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.07767059278509425,
			"x": -399.8831626639236,
			"y": -786.5409910277898,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 9.013229370117188,
			"height": 51.45242550773685,
			"seed": 91827,
			"groupIds": [
				"5O95QWKl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 41.16194040618948,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 1222189157,
			"isDeleted": false,
			"id": "JJTfTgrP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.14981199329060946,
			"x": -392.95118589999885,
			"y": -780.0069394025948,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 26.051925659179688,
			"height": 51.45242550773685,
			"seed": 60772,
			"groupIds": [
				"5O95QWKl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 41.16194040618948,
			"fontFamily": 1,
			"text": "m",
			"rawText": "m",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "m",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 622019691,
			"isDeleted": false,
			"id": "pBglTV49",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.3583305264362897,
			"x": -367.35759485069195,
			"y": -774.6146341065967,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 22.512496948242188,
			"height": 51.45242550773685,
			"seed": 99273,
			"groupIds": [
				"5O95QWKl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 41.16194040618948,
			"fontFamily": 1,
			"text": "e",
			"rawText": "e",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "e",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 1543621573,
			"isDeleted": false,
			"id": "fQARXgX0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.5385195918085319,
			"x": -346.7046602570799,
			"y": -765.9311940571569,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 19.219985961914062,
			"height": 51.45242550773685,
			"seed": 31129,
			"groupIds": [
				"5O95QWKl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 41.16194040618948,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 916815627,
			"isDeleted": false,
			"id": "LVpqh3yJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.6923554718636789,
			"x": -331.3956438036006,
			"y": -753.8328560626652,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 22.347869873046875,
			"height": 51.45242550773685,
			"seed": 3416,
			"groupIds": [
				"5O95QWKl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 41.16194040618948,
			"fontFamily": 1,
			"text": "s",
			"rawText": "s",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "s",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 264112933,
			"isDeleted": false,
			"id": "bdJ04JeJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.8712267164064178,
			"x": -313.97263175828124,
			"y": -742.4194774206147,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 9.013229370117188,
			"height": 51.45242550773685,
			"seed": 3806,
			"groupIds": [
				"5O95QWKl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 41.16194040618948,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 1532454315,
			"isDeleted": false,
			"id": "xTLIdmNW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.943368116911933,
			"x": -310.0584392753574,
			"y": -730.8595016224631,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 22.800582885742188,
			"height": 51.45242550773685,
			"seed": 37860,
			"groupIds": [
				"5O95QWKl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 41.16194040618948,
			"fontFamily": 1,
			"text": "o",
			"rawText": "o",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "o",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 880500357,
			"isDeleted": false,
			"id": "pVUPz6S7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.1258630545842676,
			"x": -298.0001383332128,
			"y": -712.4411732803766,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 19.219985961914062,
			"height": 51.45242550773685,
			"seed": 87195,
			"groupIds": [
				"5O95QWKl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 41.16194040618948,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 1783855179,
			"isDeleted": false,
			"id": "mas8bOpt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.2796989346394145,
			"x": -292.0682816514126,
			"y": -691.8608501163726,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 27.451248168945312,
			"height": 51.45242550773685,
			"seed": 10152,
			"groupIds": [
				"5O95QWKl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 41.16194040618948,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 821511653,
			"isDeleted": false,
			"id": "adMtCD5L",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.4994174189569698,
			"x": -285.1560355521093,
			"y": -670.2877368758882,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 10.824111938476562,
			"height": 51.45242550773685,
			"seed": 10927,
			"groupIds": [
				"5O95QWKl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 41.16194040618948,
			"fontFamily": 1,
			"text": "l",
			"rawText": "l",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "l",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 387,
			"versionNonce": 1903441643,
			"isDeleted": false,
			"id": "bxYAVmOc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.4061526346023694,
			"x": -418.2951987336096,
			"y": -481.6371073599743,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 10.472305297851562,
			"height": 31.5564827697916,
			"seed": 37621,
			"groupIds": [
				"Ms2Ahhkt"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 25.24518621583328,
			"fontFamily": 1,
			"text": "(",
			"rawText": "(",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 387,
			"versionNonce": 943669573,
			"isDeleted": false,
			"id": "xt13692B",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.472552781086746,
			"x": -432.6648086008115,
			"y": -485.83299147831264,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 15.115447998046875,
			"height": 31.556482769791604,
			"seed": 78996,
			"groupIds": [
				"Ms2Ahhkt"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 25.245186215833282,
			"fontFamily": 1,
			"text": "L",
			"rawText": "L",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "L",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 387,
			"versionNonce": 1598300555,
			"isDeleted": false,
			"id": "C0LdeWQb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.5683929300125268,
			"x": -445.6436159003076,
			"y": -491.1495479507829,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 13.979888916015625,
			"height": 31.5564827697916,
			"seed": 6866,
			"groupIds": [
				"Ms2Ahhkt"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 25.24518621583328,
			"fontFamily": 1,
			"text": "o",
			"rawText": "o",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "o",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 387,
			"versionNonce": 1068552357,
			"isDeleted": false,
			"id": "9y7XH5SM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.6570330667312767,
			"x": -456.8708189486651,
			"y": -497.17813097740014,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 12.667694091796875,
			"height": 31.556482769791593,
			"seed": 46436,
			"groupIds": [
				"Ms2Ahhkt"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 25.245186215833275,
			"fontFamily": 1,
			"text": "c",
			"rawText": "c",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "c",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 387,
			"versionNonce": 1828567083,
			"isDeleted": false,
			"id": "9hNjkfm1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.7373531961258077,
			"x": -471.54073217901464,
			"y": -504.8676514759987,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 16.831390380859375,
			"height": 31.556482769791593,
			"seed": 42249,
			"groupIds": [
				"Ms2Ahhkt"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 25.245186215833275,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 387,
			"versionNonce": 888763397,
			"isDeleted": false,
			"id": "ZcfjP7Gz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.8440734720047143,
			"x": -475.3846286069399,
			"y": -512.5762771184291,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 6.63665771484375,
			"height": 31.5564827697916,
			"seed": 7646,
			"groupIds": [
				"Ms2Ahhkt"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 25.24518621583328,
			"fontFamily": 1,
			"text": "l",
			"rawText": "l",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "l",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 313,
			"versionNonce": 1217100491,
			"isDeleted": false,
			"id": "IePxxiug",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 4.179630193487732,
			"x": -494.1763478421891,
			"y": -537.6789784242666,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 15.667556762695312,
			"height": 32.70215701916803,
			"seed": 85046,
			"groupIds": [
				"cCiXY64s"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 26.16172561533442,
			"fontFamily": 1,
			"text": "L",
			"rawText": "L",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "L",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 313,
			"versionNonce": 1947642725,
			"isDeleted": false,
			"id": "C56Npyo3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 4.307417058722109,
			"x": -495.19571068690743,
			"y": -546.7986257391187,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 5.72821044921875,
			"height": 32.70215701916803,
			"seed": 24694,
			"groupIds": [
				"cCiXY64s"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 26.16172561533442,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 313,
			"versionNonce": 2122836331,
			"isDeleted": false,
			"id": "5dHslA1h",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 4.354137232875754,
			"x": -501.2823104527669,
			"y": -555.2810685019123,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 12.214935302734375,
			"height": 32.70215701916802,
			"seed": 80422,
			"groupIds": [
				"cCiXY64s"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 26.161725615334415,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 313,
			"versionNonce": 2102785733,
			"isDeleted": false,
			"id": "73qMqUYa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 4.4537641046205465,
			"x": -506.26484796167136,
			"y": -567.9384148517781,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 14.30743408203125,
			"height": 32.70215701916802,
			"seed": 76277,
			"groupIds": [
				"cCiXY64s"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097376,
			"link": null,
			"locked": false,
			"fontSize": 26.161725615334415,
			"fontFamily": 1,
			"text": "e",
			"rawText": "e",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "e",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 313,
			"versionNonce": 608011275,
			"isDeleted": false,
			"id": "DHYx3E36",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 4.57045762675596,
			"x": -511.0229686983545,
			"y": -583.4866644933173,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 17.446182250976562,
			"height": 32.70215701916802,
			"seed": 67122,
			"groupIds": [
				"cCiXY64s"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 26.161725615334415,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 313,
			"versionNonce": 1800721957,
			"isDeleted": false,
			"id": "wYDFDFqB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 4.712751327927837,
			"x": -508.4783579195854,
			"y": -597.8529777746252,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 11.247161865234375,
			"height": 32.70215701916803,
			"seed": 92668,
			"groupIds": [
				"cCiXY64s"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 26.16172561533442,
			"fontFamily": 1,
			"text": "r",
			"rawText": "r",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 1101449899,
			"isDeleted": false,
			"id": "osAs2sNh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 4.910357349709887,
			"x": -505.6294633714912,
			"y": -614.7070599268799,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 13.269317626953125,
			"height": 24.6147259191901,
			"seed": 30722,
			"groupIds": [
				"uoX9v4nC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 19.69178073535208,
			"fontFamily": 1,
			"text": "E",
			"rawText": "E",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "E",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 687917445,
			"isDeleted": false,
			"id": "xozyZV0w",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.012861011819261,
			"x": -502.17750232538026,
			"y": -627.2164903570371,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 12.462127685546875,
			"height": 24.614725919190104,
			"seed": 56319,
			"groupIds": [
				"uoX9v4nC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 19.691780735352083,
			"fontFamily": 1,
			"text": "m",
			"rawText": "m",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "m",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 2070822219,
			"isDeleted": false,
			"id": "tA4VCGrO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.109129118915618,
			"x": -497.3687617562063,
			"y": -637.8895664978285,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 10.001205444335938,
			"height": 24.614725919190104,
			"seed": 45431,
			"groupIds": [
				"uoX9v4nC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 19.691780735352083,
			"fontFamily": 1,
			"text": "b",
			"rawText": "b",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "b",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 1737969893,
			"isDeleted": false,
			"id": "hwcM2Pt5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.1863870127958265,
			"x": -493.32751610831366,
			"y": -647.271606658995,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 10.769012451171875,
			"height": 24.614725919190104,
			"seed": 22191,
			"groupIds": [
				"uoX9v4nC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 19.691780735352083,
			"fontFamily": 1,
			"text": "e",
			"rawText": "e",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "e",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 2095995883,
			"isDeleted": false,
			"id": "DM3DflSv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.269576099709887,
			"x": -488.12004691216583,
			"y": -656.8139527061167,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 11.202133178710938,
			"height": 24.614725919190104,
			"seed": 34880,
			"groupIds": [
				"uoX9v4nC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 19.691780735352083,
			"fontFamily": 1,
			"text": "d",
			"rawText": "d",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "d",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 1420160069,
			"isDeleted": false,
			"id": "pjVKLCam",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.356110930439055,
			"x": -481.7960258600788,
			"y": -666.0487386462107,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 11.202133178710938,
			"height": 24.614725919190104,
			"seed": 1209,
			"groupIds": [
				"uoX9v4nC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 19.691780735352083,
			"fontFamily": 1,
			"text": "d",
			"rawText": "d",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "d",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 573679243,
			"isDeleted": false,
			"id": "5vtgCcFw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.442645761168222,
			"x": -473.1413999787715,
			"y": -671.8222394385626,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 4.3115386962890625,
			"height": 24.614725919190104,
			"seed": 84855,
			"groupIds": [
				"uoX9v4nC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 19.691780735352083,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 269097893,
			"isDeleted": false,
			"id": "ifblJc5K",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.475951832131763,
			"x": -471.31659192353584,
			"y": -677.0249759456377,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 9.194015502929688,
			"height": 24.614725919190104,
			"seed": 9400,
			"groupIds": [
				"uoX9v4nC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 19.691780735352083,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 1643289899,
			"isDeleted": false,
			"id": "K0To2aoH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.546974374449469,
			"x": -464.883226697225,
			"y": -683.7116070933652,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 9.863388061523438,
			"height": 24.614725919190104,
			"seed": 33500,
			"groupIds": [
				"uoX9v4nC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 19.691780735352083,
			"fontFamily": 1,
			"text": "g",
			"rawText": "g",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "g",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 1643208453,
			"isDeleted": false,
			"id": "kfr1KfXt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.623167611754159,
			"x": -456.608500402776,
			"y": -688.7052591626567,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 6.6543426513671875,
			"height": 24.614725919190104,
			"seed": 53604,
			"groupIds": [
				"uoX9v4nC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 19.691780735352083,
			"fontFamily": 1,
			"text": ")",
			"rawText": ")",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": ")",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 2006695883,
			"isDeleted": false,
			"id": "zYsvMf2q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.834833720223314,
			"x": -446.0094807754176,
			"y": -689.3192935202035,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 8.050643920898438,
			"height": 20.387500480862112,
			"seed": 80596,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "h",
			"rawText": "h",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "h",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 819541605,
			"isDeleted": false,
			"id": "rursOLfo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.937282062286524,
			"x": -438.8697922713267,
			"y": -691.586559482093,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 10.870010375976562,
			"height": 20.387500480862112,
			"seed": 39868,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 1296535147,
			"isDeleted": false,
			"id": "f4j2kREJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.075607978923598,
			"x": -428.14002311495534,
			"y": -695.4004712851262,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 8.050643920898438,
			"height": 20.387500480862112,
			"seed": 31310,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "h",
			"rawText": "h",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "h",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 932127173,
			"isDeleted": false,
			"id": "ppIKGMXR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.1780563209868085,
			"x": -420.4721890435315,
			"y": -695.8086959529672,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 10.870010375976562,
			"height": 20.387500480862112,
			"seed": 64626,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 633374987,
			"isDeleted": false,
			"id": "xaXve5jT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.03319693044429606,
			"x": -409.3457103006394,
			"y": -697.0158641360608,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 8.1484375,
			"height": 20.38750048086211,
			"seed": 59308,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.310000384689687,
			"fontFamily": 1,
			"text": " ",
			"rawText": " ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 2066784549,
			"isDeleted": false,
			"id": "hc6cHLnO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.1368895573974207,
			"x": -401.20717501531846,
			"y": -696.392822258172,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 7.9202728271484375,
			"height": 20.387500480862112,
			"seed": 87591,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "f",
			"rawText": "f",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 109129643,
			"isDeleted": false,
			"id": "rBZCW1hr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.23767885294074453,
			"x": -393.5616307523539,
			"y": -694.5186556242153,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 9.256622314453125,
			"height": 20.387500480862112,
			"seed": 5718,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "u",
			"rawText": "u",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "u",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 19608709,
			"isDeleted": false,
			"id": "AZbxzvjA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.35547365274543186,
			"x": -384.5494145099203,
			"y": -692.3085378453999,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 7.6106414794921875,
			"height": 20.387500480862112,
			"seed": 11499,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 1639187019,
			"isDeleted": false,
			"id": "DP3B24fa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.452322574087761,
			"x": -377.60707896428806,
			"y": -689.1577994221047,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 8.1484375,
			"height": 20.38750048086211,
			"seed": 40750,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.310000384689687,
			"fontFamily": 1,
			"text": " ",
			"rawText": " ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 1161583589,
			"isDeleted": false,
			"id": "daLz2kNx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.5560152010408865,
			"x": -370.54506058826126,
			"y": -685.0135336311932,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 8.849197387695312,
			"height": 20.387500480862112,
			"seed": 66560,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "s",
			"rawText": "s",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "s",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 3375339,
			"isDeleted": false,
			"id": "L0NYNHev",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.668625341754665,
			"x": -363.4140664103466,
			"y": -679.6080818860113,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 9.924789428710938,
			"height": 20.387500480862112,
			"seed": 84930,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "w",
			"rawText": "w",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "w",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 1869715269,
			"isDeleted": false,
			"id": "3QzREgJE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.7949228936900345,
			"x": -355.4007618274778,
			"y": -674.883983791095,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 3.5690155029296875,
			"height": 20.387500480862112,
			"seed": 10408,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 730475403,
			"isDeleted": false,
			"id": "ooQFJALz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.840340263185773,
			"x": -353.30244250289877,
			"y": -671.250954107461,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 7.0076446533203125,
			"height": 20.387500480862112,
			"seed": 56549,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "r",
			"rawText": "r",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 1244161701,
			"isDeleted": false,
			"id": "XqybOaP9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.9295159556573633,
			"x": -348.5940737299775,
			"y": -666.644427443705,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 4.28607177734375,
			"height": 20.387500480862112,
			"seed": 97306,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "l",
			"rawText": "l",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "l",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 401769003,
			"isDeleted": false,
			"id": "GzgLDQ8t",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.9840583584450053,
			"x": -346.4591056502357,
			"y": -662.1366102980876,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 7.6432342529296875,
			"height": 20.387500480862112,
			"seed": 9302,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "y",
			"rawText": "y",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "y",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 2014202373,
			"isDeleted": false,
			"id": "IB4NAqHr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.081322041417307,
			"x": -342.5931924300419,
			"y": -655.424782977541,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 8.1484375,
			"height": 20.38750048086211,
			"seed": 5468,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.310000384689687,
			"fontFamily": 1,
			"text": " ",
			"rawText": " ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 240583883,
			"isDeleted": false,
			"id": "fsWqlcQB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.1850146683704317,
			"x": -339.2106756108691,
			"y": -647.8376682349185,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 8.849197387695312,
			"height": 20.387500480862112,
			"seed": 83571,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "s",
			"rawText": "s",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "s",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 1780531557,
			"isDeleted": false,
			"id": "iqgi5OOP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.2976248090842102,
			"x": -336.3840890934307,
			"y": -639.3613564011912,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 9.207733154296875,
			"height": 20.387500480862112,
			"seed": 31090,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "t",
			"rawText": "t",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 1448227691,
			"isDeleted": false,
			"id": "Mhz05AUg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.4147973277276762,
			"x": -334.42871465577366,
			"y": -630.3550447027951,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 9.256622314453125,
			"height": 20.387500480862112,
			"seed": 62353,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "u",
			"rawText": "u",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "u",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 363678917,
			"isDeleted": false,
			"id": "rusUotT8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5325921275323635,
			"x": -333.3984692416586,
			"y": -621.546900731209,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 7.9202728271484375,
			"height": 20.387500480862112,
			"seed": 8149,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "f",
			"rawText": "f",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 570,
			"versionNonce": 1613663755,
			"isDeleted": false,
			"id": "pj1r5kk1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.6333814230756882,
			"x": -333.4945690383775,
			"y": -613.6301875704808,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 7.9202728271484375,
			"height": 20.387500480862112,
			"seed": 5107,
			"groupIds": [
				"8BrgLmtO"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"fontSize": 16.31000038468969,
			"fontFamily": 1,
			"text": "f",
			"rawText": "f",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 1143,
			"versionNonce": 1783720997,
			"isDeleted": false,
			"id": "uY-AB8xy2cPaSBSymPoBW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -943.037782183741,
			"y": 29.096088384938753,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 56.393525964058476,
			"height": 46.4724426926037,
			"seed": 965243128,
			"groupIds": [
				"FzOCzbuP9T1MQEuJN0YYC",
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097377,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-17.75351743312945,
					-5.482703913172362
				],
				[
					-35.50703486625898,
					-3.1329736646699176
				],
				[
					-50.64974091216354,
					16.70919287823953
				],
				[
					-52.999471160666,
					32.89622347903407
				],
				[
					-30.024330953086615,
					40.46757650198636
				],
				[
					-15.142706045904482,
					40.98973877943134
				],
				[
					3.3940548033924793,
					31.06865550797662
				],
				[
					3.132973664669898,
					11.748651242512159
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1086,
			"versionNonce": 786863275,
			"isDeleted": false,
			"id": "AJoTXOqJuacnIlWVtOZef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -943.037782183741,
			"y": 28.573926107493776,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 40.4675765019864,
			"height": 30.024330953086654,
			"seed": 2016815608,
			"groupIds": [
				"FzOCzbuP9T1MQEuJN0YYC",
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.364328820354416,
					-4.438379358282382
				],
				[
					-34.46271031136902,
					-3.1329736646699176
				],
				[
					-37.07352169859392,
					12.270813519957146
				],
				[
					-28.980006398196668,
					22.975140207579347
				],
				[
					-12.531894658679592,
					25.58595159480427
				],
				[
					3.394054803392479,
					19.320004265464455
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1275,
			"versionNonce": 133865349,
			"isDeleted": false,
			"id": "akV3WnMio_o8_5R4e2wsL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -959.2248127845353,
			"y": 64.08096097375272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 105.21569890516454,
			"height": 57.43785051894838,
			"seed": 1245302408,
			"groupIds": [
				"88nov16FKO5iRXIByAbLi",
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.709192878239506,
					-15.403787184627063
				],
				[
					45.16703699899125,
					-39.16217080837388
				],
				[
					61.87622987723083,
					-46.99460497004867
				],
				[
					78.32434161674776,
					-48.30001066366113
				],
				[
					102.08272524049465,
					-23.758383623746816
				],
				[
					105.21569890516454,
					-7.3102718842297945
				],
				[
					81.71839642014024,
					6.00486619061733
				],
				[
					34.201629172646605,
					9.137839855287249
				],
				[
					1.044324554890017,
					6.52702846806232
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1224,
			"versionNonce": 35964747,
			"isDeleted": false,
			"id": "QZOYn47J0fryDTOYN8LFw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -958.9637316458129,
			"y": 66.69177236097761,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 104.43245548899704,
			"height": 43.60055016665628,
			"seed": 1348513928,
			"groupIds": [
				"88nov16FKO5iRXIByAbLi",
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.660002132732199,
					-1.5664868323349488
				],
				[
					23.23622134630181,
					0
				],
				[
					40.72865764070883,
					-7.049190745507308
				],
				[
					59.787580767450805,
					-19.32000426546445
				],
				[
					74.93028681335537,
					-33.94054803392404
				],
				[
					86.1567757784225,
					-36.290278282426485
				],
				[
					97.12218360476723,
					-32.896223479034056
				],
				[
					104.43245548899704,
					-16.187030600794536
				],
				[
					98.16650815965724,
					-3.3940548033924016
				],
				[
					73.62488111974292,
					3.3940548033924016
				],
				[
					43.60055016665623,
					6.788109606784803
				],
				[
					13.57621921356961,
					7.310271884229793
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2021,
			"versionNonce": 887514853,
			"isDeleted": false,
			"id": "3Za4qtFD5qjCu2Z0x6hNd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -938.6885975552273,
			"y": 44.91374944586801,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#7e3f09",
			"width": 71.57336079709265,
			"height": 444.9299219699863,
			"seed": 1823188984,
			"groupIds": [
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.011943372808842,
					-80.65356328627603
				],
				[
					-9.614332047370596,
					-139.94194424506168
				],
				[
					-17.359210641085813,
					-188.54773404010223
				],
				[
					-23.234635781145727,
					-234.48287604420642
				],
				[
					-36.58787473582716,
					-382.9708932202644
				],
				[
					-37.12200429401441,
					-408.60911201325274
				],
				[
					-42.730364654980626,
					-427.30364654980684
				],
				[
					-38.72439296857616,
					-438.52036727173925
				],
				[
					-23.50170056023935,
					-444.9299219699863
				],
				[
					-17.092145861992186,
					-442.25927417905
				],
				[
					-10.415526384651471,
					-406.4725937805037
				],
				[
					6.943684256434417,
					-196.29261263381747
				],
				[
					18.42746975746047,
					-112.16720721932423
				],
				[
					20.296923211115846,
					-69.43684256434358
				],
				[
					28.842996142112014,
					-22.700506222958456
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1892,
			"versionNonce": 1078175211,
			"isDeleted": false,
			"id": "xTczb1Fxsh4jA-wMUqN_v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -954.7192319067626,
			"y": -140.1257321258658,
			"strokeColor": "transparent",
			"backgroundColor": "#6e3907",
			"width": 38.95619417247488,
			"height": 130.71308932912822,
			"seed": 1082896264,
			"groupIds": [
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.180377645761509,
					-28.565504650425943
				],
				[
					-4.371273752417802,
					-32.97225704196145
				],
				[
					-2.973854155136713,
					-37.10928945704751
				],
				[
					8.802068631957658,
					-38.284088648564456
				],
				[
					19.386739606787717,
					-39.15788538509447
				],
				[
					20.737420266716757,
					-29.597475413958815
				],
				[
					27.202213587503714,
					27.848941747083792
				],
				[
					32.705310861671215,
					61.578345555572206
				],
				[
					34.58492042005708,
					91.55520394403375
				],
				[
					23.294258382717835,
					41.731498859663645
				],
				[
					15.181287612647502,
					21.174031395864706
				],
				[
					8.97658289475512,
					7.087747040910842
				],
				[
					1.9871050926107854,
					0.5419377525302247
				]
			]
		},
		{
			"type": "line",
			"version": 1116,
			"versionNonce": 329400901,
			"isDeleted": false,
			"id": "6s0Uj-bprFZEo-iVn75dG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -968.8809554080408,
			"y": -360.0370627857776,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 5.008658205317755,
			"height": 27.631795849125538,
			"seed": 207053960,
			"groupIds": [
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.3513170812127435,
					-10.66087028488931
				],
				[
					-2.6573411241050127,
					-27.631795849125538
				]
			]
		},
		{
			"type": "line",
			"version": 1036,
			"versionNonce": 541962379,
			"isDeleted": false,
			"id": "FSEu3OioA4BVwrlpC2Z8I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -950.6939336889641,
			"y": -177.3280702391604,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 7.50748808437264,
			"height": 68.36606170449983,
			"seed": 1537665528,
			"groupIds": [
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.15973378902912658,
					21.24459394088429
				],
				[
					7.347754295343513,
					41.690518936622546
				],
				[
					5.271215037963791,
					68.36606170449983
				]
			]
		},
		{
			"type": "line",
			"version": 935,
			"versionNonce": 420196773,
			"isDeleted": false,
			"id": "kPONxGepUrEJoqV7MgNHx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -936.4563282322488,
			"y": -124.87199618997374,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 5.860615081730783,
			"height": 39.116198336203176,
			"seed": 172565896,
			"groupIds": [
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.860615081730783,
					18.399605489154805
				],
				[
					0,
					39.116198336203176
				]
			]
		},
		{
			"type": "line",
			"version": 1026,
			"versionNonce": 335374123,
			"isDeleted": false,
			"id": "rJt11AaVVYEpvUsOLeG21",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -939.3967007547308,
			"y": -97.05123620768478,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 18.617317945055774,
			"height": 57.00117099226952,
			"seed": 852022664,
			"groupIds": [
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.137181765567941,
					34.01682785022536
				],
				[
					7.814676668295035,
					57.00117099226952
				],
				[
					14.480136179487834,
					32.86761069312315
				],
				[
					0.6895302942613107,
					26.431994613350792
				],
				[
					5.746085785511025,
					42.98072167562257
				]
			]
		},
		{
			"type": "freedraw",
			"version": 938,
			"versionNonce": 1112552709,
			"isDeleted": false,
			"id": "cd7H3z2KQcU9sEWCzOt6a",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -923.5375039867204,
			"y": -30.856327958597603,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 12.411545296703823,
			"height": 41.601661087099934,
			"seed": 1875529976,
			"groupIds": [
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
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
					-2.7581211770453202,
					24.593247161987247
				],
				[
					9.653424119658505,
					41.601661087099934
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
			"version": 957,
			"versionNonce": 1908230603,
			"isDeleted": false,
			"id": "z-k6iv7AR3KbsWnJHHxu8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -938.2705229531839,
			"y": -26.719146193029644,
			"strokeColor": "#90511c",
			"backgroundColor": "#672f14",
			"width": 17.238257356533154,
			"height": 54.243049815224225,
			"seed": 701872776,
			"groupIds": [
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
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
					0.459686862840925,
					23.444030004885047
				],
				[
					6.435616079772336,
					48.26712059829273
				],
				[
					17.238257356533154,
					54.243049815224225
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
			"version": 927,
			"versionNonce": 183323749,
			"isDeleted": false,
			"id": "QN9G7mcy5ypIJTYvxoUZm",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -963.269893526463,
			"y": -393.83260456625476,
			"strokeColor": "#90511c",
			"backgroundColor": "#672f14",
			"width": 8.601221540300148,
			"height": 22.81956735181687,
			"seed": 883068040,
			"groupIds": [
				"IExmmnqaN8keZ5S5JcY6x",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
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
					8.42568640682468,
					12.111924209810491
				],
				[
					8.601221540300148,
					22.81956735181687
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
			"version": 3480,
			"versionNonce": 1588058219,
			"isDeleted": false,
			"id": "D9h6fe2c8HoICWqqmtU0d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.220026921067632,
			"x": -806.8665343643979,
			"y": -180.87680232684113,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c07912",
			"width": 305.8175624320241,
			"height": 194.22866768396145,
			"seed": 27061752,
			"groupIds": [
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-17.70065617697451,
					12.935094898558326
				],
				[
					-43.91124320826377,
					15.658272771939027
				],
				[
					-60.59070768272054,
					8.850328088487274
				],
				[
					-115.05426515033453,
					14.977478303593871
				],
				[
					-149.7747830359384,
					19.402642347837496
				],
				[
					-187.21847879492304,
					22.1258202212182
				],
				[
					-240.32044732584671,
					26.891381499634406
				],
				[
					-265.1694454204455,
					25.870189797116673
				],
				[
					-280.7952303474424,
					20.826378797713677
				],
				[
					-283.7578873449024,
					8.784153384959245
				],
				[
					-285.72298011554983,
					1.1694188987000165
				],
				[
					-278.35388222562165,
					-6.445315587559214
				],
				[
					-280.85134566809006,
					-19.46405519309921
				],
				[
					-279.82770180360734,
					-29.535155642667878
				],
				[
					-284.3313554958824,
					-39.121516386560025
				],
				[
					-290.8813486384997,
					-53.60754208310033
				],
				[
					-278.5724365953876,
					-68.14773223277044
				],
				[
					-291.6182584274925,
					-89.22484855108709
				],
				[
					-291.8844437634028,
					-107.7428552081967
				],
				[
					-302.426268666054,
					-116.98178393648368
				],
				[
					-297.7591733357661,
					-126.31597459705954
				],
				[
					-299.7242661064137,
					-144.9843559182112
				],
				[
					-285.23170692288807,
					-156.28363934943462
				],
				[
					-228.48965317044016,
					-156.77491254209653
				],
				[
					-77.17750983057913,
					-166.35473979900328
				],
				[
					-17.979090114821854,
					-167.33728618432704
				],
				[
					-6.188533490936643,
					-152.59909040447045
				],
				[
					3.3912937659700635,
					-131.47434312000934
				],
				[
					-1.521438160648737,
					-120.42069628511689
				],
				[
					3.1456571696391693,
					-111.82341541353387
				],
				[
					-4.96035050928202,
					-104.45431752360555
				],
				[
					-9.381809243238955,
					-89.96175834007992
				],
				[
					0.6892912063297693,
					-73.74974298223766
				],
				[
					-2.2583479496415726,
					-53.11626889043846
				],
				[
					2.4087473806463335,
					-46.23844419317205
				],
				[
					-2.012711353310678,
					-31.254611816984518
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3317,
			"versionNonce": 581990341,
			"isDeleted": false,
			"id": "B1qyLMDmicbrhbrdthTPJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.220026921067632,
			"x": -806.5394844750883,
			"y": -185.1075716853769,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f0a548",
			"width": 305.8175624320241,
			"height": 194.22866768396145,
			"seed": 945633016,
			"groupIds": [
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-17.70065617697451,
					12.935094898558326
				],
				[
					-43.91124320826377,
					15.658272771939027
				],
				[
					-60.59070768272054,
					8.850328088487274
				],
				[
					-115.05426515033453,
					14.977478303593871
				],
				[
					-149.7747830359384,
					19.402642347837496
				],
				[
					-187.21847879492304,
					22.1258202212182
				],
				[
					-240.32044732584671,
					26.891381499634406
				],
				[
					-265.1694454204455,
					25.870189797116673
				],
				[
					-283.2104988315927,
					20.423834050355268
				],
				[
					-283.7578873449024,
					8.784153384959245
				],
				[
					-285.72298011554983,
					1.1694188987000165
				],
				[
					-278.35388222562165,
					-6.445315587559214
				],
				[
					-283.26661415224044,
					-19.46405519309921
				],
				[
					-279.82770180360734,
					-29.535155642667878
				],
				[
					-289.1618924641831,
					-34.69352416561768
				],
				[
					-290.8813486384997,
					-53.60754208310033
				],
				[
					-281.7927945742548,
					-66.13500849597845
				],
				[
					-291.6182584274925,
					-89.22484855108709
				],
				[
					-293.0920780054782,
					-103.71740773461275
				],
				[
					-302.426268666054,
					-116.98178393648368
				],
				[
					-297.7591733357661,
					-126.31597459705954
				],
				[
					-299.7242661064137,
					-144.9843559182112
				],
				[
					-285.23170692288807,
					-156.28363934943462
				],
				[
					-228.48965317044016,
					-156.77491254209653
				],
				[
					-77.17750983057913,
					-166.35473979900328
				],
				[
					-17.979090114821854,
					-167.33728618432704
				],
				[
					-6.188533490936643,
					-152.59909040447045
				],
				[
					3.3912937659700635,
					-131.47434312000934
				],
				[
					-1.521438160648737,
					-120.42069628511689
				],
				[
					3.1456571696391693,
					-111.82341541353387
				],
				[
					-4.96035050928202,
					-104.45431752360555
				],
				[
					-9.381809243238955,
					-89.96175834007992
				],
				[
					0.6892912063297693,
					-73.74974298223766
				],
				[
					-2.2583479496415726,
					-53.11626889043846
				],
				[
					2.4087473806463335,
					-46.23844419317205
				],
				[
					-2.012711353310678,
					-31.254611816984518
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2322,
			"versionNonce": 2022150923,
			"isDeleted": false,
			"id": "73DCUPdhl0VIuwPOY3ZZm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.220026921067632,
			"x": -1088.7601006759587,
			"y": -164.2945725855585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#bb7b1d",
			"width": 31.300177563201313,
			"height": 178.73059064401133,
			"seed": 1907711224,
			"groupIds": [
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.644541223112527,
					-9.004160668866174
				],
				[
					3.4301564452822793,
					-19.294630004713223
				],
				[
					-0.857539111320685,
					-30.442638451880857
				],
				[
					2.143847778301405,
					-41.161877343388184
				],
				[
					-7.93223677971549,
					-49.30849890093378
				],
				[
					-7.503467224055148,
					-68.603128905647
				],
				[
					1.0719238891506255,
					-78.25044390800359
				],
				[
					-9.432930224526459,
					-100.76084558016905
				],
				[
					-10.07608455801705,
					-115.12462569478889
				],
				[
					-19.509014782543357,
					-125.84386458629623
				],
				[
					-16.344114602585638,
					-138.9501028326526
				],
				[
					-18.008321337732387,
					-156.2865030381771
				],
				[
					-10.492169798064358,
					-166.41750764542465
				],
				[
					-1.2863086669810275,
					-167.43451148534473
				],
				[
					-8.575391113205928,
					-154.14265525987562
				],
				[
					-5.574004223583837,
					-137.42064258912416
				],
				[
					-8.789775891036022,
					-126.91578847544697
				],
				[
					-3.215771667452185,
					-118.12601258441094
				],
				[
					-1.2863086669810275,
					-101.83276946931979
				],
				[
					8.789775891036022,
					-88.11214368819039
				],
				[
					7.932236779715336,
					-73.31959401791028
				],
				[
					1.7150782226410626,
					-60.456507348101454
				],
				[
					5.574004223583837,
					-45.02080334433087
				],
				[
					10.076084558016895,
					-39.01802956508674
				],
				[
					7.2890824462249,
					-24.43986467263675
				],
				[
					11.791162780657958,
					-15.006934448110297
				],
				[
					7.2445401974755335,
					-0.40190208717083953
				],
				[
					8.767671202258871,
					11.29607915866659
				],
				[
					0.28069884416123464,
					9.196440757919273
				],
				[
					-1.0719238891507794,
					2.5726173339617477
				]
			]
		},
		{
			"type": "line",
			"version": 2164,
			"versionNonce": 1672951589,
			"isDeleted": false,
			"id": "VEy48V5_PsHMob8m8-BQn",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -959.519122633083,
			"y": -333.2138176888519,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#bfc2c9",
			"width": 5.426024661304821,
			"height": 10.632499191805433,
			"seed": 622445304,
			"groupIds": [
				"aWWv-8OLZpTi7PModToEI",
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.202816789681198,
					-4.140088180879992
				],
				[
					3.3559805708648356,
					-8.24881205735937
				],
				[
					2.070044090439985,
					-10.632499191805433
				],
				[
					1.5054866112290841,
					-8.53109079696483
				],
				[
					1.8191296552351375,
					-4.296909702883042
				],
				[
					-1.2232078716236223,
					-1.5368509156296986
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2372,
			"versionNonce": 1071053227,
			"isDeleted": false,
			"id": "tXjVWSEutsykwB-AIFL1u",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -955.1897372418989,
			"y": -337.1866973412847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 4.973686781299601,
			"height": 6.01167358783171,
			"seed": 735486968,
			"groupIds": [
				"aWWv-8OLZpTi7PModToEI",
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.2057219638806824,
					-0.518993403266043
				],
				[
					4.368194477489194,
					1.5137307595260037
				],
				[
					4.973686781299601,
					4.32494502721707
				],
				[
					3.4599560217736194,
					5.492680184565667
				],
				[
					3.027461519051917,
					4.49794282830575
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 2283,
			"versionNonce": 141494917,
			"isDeleted": false,
			"id": "jAtMGW_mR-5XiLG0uZSYb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.695950991298414,
			"x": -955.5028146637769,
			"y": -335.24830579769844,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d8de",
			"width": 6.670430764132693,
			"height": 3.5182225179989377,
			"seed": 1783588088,
			"groupIds": [
				"aWWv-8OLZpTi7PModToEI",
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1742,
			"versionNonce": 1103137867,
			"isDeleted": false,
			"id": "Yn-HF6jr8YAO2QRu-S7tR",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -955.032015852461,
			"y": -334.4012606773582,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.6666814751545241,
			"height": 0.4814921765004809,
			"seed": 1040713208,
			"groupIds": [
				"aWWv-8OLZpTi7PModToEI",
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.6666814751545241,
					-0.4814921765004809
				]
			]
		},
		{
			"type": "line",
			"version": 1750,
			"versionNonce": 563442149,
			"isDeleted": false,
			"id": "YuwlGRcT-IUaeN1lLOdKb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -954.4890668953797,
			"y": -335.063146023399,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.6666814751545241,
			"height": 0.4814921765004809,
			"seed": 872711928,
			"groupIds": [
				"aWWv-8OLZpTi7PModToEI",
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.6666814751545241,
					-0.4814921765004809
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1755,
			"versionNonce": 35572459,
			"isDeleted": false,
			"id": "3uh2fJjDD_vZlpYkPxj0x",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.163527388836053,
			"x": -951.8797745582144,
			"y": -335.0378195730567,
			"strokeColor": "transparent",
			"backgroundColor": "#f8f9fb",
			"width": 1.6667036878862538,
			"height": 2.3387770275322306,
			"seed": 415819768,
			"groupIds": [
				"aWWv-8OLZpTi7PModToEI",
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2636,
			"versionNonce": 1278733637,
			"isDeleted": false,
			"id": "_or1JuoI5KDeWljOK47z0",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -958.6742340841456,
			"y": -333.2316327834286,
			"strokeColor": "transparent",
			"backgroundColor": "#9ca2ad",
			"width": 3.198061834911493,
			"height": 9.396517805258984,
			"seed": 140060920,
			"groupIds": [
				"aWWv-8OLZpTi7PModToEI",
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.7517199591123069,
					-1.4784874295462835
				],
				[
					1.775179638584506,
					-3.7878865418748497
				],
				[
					1.4864677651653642,
					-7.7091702722187865
				],
				[
					1.5898329690400816,
					-9.396517805258984
				],
				[
					2.4463418757991864,
					-4.2555717680944944
				],
				[
					0.08713944846588133,
					-1.533204131809716
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1658,
			"versionNonce": 628897163,
			"isDeleted": false,
			"id": "IpiWWngK2vajXexlmMoUJ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -963.6305732989085,
			"y": -339.6295925682151,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9ca2ad",
			"width": 3.362953183325707,
			"height": 0.5553565525015296,
			"seed": 2117683704,
			"groupIds": [
				"aWWv-8OLZpTi7PModToEI",
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.3214884862061644,
					0.4301571628676903
				],
				[
					2.3907854514410953,
					0.09830638055352761
				],
				[
					3.362953183325707,
					0.5553565525015296
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1570,
			"versionNonce": 666107045,
			"isDeleted": false,
			"id": "l82Bb8CTdKveMT1JaOkss",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -965.1648349532261,
			"y": -340.48658526218617,
			"strokeColor": "#f0a548",
			"backgroundColor": "#f0a548",
			"width": 2.926645244721573,
			"height": 2.7684482044663405,
			"seed": 1701661432,
			"groupIds": [
				"aWWv-8OLZpTi7PModToEI",
				"is8WsPtoqVSG3z1jBoduF",
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 907,
			"versionNonce": 1527991339,
			"isDeleted": false,
			"id": "8kGAQCjzLKl0XDw6ByzOH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -1048.5928517020543,
			"y": -252.8764556241507,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 56.97428011140819,
			"height": 18.25389556967448,
			"seed": 408404104,
			"groupIds": [
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					23.785379075636456,
					-18.25389556967448
				],
				[
					56.97428011140819,
					-11.616115362520128
				]
			]
		},
		{
			"type": "line",
			"version": 1076,
			"versionNonce": 196550661,
			"isDeleted": false,
			"id": "auDCIpsM6VOy9fWL8aqUw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -935.1974398298341,
			"y": -279.9807248033643,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 112.2891151710279,
			"height": 30.423159282790852,
			"seed": 1926004104,
			"groupIds": [
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					42.03927464531101,
					4.978335155365775
				],
				[
					87.95058774479531,
					-13.275560414308707
				],
				[
					112.2891151710279,
					5.5314835059619805
				],
				[
					66.9309504221398,
					17.147598868482145
				],
				[
					85.18484599181429,
					0.5531483505962057
				]
			]
		},
		{
			"type": "line",
			"version": 1016,
			"versionNonce": 114200267,
			"isDeleted": false,
			"id": "3A_geAyu8kwUcUTROz6TL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -946.2604068417581,
			"y": -247.8981204687849,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 114.50170857341273,
			"height": 70.80298887631317,
			"seed": 159035384,
			"groupIds": [
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-35.95464278875283,
					21.572785673251634
				],
				[
					-95.69466465314204,
					23.785379075636456
				],
				[
					-114.50170857341273,
					53.10224165723489
				],
				[
					-74.67502733048654,
					70.80298887631317
				],
				[
					-61.39946691617791,
					49.230203203061535
				],
				[
					-89.05688444598772,
					50.33649990425387
				]
			]
		},
		{
			"type": "freedraw",
			"version": 950,
			"versionNonce": 2118047589,
			"isDeleted": false,
			"id": "AD4RjKyd8BEGAngDxgNg8",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -975.968634654553,
			"y": -198.114768915127,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 153.77524146574262,
			"height": 18.807043920270683,
			"seed": 1528071928,
			"groupIds": [
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
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
					57.527428462004465,
					7.744076908346724
				],
				[
					86.29114269300669,
					-11.06296701192396
				],
				[
					136.07449424666433,
					1.6594450517885397
				],
				[
					153.77524146574262,
					-9.956670310731548
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
			"version": 966,
			"versionNonce": 726170987,
			"isDeleted": false,
			"id": "ORpHMGhO5wljU6zeykB8P",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -833.256360200734,
			"y": -233.51626335328365,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 100.11985145791161,
			"height": 13.275560414308707,
			"seed": 1548499592,
			"groupIds": [
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
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
					-42.59242299590714,
					-13.275560414308707
				],
				[
					-66.37780207154361,
					-4.978335155365775
				],
				[
					-100.11985145791161,
					-4.425186804769568
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
			"version": 936,
			"versionNonce": 1771610821,
			"isDeleted": false,
			"id": "reUNHjp4MIfi9_fgzh96W",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -941.1202885669923,
			"y": -324.78574120165626,
			"strokeColor": "#d4831a",
			"backgroundColor": "#c07912",
			"width": 107.86392836625842,
			"height": 17.700747219078274,
			"seed": 1007476104,
			"groupIds": [
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
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
					34.84834608756042,
					-14.381857115501115
				],
				[
					79.10021413525618,
					-3.3188901035771567
				],
				[
					107.86392836625842,
					-17.700747219078274
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
			"version": 990,
			"versionNonce": 332109835,
			"isDeleted": false,
			"id": "TSTQDjnX2pFffLXyLxGrj",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -1076.6416344630607,
			"y": -303.21295552840445,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 144.92486785620343,
			"height": 13.82870876490491,
			"seed": 1862617592,
			"groupIds": [
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
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
					58.0805768126006,
					-13.82870876490491
				],
				[
					100.11985145791154,
					-3.318890103577157
				],
				[
					144.92486785620343,
					-8.850373609539137
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
			"version": 922,
			"versionNonce": 308412965,
			"isDeleted": false,
			"id": "J_vOTH6Fr2-e2EhSOhMPQ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -1074.6376917106186,
			"y": -267.17809545214925,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 102.5239074520469,
			"height": 30.268963152509066,
			"seed": 334597768,
			"groupIds": [
				"dK6ovruSd_0y0XSyzvlTW",
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
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
					46.86807197807853,
					-30.268963152509066
				],
				[
					102.5239074520469,
					-17.57552699177947
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
			"version": 1376,
			"versionNonce": 1045585579,
			"isDeleted": false,
			"id": "lNSh8Qkr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.144790679881554,
			"x": -1079.208924821647,
			"y": -322.94854711699315,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c07912",
			"width": 264.13043212890625,
			"height": 134.27665020060505,
			"seed": 964254200,
			"groupIds": [
				"_UI7bXr0n1J5Vt5Glx9jZ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": "[[PCA]]",
			"locked": false,
			"fontSize": 13.427665020060505,
			"fontFamily": 1,
			"text": "We have previously discussed motivation\nbehind wanting to do low dimensional\nembedding in order to get all the\nimportant details of the data without\nlosing much in cases that\nhave very high dimensional data like\nhigh resolution images.\nRefresh on this by reading PCA",
			"rawText": "We have previously discussed motivation\nbehind wanting to do low dimensional\nembedding in order to get all the\nimportant details of the data without\nlosing much in cases that\nhave very high dimensional data like\nhigh resolution images.\nRefresh on this by reading PCA",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We have previously discussed motivation\nbehind wanting to do low dimensional\nembedding in order to get all the\nimportant details of the data without\nlosing much in cases that\nhave very high dimensional data like\nhigh resolution images.\nRefresh on this by reading PCA",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 430,
			"versionNonce": 1300788613,
			"isDeleted": false,
			"id": "sWo8zyCe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.6637351197519585,
			"x": -275.3899847391026,
			"y": -610.6319803950121,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 23.010757446289062,
			"height": 42.69104093763425,
			"seed": 2092,
			"groupIds": [
				"VI7gcO2I"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"fontSize": 34.1528327501074,
			"fontFamily": 1,
			"text": "E",
			"rawText": "E",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "E",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 430,
			"versionNonce": 92754251,
			"isDeleted": false,
			"id": "3lQ48qMM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.8352995340364053,
			"x": -278.3315837925652,
			"y": -588.5475061353818,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 21.610992431640625,
			"height": 42.69104093763424,
			"seed": 73785,
			"groupIds": [
				"VI7gcO2I"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"fontSize": 34.15283275010739,
			"fontFamily": 1,
			"text": "m",
			"rawText": "m",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "m",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 430,
			"versionNonce": 1984527589,
			"isDeleted": false,
			"id": "tmHCm9Ag",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.9964274914671591,
			"x": -282.1440467320565,
			"y": -569.8720368784013,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 17.343414306640625,
			"height": 42.69104093763425,
			"seed": 86367,
			"groupIds": [
				"VI7gcO2I"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"fontSize": 34.1528327501074,
			"fontFamily": 1,
			"text": "b",
			"rawText": "b",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "b",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 430,
			"versionNonce": 180678635,
			"isDeleted": false,
			"id": "OVEWTv5c",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 2.1257371283634647,
			"x": -291.3975963065933,
			"y": -554.0629481294627,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 18.674896240234375,
			"height": 42.69104093763424,
			"seed": 12333,
			"groupIds": [
				"VI7gcO2I"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"fontSize": 34.15283275010739,
			"fontFamily": 1,
			"text": "e",
			"rawText": "e",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "e",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 429,
			"versionNonce": 607295557,
			"isDeleted": false,
			"id": "8SLjonbF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 2.2649741334238342,
			"x": -302.9273593287087,
			"y": -538.6303452062944,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 19.425994873046875,
			"height": 42.69104093763424,
			"seed": 38486,
			"groupIds": [
				"VI7gcO2I"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"fontSize": 34.15283275010739,
			"fontFamily": 1,
			"text": "d",
			"rawText": "d",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "d",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 429,
			"versionNonce": 1612036747,
			"isDeleted": false,
			"id": "Vyg8mZ9e",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 2.4098111140701413,
			"x": -316.3960426848414,
			"y": -524.6454219721561,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 19.425994873046875,
			"height": 42.69104093763424,
			"seed": 37362,
			"groupIds": [
				"VI7gcO2I"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"fontSize": 34.15283275010739,
			"fontFamily": 1,
			"text": "d",
			"rawText": "d",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "d",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 429,
			"versionNonce": 555829157,
			"isDeleted": false,
			"id": "uHzlBGNn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 2.5546480947164483,
			"x": -321.96339582933854,
			"y": -517.3624640821182,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 7.4767913818359375,
			"height": 42.69104093763424,
			"seed": 21124,
			"groupIds": [
				"VI7gcO2I"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"fontSize": 34.15283275010739,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 429,
			"versionNonce": 1916023083,
			"isDeleted": false,
			"id": "klsH1tTv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 2.6103937223798006,
			"x": -335.23224911656087,
			"y": -510.12822226340813,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 15.943649291992188,
			"height": 42.69104093763425,
			"seed": 62638,
			"groupIds": [
				"VI7gcO2I"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097378,
			"link": null,
			"locked": false,
			"fontSize": 34.1528327501074,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 429,
			"versionNonce": 524487429,
			"isDeleted": false,
			"id": "j1XFZDx6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 2.729266902422413,
			"x": -350.38108641981574,
			"y": -502.4361746101131,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 17.10443115234375,
			"height": 42.69104093763424,
			"seed": 53554,
			"groupIds": [
				"VI7gcO2I"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"fontSize": 34.15283275010739,
			"fontFamily": 1,
			"text": "g",
			"rawText": "g",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "g",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 63,
			"versionNonce": 847958987,
			"isDeleted": false,
			"id": "TMdTvZVe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -488.3389565127892,
			"y": -421.89916269574286,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c07912",
			"width": 188.66477966308594,
			"height": 35,
			"seed": 1486226936,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "General goals",
			"rawText": "General goals",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "General goals",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 884,
			"versionNonce": 789930597,
			"isDeleted": false,
			"id": "DckulMmW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -796.2732213374065,
			"y": -364.5848919523395,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c07912",
			"width": 823.9990844726562,
			"height": 425,
			"seed": 369730696,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1. Visualization:\nHigh dimensional structures and relations are often intriguing yet not\nintuitive to our problems, being able to visualize a structure of sorts that\nis not in 1000th dimension can be quite useful to draw insights from it.\n\n2. Better Generalization:\nFewer dimensions in some cases mean less chances of overfitting and for your\nmodel to obsess over little \"noise\" details and attributes, which results in a\nmore general result.\n\n3. Speed Up:\nMost algorithms scale horribly with dimensionality, it would be useful to have data\nthat produces similar results but is much easier to compute.\n\n4. Data compression:\nFor larger datasets, its useful to minimize on storage usage as it can quickly get\nout of hand",
			"rawText": "1. Visualization:\nHigh dimensional structures and relations are often intriguing yet not\nintuitive to our problems, being able to visualize a structure of sorts that\nis not in 1000th dimension can be quite useful to draw insights from it.\n\n2. Better Generalization:\nFewer dimensions in some cases mean less chances of overfitting and for your\nmodel to obsess over little \"noise\" details and attributes, which results in a\nmore general result.\n\n3. Speed Up:\nMost algorithms scale horribly with dimensionality, it would be useful to have data\nthat produces similar results but is much easier to compute.\n\n4. Data compression:\nFor larger datasets, its useful to minimize on storage usage as it can quickly get\nout of hand",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Visualization:\nHigh dimensional structures and relations are often intriguing yet not\nintuitive to our problems, being able to visualize a structure of sorts that\nis not in 1000th dimension can be quite useful to draw insights from it.\n\n2. Better Generalization:\nFewer dimensions in some cases mean less chances of overfitting and for your\nmodel to obsess over little \"noise\" details and attributes, which results in a\nmore general result.\n\n3. Speed Up:\nMost algorithms scale horribly with dimensionality, it would be useful to have data\nthat produces similar results but is much easier to compute.\n\n4. Data compression:\nFor larger datasets, its useful to minimize on storage usage as it can quickly get\nout of hand",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 2793,
			"versionNonce": 20193899,
			"isDeleted": false,
			"id": "bgesQsAeQseLH30VMygsc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 65.12837405630503,
			"y": -282.92754937623823,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.173685612569344,
			"height": 36.976042315380084,
			"seed": 1364270472,
			"groupIds": [
				"k3al7b8AuupTavW3kHBCx",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2857,
			"versionNonce": 1969606085,
			"isDeleted": false,
			"id": "08aNJ0huOkoh9rwo5FlEs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 86.51752022996698,
			"y": -246.1572102790292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 1.9712530443849101,
			"height": 44.82719709330239,
			"seed": 1801727112,
			"groupIds": [
				"k3al7b8AuupTavW3kHBCx",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.9712530443849101,
					44.82719709330239
				]
			]
		},
		{
			"type": "line",
			"version": 2826,
			"versionNonce": 1459264779,
			"isDeleted": false,
			"id": "ToHpjiDP8Y0dgl8VkXBoD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 88.70393763229916,
			"y": -199.53123863382655,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 1.923971872410506,
			"height": 27.337969224322613,
			"seed": 238902152,
			"groupIds": [
				"k3al7b8AuupTavW3kHBCx",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.923971872410506,
					27.337969224322613
				]
			]
		},
		{
			"type": "line",
			"version": 2845,
			"versionNonce": 559009061,
			"isDeleted": false,
			"id": "CJ_XXMnb1xrVDGvBqGP2l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 89.06688601840733,
			"y": -200.31500821861948,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 5.627366540375309,
			"height": 25.860016810105815,
			"seed": 2081991304,
			"groupIds": [
				"k3al7b8AuupTavW3kHBCx",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.627366540375309,
					25.860016810105815
				]
			]
		},
		{
			"type": "line",
			"version": 3017,
			"versionNonce": 794346411,
			"isDeleted": false,
			"id": "mMWKgQB6RlzNdUa_44Ja-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 107.17089608419982,
			"y": -234.36863785548292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 20.783279665813964,
			"height": 17.45772961141449,
			"seed": 1963049864,
			"groupIds": [
				"k3al7b8AuupTavW3kHBCx",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.6916190508120525,
					2.757998025732947
				],
				[
					-8.419936579557435,
					15.305741183937112
				],
				[
					-16.330470309729645,
					-2.1519884274773786
				],
				[
					-20.783279665813964,
					1.1724688959150322
				]
			]
		},
		{
			"type": "line",
			"version": 3057,
			"versionNonce": 575070341,
			"isDeleted": false,
			"id": "UUb93ZZx92pvbyyC9-aTr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 87.38741350039462,
			"y": -233.50625282951478,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 24.08682515105723,
			"height": 16.91217556105779,
			"seed": 576517624,
			"groupIds": [
				"k3al7b8AuupTavW3kHBCx",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.275852531631674,
					-3.2871504786239023
				],
				[
					-12.368055186268842,
					13.625025082433888
				],
				[
					-20.278588916441024,
					0.8045048990513669
				],
				[
					-24.08682515105723,
					-1.2738074209641477
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1695,
			"versionNonce": 846796363,
			"isDeleted": false,
			"id": "x_CMe9msYL4Lyqdwh_giK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 94.2849534659967,
			"y": -267.4071804366534,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6866703859883223,
			"height": 0.9016883856412318,
			"seed": 1838110600,
			"groupIds": [
				"k3al7b8AuupTavW3kHBCx",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1696,
			"versionNonce": 503482341,
			"isDeleted": false,
			"id": "w7w9jcQ2WUkfKjKkHqwjf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 76.21303739838709,
			"y": -265.8500339552959,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.693606450493255,
			"height": 1.1791309658385334,
			"seed": 399189640,
			"groupIds": [
				"k3al7b8AuupTavW3kHBCx",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 871,
			"versionNonce": 523637995,
			"isDeleted": false,
			"id": "5Ctb_9qxLA7LU6DqrNw2c",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 71.59300947312764,
			"y": -267.11273202082396,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.16773583499152,
			"height": 4.119410361696672,
			"seed": 1203049864,
			"groupIds": [
				"k3al7b8AuupTavW3kHBCx",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.324970426486695,
					-4.119410361696672
				],
				[
					9.16773583499152,
					-1.529523333173052
				]
			]
		},
		{
			"type": "line",
			"version": 657,
			"versionNonce": 647119685,
			"isDeleted": false,
			"id": "DEzGPtIt9SsH6-IWogY2g",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 96.43851201142604,
			"y": -272.7493046757204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.214046615081732,
			"height": 3.113658722138017,
			"seed": 1653154952,
			"groupIds": [
				"k3al7b8AuupTavW3kHBCx",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.214046615081732,
					3.113658722138017
				]
			]
		},
		{
			"type": "line",
			"version": 1748,
			"versionNonce": 1964654475,
			"isDeleted": false,
			"id": "GSJJVTj7pjq4uAh7qBXvH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 143.89060148388126,
			"y": -277.6071810966546,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 151.85223567727758,
			"height": 90.82215640447058,
			"seed": 656793480,
			"groupIds": [
				"UnB9g9Umow0xJi1SKp8Zr",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.590377477792487,
					9.866804949700338
				],
				[
					-25.487837333092088,
					18.18820671450787
				],
				[
					-18.271401461674444,
					2.734174865579604
				],
				[
					-12.89745985529962,
					-7.132630084120734
				],
				[
					-27.637413975642023,
					-12.006593974936543
				],
				[
					-33.47197914827754,
					-24.726450958285156
				],
				[
					-28.098037541902727,
					-38.991711126526624
				],
				[
					-10.74788321274969,
					-46.4809727148534
				],
				[
					-5.834565172635546,
					-59.67633837047674
				],
				[
					8.137683003939031,
					-68.35437163949034
				],
				[
					29.786990618191936,
					-67.28447712687218
				],
				[
					46.522980192330806,
					-72.6339496899627
				],
				[
					64.33375808774457,
					-72.158441017688
				],
				[
					80.6091240956226,
					-65.85795111004803
				],
				[
					94.27428989469006,
					-50.403919261119775
				],
				[
					110.39611471381455,
					-46.00546404257868
				],
				[
					118.38025652900002,
					-34.117747235710816
				],
				[
					115.46297394268232,
					-18.54483821871387
				],
				[
					99.955313878572,
					-9.866804949700288
				],
				[
					92.27825444089368,
					2.6152976975109254
				],
				[
					71.24311158165504,
					9.985682117769016
				],
				[
					49.4402627786486,
					4.160700882403766
				],
				[
					35.46801460207402,
					11.531085302661864
				],
				[
					14.125789365328266,
					10.936699462318458
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 421,
			"versionNonce": 810783397,
			"isDeleted": false,
			"id": "737N6O29",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 143.57730120109917,
			"y": -336.32109338934515,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c07912",
			"width": 83.23213195800781,
			"height": 56.10641827624761,
			"seed": 304677368,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"fontSize": 11.221283655249522,
			"fontFamily": 1,
			"text": "Okay but we\nalready know\nPCA, Why not\njust use that?",
			"rawText": "Okay but we\nalready know\nPCA, Why not\njust use that?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Okay but we\nalready know\nPCA, Why not\njust use that?",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 353,
			"versionNonce": 1583355435,
			"isDeleted": false,
			"id": "epHDeO6lWcHj6Q4vRoBpL",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 59.22687554095233,
			"y": -401.56712252524864,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 257.7800264429359,
			"height": 234.67709954474816,
			"seed": 1203986424,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 2848,
			"versionNonce": 1207170565,
			"isDeleted": false,
			"id": "l8hKcRwix6NwvRbi6TR2V",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 330.3853113074382,
			"y": -288.0755232876063,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.173685612569344,
			"height": 36.976042315380084,
			"seed": 205241080,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2912,
			"versionNonce": 1509038283,
			"isDeleted": false,
			"id": "qD1gghNb8ggxzEZA7R4y8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 351.7744574811001,
			"y": -251.3051841903973,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 1.9712530443849101,
			"height": 44.82719709330239,
			"seed": 1274649592,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.9712530443849101,
					44.82719709330239
				]
			]
		},
		{
			"type": "line",
			"version": 2881,
			"versionNonce": 141618533,
			"isDeleted": false,
			"id": "9zPeXtuCYAqsANqjMHgeb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 353.9608748834323,
			"y": -204.67921254519464,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 1.923971872410506,
			"height": 27.337969224322613,
			"seed": 2069060856,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.923971872410506,
					27.337969224322613
				]
			]
		},
		{
			"type": "line",
			"version": 2900,
			"versionNonce": 627754859,
			"isDeleted": false,
			"id": "_00_WfErOVy-hJNYUQc8d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 354.32382326954047,
			"y": -205.46298212998758,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 5.627366540375309,
			"height": 25.860016810105815,
			"seed": 2077031928,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.627366540375309,
					25.860016810105815
				]
			]
		},
		{
			"type": "line",
			"version": 3255,
			"versionNonce": 1360525509,
			"isDeleted": false,
			"id": "NCjchO-ktc_J35U-kDi3m",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 347.1807992681831,
			"y": -232.4144162798805,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.066920243665152,
			"height": 12.55074784443251,
			"seed": 1584037624,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.392411139826322,
					-1.4367637291542508
				],
				[
					14.066920243665152,
					3.2965639299846146
				],
				[
					9.069906937638468,
					-9.254183914447895
				],
				[
					4.617097581554148,
					-5.929726591055483
				]
			]
		},
		{
			"type": "line",
			"version": 3352,
			"versionNonce": 1729405451,
			"isDeleted": false,
			"id": "PqUfq0-MfuZ6JH9P5b-Xe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 352.6443507515278,
			"y": -238.65422674088288,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.34957067230323,
			"height": 12.771909695166771,
			"seed": 1940905976,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.275852531631674,
					-3.2871504786239023
				],
				[
					-8.381132500596038,
					9.48475921654287
				],
				[
					0.882769953668685,
					4.484741224287802
				],
				[
					5.9684381717071915,
					7.160067491036131
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1750,
			"versionNonce": 998676517,
			"isDeleted": false,
			"id": "nR9wZqZvhcHkZ0NHpQqGy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 359.5418907171299,
			"y": -272.55515434802146,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6866703859883223,
			"height": 0.9016883856412318,
			"seed": 1537286392,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1751,
			"versionNonce": 401221803,
			"isDeleted": false,
			"id": "O0g1UTm4lKzoMOF-82bF3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 341.4699746495202,
			"y": -270.998007866664,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.693606450493255,
			"height": 1.1791309658385334,
			"seed": 365052408,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 926,
			"versionNonce": 1370114949,
			"isDeleted": false,
			"id": "_eqN5vaiXJZVIXgutlPrc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 336.8499467242608,
			"y": -272.2607059321921,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.16773583499152,
			"height": 4.119410361696672,
			"seed": 286737144,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.324970426486695,
					-4.119410361696672
				],
				[
					9.16773583499152,
					-1.529523333173052
				]
			]
		},
		{
			"type": "line",
			"version": 712,
			"versionNonce": 764795723,
			"isDeleted": false,
			"id": "gSYQnJefnVkiLA2eGj9lk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 361.6954492625592,
			"y": -277.8972785870884,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.214046615081732,
			"height": 3.113658722138017,
			"seed": 1009001464,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.214046615081732,
					3.113658722138017
				]
			]
		},
		{
			"type": "line",
			"version": 1861,
			"versionNonce": 62952165,
			"isDeleted": false,
			"id": "tP6ujxgB87oAxYqXn0FYo",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 521.1219539726653,
			"y": -360.41572480191695,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 203.04166318083622,
			"height": 135.11413738060543,
			"seed": 351069432,
			"groupIds": [
				"ashj6Tkajl9wwpUHNNiRb",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.834596947248315,
					-14.678630108102423
				],
				[
					34.07979382003926,
					-27.058197669152683
				],
				[
					24.43069556978716,
					-4.0675721986307805
				],
				[
					17.245196872790956,
					10.611057909471644
				],
				[
					36.953993298837744,
					17.861947480943893
				],
				[
					44.7553918841479,
					36.78500075283495
				],
				[
					37.569893187151706,
					58.007116571778226
				],
				[
					14.370997393992468,
					69.14872737672346
				],
				[
					7.801398585310196,
					88.77918450924598
				],
				[
					-10.88089802687999,
					101.68930496576986
				],
				[
					-39.828192777636204,
					100.09764627934904
				],
				[
					-62.20588871971028,
					108.05593971145272
				],
				[
					-86.02068440118352,
					107.3485358508213
				],
				[
					-107.78248045494345,
					97.97543469745472
				],
				[
					-126.054177141591,
					74.98480922693282
				],
				[
					-147.61067323257967,
					68.44132351609201
				],
				[
					-158.28627129668834,
					50.75622700030597
				],
				[
					-154.38557200403332,
					27.588750564626213
				],
				[
					-133.65027576412984,
					14.67863010810235
				],
				[
					-123.38527762556382,
					-3.89072123347292
				],
				[
					-95.2591827258929,
					-14.855481073260282
				],
				[
					-66.10658801236542,
					-6.189783780525132
				],
				[
					-47.424291400175214,
					-17.154543620312506
				],
				[
					-18.887596574961673,
					-16.270288794523182
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 384,
			"versionNonce": 74594795,
			"isDeleted": false,
			"id": "7Rekxpx3Pf7Uw909zw2UN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 317.0069019838883,
			"y": -401.5671227647699,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 257.7800264429359,
			"height": 234.67709954474816,
			"seed": 1967261432,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 199,
			"versionNonce": 1582755397,
			"isDeleted": false,
			"id": "Smbnb8tvIdXbMtTWo3if9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 372.7315185311376,
			"y": -391.549845322656,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 17.100791623299756,
			"height": 3.717563396369485,
			"seed": 1656753656,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-17.100791623299756,
					3.717563396369485
				]
			]
		},
		{
			"type": "line",
			"version": 222,
			"versionNonce": 160023691,
			"isDeleted": false,
			"id": "2Kb2X96A92liwEPV_zIMo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 384.62772139952006,
			"y": -386.34525656773866,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 34.945095925873375,
			"height": 18.58781698184754,
			"seed": 1773826696,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-34.945095925873375,
					18.58781698184754
				]
			]
		},
		{
			"type": "line",
			"version": 268,
			"versionNonce": 4906405,
			"isDeleted": false,
			"id": "6G37917z3VQTJtNz3x1sL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 393.54987355080686,
			"y": -377.42310441645185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 44.610760756434104,
			"height": 31.971045208777753,
			"seed": 446159864,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-44.610760756434104,
					31.971045208777753
				]
			]
		},
		{
			"type": "line",
			"version": 436,
			"versionNonce": 613874475,
			"isDeleted": false,
			"id": "5-3LMbbf8g-4Nu_FL3V-o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.764903848586918,
			"x": 571.7746297142863,
			"y": -246.82102848689925,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 17.100791623299806,
			"height": 3.7175633963694956,
			"seed": 1853494152,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-17.100791623299806,
					-3.7175633963694956
				]
			]
		},
		{
			"type": "line",
			"version": 459,
			"versionNonce": 1355407621,
			"isDeleted": false,
			"id": "8E-fYcP4QJHHdfTP19imA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.764903848586918,
			"x": 568.2306013931404,
			"y": -243.01932036288852,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 34.945095925873474,
			"height": 18.587816981847592,
			"seed": 603873928,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-34.945095925873474,
					-18.587816981847592
				]
			]
		},
		{
			"type": "line",
			"version": 505,
			"versionNonce": 1644453323,
			"isDeleted": false,
			"id": "3K27-tK-fupTQafPcpGp0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.764903848586918,
			"x": 557.6858439012105,
			"y": -241.2309665442959,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 44.61076075643423,
			"height": 31.971045208777845,
			"seed": 1646317960,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-44.61076075643423,
					-31.971045208777845
				]
			]
		},
		{
			"type": "text",
			"version": 490,
			"versionNonce": 1968273509,
			"isDeleted": false,
			"id": "ewjcllJo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 366.27785619294593,
			"y": -349.99211936675283,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 199.43626403808594,
			"height": 70.14648609073178,
			"seed": 277266824,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"fontSize": 11.223437774517086,
			"fontFamily": 1,
			"text": "Well PCA is a linear\ntransformation so if data lies on a\nnon-linear manifold PCA results\nwill not be logical Also PCA\nassumes a Gaussian",
			"rawText": "Well PCA is a linear\ntransformation so if data lies on a\nnon-linear manifold PCA results\nwill not be logical Also PCA\nassumes a Gaussian",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Well PCA is a linear\ntransformation so if data lies on a\nnon-linear manifold PCA results\nwill not be logical Also PCA\nassumes a Gaussian",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 2832,
			"versionNonce": 1558998123,
			"isDeleted": false,
			"id": "bXclHfTIWbfwzSeaWnIVU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 65.12837439608472,
			"y": -47.642478178201046,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.173685612569344,
			"height": 36.976042315380084,
			"seed": 467064200,
			"groupIds": [
				"i_HxKfKJi77u5WaAnhbvO",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2896,
			"versionNonce": 128918469,
			"isDeleted": false,
			"id": "IQKBle5bxCXhTBcZW77T1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 86.5175205697467,
			"y": -10.872139080992028,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 1.9712530443849101,
			"height": 44.82719709330239,
			"seed": 1282598024,
			"groupIds": [
				"i_HxKfKJi77u5WaAnhbvO",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.9712530443849101,
					44.82719709330239
				]
			]
		},
		{
			"type": "line",
			"version": 2865,
			"versionNonce": 1763288843,
			"isDeleted": false,
			"id": "Es-7cl1h8lZ153rnSf3Mb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 88.70393797207885,
			"y": 35.75383256421061,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 1.923971872410506,
			"height": 27.337969224322613,
			"seed": 1286935432,
			"groupIds": [
				"i_HxKfKJi77u5WaAnhbvO",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.923971872410506,
					27.337969224322613
				]
			]
		},
		{
			"type": "line",
			"version": 2884,
			"versionNonce": 201351973,
			"isDeleted": false,
			"id": "CBN4k9OdwFiowhIfTtnvP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 89.06688635818705,
			"y": 34.970062979417676,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 5.627366540375309,
			"height": 25.860016810105815,
			"seed": 47800968,
			"groupIds": [
				"i_HxKfKJi77u5WaAnhbvO",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.627366540375309,
					25.860016810105815
				]
			]
		},
		{
			"type": "line",
			"version": 3056,
			"versionNonce": 2097581483,
			"isDeleted": false,
			"id": "rBHJdstl6eNKtuuTy4IT0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 107.17089642397957,
			"y": 0.9164333425542424,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 20.783279665813964,
			"height": 17.45772961141449,
			"seed": 765186440,
			"groupIds": [
				"i_HxKfKJi77u5WaAnhbvO",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.6916190508120525,
					2.757998025732947
				],
				[
					-8.419936579557435,
					15.305741183937112
				],
				[
					-16.330470309729645,
					-2.1519884274773786
				],
				[
					-20.783279665813964,
					1.1724688959150322
				]
			]
		},
		{
			"type": "line",
			"version": 3096,
			"versionNonce": 649246341,
			"isDeleted": false,
			"id": "ZOWqG7SEmOy683HTZbLKx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 87.3874138401743,
			"y": 1.77881836852238,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 24.08682515105723,
			"height": 16.91217556105779,
			"seed": 1412980872,
			"groupIds": [
				"i_HxKfKJi77u5WaAnhbvO",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.275852531631674,
					-3.2871504786239023
				],
				[
					-12.368055186268842,
					13.625025082433888
				],
				[
					-20.278588916441024,
					0.8045048990513669
				],
				[
					-24.08682515105723,
					-1.2738074209641477
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1734,
			"versionNonce": 1541251147,
			"isDeleted": false,
			"id": "ZLUXq4_SrRp6VlT0eBw0W",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 94.28495380577641,
			"y": -32.12210923861623,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6866703859883223,
			"height": 0.9016883856412318,
			"seed": 912985992,
			"groupIds": [
				"i_HxKfKJi77u5WaAnhbvO",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1735,
			"versionNonce": 310615525,
			"isDeleted": false,
			"id": "QYAQvRazZLIA7MBRNrFKp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 76.2130377381668,
			"y": -30.564962757258755,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.693606450493255,
			"height": 1.1791309658385334,
			"seed": 1013964424,
			"groupIds": [
				"i_HxKfKJi77u5WaAnhbvO",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097379,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 910,
			"versionNonce": 2138660587,
			"isDeleted": false,
			"id": "zg-tSZ0tJH5U0DDCKj6wH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 71.59300981290733,
			"y": -31.827660822786825,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.16773583499152,
			"height": 4.119410361696672,
			"seed": 1728236936,
			"groupIds": [
				"i_HxKfKJi77u5WaAnhbvO",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.324970426486695,
					-4.119410361696672
				],
				[
					9.16773583499152,
					-1.529523333173052
				]
			]
		},
		{
			"type": "line",
			"version": 696,
			"versionNonce": 1451268421,
			"isDeleted": false,
			"id": "EErrV-JESQkwgn2PlPa16",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 96.43851235120576,
			"y": -37.46423347768321,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.214046615081732,
			"height": 3.113658722138017,
			"seed": 1063246984,
			"groupIds": [
				"i_HxKfKJi77u5WaAnhbvO",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.214046615081732,
					3.113658722138017
				]
			]
		},
		{
			"type": "line",
			"version": 1787,
			"versionNonce": 1113868683,
			"isDeleted": false,
			"id": "QKSjZR00ZvSLO04aARmgh",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 143.89060182366097,
			"y": -42.322109898617455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 151.85223567727758,
			"height": 90.82215640447058,
			"seed": 1195576200,
			"groupIds": [
				"yx6vwYN7nhYXBUUrz8IB3",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.590377477792487,
					9.866804949700338
				],
				[
					-25.487837333092088,
					18.18820671450787
				],
				[
					-18.271401461674444,
					2.734174865579604
				],
				[
					-12.89745985529962,
					-7.132630084120734
				],
				[
					-27.637413975642023,
					-12.006593974936543
				],
				[
					-33.47197914827754,
					-24.726450958285156
				],
				[
					-28.098037541902727,
					-38.991711126526624
				],
				[
					-10.74788321274969,
					-46.4809727148534
				],
				[
					-5.834565172635546,
					-59.67633837047674
				],
				[
					8.137683003939031,
					-68.35437163949034
				],
				[
					29.786990618191936,
					-67.28447712687218
				],
				[
					46.522980192330806,
					-72.6339496899627
				],
				[
					64.33375808774457,
					-72.158441017688
				],
				[
					80.6091240956226,
					-65.85795111004803
				],
				[
					94.27428989469006,
					-50.403919261119775
				],
				[
					110.39611471381455,
					-46.00546404257868
				],
				[
					118.38025652900002,
					-34.117747235710816
				],
				[
					115.46297394268232,
					-18.54483821871387
				],
				[
					99.955313878572,
					-9.866804949700288
				],
				[
					92.27825444089368,
					2.6152976975109254
				],
				[
					71.24311158165504,
					9.985682117769016
				],
				[
					49.4402627786486,
					4.160700882403766
				],
				[
					35.46801460207402,
					11.531085302661864
				],
				[
					14.125789365328266,
					10.936699462318458
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 574,
			"versionNonce": 1007102117,
			"isDeleted": false,
			"id": "uOw3MsWD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 120.92095235875001,
			"y": -101.03602219130802,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c07912",
			"width": 128.54483032226562,
			"height": 56.10641827624761,
			"seed": 1760057992,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"fontSize": 11.221283655249522,
			"fontFamily": 1,
			"text": "Okay but why not\njust use Kernel PCA\nWhich we also know and\nis not Linear?",
			"rawText": "Okay but why not\njust use Kernel PCA\nWhich we also know and\nis not Linear?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Okay but why not\njust use Kernel PCA\nWhich we also know and\nis not Linear?",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 392,
			"versionNonce": 1238949931,
			"isDeleted": false,
			"id": "sv-DAXYb4Ddvz4dsoWRhr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 59.226875880732045,
			"y": -166.28205132721143,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 257.7800264429359,
			"height": 234.67709954474816,
			"seed": 1728825736,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 2889,
			"versionNonce": 80006149,
			"isDeleted": false,
			"id": "enZwbgX1w0moWIhlrYRF0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 330.3853112268053,
			"y": -52.79045120269652,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.173685612569344,
			"height": 36.976042315380084,
			"seed": 2095611784,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2953,
			"versionNonce": 801219275,
			"isDeleted": false,
			"id": "uRRazPBMcxUMlDE8SXY_b",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 351.77445740046716,
			"y": -16.020112105487527,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 1.9712530443849101,
			"height": 44.82719709330239,
			"seed": 834621064,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.9712530443849101,
					44.82719709330239
				]
			]
		},
		{
			"type": "line",
			"version": 2922,
			"versionNonce": 1622606693,
			"isDeleted": false,
			"id": "cR-imWn_CH6xWCIWzN3vR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 353.9608748027994,
			"y": 30.60585953971517,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 1.923971872410506,
			"height": 27.337969224322613,
			"seed": 1625570696,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.923971872410506,
					27.337969224322613
				]
			]
		},
		{
			"type": "line",
			"version": 2941,
			"versionNonce": 1824067947,
			"isDeleted": false,
			"id": "GdS3FkG6gTaeSPDOfe-Ux",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 354.3238231889075,
			"y": 29.822089954922234,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 5.627366540375309,
			"height": 25.860016810105815,
			"seed": 1536380040,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.627366540375309,
					25.860016810105815
				]
			]
		},
		{
			"type": "line",
			"version": 3296,
			"versionNonce": 606817989,
			"isDeleted": false,
			"id": "MdOGrJBIlBs0lLiVww0dn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 347.1807991875501,
			"y": 2.8706558050293154,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.066920243665152,
			"height": 12.55074784443251,
			"seed": 1804106632,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.392411139826322,
					-1.4367637291542508
				],
				[
					14.066920243665152,
					3.2965639299846146
				],
				[
					9.069906937638468,
					-9.254183914447895
				],
				[
					4.617097581554148,
					-5.929726591055483
				]
			]
		},
		{
			"type": "line",
			"version": 3393,
			"versionNonce": 34188299,
			"isDeleted": false,
			"id": "5c-jkJqvKXGYC4klWED9S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 352.6443506708949,
			"y": -3.3691546559730625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.34957067230323,
			"height": 12.771909695166771,
			"seed": 1124059784,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.275852531631674,
					-3.2871504786239023
				],
				[
					-8.381132500596038,
					9.48475921654287
				],
				[
					0.882769953668685,
					4.484741224287802
				],
				[
					5.9684381717071915,
					7.160067491036131
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1791,
			"versionNonce": 1035939365,
			"isDeleted": false,
			"id": "eTUInMNhZHH7l8qy4VxQA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 359.54189063649693,
			"y": -37.270082263111675,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6866703859883223,
			"height": 0.9016883856412318,
			"seed": 1823816072,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1792,
			"versionNonce": 1672344235,
			"isDeleted": false,
			"id": "T8V7_rIWsghEkgHuGtLJU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 341.46997456888727,
			"y": -35.712935781754226,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.693606450493255,
			"height": 1.1791309658385334,
			"seed": 1004849288,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 967,
			"versionNonce": 1818239365,
			"isDeleted": false,
			"id": "r0eokiJGKEoVH7FSd81JW",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 336.8499466436279,
			"y": -36.975633847282296,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.16773583499152,
			"height": 4.119410361696672,
			"seed": 1011513224,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.324970426486695,
					-4.119410361696672
				],
				[
					9.16773583499152,
					-1.529523333173052
				]
			]
		},
		{
			"type": "line",
			"version": 753,
			"versionNonce": 575694155,
			"isDeleted": false,
			"id": "4evkP7cZnT81AhzD2h33r",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 361.69544918192634,
			"y": -42.61220650217862,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.214046615081732,
			"height": 3.113658722138017,
			"seed": 572671624,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.214046615081732,
					3.113658722138017
				]
			]
		},
		{
			"type": "line",
			"version": 1902,
			"versionNonce": 894150885,
			"isDeleted": false,
			"id": "6AYTzPVzr5sYmpZpFUtJY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 521.1219538920325,
			"y": -125.13065271700711,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 203.04166318083622,
			"height": 135.11413738060543,
			"seed": 975713672,
			"groupIds": [
				"tFL6qkAAcXs-9NGYHlPho",
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.834596947248315,
					-14.678630108102423
				],
				[
					34.07979382003926,
					-27.058197669152683
				],
				[
					24.43069556978716,
					-4.0675721986307805
				],
				[
					17.245196872790956,
					10.611057909471644
				],
				[
					36.953993298837744,
					17.861947480943893
				],
				[
					44.7553918841479,
					36.78500075283495
				],
				[
					37.569893187151706,
					58.007116571778226
				],
				[
					14.370997393992468,
					69.14872737672346
				],
				[
					7.801398585310196,
					88.77918450924598
				],
				[
					-10.88089802687999,
					101.68930496576986
				],
				[
					-39.828192777636204,
					100.09764627934904
				],
				[
					-62.20588871971028,
					108.05593971145272
				],
				[
					-86.02068440118352,
					107.3485358508213
				],
				[
					-107.78248045494345,
					97.97543469745472
				],
				[
					-126.054177141591,
					74.98480922693282
				],
				[
					-147.61067323257967,
					68.44132351609201
				],
				[
					-158.28627129668834,
					50.75622700030597
				],
				[
					-154.38557200403332,
					27.588750564626213
				],
				[
					-133.65027576412984,
					14.67863010810235
				],
				[
					-123.38527762556382,
					-3.89072123347292
				],
				[
					-95.2591827258929,
					-14.855481073260282
				],
				[
					-66.10658801236542,
					-6.189783780525132
				],
				[
					-47.424291400175214,
					-17.154543620312506
				],
				[
					-18.887596574961673,
					-16.270288794523182
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 425,
			"versionNonce": 1431012331,
			"isDeleted": false,
			"id": "iITSdLIBqiO1jAJpZQVq-",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 317.00690190325537,
			"y": -166.28205067986013,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 257.7800264429359,
			"height": 234.67709954474816,
			"seed": 1503151240,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 240,
			"versionNonce": 437208133,
			"isDeleted": false,
			"id": "FPsjCcp1vMlZsgibbJ9vg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 372.73151845050467,
			"y": -156.2647732377462,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 17.100791623299756,
			"height": 3.717563396369485,
			"seed": 1311667080,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-17.100791623299756,
					3.717563396369485
				]
			]
		},
		{
			"type": "line",
			"version": 263,
			"versionNonce": 1151979147,
			"isDeleted": false,
			"id": "e6Yjf_vPHgYOGxCUZx886",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 384.62772131888715,
			"y": -151.06018448282882,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 34.945095925873375,
			"height": 18.58781698184754,
			"seed": 1311163016,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-34.945095925873375,
					18.58781698184754
				]
			]
		},
		{
			"type": "line",
			"version": 309,
			"versionNonce": 243823525,
			"isDeleted": false,
			"id": "hr2WhMKonZBtcs8wJ8suy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 393.54987347017396,
			"y": -142.138032331542,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 44.610760756434104,
			"height": 31.971045208777753,
			"seed": 1748840840,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-44.610760756434104,
					31.971045208777753
				]
			]
		},
		{
			"type": "line",
			"version": 477,
			"versionNonce": 1394984235,
			"isDeleted": false,
			"id": "S2qDqYH6qsfmQpfwHYGzJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.764903848586918,
			"x": 571.7746296336534,
			"y": -11.53595640198941,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 17.100791623299806,
			"height": 3.7175633963694956,
			"seed": 1940766856,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-17.100791623299806,
					-3.7175633963694956
				]
			]
		},
		{
			"type": "line",
			"version": 500,
			"versionNonce": 786740997,
			"isDeleted": false,
			"id": "mLm9hOrM8lWjbb5WWsovf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.764903848586918,
			"x": 568.2306013125076,
			"y": -7.734248277978708,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 34.945095925873474,
			"height": 18.587816981847592,
			"seed": 3436424,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-34.945095925873474,
					-18.587816981847592
				]
			]
		},
		{
			"type": "line",
			"version": 546,
			"versionNonce": 673834955,
			"isDeleted": false,
			"id": "9vqO2vndfTdaxwLQ4EFGI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.764903848586918,
			"x": 557.6858438205777,
			"y": -5.945894459386096,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 44.61076075643423,
			"height": 31.971045208777845,
			"seed": 1175273096,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-44.61076075643423,
					-31.971045208777845
				]
			]
		},
		{
			"type": "text",
			"version": 619,
			"versionNonce": 899780197,
			"isDeleted": false,
			"id": "mmUzWlMJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 430.60633206446147,
			"y": -114.70704728184305,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 70.77931213378906,
			"height": 70.14648609073178,
			"seed": 368323976,
			"groupIds": [
				"qNGa6B_EegvYSIvbv8xKD"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"fontSize": 11.223437774517086,
			"fontFamily": 1,
			"text": ".\n.\n.\n.\nShut up nerd",
			"rawText": ".\n.\n.\n.\nShut up nerd",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": ".\n.\n.\n.\nShut up nerd",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 95,
			"versionNonce": 433108587,
			"isDeleted": false,
			"id": "p4Ls6cEQJS-bf4mALC_Co",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 588.2785745496508,
			"y": -398.6832050365757,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 236.94140707599763,
			"height": 211.0932535767979,
			"seed": 1826641912,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xWtWRbyAwktY3eI7Thfrb",
					"type": "arrow"
				},
				{
					"id": "SLmqH8MLW0cTKJapS7vIC",
					"type": "arrow"
				}
			],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fc53746f0a2516596212dccc83d2c599bfd42c3a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 143,
			"versionNonce": 831289797,
			"isDeleted": false,
			"id": "JWvGuuxZhwyPy4r-zDl-u",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 604.0296239526531,
			"y": -154.45552539746313,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 221.19035807523576,
			"height": 214.87063355880048,
			"seed": 2036810376,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xWtWRbyAwktY3eI7Thfrb",
					"type": "arrow"
				}
			],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0b2167364772b18c6bad69ace0711b492c028665",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 251,
			"versionNonce": 1457828107,
			"isDeleted": false,
			"id": "xWtWRbyAwktY3eI7Thfrb",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 831.7163630155816,
			"y": -308.9712852652179,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 134.4962402613562,
			"height": 267.56166945610215,
			"seed": 1235127032,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "p4Ls6cEQJS-bf4mALC_Co",
				"focus": -0.29458159164565695,
				"gap": 6.496381389933163
			},
			"endBinding": {
				"elementId": "JWvGuuxZhwyPy4r-zDl-u",
				"focus": 0.18926216834390044,
				"gap": 5.780975454387772
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
					130.9192125948308,
					22.177571532457648
				],
				[
					133.78083472805122,
					246.81490899025465
				],
				[
					-0.7154055333049882,
					267.56166945610215
				]
			]
		},
		{
			"type": "text",
			"version": 345,
			"versionNonce": 2076375333,
			"isDeleted": false,
			"id": "fXt7YmJs",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 866.7262246478524,
			"y": -208.96778419959995,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 105.56820678710938,
			"height": 80,
			"seed": 1932710024,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Silly Linear\nModel moment\n\n",
			"rawText": "Silly Linear\nModel moment\n\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Silly Linear\nModel moment\n\n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 115,
			"versionNonce": 1356879787,
			"isDeleted": false,
			"id": "mhdZMIZg",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 895.02013280609,
			"y": -169.8299574356754,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 43.424072265625,
			"height": 20,
			"seed": 1857384184,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "(PCA)",
			"rawText": "(PCA)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(PCA)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 115,
			"versionNonce": 1840417925,
			"isDeleted": false,
			"id": "PJhY6UGG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1008.6528737447231,
			"y": -141.42222335950112,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 42.00007629394531,
			"height": 20,
			"seed": 1845160440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "(LLE)",
			"rawText": "(LLE)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(LLE)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 374,
			"versionNonce": 1710107211,
			"isDeleted": false,
			"id": "M2frRsFai6V8uA57nQmJX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1108.9770976192285,
			"y": -182.95616311464715,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 225.83216578285734,
			"height": 223.48585756693151,
			"seed": 1970917256,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "63ac52b94a00a31dc1bd7f5998616a22c5b81528",
			"scale": [
				-1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 312,
			"versionNonce": 1461236709,
			"isDeleted": false,
			"id": "SLmqH8MLW0cTKJapS7vIC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 832.2191600622843,
			"y": -308.31766105702513,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 289.75888757697794,
			"height": 262.06134685270797,
			"seed": 379664776,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "p4Ls6cEQJS-bf4mALC_Co",
				"focus": -0.2854189857474208,
				"gap": 6.99917843663593
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
					130.67557675040177,
					21.305800557130738
				],
				[
					165.47505099371517,
					249.98805987033387
				],
				[
					289.75888757697794,
					262.06134685270797
				]
			]
		},
		{
			"type": "text",
			"version": 39,
			"versionNonce": 1256761579,
			"isDeleted": false,
			"id": "F5BjUosa",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 983.6623471957002,
			"y": -224.51484553231091,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 103.34422302246094,
			"height": 80,
			"seed": 795568264,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We want to\npreserve\nneighbourhood\nrelations ",
			"rawText": "We want to\npreserve\nneighbourhood\nrelations ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We want to\npreserve\nneighbourhood\nrelations ",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 93,
			"versionNonce": 872607557,
			"isDeleted": false,
			"id": "Gtqh3XM1VLlsOXz9Yp1g2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 908.9200420679548,
			"y": -51.22766766764761,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 21.305800557130624,
			"height": 25.566960668556874,
			"seed": 1111639176,
			"groupIds": [
				"0krhibhrPE-nPz5Wz4CdJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-21.305800557130624,
					25.566960668556874
				]
			]
		},
		{
			"type": "line",
			"version": 111,
			"versionNonce": 895112075,
			"isDeleted": false,
			"id": "vcSyLTGyvGwKm14ovfd3D",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 908.9200420679548,
			"y": -26.3709003509951,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 20.595607205226088,
			"height": 25.566960668556874,
			"seed": 1750078200,
			"groupIds": [
				"0krhibhrPE-nPz5Wz4CdJ"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.595607205226088,
					-25.566960668556874
				]
			]
		},
		{
			"type": "line",
			"version": 154,
			"versionNonce": 583974565,
			"isDeleted": false,
			"id": "VbKb3gAOhBQ_tp3Ui_7em",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1027.5223318359829,
			"y": -49.80728096383899,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 50.423727985209325,
			"height": 26.27715402046124,
			"seed": 357862536,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.942706926660776,
					19.885413853322063
				],
				[
					50.423727985209325,
					-6.391740167139176
				]
			]
		},
		{
			"type": "text",
			"version": 53,
			"versionNonce": 1165863467,
			"isDeleted": false,
			"id": "7p17SETG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -539.5976372488981,
			"y": 197.40259505300344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 313.6293029785156,
			"height": 70,
			"seed": 1566084856,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Local Linear Embedding\n(LLE)",
			"rawText": "Local Linear Embedding\n(LLE)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Local Linear Embedding\n(LLE)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 860,
			"versionNonce": 438936069,
			"isDeleted": false,
			"id": "BkjbjkYS",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -982.561343637107,
			"y": 281.2536502676568,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1202.658935546875,
			"height": 150,
			"seed": 647021960,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The Main idea behind LLE is to narrow our scope on local regions (neighborhood) of the data, learn its structure\nand the neighborhood relations it has, reduce it to lower dimensions while keeping the sale relations we originally observed\n\nNote that this concept inherently gives us a bit of leeway with some Affine transformations. \nFor example if we take 5 points representing a pyramid, no matter if it was rotated, scaled\nor translated, it will still be a pyramid",
			"rawText": "The Main idea behind LLE is to narrow our scope on local regions (neighborhood) of the data, learn its structure\nand the neighborhood relations it has, reduce it to lower dimensions while keeping the sale relations we originally observed\n\nNote that this concept inherently gives us a bit of leeway with some Affine transformations. \nFor example if we take 5 points representing a pyramid, no matter if it was rotated, scaled\nor translated, it will still be a pyramid",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The Main idea behind LLE is to narrow our scope on local regions (neighborhood) of the data, learn its structure\nand the neighborhood relations it has, reduce it to lower dimensions while keeping the sale relations we originally observed\n\nNote that this concept inherently gives us a bit of leeway with some Affine transformations. \nFor example if we take 5 points representing a pyramid, no matter if it was rotated, scaled\nor translated, it will still be a pyramid",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 210,
			"versionNonce": 809315531,
			"isDeleted": false,
			"id": "vU3VPi5fZWwYXGM5g_jCn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -736.3525893034081,
			"y": 593.8937365736197,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.2755910185773836,
			"height": 7.275591018577446,
			"seed": 1064414088,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 212,
			"versionNonce": 1594956133,
			"isDeleted": false,
			"id": "cpq_Awkbi2A5iD-Yl4Xr2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -768.0533787414954,
			"y": 568.9488530813542,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.2755910185773836,
			"height": 7.275591018577446,
			"seed": 1550808968,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 229,
			"versionNonce": 691231595,
			"isDeleted": false,
			"id": "ckXkXRiVryIk1D43_T8Id",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -709.8893451880492,
			"y": 565.311057505591,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.2755910185773836,
			"height": 7.275591018577446,
			"seed": 1951238648,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 234,
			"versionNonce": 986883269,
			"isDeleted": false,
			"id": "0iDa3ZgAUxo4C75kKkRLz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -679.7069163305821,
			"y": 590.775625730827,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.2755910185773836,
			"height": 7.275591018577446,
			"seed": 1785347208,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 262,
			"versionNonce": 212514315,
			"isDeleted": false,
			"id": "q6M7Q9BKA365y7Nz36yWO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -726.478572921053,
			"y": 515.4212905875345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.2755910185773836,
			"height": 7.275591018577446,
			"seed": 950818808,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097380,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 207,
			"versionNonce": 1896596517,
			"isDeleted": false,
			"id": "jvCLsFxSBDmxyt4ulF0dm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -763.3762130866957,
			"y": 573.1063336633986,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 58.204728148619445,
			"height": 3.6377955092886918,
			"seed": 1274539656,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					58.204728148619445,
					-3.6377955092886918
				]
			]
		},
		{
			"type": "line",
			"version": 232,
			"versionNonce": 1235074219,
			"isDeleted": false,
			"id": "v-s_B4HoRMIkJvZrrQ2gV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -732.7147937941195,
			"y": 596.7520044737751,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 58.204728148619445,
			"height": 3.6377955092886918,
			"seed": 1111027592,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					58.204728148619445,
					-3.6377955092886918
				]
			]
		},
		{
			"type": "line",
			"version": 208,
			"versionNonce": 1974073221,
			"isDeleted": false,
			"id": "pxa7XgQ3KwQ28bQU1eX2C",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -732.1951087213638,
			"y": 597.5315320829086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 31.7007894380874,
			"height": 24.425198419510018,
			"seed": 1703974536,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-31.7007894380874,
					-24.425198419510018
				]
			]
		},
		{
			"type": "line",
			"version": 222,
			"versionNonce": 196538187,
			"isDeleted": false,
			"id": "gxIVDXCBTlhHYIiYbOoyz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -674.2502231091222,
			"y": 594.1535791099975,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 31.7007894380874,
			"height": 24.425198419510018,
			"seed": 486221304,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-31.7007894380874,
					-24.425198419510018
				]
			]
		},
		{
			"type": "line",
			"version": 223,
			"versionNonce": 1659551461,
			"isDeleted": false,
			"id": "RzW41Vatt7nZr2zumUnhl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -767.0140085959844,
			"y": 571.547278445132,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 42.61417596595354,
			"height": 52.4881923483086,
			"seed": 206472072,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					42.61417596595354,
					-52.4881923483086
				]
			]
		},
		{
			"type": "line",
			"version": 272,
			"versionNonce": 626052587,
			"isDeleted": false,
			"id": "uBenjgkABVlEa_XLaoCqN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -705.1714849380761,
			"y": 568.9488530813542,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.708662619199057,
			"height": 50.40945205728646,
			"seed": 70833912,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-18.708662619199057,
					-50.40945205728646
				]
			]
		},
		{
			"type": "line",
			"version": 215,
			"versionNonce": 794532421,
			"isDeleted": false,
			"id": "GmPx1XVzjsm5qkVTaiWAh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -733.2344788668748,
			"y": 597.0118470101529,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.874016382355066,
			"height": 78.99213105884064,
			"seed": 133689224,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.874016382355066,
					-78.99213105884064
				]
			]
		},
		{
			"type": "line",
			"version": 226,
			"versionNonce": 964024459,
			"isDeleted": false,
			"id": "7u5nB06QOFZP8xd7ZqaOd",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -674.5100656454999,
			"y": 596.4921619373974,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 47.81102669350884,
			"height": 78.99213105884064,
			"seed": 1443794056,
			"groupIds": [
				"FQd8l4y5prCXcvk93qvWB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-47.81102669350884,
					-78.99213105884064
				]
			]
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 601491877,
			"isDeleted": false,
			"id": "UHrfjz8g",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -774.7304650796862,
			"y": 459.5665563625227,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 97.77638244628906,
			"height": 35,
			"seed": 124377080,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Original",
			"rawText": "Original",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Original",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 306,
			"versionNonce": 635473707,
			"isDeleted": false,
			"id": "8XLFkOd9ZdkFX1lM7RVLx",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -539.5512833742339,
			"y": 557.6025548887128,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 8.041264754349815,
			"height": 8.041264754349882,
			"seed": 1198801544,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 308,
			"versionNonce": 294882565,
			"isDeleted": false,
			"id": "1EdDgrWKiaOXTfk1uG1ZJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -522.4664807457167,
			"y": 516.4224101212922,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 8.041264754349815,
			"height": 8.041264754349882,
			"seed": 1541058952,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 325,
			"versionNonce": 754676171,
			"isDeleted": false,
			"id": "S6iSUDc932pzyOC2_zU2k",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -501.23621892459573,
			"y": 577.2337642842438,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 8.041264754349815,
			"height": 8.041264754349882,
			"seed": 396050568,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 330,
			"versionNonce": 1208329317,
			"isDeleted": false,
			"id": "AO-QrbUYuuCw2LKkT69Hg",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -519.3272130722916,
			"y": 616.9531981288467,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 8.041264754349815,
			"height": 8.041264754349882,
			"seed": 1248980872,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 358,
			"versionNonce": 1608581227,
			"isDeleted": false,
			"id": "vRcQ2yPedFhRi4rPSHp6C",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -453.09552093678354,
			"y": 544.6902819459178,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 8.041264754349815,
			"height": 8.041264754349882,
			"seed": 1822080648,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 303,
			"versionNonce": 1258147781,
			"isDeleted": false,
			"id": "W4crUjmr47QG8WODlV-S7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -540.2325439460643,
			"y": 554.1418661947205,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 64.33011803479893,
			"height": 4.020632377174907,
			"seed": 248622472,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					64.33011803479893,
					-4.020632377174907
				]
			]
		},
		{
			"type": "line",
			"version": 328,
			"versionNonce": 1213971211,
			"isDeleted": false,
			"id": "JxxFlRTWfQJFcuNSvJe_i",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -556.244948165377,
			"y": 593.8281846243474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 64.33011803479893,
			"height": 4.020632377174907,
			"seed": 1246936200,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					64.33011803479893,
					-4.020632377174907
				]
			]
		},
		{
			"type": "line",
			"version": 304,
			"versionNonce": 1218023205,
			"isDeleted": false,
			"id": "Gpxgra6tilR5-I_gjscmk",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -509.5912000709295,
			"y": 555.1615407544211,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 35.03693928681016,
			"height": 26.995674532460345,
			"seed": 819587976,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-35.03693928681016,
					-26.995674532460345
				]
			]
		},
		{
			"type": "line",
			"version": 318,
			"versionNonce": 1390813611,
			"isDeleted": false,
			"id": "uoSEHQ2gc7pCvq2N2OXDY",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -488.70286222233995,
			"y": 615.8172316055757,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 35.03693928681016,
			"height": 26.995674532460345,
			"seed": 1017330312,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-35.03693928681016,
					-26.995674532460345
				]
			]
		},
		{
			"type": "line",
			"version": 319,
			"versionNonce": 1330012805,
			"isDeleted": false,
			"id": "utF-v1Huq3iSpF-QtVEQR",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -507.3771454445299,
			"y": 561.2157141249529,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 47.098836418334955,
			"height": 58.011981442095454,
			"seed": 1080732040,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					47.098836418334955,
					-58.011981442095454
				]
			]
		},
		{
			"type": "line",
			"version": 368,
			"versionNonce": 2024453195,
			"isDeleted": false,
			"id": "r308bipZcF2QiwK_0SHXC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -462.52387654253926,
			"y": 592.7839976111136,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 20.677537939756743,
			"height": 55.7144772265669,
			"seed": 1466710152,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.677537939756743,
					-55.7144772265669
				]
			]
		},
		{
			"type": "line",
			"version": 311,
			"versionNonce": 1136773605,
			"isDeleted": false,
			"id": "b4hXAZNGhlBLwKgIStYfW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -497.0848833612554,
			"y": 598.0339428663412,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 10.913145023760512,
			"height": 87.30516019008422,
			"seed": 1432610696,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					10.913145023760512,
					-87.30516019008422
				]
			]
		},
		{
			"type": "line",
			"version": 322,
			"versionNonce": 696513259,
			"isDeleted": false,
			"id": "Wt_dYlKoKPUCPYe5JKDcx",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.2973709602625982,
			"x": -455.73575698564616,
			"y": 629.6785800510606,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 52.84259695715628,
			"height": 87.30516019008422,
			"seed": 915256968,
			"groupIds": [
				"X19JsPjGuD0dWqL0kRYJT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-52.84259695715628,
					-87.30516019008422
				]
			]
		},
		{
			"type": "text",
			"version": 82,
			"versionNonce": 387532101,
			"isDeleted": false,
			"id": "VcghQnI5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -552.9113098098943,
			"y": 459.5665562484121,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 116.06050109863281,
			"height": 35,
			"seed": 741579912,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Rotated",
			"rawText": "Rotated",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Rotated",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 77,
			"versionNonce": 1979473291,
			"isDeleted": false,
			"id": "hOAs39B8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -289.1755431920513,
			"y": 459.56655646892034,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 88.36837768554688,
			"height": 35,
			"seed": 510438392,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Scaled",
			"rawText": "Scaled",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Scaled",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 262,
			"versionNonce": 1017795749,
			"isDeleted": false,
			"id": "hQ70DeQ6l_uKdqAM_iH_4",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -252.05414119300815,
			"y": 590.7801265757525,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.32227803774088,
			"height": 4.322278037740916,
			"seed": 518891000,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 264,
			"versionNonce": 2035184683,
			"isDeleted": false,
			"id": "Yo2mg2jnMukbUsy6Q7oyl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -270.8869240717363,
			"y": 575.9608875892125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.32227803774088,
			"height": 4.322278037740916,
			"seed": 657860344,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 281,
			"versionNonce": 1612871685,
			"isDeleted": false,
			"id": "soKfHtVLWM8ozFP4CiK1n",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -236.33287558652592,
			"y": 573.7997485308508,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.32227803774088,
			"height": 4.322278037740916,
			"seed": 1959167992,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 286,
			"versionNonce": 56932043,
			"isDeleted": false,
			"id": "zV2HP4W_M6o4edUcdFPZm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -218.40211930250717,
			"y": 588.9277214610847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.32227803774088,
			"height": 4.322278037740916,
			"seed": 1403177208,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 314,
			"versionNonce": 1535061861,
			"isDeleted": false,
			"id": "TJ1T8yNyQRuDFHR52UG-u",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -246.1881924275027,
			"y": 544.1612705972614,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 4.32227803774088,
			"height": 4.322278037740916,
			"seed": 1867442680,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 259,
			"versionNonce": 47818091,
			"isDeleted": false,
			"id": "9joi3EZHFSh1dQdfYUgnT",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -268.1083167617601,
			"y": 578.4307607536357,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 34.57822430192726,
			"height": 2.16113901887044,
			"seed": 1657727736,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					34.57822430192726,
					-2.16113901887044
				]
			]
		},
		{
			"type": "line",
			"version": 284,
			"versionNonce": 1829632709,
			"isDeleted": false,
			"id": "vupHI83wiz4GQtXRm4uum",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -249.89300217413785,
			"y": 592.4781643762935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 34.57822430192726,
			"height": 2.16113901887044,
			"seed": 1218890744,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					34.57822430192726,
					-2.16113901887044
				]
			]
		},
		{
			"type": "line",
			"version": 260,
			"versionNonce": 787988491,
			"isDeleted": false,
			"id": "4G2LGfd12huFlsGtoabuv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -249.5842680285848,
			"y": 592.9412655946232,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.832782878728253,
			"height": 14.510504840987373,
			"seed": 1255836920,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-18.832782878728253,
					-14.510504840987373
				]
			]
		},
		{
			"type": "line",
			"version": 274,
			"versionNonce": 762075685,
			"isDeleted": false,
			"id": "DNtPaZucGT6Dd6fY64dOl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -215.16041079943403,
			"y": 590.9344936485293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.832782878728253,
			"height": 14.510504840987373,
			"seed": 854470136,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-18.832782878728253,
					-14.510504840987373
				]
			]
		},
		{
			"type": "line",
			"version": 275,
			"versionNonce": 1907984043,
			"isDeleted": false,
			"id": "KrfVvmDPr7IJy3ZRB8DO3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -270.26945578063055,
			"y": 577.504558316977,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 25.31619993533961,
			"height": 31.18214870084511,
			"seed": 2045095672,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					25.31619993533961,
					-31.18214870084511
				]
			]
		},
		{
			"type": "line",
			"version": 324,
			"versionNonce": 1166527877,
			"isDeleted": false,
			"id": "UPddKZMNpFPt7-EW-xZt5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -233.53009245983276,
			"y": 575.9608875892125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 11.11442923990516,
			"height": 29.947212118633413,
			"seed": 1480921080,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.11442923990516,
					-29.947212118633413
				]
			]
		},
		{
			"type": "line",
			"version": 267,
			"versionNonce": 298416459,
			"isDeleted": false,
			"id": "6SpOmt7jI_4FXHj27-v-l",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -250.2017363196906,
			"y": 592.6325314490703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 5.865948765505506,
			"height": 46.927590124044116,
			"seed": 1443909880,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.865948765505506,
					-46.927590124044116
				]
			]
		},
		{
			"type": "line",
			"version": 278,
			"versionNonce": 1688065253,
			"isDeleted": false,
			"id": "YgAbqxREQzuFvaNKYuzUi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -215.3147778722104,
			"y": 592.3237973035173,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 28.403541390868828,
			"height": 46.927590124044116,
			"seed": 1523282424,
			"groupIds": [
				"JuznH3-QZHjAIcagNEe24"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-28.403541390868828,
					-46.927590124044116
				]
			]
		},
		{
			"type": "text",
			"version": 85,
			"versionNonce": 478287851,
			"isDeleted": false,
			"id": "oHJixLW1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -78.94510351820468,
			"y": 459.56655624455556,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 154.61663818359375,
			"height": 35,
			"seed": 2115893496,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Translated",
			"rawText": "Translated",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Translated",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 270,
			"versionNonce": 1983639621,
			"isDeleted": false,
			"id": "9ysdFC1K_8zOojFkAYsfp",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -96.47788406280324,
			"y": 589.5575931231535,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.2755910185773836,
			"height": 7.275591018577446,
			"seed": 1462964360,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 272,
			"versionNonce": 267248267,
			"isDeleted": false,
			"id": "uyc4_nPCh2JAzoQbiQRlU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -128.17867350089057,
			"y": 564.612709630888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.2755910185773836,
			"height": 7.275591018577446,
			"seed": 1720696712,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 289,
			"versionNonce": 406822821,
			"isDeleted": false,
			"id": "qBw9MS4YJvyK5AYuhQNSz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -70.01463994744438,
			"y": 560.9749140551248,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.2755910185773836,
			"height": 7.275591018577446,
			"seed": 1686015624,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 294,
			"versionNonce": 1153915179,
			"isDeleted": false,
			"id": "o9JFcLmqg1tmyI_jcABiN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -39.83221108997725,
			"y": 586.4394822803606,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.2755910185773836,
			"height": 7.275591018577446,
			"seed": 2042330504,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 322,
			"versionNonce": 1356227333,
			"isDeleted": false,
			"id": "lIQQkevy_qypOMuYdJvam",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -86.60386768044816,
			"y": 511.08514713706836,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 7.2755910185773836,
			"height": 7.275591018577446,
			"seed": 1468173448,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 267,
			"versionNonce": 410581963,
			"isDeleted": false,
			"id": "NkWoFypIigCqQBqU1gvAv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -123.50150784609082,
			"y": 568.7701902129324,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 58.204728148619445,
			"height": 3.6377955092886918,
			"seed": 663731080,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					58.204728148619445,
					-3.6377955092886918
				]
			]
		},
		{
			"type": "line",
			"version": 292,
			"versionNonce": 75348581,
			"isDeleted": false,
			"id": "rZn_tW_8VUjcfCwHFsm-E",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -92.84008855351465,
			"y": 592.4158610233089,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 58.204728148619445,
			"height": 3.6377955092886918,
			"seed": 2082409096,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					58.204728148619445,
					-3.6377955092886918
				]
			]
		},
		{
			"type": "line",
			"version": 268,
			"versionNonce": 1461537387,
			"isDeleted": false,
			"id": "QLA1U76RWMlj-EBiHGQN4",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -92.32040348075896,
			"y": 593.1953886324422,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 31.7007894380874,
			"height": 24.425198419510018,
			"seed": 1072462216,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-31.7007894380874,
					-24.425198419510018
				]
			]
		},
		{
			"type": "line",
			"version": 282,
			"versionNonce": 738403781,
			"isDeleted": false,
			"id": "lb7o_RLanEsLh0elxD6T5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -34.37551786851736,
			"y": 589.8174356595314,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 31.7007894380874,
			"height": 24.425198419510018,
			"seed": 640944264,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097381,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-31.7007894380874,
					-24.425198419510018
				]
			]
		},
		{
			"type": "line",
			"version": 283,
			"versionNonce": 1702806795,
			"isDeleted": false,
			"id": "jONoC4xo9S7Bkp6Du0b98",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -127.13930335537952,
			"y": 567.2111349946658,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 42.61417596595354,
			"height": 52.4881923483086,
			"seed": 447854472,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					42.61417596595354,
					-52.4881923483086
				]
			]
		},
		{
			"type": "line",
			"version": 332,
			"versionNonce": 1250174245,
			"isDeleted": false,
			"id": "OZxeCC-O3B6GjR6a7breC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -65.29677969747127,
			"y": 564.612709630888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.708662619199057,
			"height": 50.40945205728646,
			"seed": 832669320,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-18.708662619199057,
					-50.40945205728646
				]
			]
		},
		{
			"type": "line",
			"version": 275,
			"versionNonce": 722987947,
			"isDeleted": false,
			"id": "PZ1IBxbXvjlB-9Uo06jkX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -93.35977362627,
			"y": 592.6757035596868,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.874016382355066,
			"height": 78.99213105884064,
			"seed": 398423432,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.874016382355066,
					-78.99213105884064
				]
			]
		},
		{
			"type": "line",
			"version": 286,
			"versionNonce": 594425989,
			"isDeleted": false,
			"id": "UGd3SLeHpY7gSKoNOzt5k",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -34.635360404895096,
			"y": 592.1560184869313,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 47.81102669350884,
			"height": 78.99213105884064,
			"seed": 38241416,
			"groupIds": [
				"mhal3iPwCZErHCl1gLc2l"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-47.81102669350884,
					-78.99213105884064
				]
			]
		},
		{
			"type": "rectangle",
			"version": 68,
			"versionNonce": 1007894091,
			"isDeleted": false,
			"id": "WqTMJb6vTNoRd9FV4Acyl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -850.7280852989944,
			"y": 446.25972455864826,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 985.4737429068979,
			"height": 198.29654582882705,
			"seed": 480739320,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 96,
			"versionNonce": 813621221,
			"isDeleted": false,
			"id": "gfDTH0bO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -673.1470353986242,
			"y": 660.9449563867098,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 581.659423828125,
			"height": 25,
			"seed": 1846683016,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets Address the algorithm and how it works step by step",
			"rawText": "Lets Address the algorithm and how it works step by step",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets Address the algorithm and how it works step by step",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1161,
			"versionNonce": 1129004267,
			"isDeleted": false,
			"id": "JXEao6F6",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -816.9225448864023,
			"y": 731.1223496120188,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 879.1990356445312,
			"height": 425,
			"seed": 1019071880,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "zs3bYJQagpD7a1EPicPER",
					"type": "arrow"
				}
			],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1. Compute the neighbors:\nWhen we pick a specific point that we want to map from high dimensions\nto low dimensions, we must have a criteria that optimally decides which are its\nneighbors, one method of doing this is by choosing an optimal radius, and every datapoint\nthat lies inside of it is its neighbor. Another Method is by choosing K nearest neighbors\ni.e K nearest points to our datapoint.\n\n\n\n2. Compute the weights:\nNext we Want to take our point that we have computed the neighbors Ni for and try\nto find the closest reconstruction of it using its neighbors, what this means is\nwe are practically finding the most \"accurate\" place for this point to lie in such\nthat it becomes linearly dependent on its neighbors and no longer goes in a different\ndimension.\nThe following is the Cost function we are trying to minimize such that the weights\nare the variables in this case:",
			"rawText": "1. Compute the neighbors:\nWhen we pick a specific point that we want to map from high dimensions\nto low dimensions, we must have a criteria that optimally decides which are its\nneighbors, one method of doing this is by choosing an optimal radius, and every datapoint\nthat lies inside of it is its neighbor. Another Method is by choosing K nearest neighbors\ni.e K nearest points to our datapoint.\n\n\n\n2. Compute the weights:\nNext we Want to take our point that we have computed the neighbors Ni for and try\nto find the closest reconstruction of it using its neighbors, what this means is\nwe are practically finding the most \"accurate\" place for this point to lie in such\nthat it becomes linearly dependent on its neighbors and no longer goes in a different\ndimension.\nThe following is the Cost function we are trying to minimize such that the weights\nare the variables in this case:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Compute the neighbors:\nWhen we pick a specific point that we want to map from high dimensions\nto low dimensions, we must have a criteria that optimally decides which are its\nneighbors, one method of doing this is by choosing an optimal radius, and every datapoint\nthat lies inside of it is its neighbor. Another Method is by choosing K nearest neighbors\ni.e K nearest points to our datapoint.\n\n\n\n2. Compute the weights:\nNext we Want to take our point that we have computed the neighbors Ni for and try\nto find the closest reconstruction of it using its neighbors, what this means is\nwe are practically finding the most \"accurate\" place for this point to lie in such\nthat it becomes linearly dependent on its neighbors and no longer goes in a different\ndimension.\nThe following is the Cost function we are trying to minimize such that the weights\nare the variables in this case:",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 1006,
			"versionNonce": 1472437061,
			"isDeleted": false,
			"id": "zs3bYJQagpD7a1EPicPER",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 69.23931701579579,
			"y": 837.7746256626202,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 125.00671007003825,
			"height": 102.06879865541646,
			"seed": 64278920,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JXEao6F6",
				"focus": -0.27392818521959805,
				"gap": 6.962826257666791
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
					64.2442542686507,
					-5.397829145884202
				],
				[
					125.00671007003825,
					-102.06879865541646
				]
			]
		},
		{
			"type": "text",
			"version": 723,
			"versionNonce": 743073675,
			"isDeleted": false,
			"id": "TL0GAojh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 183.47911158787565,
			"y": 575.8980466741134,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 484.56103515625,
			"height": 260,
			"seed": 565187208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "You have to take into account the fact that\nif the parameters of the neighbor choosing function\nis either too low or too high, it will fail and properly\naddressing the structure of the neighborhood.\n\nToo big of a neighborhood means it will assume other\nareas next to it that are not part of the neighborhood\n\nToo little of a neighborhood means it will not really\nreduce the dimensionality of the manifold at all\n\nRemember we want to take regions in the manifold that\nare close to locally linear and fit them in a global structure",
			"rawText": "You have to take into account the fact that\nif the parameters of the neighbor choosing function\nis either too low or too high, it will fail and properly\naddressing the structure of the neighborhood.\n\nToo big of a neighborhood means it will assume other\nareas next to it that are not part of the neighborhood\n\nToo little of a neighborhood means it will not really\nreduce the dimensionality of the manifold at all\n\nRemember we want to take regions in the manifold that\nare close to locally linear and fit them in a global structure",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "You have to take into account the fact that\nif the parameters of the neighbor choosing function\nis either too low or too high, it will fail and properly\naddressing the structure of the neighborhood.\n\nToo big of a neighborhood means it will assume other\nareas next to it that are not part of the neighborhood\n\nToo little of a neighborhood means it will not really\nreduce the dimensionality of the manifold at all\n\nRemember we want to take regions in the manifold that\nare close to locally linear and fit them in a global structure",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 496,
			"versionNonce": 1637477029,
			"isDeleted": false,
			"id": "uXHWKrJLO855D-GpukWLa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 372.8703777719153,
			"y": 886.4311382610349,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 133.9730589880331,
			"height": 119.35781618933859,
			"seed": 914267784,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fc53746f0a2516596212dccc83d2c599bfd42c3a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 283,
			"versionNonce": 223034923,
			"isDeleted": false,
			"id": "MDeFz2v-n_5VO9mq4bG0x",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.6084443649560365,
			"x": 451.65098286752595,
			"y": 942.5669516130718,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 39.871931540335254,
			"height": 25.5320263372323,
			"seed": 619191688,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 572,
			"versionNonce": 783240709,
			"isDeleted": false,
			"id": "ccPsj4jl2soFsC5ZVywBc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 202.1095417019994,
			"y": 886.431137878907,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 133.9730589880331,
			"height": 119.35781618933859,
			"seed": 1140360952,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fc53746f0a2516596212dccc83d2c599bfd42c3a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 472,
			"versionNonce": 1362641099,
			"isDeleted": false,
			"id": "z4Zli40uzhYQ8npwMA_7f",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.6084443649560365,
			"x": 294.5815133692262,
			"y": 963.3941381857303,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.0689258715651135,
			"height": 1.7755629089174356,
			"seed": 171763704,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 541,
			"versionNonce": 771835237,
			"isDeleted": false,
			"id": "wseHxeLW9cqjBvAWsXTOJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 543.6312141107338,
			"y": 886.4311378613227,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 133.9730589880331,
			"height": 119.35781618933859,
			"seed": 1541495944,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fc53746f0a2516596212dccc83d2c599bfd42c3a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 466,
			"versionNonce": 564916075,
			"isDeleted": false,
			"id": "cJ95C5MNV1FmlE-2zGeZ8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.6084443649560365,
			"x": 618.0533675816515,
			"y": 922.8423837360172,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 49.168481577347954,
			"height": 57.27461923927574,
			"seed": 1469352840,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 106,
			"versionNonce": 316494021,
			"isDeleted": false,
			"id": "2plQBrJST6AWnl-1Yv3gY",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 169.5159029050283,
			"y": 1014.106759122853,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 564.9242687229568,
			"height": 0.5782234070859431,
			"seed": 2008096504,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
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
					564.9242687229568,
					-0.5782234070859431
				]
			]
		},
		{
			"type": "line",
			"version": 35,
			"versionNonce": 284215819,
			"isDeleted": false,
			"id": "geFQpy3yiVjQDPwqphtLa",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 445.32846808501847,
			"y": 1007.1680782378216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.5782234070859431,
			"height": 17.346702212578066,
			"seed": 1247253128,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5782234070859431,
					17.346702212578066
				]
			]
		},
		{
			"type": "line",
			"version": 69,
			"versionNonce": 1256255525,
			"isDeleted": false,
			"id": "NxucbLAbfZFFFaIH1ILfh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 260.00786596357835,
			"y": 1007.1680779811342,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.5782234070859431,
			"height": 17.346702212578066,
			"seed": 707001992,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5782234070859431,
					17.346702212578066
				]
			]
		},
		{
			"type": "line",
			"version": 75,
			"versionNonce": 67195051,
			"isDeleted": false,
			"id": "HqUVk_UGZsLRiWti7c2Lk",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 610.6177439758104,
			"y": 1005.7889539724544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.5782234070859431,
			"height": 17.346702212578066,
			"seed": 971835272,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5782234070859431,
					17.346702212578066
				]
			]
		},
		{
			"type": "text",
			"version": 50,
			"versionNonce": 871998341,
			"isDeleted": false,
			"id": "lHMmKczW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 407.624374151913,
			"y": 1032.031684742517,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 75.40818786621094,
			"height": 20,
			"seed": 1378124024,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "just right",
			"rawText": "just right",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "just right",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 35,
			"versionNonce": 1552417611,
			"isDeleted": false,
			"id": "Ic5a7qvc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 225.69557320967607,
			"y": 1029.7187911141732,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 72.67214965820312,
			"height": 20,
			"seed": 508462216,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "too small",
			"rawText": "too small",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "too small",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 36,
			"versionNonce": 308603621,
			"isDeleted": false,
			"id": "37Z35Aft",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 583.9879054083024,
			"y": 1032.031685034634,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.41612243652344,
			"height": 20,
			"seed": 253894392,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "too big",
			"rawText": "too big",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "too big",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 175,
			"versionNonce": 1658806763,
			"isDeleted": false,
			"id": "COgaCT7J",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -666.104390459112,
			"y": 1156.122349762078,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 335.03046834977556,
			"height": 73.76817651738178,
			"seed": 65159,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_6vvuA0s6a5YQw7tcHAj9",
					"type": "arrow"
				}
			],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9175afb22dedfbe72de64655fdb099091ecd3e7b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 332,
			"versionNonce": 1185957445,
			"isDeleted": false,
			"id": "0pGSDW5l",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -199.75262985262214,
			"y": 1166.9199152895483,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 111.21096557210296,
			"height": 52.173045577035964,
			"seed": 10080,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_aioZGkNCdV1Yn-n0fa4L",
					"type": "arrow"
				}
			],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "86673082c71a6297fc53dbc0571481afb457d338",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 144,
			"versionNonce": 1880222859,
			"isDeleted": false,
			"id": "ZuDWkMuY",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -289.25537061199054,
			"y": 1175.5064379710907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 47.68418884277344,
			"height": 35,
			"seed": 2102650360,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "and",
			"rawText": "and",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "and",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 342,
			"versionNonce": 1136211365,
			"isDeleted": false,
			"id": "_aioZGkNCdV1Yn-n0fa4L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -78.23277724807326,
			"y": 1169.4615705679903,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 116.54474073626918,
			"height": 36.738650362131466,
			"seed": 31222776,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "0pGSDW5l",
				"focus": -0.5747362519194649,
				"gap": 10.30888703244591
			},
			"endBinding": {
				"elementId": "4J7aVyrt",
				"focus": 0.09418216576205635,
				"gap": 9.140487716987082
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
					82.75086585887414,
					-7.23065818184341
				],
				[
					116.54474073626918,
					29.507992180288056
				]
			]
		},
		{
			"type": "text",
			"version": 324,
			"versionNonce": 1473913643,
			"isDeleted": false,
			"id": "4J7aVyrt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -92.07365838911278,
			"y": 1208.1100504652654,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 345.07269287109375,
			"height": 120,
			"seed": 1328026872,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_aioZGkNCdV1Yn-n0fa4L",
					"type": "arrow"
				}
			],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This Equation shows invariance to\ntranslation because if we translate\none point by a constant and the weights\ndont sum up to one (dont describe ratios)\nthe reconstruction will also be influenced by\nthe translation",
			"rawText": "This Equation shows invariance to\ntranslation because if we translate\none point by a constant and the weights\ndont sum up to one (dont describe ratios)\nthe reconstruction will also be influenced by\nthe translation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This Equation shows invariance to\ntranslation because if we translate\none point by a constant and the weights\ndont sum up to one (dont describe ratios)\nthe reconstruction will also be influenced by\nthe translation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 79,
			"versionNonce": 1152203013,
			"isDeleted": false,
			"id": "bvxz85OL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -652.7875960276347,
			"y": 1239.1829909319542,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 550.9291381835938,
			"height": 40,
			"seed": 2072057336,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The weights wij summarize the contribution of the j th data point to\nthe i th reconstruction",
			"rawText": "The weights wij summarize the contribution of the j th data point to\nthe i th reconstruction",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The weights wij summarize the contribution of the j th data point to\nthe i th reconstruction",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 207,
			"versionNonce": 312640971,
			"isDeleted": false,
			"id": "_6vvuA0s6a5YQw7tcHAj9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -675.8456220681508,
			"y": 1192.1912430850773,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 114.70160548589956,
			"height": 7.609672887890383,
			"seed": 524096904,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "COgaCT7J",
				"focus": 0.30922896291864255,
				"gap": 9.741231609038778
			},
			"endBinding": {
				"elementId": "arg16uaX",
				"focus": -0.12270841570401923,
				"gap": 8.1950323408048
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
					-90.14535574885429,
					7.609672887890383
				],
				[
					-114.70160548589956,
					2.552882616899524
				]
			]
		},
		{
			"type": "text",
			"version": 449,
			"versionNonce": 1124716645,
			"isDeleted": false,
			"id": "arg16uaX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1217.8311270823551,
			"y": 1102.5632046154255,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 419.0888671875,
			"height": 120,
			"seed": 1354221816,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_6vvuA0s6a5YQw7tcHAj9",
					"type": "arrow"
				}
			],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This form gives invariance to Rotations\nand Scaling because even if all the xj points\nwere twice as far apart or upside down, the\nweights still describe the ratios of their contribution\n(Barycentric coordinates) which will not change the\nsolution",
			"rawText": "This form gives invariance to Rotations\nand Scaling because even if all the xj points\nwere twice as far apart or upside down, the\nweights still describe the ratios of their contribution\n(Barycentric coordinates) which will not change the\nsolution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This form gives invariance to Rotations\nand Scaling because even if all the xj points\nwere twice as far apart or upside down, the\nweights still describe the ratios of their contribution\n(Barycentric coordinates) which will not change the\nsolution",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 663065707,
			"isDeleted": false,
			"id": "vd1aG4LI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -768.0426315140813,
			"y": 1692.2966658460484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 781.439208984375,
			"height": 75,
			"seed": 602395528,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "\"A consequence of this symmetry is that the reconstruction weights\ncharacterize intrinsic geometric properties of each neighborhood, as opposed to\nproperties that depend on a particular frame of reference.\"",
			"rawText": "\"A consequence of this symmetry is that the reconstruction weights\ncharacterize intrinsic geometric properties of each neighborhood, as opposed to\nproperties that depend on a particular frame of reference.\"",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "\"A consequence of this symmetry is that the reconstruction weights\ncharacterize intrinsic geometric properties of each neighborhood, as opposed to\nproperties that depend on a particular frame of reference.\"",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 846,
			"versionNonce": 748452805,
			"isDeleted": false,
			"id": "gGYRzBAL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -898.8624555603108,
			"y": 1821.9554739533705,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1043.078857421875,
			"height": 225,
			"seed": 1743992056,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3. Map the point:\nNow that we have computed the more optimal weights according to out point through\nan optimization problem, we now freeze the weights (Basically memorize the structure of\nthe neighborhood and its effects on our datapoint) and find the best low dimensional mapping\nthat still holds this relation as close as possible.\nNote that W is a constant here and Y (which is our low dimensional vector representing\nthe possible new mapping for our points) is variable and we iterate and find the best coordinates\nin low dimensions that keep the same angles and ratio of lengths and other intrinsic properties preserved\nby the weights.",
			"rawText": "3. Map the point:\nNow that we have computed the more optimal weights according to out point through\nan optimization problem, we now freeze the weights (Basically memorize the structure of\nthe neighborhood and its effects on our datapoint) and find the best low dimensional mapping\nthat still holds this relation as close as possible.\nNote that W is a constant here and Y (which is our low dimensional vector representing\nthe possible new mapping for our points) is variable and we iterate and find the best coordinates\nin low dimensions that keep the same angles and ratio of lengths and other intrinsic properties preserved\nby the weights.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3. Map the point:\nNow that we have computed the more optimal weights according to out point through\nan optimization problem, we now freeze the weights (Basically memorize the structure of\nthe neighborhood and its effects on our datapoint) and find the best low dimensional mapping\nthat still holds this relation as close as possible.\nNote that W is a constant here and Y (which is our low dimensional vector representing\nthe possible new mapping for our points) is variable and we iterate and find the best coordinates\nin low dimensions that keep the same angles and ratio of lengths and other intrinsic properties preserved\nby the weights.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 284,
			"versionNonce": 1447939851,
			"isDeleted": false,
			"id": "JKsFedm7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -534.6630151303943,
			"y": 2059.3164514532773,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 314.6799779148994,
			"height": 71.92685209483415,
			"seed": 67871,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4283264771835b4fb41cb96b1bc697618a2c89b6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 372,
			"versionNonce": 1501739813,
			"isDeleted": false,
			"id": "lMcOcL5g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -661.5538347315613,
			"y": 2143.604280752724,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 634.3693237304688,
			"height": 60,
			"seed": 9101048,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Note that the weights of the neighbors of a singular point is independent\nfrom the weights of other datapoints, each datapoint has K amount of weights\ndescribing its neighborhood and we do this exact method for every single point",
			"rawText": "Note that the weights of the neighbors of a singular point is independent\nfrom the weights of other datapoints, each datapoint has K amount of weights\ndescribing its neighborhood and we do this exact method for every single point",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note that the weights of the neighbors of a singular point is independent\nfrom the weights of other datapoints, each datapoint has K amount of weights\ndescribing its neighborhood and we do this exact method for every single point",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 135,
			"versionNonce": 24491435,
			"isDeleted": false,
			"id": "5WGtozXR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -627.1973637995873,
			"y": 1449.2493651469842,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 489.4794616699219,
			"height": 25,
			"seed": 308126743,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "GuKbPWkSPv_Rh8p1m6JPA",
					"type": "arrow"
				}
			],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can Derive the following Using the Lagrangian:",
			"rawText": "We can Derive the following Using the Lagrangian:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can Derive the following Using the Lagrangian:",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 173,
			"versionNonce": 1110052485,
			"isDeleted": false,
			"id": "Y4ENYq2f",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -672.4338234408167,
			"y": 1478.4146659730732,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 582.3333333333333,
			"height": 84.96048632218844,
			"seed": 73563,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4e1e6f8654d9a715b5805948854d40e9dfb09fe8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 329,
			"versionNonce": 1479002187,
			"isDeleted": false,
			"id": "86SzHe49t3YKcWJ5UuplN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -514.897495776296,
			"y": 1279.1829913825982,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 267.26067845189937,
			"height": 58.84638791601454,
			"seed": 196916857,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7fef613491413afe444fe6b8914351273d96a3c3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 133,
			"versionNonce": 1968174565,
			"isDeleted": false,
			"id": "q84xTUT7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -545.6176967508759,
			"y": 1339.1039806200536,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 336.5893404307993,
			"height": 23.087355480812946,
			"seed": 22754,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9c16ff432f82627a7cc7502084df1528430e23c9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 110,
			"versionNonce": 1077839595,
			"isDeleted": false,
			"id": "Q4bn1ytz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -600.3737663551315,
			"y": 1374.7493069349102,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 446.1014794253114,
			"height": 20.47325630212782,
			"seed": 36556,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0df694bf2875206f404258b4bbf8efe42d373ff2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 70,
			"versionNonce": 1308750149,
			"isDeleted": false,
			"id": "Tk6hLbd7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -453.2671568891693,
			"y": 1404.9091288689563,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 144,
			"height": 19,
			"seed": 61929,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "XVd24uF20sXRi5TVcSJ-V",
					"type": "arrow"
				},
				{
					"id": "GuKbPWkSPv_Rh8p1m6JPA",
					"type": "arrow"
				}
			],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0a425e606aa649c42e535f76bff5c71f43453749",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 123,
			"versionNonce": 4485515,
			"isDeleted": false,
			"id": "XVd24uF20sXRi5TVcSJ-V",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -465.3081690360309,
			"y": 1400.3331927873407,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 165.92694505718964,
			"height": 24.748425703445264,
			"seed": 1331909593,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Tk6hLbd7",
				"focus": 1.2457628039126658,
				"gap": 12.04101214686159
			},
			"endBinding": {
				"elementId": "r27YsVwG",
				"focus": 1.8544086917886013,
				"gap": 13.918699572290052
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
					-62.433528479145934,
					24.748425703445264
				],
				[
					-165.92694505718964,
					23.061033041846713
				]
			]
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 1771929765,
			"isDeleted": false,
			"id": "5nIRJCyt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -711.2255620705938,
			"y": 1370.7727322169685,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 62.11212158203125,
			"height": 20,
			"seed": 202603639,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "because",
			"rawText": "because",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "because",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 179,
			"versionNonce": 695470123,
			"isDeleted": false,
			"id": "r27YsVwG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -717.1538136655106,
			"y": 1391.5205854489395,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 72,
			"height": 21,
			"seed": 26442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "XVd24uF20sXRi5TVcSJ-V",
					"type": "arrow"
				}
			],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5501674b407f17e5695d25ecc168d9a25b5746ca",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 105,
			"versionNonce": 1573921797,
			"isDeleted": false,
			"id": "CZwIAhu6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -712.4667072396492,
			"y": 1416.7056882246397,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 54.824652959148075,
			"height": 33.62578714827749,
			"seed": 36352,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1aa1069c00d6d5a01b7aa8d4ee2d9de3b4e39e40",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 66,
			"versionNonce": 1102564043,
			"isDeleted": false,
			"id": "GuKbPWkSPv_Rh8p1m6JPA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -332.00414876974594,
			"y": 1425.6440827113188,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 80.99484775672988,
			"height": 15.18653395438696,
			"seed": 2069721303,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Tk6hLbd7",
				"focus": -0.6842084461031026,
				"gap": 1.734953842362529
			},
			"endBinding": {
				"elementId": "5WGtozXR",
				"focus": 0.47302005009145265,
				"gap": 15.730783348205705
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
					0,
					15.18653395438696
				],
				[
					80.99484775672988,
					7.874499087459753
				]
			]
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 781671269,
			"isDeleted": false,
			"id": "8CJcUzda",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -246.56355340509924,
			"y": 1405.5015689471254,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 100.17332458496094,
			"height": 44.144803650091205,
			"seed": 1160689913,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"fontSize": 11.771947640024322,
			"fontFamily": 1,
			"text": "matrix of inner\nproducts between\nneighbors of i",
			"rawText": "matrix of inner\nproducts between\nneighbors of i",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "matrix of inner\nproducts between\nneighbors of i",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 96,
			"versionNonce": 766130539,
			"isDeleted": false,
			"id": "w9PTgU5g",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -480.51978275868,
			"y": 1563.3751521565734,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 206.39351098338489,
			"height": 55.33739062598001,
			"seed": 31062,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "17093277e75f7eba6c16b90f952a358c8a544029",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 126,
			"versionNonce": 71345861,
			"isDeleted": false,
			"id": "Z7tYdydb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -456.9850612421047,
			"y": 1618.7125425230993,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 159.32406786866986,
			"height": 58.77975319426655,
			"seed": 76073,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097382,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "29abfe972251be29677c979b05d3303e28d6097a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 55,
			"versionNonce": 1519768587,
			"isDeleted": false,
			"id": "0Z_IRWSz88l3haI_dTCFP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -738.7799751048079,
			"y": 2204.567134856845,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 857,
			"height": 178,
			"seed": 507973271,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3173027f47d81c54653bd215c48e233de035a2be",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 47,
			"versionNonce": 560563749,
			"isDeleted": false,
			"id": "e-eJQPbZyxMmq32iQrfcQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -651.5744941597961,
			"y": 2377.5566615251014,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 528,
			"height": 95,
			"seed": 1502014327,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "0htXxJ5_7DeQj2OQLESlT",
					"type": "arrow"
				}
			],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "830189619a6246c10211a66319c2b5ca4d17ecb2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 58,
			"versionNonce": 678763179,
			"isDeleted": false,
			"id": "iEibfhdZ9Msd5vgnhUacU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -648.1499139804749,
			"y": 2474.484386661976,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 378.99999999999994,
			"height": 189,
			"seed": 1801722041,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "0htXxJ5_7DeQj2OQLESlT",
					"type": "arrow"
				}
			],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "357bde7fb1a7de684ad70b6b66c198cdd083a550",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 144,
			"versionNonce": 419395973,
			"isDeleted": false,
			"id": "0htXxJ5_7DeQj2OQLESlT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -654.9501611616921,
			"y": 2393.3049795066945,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 79.94168313727175,
			"height": 61.89033533208158,
			"seed": 558244761,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "e-eJQPbZyxMmq32iQrfcQ",
				"focus": 0.7941579993267986,
				"gap": 3.3756670018959767
			},
			"endBinding": {
				"elementId": "iEibfhdZ9Msd5vgnhUacU",
				"focus": 1.2186997091585485,
				"gap": 21.867835795369956
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
					-74.78415519293151,
					7.736291916510254
				],
				[
					-77.36291916510163,
					61.89033533208158
				],
				[
					2.5787639721701225,
					59.31157135991134
				]
			]
		},
		{
			"type": "image",
			"version": 118,
			"versionNonce": 334662987,
			"isDeleted": false,
			"id": "Ie3I0fMY_C9dtWCeYZR3H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -991.9216438309344,
			"y": 2386.605456179693,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 242,
			"height": 74,
			"seed": 1713884791,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3a0e5b5d004eac7c67fd838a68b79e17ed8d86a2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 85,
			"versionNonce": 1145045221,
			"isDeleted": false,
			"id": "DS06XCWW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -973.7113876767482,
			"y": 2368.806721771079,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 232.65650939941406,
			"height": 20,
			"seed": 419022841,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Comes from the identity that",
			"rawText": "Comes from the identity that",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Comes from the identity that",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 186,
			"versionNonce": 543730667,
			"isDeleted": false,
			"id": "26QTUhVgI_wqVTipUo4PC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -823.4432426458417,
			"y": 2431.4001154618977,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 43.91139226265341,
			"height": 38.4320940306211,
			"seed": 1529623735,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "B2Z14Jzj-owcuTHVwwNaX",
				"focus": 0.028404195084689395,
				"gap": 12.936285284831229
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
					-11.15480284477826,
					20.140616247516846
				],
				[
					-43.91139226265341,
					38.4320940306211
				]
			]
		},
		{
			"type": "image",
			"version": 127,
			"versionNonce": 2025364549,
			"isDeleted": false,
			"id": "B2Z14Jzj-owcuTHVwwNaX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -957.3441864100289,
			"y": 2482.76849477735,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 98.62071104923656,
			"height": 17.49722292809036,
			"seed": 157175863,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "26QTUhVgI_wqVTipUo4PC",
					"type": "arrow"
				}
			],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5f1490bcb48131c7c4efae1850bdeddfdef95b59",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 87,
			"versionNonce": 31585931,
			"isDeleted": false,
			"id": "fHYWM5sbDM0IwrE3LkbXu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -846.0567354239369,
			"y": 2485.688224236075,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 97.59258779973317,
			"height": 17.556338545983742,
			"seed": 1806964729,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8sYQ16g_cO4Tvf3SfJ5gp",
					"type": "arrow"
				}
			],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f3d82e26b04fa79ae0d195ccf594e914c513b4fd",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 95,
			"versionNonce": 2118568869,
			"isDeleted": false,
			"id": "8sYQ16g_cO4Tvf3SfJ5gp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -785.6408552274261,
			"y": 2431.4001154618977,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 7.4365352298520975,
			"height": 48.95719026319421,
			"seed": 708984313,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "fHYWM5sbDM0IwrE3LkbXu",
				"focus": 0.42288862142294953,
				"gap": 5.330918510982883
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
					7.4365352298520975,
					48.95719026319421
				]
			]
		},
		{
			"type": "text",
			"version": 59,
			"versionNonce": 119074091,
			"isDeleted": false,
			"id": "jTCXa5FI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -696.6782321823964,
			"y": 2676.9000452081104,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 517.489013671875,
			"height": 20,
			"seed": 1243863639,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The solution consists of the p eigenvectors of M orthogonal to 1",
			"rawText": "The solution consists of the p eigenvectors of M orthogonal to 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The solution consists of the p eigenvectors of M orthogonal to 1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 59,
			"versionNonce": 1159204613,
			"isDeleted": false,
			"id": "iFEoDfVR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -603.462076176537,
			"y": 2706.9000452081104,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 331.05670166015625,
			"height": 20,
			"seed": 1046403737,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "corresponding to the smallest eigenvalues.",
			"rawText": "corresponding to the smallest eigenvalues.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "corresponding to the smallest eigenvalues.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 34,
			"versionNonce": 1131941835,
			"isDeleted": false,
			"id": "9F4sQLNZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -723.0329256122152,
			"y": 2732.0672141390287,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 545.217041015625,
			"height": 40,
			"seed": 1672487639,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The columns of Y are these eigenvectors and the new locations (in p\ndimensions) are the corresponding rows",
			"rawText": "The columns of Y are these eigenvectors and the new locations (in p\ndimensions) are the corresponding rows",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The columns of Y are these eigenvectors and the new locations (in p\ndimensions) are the corresponding rows",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 461,
			"versionNonce": 1537861221,
			"isDeleted": false,
			"id": "Xi8qjB3x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1850.625015686019,
			"y": -412.3307019888671,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 256.53704833984375,
			"height": 35,
			"seed": 2093614967,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Limitations of LLE",
			"rawText": "Limitations of LLE",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Limitations of LLE",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 1289,
			"versionNonce": 2031738475,
			"isDeleted": false,
			"id": "RLgAtltW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2210.9634184978104,
			"y": -354.44031287463804,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 996.6190795898438,
			"height": 700,
			"seed": 1318389305,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1714046097383,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1. Sensitivity to noise:\nThe weights vectors that capture the high dimensional structure are highly\nsensitive to noise which means small perturbation of the input may yield an entirely\ndifferent embedding\n\n\n2. Sensitivity to non-uniform sampling of the manifold:\nIf sampling from the manifold focuses a lot on one area but draws little to no samples\nfrom another neighborhood/idea then the local structure of that area is not preserved\nnor embedded.\n\n\n3. No mapping:\nWhile we do map points from high dimensions to low, we do not actually get the mapping\nin explicit form (though one can be learned in a supervised fashion from the pairs {𝑋𝑖,𝑌𝑖})\n\n\n4. Complexity:\nQuadratic complexity on the training set size O(dn^2)\n\n\n5. intrinsic dimensionality\nUnlike ISOMAP, no robust method to compute the intrinsic dimensionality\nwhich I THINK means that we dont actually know the best low dimensional structure's dimensionality\nthat best represents this high dimensional manifold??\n\n\n6. No robust method to define the neighborhood size K, its mostly heuristics",
			"rawText": "1. Sensitivity to noise:\nThe weights vectors that capture the high dimensional structure are highly\nsensitive to noise which means small perturbation of the input may yield an entirely\ndifferent embedding\n\n\n2. Sensitivity to non-uniform sampling of the manifold:\nIf sampling from the manifold focuses a lot on one area but draws little to no samples\nfrom another neighborhood/idea then the local structure of that area is not preserved\nnor embedded.\n\n\n3. No mapping:\nWhile we do map points from high dimensions to low, we do not actually get the mapping\nin explicit form (though one can be learned in a supervised fashion from the pairs {𝑋𝑖,𝑌𝑖})\n\n\n4. Complexity:\nQuadratic complexity on the training set size O(dn^2)\n\n\n5. intrinsic dimensionality\nUnlike ISOMAP, no robust method to compute the intrinsic dimensionality\nwhich I THINK means that we dont actually know the best low dimensional structure's dimensionality\nthat best represents this high dimensional manifold??\n\n\n6. No robust method to define the neighborhood size K, its mostly heuristics",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Sensitivity to noise:\nThe weights vectors that capture the high dimensional structure are highly\nsensitive to noise which means small perturbation of the input may yield an entirely\ndifferent embedding\n\n\n2. Sensitivity to non-uniform sampling of the manifold:\nIf sampling from the manifold focuses a lot on one area but draws little to no samples\nfrom another neighborhood/idea then the local structure of that area is not preserved\nnor embedded.\n\n\n3. No mapping:\nWhile we do map points from high dimensions to low, we do not actually get the mapping\nin explicit form (though one can be learned in a supervised fashion from the pairs {𝑋𝑖,𝑌𝑖})\n\n\n4. Complexity:\nQuadratic complexity on the training set size O(dn^2)\n\n\n5. intrinsic dimensionality\nUnlike ISOMAP, no robust method to compute the intrinsic dimensionality\nwhich I THINK means that we dont actually know the best low dimensional structure's dimensionality\nthat best represents this high dimensional manifold??\n\n\n6. No robust method to define the neighborhood size K, its mostly heuristics",
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
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "triangle",
		"scrollX": 1502.4148320492022,
		"scrollY": 1026.5639863110493,
		"zoom": {
			"value": 0.7314513364621459
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