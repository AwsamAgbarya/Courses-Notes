---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Fischer's linear discriminant ^DTg1Gg1I

What is the concept behind 
fischer's discriminant? ^meUocH6e

Instead of spending our time making assumptions about the distributions
and predicting/estimating the values at which those distributions
are correct, why not just assume the model from the start?
i.e assume that the model is linear and continue solving! ^obgTPIYm

how do we estimate
our parameters
w and b ^VkLaF7Uz

Naive Solution ^EnrYkj8V

Mean seperation ^jLIrfgUy

Project all datapoints onto a line such that on that
lines their means are as far apart as possible! ^rVRk5Esx

Z = W X ^SNoHeLML

T ^gyqel4Cj

Projections
(Assuming |w| = 1 ) ^h6DtoAoh

%%***>>>text element-link:[[Projections]]<<<***%%how did we get this? ^inWNlylq

We can compute the means for each class after projections ^o4BprxZA

Thus we are left with finding the right W such that it maximizes the difference
between our means given our constraints ^rwQCWClv

Notice how the best w vector we can find is the one
that aligns and is parallel to u2-u1
 ^OLu3JNR0

w ^i1RU028w

We can notice that there is still significant overlap between
the classes in the projected space!

furthermore, we notice that this seperation method is not ideal
because it does not take into account the variance of each class
meaning in certain cases this will not work ^PcacPwAT

What if we controlled the orientation of our
projection and moved it around to match
the variances? ^fQReoBte

Fischer's idea! ^gqVziAEF

 In addition to maximizing the separation
between class means in projected space, how about we
also consider to reduce the within-class variance! ^GeURAulf

a value indicating positive "distances" of
projected points from their mean, the larger
this value is the more space the projected
class takes, thus we want to make it
minimal and concise ^l5r2fAGq

Our new objective! ^jJD2OHjp

lets simplify ^2a5GXaDd

Projections of original points onto w ^m2v4Wc8Y

The definition of the covariance matrix
so realistically, Sj is just the covariance matrix
in projected space (unnormalized) ^UXghCG4Q

This is just an empathy term for 
the scatter matrix Sj ^fadVd9eR

we know from linear algebra whenever
we have 


it is called an empathy term as we
transform our basis into w to empathize
with the basis of what we are trying to calculate
and then transform back after we are done! ^BkmPCdUY

or written as an objective function to maximize ^XVMbb1JR

Or ^jai9yquq

Rayleigh Co-efficient ^zXOl9Ceh

constrained version of this ^YNfChw3w

%%***>>>text element-link:[[Lagrange]]<<<***%%We can use the lagrange method to find the optimal
solution for this objective! ^k5nY7cOj

Which is a generalized eignevalue issue
describing that Sb's effect on w
is the same as a scalar product of Sw's
effect on w ^07jNDomH

if Sw is invertible ^bETXzbBR

The optimum is defined up to a scaling factor
i.e we dont care about scalars multiplied by w
as it brings us the same solution ^OxLKRkvi

Fisher Discriminant requires inversion of a covariance matrix
(only tractable for low-dimensional data) ^5U1vbTUK

PROS ^Aewa8B2u

CONS ^lFN4fNIA

V.S ^lpVrSrdL

Accurate when the means/covariances
describe well the data

Close to optimal when the data is
Gaussian of fixed covariance.

The Fisher discriminant is given in
closed form and is fast to compute. ^232YRj7v

Although applicable to non-Gaussian
distributions, the resulting decision boundary can
become in that case strongly suboptimal

In particular, like principal component analysis,
Fisher Discriminant is not robust to outliers. ^ofuZdUiS

Lets take a second to understand this objective
as it represents two objective functions written as
Rayleigh Quotients
we would like to analyze spectrum of these matrices ^LJoY77bI

Maximizing the range of the Rayleigh Quotient on the left
i.e maximizing the spectrum of the Between classes matrix
results in maximizing the eigenvalue of this matrix for the eigenvector w

the eigenvalues of this matrix represent the magnitude of the spread in
the direction of the principal components while The eigenvectors show the direction
since our eigenvector is w, we are maximizing the the spread of points
along w! ^H5zBz3WH

V and lambda are eigenvalues
and eigenvectors of the covariance
matrix describing this distribution ^rNCrcqPD

our eigenvalue describes
the variance/spread
in direction of w, which is
the distance between the
two means! ^bH9MbEnP

w ^fzFMeSLF

and in our case ^jxPH6dkv

Minimizing this Quotient means
maximizing its inverse ^5mtxBjre

Minimizing this Quotient means
Minimizing its spectrum and thus
minimizing its eigenvectors blah
blah blah which describes
the magnitude and its PCA
which for this matrix (Which describes
how far the points are from the mean)
is like minimizing the distance of points
from the mean in protective space ^yiZwcKhe

Combining both objectives we multiply them with each other and Arrive
at our objective function to maximize! ^6neHzVxb

Now we cant just take any vector W here otherwise we would have infinite
solutions, since we know W is in the direction of the eigenvector of the matrices
we can suffice by taking the Unit eigenvector instead...
(This is because any scaled version of that eigenvector 
is gonna have a solution that maximizes this function but it
all stems from the direction w) ^UpO4O0QX

In other words ^IZd2aFwS

If we have an objective function J that we
want to maximize, multiplying the function by
any constant scalar that does not depend
on the parameters of J is useless because
it doesn't not affect the solution.
(take our constant values from a max function) ^UBNaxOQu

Quadratic representation ^XidIPDcW

This assumption leads us to an optimal
classifier only when the two classes have
a the same scatter/covariance matrix because we are making
this assumption that this matrix SW represents BOTH
their "spread" but this is only true when
S1 and S2 have to have the same structure ^na3jWo0G


