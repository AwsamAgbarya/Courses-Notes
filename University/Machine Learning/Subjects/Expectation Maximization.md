---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Clustering ^O5VFL6u2

This video is sponsored by unsupervised learning ^nPy88gtJ

Given N d-dimensional datapoints with no labels,
how do we group these datapoints into K clusters based on similarities? ^lTrPKmd3

But what is a cluster? ^rpx4lHsk

clusters are compromised of all X datapoints with minimal
euclidean distance to the cluster mean ^hEWtG6a2

Let's find K clusters such that it minimizes ^3kt8PB42

lets devise an algorithm such that we can converge to an optimal
separation of datapoints into a given k ^FDFve01S

1) Firstly we initialize the initial cluster means (by assigning them to K random points)

2) We split up all datapoints according to the closest center to it


3) we calculate the means of the resulting clusters and update our mean values



4) Iterate over 2 and 3 until we converge to a local minimum

5) repeat entire process over different random initialization in order to get the best local minima ^XfeX7Pim

hard to find global
minima ^5rKS4tnv

But theres a major
flaw in this algorithm ^kjukw4oZ

This algorithm has quite a few assumptions:
 1) The clusters are of similar size
2) the clusters are isometric Gaussian distributions
3) The clusters have similar variances ^AfJPm0RK

all of which does not allow us to model many things
in the real world ^AyHW1U7U

As always we will
take a detour
onto something 
different and by
product we can
reach a clustering
solution ^CQoUAznF

Gaussian mixture models ^TUTcduEN

We seek a way in order to be able to describe multiple distributions
with different sizes and different variables in order to continue with a
different clustering algorithm ^OJG9fe5X

We formally write the following:
given theta ^i4ULvx7C

Cluster priors
think of it as ratio of sizes
between clusters
or
 how likely is it that a random x
belongs to cluster k ^OR9LTSNg

parameters that generate
our distribution k ^R4MrW9R4

note that this works
on any distribution that is
of the exponential family
but we choose gaussian
for our case ^Kx0lUoRG

Such that ^oIt6bdSw

is the probability density function for a given x
and since all datapoints xi are i.i.d we can
generalize this to all our datapoints X ^Tepyx7K2

lets attempt to optimize these parameters
using maximum liklihood ^AF92zedz

it is quite difficult to optimize this due to having a log of sums
which has no analytical solution to simplify this equation ^oAPsLdmm

Introducing auxiliary variables ^nrKsB9lR

An auxiliary variable Z indicates
whether a sample x
belongs to the current cluster
(and by how much)
Ideally if z is confident of its choice,
kth dimension will have 1
and the others will be 0 ^ca4BPSnw

But how is this useful? ^JiUoEcNF

Think about it this way
We have already understood that optimizing the
incomplete-data log-liklihood ^lY6GeF1v

because the log of sums is analytically hard to solve.
The inner sum indicates the likelihood of a point xn belonging
to not one cluster, but all of them (weighted by their priors)
BUT what if we know that a large majority of that sum is insignificant?
aka what if we have a variable Z such that it can tell us which x belongs to
such that it eliminates the sum?

well this is exactly the complete-data log-likelihood is ^Ceabu8xT

The delta indicates that we only take into account the relevant probability 
density functions where the Z value at that dimension is 1 (aka we are sure
it belongs to it) and thus the sum collapses and we no longer have a log of sums ^0Umi5Tdl

Problem:
We dont know Z, we just defined it to solve our problem and created
another problem with trying to find the optimal Z ^Tdfd3fPB

Worry not my dear, we can multi-task our optimization! ^aBIWYBaP

Expectation Maximization Algorithm ^WM2Of3Tp

1) Firstly we initialize the initial cluster variables


2) EXPECTATION: we try to optimally find our latent variable Z
by computing the membership probabilities given the current parameters
which are treated as constant for this step












3) MAXIMIZATION: according to our naive assumption of membership, update
the parameters theta such that they reflect it better  ^4DyTt80m

given our parameters
whats the membership of point n
to each cluster k ^kxihJn5n

i.e how likely is it that
xn belongs to each cluster k
given our theta ^DnexHjBK

bayes ^IPpkawLF

given that we know
znk according to our
parameters, how likely
is it that xn belongs to
cluster k ^c9E9wAUc

density function
for all our datapoints
given our parameters ^TWqHDoXp

what points belong
to cluster k
given our parameters ^KSDQ3C8r

our memberships for each point
into each cluster ^2t1wCMDn

scale of each cluster
in comparsion to others ^BsNDMwvx

Keep in mind that this is a soft cluster assignment, meaning the membership probabilities range between
0 and 1 to give gradual effects between the clusters.
a Hard assignment approach will give the maximal dimension of z a 1 and the rest 0 that way
x only belongs to one cluster ^JwYchEdu

Does this really work?
how can we be sure it converges
into an optimal solution that we
want? ^PbQ2qjhr

Iterate between the updates of our latent variable and our distribution parameters

IN THEORY:
updates are defined in such a way that p(X | theta) increases in each step
this helps us find a local maxima of p
but it is rather difficult to find the global maxima of p if p is non-concave
I.e at every iteration we are guaranteed to be at an equal/better place then
the previous step thus we will always keep improving and converge locally

IN PRACTICE:
we optimize the lower bound of P then decrease the gap between P and the lower bound ^E6azPWO3

Given a parameter setting theta
and a probability mass function of z, q ^pq4FyVfV

Using Jensens inequality
and our knowledge that log is concave
and sum of q = 1 ^XNdHVvQx

%%***>>>text element-link:[[Jensens inequality]]<<<***%%Jensen from spn?? ^ncNHPwDo

which we mark as
F( q(z) , theta ) ^bKq3U7uu

WHICH IS WAY EASIER TO OPTIMIZE
rather than the log of a sum ^rCtKpNGd

Our EM objective is now the maximization of the lower bound



which is done in one of two ways:

1) Expectation: improve q for a given theta
2) Maximization: improve theta for a given q ^C5lebmgZ

but how do we select
q(z) in theory such that
we minimize the distance
between the lower bound
and the objective
(making it a tighter bound) ^OSSuBnAG

Lets measure distance between the
log likelihood and the lower bound ^m1mjxl9K

KL divergence is a method
of calculating distance/divergence
of two distributions ^01K4rXed

In conclusion ^ROzf5LvZ

Expectation step ^OrQEQyEy

Maximization step ^dilz5M58

we set q to a constant
and use the maximization step
in order to get theta ^CJ968S2m

can be taken out of
the max because its
a constant value added
everytime ^t9aTv43n

This entire process can be thought of as block coordinate gradient
descent over q and theta such that we set one of em to constant
and optimize the other for one step and then set the other to constant
and optimize the first up untill we reach a local minima ^lX8bxdv4

Whys it called expectation? ^bIkofRHh

Which boils down to trying to compute the expectation
of our PDF of our data given t iterations ^B853Z8rD

You want more math thrown at you? ^TbOHUgg6

Pros ^faevymCo

Cons ^isl7E9Ur

V.S ^61ZLzMfH

1) No step-size / learning rate

2) Each iteration improves likelihood ^bJpHCbSj

1) Locates local minima

2) Solution depends on initialization

3) can be slow ^lrUCtzjT

easier than maximizing
the actual objective ^S7wlLT8G

2 ^LXdiPtdG

1 ^kNkbMszU

marginalization ^W3c3xnEW

this roughly translates to:
Given my current guess about which datapoints belong to which clusters (q)
Which parameter theta maximizes the log likelihood of that data actually agreeing
with what q is telling me ^pwNeFnyV

this step roughly translates to:
given our current guess of the parameter theta and our data
the best estimate at which datapoints belong to which clusters (q)
IS ACTUALLY just the likelihood of the data being sampled from that
specific parameter guess
(This initial step just tells us to make our lower bound as close
to the data likelihood as possible) ^Qivvj3h8

Maximization step ^OHmwftEc

Expectation step ^uZ3ClSxP

So we are maximizing
an expectation ^3lx3Yxcd

Overall Objective ^U5acBinT

Explained
at the end
of the expectation step ^Jtoktn8E

i.i.d data ^MjysYgOn

How to estimate best
mean and covariance ^8TKrXSzI

Currently a known constant value ^4yBpegot

How to estimate best
Prior/Size of clusters? ^7I6RmZ6G

Lagrangian ^nhm3O7tN

= 1 ^tPc4o9sR

Maximal lambda
value possible
for our solution ^qRgObuCW


# Embedded files
7587d4d609d45472e0043ec8a569eba9daf5025e: $$\color{blue}S_k = \{ x_n : \|x_n - \mu_k\|^2 \leq \|x_n - \mu_l \|^2, \text{for every l} \in \{1..K\} \} $$
6f65e68c6514fdcfbccabbc418ac1eea68c25f68: $$\color{blue} \mu_k = \frac{1}{\|S_k\|} \sum_{x_n \in S_k} x_n $$
10f5df4f01138094014a36776c018f8d19975c13: $$p(X| \theta) =$$
622bd69a90b19a97c2edcec974a2f209c05027fb: $$\color{blue} q^{(t)} (z_{nk}) = p (z_{nk} = 1 | x_n, \theta^{(t)} ) = \frac{p (x_n | z_{nk} , \theta^{(t)}) p( z_{nk}, \theta^{(t)} )}{ p{(x_n | \theta{(t)} )}}$$
d11152a6ad56a5f2b7df26f4cb963bfc942f06d4: $$\color{blue} = \frac{\mathcal{T_k^{(t)}} p_k (x_n | \mu_k^{(t)} , \Sigma_k^{(t)} ) }{\sum_{I=1}^K \mathcal{T_I^{(t)}} p_I (x_n | \mu_k^{(I)} , \Sigma_l^{(I)} ) }$$
825ab123e91b432874fc770a879082112cb1dde5: $$\color{blue} \mathcal{T_k^{(t+1)}} = \frac{1}{N} \sum_{(n=1)}^N q^{(t)} (z_{nk})$$
0fedee441940f1250d8111e44f0fc2738675922a: $$\color{blue} \mu_k^{(t+1)} = \frac{1}{N_{\mathcal{T_k^{(t+1)}}}} \sum_{n=1}^N q^{(t)} (z_{nk}) x_n$$
400e8bf2866c666b05a9fa12445f893977b886e8: $$\color{blue} \Sigma_k^{(t+1)} = \frac{1}{N_{\mathcal{T_k^{(t+1)}}}} \sum_{n=1}^N q^{(t)} (z_{nk}) (x_n - \mu_k^{(t+1)})(x_n - \mu_k^{(t+1)})^T$$
b41cf9c321a79fee71d6b88511d46f07ad3d7535: $$log \sum_z \color{red} q(z) \color{black} \left[ \frac{p(X,z|\theta)}{\color{red} q(z)} \right]$$
32fd3e04847271eb037daae8869d30b53223f72e: $$\rightarrow \lambda \mathcal{T_k^{(t+1)}} = \sum_{n=1}^N q^{(t)} (z_{nk}) $$
30f9cecd49c367635a99a397a0ff4c47fea7a7a6: [[Pasted Image 20240127135720_029.png]]
feae62b03ef0fe8a38d7fff69f3180b14ef33ad4: [[Pasted Image 20240127140138_053.png]]
55cd904840cf93aba36460b9834bde676af757d0: [[Pasted Image 20240127142516_635.png]]
a998b774b6a8621493a054d61b021fcc66f4e5ef: [[Pasted Image 20240127142549_654.png]]
aff9591217b7b01199fd0e8b18e7f1a8c0f1e678: [[Pasted Image 20240127142634_670.png]]
9b6655e65243a633983ccae3663474295097d10a: [[Pasted Image 20240127142720_690.png]]
89c1a7183e68d9fddd6ea23eae022c60880a7211: [[Pasted Image 20240127154302_426.png]]
767b4a9c6ea0894da3bb0e62c8d7a32ce745cca8: [[Pasted Image 20240127154314_171.png]]
c1d51d6ca5dfc8d99d4ad65ee895e0a3274d5446: [[Pasted Image 20240127154405_444.png]]
396161be578a452c9f0275b74028160d7cb54449: [[Pasted Image 20240127155019_511.png]]
9c539cf09165fba075960183ebdba98d496bf5c3: [[Pasted Image 20240127155137_518.png]]
ea068c0aafd80b1351093ec2173fa193d1ea31e0: [[Pasted Image 20240127155236_544.png]]
19f317bd072751fcac570c2d14416b41af49e2ee: [[Pasted Image 20240127155407_569.png]]
04e5661b91f8ddcaac24cfa6c505041b73a155b1: [[Pasted Image 20240127155616_592.png]]
c880ba685988e865bee9eceb71a0a9d595bd9c7d: [[Pasted Image 20240127160351_653.png]]
1eba7a36fd1e36379100b64bbc9bdfd16a19d468: [[Pasted Image 20240127160421_669.png]]
4e5e506fc51f66dae7fa5c06ea1da834a61e9cb3: [[Pasted Image 20240127161718_752.png]]
3064387776cd4047806a71e94bf27a70819b4561: [[Pasted Image 20240127162133_802.png]]
802e84056c3f0c39df4ceacf53c71d201de3b279: [[Pasted Image 20240127162812_896.png]]
68d4006fa4e822abce1e7bad47471ecfa1cdd5c6: [[Pasted Image 20240127170034_731.png]]
fccaac32b22163c93ad9bef446df46e8b874795a: [[Pasted Image 20240127170052_749.png]]
5f197d46bfa2027fdc91c58b0ccfc3d4adb1c1c9: [[Pasted Image 20240127170124_767.png]]
6e8ccaa91fe9233f54a630b589949ab1a4342260: [[Pasted Image 20240127170225_462.png]]
f12310d092daa844726ae400738a24544314adc2: [[Pasted Image 20240127170313_787.png]]
fe9efede3738c085f7f832ec9b8ccf4d22bf50e6: [[Pasted Image 20240127170343_803.png]]
b5228740c73e1d3868bcce6181fd017b6ab12b36: [[Pasted Image 20240127173009_993.png]]
70e340bc5f695736b66754f98b64868b4ba4652d: [[Pasted Image 20240127173025_996.png]]
93948e7b53c77334e0fc1bc039ef94b2f6cd41eb: [[Pasted Image 20240127180132_279.png]]
807fd8690ff7d48d9cd9257bb0b313ca32a1ecb0: [[Pasted Image 20240127180532_346.png]]
8894a5490b51c4d5daea8ea1766f5ada473aa3b5: [[Pasted Image 20240127180737_382.png]]
dd904281f8202291acf13fce4810b801fad49ca3: [[Pasted Image 20240127181207_407.png]]
644ba028a75aae6377c52a56bbec2e240286893a: [[Pasted Image 20240127181228_422.png]]
d121785775551808ce8e9a8cbcf42f88a44ba3e0: [[Pasted Image 20240127181700_441.png]]
5e929293d189ef469b361e1cded51f97f6e0089a: [[Pasted Image 20240127181731_474.png]]
fc9aebe857f494974a4cf5b15a4699e14ee9c0f3: [[Pasted Image 20240127182107_496.png]]
8df35491a1fb61b0beb3f81b450238259368f440: [[Pasted Image 20240127182235_719.png]]
6f3dd3932218a217fb29b32392badc19c96e8f89: [[Pasted Image 20240127182522_527.png]]
53d79f28baf053a5b36d4e9ebeac7324c3be4dc9: [[Pasted Image 20240127183004_575.png]]
af2becbb12d7bd7e701529455596383c14401b73: [[Pasted Image 20240127183050_592.png]]
816b9fbc13fea968ed9d967489d47ffb05e30eec: [[Pasted Image 20240127183127_616.png]]
0ca5b46f5ba32030313ffdf160337d22a734711c: [[Pasted Image 20240127183542_643.png]]
fd9964bf551b49b60572341a4a60f98435c20ec9: [[Pasted Image 20240127183627_666.png]]
864af944519ff4cea4a494576808a555d25a7a1f: [[Pasted Image 20240127183642_678.png]]
95a5fb477c0d84178eecd993d96f470a3312b8a5: [[Pasted Image 20240127183657_680.png]]
d59a9c6dbf9f512ec01dd9bd6e19dd8379d19268: [[Pasted Image 20240127183712_684.png]]
acebfa05d7c8caaab907d5f59a5965329195fdab: [[Pasted Image 20240127183758_690.png]]
7579bcb18fbfe5027510ab807911b93d0e8b32a3: [[Pasted Image 20240227165245_971.png]]

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
			"version": 92,
			"versionNonce": 310547215,
			"isDeleted": false,
			"id": "4xd7dncAvIxt6ZoG5pJUz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1777.9287559732313,
			"y": 3659.8894252131877,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 1208.72333949173,
			"height": 192.74909220289936,
			"seed": 896826896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "zGDb548bzIELQGwMcskj6",
					"type": "arrow"
				}
			],
			"updated": 1709051767264,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "acebfa05d7c8caaab907d5f59a5965329195fdab",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 229,
			"versionNonce": 988752225,
			"isDeleted": false,
			"id": "bj064YxDC6NAXiehQ8run",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2258.9131741678834,
			"y": 2790.34774421615,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 989,
			"height": 615,
			"seed": 724305648,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "81ZDD0-iNDLFbyBY3TWm_",
					"type": "arrow"
				},
				{
					"id": "zGDb548bzIELQGwMcskj6",
					"type": "arrow"
				}
			],
			"updated": 1709051767264,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0ca5b46f5ba32030313ffdf160337d22a734711c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 182,
			"versionNonce": 234576175,
			"isDeleted": false,
			"id": "ORZHEfndLsb1SZYcA6euQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2403.119054662002,
			"y": 2023.4929064497496,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 292.0914255305065,
			"height": 107.2473916634689,
			"seed": 1675541744,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767264,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "644ba028a75aae6377c52a56bbec2e240286893a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 229,
			"versionNonce": 1692751169,
			"isDeleted": false,
			"id": "YGK3gAttgjtp2IQjR8RuP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2406.9098917052515,
			"y": 1806.5496149360765,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 579.1964690764573,
			"height": 223.82296275398082,
			"seed": 307688688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "sWOM4TvsPlNsfA8dWj11h",
					"type": "arrow"
				}
			],
			"updated": 1709051767264,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dd904281f8202291acf13fce4810b801fad49ca3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 247,
			"versionNonce": 1186356047,
			"isDeleted": false,
			"id": "tGKYoKJ19wECVuagidkge",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1677.8106727750746,
			"y": 1708.5418441478341,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 350.7429778770654,
			"height": 259.8570237556361,
			"seed": 584631536,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767264,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8894a5490b51c4d5daea8ea1766f5ada473aa3b5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 219,
			"versionNonce": 1793787169,
			"isDeleted": false,
			"id": "kWKjDi7EfqzFHm4UhDgJQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1112.1253241233826,
			"y": 1319.2663563922029,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 332.5721955002259,
			"height": 88.03381645594216,
			"seed": 1427899632,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767264,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "70e340bc5f695736b66754f98b64868b4ba4652d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 111,
			"versionNonce": 1359747439,
			"isDeleted": false,
			"id": "2FL0sNaoazkbs1UH-sB_R",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -191.75,
			"y": -418.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 381,
			"height": 176,
			"seed": 1770063600,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "O5VFL6u2"
				}
			],
			"updated": 1709051767264,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 62,
			"versionNonce": 678410497,
			"isDeleted": false,
			"id": "O5VFL6u2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -67.9121166573459,
			"y": -347.9832092444162,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 132.9165496826172,
			"height": 35,
			"seed": 709537520,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767264,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Clustering",
			"rawText": "Clustering",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "2FL0sNaoazkbs1UH-sB_R",
			"originalText": "Clustering",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 267,
			"versionNonce": 574952335,
			"isDeleted": false,
			"id": "nPy88gtJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -184.75,
			"y": -180.7578125,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 375.82476806640625,
			"height": 20,
			"seed": 1820712976,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767264,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This video is sponsored by unsupervised learning",
			"rawText": "This video is sponsored by unsupervised learning",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This video is sponsored by unsupervised learning",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 197,
			"versionNonce": 1592979681,
			"isDeleted": false,
			"id": "lTrPKmd3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -358.83963775634766,
			"y": -234.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 715.0792236328125,
			"height": 50,
			"seed": 1668591120,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767264,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Given N d-dimensional datapoints with no labels,\nhow do we group these datapoints into K clusters based on similarities?",
			"rawText": "Given N d-dimensional datapoints with no labels,\nhow do we group these datapoints into K clusters based on similarities?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given N d-dimensional datapoints with no labels,\nhow do we group these datapoints into K clusters based on similarities?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 114,
			"versionNonce": 1922681263,
			"isDeleted": false,
			"id": "TEYCCdHAgOS2ncf2lBtNy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -191.75000000000003,
			"y": -152.9083141722408,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 384.00000000000006,
			"height": 57.15050167224081,
			"seed": 589881072,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "30f9cecd49c367635a99a397a0ff4c47fea7a7a6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 136,
			"versionNonce": 1946430657,
			"isDeleted": false,
			"id": "vzQmSuDSEG2CmgnM5T-Cw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 285.25,
			"y": -222.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 372,
			"height": 125,
			"seed": 419482352,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					149,
					-62
				],
				[
					336,
					10
				],
				[
					372,
					63
				]
			]
		},
		{
			"type": "text",
			"version": 40,
			"versionNonce": 1597160399,
			"isDeleted": false,
			"id": "rpx4lHsk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 548.1701354980469,
			"y": -152.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 230.15972900390625,
			"height": 25,
			"seed": 2082118160,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "But what is a cluster?",
			"rawText": "But what is a cluster?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But what is a cluster?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 129,
			"versionNonce": 1866656929,
			"isDeleted": false,
			"id": "hEWtG6a2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 431.3119205416715,
			"y": -123.04402869217591,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 454.5610046386719,
			"height": 40,
			"seed": 892679408,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "clusters are compromised of all X datapoints with minimal\neuclidean distance to the cluster mean",
			"rawText": "clusters are compromised of all X datapoints with minimal\neuclidean distance to the cluster mean",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "clusters are compromised of all X datapoints with minimal\neuclidean distance to the cluster mean",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 81,
			"versionNonce": 1277716975,
			"isDeleted": false,
			"id": "3kt8PB42",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -216.98981462404674,
			"y": -64.40831441887948,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 431.37957763671875,
			"height": 25,
			"seed": 110498544,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Let's find K clusters such that it minimizes",
			"rawText": "Let's find K clusters such that it minimizes",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Let's find K clusters such that it minimizes",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 99,
			"versionNonce": 945729665,
			"isDeleted": false,
			"id": "hCxrVo081FXfPCwNCgvwj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -328.73636276288994,
			"y": -39.40831371886803,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 663.7974935562888,
			"height": 64.65071851171103,
			"seed": 1437818896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "feae62b03ef0fe8a38d7fff69f3180b14ef33ad4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 178,
			"versionNonce": 109270031,
			"isDeleted": false,
			"id": "FDFve01S",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -318.81497802956426,
			"y": 23.48807529065084,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 654.679443359375,
			"height": 50,
			"seed": 815031312,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "lets devise an algorithm such that we can converge to an optimal\nseparation of datapoints into a given k",
			"rawText": "lets devise an algorithm such that we can converge to an optimal\nseparation of datapoints into a given k",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "lets devise an algorithm such that we can converge to an optimal\nseparation of datapoints into a given k",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 500,
			"versionNonce": 353826913,
			"isDeleted": false,
			"id": "XfeX7Pim",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -481.5170283694409,
			"y": 109.45534786596963,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffec99",
			"width": 969.3588256835938,
			"height": 300,
			"seed": 1555794960,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "tpHAwO-ptv-UCQqOBw3HA",
					"type": "arrow"
				},
				{
					"id": "zcGXnHpH1mYspO1yvghDV",
					"type": "arrow"
				}
			],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Firstly we initialize the initial cluster means (by assigning them to K random points)\n\n2) We split up all datapoints according to the closest center to it\n\n\n3) we calculate the means of the resulting clusters and update our mean values\n\n\n\n4) Iterate over 2 and 3 until we converge to a local minimum\n\n5) repeat entire process over different random initialization in order to get the best local minima",
			"rawText": "1) Firstly we initialize the initial cluster means (by assigning them to K random points)\n\n2) We split up all datapoints according to the closest center to it\n\n\n3) we calculate the means of the resulting clusters and update our mean values\n\n\n\n4) Iterate over 2 and 3 until we converge to a local minimum\n\n5) repeat entire process over different random initialization in order to get the best local minima",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Firstly we initialize the initial cluster means (by assigning them to K random points)\n\n2) We split up all datapoints according to the closest center to it\n\n\n3) we calculate the means of the resulting clusters and update our mean values\n\n\n\n4) Iterate over 2 and 3 until we converge to a local minimum\n\n5) repeat entire process over different random initialization in order to get the best local minima",
			"lineHeight": 1.25,
			"baseline": 293
		},
		{
			"type": "image",
			"version": 152,
			"versionNonce": 641464879,
			"isDeleted": false,
			"id": "U3vSZXUW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -273.69930403720883,
			"y": 186.6373775082332,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 574.550484417589,
			"height": 26.115931109890415,
			"seed": 48036,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7587d4d609d45472e0043ec8a569eba9daf5025e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 189,
			"versionNonce": 1731937345,
			"isDeleted": false,
			"id": "fRS6rlkn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -73.59134375889677,
			"y": 259.4553475315176,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 164.2321751094085,
			"height": 52.363881918941836,
			"seed": 8447,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6f65e68c6514fdcfbccabbc418ac1eea68c25f68",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 83,
			"versionNonce": 809163855,
			"isDeleted": false,
			"id": "9MyWDhOgWpTp-stNCGrQ6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 316.4665026855555,
			"y": 341.0755992943502,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 106.32133307466597,
			"height": 71.5624357233329,
			"seed": 735731728,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767265,
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
					106.32133307466597,
					-29.647294799666497
				],
				[
					82.80796133699937,
					41.9151409236664
				]
			]
		},
		{
			"type": "text",
			"version": 81,
			"versionNonce": 715854881,
			"isDeleted": false,
			"id": "5rKS4tnv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 382.3162445714361,
			"y": 281.6694071433506,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 148.4163360595703,
			"height": 40,
			"seed": 205288464,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "hard to find global\nminima",
			"rawText": "hard to find global\nminima",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "hard to find global\nminima",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 285,
			"versionNonce": 2019064431,
			"isDeleted": false,
			"id": "79pSch98D_r12FN-zNXi2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -580.4298240824705,
			"y": 38.045989237919315,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 146.1660303694584,
			"height": 142.81871669687538,
			"seed": 708356336,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "zRWFXiniexbmr3NunxGTf",
					"type": "arrow"
				}
			],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "55cd904840cf93aba36460b9834bde676af757d0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 252,
			"versionNonce": 861267969,
			"isDeleted": false,
			"id": "309C22I5gtshiIARBCOij",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -709.1473452809018,
			"y": 118.22697978905057,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 129.55118446457757,
			"height": 133.25264687785122,
			"seed": 1640421616,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "zRWFXiniexbmr3NunxGTf",
					"type": "arrow"
				}
			],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a998b774b6a8621493a054d61b021fcc66f4e5ef",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 131,
			"versionNonce": 1130189967,
			"isDeleted": false,
			"id": "zRWFXiniexbmr3NunxGTf",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -584.5378914074098,
			"y": 90.9010545822132,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 60.17331515549665,
			"height": 30.835805333366736,
			"seed": 804726512,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "309C22I5gtshiIARBCOij",
				"focus": 1.2963194828557256,
				"gap": 27.325925206837383
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
					-53.16525894889173,
					2.803580506946915
				],
				[
					-60.17331515549665,
					30.835805333366736
				]
			]
		},
		{
			"type": "image",
			"version": 266,
			"versionNonce": 725303265,
			"isDeleted": false,
			"id": "v8lCgQpctpceZiDmPD236",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -570.133693782,
			"y": 219.27328280027024,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 126.11060664075366,
			"height": 125.10172178762762,
			"seed": 1524732144,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "tpHAwO-ptv-UCQqOBw3HA",
					"type": "arrow"
				}
			],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "aff9591217b7b01199fd0e8b18e7f1a8c0f1e678",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 292,
			"versionNonce": 687991471,
			"isDeleted": false,
			"id": "Uu1edkMuXojjDe97Qhavf",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -700.3089169176097,
			"y": 287.24507208836553,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 125.71380712180618,
			"height": 127.23453865956996,
			"seed": 152201744,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "71UcUBRML4Z9N32JGFj2y",
					"type": "arrow"
				}
			],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9b6655e65243a633983ccae3663474295097d10a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 74,
			"versionNonce": 1349163969,
			"isDeleted": false,
			"id": "tpHAwO-ptv-UCQqOBw3HA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -581.0244721227457,
			"y": 191.52343090452783,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 71.15390660068908,
			"height": 30.965126020670255,
			"seed": 897708560,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "v8lCgQpctpceZiDmPD236",
				"focus": -1.2018472332530126,
				"gap": 27.74985189574241
			},
			"endBinding": {
				"elementId": "XfeX7Pim",
				"focus": -0.9671412280107536,
				"gap": 28.353537152615672
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
					65.22441438396504,
					6.588324685249006
				],
				[
					71.15390660068908,
					30.965126020670255
				]
			]
		},
		{
			"type": "arrow",
			"version": 284,
			"versionNonce": 904838351,
			"isDeleted": false,
			"id": "71UcUBRML4Z9N32JGFj2y",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -573.5335512791798,
			"y": 268.12537417876365,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 77.82482945749632,
			"height": 22.400303929846302,
			"seed": 1152524528,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Uu1edkMuXojjDe97Qhavf",
				"focus": 1.2874245835799292,
				"gap": 19.119697909601882
			},
			"endBinding": {
				"elementId": "Uu1edkMuXojjDe97Qhavf",
				"focus": -0.33051211628012844,
				"gap": 6.1204254644515
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
					-70.73883782195617,
					-3.4715392679719344
				],
				[
					-77.82482945749632,
					18.928764661874368
				]
			]
		},
		{
			"type": "arrow",
			"version": 113,
			"versionNonce": 1929608097,
			"isDeleted": false,
			"id": "zcGXnHpH1mYspO1yvghDV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 492.48879923370976,
			"y": 197.51233439819356,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 316.4500439901003,
			"height": 0.9858256822121234,
			"seed": 1277837040,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XfeX7Pim",
				"focus": -0.3987767811475238,
				"gap": 4.647001919556885
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
					316.4500439901003,
					-0.9858256822121234
				]
			]
		},
		{
			"type": "text",
			"version": 169,
			"versionNonce": 1304185583,
			"isDeleted": false,
			"id": "kjukw4oZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 567.8081488044074,
			"y": 154.75311115644024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 165.7283935546875,
			"height": 40,
			"seed": 1800739568,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "But theres a major\nflaw in this algorithm",
			"rawText": "But theres a major\nflaw in this algorithm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But theres a major\nflaw in this algorithm",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 346,
			"versionNonce": 859135873,
			"isDeleted": false,
			"id": "AfJPm0RK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 836.800291293474,
			"y": 135.14178045271768,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 518.099365234375,
			"height": 100,
			"seed": 778070768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This algorithm has quite a few assumptions:\n 1) The clusters are of similar size\n2) the clusters are isometric Gaussian distributions\n3) The clusters have similar variances",
			"rawText": "This algorithm has quite a few assumptions:\n 1) The clusters are of similar size\n2) the clusters are isometric Gaussian distributions\n3) The clusters have similar variances",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This algorithm has quite a few assumptions:\n 1) The clusters are of similar size\n2) the clusters are isometric Gaussian distributions\n3) The clusters have similar variances",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 1290999055,
			"isDeleted": false,
			"id": "AyHW1U7U",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 886.7958494804222,
			"y": 237.51255518465177,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 408.4328308105469,
			"height": 40,
			"seed": 225635056,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "all of which does not allow us to model many things\nin the real world",
			"rawText": "all of which does not allow us to model many things\nin the real world",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "all of which does not allow us to model many things\nin the real world",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 95,
			"versionNonce": 2134886241,
			"isDeleted": false,
			"id": "ak4FWMkbtEgsm35PHQADM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1095.7711930149078,
			"y": 306.2266395880075,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 3.455667813015907,
			"height": 263.7826430602249,
			"seed": 1897130736,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767265,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "TUTcduEN",
				"focus": -0.00603909254554128,
				"gap": 8.326087147713793
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
					3.455667813015907,
					263.7826430602249
				]
			]
		},
		{
			"type": "text",
			"version": 276,
			"versionNonce": 1795922735,
			"isDeleted": false,
			"id": "CQoUAznF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1107.1721383031556,
			"y": 358.9092190868771,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 142.59231567382812,
			"height": 140,
			"seed": 1902216720,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "As always we will\ntake a detour\nonto something \ndifferent and by\nproduct we can\nreach a clustering\nsolution",
			"rawText": "As always we will\ntake a detour\nonto something \ndifferent and by\nproduct we can\nreach a clustering\nsolution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "As always we will\ntake a detour\nonto something \ndifferent and by\nproduct we can\nreach a clustering\nsolution",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "text",
			"version": 67,
			"versionNonce": 1366438721,
			"isDeleted": false,
			"id": "TUTcduEN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 931.2445706020324,
			"y": 578.3353697959462,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 338.68939208984375,
			"height": 35,
			"seed": 236930288,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ak4FWMkbtEgsm35PHQADM",
					"type": "arrow"
				}
			],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Gaussian mixture models",
			"rawText": "Gaussian mixture models",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gaussian mixture models",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 224,
			"versionNonce": 1550736719,
			"isDeleted": false,
			"id": "OJG9fe5X",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 747.8466077248784,
			"y": 613.33537008377,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 705.8193359375,
			"height": 75,
			"seed": 1193754864,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We seek a way in order to be able to describe multiple distributions\nwith different sizes and different variables in order to continue with a\ndifferent clustering algorithm",
			"rawText": "We seek a way in order to be able to describe multiple distributions\nwith different sizes and different variables in order to continue with a\ndifferent clustering algorithm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We seek a way in order to be able to describe multiple distributions\nwith different sizes and different variables in order to continue with a\ndifferent clustering algorithm",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 179,
			"versionNonce": 774644513,
			"isDeleted": false,
			"id": "i4ULvx7C",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 954.7050906091999,
			"y": 966.8802356695677,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 303.83966064453125,
			"height": 50,
			"seed": 1139301104,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We formally write the following:\ngiven theta",
			"rawText": "We formally write the following:\ngiven theta",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We formally write the following:\ngiven theta",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 88,
			"versionNonce": 880008047,
			"isDeleted": false,
			"id": "l60T-7yDLa-CV0qagu0tF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 753.1721376849285,
			"y": 688.3353701174709,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 354,
			"height": 278,
			"seed": 474337520,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "89c1a7183e68d9fddd6ea23eae022c60880a7211",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 61,
			"versionNonce": 1641879297,
			"isDeleted": false,
			"id": "xrjQ8d9xyVFueN8YhmeMV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1100.7562764553552,
			"y": 699.335369855407,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 410,
			"height": 267,
			"seed": 899347696,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "767b4a9c6ea0894da3bb0e62c8d7a32ce745cca8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 95,
			"versionNonce": 124032399,
			"isDeleted": false,
			"id": "Laqklabyh6HK9QQointKk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 893.1201181592035,
			"y": 1021.6736137798298,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 421.0953165785241,
			"height": 40.90257055937894,
			"seed": 1147659280,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c1d51d6ca5dfc8d99d4ad65ee895e0a3274d5446",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 80,
			"versionNonce": 2131005153,
			"isDeleted": false,
			"id": "AxgD3eA-pq5mnWFj1zHVu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 977.8256851682302,
			"y": 1059.948962326105,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 153.64739135883133,
			"height": 45.07836688626867,
			"seed": 1361501712,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.063224941395788,
					45.07836688626867
				],
				[
					-153.64739135883133,
					43.808553734542784
				]
			]
		},
		{
			"type": "text",
			"version": 333,
			"versionNonce": 1283001263,
			"isDeleted": false,
			"id": "OR9LTSNg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 530.4777491425709,
			"y": 1012.3309691363847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 325.819580078125,
			"height": 150,
			"seed": 1879276784,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Cluster priors\nthink of it as ratio of sizes\nbetween clusters\nor\n how likely is it that a random x\nbelongs to cluster k",
			"rawText": "Cluster priors\nthink of it as ratio of sizes\nbetween clusters\nor\n how likely is it that a random x\nbelongs to cluster k",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cluster priors\nthink of it as ratio of sizes\nbetween clusters\nor\n how likely is it that a random x\nbelongs to cluster k",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 104,
			"versionNonce": 473041601,
			"isDeleted": false,
			"id": "Qx7g_TdrzOVelMUNw5crN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 622.2357186954151,
			"y": 1162.3309691037964,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 142.3036399240109,
			"height": 75.69342549149516,
			"seed": 1346431728,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "396161be578a452c9f0275b74028160d7cb54449",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 73,
			"versionNonce": 2144976335,
			"isDeleted": false,
			"id": "IT8czmwTHxB-aLSi1YP98",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1174.0013842240978,
			"y": 1064.8493388220854,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 252.912563593575,
			"height": 50.94317234594291,
			"seed": 1433161968,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					23.8937003038493,
					44.63162886945429
				],
				[
					252.912563593575,
					50.94317234594291
				]
			]
		},
		{
			"type": "text",
			"version": 120,
			"versionNonce": 1376062113,
			"isDeleted": false,
			"id": "R4MrW9R4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1396.1571506234186,
			"y": 1072.5133559006786,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 261.6796875,
			"height": 50,
			"seed": 449394416,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "parameters that generate\nour distribution k",
			"rawText": "parameters that generate\nour distribution k",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "parameters that generate\nour distribution k",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 166,
			"versionNonce": 77540335,
			"isDeleted": false,
			"id": "CmBB8a5Jjw32ZOiOfuMfa",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1415.916023850572,
			"y": 1127.448249649764,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 222.61276557972866,
			"height": 32.27064660738081,
			"seed": 1554117872,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9c539cf09165fba075960183ebdba98d496bf5c3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 44,
			"versionNonce": 2032995969,
			"isDeleted": false,
			"id": "5wPd7eA4QTCkxLh2phevq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1440.7961926567737,
			"y": 616.4178414032183,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 196.19388332397193,
			"height": 98.61597309935098,
			"seed": 527401488,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					144.29073958747176,
					11.41869162203011
				],
				[
					196.19388332397193,
					98.61597309935098
				]
			]
		},
		{
			"type": "text",
			"version": 120,
			"versionNonce": 1188156943,
			"isDeleted": false,
			"id": "Kx0lUoRG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1505.9602297893393,
			"y": 715.0338145025693,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 262.0596923828125,
			"height": 125,
			"seed": 1582021648,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "note that this works\non any distribution that is\nof the exponential family\nbut we choose gaussian\nfor our case",
			"rawText": "note that this works\non any distribution that is\nof the exponential family\nbut we choose gaussian\nfor our case",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "note that this works\non any distribution that is\nof the exponential family\nbut we choose gaussian\nfor our case",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 57,
			"versionNonce": 678008417,
			"isDeleted": false,
			"id": "oIt6bdSw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1050.514476662766,
			"y": 1130.9823206662365,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 99.2598876953125,
			"height": 25,
			"seed": 48306192,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Such that",
			"rawText": "Such that",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Such that",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 95,
			"versionNonce": 493501487,
			"isDeleted": false,
			"id": "N7KxSuXgmadHFMLHhJiTK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 943.6932588243583,
			"y": 1155.2275986074444,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 311.4816512316852,
			"height": 80.63408090340076,
			"seed": 1659743760,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ea068c0aafd80b1351093ec2173fa193d1ea31e0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 160,
			"versionNonce": 1921655361,
			"isDeleted": false,
			"id": "Tepyx7K2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 852.8922472299921,
			"y": 1237.4299633559513,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 468.51947021484375,
			"height": 75,
			"seed": 962974960,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "is the probability density function for a given x\nand since all datapoints xi are i.i.d we can\ngeneralize this to all our datapoints X",
			"rawText": "is the probability density function for a given x\nand since all datapoints xi are i.i.d we can\ngeneralize this to all our datapoints X",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "is the probability density function for a given x\nand since all datapoints xi are i.i.d we can\ngeneralize this to all our datapoints X",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 136,
			"versionNonce": 1817239119,
			"isDeleted": false,
			"id": "yk5-q4pHIOaz63x2ez6pi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1016.4084130393776,
			"y": 1313.9982461387947,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 272,
			"height": 98,
			"seed": 1235170832,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "j49DhnAXlxjLoQDo1Gd0l",
					"type": "arrow"
				}
			],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "19f317bd072751fcac570c2d14416b41af49e2ee",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 234,
			"versionNonce": 1684943393,
			"isDeleted": false,
			"id": "swjKA2J8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 913.1041380706914,
			"y": 1351.4135628648519,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 102.67185974539544,
			"height": 26.852640241103423,
			"seed": 19408,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767266,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "10f5df4f01138094014a36776c018f8d19975c13",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 113,
			"versionNonce": 106839151,
			"isDeleted": false,
			"id": "j49DhnAXlxjLoQDo1Gd0l",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1304.4945544178636,
			"y": 1363.0985983689036,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 542.0231834411206,
			"height": 0.920243095825299,
			"seed": 971416080,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767267,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "yk5-q4pHIOaz63x2ez6pi",
				"focus": 0.007283291544388347,
				"gap": 16.08614137848599
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
					542.0231834411206,
					-0.920243095825299
				]
			]
		},
		{
			"type": "text",
			"version": 143,
			"versionNonce": 1124419073,
			"isDeleted": false,
			"id": "AF92zedz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1390.565677465402,
			"y": 1314.9533374584869,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 345.4727478027344,
			"height": 40,
			"seed": 916588048,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767267,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "lets attempt to optimize these parameters\nusing maximum liklihood",
			"rawText": "lets attempt to optimize these parameters\nusing maximum liklihood",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "lets attempt to optimize these parameters\nusing maximum liklihood",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 112,
			"versionNonce": 1331353231,
			"isDeleted": false,
			"id": "D8bLwEuKBQa9XabZuAeMh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1836.42543831886,
			"y": 1332.2528858421124,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 875.9999999999999,
			"height": 373,
			"seed": 552746224,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "04e5661b91f8ddcaac24cfa6c505041b73a155b1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 174,
			"versionNonce": 156163553,
			"isDeleted": false,
			"id": "oAPsLdmm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1971.7959943877163,
			"y": 1688.2947635641592,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 641.919189453125,
			"height": 50,
			"seed": 1190034448,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "it is quite difficult to optimize this due to having a log of sums\nwhich has no analytical solution to simplify this equation",
			"rawText": "it is quite difficult to optimize this due to having a log of sums\nwhich has no analytical solution to simplify this equation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "it is quite difficult to optimize this due to having a log of sums\nwhich has no analytical solution to simplify this equation",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 262,
			"versionNonce": 503262383,
			"isDeleted": false,
			"id": "TkZxpCVp9Wrz2IDAw34ug",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2282.4295188456426,
			"y": 1758.092187590176,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 397.81845640912456,
			"height": 92.74217034212893,
			"seed": 461044240,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "ca4BPSnw",
				"focus": -0.4471817580832768,
				"gap": 9.766570340558474
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
					-54.72991969343093,
					90.8019122186463
				],
				[
					-397.81845640912456,
					92.74217034212893
				]
			]
		},
		{
			"type": "text",
			"version": 460,
			"versionNonce": 643463617,
			"isDeleted": false,
			"id": "nrKsB9lR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1539.8648625793578,
			"y": 1779.0468024078962,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 296.3596496582031,
			"height": 25,
			"seed": 1421421296,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "kI5xv6MxAGDEm6QsYatRb",
					"type": "arrow"
				}
			],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Introducing auxiliary variables",
			"rawText": "Introducing auxiliary variables",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Introducing auxiliary variables",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 444,
			"versionNonce": 1576255183,
			"isDeleted": false,
			"id": "ca4BPSnw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1501.2448827209596,
			"y": 1804.0468018358179,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 373.599609375,
			"height": 175,
			"seed": 178872560,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "TkZxpCVp9Wrz2IDAw34ug",
					"type": "arrow"
				}
			],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "An auxiliary variable Z indicates\nwhether a sample x\nbelongs to the current cluster\n(and by how much)\nIdeally if z is confident of its choice,\nkth dimension will have 1\nand the others will be 0",
			"rawText": "An auxiliary variable Z indicates\nwhether a sample x\nbelongs to the current cluster\n(and by how much)\nIdeally if z is confident of its choice,\nkth dimension will have 1\nand the others will be 0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "An auxiliary variable Z indicates\nwhether a sample x\nbelongs to the current cluster\n(and by how much)\nIdeally if z is confident of its choice,\nkth dimension will have 1\nand the others will be 0",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "image",
			"version": 509,
			"versionNonce": 2068289953,
			"isDeleted": false,
			"id": "vEi2RH2rRbfG2PTCOduzH",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1537.430652995376,
			"y": 1983.776626999474,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 301.2280688946206,
			"height": 31.18181181916971,
			"seed": 637991664,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c880ba685988e865bee9eceb71a0a9d595bd9c7d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 397,
			"versionNonce": 1909525743,
			"isDeleted": false,
			"id": "y9LlY4tu2tW7Sf3bky6Rg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1604.3265694232969,
			"y": 2015.305975910703,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 167.43623730315244,
			"height": 33.487247460630485,
			"seed": 1754348560,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1eba7a36fd1e36379100b64bbc9bdfd16a19d468",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 528,
			"versionNonce": 424000897,
			"isDeleted": false,
			"id": "kI5xv6MxAGDEm6QsYatRb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1672.0447435727324,
			"y": 1766.7641818273337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 303.1477560439014,
			"height": 197.1648324904279,
			"seed": 19991280,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "nrKsB9lR",
				"focus": -0.07464646799909666,
				"gap": 12.28262058056248
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
					-34.24566177982956,
					-178.31122857494597
				],
				[
					-303.1477560439014,
					-197.1648324904279
				]
			]
		},
		{
			"type": "text",
			"version": 187,
			"versionNonce": 1428133647,
			"isDeleted": false,
			"id": "JiUoEcNF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1406.96354233045,
			"y": 1541.048573918536,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 184.6563720703125,
			"height": 20,
			"seed": 368948464,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "But how is this useful?",
			"rawText": "But how is this useful?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But how is this useful?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 320,
			"versionNonce": 1066689889,
			"isDeleted": false,
			"id": "lY6GeF1v",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 847.0041332174732,
			"y": 1465.6912882217239,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 476.8194885253906,
			"height": 75,
			"seed": 1491975696,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Think about it this way\nWe have already understood that optimizing the\nincomplete-data log-liklihood",
			"rawText": "Think about it this way\nWe have already understood that optimizing the\nincomplete-data log-liklihood",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Think about it this way\nWe have already understood that optimizing the\nincomplete-data log-liklihood",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 143,
			"versionNonce": 2119687471,
			"isDeleted": false,
			"id": "3pJOxXRpNUqfCd0f6pW0G",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 907.6765123331448,
			"y": 1541.8401535787245,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 378.03103990324763,
			"height": 73.04139561552425,
			"seed": 1437520112,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4e5e506fc51f66dae7fa5c06ea1da834a61e9cb3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 564,
			"versionNonce": 428020033,
			"isDeleted": false,
			"id": "Ceabu8xT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 775.2713059147023,
			"y": 1619.046802483539,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 623.7613525390625,
			"height": 160,
			"seed": 1447930896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "because the log of sums is analytically hard to solve.\nThe inner sum indicates the likelihood of a point xn belonging\nto not one cluster, but all of them (weighted by their priors)\nBUT what if we know that a large majority of that sum is insignificant?\naka what if we have a variable Z such that it can tell us which x belongs to\nsuch that it eliminates the sum?\n\nwell this is exactly the complete-data log-likelihood is",
			"rawText": "because the log of sums is analytically hard to solve.\nThe inner sum indicates the likelihood of a point xn belonging\nto not one cluster, but all of them (weighted by their priors)\nBUT what if we know that a large majority of that sum is insignificant?\naka what if we have a variable Z such that it can tell us which x belongs to\nsuch that it eliminates the sum?\n\nwell this is exactly the complete-data log-likelihood is",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "because the log of sums is analytically hard to solve.\nThe inner sum indicates the likelihood of a point xn belonging\nto not one cluster, but all of them (weighted by their priors)\nBUT what if we know that a large majority of that sum is insignificant?\naka what if we have a variable Z such that it can tell us which x belongs to\nsuch that it eliminates the sum?\n\nwell this is exactly the complete-data log-likelihood is",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "image",
			"version": 91,
			"versionNonce": 14835535,
			"isDeleted": false,
			"id": "viVgghIpb24PFL2crXg76",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 876.533384112262,
			"y": 1782.9108737751,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 430.51760162421715,
			"height": 77.83672348567517,
			"seed": 916549872,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3064387776cd4047806a71e94bf27a70819b4561",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 353,
			"versionNonce": 1014055201,
			"isDeleted": false,
			"id": "0Umi5Tdl",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 761.6234172143576,
			"y": 1860.7475974269669,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 651.05712890625,
			"height": 60,
			"seed": 1772395760,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The delta indicates that we only take into account the relevant probability \ndensity functions where the Z value at that dimension is 1 (aka we are sure\nit belongs to it) and thus the sum collapses and we no longer have a log of sums",
			"rawText": "The delta indicates that we only take into account the relevant probability \ndensity functions where the Z value at that dimension is 1 (aka we are sure\nit belongs to it) and thus the sum collapses and we no longer have a log of sums",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The delta indicates that we only take into account the relevant probability \ndensity functions where the Z value at that dimension is 1 (aka we are sure\nit belongs to it) and thus the sum collapses and we no longer have a log of sums",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 166,
			"versionNonce": 1863818607,
			"isDeleted": false,
			"id": "Tdfd3fPB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 758.5502512418852,
			"y": 1927.414384915803,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 690.519287109375,
			"height": 75,
			"seed": 2062534160,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Gvn7hSCn9gijcDOtDYiNH",
					"type": "arrow"
				}
			],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Problem:\nWe dont know Z, we just defined it to solve our problem and created\nanother problem with trying to find the optimal Z",
			"rawText": "Problem:\nWe dont know Z, we just defined it to solve our problem and created\nanother problem with trying to find the optimal Z",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem:\nWe dont know Z, we just defined it to solve our problem and created\nanother problem with trying to find the optimal Z",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 1708029185,
			"isDeleted": false,
			"id": "aBIWYBaP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 833.0601999713577,
			"y": 2014.9584386781305,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffec99",
			"width": 541.4993896484375,
			"height": 25,
			"seed": 1515898096,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Worry not my dear, we can multi-task our optimization!",
			"rawText": "Worry not my dear, we can multi-task our optimization!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Worry not my dear, we can multi-task our optimization!",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 888,
			"versionNonce": 2084575119,
			"isDeleted": false,
			"id": "Gvn7hSCn9gijcDOtDYiNH",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 774.3873174491822,
			"y": 2012.8282110607138,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 766.2336444554439,
			"height": 1468.7903605979845,
			"seed": 1572231184,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Tdfd3fPB",
				"focus": -1.0026379731600543,
				"gap": 10.413826144910672
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
					-270.9734105280577,
					-166.8909084709228
				],
				[
					-273.1044422631471,
					-1311.0531302110107
				],
				[
					-716.9390806929061,
					-1468.7903605979845
				],
				[
					-766.2336444554439,
					-1383.9572838064785
				]
			]
		},
		{
			"type": "text",
			"version": 86,
			"versionNonce": 2031758561,
			"isDeleted": false,
			"id": "WM2Of3Tp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -232.8362487127732,
			"y": 650.835370419714,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 482.72198486328125,
			"height": 35,
			"seed": 80762896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Expectation Maximization Algorithm",
			"rawText": "Expectation Maximization Algorithm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Expectation Maximization Algorithm",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 974,
			"versionNonce": 1586777519,
			"isDeleted": false,
			"id": "4DyTt80m",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -369.6136982268372,
			"y": 712.3309686564525,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffec99",
			"width": 766.3792724609375,
			"height": 500,
			"seed": 449517584,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Firstly we initialize the initial cluster variables\n\n\n2) EXPECTATION: we try to optimally find our latent variable Z\nby computing the membership probabilities given the current parameters\nwhich are treated as constant for this step\n\n\n\n\n\n\n\n\n\n\n\n\n3) MAXIMIZATION: according to our naive assumption of membership, update\nthe parameters theta such that they reflect it better ",
			"rawText": "1) Firstly we initialize the initial cluster variables\n\n\n2) EXPECTATION: we try to optimally find our latent variable Z\nby computing the membership probabilities given the current parameters\nwhich are treated as constant for this step\n\n\n\n\n\n\n\n\n\n\n\n\n3) MAXIMIZATION: according to our naive assumption of membership, update\nthe parameters theta such that they reflect it better ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Firstly we initialize the initial cluster variables\n\n\n2) EXPECTATION: we try to optimally find our latent variable Z\nby computing the membership probabilities given the current parameters\nwhich are treated as constant for this step\n\n\n\n\n\n\n\n\n\n\n\n\n3) MAXIMIZATION: according to our naive assumption of membership, update\nthe parameters theta such that they reflect it better ",
			"lineHeight": 1.25,
			"baseline": 493
		},
		{
			"type": "image",
			"version": 80,
			"versionNonce": 1038346433,
			"isDeleted": false,
			"id": "bFyULto8BVwp_b0N6sAxx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -125.06706824121432,
			"y": 739.227759480783,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 265.1844040454796,
			"height": 31.67182153579614,
			"seed": 1660102896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "802e84056c3f0c39df4ceacf53c71d201de3b279",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 115,
			"versionNonce": 1899806671,
			"isDeleted": false,
			"id": "KgbEylUU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -249.47139414414005,
			"y": 863.5066326002981,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 560.4243786822348,
			"height": 59.35529133826625,
			"seed": 2331,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "622bd69a90b19a97c2edcec974a2f209c05027fb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 52,
			"versionNonce": 1573595297,
			"isDeleted": false,
			"id": "LJcJ8hmcLyj7Vq6scdS4W",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -214.64283029076103,
			"y": 919.1567528561695,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 65.55990544468466,
			"height": 19.888960078724494,
			"seed": 318171152,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.629653359574888,
					18.41570377659673
				],
				[
					-65.55990544468466,
					19.888960078724494
				]
			]
		},
		{
			"type": "text",
			"version": 161,
			"versionNonce": 374468079,
			"isDeleted": false,
			"id": "kxihJn5n",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -500.44278911879945,
			"y": 892.6381394178701,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 253.37655639648438,
			"height": 60,
			"seed": 59752688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "given our parameters\nwhats the membership of point n\nto each cluster k",
			"rawText": "given our parameters\nwhats the membership of point n\nto each cluster k",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "given our parameters\nwhats the membership of point n\nto each cluster k",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 168,
			"versionNonce": 578776193,
			"isDeleted": false,
			"id": "CyniW5Wr4KDMTpvpTOYH6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -69.48711210223883,
			"y": 919.8534085782935,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 42.7786794054162,
			"height": 55.9837394808543,
			"seed": 483068944,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.2098844531915347,
					50.090714272343234
				],
				[
					-42.7786794054162,
					55.9837394808543
				]
			]
		},
		{
			"type": "text",
			"version": 116,
			"versionNonce": 1490835471,
			"isDeleted": false,
			"id": "DnexHjBK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -325.9181108325204,
			"y": 957.698377931862,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 226.3364715576172,
			"height": 60,
			"seed": 2136992272,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "i.e how likely is it that\nxn belongs to each cluster k\ngiven our theta",
			"rawText": "i.e how likely is it that\nxn belongs to each cluster k\ngiven our theta",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i.e how likely is it that\nxn belongs to each cluster k\ngiven our theta",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 68,
			"versionNonce": 1941976161,
			"isDeleted": false,
			"id": "O_mUnpVdbXWVyl3H8z4vd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 48.399894570869094,
			"y": 911.4791221296443,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.9866143178874722,
			"height": 32.064965331342705,
			"seed": 669615856,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.9866143178874722,
					32.064965331342705
				]
			]
		},
		{
			"type": "text",
			"version": 33,
			"versionNonce": 1322548783,
			"isDeleted": false,
			"id": "IPpkawLF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 19.12823976239673,
			"y": 947.4905447325369,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 43.74409484863281,
			"height": 20,
			"seed": 92929264,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "bayes",
			"rawText": "bayes",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "bayes",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 123,
			"versionNonce": 358416449,
			"isDeleted": false,
			"id": "fOBrqZYp00FpTzt6GkkGw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 205.23580075468678,
			"y": 861.7782712262078,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 220.96015185975958,
			"height": 19.68464604541282,
			"seed": 1020423696,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					120.56845702815386,
					-11.810787627247691
				],
				[
					220.96015185975958,
					7.873858418165128
				]
			]
		},
		{
			"type": "text",
			"version": 142,
			"versionNonce": 992141391,
			"isDeleted": false,
			"id": "c9E9wAUc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 331.25173874725886,
			"y": 869.652129644373,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 189.888427734375,
			"height": 100,
			"seed": 907249680,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "given that we know\nznk according to our\nparameters, how likely\nis it that xn belongs to\ncluster k",
			"rawText": "given that we know\nznk according to our\nparameters, how likely\nis it that xn belongs to\ncluster k",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "given that we know\nznk according to our\nparameters, how likely\nis it that xn belongs to\ncluster k",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "line",
			"version": 32,
			"versionNonce": 624250913,
			"isDeleted": false,
			"id": "a110RoLB98jRuatDSd0Kw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 141.17954735640262,
			"y": 945.6323571518017,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 19.152239361471914,
			"height": 45.67072463120235,
			"seed": 305475312,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767268,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-19.152239361471914,
					45.67072463120235
				]
			]
		},
		{
			"type": "text",
			"version": 123,
			"versionNonce": 1872756335,
			"isDeleted": false,
			"id": "TWqHDoXp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 26.959953069586106,
			"y": 994.2495801463074,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 176.38438415527344,
			"height": 60,
			"seed": 302997232,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "density function\nfor all our datapoints\ngiven our parameters",
			"rawText": "density function\nfor all our datapoints\ngiven our parameters",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "density function\nfor all our datapoints\ngiven our parameters",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 63,
			"versionNonce": 1496884225,
			"isDeleted": false,
			"id": "V8sYiQQ6lsSxIWM2r7Gml",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 306.1834557013917,
			"y": 887.6845560068352,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 8.348412029359565,
			"height": 124.24401431929232,
			"seed": 757353200,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.348412029359565,
					124.24401431929232
				]
			]
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 1863604367,
			"isDeleted": false,
			"id": "KSDQ3C8r",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 215.18686557144622,
			"y": 1011.9285703261276,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 165.29635620117188,
			"height": 60,
			"seed": 1451972848,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "what points belong\nto cluster k\ngiven our parameters",
			"rawText": "what points belong\nto cluster k\ngiven our parameters",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "what points belong\nto cluster k\ngiven our parameters",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 273,
			"versionNonce": 2103868385,
			"isDeleted": false,
			"id": "G7hDdvdT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -130.94489118146268,
			"y": 1065.3616172002733,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 276.94005099682204,
			"height": 69.23501274920551,
			"seed": 37183,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d11152a6ad56a5f2b7df26f4cb963bfc942f06d4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 141,
			"versionNonce": 1329098415,
			"isDeleted": false,
			"id": "ddRUYw3p",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -119.01228811672306,
			"y": 1222.6721802003565,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 254.15848525478953,
			"height": 71.05506039381213,
			"seed": 61075,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "825ab123e91b432874fc770a879082112cb1dde5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 73,
			"versionNonce": 835606465,
			"isDeleted": false,
			"id": "P9LcGEkmgzshgeew9YtTY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 147.39025441450025,
			"y": 1253.7294074560332,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 94.17350181642462,
			"height": 29.3716663314151,
			"seed": 1396823792,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					78.56393476685969,
					6.501842877257332
				],
				[
					94.17350181642462,
					29.3716663314151
				]
			]
		},
		{
			"type": "text",
			"version": 102,
			"versionNonce": 1521795279,
			"isDeleted": false,
			"id": "2t1wCMDn",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 121.76971414962674,
			"y": 1285.3509306695796,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 241.92051696777344,
			"height": 40,
			"seed": 1578250992,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "our memberships for each point\ninto each cluster",
			"rawText": "our memberships for each point\ninto each cluster",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "our memberships for each point\ninto each cluster",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 210,
			"versionNonce": 1754249121,
			"isDeleted": false,
			"id": "vSgRHA8BG8le_saF1lQ1Z",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -126.40712471199458,
			"y": 1251.7880375637628,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 87.17795946427398,
			"height": 24.620679197939126,
			"seed": 194378992,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-42.41626023163687,
					-16.307871445425008
				],
				[
					-87.17795946427398,
					8.312807752514118
				]
			]
		},
		{
			"type": "text",
			"version": 175,
			"versionNonce": 1931595503,
			"isDeleted": false,
			"id": "BsNDMwvx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -398.45327360758387,
			"y": 1240.5852149567866,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 184.00039672851562,
			"height": 40,
			"seed": 1204636400,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "scale of each cluster\nin comparsion to others",
			"rawText": "scale of each cluster\nin comparsion to others",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scale of each cluster\nin comparsion to others",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 149,
			"versionNonce": 601496449,
			"isDeleted": false,
			"id": "4pKV1Awr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -114.14902066062498,
			"y": 1313.5858960413168,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 260.1441802992057,
			"height": 59.49485737784525,
			"seed": 14312,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0fedee441940f1250d8111e44f0fc2738675922a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 122,
			"versionNonce": 856168719,
			"isDeleted": false,
			"id": "XsSQE8G6IxI1otpY3DEnN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 77.87328628979577,
			"y": 1320.461067790101,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 34.4957964421331,
			"height": 23.833459360019106,
			"seed": 2140042768,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					7.526355587374496,
					-21.95187046317551
				],
				[
					34.4957964421331,
					-23.833459360019106
				]
			]
		},
		{
			"type": "image",
			"version": 112,
			"versionNonce": 1944912737,
			"isDeleted": false,
			"id": "9rb3hOmk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -196.00888524591872,
			"y": 1373.0807528537987,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 445.2469945247591,
			"height": 57.05426311749425,
			"seed": 32481,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "400e8bf2866c666b05a9fa12445f893977b886e8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 318,
			"versionNonce": 1340088111,
			"isDeleted": false,
			"id": "JwYchEdu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -383.95779762569714,
			"y": 1439.9547578125903,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 817.2977294921875,
			"height": 80,
			"seed": 1597147152,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Keep in mind that this is a soft cluster assignment, meaning the membership probabilities range between\n0 and 1 to give gradual effects between the clusters.\na Hard assignment approach will give the maximal dimension of z a 1 and the rest 0 that way\nx only belongs to one cluster",
			"rawText": "Keep in mind that this is a soft cluster assignment, meaning the membership probabilities range between\n0 and 1 to give gradual effects between the clusters.\na Hard assignment approach will give the maximal dimension of z a 1 and the rest 0 that way\nx only belongs to one cluster",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Keep in mind that this is a soft cluster assignment, meaning the membership probabilities range between\n0 and 1 to give gradual effects between the clusters.\na Hard assignment approach will give the maximal dimension of z a 1 and the rest 0 that way\nx only belongs to one cluster",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "image",
			"version": 180,
			"versionNonce": 890761025,
			"isDeleted": false,
			"id": "9WwEH2eV39_7vGO0wga04",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -374.4733995433015,
			"y": 1526.496537192891,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 197.04841778790754,
			"height": 185.57642086189924,
			"seed": 1422659088,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "68d4006fa4e822abce1e7bad47471ecfa1cdd5c6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 252,
			"versionNonce": 1007837519,
			"isDeleted": false,
			"id": "rVqb9SvyYP8N0ERg0kVG1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -103.91050880512682,
			"y": 1525.9976734475028,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 192.85697506573206,
			"height": 184.90411011456786,
			"seed": 311305232,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YaWDuv0EDQ0bpkKEzzvAM",
					"type": "arrow"
				}
			],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fccaac32b22163c93ad9bef446df46e8b874795a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 563,
			"versionNonce": 230317857,
			"isDeleted": false,
			"id": "YaWDuv0EDQ0bpkKEzzvAM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 94.43573539024828,
			"y": 1611.1963007220183,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 88.07707365895851,
			"height": 0.3603393761204643,
			"seed": 1741892112,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rVqb9SvyYP8N0ERg0kVG1",
				"focus": -0.07363184516893059,
				"gap": 5.4892691296430485
			},
			"endBinding": {
				"elementId": "wL8Ztfz7-AlflREcMjHay",
				"focus": 0.11061757714589521,
				"gap": 10.505756948470435
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
					88.07707365895851,
					-0.3603393761204643
				]
			]
		},
		{
			"type": "image",
			"version": 284,
			"versionNonce": 150429551,
			"isDeleted": false,
			"id": "wL8Ztfz7-AlflREcMjHay",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 193.01856599767723,
			"y": 1529.041305148204,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 191.77151167279703,
			"height": 183.05462477857898,
			"seed": 1037703184,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YaWDuv0EDQ0bpkKEzzvAM",
					"type": "arrow"
				},
				{
					"id": "FKN2RuILfRGB3C0Uid8Wm",
					"type": "arrow"
				}
			],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5f197d46bfa2027fdc91c58b0ccfc3d4adb1c1c9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 114,
			"versionNonce": 742642433,
			"isDeleted": false,
			"id": "hK-HUWYUxPWaNbhpYNUyh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 191.44574805745594,
			"y": 1760.054755063931,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 196.2250398289414,
			"height": 181.6407463281417,
			"seed": 1528426512,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "iMorrqUva1yJu-Luaj9Hx",
					"type": "arrow"
				}
			],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6e8ccaa91fe9233f54a630b589949ab1a4342260",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 85,
			"versionNonce": 148347279,
			"isDeleted": false,
			"id": "FKN2RuILfRGB3C0Uid8Wm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 288.06377818804845,
			"y": 1719.4024858636635,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1.1368683772161603e-13,
			"height": 42.77902611727836,
			"seed": 851850480,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wL8Ztfz7-AlflREcMjHay",
				"focus": 0.008766095012706381,
				"gap": 7.3065559368805
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
					-1.1368683772161603e-13,
					42.77902611727836
				]
			]
		},
		{
			"type": "image",
			"version": 242,
			"versionNonce": 1161022177,
			"isDeleted": false,
			"id": "9zAdO27r0RO9CdJHdjmAn",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -112.93655023328843,
			"y": 1745.1058930950153,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 205.47090376284692,
			"height": 195.65318139875185,
			"seed": 137438224,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "iMorrqUva1yJu-Luaj9Hx",
					"type": "arrow"
				}
			],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f12310d092daa844726ae400738a24544314adc2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 59,
			"versionNonce": 820744111,
			"isDeleted": false,
			"id": "iMorrqUva1yJu-Luaj9Hx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 187.58280986606894,
			"y": 1831.8217870555814,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 87.54777437954652,
			"height": 1.9897221449896279,
			"seed": 1879746288,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hK-HUWYUxPWaNbhpYNUyh",
				"focus": 0.22967134400604025,
				"gap": 3.862938191387002
			},
			"endBinding": {
				"elementId": "9zAdO27r0RO9CdJHdjmAn",
				"focus": -0.06604941771359593,
				"gap": 7.500681956963945
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
					-87.54777437954652,
					1.9897221449896279
				]
			]
		},
		{
			"type": "arrow",
			"version": 232,
			"versionNonce": 1360643777,
			"isDeleted": false,
			"id": "2uXxiv81ebcgX3C8kEIUU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -181.78313262014478,
			"y": 1607.4714422985965,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 82.20526874836116,
			"height": 0.8388292729423483,
			"seed": 1482909424,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
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
					82.20526874836116,
					0.8388292729423483
				]
			]
		},
		{
			"type": "image",
			"version": 130,
			"versionNonce": 995869135,
			"isDeleted": false,
			"id": "aeQCvmc9Bn0BKA29gOM47",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -372.5737170021549,
			"y": 1749.2246308701165,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 189.6205204175178,
			"height": 180.59097182620744,
			"seed": 717443088,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fe9efede3738c085f7f832ec9b8ccf4d22bf50e6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 68,
			"versionNonce": 177555105,
			"isDeleted": false,
			"id": "BHgSlRvRvlxCAd_lyTzsB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -112.86523402737521,
			"y": 1837.7909534905502,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 76.10687204585577,
			"height": 0.49743053624752065,
			"seed": 279482896,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
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
					-76.10687204585577,
					0.49743053624752065
				]
			]
		},
		{
			"type": "arrow",
			"version": 281,
			"versionNonce": 155234287,
			"isDeleted": false,
			"id": "Rf_SYg19KI91OA_U1j228",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -405.2934121838407,
			"y": 1053.711422637058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 309.83360112034893,
			"height": 0.6962159881288699,
			"seed": 49556208,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "E6azPWO3",
				"focus": 0.07338056962885091,
				"gap": 4.224787318741505
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
					-309.83360112034893,
					-0.6962159881288699
				]
			]
		},
		{
			"type": "text",
			"version": 165,
			"versionNonce": 743819905,
			"isDeleted": false,
			"id": "PbQ2qjhr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -681.7516544778559,
			"y": 964.8942469831754,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 256.20855712890625,
			"height": 80,
			"seed": 792414448,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Does this really work?\nhow can we be sure it converges\ninto an optimal solution that we\nwant?",
			"rawText": "Does this really work?\nhow can we be sure it converges\ninto an optimal solution that we\nwant?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Does this really work?\nhow can we be sure it converges\ninto an optimal solution that we\nwant?",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 855,
			"versionNonce": 1151523343,
			"isDeleted": false,
			"id": "E6azPWO3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1596.450921716681,
			"y": 904.3581231364755,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 877.09912109375,
			"height": 275,
			"seed": 346287856,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Rf_SYg19KI91OA_U1j228",
					"type": "arrow"
				},
				{
					"id": "WiWxhoOkjSS-9GSZ8Le27",
					"type": "arrow"
				}
			],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Iterate between the updates of our latent variable and our distribution parameters\n\nIN THEORY:\nupdates are defined in such a way that p(X | theta) increases in each step\nthis helps us find a local maxima of p\nbut it is rather difficult to find the global maxima of p if p is non-concave\nI.e at every iteration we are guaranteed to be at an equal/better place then\nthe previous step thus we will always keep improving and converge locally\n\nIN PRACTICE:\nwe optimize the lower bound of P then decrease the gap between P and the lower bound",
			"rawText": "Iterate between the updates of our latent variable and our distribution parameters\n\nIN THEORY:\nupdates are defined in such a way that p(X | theta) increases in each step\nthis helps us find a local maxima of p\nbut it is rather difficult to find the global maxima of p if p is non-concave\nI.e at every iteration we are guaranteed to be at an equal/better place then\nthe previous step thus we will always keep improving and converge locally\n\nIN PRACTICE:\nwe optimize the lower bound of P then decrease the gap between P and the lower bound",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Iterate between the updates of our latent variable and our distribution parameters\n\nIN THEORY:\nupdates are defined in such a way that p(X | theta) increases in each step\nthis helps us find a local maxima of p\nbut it is rather difficult to find the global maxima of p if p is non-concave\nI.e at every iteration we are guaranteed to be at an equal/better place then\nthe previous step thus we will always keep improving and converge locally\n\nIN PRACTICE:\nwe optimize the lower bound of P then decrease the gap between P and the lower bound",
			"lineHeight": 1.25,
			"baseline": 268
		},
		{
			"type": "arrow",
			"version": 634,
			"versionNonce": 1864028769,
			"isDeleted": false,
			"id": "WiWxhoOkjSS-9GSZ8Le27",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1152.350899116103,
			"y": 1205.6795218146826,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.759270456948343,
			"height": 49.57173685134376,
			"seed": 1922963184,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "E6azPWO3",
				"focus": -0.01763652825926975,
				"gap": 26.321398678207004
			},
			"endBinding": {
				"elementId": "pq4FyVfV",
				"focus": -0.007944405926661052,
				"gap": 14.015097184829528
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
					-0.759270456948343,
					49.57173685134376
				]
			]
		},
		{
			"type": "text",
			"version": 150,
			"versionNonce": 1115340847,
			"isDeleted": false,
			"id": "pq4FyVfV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1346.103728307882,
			"y": 1269.266355850856,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 387.8795166015625,
			"height": 50,
			"seed": 506702352,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "WiWxhoOkjSS-9GSZ8Le27",
					"type": "arrow"
				}
			],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Given a parameter setting theta\nand a probability mass function of z, q",
			"rawText": "Given a parameter setting theta\nand a probability mass function of z, q",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given a parameter setting theta\nand a probability mass function of z, q",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 181,
			"versionNonce": 1202970177,
			"isDeleted": false,
			"id": "JIUqVnXfWLwEGpMSXMK23",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1527.5939768340331,
			"y": 1334.9026657368331,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 410,
			"height": 68,
			"seed": 1774139632,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b5228740c73e1d3868bcce6181fd017b6ab12b36",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 157,
			"versionNonce": 615572047,
			"isDeleted": false,
			"id": "XNdHVvQx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1335.8540922894886,
			"y": 1424.2963143093457,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 378.63958740234375,
			"height": 75,
			"seed": 1391113232,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Using Jensens inequality\nand our knowledge that log is concave\nand sum of q = 1",
			"rawText": "Using Jensens inequality\nand our knowledge that log is concave\nand sum of q = 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Using Jensens inequality\nand our knowledge that log is concave\nand sum of q = 1",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 196,
			"versionNonce": 1694527009,
			"isDeleted": false,
			"id": "AlJmgkt0QPOsE4STy31om",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1285.3199114992617,
			"y": 1443.9748713638824,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 392.5354275615523,
			"height": 98.39278527268448,
			"seed": 298784784,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "ncNHPwDo",
				"focus": 0.21446747855429277,
				"gap": 13.321400579887722
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
					-298.2854964056123,
					-7.249994704302935
				],
				[
					-392.5354275615523,
					-98.39278527268448
				]
			]
		},
		{
			"type": "text",
			"version": 92,
			"versionNonce": 1008582767,
			"isDeleted": false,
			"id": "ncNHPwDo",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1770.463815459186,
			"y": 1307.2606855113102,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 174.8598175048828,
			"height": 25,
			"seed": 775051280,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "AlJmgkt0QPOsE4STy31om",
					"type": "arrow"
				}
			],
			"updated": 1709051767269,
			"link": "[[Jensens inequality]]",
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Jensen from spn??",
			"rawText": "Jensen from spn??",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Jensen from spn??",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 302,
			"versionNonce": 1844445697,
			"isDeleted": false,
			"id": "jltNEkuGm6XsMnj4zkpNr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1175.5839207353845,
			"y": 1503.0722759907553,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 337.67169979086754,
			"height": 103.89898455103616,
			"seed": 131594256,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767269,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "93948e7b53c77334e0fc1bc039ef94b2f6cd41eb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 194,
			"versionNonce": 713677455,
			"isDeleted": false,
			"id": "koWKumw0zL8Y-sNa6QaaM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -829.1946860580088,
			"y": 1553.7415661656917,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 198.64838217509987,
			"height": 38.865987816867346,
			"seed": 889439984,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					138.19017890441728,
					-3.454754472610375
				],
				[
					198.64838217509987,
					-38.865987816867346
				]
			]
		},
		{
			"type": "text",
			"version": 287,
			"versionNonce": 2139232737,
			"isDeleted": false,
			"id": "bKq3U7uu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -698.146123092111,
			"y": 1460.46319540521,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 168.01980590820312,
			"height": 50,
			"seed": 2092069616,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "which we mark as\nF( q(z) , theta )",
			"rawText": "which we mark as\nF( q(z) , theta )",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "which we mark as\nF( q(z) , theta )",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 150,
			"versionNonce": 1152233647,
			"isDeleted": false,
			"id": "rCtKpNGd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1322.6377543321446,
			"y": 1618.4091971088628,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 389.81964111328125,
			"height": 50,
			"seed": 794015984,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "WHICH IS WAY EASIER TO OPTIMIZE\nrather than the log of a sum",
			"rawText": "WHICH IS WAY EASIER TO OPTIMIZE\nrather than the log of a sum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "WHICH IS WAY EASIER TO OPTIMIZE\nrather than the log of a sum",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 252,
			"versionNonce": 1791374785,
			"isDeleted": false,
			"id": "C5lebmgZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1424.110922543381,
			"y": 1683.8537904279858,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 602.9393310546875,
			"height": 200,
			"seed": 1236576272,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Our EM objective is now the maximization of the lower bound\n\n\n\nwhich is done in one of two ways:\n\n1) Expectation: improve q for a given theta\n2) Maximization: improve theta for a given q",
			"rawText": "Our EM objective is now the maximization of the lower bound\n\n\n\nwhich is done in one of two ways:\n\n1) Expectation: improve q for a given theta\n2) Maximization: improve theta for a given q",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Our EM objective is now the maximization of the lower bound\n\n\n\nwhich is done in one of two ways:\n\n1) Expectation: improve q for a given theta\n2) Maximization: improve theta for a given q",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "image",
			"version": 81,
			"versionNonce": 875676367,
			"isDeleted": false,
			"id": "1ookZ6uHUMK-otLdx5Zxg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1284.037543650546,
			"y": 1716.7731611418953,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 323.9879797856133,
			"height": 59.12189412146227,
			"seed": 176524304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "807fd8690ff7d48d9cd9257bb0b313ca32a1ecb0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 266,
			"versionNonce": 853267873,
			"isDeleted": false,
			"id": "Xt5zDksmZ4BEkfaKhaq0A",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1659.965992400839,
			"y": 1834.4091981825698,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 278.53791125921384,
			"height": 1.3719441689274845,
			"seed": 897749744,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "OSSuBnAG",
				"focus": -1.0754273503991578,
				"gap": 5.69791807746401
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
					-278.53791125921384,
					1.3719441689274845
				]
			]
		},
		{
			"type": "text",
			"version": 283,
			"versionNonce": 1504612591,
			"isDeleted": false,
			"id": "OSSuBnAG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1924.8987235456798,
			"y": 1678.7112801051057,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 263.2996826171875,
			"height": 150,
			"seed": 613405712,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Xt5zDksmZ4BEkfaKhaq0A",
					"type": "arrow"
				}
			],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "but how do we select\nq(z) in theory such that\nwe minimize the distance\nbetween the lower bound\nand the objective\n(making it a tighter bound)",
			"rawText": "but how do we select\nq(z) in theory such that\nwe minimize the distance\nbetween the lower bound\nand the objective\n(making it a tighter bound)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "but how do we select\nq(z) in theory such that\nwe minimize the distance\nbetween the lower bound\nand the objective\n(making it a tighter bound)",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "text",
			"version": 152,
			"versionNonce": 1257404801,
			"isDeleted": false,
			"id": "m1mjxl9K",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2369.023464106026,
			"y": 1751.0428028831107,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 353.2796325683594,
			"height": 50,
			"seed": 1193044208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets measure distance between the\nlog likelihood and the lower bound",
			"rawText": "Lets measure distance between the\nlog likelihood and the lower bound",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets measure distance between the\nlog likelihood and the lower bound",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 73,
			"versionNonce": 1856805647,
			"isDeleted": false,
			"id": "tCmV2APxeqFDzoxdv_9-0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2163.675038532719,
			"y": 2111.6115837967272,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 242.36087249330535,
			"height": 1.994739691302584,
			"seed": 1519965200,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					242.36087249330535,
					-1.994739691302584
				]
			]
		},
		{
			"type": "text",
			"version": 168,
			"versionNonce": 340369761,
			"isDeleted": false,
			"id": "01K4rXed",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1973.166438476996,
			"y": 2049.774653366337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 333.099609375,
			"height": 75,
			"seed": 2024423664,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "KL divergence is a method\nof calculating distance/divergence\nof two distributions",
			"rawText": "KL divergence is a method\nof calculating distance/divergence\nof two distributions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "KL divergence is a method\nof calculating distance/divergence\nof two distributions",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 115,
			"versionNonce": 1738826031,
			"isDeleted": false,
			"id": "fUexgzblgDrL8p5b0EEj4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2018.5823608476414,
			"y": 2129.790874081722,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 409.67780926793984,
			"height": 46.56769342757878,
			"seed": 1328603664,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d121785775551808ce8e9a8cbcf42f88a44ba3e0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 141,
			"versionNonce": 472960321,
			"isDeleted": false,
			"id": "vR-dK6ARwcoX0Xyv7lciP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2399.8368141637957,
			"y": 2186.1847088768554,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 352,
			"height": 65,
			"seed": 1262386192,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5e929293d189ef469b361e1cded51f97f6e0089a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 113,
			"versionNonce": 368993103,
			"isDeleted": false,
			"id": "-In7shtEtEhe8zg_SKbA4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1871.3631715073047,
			"y": 2192.723477406406,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 156.7658977254082,
			"height": 37.943338302965,
			"seed": 1578370800,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767270,
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
					-19.970178054192047,
					35.94632049754591
				],
				[
					-156.7658977254082,
					37.943338302965
				]
			]
		},
		{
			"type": "text",
			"version": 28,
			"versionNonce": 436698401,
			"isDeleted": false,
			"id": "ROzf5LvZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2004.7657536034708,
			"y": 2244.6459403473054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 123.01988220214844,
			"height": 25,
			"seed": 933908720,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "In conclusion",
			"rawText": "In conclusion",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In conclusion",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 115,
			"versionNonce": 169025903,
			"isDeleted": false,
			"id": "OrQEQyEy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2303.8176022908087,
			"y": 1677.6660043862432,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 236.9650115966797,
			"height": 35,
			"seed": 248736784,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Expectation step",
			"rawText": "Expectation step",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Expectation step",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "arrow",
			"version": 58,
			"versionNonce": 758984961,
			"isDeleted": false,
			"id": "fef2vWS4hz66AxvGvGtjl",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1129.8061722812845,
			"y": 1946.8033689258755,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.997466345479097,
			"height": 204.82686694106224,
			"seed": 264364784,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767270,
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
					-2.997466345479097,
					204.82686694106224
				]
			]
		},
		{
			"type": "text",
			"version": 29,
			"versionNonce": 892017551,
			"isDeleted": false,
			"id": "dilz5M58",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1257.4144525755073,
			"y": 2175.609966630769,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 245.22500610351562,
			"height": 35,
			"seed": 176706288,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Maximization step",
			"rawText": "Maximization step",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Maximization step",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 1532061921,
			"isDeleted": false,
			"id": "CJ968S2m",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1115.6564538245748,
			"y": 1993.2704314171021,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 241.4725341796875,
			"height": 60,
			"seed": 339224816,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "we set q to a constant\nand use the maximization step\nin order to get theta",
			"rawText": "we set q to a constant\nand use the maximization step\nin order to get theta",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "we set q to a constant\nand use the maximization step\nin order to get theta",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 122,
			"versionNonce": 1266602415,
			"isDeleted": false,
			"id": "Rrag7Bi8QZhRDtlt6ILka",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1420.4083630136333,
			"y": 2225.5181478585637,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 583.202692361683,
			"height": 261.48456073081536,
			"seed": 841430032,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fc9aebe857f494974a4cf5b15a4699e14ee9c0f3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 98,
			"versionNonce": 1305715905,
			"isDeleted": false,
			"id": "t9aTv43n",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1042.2690811663279,
			"y": 2413.7608774692094,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 191.77639770507812,
			"height": 80,
			"seed": 571572240,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "can be taken out of\nthe max because its\na constant value added\neverytime",
			"rawText": "can be taken out of\nthe max because its\na constant value added\neverytime",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "can be taken out of\nthe max because its\na constant value added\neverytime",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "image",
			"version": 111,
			"versionNonce": 1714865103,
			"isDeleted": false,
			"id": "iBmUA7T0so684yTNybXPh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1344.3968139800295,
			"y": 2560.131487402101,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 402.90400657790894,
			"height": 41.45402233743829,
			"seed": 2073346064,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "oi00o8Wm8jO8wZRBAwVOy",
					"type": "arrow"
				}
			],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8df35491a1fb61b0beb3f81b450238259368f440",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 28,
			"versionNonce": 1348691105,
			"isDeleted": false,
			"id": "oi00o8Wm8jO8wZRBAwVOy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1119.4902227147516,
			"y": 2475.7718752670285,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 75.12594086349782,
			"seed": 1010539248,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "iBmUA7T0so684yTNybXPh",
				"focus": 0.11642767306057072,
				"gap": 9.233671271574849
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
					75.12594086349782
				]
			]
		},
		{
			"type": "image",
			"version": 557,
			"versionNonce": 1701540335,
			"isDeleted": false,
			"id": "HwdIK7LKbp8DfN7UZEu3f",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2426.077256628796,
			"y": 944.4164625949079,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 554.2194581980706,
			"height": 339.5166722225784,
			"seed": 93440752,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6f3dd3932218a217fb29b32392badc19c96e8f89",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 398,
			"versionNonce": 246425729,
			"isDeleted": false,
			"id": "lX8bxdv4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2435.24437183339,
			"y": 878.7584830222768,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 583.4091796875,
			"height": 80,
			"seed": 2037565456,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This entire process can be thought of as block coordinate gradient\ndescent over q and theta such that we set one of em to constant\nand optimize the other for one step and then set the other to constant\nand optimize the first up untill we reach a local minima",
			"rawText": "This entire process can be thought of as block coordinate gradient\ndescent over q and theta such that we set one of em to constant\nand optimize the other for one step and then set the other to constant\nand optimize the first up untill we reach a local minima",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This entire process can be thought of as block coordinate gradient\ndescent over q and theta such that we set one of em to constant\nand optimize the other for one step and then set the other to constant\nand optimize the first up untill we reach a local minima",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 358,
			"versionNonce": 309948513,
			"isDeleted": false,
			"id": "bIkofRHh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3087.1753255903477,
			"y": 1810.5869880784192,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 270.0196838378906,
			"height": 25,
			"seed": 1473074704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "45IvEXQJIFzLYVdqQLHcC",
					"type": "arrow"
				}
			],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Whys it called expectation?",
			"rawText": "Whys it called expectation?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Whys it called expectation?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 393,
			"versionNonce": 6095407,
			"isDeleted": false,
			"id": "6ZV3fWa-RsF5zUW6_lDiY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3220.058139752375,
			"y": 1843.7685816133323,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 557.3591497450432,
			"height": 311.60051366240737,
			"seed": 795803888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "53d79f28baf053a5b36d4e9ebeac7324c3be4dc9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 418,
			"versionNonce": 26131521,
			"isDeleted": false,
			"id": "B853Z8rD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3239.535034669974,
			"y": 2163.1464148547666,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 535.7194213867188,
			"height": 50,
			"seed": 272989936,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Which boils down to trying to compute the expectation\nof our PDF of our data given t iterations",
			"rawText": "Which boils down to trying to compute the expectation\nof our PDF of our data given t iterations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which boils down to trying to compute the expectation\nof our PDF of our data given t iterations",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 464,
			"versionNonce": 821748815,
			"isDeleted": false,
			"id": "OtJG4UJw0dlqqOMbVnm5A",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3106.251546580822,
			"y": 2219.1020959394045,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 280.9559765836784,
			"height": 46.55215986279272,
			"seed": 546022128,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "af2becbb12d7bd7e701529455596383c14401b73",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 401,
			"versionNonce": 466586657,
			"isDeleted": false,
			"id": "moTknLQFtdtz7KJgjXcBj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3087.996179464622,
			"y": 2257.302727374228,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 172.55250965554217,
			"height": 29.674635418469034,
			"seed": 793788144,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "816b9fbc13fea968ed9d967489d47ffb05e30eec",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 165,
			"versionNonce": 1943503471,
			"isDeleted": false,
			"id": "U7e7SjpD8CFyz6-dFlm1J",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1170.5331207086786,
			"y": 2696.885399539658,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 515.2133867925379,
			"height": 119.87143558558319,
			"seed": 1857856016,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "pwNeFnyV",
				"focus": -0.09777006440444508,
				"gap": 10.967072504231965
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
					-113.39520497435592,
					110.78052649467418
				],
				[
					-515.2133867925379,
					119.87143558558319
				]
			]
		},
		{
			"type": "text",
			"version": 75,
			"versionNonce": 2032885761,
			"isDeleted": false,
			"id": "TbOHUgg6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1682.6981315912376,
			"y": 2764.029562397968,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 357.53961181640625,
			"height": 25,
			"seed": 1390880496,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "You want more math thrown at you?",
			"rawText": "You want more math thrown at you?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "You want more math thrown at you?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 161,
			"versionNonce": 163273871,
			"isDeleted": false,
			"id": "81ZDD0-iNDLFbyBY3TWm_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1849.7188684735786,
			"y": 3410.2623296307347,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 537.3333333333333,
			"height": 210.66666666666652,
			"seed": 1408585744,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bj064YxDC6NAXiehQ8run",
				"focus": -0.1267426801314897,
				"gap": 4.914585414584508
			},
			"endBinding": {
				"elementId": "EJW2E3M7xXiZN68znW6RC",
				"focus": -0.11132161756059362,
				"gap": 8.66666666666697
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
					-61.33333333333326,
					113.33333333333348
				],
				[
					-479.9999999999998,
					108
				],
				[
					-537.3333333333333,
					210.66666666666652
				]
			]
		},
		{
			"type": "image",
			"version": 39,
			"versionNonce": 128038881,
			"isDeleted": false,
			"id": "EJW2E3M7xXiZN68znW6RC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2656.8855351402453,
			"y": 3629.595662964068,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 545,
			"height": 92,
			"seed": 439586320,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "81ZDD0-iNDLFbyBY3TWm_",
					"type": "arrow"
				}
			],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fd9964bf551b49b60572341a4a60f98435c20ec9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 148,
			"versionNonce": 106885807,
			"isDeleted": false,
			"id": "2JNtgv9Hu2fSPPdbTq_CE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2585.4226262830066,
			"y": 3730.546572451643,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 450.75394277435817,
			"height": 77.29396981359962,
			"seed": 916373520,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "864af944519ff4cea4a494576808a555d25a7a1f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 62,
			"versionNonce": 1229067201,
			"isDeleted": false,
			"id": "CustN4CvYPHH6PuUbgAep",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2672.5895826648975,
			"y": 3822.647883696363,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 524,
			"height": 89,
			"seed": 1848332816,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "95a5fb477c0d84178eecd993d96f470a3312b8a5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 331,
			"versionNonce": 1536106511,
			"isDeleted": false,
			"id": "AiIZTJtkvr6K53y3dPTLp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2660.0199970497174,
			"y": 3997.733046936138,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 665,
			"height": 95,
			"seed": 348297232,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709052515186,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d59a9c6dbf9f512ec01dd9bd6e19dd8379d19268",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 347,
			"versionNonce": 1378612129,
			"isDeleted": false,
			"id": "zGDb548bzIELQGwMcskj6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1852.125284264258,
			"y": 3414.257195956369,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 412.94094542646894,
			"height": 234.04437165797572,
			"seed": 97268240,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767270,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bj064YxDC6NAXiehQ8run",
				"focus": 0.3470054911618836,
				"gap": 8.909451740218628
			},
			"endBinding": {
				"elementId": "4xd7dncAvIxt6ZoG5pJUz",
				"focus": -0.3582208921831427,
				"gap": 11.58785759884313
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
					42.278983267247895,
					105.69745816811837
				],
				[
					375.9809583408778,
					126.83694980174141
				],
				[
					412.94094542646894,
					234.04437165797572
				]
			]
		},
		{
			"type": "text",
			"version": 144,
			"versionNonce": 762794735,
			"isDeleted": false,
			"id": "faevymCo",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -308.3955824378941,
			"y": 2027.3658082065854,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 61.264251708984375,
			"height": 35,
			"seed": 157995248,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Pros",
			"rawText": "Pros",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Pros",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 34,
			"versionNonce": 110024577,
			"isDeleted": false,
			"id": "isl7E9Ur",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 256.3470463522632,
			"y": 2027.365807683189,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 61.824249267578125,
			"height": 35,
			"seed": 1625067024,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Cons",
			"rawText": "Cons",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cons",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 19,
			"versionNonce": 269294863,
			"isDeleted": false,
			"id": "61ZLzMfH",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -27.068103126321756,
			"y": 2123.816462561625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 39.17216491699219,
			"height": 35,
			"seed": 556830736,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "V.S",
			"rawText": "V.S",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V.S",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 96,
			"versionNonce": 413810529,
			"isDeleted": false,
			"id": "bJpHCbSj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -468.3054594815633,
			"y": 2097.640103122407,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 354.61956787109375,
			"height": 75,
			"seed": 1084598800,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) No step-size / learning rate\n\n2) Each iteration improves likelihood",
			"rawText": "1) No step-size / learning rate\n\n2) Each iteration improves likelihood",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) No step-size / learning rate\n\n2) Each iteration improves likelihood",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 120,
			"versionNonce": 1302635311,
			"isDeleted": false,
			"id": "lrUCtzjT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 112.39936869840106,
			"y": 2096.316462933558,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 349.7196044921875,
			"height": 125,
			"seed": 192381680,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Locates local minima\n\n2) Solution depends on initialization\n\n3) can be slow",
			"rawText": "1) Locates local minima\n\n2) Solution depends on initialization\n\n3) can be slow",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Locates local minima\n\n2) Solution depends on initialization\n\n3) can be slow",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 171,
			"versionNonce": 1187883841,
			"isDeleted": false,
			"id": "kNSbRvVv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1441.4774769835926,
			"y": 1517.898212535285,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 263.98047392081344,
			"height": 64.1308495965818,
			"seed": 37874,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b41cf9c321a79fee71d6b88511d46f07ad3d7535",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "y-y9IQifIFjMftnHivlDA",
			"type": "line",
			"x": -802.4945359392175,
			"y": 1700.0418168961753,
			"width": 103.44787925607261,
			"height": 52.681790361888716,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2012021775,
			"version": 49,
			"versionNonce": 380003663,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					96.74292411910494,
					5.268179036188712
				],
				[
					103.44787925607261,
					52.681790361888716
				]
			],
			"lastCommittedPoint": [
				103.44787925607261,
				52.681790361888716
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "S7wlLT8G",
			"type": "text",
			"x": -798.8058676321831,
			"y": 1763.738890697368,
			"width": 216.75973510742188,
			"height": 50,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1527672879,
			"version": 47,
			"versionNonce": 1498979105,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "easier than maximizing\nthe actual objective",
			"rawText": "easier than maximizing\nthe actual objective",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "easier than maximizing\nthe actual objective",
			"lineHeight": 1.25
		},
		{
			"id": "VmwApaPv0eYtO-XqJ3pMJ",
			"type": "image",
			"x": -798.8058681445992,
			"y": 1818.107785058423,
			"width": 224.09618159987446,
			"height": 42.824662975892245,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 229175457,
			"version": 112,
			"versionNonce": 2053825391,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7579bcb18fbfe5027510ab807911b93d0e8b32a3",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "HakYnFTVK2sNMRy-HUn3M",
			"type": "ellipse",
			"x": -1206.18084417962,
			"y": 2030.8493048105443,
			"width": 52.933354123647405,
			"height": 49,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 712551503,
			"version": 53,
			"versionNonce": 863176417,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "LXdiPtdG"
				}
			],
			"updated": 1709051767271,
			"link": null,
			"locked": false
		},
		{
			"id": "LXdiPtdG",
			"type": "text",
			"x": -1187.0489290608737,
			"y": 2043.0251886714739,
			"width": 14.239990234375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1936989615,
			"version": 32,
			"versionNonce": 911086511,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "2",
			"rawText": "2",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "HakYnFTVK2sNMRy-HUn3M",
			"originalText": "2",
			"lineHeight": 1.25
		},
		{
			"id": "RavwJ-B_CWzQwLKTqrOQY",
			"type": "ellipse",
			"x": -1824.8936554937286,
			"y": 1850.355244847943,
			"width": 46.85903479798321,
			"height": 49,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1785989217,
			"version": 18,
			"versionNonce": 739345089,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "kNkbMszU"
				}
			],
			"updated": 1709051767271,
			"link": null,
			"locked": false
		},
		{
			"id": "kNkbMszU",
			"type": "text",
			"x": -1804.2413078119648,
			"y": 1862.5311287088725,
			"width": 5.4199981689453125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 430351969,
			"version": 5,
			"versionNonce": 2043528655,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "1",
			"rawText": "1",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "RavwJ-B_CWzQwLKTqrOQY",
			"originalText": "1",
			"lineHeight": 1.25
		},
		{
			"id": "sWOM4TvsPlNsfA8dWj11h",
			"type": "arrow",
			"x": -2397.8885546884985,
			"y": 1830.5597480590914,
			"width": 68.89132510149784,
			"height": 89.66003340415477,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 701073167,
			"version": 64,
			"versionNonce": 657818273,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-63.82578649109337,
					7.598307915606256
				],
				[
					-68.89132510149784,
					89.66003340415477
				],
				[
					-16.716277414333945,
					83.07483321062932
				]
			],
			"lastCommittedPoint": [
				-16.716277414333945,
				83.07483321062932
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "YGK3gAttgjtp2IQjR8RuP",
				"focus": 0.28524976548894415,
				"gap": 7.694940397580808
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "W3c3xnEW",
			"type": "text",
			"x": -2463.3801125381,
			"y": 1858.8939949721528,
			"width": 113.76028442382812,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 777439521,
			"version": 76,
			"versionNonce": 1099859585,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "marginalization",
			"rawText": "marginalization",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "marginalization",
			"lineHeight": 1.25
		},
		{
			"id": "pwNeFnyV",
			"type": "text",
			"x": -1483.3313556756295,
			"y": 2605.918327035426,
			"width": 657.6334228515625,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 424608609,
			"version": 417,
			"versionNonce": 1231281679,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "U7e7SjpD8CFyz6-dFlm1J",
					"type": "arrow"
				}
			],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "this roughly translates to:\nGiven my current guess about which datapoints belong to which clusters (q)\nWhich parameter theta maximizes the log likelihood of that data actually agreeing\nwith what q is telling me",
			"rawText": "this roughly translates to:\nGiven my current guess about which datapoints belong to which clusters (q)\nWhich parameter theta maximizes the log likelihood of that data actually agreeing\nwith what q is telling me",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "this roughly translates to:\nGiven my current guess about which datapoints belong to which clusters (q)\nWhich parameter theta maximizes the log likelihood of that data actually agreeing\nwith what q is telling me",
			"lineHeight": 1.25
		},
		{
			"id": "Qivvj3h8",
			"type": "text",
			"x": -2507.5637997198924,
			"y": 2250.6249266178224,
			"width": 561.361083984375,
			"height": 140,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 774993121,
			"version": 441,
			"versionNonce": 1440484961,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "this step roughly translates to:\ngiven our current guess of the parameter theta and our data\nthe best estimate at which datapoints belong to which clusters (q)\nIS ACTUALLY just the likelihood of the data being sampled from that\nspecific parameter guess\n(This initial step just tells us to make our lower bound as close\nto the data likelihood as possible)",
			"rawText": "this step roughly translates to:\ngiven our current guess of the parameter theta and our data\nthe best estimate at which datapoints belong to which clusters (q)\nIS ACTUALLY just the likelihood of the data being sampled from that\nspecific parameter guess\n(This initial step just tells us to make our lower bound as close\nto the data likelihood as possible)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 134,
			"containerId": null,
			"originalText": "this step roughly translates to:\ngiven our current guess of the parameter theta and our data\nthe best estimate at which datapoints belong to which clusters (q)\nIS ACTUALLY just the likelihood of the data being sampled from that\nspecific parameter guess\n(This initial step just tells us to make our lower bound as close\nto the data likelihood as possible)",
			"lineHeight": 1.25
		},
		{
			"id": "45IvEXQJIFzLYVdqQLHcC",
			"type": "arrow",
			"x": -2434.631538543202,
			"y": 2216.8050474915835,
			"width": 536.4694267441978,
			"height": 471.150793947,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 239592289,
			"version": 265,
			"versionNonce": 276513839,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-155.26560255071627,
					-47.11507939469993
				],
				[
					-152.05321077380495,
					-432.60209262406374
				],
				[
					-490.42514460846814,
					-471.150793947
				],
				[
					-536.4694267441978,
					-414.3985392215661
				]
			],
			"lastCommittedPoint": [
				-536.4694267441978,
				-414.3985392215661
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "bIkofRHh",
				"focus": -0.2460465146840263,
				"gap": 8.180479808401742
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "dq0lxMRplJVKanWbRA3J7",
			"type": "line",
			"x": -3210.3261981291726,
			"y": 1977.550653943431,
			"width": 586.8062314660715,
			"height": 2.532976538702542,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1551764225,
			"version": 95,
			"versionNonce": 1101179425,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					586.8062314660715,
					-2.532976538702542
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "OHmwftEc",
			"type": "text",
			"x": -3373.266167756271,
			"y": 1910.8489384242657,
			"width": 140.12857491629464,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1343599951,
			"version": 225,
			"versionNonce": 516768879,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "Maximization step",
			"rawText": "Maximization step",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Maximization step",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 165,
			"versionNonce": 1927986689,
			"isDeleted": false,
			"id": "yvxAPGVaDFnOB2O560Jt0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3221.9029591122135,
			"y": 1852.7173103544044,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 586.8062314660715,
			"height": 2.532976538702542,
			"seed": 397619663,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					586.8062314660715,
					-2.532976538702542
				]
			]
		},
		{
			"id": "7O77ODi0kx5DNnsvFS4x2",
			"type": "line",
			"x": -2633.7335420232766,
			"y": 2050.8720480754446,
			"width": 582.0623341263054,
			"height": 4.032764439674338,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 527444143,
			"version": 179,
			"versionNonce": 346611343,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-582.0623341263054,
					4.032764439674338
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "uZ3ClSxP",
			"type": "text",
			"x": -3386.335516700141,
			"y": 2002.478874799354,
			"width": 135.40857805524553,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1385652033,
			"version": 67,
			"versionNonce": 231036385,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "Expectation step",
			"rawText": "Expectation step",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Expectation step",
			"lineHeight": 1.25
		},
		{
			"id": "PdZdEHCKBFlcKwAAAhI3z",
			"type": "line",
			"x": -2996.3151654785365,
			"y": 2095.0387610206008,
			"width": 264.8675099303514,
			"height": 21.5706494829642,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 898189295,
			"version": 64,
			"versionNonce": 474756271,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-188.61777222312912,
					21.5706494829642
				],
				[
					-264.8675099303514,
					12.039432269561075
				]
			],
			"lastCommittedPoint": [
				-264.8675099303514,
				12.039432269561075
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "3lx3Yxcd",
			"type": "text",
			"x": -3420.169527513575,
			"y": 2075.976326593795,
			"width": 162.46437072753906,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1806589999,
			"version": 50,
			"versionNonce": 492816079,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "So we are maximizing\nan expectation",
			"rawText": "So we are maximizing\nan expectation",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "So we are maximizing\nan expectation",
			"lineHeight": 1.25
		},
		{
			"id": "U5acBinT",
			"type": "text",
			"x": -2260.6215503803505,
			"y": 2768.702891239615,
			"width": 134.144287109375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 192535393,
			"version": 56,
			"versionNonce": 1048580513,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "Overall Objective",
			"rawText": "Overall Objective",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Overall Objective",
			"lineHeight": 1.25
		},
		{
			"id": "F_P5mthhqEUjl1jwieaWN",
			"type": "arrow",
			"x": -1800.2361657895535,
			"y": 2820.5867655890597,
			"width": 153.97794968222183,
			"height": 80.33632157333295,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 38032225,
			"version": 76,
			"versionNonce": 1987843311,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					39.331324103610996,
					39.33132410361077
				],
				[
					28.452447223888612,
					80.33632157333295
				],
				[
					-114.64662557861084,
					77.82581152416606
				]
			],
			"lastCommittedPoint": [
				-114.64662557861084,
				77.82581152416606
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Jtoktn8E",
			"type": "text",
			"x": -1800.6929850930958,
			"y": 2861.591763058782,
			"width": 191.71240234375,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 893745871,
			"version": 121,
			"versionNonce": 522821391,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "Explained\nat the end\nof the expectation step",
			"rawText": "Explained\nat the end\nof the expectation step",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "Explained\nat the end\nof the expectation step",
			"lineHeight": 1.25
		},
		{
			"id": "l3bltJIo9Gx9JspsOeEmt",
			"type": "arrow",
			"x": -2246.5552785098134,
			"y": 2888.055445032638,
			"width": 97.657901549509,
			"height": 81.38158462459069,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 253466177,
			"version": 68,
			"versionNonce": 2031017313,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-96.75366172034683,
					33.45687367899836
				],
				[
					-97.657901549509,
					81.38158462459069
				],
				[
					0,
					73.24342616213153
				]
			],
			"lastCommittedPoint": [
				0,
				73.24342616213153
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "MjysYgOn",
			"type": "text",
			"x": -2442.7898103027587,
			"y": 2928.7462373449334,
			"width": 72.3681640625,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 519678337,
			"version": 22,
			"versionNonce": 753830209,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "i.i.d data",
			"rawText": "i.i.d data",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "i.i.d data",
			"lineHeight": 1.25
		},
		{
			"id": "8TKrXSzI",
			"type": "text",
			"x": -1729.9498355916107,
			"y": 3477.5868675676993,
			"width": 172.5123748779297,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1513598479,
			"version": 58,
			"versionNonce": 1175086927,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "How to estimate best\nmean and covariance",
			"rawText": "How to estimate best\nmean and covariance",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "How to estimate best\nmean and covariance",
			"lineHeight": 1.25
		},
		{
			"id": "bKH35quZT3qGdzI3EIRU6",
			"type": "line",
			"x": -1267.2869524013222,
			"y": 3828.444148656772,
			"width": 173.29231634344592,
			"height": 163.92516410866483,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1435268495,
			"version": 29,
			"versionNonce": 1135458593,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-16.860874022605685,
					111.4691115938922
				],
				[
					-173.29231634344592,
					163.92516410866483
				]
			],
			"lastCommittedPoint": [
				-173.29231634344592,
				163.92516410866483
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "4yBpegot",
			"type": "text",
			"x": -1618.734586057499,
			"y": 4000.79974977674,
			"width": 264.5125427246094,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 77592847,
			"version": 73,
			"versionNonce": 1644078447,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767271,
			"link": null,
			"locked": false,
			"text": "Currently a known constant value",
			"rawText": "Currently a known constant value",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Currently a known constant value",
			"lineHeight": 1.25
		},
		{
			"id": "7I6RmZ6G",
			"type": "text",
			"x": -2184.0626836973133,
			"y": 3476.2392246290087,
			"width": 179.3123779296875,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 662684303,
			"version": 63,
			"versionNonce": 1052503297,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051767272,
			"link": null,
			"locked": false,
			"text": "How to estimate best\nPrior/Size of clusters?",
			"rawText": "How to estimate best\nPrior/Size of clusters?",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "How to estimate best\nPrior/Size of clusters?",
			"lineHeight": 1.25
		},
		{
			"id": "nhm3O7tN",
			"type": "text",
			"x": -2124.365458026219,
			"y": 3759.346208105921,
			"width": 82.960205078125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1335074991,
			"version": 40,
			"versionNonce": 123067087,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051780018,
			"link": null,
			"locked": false,
			"text": "Lagrangian",
			"rawText": "Lagrangian",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Lagrangian",
			"lineHeight": 1.25
		},
		{
			"id": "utXeBDWuc0QanKmwwPyXo",
			"type": "freedraw",
			"x": -2542.7682068886525,
			"y": 3780.257667662041,
			"width": 50.07911923025358,
			"height": 25.039559615126564,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 118202529,
			"version": 121,
			"versionNonce": 2138560207,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051772401,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.29115766994345904
				],
				[
					0,
					-0.8734730098299224
				],
				[
					-0.2911576699430043,
					-1.4557883497168405
				],
				[
					-0.5823153398864633,
					-2.329261359546763
				],
				[
					-0.5823153398864633,
					-3.4938920393201442
				],
				[
					-0.5823153398864633,
					-4.658522719093526
				],
				[
					0,
					-5.531995728923448
				],
				[
					0.29115766994345904,
					-5.823153398866907
				],
				[
					1.1646306797733814,
					-6.114311068809911
				],
				[
					1.7469460196602995,
					-6.114311068809911
				],
				[
					2.038103689603304,
					-5.823153398866907
				],
				[
					3.202734369376685,
					-5.531995728923448
				],
				[
					4.076207379207062,
					-5.240838058979989
				],
				[
					4.949680389036985,
					-4.949680389036985
				],
				[
					5.531995728923448,
					-4.367365049150067
				],
				[
					5.823153398866907,
					-3.4938920393201442
				],
				[
					5.240838058979989,
					-2.038103689603304
				],
				[
					4.076207379207062,
					-1.7469460196602995
				],
				[
					2.329261359546763,
					-1.7469460196602995
				],
				[
					1.1646306797733814,
					-2.329261359546763
				],
				[
					0.29115766994345904,
					-2.620419029490222
				],
				[
					-0.8734730098299224,
					-3.202734369376685
				],
				[
					-2.038103689603304,
					-4.658522719093526
				],
				[
					-2.620419029489767,
					-5.240838058979989
				],
				[
					-3.202734369376685,
					-6.9877840786402885
				],
				[
					-3.4938920393196895,
					-8.152414758413215
				],
				[
					-3.4938920393196895,
					-9.608203108130056
				],
				[
					0,
					-11.937464467676818
				],
				[
					2.620419029490222,
					-13.1020951474502
				],
				[
					4.949680389036985,
					-13.975568157280122
				],
				[
					6.6966264086968295,
					-13.975568157280122
				],
				[
					6.9877840786402885,
					-13.975568157280122
				],
				[
					7.570099418526752,
					-13.393252817393659
				],
				[
					7.570099418526752,
					-11.355149127790355
				],
				[
					6.40546873875337,
					-9.025887768243592
				],
				[
					4.076207379207062,
					-6.114311068809911
				],
				[
					1.1646306797733814,
					-3.202734369376685
				],
				[
					-1.4557883497163857,
					-1.1646306797733814
				],
				[
					-3.4938920393196895,
					-0.29115766994345904
				],
				[
					-4.076207379206608,
					-0.29115766994345904
				],
				[
					-4.94968038903653,
					-0.5823153398869181
				],
				[
					-6.114311068809911,
					-2.329261359546763
				],
				[
					-7.570099418526752,
					-3.7850497092636033
				],
				[
					-7.861257088469756,
					-4.658522719093526
				],
				[
					-8.443572428356674,
					-6.9877840786402885
				],
				[
					-9.025887768243138,
					-10.481676117959978
				],
				[
					-8.734730098299679,
					-12.519779807563282
				],
				[
					-7.861257088469756,
					-12.81093747750674
				],
				[
					-5.823153398866452,
					-13.393252817393659
				],
				[
					-4.94968038903653,
					-13.393252817393659
				],
				[
					-4.367365049150067,
					-13.393252817393659
				],
				[
					-4.367365049150067,
					-12.519779807563282
				],
				[
					-4.367365049150067,
					-11.355149127790355
				],
				[
					-6.987784078639834,
					-8.443572428356674
				],
				[
					-10.772833787903437,
					-5.531995728923448
				],
				[
					-14.557883497166586,
					-2.911576699433226
				],
				[
					-15.722514176939967,
					-2.038103689603304
				],
				[
					-15.722514176939967,
					-1.7469460196602995
				],
				[
					-15.431356506996508,
					-2.620419029490222
				],
				[
					-14.849041167110045,
					-3.7850497092636033
				],
				[
					-14.266725827223127,
					-4.658522719093526
				],
				[
					-12.228622137619823,
					-7.278941748583293
				],
				[
					-6.40546873875337,
					-10.481676117959978
				],
				[
					-3.7850497092631485,
					-11.063991457846896
				],
				[
					-1.7469460196598448,
					-11.355149127790355
				],
				[
					0.8734730098303771,
					-11.063991457846896
				],
				[
					2.620419029490222,
					-9.608203108130056
				],
				[
					4.949680389036985,
					-7.278941748583293
				],
				[
					6.114311068810366,
					-4.367365049150067
				],
				[
					6.114311068810366,
					-2.620419029490222
				],
				[
					6.114311068810366,
					-1.1646306797733814
				],
				[
					6.114311068810366,
					1.4557883497163857
				],
				[
					5.823153398866907,
					3.4938920393201442
				],
				[
					4.658522719093526,
					4.658522719093071
				],
				[
					3.7850497092636033,
					5.531995728923448
				],
				[
					3.7850497092636033,
					5.823153398866452
				],
				[
					4.658522719093526,
					3.202734369376685
				],
				[
					5.823153398866907,
					0.29115766994345904
				],
				[
					8.15241475841367,
					-4.076207379206608
				],
				[
					9.317045438187051,
					-7.278941748583293
				],
				[
					10.772833787903437,
					-8.734730098300133
				],
				[
					12.519779807563737,
					-10.190518448016974
				],
				[
					13.684410487337118,
					-10.190518448016974
				],
				[
					14.55788349716704,
					-9.608203108130056
				],
				[
					16.013671846883426,
					-7.861257088470211
				],
				[
					17.469460196600266,
					-4.949680389036985
				],
				[
					18.05177553648673,
					-2.620419029490222
				],
				[
					18.05177553648673,
					-0.8734730098299224
				],
				[
					18.05177553648673,
					0.29115766994345904
				],
				[
					18.05177553648673,
					1.7469460196598448
				],
				[
					17.469460196600266,
					2.329261359546763
				],
				[
					17.469460196600266,
					2.911576699433226
				],
				[
					17.178302526656807,
					3.202734369376685
				],
				[
					17.178302526656807,
					1.4557883497163857
				],
				[
					17.178302526656807,
					-2.329261359546763
				],
				[
					17.178302526656807,
					-7.861257088470211
				],
				[
					18.634090876373648,
					-13.975568157280122
				],
				[
					20.381036896033493,
					-16.88714485671335
				],
				[
					21.836825245750333,
					-18.34293320643019
				],
				[
					23.001455925523715,
					-19.21640621626011
				],
				[
					24.166086605297096,
					-18.925248546316652
				],
				[
					25.03955961512702,
					-18.05177553648673
				],
				[
					28.824609324390167,
					-12.81093747750674
				],
				[
					31.15387068393693,
					-9.025887768243592
				],
				[
					33.19197437354023,
					-5.531995728923448
				],
				[
					34.356605053313615,
					-2.620419029490222
				],
				[
					34.356605053313615,
					-0.8734730098299224
				],
				[
					34.356605053313615,
					1.4557883497163857
				],
				[
					34.356605053313615,
					3.7850497092631485
				],
				[
					32.90081670359723,
					4.94968038903653
				],
				[
					31.44502835388039,
					5.240838058979989
				],
				[
					30.280397674107007,
					5.240838058979989
				],
				[
					29.69808233422009,
					5.240838058979989
				],
				[
					29.115766994333626,
					5.240838058979989
				],
				[
					28.824609324390167,
					4.076207379206608
				],
				[
					28.824609324390167,
					1.4557883497163857
				],
				[
					28.824609324390167,
					-0.5823153398869181
				],
				[
					29.115766994333626,
					-1.4557883497168405
				],
				[
					29.115766994333626,
					-1.4557883497168405
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				29.115766994333626,
				-1.4557883497168405
			]
		},
		{
			"id": "_dPQNhTLCbo3AwLOQF84F",
			"type": "freedraw",
			"x": -2493.8537183381723,
			"y": 3770.9406222238545,
			"width": 14.557883497166586,
			"height": 12.228622137620277,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 306324865,
			"version": 30,
			"versionNonce": 1196683919,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709051773279,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.2911576699430043,
					5.531995728922993
				],
				[
					-0.2911576699430043,
					5.823153398866452
				],
				[
					-1.4557883497163857,
					8.734730098299679
				],
				[
					-2.038103689603304,
					10.190518448016519
				],
				[
					-2.911576699433226,
					11.063991457846441
				],
				[
					-2.911576699433226,
					11.3551491277899
				],
				[
					-3.7850497092631485,
					11.3551491277899
				],
				[
					-4.658522719093071,
					11.063991457846441
				],
				[
					-4.94968038903653,
					11.063991457846441
				],
				[
					-4.94968038903653,
					10.772833787902982
				],
				[
					-4.94968038903653,
					10.190518448016519
				],
				[
					-5.531995728922993,
					9.025887768243138
				],
				[
					-5.823153398866452,
					7.861257088469756
				],
				[
					-6.40546873875337,
					6.40546873875337
				],
				[
					-7.278941748583293,
					4.94968038903653
				],
				[
					-7.861257088469756,
					3.202734369376685
				],
				[
					-8.152414758413215,
					1.7469460196598448
				],
				[
					-8.443572428356674,
					0.5823153398864633
				],
				[
					-8.734730098299679,
					-0.29115766994345904
				],
				[
					-9.317045438186597,
					-0.5823153398869181
				],
				[
					-9.317045438186597,
					-0.8734730098303771
				],
				[
					-9.89936077807306,
					-0.29115766994345904
				],
				[
					-11.937464467676364,
					0.8734730098299224
				],
				[
					-13.102095147449745,
					1.4557883497163857
				],
				[
					-13.393252817393204,
					1.4557883497163857
				],
				[
					-13.975568157279668,
					1.7469460196598448
				],
				[
					-14.557883497166586,
					1.7469460196598448
				],
				[
					-14.557883497166586,
					1.7469460196598448
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-14.557883497166586,
				1.7469460196598448
			]
		},
		{
			"type": "image",
			"version": 314,
			"versionNonce": 1791392463,
			"isDeleted": false,
			"id": "-zIqCLGqifF2wG6WyrCLo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2504.7304355226274,
			"y": 3925.5055440771216,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 276.0390572237623,
			"height": 73.11304758899651,
			"seed": 1045041327,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709052422319,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "32fd3e04847271eb037daae8869d30b53223f72e",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "wsnG3W2CM_h48yHe4UqD0",
			"type": "ellipse",
			"x": -2372.7719524846175,
			"y": 3913.424553189058,
			"width": 162.80949239609618,
			"height": 98.12423952492009,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 25703393,
			"version": 63,
			"versionNonce": 1192177967,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "VdmWkeg4tZd6wcKCPpIJu",
					"type": "arrow"
				}
			],
			"updated": 1709052538004,
			"link": null,
			"locked": false
		},
		{
			"id": "VdmWkeg4tZd6wcKCPpIJu",
			"type": "arrow",
			"x": -2211.6070004157546,
			"y": 3936.996297879402,
			"width": 96.47969919768639,
			"height": 3.8372607635442364,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 359060481,
			"version": 22,
			"versionNonce": 389114639,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709052538004,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					96.47969919768639,
					-3.8372607635442364
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "wsnG3W2CM_h48yHe4UqD0",
				"focus": -0.4539073311303266,
				"gap": 7.641922059857606
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "tPc4o9sR",
			"type": "text",
			"x": -2096.186776712507,
			"y": 3906.472733298136,
			"width": 38.864166259765625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 151646575,
			"version": 17,
			"versionNonce": 367112865,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709052547904,
			"link": null,
			"locked": false,
			"text": "= 1",
			"rawText": "= 1",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "= 1",
			"lineHeight": 1.25
		},
		{
			"id": "mvuNSUcaviL5VM7_0TEXM",
			"type": "line",
			"x": -2433.071764483172,
			"y": 4058.692282094665,
			"width": 100.31695996123108,
			"height": 3.8372607635442364,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1948366415,
			"version": 42,
			"versionNonce": 1351099681,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709052558865,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					100.31695996123108,
					3.8372607635442364
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "qRgObuCW",
			"type": "text",
			"x": -2447.4202179792464,
			"y": 4078.4513815492764,
			"width": 124.08024597167969,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 493410561,
			"version": 97,
			"versionNonce": 1223541985,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709052578956,
			"link": null,
			"locked": false,
			"text": "Maximal lambda\nvalue possible\nfor our solution",
			"rawText": "Maximal lambda\nvalue possible\nfor our solution",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "Maximal lambda\nvalue possible\nfor our solution",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 357,
			"versionNonce": 1148589103,
			"isDeleted": true,
			"id": "zW6RfMmX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2510.9387732414984,
			"y": 4237.688640740628,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 287.01174495787797,
			"height": 70.31787751468009,
			"seed": 21382,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709052554732,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0d56c735576ac0954285e5706500e800c778501d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "O-2i3ZNTsASF_p8fVI60z",
			"type": "arrow",
			"x": -2217.0687589341055,
			"y": 3957.7951520833603,
			"width": 83.03948484507873,
			"height": 2.084181509037535,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2129397519,
			"version": 228,
			"versionNonce": 531758529,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1709052422319,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					83.03948484507873,
					2.084181509037535
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "-zIqCLGqifF2wG6WyrCLo",
				"gap": 11.622619364759657,
				"focus": -0.20035759553528756
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "image",
			"version": 438,
			"versionNonce": 804578287,
			"isDeleted": true,
			"id": "fvLTsmaoyM8i79F7Brsa_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2129.011930447543,
			"y": 3939.383993761712,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 143.62560428734878,
			"height": 35.52031073773142,
			"seed": 1394024193,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "O-2i3ZNTsASF_p8fVI60z",
					"type": "arrow"
				}
			],
			"updated": 1709052406580,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8ecee6de3150bdfcf291cbe5a623500fe1ea964b",
			"scale": [
				1,
				1
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 2,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 2974.074662870283,
		"scrollY": -3475.258314623147,
		"zoom": {
			"value": 1.1249465115120567
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