# Embedded files
d8dfee08b57bcf1220b4a997ea3145849bd57517: $$\frac{w^T \color{orange} S_B \color{black} w}{w^Tw}$$
65906daa2be3370807b0bc898449229ca969b5c3: $$\frac{w^T \color{green} S_w \color{black} w}{w^Tw}$$
fc40124908b395c6690f3742665115736b2b02ef: $$\color{red} v_1, \lambda_1$$
dbe61c7bbe5bf8e511bb9f296840fdd3d4bf0b7a: $$\color{blue} v_2 , \lambda_2$$
71db7c36b67ca672b6dc20dd34cab376312feb95: $$\color{orange} w, \lambda_1$$
9ba413074885b507fef36460f8252594f14203ec: $$\frac{w^Tw}{w^T \color{green} S_w \color{black} w}$$
87cfb03e193ad5c207e70119bfb05aaf86c34974: $$\alpha w$$
e171ab9c2159f4b1ca128d7a90ad08fbb3777836: $$\mathcal{L}(w,\lambda) = w^T S_B w + \lambda \cdot (1 - w^T S_W w)$$
a5a8acab81d97208afd0ef8274c6b80af33994d7: $$S_B w = \lambda S_W w$$
449a55458a42f1398fe2253cd2d9480a580860a8: [[Pasted Image 20231227104758_505.png]]
b82f28b646059b0ca443d1b49e5375aba873b84e: [[Pasted Image 20231227111216_601.png]]
98d27e3520411c83f7ba85a223dc32f16eb2f929: [[Pasted Image 20231227111331_605.png]]
ae7160192538e55aa6bb81a9fd1cae1bab7aa515: [[Pasted Image 20231227111432_617.png]]
3ab4450129fb23b297d75c764c516998b69ddb8c: [[Pasted Image 20231227111512_628.png]]
6ddfa0c50eaf9f1ad98ab8af8b8ee32e0903f487: [[Pasted Image 20231227111716_681.png]]
1b693af5b821a3377e14463fc3d7de79ba570b42: [[Pasted Image 20231227111816_698.png]]
3a8ddea7f349b7a3f80f72473d45b69d38b7efcc: [[Pasted Image 20231227111832_711.png]]
073f4707a037656acb18f987ce16c3585126ecb4: [[Pasted Image 20231227111902_727.png]]
96068472038066230d3805c50ac8d78b106b0b2d: [[Pasted Image 20231227112521_769.png]]
2d6f2adec9930ab0c82d585d0d668eeb12088eaa: [[Pasted Image 20231227112952_837.png]]
9a71a636005183bf77b3059d91793bdd8d272353: [[Pasted Image 20231227113053_855.png]]
a50dd23a8098a8378e948e195357f4ee692c9c2e: [[Pasted Image 20231227113529_925.png]]
d49fbd8b375f21bc0abdd8a772457a23ac76de6b: [[Pasted Image 20231227113652_946.png]]
13ae799ac94c664820c4ebb28ed488f83c4d9e32: [[Pasted Image 20231227113724_952.png]]
5b001231a8f0a9d883b38cc5b7960e73d9819c81: [[Pasted Image 20231227113740_963.png]]
5b8a7455dedb8026378c1955bcbed3784c117d66: [[Pasted Image 20231227131636_477.png]]
eadc58658c743b5207e32d5b66ae65ca1f6969c8: [[Pasted Image 20231227132100_883.png]]
f3b5db89186ce84c59f45c12cc8ae432bb2d7898: [[Pasted Image 20231227132208_903.png]]
c0f6e8ed8fec32f5794180179733fd6db99102b4: [[Pasted Image 20231227132302_927.png]]
96e69abc7c0cdac1b515229ea3c5f72ce1ca818e: [[Pasted Image 20231227132432_942.png]]
27b960c0eaade277b9467a11017a9067588dca90: [[Pasted Image 20231227132647_952.png]]
065b2c53a310c2f0086c77e60faa484c48d58bfe: [[Pasted Image 20231227132705_963.png]]

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
			"version": 388,
			"versionNonce": 362957335,
			"isDeleted": false,
			"id": "U5dYV3RUeqmwOEOmMoKSP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 58.70613988498013,
			"y": 496.4742545189452,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 156.52976578123582,
			"height": 38.548375155080464,
			"seed": 1748616503,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314480,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3ab4450129fb23b297d75c764c516998b69ddb8c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 71,
			"versionNonce": 1141917401,
			"isDeleted": false,
			"id": "gNuexxkktALhu8blryc-8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -215,
			"y": -415,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 388,
			"height": 190,
			"seed": 1366479895,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "DTg1Gg1I"
				}
			],
			"updated": 1703680314480,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 42,
			"versionNonce": 2032070455,
			"isDeleted": false,
			"id": "DTg1Gg1I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -122.133129917866,
			"y": -355.175144212722,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 201.90882873535156,
			"height": 70,
			"seed": 430113079,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314480,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Fischer's linear\ndiscriminant",
			"rawText": "Fischer's linear discriminant",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "gNuexxkktALhu8blryc-8",
			"originalText": "Fischer's linear discriminant",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 112,
			"versionNonce": 1609827257,
			"isDeleted": false,
			"id": "meUocH6e",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -210.09698486328125,
			"y": -215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 385.67364501953125,
			"height": 70,
			"seed": 1371292375,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314480,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is the concept behind \nfischer's discriminant?",
			"rawText": "What is the concept behind \nfischer's discriminant?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is the concept behind \nfischer's discriminant?",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 376,
			"versionNonce": 1275719767,
			"isDeleted": false,
			"id": "obgTPIYm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -375.7095947265625,
			"y": -142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 719.419189453125,
			"height": 100,
			"seed": 565403257,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Instead of spending our time making assumptions about the distributions\nand predicting/estimating the values at which those distributions\nare correct, why not just assume the model from the start?\ni.e assume that the model is linear and continue solving!",
			"rawText": "Instead of spending our time making assumptions about the distributions\nand predicting/estimating the values at which those distributions\nare correct, why not just assume the model from the start?\ni.e assume that the model is linear and continue solving!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Instead of spending our time making assumptions about the distributions\nand predicting/estimating the values at which those distributions\nare correct, why not just assume the model from the start?\ni.e assume that the model is linear and continue solving!",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 52,
			"versionNonce": 1175266457,
			"isDeleted": false,
			"id": "HrVGIoC0Ag-me8pXyVcuz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -121.3949579831935,
			"y": -29.843512208032777,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 211.14285714285705,
			"height": 38.238470191226085,
			"seed": 1201192889,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "M_CD4SA0nbPbw6PZqwZMo",
					"type": "arrow"
				}
			],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "449a55458a42f1398fe2253cd2d9480a580860a8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 58,
			"versionNonce": 1211616631,
			"isDeleted": false,
			"id": "M_CD4SA0nbPbw6PZqwZMo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -16.41176470588232,
			"y": 22.296218487394867,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0,
			"height": 101.17647058823536,
			"seed": 1900775865,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "HrVGIoC0Ag-me8pXyVcuz",
				"focus": 0.005571917535617562,
				"gap": 13.90126050420156
			},
			"endBinding": {
				"elementId": "EnrYkj8V",
				"focus": -0.0023204313965428432,
				"gap": 13.508403361344449
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
					0,
					101.17647058823536
				]
			]
		},
		{
			"type": "text",
			"version": 104,
			"versionNonce": 1376725369,
			"isDeleted": false,
			"id": "VkLaF7Uz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -7.1291023703182645,
			"y": 31.855042016806692,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 155.5523223876953,
			"height": 60,
			"seed": 1160786711,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "how do we estimate\nour parameters\nw and b",
			"rawText": "how do we estimate\nour parameters\nw and b",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "how do we estimate\nour parameters\nw and b",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 56,
			"versionNonce": 2028799639,
			"isDeleted": false,
			"id": "EnrYkj8V",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -112.7600780241296,
			"y": 136.98109243697468,
			"strokeColor": "#f08c00",
			"backgroundColor": "#b2f2bb",
			"width": 193.14480590820312,
			"height": 35,
			"seed": 1301778615,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "M_CD4SA0nbPbw6PZqwZMo",
					"type": "arrow"
				}
			],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Naive Solution",
			"rawText": "Naive Solution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Naive Solution",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 50,
			"versionNonce": 490574425,
			"isDeleted": false,
			"id": "jLIrfgUy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -124.08461793530898,
			"y": 169.24299719887944,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 223.41293334960938,
			"height": 35,
			"seed": 1632083897,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Mean seperation",
			"rawText": "Mean seperation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mean seperation",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 167,
			"versionNonce": 215882679,
			"isDeleted": false,
			"id": "rVRk5Esx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -274.5883418064492,
			"y": 207.5763305322128,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 532.0394287109375,
			"height": 50,
			"seed": 1924235415,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Project all datapoints onto a line such that on that\nlines their means are as far apart as possible!",
			"rawText": "Project all datapoints onto a line such that on that\nlines their means are as far apart as possible!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Project all datapoints onto a line such that on that\nlines their means are as far apart as possible!",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 256,
			"versionNonce": 1282137913,
			"isDeleted": false,
			"id": "7g2zwg-EcoERsT-QMz0hT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -275.2352941176471,
			"y": 243.5287114845937,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 286.6666666666665,
			"height": 162.85714285714283,
			"seed": 1670884761,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-152.3809523809524,
					35.23809523809524
				],
				[
					-197.14285714285717,
					-110.47619047619048
				],
				[
					-286.6666666666665,
					-127.61904761904759
				]
			]
		},
		{
			"type": "text",
			"version": 152,
			"versionNonce": 1747946711,
			"isDeleted": false,
			"id": "SNoHeLML",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -686.3866711143687,
			"y": 108.54679817357818,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 110.17616271972656,
			"height": 32.36286569196797,
			"seed": 125969049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 25.890292553574376,
			"fontFamily": 1,
			"text": "Z = W X",
			"rawText": "Z = W X",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z = W X",
			"lineHeight": 1.25,
			"baseline": 22
		},
		{
			"type": "text",
			"version": 149,
			"versionNonce": 503156761,
			"isDeleted": false,
			"id": "gyqel4Cj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -608.3866749499063,
			"y": 93.75234528582145,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 20.803573608398438,
			"height": 32.36286569196797,
			"seed": 540196441,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 25.890292553574376,
			"fontFamily": 1,
			"text": "T",
			"rawText": "T",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "T",
			"lineHeight": 1.25,
			"baseline": 22
		},
		{
			"type": "text",
			"version": 135,
			"versionNonce": 1987434999,
			"isDeleted": false,
			"id": "h6DtoAoh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -718.2940724347308,
			"y": 43.30057860116189,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 181.674072265625,
			"height": 52.13488438065059,
			"seed": 1420798263,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 20.853953752260235,
			"fontFamily": 1,
			"text": "Projections\n(Assuming |w| = 1 )",
			"rawText": "Projections\n(Assuming |w| = 1 )",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Projections\n(Assuming |w| = 1 )",
			"lineHeight": 1.25,
			"baseline": 44
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 937829625,
			"isDeleted": false,
			"id": "inWNlylq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -702.4621338189818,
			"y": 145.31442577030796,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 161.12034606933594,
			"height": 20,
			"seed": 483355639,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": "[[Projections]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "how did we get this?",
			"rawText": "how did we get this?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "how did we get this?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 1018528535,
			"isDeleted": false,
			"id": "o4BprxZA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -311.8202172714798,
			"y": 272.45728291316505,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 596.9793701171875,
			"height": 25,
			"seed": 1575082743,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can compute the means for each class after projections",
			"rawText": "We can compute the means for each class after projections",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can compute the means for each class after projections",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 118,
			"versionNonce": 900275673,
			"isDeleted": false,
			"id": "R8cu3v6-gf6QsyiDFDLIE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -184.7829131652669,
			"y": 302.8513063265971,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 393.3809523809524,
			"height": 81.43930991990142,
			"seed": 401737241,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b82f28b646059b0ca443d1b49e5375aba873b84e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 210,
			"versionNonce": 727910455,
			"isDeleted": false,
			"id": "rwQCWClv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -419.50911685764027,
			"y": 383.686300113618,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 792.5791015625,
			"height": 50,
			"seed": 587824311,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Thus we are left with finding the right W such that it maximizes the difference\nbetween our means given our constraints",
			"rawText": "Thus we are left with finding the right W such that it maximizes the difference\nbetween our means given our constraints",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Thus we are left with finding the right W such that it maximizes the difference\nbetween our means given our constraints",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 93,
			"versionNonce": 1985608377,
			"isDeleted": false,
			"id": "xVrJq7kAVhW52i-grxZcd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -211.92014946418283,
			"y": 450.7009353847428,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 441.55291008495516,
			"height": 36.30106136722352,
			"seed": 577484249,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "98d27e3520411c83f7ba85a223dc32f16eb2f929",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 184,
			"versionNonce": 811788631,
			"isDeleted": false,
			"id": "xvg57yxWDThuI3SpDD0pv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -212.59194503422208,
			"y": 487.1263297935558,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 235.2484511532257,
			"height": 42.588081674290855,
			"seed": 565156503,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ae7160192538e55aa6bb81a9fd1cae1bab7aa515",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 157,
			"versionNonce": 714881945,
			"isDeleted": false,
			"id": "OLu3JNR0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -292.22783694691367,
			"y": 533.3063777903175,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 523.1195068359375,
			"height": 75,
			"seed": 1126729047,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Notice how the best w vector we can find is the one\nthat aligns and is parallel to u2-u1\n",
			"rawText": "Notice how the best w vector we can find is the one\nthat aligns and is parallel to u2-u1\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Notice how the best w vector we can find is the one\nthat aligns and is parallel to u2-u1\n",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 99,
			"versionNonce": 151627383,
			"isDeleted": false,
			"id": "BH53E_ZQGCokoTfCASavu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -139.51599873406025,
			"y": 593.3608458883323,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 259.8542426086577,
			"height": 38.6372197464768,
			"seed": 182489879,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6ddfa0c50eaf9f1ad98ab8af8b8ee32e0903f487",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 113,
			"versionNonce": 581132409,
			"isDeleted": false,
			"id": "ILfaILQYv7Vewct-KiWHA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -117.30076502967455,
			"y": 651.2935731376338,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 235.2193451271153,
			"height": 201.79023923049684,
			"seed": 48685687,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1b693af5b821a3377e14463fc3d7de79ba570b42",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 148,
			"versionNonce": 1411104663,
			"isDeleted": false,
			"id": "2mQ8ZB85GRhasqzmP5VMs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -18.366469309326078,
			"y": 686.4945218546397,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 8.3098128382179,
			"height": 7.686576875351556,
			"seed": 1264409879,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3a8ddea7f349b7a3f80f72473d45b69d38b7efcc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 127,
			"versionNonce": 1546840409,
			"isDeleted": false,
			"id": "E65-gj-L_ipX1g4F2Xo4w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 47.17515365616816,
			"y": 719.1226654634479,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 9.449185205679681,
			"height": 8.722324805242783,
			"seed": 1524548729,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "073f4707a037656acb18f987ce16c3585126ecb4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 40,
			"versionNonce": 1674425527,
			"isDeleted": false,
			"id": "i1RU028w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -18.864373872270136,
			"y": 793.4225131160613,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 12.17999267578125,
			"height": 25,
			"seed": 388641913,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "w",
			"rawText": "w",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "w",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 378,
			"versionNonce": 1352554041,
			"isDeleted": false,
			"id": "PcacPwAT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -245.93445940165185,
			"y": 872.7601766106851,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 532.1130981445312,
			"height": 120,
			"seed": 921186903,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "tcHTmZKpZdJcvQQQ7di5O",
					"type": "arrow"
				}
			],
			"updated": 1703680314481,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can notice that there is still significant overlap between\nthe classes in the projected space!\n\nfurthermore, we notice that this seperation method is not ideal\nbecause it does not take into account the variance of each class\nmeaning in certain cases this will not work",
			"rawText": "We can notice that there is still significant overlap between\nthe classes in the projected space!\n\nfurthermore, we notice that this seperation method is not ideal\nbecause it does not take into account the variance of each class\nmeaning in certain cases this will not work",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can notice that there is still significant overlap between\nthe classes in the projected space!\n\nfurthermore, we notice that this seperation method is not ideal\nbecause it does not take into account the variance of each class\nmeaning in certain cases this will not work",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "arrow",
			"version": 283,
			"versionNonce": 1338246615,
			"isDeleted": false,
			"id": "tcHTmZKpZdJcvQQQ7di5O",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 300.2490785454278,
			"y": 925.5838197302679,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 340.5709115105443,
			"height": 784.2135193399467,
			"seed": 517033367,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PcacPwAT",
				"focus": 0.2526555749998355,
				"gap": 14.070439802548378
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
					261.29454260600403,
					-27.412029405800695
				],
				[
					128.48900812987551,
					-716.2300682219868
				],
				[
					340.5709115105443,
					-784.2135193399467
				]
			]
		},
		{
			"type": "text",
			"version": 412,
			"versionNonce": 255618570,
			"isDeleted": false,
			"id": "fQReoBte",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 307.4704235044949,
			"y": 887.9310362897764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 226.51968383789062,
			"height": 38.63337605341866,
			"seed": 809743705,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708721655343,
			"link": null,
			"locked": false,
			"fontSize": 10.302233614244976,
			"fontFamily": 1,
			"text": "What if we controlled the orientation of our\nprojection and moved it around to match\nthe variances?",
			"rawText": "What if we controlled the orientation of our\nprojection and moved it around to match\nthe variances?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What if we controlled the orientation of our\nprojection and moved it around to match\nthe variances?",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 1192440567,
			"isDeleted": false,
			"id": "gqVziAEF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 440.7106367329943,
			"y": 96.93784980525842,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 110.65625,
			"height": 20,
			"seed": 1658413399,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Fischer's idea!",
			"rawText": "Fischer's idea!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Fischer's idea!",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 79,
			"versionNonce": 1294392313,
			"isDeleted": false,
			"id": "GeURAulf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 670.0745246726012,
			"y": 101.47396926711926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 541.3994140625,
			"height": 75,
			"seed": 2114299415,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": " In addition to maximizing the separation\nbetween class means in projected space, how about we\nalso consider to reduce the within-class variance!",
			"rawText": " In addition to maximizing the separation\nbetween class means in projected space, how about we\nalso consider to reduce the within-class variance!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " In addition to maximizing the separation\nbetween class means in projected space, how about we\nalso consider to reduce the within-class variance!",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 102,
			"versionNonce": 574602263,
			"isDeleted": false,
			"id": "LMERT5nRbXh9yugWaeBGE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 707.0871387385153,
			"y": 196.21502751768986,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 474.2311972488973,
			"height": 77.39189677325754,
			"seed": 2009708153,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "l9xJbXjxQdnTLEjbOOs2Y",
					"type": "arrow"
				}
			],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "96068472038066230d3805c50ac8d78b106b0b2d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 166,
			"versionNonce": 1874523353,
			"isDeleted": false,
			"id": "ZLVLZl7Hdxus5jLz8bw8D",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1118.0920690008845,
			"y": 249.95317374405667,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 138.23870348353955,
			"height": 76.94418401442292,
			"seed": 311477753,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-138.23870348353955,
					76.94418401442292
				]
			]
		},
		{
			"type": "text",
			"version": 429,
			"versionNonce": 893264183,
			"isDeleted": false,
			"id": "l5r2fAGq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 787.6030682011406,
			"y": 334.61391260691545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 347.9847106933594,
			"height": 100,
			"seed": 651060793,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HxtKP726RRsHugatnne7C",
					"type": "arrow"
				}
			],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "a value indicating positive \"distances\" of\nprojected points from their mean, the larger\nthis value is the more space the projected\nclass takes, thus we want to make it\nminimal and concise",
			"rawText": "a value indicating positive \"distances\" of\nprojected points from their mean, the larger\nthis value is the more space the projected\nclass takes, thus we want to make it\nminimal and concise",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a value indicating positive \"distances\" of\nprojected points from their mean, the larger\nthis value is the more space the projected\nclass takes, thus we want to make it\nminimal and concise",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "line",
			"version": 178,
			"versionNonce": 1578693049,
			"isDeleted": false,
			"id": "s1WLbFDTHv2deZuQThbjD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 857.4420164795746,
			"y": 250.4994134893708,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 94.55005662789279,
			"height": 78.24832272653184,
			"seed": 238466455,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					94.55005662789279,
					78.24832272653184
				]
			]
		},
		{
			"type": "text",
			"version": 35,
			"versionNonce": 1634918999,
			"isDeleted": false,
			"id": "jJD2OHjp",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 868.2900295580109,
			"y": 518.3731348449277,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 178.71981811523438,
			"height": 25,
			"seed": 5857047,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HxtKP726RRsHugatnne7C",
					"type": "arrow"
				}
			],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Our new objective!",
			"rawText": "Our new objective!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Our new objective!",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 51,
			"versionNonce": 1298420377,
			"isDeleted": false,
			"id": "HxtKP726RRsHugatnne7C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 954.6385664233321,
			"y": 446.79337891444345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 1.204548876918352,
			"height": 64.44336491513661,
			"seed": 1359552313,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "l5r2fAGq",
				"focus": 0.03312596837351229,
				"gap": 12.179466307528003
			},
			"endBinding": {
				"elementId": "jJD2OHjp",
				"focus": -0.0511527472112475,
				"gap": 7.136391015347613
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
					-1.204548876918352,
					64.44336491513661
				]
			]
		},
		{
			"type": "image",
			"version": 91,
			"versionNonce": 1739751287,
			"isDeleted": false,
			"id": "yLl4gEB5fgdumJC_oXWkQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 845.6387922999494,
			"y": 549.0432370544845,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 219.2040971236837,
			"height": 69.77318741337412,
			"seed": 1589489655,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2d6f2adec9930ab0c82d585d0d668eeb12088eaa",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 135,
			"versionNonce": 38836089,
			"isDeleted": false,
			"id": "l9xJbXjxQdnTLEjbOOs2Y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1200.1210780660128,
			"y": 225.89193528335164,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 303.8621870264881,
			"height": 127.37236880836357,
			"seed": 1669467159,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "LMERT5nRbXh9yugWaeBGE",
				"focus": -0.3254597978406499,
				"gap": 18.80274207860043
			},
			"endBinding": {
				"elementId": "n9UwNRjX_SsiFZHjsWKIc",
				"focus": 0.6611573849766422,
				"gap": 8.099991657129635
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
					166.4998285076647,
					3.3299965701532983
				],
				[
					199.79979420919767,
					-124.04237223821028
				],
				[
					303.8621870264881,
					-123.20987309567195
				]
			]
		},
		{
			"type": "image",
			"version": 97,
			"versionNonce": 2051111063,
			"isDeleted": false,
			"id": "n9UwNRjX_SsiFZHjsWKIc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1512.0832567496307,
			"y": 72.2608543906343,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 326.7896634115302,
			"height": 192.75854059201853,
			"seed": 1549134809,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "l9xJbXjxQdnTLEjbOOs2Y",
					"type": "arrow"
				}
			],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9a71a636005183bf77b3059d91793bdd8d272353",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 24,
			"versionNonce": 1596014681,
			"isDeleted": false,
			"id": "2a5GXaDd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1229.101901468192,
			"y": 207.57945671989347,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 91.88819885253906,
			"height": 20,
			"seed": 1712145975,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "lets simplify",
			"rawText": "lets simplify",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "lets simplify",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 87,
			"versionNonce": 248794551,
			"isDeleted": false,
			"id": "rwkjlE5s7dWCvKLTDNj83",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1648.534951444372,
			"y": 125.2071738309395,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 124.12116359783431,
			"height": 55.118211631580635,
			"seed": 1660088441,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					124.12116359783431,
					-55.118211631580635
				]
			]
		},
		{
			"type": "line",
			"version": 44,
			"versionNonce": 833211705,
			"isDeleted": false,
			"id": "MiLV5_-ZZPI4kx7drPpqu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1717.9586531177367,
			"y": 127.31092236649602,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 53.855962510246854,
			"height": 58.48420928847105,
			"seed": 1551636089,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					53.855962510246854,
					-58.48420928847105
				]
			]
		},
		{
			"type": "text",
			"version": 66,
			"versionNonce": 1888452311,
			"isDeleted": false,
			"id": "m2v4Wc8Y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1644.4013023496154,
			"y": 37.691234751788556,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 285.12060546875,
			"height": 20,
			"seed": 1354272793,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Projections of original points onto w",
			"rawText": "Projections of original points onto w",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Projections of original points onto w",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 149,
			"versionNonce": 1095613977,
			"isDeleted": false,
			"id": "UXghCG4Q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1512.0297556946043,
			"y": 264.38252926396046,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 382.9288330078125,
			"height": 60,
			"seed": 2001815577,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The definition of the covariance matrix\nso realistically, Sj is just the covariance matrix\nin projected space (unnormalized)",
			"rawText": "The definition of the covariance matrix\nso realistically, Sj is just the covariance matrix\nin projected space (unnormalized)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The definition of the covariance matrix\nso realistically, Sj is just the covariance matrix\nin projected space (unnormalized)",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 49,
			"versionNonce": 302484471,
			"isDeleted": false,
			"id": "vAiM3Ch6cfIb-U9dHUtll",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1836.733558124996,
			"y": 199.47930631203403,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 131.7478282713962,
			"height": 3.072835644813921,
			"seed": 1136438071,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					131.7478282713962,
					-3.072835644813921
				]
			]
		},
		{
			"type": "text",
			"version": 92,
			"versionNonce": 486576889,
			"isDeleted": false,
			"id": "fadVd9eR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1949.4648391415085,
			"y": 166.06221867468278,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 271.568603515625,
			"height": 40,
			"seed": 25626393,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is just an empathy term for \nthe scatter matrix Sj",
			"rawText": "This is just an empathy term for \nthe scatter matrix Sj",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is just an empathy term for \nthe scatter matrix Sj",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 269,
			"versionNonce": 524350743,
			"isDeleted": false,
			"id": "BkmPCdUY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1903.605608662212,
			"y": 211.38654443568794,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 399.39288330078125,
			"height": 160,
			"seed": 197302521,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "we know from linear algebra whenever\nwe have \n\n\nit is called an empathy term as we\ntransform our basis into w to empathize\nwith the basis of what we are trying to calculate\nand then transform back after we are done!",
			"rawText": "we know from linear algebra whenever\nwe have \n\n\nit is called an empathy term as we\ntransform our basis into w to empathize\nwith the basis of what we are trying to calculate\nand then transform back after we are done!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "we know from linear algebra whenever\nwe have \n\n\nit is called an empathy term as we\ntransform our basis into w to empathize\nwith the basis of what we are trying to calculate\nand then transform back after we are done!",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "image",
			"version": 95,
			"versionNonce": 692440025,
			"isDeleted": false,
			"id": "rfrQrK5vDyAUgsdD61QYN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2049.9277953706983,
			"y": 255.33661525478868,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 100.67112383073233,
			"height": 30.404030687133925,
			"seed": 316380855,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a50dd23a8098a8378e948e195357f4ee692c9c2e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 104,
			"versionNonce": 1336949303,
			"isDeleted": false,
			"id": "XVMbb1JR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 770.5279970206279,
			"y": 611.830228628915,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 376.352783203125,
			"height": 20,
			"seed": 851761593,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "or written as an objective function to maximize",
			"rawText": "or written as an objective function to maximize",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "or written as an objective function to maximize",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 169,
			"versionNonce": 1848699065,
			"isDeleted": false,
			"id": "epAJ-avyoGlnY5zvINVW1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 847.9738682138847,
			"y": 634.6843794054687,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 213.28472431677835,
			"height": 63.61926326187166,
			"seed": 1270627159,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d49fbd8b375f21bc0abdd8a772457a23ac76de6b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 239,
			"versionNonce": 2017057623,
			"isDeleted": false,
			"id": "9161Uoi-ML5wIBvQ5kv_r",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 831.0712687917302,
			"y": 719.0906660520222,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 127.97461681828011,
			"height": 44.454340578981515,
			"seed": 818410999,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "13ae799ac94c664820c4ebb28ed488f83c4d9e32",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 9,
			"versionNonce": 627403161,
			"isDeleted": false,
			"id": "jai9yquq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 949.5908752973303,
			"y": 698.0605801121567,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 18.496047973632812,
			"height": 20,
			"seed": 610568247,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314482,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Or",
			"rawText": "Or",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Or",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 289,
			"versionNonce": 769898634,
			"isDeleted": false,
			"id": "dOal1sFT40NDd3fL1lVmS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 963.6599756238141,
			"y": 714.9643068587151,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 186.7082413458697,
			"height": 53.79068331050108,
			"seed": 4153,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708721194576,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5b001231a8f0a9d883b38cc5b7960e73d9819c81",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 31,
			"versionNonce": 135712377,
			"isDeleted": false,
			"id": "2n8TiQPBIu3rmhRncyn9z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 804.9456594769117,
			"y": 746.6371313170157,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 60.444268416035584,
			"height": 16.718627434222526,
			"seed": 1147459417,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703680314483,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-60.444268416035584,
					-16.718627434222526
				]
			]
		},
		{
			"type": "text",
			"version": 77,
			"versionNonce": 1147023767,
			"isDeleted": false,
			"id": "zXOl9Ceh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 638.6347697519902,
			"y": 708.0891088038935,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 142.28663635253906,
			"height": 17.826538054054787,
			"seed": 306944279,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703680314483,
			"link": null,
			"locked": false,
			"fontSize": 14.26123044324383,
			"fontFamily": 1,
			"text": "Rayleigh Co-efficient",
			"rawText": "Rayleigh Co-efficient",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Rayleigh Co-efficient",
			"lineHeight": 1.25,
			"baseline": 12
		},
		{
			"type": "arrow",
			"version": 274,
			"versionNonce": 1746669654,
			"isDeleted": false,
			"id": "IbYCbPXhu8gHEkU3uHWyj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1964.9196283127417,
			"y": 1163.8062613392792,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 383.8287431184773,
			"height": 175.83777498883126,
			"seed": 651087575,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708722763035,
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
					-14.067021999106487,
					158.75639113277327
				],
				[
					369.7617211193708,
					175.83777498883126
				]
			]
		},
		{
			"type": "text",
			"version": 249,
			"versionNonce": 242534870,
			"isDeleted": false,
			"id": "YNfChw3w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2054.45613455608,
			"y": 1299.4525449020919,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 210.78445434570312,
			"height": 20,
			"seed": 26541977,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722774050,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "constrained version of this",
			"rawText": "constrained version of this",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "constrained version of this",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 224,
			"versionNonce": 864580310,
			"isDeleted": false,
			"id": "hCvWDjni41Zbno5CFfRoQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1990.5877260114546,
			"y": 1357.224013863261,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 301.3441418658863,
			"height": 42.55885374871287,
			"seed": 1313704535,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "WmgJuSQhPIwclwydxr1_-",
					"type": "arrow"
				}
			],
			"updated": 1708722763035,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5b8a7455dedb8026378c1955bcbed3784c117d66",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 353,
			"versionNonce": 230692187,
			"isDeleted": false,
			"id": "k5nY7cOj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2351.827341351803,
			"y": 1321.8003079333698,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 415.328857421875,
			"height": 40,
			"seed": 1169053367,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708723048161,
			"link": "[[Lagrange]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can use the lagrange method to find the optimal\nsolution for this objective!",
			"rawText": "We can use the lagrange method to find the optimal\nsolution for this objective!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can use the lagrange method to find the optimal\nsolution for this objective!",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 557,
			"versionNonce": 1222963542,
			"isDeleted": false,
			"id": "WmgJuSQhPIwclwydxr1_-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2302.138090475113,
			"y": 1377.305258077013,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 95.02390147594383,
			"height": 1.6015264293697555,
			"seed": 1595841113,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708722835263,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hCvWDjni41Zbno5CFfRoQ",
				"focus": -0.21516868910374448,
				"gap": 10.206222597772353
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
					60.85800431605389,
					1.6015264293697555
				],
				[
					95.02390147594383,
					1.6015264293697555
				]
			]
		},
		{
			"type": "arrow",
			"version": 553,
			"versionNonce": 409583382,
			"isDeleted": false,
			"id": "fKe4yw71a4plMy1vVYKGj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2546.9012791856503,
			"y": 1394.5191330350087,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 0.27964855585105397,
			"height": 33.837475257982305,
			"seed": 805557273,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708722865120,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ReF0UBZV",
				"focus": 0.03357219324037336,
				"gap": 6.945465516329477
			},
			"endBinding": {
				"elementId": "thPLeRw0",
				"focus": -0.11158255994762206,
				"gap": 7.722853841463575
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
					0,
					15.93996768351235
				],
				[
					-0.27964855585105397,
					33.837475257982305
				]
			]
		},
		{
			"type": "text",
			"version": 309,
			"versionNonce": 1728201302,
			"isDeleted": false,
			"id": "07jNDomH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2377.92393607733,
			"y": 1462.0481974534425,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 327.2646484375,
			"height": 80,
			"seed": 819550967,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722983040,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Which is a generalized eignevalue issue\ndescribing that Sb's effect on w\nis the same as a scalar product of Sw's\neffect on w",
			"rawText": "Which is a generalized eignevalue issue\ndescribing that Sb's effect on w\nis the same as a scalar product of Sw's\neffect on w",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which is a generalized eignevalue issue\ndescribing that Sb's effect on w\nis the same as a scalar product of Sw's\neffect on w",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "image",
			"version": 543,
			"versionNonce": 988783062,
			"isDeleted": false,
			"id": "L30UWXqGgKh1Gyovjv3kk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2852.9152366118133,
			"y": 1463.0867258657029,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 123.07626983427511,
			"height": 26.19940397462292,
			"seed": 239983577,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "d7sK0xhus0r0_ITXfZBTG",
					"type": "arrow"
				}
			],
			"updated": 1708722763035,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "eadc58658c743b5207e32d5b66ae65ca1f6969c8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 499,
			"versionNonce": 593458698,
			"isDeleted": false,
			"id": "d7sK0xhus0r0_ITXfZBTG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2620.508172571013,
			"y": 1437.8259621018904,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 277.7304030854575,
			"height": 20.751382995624226,
			"seed": 498552121,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708722763160,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "L30UWXqGgKh1Gyovjv3kk",
				"focus": 0.46794348377184264,
				"gap": 6.145105745716023
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
					206.5102784129067,
					-1.6357249775278433
				],
				[
					277.7304030854575,
					19.115658018096383
				]
			]
		},
		{
			"type": "text",
			"version": 210,
			"versionNonce": 1618651542,
			"isDeleted": false,
			"id": "bETXzbBR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2688.0882608969996,
			"y": 1416.5615373940266,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 135.55230712890625,
			"height": 20,
			"seed": 1688139129,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722763035,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "if Sw is invertible",
			"rawText": "if Sw is invertible",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "if Sw is invertible",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 711,
			"versionNonce": 232589014,
			"isDeleted": false,
			"id": "ek9mUm01YOu_KTGdHCHo6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2748.006146107175,
			"y": 1495.832702846648,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 232.34111037089906,
			"height": 44.74717681217315,
			"seed": 1439018071,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722763035,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f3b5db89186ce84c59f45c12cc8ae432bb2d7898",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 366,
			"versionNonce": 830585878,
			"isDeleted": false,
			"id": "lzjULYyOyQVUsqBVtr8C3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2915.2950161077124,
			"y": 1534.5495893989646,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 121.87387954806078,
			"height": 25.15745220028778,
			"seed": 1298471769,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722763035,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c0f6e8ed8fec32f5794180179733fd6db99102b4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 338,
			"versionNonce": 22923606,
			"isDeleted": false,
			"id": "gglJ6gV938Ycx5DQc6sJt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2093.602191813865,
			"y": 1319.7648332776178,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 130.21354417817386,
			"height": 15.768046365325741,
			"seed": 1814601561,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722763035,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "96e69abc7c0cdac1b515229ea3c5f72ce1ca818e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 227,
			"versionNonce": 751185558,
			"isDeleted": false,
			"id": "ZGn3JwFGZLE1NljYpeRXe",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2958.617518721484,
			"y": 1502.5269882605219,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 78.90031800464567,
			"height": 33.18822900195414,
			"seed": 164716119,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708722763035,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					39.76325550234128,
					-26.92629900158545
				],
				[
					78.90031800464567,
					-33.18822900195414
				]
			]
		},
		{
			"type": "text",
			"version": 337,
			"versionNonce": 1894877206,
			"isDeleted": false,
			"id": "OxLKRkvi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3039.359905780322,
			"y": 1464.3292152582728,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 178.53802490234375,
			"height": 29.312124037384546,
			"seed": 1775064825,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708723121127,
			"link": null,
			"locked": false,
			"fontSize": 7.816566409969212,
			"fontFamily": 1,
			"text": "The optimum is defined up to a scaling factor\ni.e we dont care about scalars multiplied by w\nas it brings us the same solution",
			"rawText": "The optimum is defined up to a scaling factor\ni.e we dont care about scalars multiplied by w\nas it brings us the same solution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The optimum is defined up to a scaling factor\ni.e we dont care about scalars multiplied by w\nas it brings us the same solution",
			"lineHeight": 1.25,
			"baseline": 26
		},
		{
			"type": "image",
			"version": 335,
			"versionNonce": 711983382,
			"isDeleted": false,
			"id": "ANgT4jW7GT6dLPPgnd9YB",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2882.026637008261,
			"y": 1186.8115707440863,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 200.13452864152302,
			"height": 162.34979398098653,
			"seed": 1414932793,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "6jTt0AORngmHN4NM5sc09",
					"type": "arrow"
				}
			],
			"updated": 1708722763035,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "27b960c0eaade277b9467a11017a9067588dca90",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 303,
			"versionNonce": 413610902,
			"isDeleted": false,
			"id": "BnttKaJCWaPA7Zs-ZgQfL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3166.4198570389453,
			"y": 1192.8557260594741,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 184.98870875658554,
			"height": 155.88488173238133,
			"seed": 1319978073,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "6jTt0AORngmHN4NM5sc09",
					"type": "arrow"
				}
			],
			"updated": 1708722763035,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "065b2c53a310c2f0086c77e60faa484c48d58bfe",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 565,
			"versionNonce": 818740106,
			"isDeleted": false,
			"id": "6jTt0AORngmHN4NM5sc09",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3091.633118358078,
			"y": 1276.4654658689335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 71.58765603739675,
			"height": 3.3006112027986774,
			"seed": 1817452631,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708722763160,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ANgT4jW7GT6dLPPgnd9YB",
				"focus": 0.12057143094666763,
				"gap": 9.471952708293657
			},
			"endBinding": {
				"elementId": "BnttKaJCWaPA7Zs-ZgQfL",
				"focus": 0.09916103416909235,
				"gap": 3.199082643470774
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
					48.92917775033038,
					-0.6567674865817708
				],
				[
					71.58765603739675,
					-3.3006112027986774
				]
			]
		},
		{
			"type": "text",
			"version": 397,
			"versionNonce": 278827862,
			"isDeleted": false,
			"id": "5U1vbTUK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3175.9599252980197,
			"y": 1348.806982458336,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 167.8660888671875,
			"height": 14.18178689479811,
			"seed": 127638359,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722763035,
			"link": null,
			"locked": false,
			"fontSize": 5.672714757919244,
			"fontFamily": 1,
			"text": "Fisher Discriminant requires inversion of a covariance matrix\n(only tractable for low-dimensional data)",
			"rawText": "Fisher Discriminant requires inversion of a covariance matrix\n(only tractable for low-dimensional data)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Fisher Discriminant requires inversion of a covariance matrix\n(only tractable for low-dimensional data)",
			"lineHeight": 1.25,
			"baseline": 12
		},
		{
			"type": "text",
			"version": 188,
			"versionNonce": 625629334,
			"isDeleted": false,
			"id": "Aewa8B2u",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1379.4557301485845,
			"y": 463.05199565874875,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 53.45994567871094,
			"height": 25,
			"seed": 1667884313,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708721341012,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PROS",
			"rawText": "PROS",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PROS",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 202,
			"versionNonce": 450811350,
			"isDeleted": false,
			"id": "lFN4fNIA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1763.8926703311652,
			"y": 457.3406453189915,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 52.43995666503906,
			"height": 25,
			"seed": 1601933561,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708721341012,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CONS",
			"rawText": "CONS",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CONS",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 192,
			"versionNonce": 2071046934,
			"isDeleted": false,
			"id": "lpVrSrdL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1571.49362562445,
			"y": 559.6390192444607,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 27.97998046875,
			"height": 25,
			"seed": 1430801337,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708721341012,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "V.S",
			"rawText": "V.S",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V.S",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 266,
			"versionNonce": 91740246,
			"isDeleted": false,
			"id": "232YRj7v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1265.9575282064475,
			"y": 499.68039856036523,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 298.2086181640625,
			"height": 160,
			"seed": 607906263,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708721341012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Accurate when the means/covariances\ndescribe well the data\n\nClose to optimal when the data is\nGaussian of fixed covariance.\n\nThe Fisher discriminant is given in\nclosed form and is fast to compute.",
			"rawText": "Accurate when the means/covariances\ndescribe well the data\n\nClose to optimal when the data is\nGaussian of fixed covariance.\n\nThe Fisher discriminant is given in\nclosed form and is fast to compute.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Accurate when the means/covariances\ndescribe well the data\n\nClose to optimal when the data is\nGaussian of fixed covariance.\n\nThe Fisher discriminant is given in\nclosed form and is fast to compute.",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "text",
			"version": 234,
			"versionNonce": 1623612822,
			"isDeleted": false,
			"id": "ofuZdUiS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1605.543852192935,
			"y": 498.33282710993456,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 382.7688293457031,
			"height": 120,
			"seed": 1655226265,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708721341012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Although applicable to non-Gaussian\ndistributions, the resulting decision boundary can\nbecome in that case strongly suboptimal\n\nIn particular, like principal component analysis,\nFisher Discriminant is not robust to outliers.",
			"rawText": "Although applicable to non-Gaussian\ndistributions, the resulting decision boundary can\nbecome in that case strongly suboptimal\n\nIn particular, like principal component analysis,\nFisher Discriminant is not robust to outliers.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Although applicable to non-Gaussian\ndistributions, the resulting decision boundary can\nbecome in that case strongly suboptimal\n\nIn particular, like principal component analysis,\nFisher Discriminant is not robust to outliers.",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"id": "LJoY77bI",
			"type": "text",
			"x": 784.4118384483497,
			"y": 774.5171741363735,
			"width": 418.0648193359375,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 541751062,
			"version": 229,
			"versionNonce": 1633356118,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708721412997,
			"link": null,
			"locked": false,
			"text": "Lets take a second to understand this objective\nas it represents two objective functions written as\nRayleigh Quotients\nwe would like to analyze spectrum of these matrices",
			"rawText": "Lets take a second to understand this objective\nas it represents two objective functions written as\nRayleigh Quotients\nwe would like to analyze spectrum of these matrices",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "Lets take a second to understand this objective\nas it represents two objective functions written as\nRayleigh Quotients\nwe would like to analyze spectrum of these matrices",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 257,
			"versionNonce": 1297489430,
			"isDeleted": false,
			"id": "rfvuOObf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 894.2156325696382,
			"y": 854.5171741638256,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 90.76028541634292,
			"height": 55.051320662371936,
			"seed": 85079,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708721420657,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d8dfee08b57bcf1220b4a997ea3145849bd57517",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 243,
			"versionNonce": 676719446,
			"isDeleted": false,
			"id": "mOeGY92-FBDnhnRMv6pc7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1001.9125783584367,
			"y": 855.4300863414318,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 90.76028541634292,
			"height": 55.051320662371936,
			"seed": 1633359510,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708721420657,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "65906daa2be3370807b0bc898449229ca969b5c3",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "H5zBz3WH",
			"type": "text",
			"x": 411.7951855920794,
			"y": 995.9653319063314,
			"width": 651.2332763671875,
			"height": 160,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 759664086,
			"version": 510,
			"versionNonce": 170488790,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "xEaNjEV1HyXyH4XP-52yV",
					"type": "arrow"
				},
				{
					"id": "uT5pKjesdx5tVQERJI_7N",
					"type": "arrow"
				}
			],
			"updated": 1708722448487,
			"link": null,
			"locked": false,
			"text": "Maximizing the range of the Rayleigh Quotient on the left\ni.e maximizing the spectrum of the Between classes matrix\nresults in maximizing the eigenvalue of this matrix for the eigenvector w\n\nthe eigenvalues of this matrix represent the magnitude of the spread in\nthe direction of the principal components while The eigenvectors show the direction\nsince our eigenvector is w, we are maximizing the the spread of points\nalong w!",
			"rawText": "Maximizing the range of the Rayleigh Quotient on the left\ni.e maximizing the spectrum of the Between classes matrix\nresults in maximizing the eigenvalue of this matrix for the eigenvector w\n\nthe eigenvalues of this matrix represent the magnitude of the spread in\nthe direction of the principal components while The eigenvectors show the direction\nsince our eigenvector is w, we are maximizing the the spread of points\nalong w!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 154,
			"containerId": null,
			"originalText": "Maximizing the range of the Rayleigh Quotient on the left\ni.e maximizing the spectrum of the Between classes matrix\nresults in maximizing the eigenvalue of this matrix for the eigenvector w\n\nthe eigenvalues of this matrix represent the magnitude of the spread in\nthe direction of the principal components while The eigenvectors show the direction\nsince our eigenvector is w, we are maximizing the the spread of points\nalong w!",
			"lineHeight": 1.25
		},
		{
			"id": "nXU30nCt6ynDnLpFtaVW0",
			"type": "line",
			"x": 888.2192795054295,
			"y": 922.8255861331388,
			"width": 100.94931941306868,
			"height": 62.25208030472572,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 1213349706,
			"version": 28,
			"versionNonce": 1139897046,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708721662292,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-100.94931941306868,
					62.25208030472572
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "xEaNjEV1HyXyH4XP-52yV",
			"type": "arrow",
			"x": 383.5689362092461,
			"y": 1103.7756338809072,
			"width": 117.14875952550506,
			"height": 57.97995121839244,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
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
			"seed": 393235082,
			"version": 128,
			"versionNonce": 599296278,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708722448487,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-80.98046860809785,
					9.564129139820352
				],
				[
					-117.14875952550506,
					57.97995121839244
				]
			],
			"lastCommittedPoint": [
				-148.06711245226984,
				95.30137783291548
			],
			"startBinding": {
				"elementId": "H5zBz3WH",
				"focus": 0.11801791908896345,
				"gap": 28.226249382833316
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "vvg0HFOkHwDXa8lpLflA-",
			"type": "arrow",
			"x": 139.48148535174033,
			"y": 1275.0509059529618,
			"width": 135.39459110624506,
			"height": 0.007038509238327606,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 226473738,
			"version": 231,
			"versionNonce": 190698058,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086982,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					135.39459110624506,
					0.007038509238327606
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "rNCrcqPD",
				"focus": -1.2394992684593915,
				"gap": 7.1970516783108
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "hLNywD9gyRZ92hNpd9xmB",
			"type": "arrow",
			"x": 141.26363298319222,
			"y": 1273.756650208465,
			"width": 1.5837383504803029,
			"height": 112.80790344904335,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
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
			"seed": 1416922198,
			"version": 217,
			"versionNonce": 1765865738,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086982,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.5837383504803029,
					-112.80790344904335
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "rNCrcqPD",
				"focus": -0.4214467622892028,
				"gap": 8.491307422807495
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "nUI2KfP4_VfK0IrIkh_n-",
			"type": "freedraw",
			"x": 217.18161177366846,
			"y": 1217.2458792589964,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 911936086,
			"version": 47,
			"versionNonce": 1330007126,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "1tHXqBY3RmWKesw7tutPK",
			"type": "freedraw",
			"x": 218.51557342194113,
			"y": 1201.2383394797243,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 772334102,
			"version": 47,
			"versionNonce": 1353077142,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "ODKYMOu4oPuM99Y5xOTgA",
			"type": "freedraw",
			"x": 237.72462115706747,
			"y": 1206.3073937431604,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 876663254,
			"version": 47,
			"versionNonce": 1246998230,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "EgdznVWHRf8Y3zCrRfvrk",
			"type": "freedraw",
			"x": 199.30652568681478,
			"y": 1210.576071017633,
			"width": 0,
			"height": 0.800376988963535,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 186243478,
			"version": 48,
			"versionNonce": 2028168214,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.800376988963535
				],
				[
					0,
					0.800376988963535
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0,
				0.800376988963535
			]
		},
		{
			"id": "lJJ5gujOAookPZ656tGqn",
			"type": "freedraw",
			"x": 191.56954812683333,
			"y": 1233.2534190382682,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 911040150,
			"version": 47,
			"versionNonce": 1045066070,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "dw0DBntlWb8isLkvSFEFb",
			"type": "freedraw",
			"x": 213.446519158505,
			"y": 1224.4492721596687,
			"width": 0.26679232965452115,
			"height": 0.26679232965466326,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 214998614,
			"version": 48,
			"versionNonce": 1977472662,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.26679232965452115,
					0.26679232965466326
				],
				[
					-0.26679232965452115,
					0.26679232965466326
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-0.26679232965452115,
				0.26679232965466326
			]
		},
		{
			"id": "1GF3mcwE3Y2a5cr0G56tm",
			"type": "freedraw",
			"x": 185.70011687443363,
			"y": 1224.9828568189778,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 589022038,
			"version": 47,
			"versionNonce": 1213371350,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "PNQSpXXhKLrYJ56MSMXNQ",
			"type": "freedraw",
			"x": 170.49295408412524,
			"y": 1245.2590738727222,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1635269398,
			"version": 47,
			"versionNonce": 2143136022,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "MJZbvzzgHu_nkYgCHpK4d",
			"type": "freedraw",
			"x": 207.04350324679623,
			"y": 1242.3243582465225,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 560122582,
			"version": 47,
			"versionNonce": 1536431702,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "8qjnMg_V9QvoNVycTyk69",
			"type": "freedraw",
			"x": 186.76728619305175,
			"y": 1250.594920465813,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1400009366,
			"version": 47,
			"versionNonce": 1688918934,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "4i8AlXG4Zcbhxw6yydgPP",
			"type": "freedraw",
			"x": 169.42578476550713,
			"y": 1259.6658596740672,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2073965142,
			"version": 47,
			"versionNonce": 1094121686,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "WrrMDYz5so4W03gtglQxU",
			"type": "freedraw",
			"x": 232.65556689363135,
			"y": 1224.4492721596687,
			"width": 0,
			"height": 0.2667923296544359,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1832716822,
			"version": 48,
			"versionNonce": 147680790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.2667923296544359
				],
				[
					0,
					-0.2667923296544359
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0,
				-0.2667923296544359
			]
		},
		{
			"id": "yM8-Ac66Y-jpPmS3xml7w",
			"type": "freedraw",
			"x": 232.9223592232859,
			"y": 1195.6357005569791,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 521424662,
			"version": 47,
			"versionNonce": 409156438,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "O71OnGbZpitmP0WzM5Pve",
			"type": "freedraw",
			"x": 220.91670438883193,
			"y": 1230.3187034120685,
			"width": 0.26679232965452115,
			"height": 0.26679232965466326,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1342660310,
			"version": 48,
			"versionNonce": 1716347030,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.26679232965452115,
					-0.26679232965466326
				],
				[
					0.26679232965452115,
					-0.26679232965466326
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.26679232965452115,
				-0.26679232965466326
			]
		},
		{
			"id": "gjcjjHj5zKec7J_y7B3fP",
			"type": "freedraw",
			"x": 249.46348366186692,
			"y": 1211.9100326659056,
			"width": 0,
			"height": 0.2667923296544359,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1051608022,
			"version": 48,
			"versionNonce": 1447091670,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.2667923296544359
				],
				[
					0,
					-0.2667923296544359
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0,
				-0.2667923296544359
			]
		},
		{
			"id": "EH_FErsEvSXVSUGJUZTqx",
			"type": "freedraw",
			"x": 247.59593735428518,
			"y": 1192.1674002714703,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 339388630,
			"version": 47,
			"versionNonce": 223523606,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "iaSu9ZWdfq4a51CVpP0NU",
			"type": "freedraw",
			"x": 263.06989247424804,
			"y": 1191.3670232825068,
			"width": 0.5335846593090423,
			"height": 0.5335846593088718,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2041516182,
			"version": 49,
			"versionNonce": 1173872726,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.26679232965449273,
					0.2667923296544359
				],
				[
					-0.5335846593090423,
					0.5335846593088718
				],
				[
					-0.5335846593090423,
					0.5335846593088718
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-0.5335846593090423,
				0.5335846593088718
			]
		},
		{
			"id": "EVTaEiccQFGrQUANQDFQ0",
			"type": "freedraw",
			"x": 256.6668765625393,
			"y": 1201.505131809379,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1493430998,
			"version": 47,
			"versionNonce": 604333462,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086751,
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
			"id": "HStEt3zOCue2J314D42Hx",
			"type": "arrow",
			"x": 212.03867830943867,
			"y": 1222.2360321909264,
			"width": 52.93569403057083,
			"height": 34.5662181169771,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 717281238,
			"version": 209,
			"versionNonce": 1435584458,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086982,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					38.12160055186632,
					-23.505028319544408
				],
				[
					52.93569403057083,
					-34.5662181169771
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "rpfhvGAJ",
				"focus": 1.255997123927874,
				"gap": 9.31187997009053
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "image",
			"version": 168,
			"versionNonce": 1720547350,
			"isDeleted": false,
			"id": "rpfhvGAJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 274.2862523101,
			"y": 1185.3595824502406,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 32.3367216265627,
			"height": 12.126270609961013,
			"seed": 80337,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HStEt3zOCue2J314D42Hx",
					"type": "arrow"
				}
			],
			"updated": 1708722086751,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fc40124908b395c6690f3742665115736b2b02ef",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "wu2EYz2VWFZyOiIeZxsx4",
			"type": "arrow",
			"x": 211.4461145702905,
			"y": 1221.248425959013,
			"width": 11.91356495877011,
			"height": 12.048796029346477,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
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
			"seed": 284842966,
			"version": 207,
			"versionNonce": 1483325066,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722086982,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-11.91356495877011,
					-12.048796029346477
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "0gqph6tZ",
				"focus": 0.5026656274230451,
				"gap": 12.003679945556769
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "image",
			"version": 167,
			"versionNonce": 969222102,
			"isDeleted": false,
			"id": "0gqph6tZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 177.86652888147802,
			"y": 1186.4179666255407,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 28.741288956184555,
			"height": 10.777983358569209,
			"seed": 8345,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "wu2EYz2VWFZyOiIeZxsx4",
					"type": "arrow"
				}
			],
			"updated": 1708722086751,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dbe61c7bbe5bf8e511bb9f296840fdd3d4bf0b7a",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "rNCrcqPD",
			"type": "text",
			"x": 60.495566495118226,
			"y": 1282.2479576312726,
			"width": 277.95257568359375,
			"height": 60,
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
			"seed": 466901578,
			"version": 170,
			"versionNonce": 410102358,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "vvg0HFOkHwDXa8lpLflA-",
					"type": "arrow"
				},
				{
					"id": "hLNywD9gyRZ92hNpd9xmB",
					"type": "arrow"
				}
			],
			"updated": 1708722086751,
			"link": null,
			"locked": false,
			"text": "V and lambda are eigenvalues\nand eigenvectors of the covariance\nmatrix describing this distribution",
			"rawText": "V and lambda are eigenvalues\nand eigenvectors of the covariance\nmatrix describing this distribution",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "V and lambda are eigenvalues\nand eigenvectors of the covariance\nmatrix describing this distribution",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 460,
			"versionNonce": 727028630,
			"isDeleted": false,
			"id": "xIZGgTChu5-Rn--jyqfvK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 459.78046838611044,
			"y": 1267.412400241819,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 131.6853435996191,
			"height": 0.8865712258334497,
			"seed": 1942353750,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708722197190,
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
					131.6853435996191,
					-0.8865712258334497
				]
			]
		},
		{
			"type": "arrow",
			"version": 550,
			"versionNonce": 2100491862,
			"isDeleted": false,
			"id": "uT5pKjesdx5tVQERJI_7N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 460.6296372722463,
			"y": 1268.5671826399703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 10.217008459409158,
			"height": 82.72078110217717,
			"seed": 1039703190,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708722448487,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "H5zBz3WH",
				"focus": 0.8958956098625365,
				"gap": 29.88106963146174
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
					-10.217008459409158,
					-82.72078110217717
				]
			]
		},
		{
			"type": "text",
			"version": 530,
			"versionNonce": 57599306,
			"isDeleted": false,
			"id": "bH9MbEnP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 423.009056365212,
			"y": 1295.162475826784,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 201.2964324951172,
			"height": 100,
			"seed": 505435478,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722235020,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "our eigenvalue describes\nthe variance/spread\nin direction of w, which is\nthe distance between the\ntwo means!",
			"rawText": "our eigenvalue describes\nthe variance/spread\nin direction of w, which is\nthe distance between the\ntwo means!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "our eigenvalue describes\nthe variance/spread\nin direction of w, which is\nthe distance between the\ntwo means!",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"id": "ohN4ffoAhCb_8zsn3G2FT",
			"type": "arrow",
			"x": 343.06755799494397,
			"y": 1224.8227894701638,
			"width": 88.0857149874945,
			"height": 0.7900064124439723,
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
			"roundness": {
				"type": 2
			},
			"seed": 347019350,
			"version": 48,
			"versionNonce": 153443978,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722122911,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					88.0857149874945,
					0.7900064124439723
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "SPjcecL5D_9fpoK4WD2VG",
			"type": "line",
			"x": 471.8386032232991,
			"y": 1189.2725009101885,
			"width": 68.33555467639707,
			"height": 73.0755931510605,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
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
			"seed": 1462030730,
			"version": 61,
			"versionNonce": 689150422,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722141997,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					68.33555467639707,
					73.0755931510605
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "fzFMeSLF",
			"type": "text",
			"x": 490.66678631927226,
			"y": 1235.8828792443785,
			"width": 9.743994140625,
			"height": 20,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1852698390,
			"version": 2,
			"versionNonce": 1493924874,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722144147,
			"link": null,
			"locked": false,
			"text": "w",
			"rawText": "w",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "w",
			"lineHeight": 1.25
		},
		{
			"id": "jxPH6dkv",
			"type": "text",
			"x": 318.29311373060983,
			"y": 1180.6889119598109,
			"width": 123.20025634765625,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 61833610,
			"version": 35,
			"versionNonce": 1773061258,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722153520,
			"link": null,
			"locked": false,
			"text": "and in our case",
			"rawText": "and in our case",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "and in our case",
			"lineHeight": 1.25
		},
		{
			"id": "bEkmAkXLSmj9ymTPMreTa",
			"type": "arrow",
			"x": 500.3919974971446,
			"y": 1219.4972338744367,
			"width": 28.311771494534128,
			"height": 30.69759493508468,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
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
			"seed": 1635428874,
			"version": 49,
			"versionNonce": 49105494,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722167804,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-28.311771494534128,
					-30.69759493508468
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "image",
			"version": 34,
			"versionNonce": 1981198602,
			"isDeleted": false,
			"id": "XQkzMlTM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 497.22386655256776,
			"y": 1182.9311942401034,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 36,
			"height": 15,
			"seed": 90924,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722185730,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "71db7c36b67ca672b6dc20dd34cab376312feb95",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "KuG4t-vg8YMwMUEOVHomQ",
			"type": "arrow",
			"x": 1114.336873991283,
			"y": 894.7436059840745,
			"width": 103.66341660017133,
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
			"roundness": {
				"type": 2
			},
			"seed": 800410634,
			"version": 60,
			"versionNonce": 19802646,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722271874,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					103.66341660017133,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "5mtxBjre",
			"type": "text",
			"x": 1234.8039477608404,
			"y": 866.2993758193933,
			"width": 234.40054321289062,
			"height": 40,
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
			"seed": 1700385034,
			"version": 123,
			"versionNonce": 1413624970,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "xAK18gFRUrbGYEphILCF7",
					"type": "arrow"
				}
			],
			"updated": 1708722466108,
			"link": null,
			"locked": false,
			"text": "Minimizing this Quotient means\nmaximizing its inverse",
			"rawText": "Minimizing this Quotient means\nmaximizing its inverse",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Minimizing this Quotient means\nmaximizing its inverse",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 325,
			"versionNonce": 1911012106,
			"isDeleted": false,
			"id": "UqYEJZUQXoeCijAXNHsct",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1314.623152844123,
			"y": 907.5035517135045,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 87.29044737651324,
			"height": 57.23963762394311,
			"seed": 315168598,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722322155,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9ba413074885b507fef36460f8252594f14203ec",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "e-mVtXIDTT6hRN8hf8Wp-",
			"type": "line",
			"x": 1066.6341466454403,
			"y": 931.578152872037,
			"width": 65.18147190768786,
			"height": 61.53762037376771,
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
			"roundness": {
				"type": 2
			},
			"seed": 1405616266,
			"version": 180,
			"versionNonce": 118271702,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722363295,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					65.18147190768786,
					61.53762037376771
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "yiZwcKhe",
			"type": "text",
			"x": 1078.7080613191504,
			"y": 997.874343849867,
			"width": 307.0726318359375,
			"height": 180,
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
			"seed": 18095062,
			"version": 366,
			"versionNonce": 1990040086,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "4tt_lHfqBNKzAeuaHPzEp",
					"type": "arrow"
				}
			],
			"updated": 1708723572097,
			"link": null,
			"locked": false,
			"text": "Minimizing this Quotient means\nMinimizing its spectrum and thus\nminimizing its eigenvectors blah\nblah blah which describes\nthe magnitude and its PCA\nwhich for this matrix (Which describes\nhow far the points are from the mean)\nis like minimizing the distance of points\nfrom the mean in protective space",
			"rawText": "Minimizing this Quotient means\nMinimizing its spectrum and thus\nminimizing its eigenvectors blah\nblah blah which describes\nthe magnitude and its PCA\nwhich for this matrix (Which describes\nhow far the points are from the mean)\nis like minimizing the distance of points\nfrom the mean in protective space",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 174,
			"containerId": null,
			"originalText": "Minimizing this Quotient means\nMinimizing its spectrum and thus\nminimizing its eigenvectors blah\nblah blah which describes\nthe magnitude and its PCA\nwhich for this matrix (Which describes\nhow far the points are from the mean)\nis like minimizing the distance of points\nfrom the mean in protective space",
			"lineHeight": 1.25
		},
		{
			"id": "xAK18gFRUrbGYEphILCF7",
			"type": "arrow",
			"x": 1473.9371137677458,
			"y": 912.4805626148255,
			"width": 176.4731715299738,
			"height": 1.7916058023346295,
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
			"roundness": {
				"type": 2
			},
			"seed": 1889392854,
			"version": 32,
			"versionNonce": 989345098,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722491340,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					176.4731715299738,
					1.7916058023346295
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "5mtxBjre",
				"focus": 1.1771338085629142,
				"gap": 7.784907752212348
			},
			"endBinding": {
				"elementId": "6neHzVxb",
				"focus": 0.13450695505070734,
				"gap": 6.962025593820385
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "6neHzVxb",
			"type": "text",
			"x": 1657.3723108915403,
			"y": 900.187223314884,
			"width": 547.713134765625,
			"height": 40,
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
			"seed": 1407128394,
			"version": 147,
			"versionNonce": 1643388054,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "xAK18gFRUrbGYEphILCF7",
					"type": "arrow"
				}
			],
			"updated": 1708722490781,
			"link": null,
			"locked": false,
			"text": "Combining both objectives we multiply them with each other and Arrive\nat our objective function to maximize!",
			"rawText": "Combining both objectives we multiply them with each other and Arrive\nat our objective function to maximize!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Combining both objectives we multiply them with each other and Arrive\nat our objective function to maximize!",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 293,
			"versionNonce": 437171082,
			"isDeleted": false,
			"id": "mAiFv3H5aH8fZ0iVh9JCl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1864.6006428985959,
			"y": 941.7999238812358,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 161.42636143618626,
			"height": 56.07442028835944,
			"seed": 1482047562,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722508098,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "13ae799ac94c664820c4ebb28ed488f83c4d9e32",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "UpO4O0QX",
			"type": "text",
			"x": 1657.988022965611,
			"y": 1000.7630172012393,
			"width": 636.0972290039062,
			"height": 120,
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
			"seed": 535484682,
			"version": 555,
			"versionNonce": 993470806,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "f9NK_t-UDsung28aJ1ZHG",
					"type": "arrow"
				}
			],
			"updated": 1708722666303,
			"link": null,
			"locked": false,
			"text": "Now we cant just take any vector W here otherwise we would have infinite\nsolutions, since we know W is in the direction of the eigenvector of the matrices\nwe can suffice by taking the Unit eigenvector instead...\n(This is because any scaled version of that eigenvector \nis gonna have a solution that maximizes this function but it\nall stems from the direction w)",
			"rawText": "Now we cant just take any vector W here otherwise we would have infinite\nsolutions, since we know W is in the direction of the eigenvector of the matrices\nwe can suffice by taking the Unit eigenvector instead...\n(This is because any scaled version of that eigenvector \nis gonna have a solution that maximizes this function but it\nall stems from the direction w)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "Now we cant just take any vector W here otherwise we would have infinite\nsolutions, since we know W is in the direction of the eigenvector of the matrices\nwe can suffice by taking the Unit eigenvector instead...\n(This is because any scaled version of that eigenvector \nis gonna have a solution that maximizes this function but it\nall stems from the direction w)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 76,
			"versionNonce": 1071852170,
			"isDeleted": false,
			"id": "9y965FkL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2200.85065028197,
			"y": 1067.3042923096175,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 23,
			"height": 8,
			"seed": 52179,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708722655566,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "87cfb03e193ad5c207e70119bfb05aaf86c34974",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "f9NK_t-UDsung28aJ1ZHG",
			"type": "arrow",
			"x": 2302.61377826025,
			"y": 1058.251831791962,
			"width": 134.63336420195947,
			"height": 0,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1447923722,
			"version": 53,
			"versionNonce": 611552918,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722667139,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					134.63336420195947,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "UpO4O0QX",
				"focus": -0.04185309015462051,
				"gap": 8.52852629073277
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "IZd2aFwS",
			"type": "text",
			"x": 2308.6983913555305,
			"y": 1020.7765654677053,
			"width": 116.91224670410156,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 191974358,
			"version": 57,
			"versionNonce": 493179990,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722675469,
			"link": null,
			"locked": false,
			"text": "In other words",
			"rawText": "In other words",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "In other words",
			"lineHeight": 1.25
		},
		{
			"id": "UBNaxOQu",
			"type": "text",
			"x": 2432.153089965003,
			"y": 1002.7329187189894,
			"width": 383.55279541015625,
			"height": 120,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1381021398,
			"version": 327,
			"versionNonce": 1684508886,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708722754908,
			"link": null,
			"locked": false,
			"text": "If we have an objective function J that we\nwant to maximize, multiplying the function by\nany constant scalar that does not depend\non the parameters of J is useless because\nit doesn't not affect the solution.\n(take our constant values from a max function)",
			"rawText": "If we have an objective function J that we\nwant to maximize, multiplying the function by\nany constant scalar that does not depend\non the parameters of J is useless because\nit doesn't not affect the solution.\n(take our constant values from a max function)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "If we have an objective function J that we\nwant to maximize, multiplying the function by\nany constant scalar that does not depend\non the parameters of J is useless because\nit doesn't not affect the solution.\n(take our constant values from a max function)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 38,
			"versionNonce": 259400970,
			"isDeleted": false,
			"id": "ReF0UBZV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2416.4335252731007,
			"y": 1368.5736675186793,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 270,
			"height": 19,
			"seed": 17356,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "fKe4yw71a4plMy1vVYKGj",
					"type": "arrow"
				}
			],
			"updated": 1708722837768,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e171ab9c2159f4b1ca128d7a90ad08fbb3777836",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 70,
			"versionNonce": 1917676630,
			"isDeleted": false,
			"id": "thPLeRw0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2501.982918378402,
			"y": 1436.0794621344546,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 100,
			"height": 14,
			"seed": 44817,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "fKe4yw71a4plMy1vVYKGj",
					"type": "arrow"
				}
			],
			"updated": 1708722865120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a5a8acab81d97208afd0ef8274c6b80af33994d7",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "PpH9tqTp99ErM1SBvY2bl",
			"type": "arrow",
			"x": 905.063579062114,
			"y": 719.7978671512459,
			"width": 201.63780779879244,
			"height": 107.45967002450618,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1994511446,
			"version": 52,
			"versionNonce": 1376594698,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708723369034,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-104.23990463051348,
					-44.6742448416486
				],
				[
					-201.63780779879244,
					-107.45967002450618
				]
			],
			"lastCommittedPoint": [
				-201.63780779879244,
				-107.45967002450618
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "XidIPDcW",
				"focus": 0.19169729990149614,
				"gap": 13.80753663692326
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "XidIPDcW",
			"type": "text",
			"x": 589.0701305470623,
			"y": 578.5306604898165,
			"width": 198.92845153808594,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1081418634,
			"version": 18,
			"versionNonce": 2047293898,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "PpH9tqTp99ErM1SBvY2bl",
					"type": "arrow"
				}
			],
			"updated": 1708723369034,
			"link": null,
			"locked": false,
			"text": "Quadratic representation",
			"rawText": "Quadratic representation",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Quadratic representation",
			"lineHeight": 1.25
		},
		{
			"id": "4tt_lHfqBNKzAeuaHPzEp",
			"type": "arrow",
			"x": 1211.446204933861,
			"y": 1188.7811892805908,
			"width": 1.0006232954490315,
			"height": 52.23617058612081,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 854868426,
			"version": 586,
			"versionNonce": 18945686,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708723702995,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.0006232954490315,
					52.23617058612081
				]
			],
			"lastCommittedPoint": [
				-3.8221588233745933,
				80.90236176143094
			],
			"startBinding": {
				"elementId": "yiZwcKhe",
				"focus": 0.14194407047375474,
				"gap": 10.906845430723706
			},
			"endBinding": {
				"elementId": "na3jWo0G",
				"focus": -0.11169654164952934,
				"gap": 3.8221588233745933
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "na3jWo0G",
			"type": "text",
			"x": 994.9761875095953,
			"y": 1244.8395186900862,
			"width": 492.67303466796875,
			"height": 120,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 24608394,
			"version": 427,
			"versionNonce": 1073128470,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "4tt_lHfqBNKzAeuaHPzEp",
					"type": "arrow"
				}
			],
			"updated": 1708723702995,
			"link": null,
			"locked": false,
			"text": "This assumption leads us to an optimal\nclassifier only when the two classes have\na the same scatter/covariance matrix because we are making\nthis assumption that this matrix SW represents BOTH\ntheir \"spread\" but this is only true when\nS1 and S2 have to have the same structure",
			"rawText": "This assumption leads us to an optimal\nclassifier only when the two classes have\na the same scatter/covariance matrix because we are making\nthis assumption that this matrix SW represents BOTH\ntheir \"spread\" but this is only true when\nS1 and S2 have to have the same structure",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "This assumption leads us to an optimal\nclassifier only when the two classes have\na the same scatter/covariance matrix because we are making\nthis assumption that this matrix SW represents BOTH\ntheir \"spread\" but this is only true when\nS1 and S2 have to have the same structure",
			"lineHeight": 1.25
		},
		{
			"text": "This assumption leads us to an optimal\nclassifier only when the two classes have\na similar scatter matrix",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"id": "cLpZ6CAC",
			"type": "text",
			"x": 1236.8535195496427,
			"y": 1348.037806921203,
			"width": 327.3926696777344,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"roundness": null,
			"seed": 60711,
			"version": 2,
			"versionNonce": 1767143766,
			"updated": 1708723609063,
			"isDeleted": true,
			"groupIds": [],
			"boundElements": [],
			"link": null,
			"locked": false,
			"containerId": null,
			"originalText": "This assumption leads us to an optimal\nclassifier only when the two classes have\na similar scatter matrix",
			"rawText": "This assumption leads us to an optimal\nclassifier only when the two classes have\na similar scatter matrix",
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
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": -356.67718900040074,
		"scrollY": -719.4573934367817,
		"zoom": {
			"value": 0.9233143007073422
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