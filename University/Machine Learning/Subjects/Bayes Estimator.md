---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Bayes estimator ^rNPaD7SA

Previously on dragon ball Z, I mean maximum likelihood
 ^QcLn5o2I

To try and estimate our data distribution we assumed its a Gaussian
distribution with a fixed variance and we found a way to estimate the 
best mean to represent our data! ^CpM7A9Az

This is cool and all but another approach to this solution is
to build a distribution of all possible estimates of this value
using bayes theorem to convert the posterior!
that way we have a plethora of choices, some of which are better than others ^rAbF4cVa

a distribution describing
thetas possible for our
dataset ^3ch9xrW3

an input from the user describing
out initial assumptions about
what theta possibilities 
might look like ^FUigDZj4

The probability that the
representation of the data given theta
is our D ^q82E39bD

Distribution of our
data ^l9NSC5zY

Lets build a classifier ^UEJMCNTJ

using terms we are
more familiar with ^zEu5EHHG

prediction of class wi
given x from assumptions
we made given our D ^NHXCoWaE

Prior knowledge of 
classes does not depend
on the Data in our dataset
it is something thats given as a
constant in the wild ^ZdfV7o1h

How do we compute p ( x | wi, D )? ^1QjSz5jz

data generating
distribution given
a certain dataset
and a class ^GATNtDzy

integral over the whole
parameter space
that we have inferred
in previous steps so we are
taking into account all possible
parameter values with their respective
probability given our dataset
and seeing how it influences
the data we generate

 ^xvg4sFBW

theta depends on D ^wIyZpmj6

Theta is built off of Di
in order to describe the data
generating distribution
thus there is no need to specify
Previously generated data
because all data is generated
i.i.d which means there are no
connections between the old and the new
data other than the distribution
describing their generation ^EoYcdzIm

This approach is less sensitive to data
and takes into account prior knowledge ^ysMbKG12

Lets Compare Bayes vs Likelihood! ^BIOTDksK

Likelihood estimation ^jpXCsCIT

%%***>>>text element-link:[[Maximum Likelihood]]<<<***%%explained previously in maximum likelihood chapter ^bmCJQpgr

V.S ^DOIozpXi

Bayes estimation ^Eu28sLRb

normalizing term used to collect
garbage constant terms that
we dont care about
it depends on D but is independnt of mu ^w75pEBu4

our prior assumption about our
theta is that its drawn from a normal distribution ^59tyyOLI

Which results in a Gaussian distribution
 generated from mu_n and sigma_n ^nGAM0KmZ

if we dont have a lot of data, this term
is pulled towards our prior knowledge!
if we do have a good bit of knowledge this is
pulled toward our maximum likelihood empirical mean ^smIVaSPI

confidence estimation!
if we increase the amount of datapoints this will
go to 0 i.e we are very confident in our mean ^MsM9CisL

So the goal is to generate a distribution of parameters
from which we can infer our dataset, and to do that we use
our knowledge of the most likely values + a restriction of parameter values
(prior knowledge of theta) over the entire space, once we have this
distribution we can continue forward with our prediction ^hUb1WH7O

from previously ^pg1g8fEo

As opposed to ML classifier where we use the maximum likely theta in order to define
our class posteriors, here we condition our class posterior to depend on the actual dataset
thus the dataset has a huge effect on what we pick, and the bigger the dataset the more accurate
we get ^snAVycE1

Lets take an example ^qnSxIr7b

Given Two possible classes w1 and w2 such that they're equally to occur in the wild P(w1) = P(w2) = 0.5
it is known that the data generation distribution is of the shape 
Our Current dataset contains {  ,   ,   ,    ,   ,   } such that the green points belong to class 1
and the red points belong to class 2
This time we use Bayes estimation to learn about our data generating distribution ^uX3vU2MG

Example ^NA5TrwTO

0         2 ^jMH0O6jZ

1   0      2   0 ^42sjMU0R

we have to define this
as our prior knowledge
to be uniformly generated
from ^W1QC3a7E

this always samples a value
between 0 and 1 thus we set
the prior to 1 (not sure tbh) ^NcmDhSIK

This integral goes
between 0 and 1 ^mxedpwY6

0.5 ^8L8x3GGC

1 ^apw0yQtq

1 ^Xjwpv203

Prior of theta ^Y9iXdeOI

Posterior of theta ^HE90N7H2

our observations shrunk our
beliefs of theta into something
that reflects the dataset ^OgBsjHUM

We can do the same with the second
class, its the exact same steps
so its redundant to mention it ^7aQ2MFy9

And the classifier ^DnEiRTqi

Denominator is constant thus not needed ^nkC14cdd

This is just a really long way of proving that the posterior of a estimating the mean of a gaussian distribution
using bayes estimator is also a gaussian distribution classified by this mean and variance ^wuckAz3l

Consider the case where μ is the only unknown parameter. We assume that whatever prior
knowledge we might have about μ can be expressed by ^yPSFRWeL

where both μ0 and σ0 are known. Roughly speaking, μ0 represents our best a priori guess for μ, and σ0^2
measures our uncertainty about this guess. The assumption that the prior distribution for
μ is normal will simplify the subsequent mathematics. ^8QlTBw9H

Imagine that a value is drawn for μ from a population governed by the probability
law p(μ). Once this value is drawn, it becomes the true value of μ and completely
determines the density for x. Suppose now that n samples x1, ..., xn are independently
drawn from the resulting population. ^78dVLU9C

This equation shows how the observation of a set of training
samples affects our ideas about the true value of μ ^rycvpQk7

From this result we can also show that
the variance of the posterior is contained both by
the uncertainty of the data mean and of the prior

which means we are as confident with our posterior
mean as we are with either the confidence of the prior
or the confidence of the empirical ^CX6Gxddc

We can also show that our posterior
mean always lies between our prior mean
and our empirical mean, the more datapoints
we have the closer it gets to the empirical ^9CvkK6Hm


# Embedded files
4c5aaf7d4b581b380debc6ba9ccdf643071a4cc5: $$(1 - \theta_i)^k \theta_i$$
742c3c9dfb8b1ffcb0d8dcf791fe597bb6e7da30: $$p(\theta_1 | D_1) = \frac{p(D_1|\theta_1)p(\theta_1)}{\int p(D_1 | \theta_1) p(\theta_1) d\theta_1 }$$
5ba0b960246bd0516aad17f188c68bd1f54386a4: $$P(D_1 | \theta_1) = \Pi_{x \in D_1} P(x=k | \theta_1) =\Pi_{x \in D_1} (1- \theta_1)^k \theta_1$$
63708e6185b9f9dbb2c1e094191bded40d6debe8: $$\color{green} \theta_1 ^2 (1-\theta_1)^2$$
9cb4c72138506736d31e8efcb309fd18a08872e6: $$p(\theta_1) \in \mathcal{U}(0,1)$$
7b12506547c08103493d80a44463c92c81f732cb: $$p(\theta_2) \in \mathcal{U}(0,1)$$
8eb8769ad90c1073aad6544ad85729a31fe047ab: $$\color{green} \frac{ \theta_1 ^2 (1-\theta_1)^2 \cdot 1}{\int  \theta_1 ^2 (1-\theta_1)^2 \cdot 1 d\theta}$$
431b535372ab29a4fb615e412d4a6c36187a5c27: $$\color{green} \frac{ \theta_1 ^4 -2\theta_1^3 + \theta_1^2 }{ |_0^1 \frac{\theta_1 ^5}{5} - \frac{2\theta_1^4}{4} + \frac{\theta_1^3}{3}} = \frac{ \theta_1 ^4 -2\theta_1^3 + \theta_1^2 }{ \frac{1 ^5}{5} - \frac{2^4}{4} + \frac{1^3}{3} -\frac{0 ^5}{5} - \frac{0^4}{4} + \frac{0^3}{3}  } =\frac{ \theta_1 ^4 -2\theta_1^3 + \theta_1^2 }{\frac{2}{60}} = 30 (\theta_1 ^4 -2\theta_1^3 + \theta_1^2)$$
3c0652392c8676b475ec5da08967b0cdad56f6a8: $$p(\theta_2 | D_2) = 280 \cdot \theta_2^4 \cdot(1-\theta_2)^3$$
d8da25b94953ee9528d4d58eb3b799227fc3541b: $$\arg\max P(w_i | x,D) = \arg\max p(x ==k | w_i,D) P(w_i)$$
aba446d087156b0bb2ffd209ab1841624165e7b6: $$\arg\max P( w_i) \int p( x | \theta_i ) p( \theta_i | D) $$
5cf1bd5665aeda9739d51496b7a4d545825c03a7: $$\arg\max \left[ 0.5 \int (1 - \theta_1)^k \theta_1 \cdot 30 (\theta_1 ^4 -2\theta_1^3 + \theta_1^2), 0.5 \int (1 - \theta_i)^k \cdot 280 \cdot \theta_2^4 \cdot(1-\theta_2)^3 \right]$$
cbe60153323b09ab985e4f2563e9ce7863b19c05: $$p(x|μ) ∼ N(μ, σ^2)$$
26b978377f0a453705ac8f5e1b3de7f891c00e96: $$\sigma_n^2  = (\frac{n}{\sigma^2} + \frac{1}{\sigma_0^2})^{-1}$$
7154dcc7583e12821a16a787f840f4278e7d508d: $$\frac{n}{\sigma^2} + \frac{1}{\sigma_0^2} \geq max [ \frac{n}{\sigma^2} + \frac{1}{\sigma_0^2} ]$$
e3c161b0345a857204f48519b14ac7ef59193c5f: $$\sigma_n^2  \geq \frac{1}{max[\frac{n}{\sigma^2} + \frac{1}{\sigma_0^2}]}$$
eedeb20788af7e8a7c08bdab1f9ab1132e35296f: $$\sigma_n^2  \leq min[\frac{n}{\sigma^2} + \frac{1}{\sigma_0^2}]$$
110ce5ad4e030538e30d955ef0b56f8f9f358002: $$\hat{\mu}$$
2294ea9ef22aca465f0b82d6c5616929728a14c0: $$\mu_n$$
6fb39a57a395516d0234ce5029b7602e59c4baef: $$\mu_0$$
a812e44af232c6754da9ce2aed4f32239ee30f9a: $$ min(\hat{μ_n}, μ_0) ≤ μ_n ≤ max(\hat{μ_n}, μ_0)$$
6c2a77b2bb531eac96e180150e7235497c6a3f4d: $$\frac{1}{\sigma_n^2}\mu_n = \frac{n}{\sigma^2}\hat{\mu_n} + \frac{1}{\sigma_0^2} \mu_0$$
aef1be19afe0a3e6634ac521d9589f10038c9d90: $$\left[ \frac{n}{\sigma^2} + \frac{1}{\sigma_0^2} \right] min(\hat{\mu_n},\mu_0) \leq \frac{n}{\sigma^2}\hat{\mu_n} + \frac{1}{\sigma_0^2} \mu_0 \leq \left[ \frac{n}{\sigma^2} + \frac{1}{\sigma_0^2} \right] max(\hat{\mu_n},\mu_0) $$
cfae5783c2c3167c79389b075b2007671e56cfa8: $$\left[ \frac{n}{\sigma^2} + \frac{1}{\sigma_0^2} \right] min(\hat{\mu_n},\mu_0) \leq \frac{1}{\sigma_n^2} \mu_n \leq \left[ \frac{n}{\sigma^2} + \frac{1}{\sigma_0^2} \right] max(\hat{\mu_n},\mu_0) $$
0175b941b7d8f8988fa4f79ce7f144474eecf3c1: $$ min(\hat{μ_n}, μ_0) ≤ μ_n ≤ max(\hat{μ_n}, μ_0)$$
b77dce9e6901e7ba2f328a64fb468bbcc0bd3b13: [[Pasted Image 20231225183608_133.png]]
93abc68cae88a4fb584934c37d3f2fcd645099bf: [[Pasted Image 20231225184209_198.png]]
97da2ba2e10d678b2ac16cede6c88c489c0682cb: [[Pasted Image 20231225184902_322.png]]
d4a57a95be2d776438226bb7ac16751c75f73057: [[Pasted Image 20231225185205_398.png]]
8a7aff35b61642903193ab222fb346e1e8b7f869: [[Pasted Image 20231225185220_419.png]]
0d8f230f10576aaca3a28d10d3cbb34823602946: [[Pasted Image 20231225190541_199.png]]
d46c2c93e8e960ca296955cf8af006215edc51df: [[Pasted Image 20231225190633_215.png]]
e678ac316e97f62f217cc986f18948756109e8ff: [[Pasted Image 20231225190826_245.png]]
10deafbef1f6ee62a23d80138e3eda7f3415594d: [[Pasted Image 20231225190930_287.png]]
405f337df2b5eed7ba4f9cce8eac77eaa6bc4425: [[Pasted Image 20231225191000_300.png]]
a2a744a4e059840ffe773aa4e08d23d34c76fbce: [[Pasted Image 20231225191313_318.png]]
5b34fc25f502e3abbe7179d18950ea1b3c362d5a: [[Pasted Image 20240223200839_891.png]]
34f2ab641d383e210d45d15dc2e8778163181f82: [[Pasted Image 20231225191015_301.png]]
223448c7d79fcd6d722a97952a16ad23923f2026: [[Pasted Image 20240223202017_964.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.22",
	"elements": [
		{
			"id": "k9O2YgsMVtTG_TLfP2BKv",
			"type": "image",
			"x": -321.40080814221847,
			"y": 2566.4314251618603,
			"width": 239.00000000000003,
			"height": 46,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 71648598,
			"version": 172,
			"versionNonce": 1673621514,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "223448c7d79fcd6d722a97952a16ad23923f2026",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "v0H6RMk3lbNvFXgcDDpiH",
			"type": "rectangle",
			"x": -2594.24012733674,
			"y": 1287.4308700182219,
			"width": 2265.9942329156015,
			"height": 1672.3225717221324,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1182519114,
			"version": 1030,
			"versionNonce": 921362122,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 326,
			"versionNonce": 99823562,
			"isDeleted": false,
			"id": "VeD11G3O5E4EwZa-TST4D",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 527.9560609108746,
			"y": 1158.478552201034,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 218.30595708652962,
			"height": 67.3870478466458,
			"seed": 1075667670,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "93abc68cae88a4fb584934c37d3f2fcd645099bf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 368,
			"versionNonce": 1777338838,
			"isDeleted": false,
			"id": "JWLlktAe308g-IQYaBUOE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1008.0959113679517,
			"y": 795.7820703959761,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 435.77563218475956,
			"height": 105.35235063807374,
			"seed": 773826192,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d4a57a95be2d776438226bb7ac16751c75f73057",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 680,
			"versionNonce": 678983050,
			"isDeleted": false,
			"id": "ehG2POBTfTcoLtDdw3LUr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1530.5982051728965,
			"y": 1889.6997966279123,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 1171.6697409356,
			"height": 151.2271409812228,
			"seed": 1210932848,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "RZSGIUIYR2x9EM_XC4-5_",
					"type": "arrow"
				}
			],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e678ac316e97f62f217cc986f18948756109e8ff",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 212,
			"versionNonce": 977035030,
			"isDeleted": false,
			"id": "insTve6I4wAQgylYtXJ4Z",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -70.79840783232557,
			"y": 95.47592839233477,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 218.30595708652962,
			"height": 67.3870478466458,
			"seed": 1711409808,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "R5kyLTDcvMZzlDouMDyEK",
					"type": "arrow"
				}
			],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "93abc68cae88a4fb584934c37d3f2fcd645099bf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 98,
			"versionNonce": 1569539402,
			"isDeleted": false,
			"id": "62ExPX4-b29jjfWX9wGka",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -199,
			"y": -418.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 380,
			"height": 155,
			"seed": 381727856,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "rNPaD7SA"
				}
			],
			"updated": 1708716338019,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 53,
			"versionNonce": 13372502,
			"isDeleted": false,
			"id": "rNPaD7SA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -123.314758335112,
			"y": -358.0585880419574,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 228.92893981933594,
			"height": 35,
			"seed": 1623915152,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Bayes estimator",
			"rawText": "Bayes estimator",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "62ExPX4-b29jjfWX9wGka",
			"originalText": "Bayes estimator",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 155,
			"versionNonce": 1258949642,
			"isDeleted": false,
			"id": "QcLn5o2I",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -285,
			"y": -254.7578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 533.679443359375,
			"height": 50,
			"seed": 599508112,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Previously on dragon ball Z, I mean maximum likelihood\n",
			"rawText": "Previously on dragon ball Z, I mean maximum likelihood\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Previously on dragon ball Z, I mean maximum likelihood\n",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 280,
			"versionNonce": 1265897878,
			"isDeleted": false,
			"id": "CpM7A9Az",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -300,
			"y": -223.7578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 572.9771118164062,
			"height": 60,
			"seed": 54582416,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "To try and estimate our data distribution we assumed its a Gaussian\ndistribution with a fixed variance and we found a way to estimate the \nbest mean to represent our data!",
			"rawText": "To try and estimate our data distribution we assumed its a Gaussian\ndistribution with a fixed variance and we found a way to estimate the \nbest mean to represent our data!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "To try and estimate our data distribution we assumed its a Gaussian\ndistribution with a fixed variance and we found a way to estimate the \nbest mean to represent our data!",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 313,
			"versionNonce": 1656748746,
			"isDeleted": false,
			"id": "rAbF4cVa",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -345.224609375,
			"y": -160.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 632.44921875,
			"height": 80,
			"seed": 1981259888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "sJYjvCv9yw_y9D8oHzsCl",
					"type": "arrow"
				}
			],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is cool and all but another approach to this solution is\nto build a distribution of all possible estimates of this value\nusing bayes theorem to convert the posterior!\nthat way we have a plethora of choices, some of which are better than others",
			"rawText": "This is cool and all but another approach to this solution is\nto build a distribution of all possible estimates of this value\nusing bayes theorem to convert the posterior!\nthat way we have a plethora of choices, some of which are better than others",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is cool and all but another approach to this solution is\nto build a distribution of all possible estimates of this value\nusing bayes theorem to convert the posterior!\nthat way we have a plethora of choices, some of which are better than others",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 437,
			"versionNonce": 627666646,
			"isDeleted": false,
			"id": "sJYjvCv9yw_y9D8oHzsCl",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -50.23617180781886,
			"y": -65.25781250000001,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0.5549334908562855,
			"height": 141.45848441075475,
			"seed": 914284144,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rAbF4cVa",
				"focus": 0.0664400673723869,
				"gap": 14.999999999999986
			},
			"endBinding": {
				"elementId": "B1QPaPmmxQRE08-OQUyBT",
				"focus": 1.0620671482366832,
				"gap": 9.82618661434374
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
					-0.5549334908562855,
					141.45848441075475
				]
			]
		},
		{
			"type": "image",
			"version": 220,
			"versionNonce": 1397363082,
			"isDeleted": false,
			"id": "B1QPaPmmxQRE08-OQUyBT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -325.3798456096061,
			"y": 86.02685852509848,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 266,
			"height": 73,
			"seed": 63983728,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "sJYjvCv9yw_y9D8oHzsCl",
					"type": "arrow"
				}
			],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b77dce9e6901e7ba2f328a64fb468bbcc0bd3b13",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 139,
			"versionNonce": 1799431190,
			"isDeleted": false,
			"id": "SKFZcz1fFdzTGzvNaqTob",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -299.89192875761194,
			"y": 158.17100746962052,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 28.566072833038334,
			"height": 40.90142246548669,
			"seed": 2106155120,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-28.566072833038334,
					40.90142246548669
				]
			]
		},
		{
			"type": "text",
			"version": 178,
			"versionNonce": 1071861834,
			"isDeleted": false,
			"id": "3ch9xrW3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -421.2422194251229,
			"y": 199.0724299351072,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 185.5684356689453,
			"height": 60,
			"seed": 85556848,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "a distribution describing\nthetas possible for our\ndataset",
			"rawText": "a distribution describing\nthetas possible for our\ndataset",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a distribution describing\nthetas possible for our\ndataset",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 147,
			"versionNonce": 519057750,
			"isDeleted": false,
			"id": "D9x6PdDhrd3kK_serdVp0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 100.8875269183061,
			"y": 111.17351560253417,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 83.75053171504408,
			"height": 9.738433920353941,
			"seed": 145822352,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					83.75053171504408,
					-9.738433920353941
				]
			]
		},
		{
			"type": "text",
			"version": 250,
			"versionNonce": 744929034,
			"isDeleted": false,
			"id": "FUigDZj4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 165.67192187811986,
			"y": 55.98905672052837,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 259.96856689453125,
			"height": 80,
			"seed": 1719116944,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "an input from the user describing\nout initial assumptions about\nwhat theta possibilities \nmight look like",
			"rawText": "an input from the user describing\nout initial assumptions about\nwhat theta possibilities \nmight look like",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "an input from the user describing\nout initial assumptions about\nwhat theta possibilities \nmight look like",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "line",
			"version": 156,
			"versionNonce": 1003198102,
			"isDeleted": false,
			"id": "d4h9BHEvFEpLaNKRsy3fu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 32.51906212990514,
			"y": 93.26874373772802,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 411.9767313205824,
			"height": 115.68401051408904,
			"seed": 1804976784,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					244.94318552728032,
					-115.68401051408904
				],
				[
					411.9767313205824,
					-93.84570240683755
				]
			]
		},
		{
			"type": "text",
			"version": 185,
			"versionNonce": 1766802890,
			"isDeleted": false,
			"id": "q82E39bD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 350.8299177332151,
			"y": 0.01326587432973092,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 316.0007019042969,
			"height": 60,
			"seed": 1427766416,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The probability that the\nrepresentation of the data given theta\nis our D",
			"rawText": "The probability that the\nrepresentation of the data given theta\nis our D",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The probability that the\nrepresentation of the data given theta\nis our D",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 60,
			"versionNonce": 176706518,
			"isDeleted": false,
			"id": "SIzqU_eMQxek1zGuqfyHF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -135.04930483287342,
			"y": 177.0224153796136,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 15.756096690943878,
			"height": 56.914879883613565,
			"seed": 578599024,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					15.756096690943878,
					56.914879883613565
				]
			]
		},
		{
			"type": "text",
			"version": 142,
			"versionNonce": 2142764170,
			"isDeleted": false,
			"id": "l9NSC5zY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -194.01114962377386,
			"y": 236.89373843936482,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 147.66432189941406,
			"height": 40,
			"seed": 745516656,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Distribution of our\ndata",
			"rawText": "Distribution of our\ndata",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Distribution of our\ndata",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 319,
			"versionNonce": 1966827798,
			"isDeleted": false,
			"id": "34q2jIonOU6ZDm_ulnZ8h",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -59.16591979806043,
			"y": 461.9018452575551,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.1619734022054473,
			"height": 68.90989950754647,
			"seed": 1190425200,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "hnQeSJlRHEg4tjJWAc7wA",
				"gap": 22.5925579095466,
				"focus": -0.02994906830078399
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
					-1.1619734022054473,
					68.90989950754647
				]
			]
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 492559178,
			"isDeleted": false,
			"id": "UEJMCNTJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -43.11149614179146,
			"y": 507.2758926289305,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 175.47238159179688,
			"height": 20,
			"seed": 1930328688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Lets build a classifier",
			"rawText": "Lets build a classifier",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets build a classifier",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 84,
			"versionNonce": 1532614230,
			"isDeleted": false,
			"id": "R5kyLTDcvMZzlDouMDyEK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -108.05854436785194,
			"y": 197.76727552396187,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 145.988454244372,
			"height": 38.43953697190747,
			"seed": 1788668528,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "insTve6I4wAQgylYtXJ4Z",
				"focus": -0.1973164410949768,
				"gap": 4.234455956331701
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
					118.99899211516038,
					7.769693643257881
				],
				[
					145.988454244372,
					-30.66984332864959
				]
			]
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 9822730,
			"isDeleted": false,
			"id": "zEu5EHHG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 48.05051736837811,
			"y": 174.4581945941882,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 149.0563201904297,
			"height": 40,
			"seed": 1448512112,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "using terms we are\nmore familiar with",
			"rawText": "using terms we are\nmore familiar with",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "using terms we are\nmore familiar with",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 283,
			"versionNonce": 1706597270,
			"isDeleted": false,
			"id": "hnQeSJlRHEg4tjJWAc7wA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -313.45600743204716,
			"y": 553.4043026746481,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 517.4009457478236,
			"height": 219.4163269930585,
			"seed": 786866832,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "34q2jIonOU6ZDm_ulnZ8h",
					"type": "arrow"
				},
				{
					"id": "eBYmyMI_B44RYDCX-6b_q",
					"type": "arrow"
				}
			],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "97da2ba2e10d678b2ac16cede6c88c489c0682cb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 169,
			"versionNonce": 1684082890,
			"isDeleted": false,
			"id": "zk-L3zCc7PAUCzFxnrgn4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -236.53860557406585,
			"y": 591.7177470265199,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 35.55016499970304,
			"height": 30.989346091115863,
			"seed": 1057860208,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-35.55016499970304,
					-30.989346091115863
				]
			]
		},
		{
			"type": "text",
			"version": 192,
			"versionNonce": 1519171798,
			"isDeleted": false,
			"id": "NHXCoWaE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -427.8674765568194,
			"y": 500.0929013688468,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 195.472412109375,
			"height": 60,
			"seed": 1948114064,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "prediction of class wi\ngiven x from assumptions\nwe made given our D",
			"rawText": "prediction of class wi\ngiven x from assumptions\nwe made given our D",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "prediction of class wi\ngiven x from assumptions\nwe made given our D",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 478,
			"versionNonce": 1817733002,
			"isDeleted": false,
			"id": "qm2xBeS-gb1bwCk0R_2Zw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 179.2251389958491,
			"y": 596.4876195979032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 75.76033947150188,
			"height": 81.51703244571627,
			"seed": 656972432,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
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
					56.468126191340275,
					37.26990930847728
				],
				[
					-19.292213280161604,
					81.51703244571627
				]
			]
		},
		{
			"type": "text",
			"version": 473,
			"versionNonce": 1902849558,
			"isDeleted": false,
			"id": "ZdfV7o1h",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 219.1167851038366,
			"y": 603.5135236246524,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 256.59259033203125,
			"height": 100,
			"seed": 85746288,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Prior knowledge of \nclasses does not depend\non the Data in our dataset\nit is something thats given as a\nconstant in the wild",
			"rawText": "Prior knowledge of \nclasses does not depend\non the Data in our dataset\nit is something thats given as a\nconstant in the wild",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Prior knowledge of \nclasses does not depend\non the Data in our dataset\nit is something thats given as a\nconstant in the wild",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 868,
			"versionNonce": 280421962,
			"isDeleted": false,
			"id": "rhTVjvX-WDdWk3oO60En3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -191.52307568899386,
			"y": 850.6176815006435,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 407.7982639884633,
			"height": 110.76765758953559,
			"seed": 1759983760,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
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
					-73.27712263378129,
					73.22552238910612
				],
				[
					-202.87112683201525,
					-37.54213520042947
				],
				[
					-407.7982639884633,
					-31.87880883549701
				]
			]
		},
		{
			"type": "text",
			"version": 386,
			"versionNonce": 659094358,
			"isDeleted": false,
			"id": "1QjSz5jz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -402.6274569547546,
			"y": 933.7371557175076,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 274.592529296875,
			"height": 20,
			"seed": 247849072,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "How do we compute p ( x | wi, D )?",
			"rawText": "How do we compute p ( x | wi, D )?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we compute p ( x | wi, D )?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 755,
			"versionNonce": 173509898,
			"isDeleted": false,
			"id": "PjCahr9ukpT583xAVWDHd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -793.3371239644389,
			"y": 976.1735733953411,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 255.47318704346148,
			"height": 60.0471166127794,
			"seed": 1349061776,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "k-pKunQ1GNzsORhEsQkBP",
					"type": "arrow"
				}
			],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8a7aff35b61642903193ab222fb346e1e8b7f869",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 345,
			"versionNonce": 310059158,
			"isDeleted": false,
			"id": "phL8qW0Y-0_YTAlYopOzD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1000.371346318685,
			"y": 828.4596983422393,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 72.87568673393184,
			"height": 20.680938127196896,
			"seed": 1115573360,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-55.64157162793458,
					0.9848065774855286
				],
				[
					-72.87568673393184,
					20.680938127196896
				]
			]
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 1052072906,
			"isDeleted": false,
			"id": "GATNtDzy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1152.1596392727326,
			"y": 860.4659121105202,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 146.99234008789062,
			"height": 80,
			"seed": 1654600304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "data generating\ndistribution given\na certain dataset\nand a class",
			"rawText": "data generating\ndistribution given\na certain dataset\nand a class",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "data generating\ndistribution given\na certain dataset\nand a class",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "line",
			"version": 456,
			"versionNonce": 917937622,
			"isDeleted": false,
			"id": "zV6ii_AMxoZSwwEALWm-8",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -868.4072649356194,
			"y": 802.3623240388719,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 259.70638201562247,
			"height": 102.55579104250319,
			"seed": 1628044912,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-126.70230533438439,
					-89.56090038192326
				],
				[
					-259.70638201562247,
					-102.55579104250319
				]
			]
		},
		{
			"type": "text",
			"version": 765,
			"versionNonce": 736842378,
			"isDeleted": false,
			"id": "xvg4sFBW",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1376.9450783660843,
			"y": 640.3175402331344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 306.36865234375,
			"height": 220,
			"seed": 1256332400,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "integral over the whole\nparameter space\nthat we have inferred\nin previous steps so we are\ntaking into account all possible\nparameter values with their respective\nprobability given our dataset\nand seeing how it influences\nthe data we generate\n\n",
			"rawText": "integral over the whole\nparameter space\nthat we have inferred\nin previous steps so we are\ntaking into account all possible\nparameter values with their respective\nprobability given our dataset\nand seeing how it influences\nthe data we generate\n\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "integral over the whole\nparameter space\nthat we have inferred\nin previous steps so we are\ntaking into account all possible\nparameter values with their respective\nprobability given our dataset\nand seeing how it influences\nthe data we generate\n\n",
			"lineHeight": 1.25,
			"baseline": 214
		},
		{
			"type": "line",
			"version": 337,
			"versionNonce": 1494250262,
			"isDeleted": false,
			"id": "pNOHOKc5AspXoyISX8Gb0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -673.1066190277538,
			"y": 804.2513723448004,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 18.16356191784348,
			"height": 40.31424718350627,
			"seed": 550828688,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					18.16356191784348,
					-40.31424718350627
				]
			]
		},
		{
			"type": "text",
			"version": 435,
			"versionNonce": 1421111626,
			"isDeleted": false,
			"id": "wIyZpmj6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -707.5623554301873,
			"y": 733.3601632815237,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 157.9843292236328,
			"height": 20,
			"seed": 448590480,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "theta depends on D",
			"rawText": "theta depends on D",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "theta depends on D",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 332,
			"versionNonce": 1409130582,
			"isDeleted": false,
			"id": "mfb2k93c6X8nGZFel_JQI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -789.6991606217202,
			"y": 809.2226194226703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 25.71697918523705,
			"height": 125.27842717379792,
			"seed": 2105791088,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-25.71697918523705,
					-125.27842717379792
				]
			]
		},
		{
			"type": "text",
			"version": 957,
			"versionNonce": 745256970,
			"isDeleted": false,
			"id": "EoYcdzIm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -986.5810807013197,
			"y": 477.4564040231203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 321.6166076660156,
			"height": 200,
			"seed": 453041808,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Theta is built off of Di\nin order to describe the data\ngenerating distribution\nthus there is no need to specify\nPreviously generated data\nbecause all data is generated\ni.i.d which means there are no\nconnections between the old and the new\ndata other than the distribution\ndescribing their generation",
			"rawText": "Theta is built off of Di\nin order to describe the data\ngenerating distribution\nthus there is no need to specify\nPreviously generated data\nbecause all data is generated\ni.i.d which means there are no\nconnections between the old and the new\ndata other than the distribution\ndescribing their generation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Theta is built off of Di\nin order to describe the data\ngenerating distribution\nthus there is no need to specify\nPreviously generated data\nbecause all data is generated\ni.i.d which means there are no\nconnections between the old and the new\ndata other than the distribution\ndescribing their generation",
			"lineHeight": 1.25,
			"baseline": 194
		},
		{
			"type": "line",
			"version": 91,
			"versionNonce": 1800611222,
			"isDeleted": false,
			"id": "fdjJeZ_ILcGYGcp7spHi9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 294.1176839132642,
			"y": -164.06254372609817,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 142.03362614507728,
			"height": 46.98035326337174,
			"seed": 128861328,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					142.03362614507728,
					-46.98035326337174
				]
			]
		},
		{
			"type": "text",
			"version": 116,
			"versionNonce": 51128010,
			"isDeleted": false,
			"id": "ysMbKG12",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 388.2761771927202,
			"y": -258.0232502528416,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 316.44866943359375,
			"height": 40,
			"seed": 522464912,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338019,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This approach is less sensitive to data\nand takes into account prior knowledge",
			"rawText": "This approach is less sensitive to data\nand takes into account prior knowledge",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This approach is less sensitive to data\nand takes into account prior knowledge",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 634,
			"versionNonce": 1280056074,
			"isDeleted": false,
			"id": "BIOTDksK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1909.161348056647,
			"y": 1314.7932637005438,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 613.51220703125,
			"height": 45,
			"seed": 23912592,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Lets Compare Bayes vs Likelihood!",
			"rawText": "Lets Compare Bayes vs Likelihood!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets Compare Bayes vs Likelihood!",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 525,
			"versionNonce": 786966986,
			"isDeleted": false,
			"id": "jpXCsCIT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2086.6445302532093,
			"y": 1726.5230977179149,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 279.55316162109375,
			"height": 35,
			"seed": 1051381904,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Likelihood estimation",
			"rawText": "Likelihood estimation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Likelihood estimation",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 538,
			"versionNonce": 1754554506,
			"isDeleted": false,
			"id": "CvV3R2FBBHBEXw4Mm4o9s",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2060.8472842465717,
			"y": 1776.2182366695592,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 203.00000000000003,
			"height": 83,
			"seed": 257272976,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0d8f230f10576aaca3a28d10d3cbb34823602946",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 586,
			"versionNonce": 1963704138,
			"isDeleted": false,
			"id": "bmCJQpgr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2144.876012891011,
			"y": 1850.1769062773778,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 382.57684326171875,
			"height": 20,
			"seed": 1673775760,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": "[[Maximum Likelihood]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "explained previously in maximum likelihood chapter",
			"rawText": "explained previously in maximum likelihood chapter",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "explained previously in maximum likelihood chapter",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 534,
			"versionNonce": 547964426,
			"isDeleted": false,
			"id": "DOIozpXi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1687.321310921459,
			"y": 1777.931130517246,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 50.364013671875,
			"height": 45,
			"seed": 666900080,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "V.S",
			"rawText": "V.S",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V.S",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 561,
			"versionNonce": 1952969930,
			"isDeleted": false,
			"id": "Eu28sLRb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1531.7202396209186,
			"y": 1724.5870793892113,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 236.09695434570312,
			"height": 35,
			"seed": 1096991344,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Bayes estimation",
			"rawText": "Bayes estimation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bayes estimation",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 584,
			"versionNonce": 568511370,
			"isDeleted": false,
			"id": "WUzxpUGsPi2mGeb_66o1V",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1534.8077435306427,
			"y": 1765.3932441492639,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 616,
			"height": 124,
			"seed": 772688528,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d46c2c93e8e960ca296955cf8af006215edc51df",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 587,
			"versionNonce": 1867827786,
			"isDeleted": false,
			"id": "hYdpN6iPDt_62EGCu5MAU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1153.0099188789345,
			"y": 1798.3908171626008,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 239.5015206622345,
			"height": 108.51698805655974,
			"seed": 929861264,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					27.81223678374522,
					-94.2737920295524
				],
				[
					239.5015206622345,
					-108.51698805655974
				]
			]
		},
		{
			"type": "text",
			"version": 788,
			"versionNonce": 597225738,
			"isDeleted": false,
			"id": "w75pEBu4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -927.6685100400318,
			"y": 1676.9940855875893,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 317.9845886230469,
			"height": 80,
			"seed": 1891119248,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "normalizing term used to collect\ngarbage constant terms that\nwe dont care about\nit depends on D but is independnt of mu",
			"rawText": "normalizing term used to collect\ngarbage constant terms that\nwe dont care about\nit depends on D but is independnt of mu",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "normalizing term used to collect\ngarbage constant terms that\nwe dont care about\nit depends on D but is independnt of mu",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 1088,
			"versionNonce": 342016662,
			"isDeleted": false,
			"id": "ANW_xQTABdcd4lesjUQUp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -529.4909312358543,
			"y": 1933.263039959288,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 246.25395269954402,
			"height": 41.68779089186455,
			"seed": 1265766544,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716948104,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "59tyyOLI",
				"focus": -0.5387054368362417,
				"gap": 1
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
					147.52279776010187,
					-39.76303498051948
				],
				[
					246.25395269954402,
					1.9247559113450734
				]
			]
		},
		{
			"type": "text",
			"version": 648,
			"versionNonce": 1730393738,
			"isDeleted": false,
			"id": "59tyyOLI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -303.1294276637916,
			"y": 1935.2343575285363,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 402.720947265625,
			"height": 40,
			"seed": 1118202992,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ANW_xQTABdcd4lesjUQUp",
					"type": "arrow"
				}
			],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "our prior assumption about our\ntheta is that its drawn from a normal distribution",
			"rawText": "our prior assumption about our\ntheta is that its drawn from a normal distribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "our prior assumption about our\ntheta is that its drawn from a normal distribution",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 557,
			"versionNonce": 937106442,
			"isDeleted": false,
			"id": "vBeTcI809P89fPB9I0J52",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -223.86334949107345,
			"y": 1980.5942440308881,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 238,
			"height": 64,
			"seed": 1049591440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "10deafbef1f6ee62a23d80138e3eda7f3415594d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 578,
			"versionNonce": 854526666,
			"isDeleted": false,
			"id": "4eAJ9H65F47iCNqlJc46R",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1388.6021306955809,
			"y": 2083.804036380662,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 838,
			"height": 123,
			"seed": 329597040,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "405f337df2b5eed7ba4f9cce8eac77eaa6bc4425",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 548,
			"versionNonce": 1796678026,
			"isDeleted": false,
			"id": "IcmTh5AE9z8TQV44RoZ9W",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1409.5042927816517,
			"y": 2255.0901821459292,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 919,
			"height": 127,
			"seed": 653087344,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ME0_AAgzOLcT6u1DseAMc",
					"type": "arrow"
				}
			],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "34f2ab641d383e210d45d15dc2e8778163181f82",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 535,
			"versionNonce": 1613743882,
			"isDeleted": false,
			"id": "9gkdNoJwTaWwOcsY29XQg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 70,
			"angle": 0,
			"x": -1230.7283674739774,
			"y": 1953.5765674998938,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 67.44694038549153,
			"height": 78.42667486685059,
			"seed": 1959556752,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					67.44694038549153,
					78.42667486685059
				]
			]
		},
		{
			"type": "line",
			"version": 537,
			"versionNonce": 1635145162,
			"isDeleted": false,
			"id": "QotmzII5q7NjtzH261dkO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 70,
			"angle": 0,
			"x": -814.3071107291366,
			"y": 1946.9221383106697,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 67.44694038549153,
			"height": 78.42667486685059,
			"seed": 1990820464,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					67.44694038549153,
					78.42667486685059
				]
			]
		},
		{
			"type": "arrow",
			"version": 1074,
			"versionNonce": 525991894,
			"isDeleted": false,
			"id": "ME0_AAgzOLcT6u1DseAMc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 70,
			"angle": 0,
			"x": -1004.9720159308577,
			"y": 2400.1169718833235,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 3.6960047294469405,
			"height": 142.91218287194783,
			"seed": 1830412432,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716948105,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "IcmTh5AE9z8TQV44RoZ9W",
				"focus": 0.1237712997994126,
				"gap": 18.02678973739421
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
					3.6960047294469405,
					142.91218287194783
				]
			]
		},
		{
			"type": "text",
			"version": 621,
			"versionNonce": 1660873546,
			"isDeleted": false,
			"id": "nGAM0KmZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -982.2355039937647,
			"y": 2441.9690286366867,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 393.1195373535156,
			"height": 50,
			"seed": 452114032,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Which results in a Gaussian distribution\n generated from mu_n and sigma_n",
			"rawText": "Which results in a Gaussian distribution\n generated from mu_n and sigma_n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which results in a Gaussian distribution\n generated from mu_n and sigma_n",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 529,
			"versionNonce": 1062662666,
			"isDeleted": false,
			"id": "zbyoU0qiHiZdxJ9GKnvy2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1385.116003318999,
			"y": 2569.9492493442094,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 779.9999999999999,
			"height": 94,
			"seed": 2142094448,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "WrrjScmhWu_-_9sWwzNDW",
					"type": "arrow"
				},
				{
					"id": "k5Z0wQIH-KxAHKObgGP9Z",
					"type": "arrow"
				}
			],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a2a744a4e059840ffe773aa4e08d23d34c76fbce",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 1264,
			"versionNonce": 280003158,
			"isDeleted": false,
			"id": "WrrjScmhWu_-_9sWwzNDW",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1271.2865538570627,
			"y": 2682.2453328977717,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 81.69339291215975,
			"height": 35.6460412750489,
			"seed": 590962800,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716948106,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zbyoU0qiHiZdxJ9GKnvy2",
				"focus": 0.25421281464802886,
				"gap": 18.296083553562312
			},
			"endBinding": {
				"elementId": "smIVaSPI",
				"focus": -0.11966927796530268,
				"gap": 7.5763497827279025
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
					-81.69339291215975,
					35.6460412750489
				]
			]
		},
		{
			"type": "text",
			"version": 793,
			"versionNonce": 403741962,
			"isDeleted": false,
			"id": "smIVaSPI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1691.4787154225319,
			"y": 2725.4677239555485,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 500.3994140625,
			"height": 100,
			"seed": 62781072,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "WrrjScmhWu_-_9sWwzNDW",
					"type": "arrow"
				}
			],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "if we dont have a lot of data, this term\nis pulled towards our prior knowledge!\nif we do have a good bit of knowledge this is\npulled toward our maximum likelihood empirical mean",
			"rawText": "if we dont have a lot of data, this term\nis pulled towards our prior knowledge!\nif we do have a good bit of knowledge this is\npulled toward our maximum likelihood empirical mean",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "if we dont have a lot of data, this term\nis pulled towards our prior knowledge!\nif we do have a good bit of knowledge this is\npulled toward our maximum likelihood empirical mean",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 1804,
			"versionNonce": 321414358,
			"isDeleted": false,
			"id": "k5Z0wQIH-KxAHKObgGP9Z",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -815.027313212715,
			"y": 2678.549328168325,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 4.097775567753558,
			"height": 55.35216056061927,
			"seed": 691752048,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716948106,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zbyoU0qiHiZdxJ9GKnvy2",
				"focus": -0.4460928566723003,
				"gap": 14.600078824115371
			},
			"endBinding": {
				"elementId": "MsM9CisL",
				"focus": 0.16053343865100764,
				"gap": 11.088014188340821
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
					4.097775567753558,
					55.35216056061927
				]
			]
		},
		{
			"type": "text",
			"version": 658,
			"versionNonce": 2051506506,
			"isDeleted": false,
			"id": "MsM9CisL",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1090.565029869115,
			"y": 2744.989502917285,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 487.33941650390625,
			"height": 75,
			"seed": 1433649296,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "k5Z0wQIH-KxAHKObgGP9Z",
					"type": "arrow"
				}
			],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "confidence estimation!\nif we increase the amount of datapoints this will\ngo to 0 i.e we are very confident in our mean",
			"rawText": "confidence estimation!\nif we increase the amount of datapoints this will\ngo to 0 i.e we are very confident in our mean",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "confidence estimation!\nif we increase the amount of datapoints this will\ngo to 0 i.e we are very confident in our mean",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"id": "hUb1WH7O",
			"type": "text",
			"x": -429.06526155824,
			"y": 288.0849129381634,
			"width": 757.17919921875,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1210073482,
			"version": 399,
			"versionNonce": 396330954,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"text": "So the goal is to generate a distribution of parameters\nfrom which we can infer our dataset, and to do that we use\nour knowledge of the most likely values + a restriction of parameter values\n(prior knowledge of theta) over the entire space, once we have this\ndistribution we can continue forward with our prediction",
			"rawText": "So the goal is to generate a distribution of parameters\nfrom which we can infer our dataset, and to do that we use\nour knowledge of the most likely values + a restriction of parameter values\n(prior knowledge of theta) over the entire space, once we have this\ndistribution we can continue forward with our prediction",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 118,
			"containerId": null,
			"originalText": "So the goal is to generate a distribution of parameters\nfrom which we can infer our dataset, and to do that we use\nour knowledge of the most likely values + a restriction of parameter values\n(prior knowledge of theta) over the entire space, once we have this\ndistribution we can continue forward with our prediction",
			"lineHeight": 1.25
		},
		{
			"id": "k-pKunQ1GNzsORhEsQkBP",
			"type": "arrow",
			"x": -748.2958118466529,
			"y": 893.3826099554595,
			"width": 0.19836001033263528,
			"height": 82.08839961904027,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 706382346,
			"version": 280,
			"versionNonce": 1507144150,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.19836001033263528,
					82.08839961904027
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "PjCahr9ukpT583xAVWDHd",
				"focus": -0.6448887163798849,
				"gap": 1
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "pg1g8fEo",
			"type": "text",
			"x": -740.251480376599,
			"y": 916.7959460934748,
			"width": 115.39222717285156,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1078371978,
			"version": 220,
			"versionNonce": 1051721354,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"text": "from previously",
			"rawText": "from previously",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "from previously",
			"lineHeight": 1.25
		},
		{
			"id": "snAVycE1",
			"type": "text",
			"x": -358.59347089835063,
			"y": 776.7396639995021,
			"width": 815.12158203125,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1322653578,
			"version": 332,
			"versionNonce": 1128040214,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"text": "As opposed to ML classifier where we use the maximum likely theta in order to define\nour class posteriors, here we condition our class posterior to depend on the actual dataset\nthus the dataset has a huge effect on what we pick, and the bigger the dataset the more accurate\nwe get",
			"rawText": "As opposed to ML classifier where we use the maximum likely theta in order to define\nour class posteriors, here we condition our class posterior to depend on the actual dataset\nthus the dataset has a huge effect on what we pick, and the bigger the dataset the more accurate\nwe get",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "As opposed to ML classifier where we use the maximum likely theta in order to define\nour class posteriors, here we condition our class posterior to depend on the actual dataset\nthus the dataset has a huge effect on what we pick, and the bigger the dataset the more accurate\nwe get",
			"lineHeight": 1.25
		},
		{
			"id": "eBYmyMI_B44RYDCX-6b_q",
			"type": "arrow",
			"x": 42.21631881112796,
			"y": 742.0579810522513,
			"width": 22.330377414834345,
			"height": 35.43733807136755,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
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
			"seed": 332847114,
			"version": 103,
			"versionNonce": 33791306,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					22.330377414834345,
					16.990504554765266
				],
				[
					18.20411202296279,
					35.43733807136755
				]
			],
			"lastCommittedPoint": [
				18.20411202296279,
				35.43733807136755
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "hnQeSJlRHEg4tjJWAc7wA",
				"focus": 0.4969685656350785,
				"gap": 4.674689455912187
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "uXCLQ7zgoMUzZbRAh7SRS",
			"type": "arrow",
			"x": 451.1973052789068,
			"y": 798.8757025445245,
			"width": 237.05290891720267,
			"height": 200.7693004094674,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 81793034,
			"version": 250,
			"versionNonce": 1200043094,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					237.05290891720267,
					20.560711487716844
				],
				[
					235.84345530027815,
					200.7693004094674
				]
			],
			"lastCommittedPoint": [
				235.84345530027815,
				200.7693004094674
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "NA5TrwTO",
				"focus": -0.00441038504629447,
				"gap": 10.284364334978818
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "qnSxIr7b",
			"type": "text",
			"x": 528.7548126713617,
			"y": 768.639362121412,
			"width": 173.8563690185547,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 132077398,
			"version": 115,
			"versionNonce": 1056269322,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"text": "Lets take an example",
			"rawText": "Lets take an example",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Lets take an example",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 861,
			"versionNonce": 1619671446,
			"isDeleted": false,
			"id": "uX3vU2MG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 271.8349424712367,
			"y": 1040.4543100930841,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 835.2494506835938,
			"height": 100,
			"seed": 1067958102,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Given Two possible classes w1 and w2 such that they're equally to occur in the wild P(w1) = P(w2) = 0.5\nit is known that the data generation distribution is of the shape \nOur Current dataset contains {  ,   ,   ,    ,   ,   } such that the green points belong to class 1\nand the red points belong to class 2\nThis time we use Bayes estimation to learn about our data generating distribution",
			"rawText": "Given Two possible classes w1 and w2 such that they're equally to occur in the wild P(w1) = P(w2) = 0.5\nit is known that the data generation distribution is of the shape \nOur Current dataset contains {  ,   ,   ,    ,   ,   } such that the green points belong to class 1\nand the red points belong to class 2\nThis time we use Bayes estimation to learn about our data generating distribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given Two possible classes w1 and w2 such that they're equally to occur in the wild P(w1) = P(w2) = 0.5\nit is known that the data generation distribution is of the shape \nOur Current dataset contains {  ,   ,   ,    ,   ,   } such that the green points belong to class 1\nand the red points belong to class 2\nThis time we use Bayes estimation to learn about our data generating distribution",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "text",
			"version": 114,
			"versionNonce": 1870680778,
			"isDeleted": false,
			"id": "NA5TrwTO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 648.6675762451141,
			"y": 1009.9293672889708,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 76.7799072265625,
			"height": 25,
			"seed": 979461270,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "uXCLQ7zgoMUzZbRAh7SRS",
					"type": "arrow"
				}
			],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Example",
			"rawText": "Example",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Example",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 255,
			"versionNonce": 91920086,
			"isDeleted": false,
			"id": "jMH0O6jZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 553.9208809209252,
			"y": 1081.5780882586414,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#a5d8ff",
			"width": 94.40019226074219,
			"height": 20,
			"seed": 288645590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "0         2",
			"rawText": "0         2",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0         2",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 155,
			"versionNonce": 373254538,
			"isDeleted": false,
			"id": "42sjMU0R",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 580.9037429952987,
			"y": 1080.4838227714476,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 133.74427795410156,
			"height": 20,
			"seed": 657831702,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1   0      2   0",
			"rawText": "1   0      2   0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1   0      2   0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 134,
			"versionNonce": 2129480726,
			"isDeleted": false,
			"id": "K4xoLI-P7_EwWPArybfP1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 949.4166557042183,
			"y": 1059.1093258940964,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 75,
			"height": 19,
			"seed": 886727766,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4c5aaf7d4b581b380debc6ba9ccdf643071a4cc5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 246,
			"versionNonce": 711829578,
			"isDeleted": false,
			"id": "d9tDhXG6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 773.330091200741,
			"y": 1152.2442180269716,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 326.0217944847302,
			"height": 60.58812109893216,
			"seed": 40256,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "JfZ0i7vdcLztnQ2dzZTYC",
					"type": "arrow"
				}
			],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "742c3c9dfb8b1ffcb0d8dcf791fe597bb6e7da30",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 286,
			"versionNonce": 987191638,
			"isDeleted": false,
			"id": "geutJXcQR-YWH6JTnxSCN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 279.5674501441604,
			"y": 1146.0382785632025,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 266,
			"height": 73,
			"seed": 496665942,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b77dce9e6901e7ba2f328a64fb468bbcc0bd3b13",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "JfZ0i7vdcLztnQ2dzZTYC",
			"type": "arrow",
			"x": 728.72586566851,
			"y": 1183.8222946051196,
			"width": 39.59309453695096,
			"height": 0.8248561361865541,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1715187734,
			"version": 74,
			"versionNonce": 65408778,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					39.59309453695096,
					-0.8248561361865541
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "d9tDhXG6",
				"focus": 0.09027272527059452,
				"gap": 5.011130995280041
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "image",
			"version": 320,
			"versionNonce": 546160278,
			"isDeleted": false,
			"id": "Wit27DqEEjmQ0Uu1AzcAO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 349.69691405280315,
			"y": 1227.789612344447,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 501.1924177357087,
			"height": 26.378548301879405,
			"seed": 1515293002,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5ba0b960246bd0516aad17f188c68bd1f54386a4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 343,
			"versionNonce": 1193516490,
			"isDeleted": false,
			"id": "m2_tFjx4YL1OmU9eShxiN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 921.9241922863571,
			"y": 1226.119634395108,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 133.60125743390734,
			"height": 32.13194799043341,
			"seed": 1666084694,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "63708e6185b9f9dbb2c1e094191bded40d6debe8",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "JiUv8CPrOWZL4ULMCIeUD",
			"type": "arrow",
			"x": 855.3323669292697,
			"y": 1242.1856083903247,
			"width": 60.46293479056976,
			"height": 2.2737367544323206e-13,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 2046111318,
			"version": 205,
			"versionNonce": 1690663894,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					60.46293479056976,
					2.2737367544323206e-13
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "BWJx5vFTORXuOoP09cI_X",
			"type": "arrow",
			"x": 1077.7278521878563,
			"y": 1169.708685630997,
			"width": 188.42573401617642,
			"height": 39.81615212841825,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
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
			"seed": 20359178,
			"version": 60,
			"versionNonce": 1363235978,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					100.94235750866596,
					-30.84349812764799
				],
				[
					188.42573401617642,
					8.972654000770262
				]
			],
			"lastCommittedPoint": [
				188.42573401617642,
				8.972654000770262
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "W1QC3a7E",
			"type": "text",
			"x": 1206.267108961942,
			"y": 1181.4852940070077,
			"width": 201.64842224121094,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1994987734,
			"version": 92,
			"versionNonce": 1569952022,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"text": "we have to define this\nas our prior knowledge\nto be uniformly generated\nfrom",
			"rawText": "we have to define this\nas our prior knowledge\nto be uniformly generated\nfrom",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "we have to define this\nas our prior knowledge\nto be uniformly generated\nfrom",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 135,
			"versionNonce": 603599690,
			"isDeleted": false,
			"id": "bHLiuAxv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1254.998043905491,
			"y": 1267.39450892634,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 96.66954018717581,
			"height": 15.651258887447513,
			"seed": 17113,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9cb4c72138506736d31e8efcb309fd18a08872e6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 150,
			"versionNonce": 1449983574,
			"isDeleted": false,
			"id": "vzg_ma_xot4JDdTcvlBf8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1254.0480057632435,
			"y": 1291.9374183572118,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 96.66954018717581,
			"height": 15.651258887447513,
			"seed": 1817570198,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7b12506547c08103493d80a44463c92c81f732cb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 165,
			"versionNonce": 1370044938,
			"isDeleted": false,
			"id": "ze5XMdee",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 637.4551404392611,
			"y": 1291.6549816966115,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 195.692224295795,
			"height": 63.31219021334544,
			"seed": 86908,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "SMs2n-JgFXWhZOW768eJV",
					"type": "arrow"
				}
			],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8eb8769ad90c1073aad6544ad85729a31fe047ab",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "SMs2n-JgFXWhZOW768eJV",
			"type": "arrow",
			"x": 989.5878022360282,
			"y": 1279.074311029993,
			"width": 141.9709170923079,
			"height": 44.79168094721649,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
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
			"seed": 2072060042,
			"version": 95,
			"versionNonce": 1680262038,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					43.19832021406205
				],
				[
					-141.9709170923079,
					44.79168094721649
				]
			],
			"lastCommittedPoint": [
				-142.94716870835123,
				34.558656171249595
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "ze5XMdee",
				"focus": 0.05542642491805689,
				"gap": 14.46952040866421
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "NcmDhSIK",
			"type": "text",
			"x": 856.8726974247977,
			"y": 1328.9933035491474,
			"width": 230.92848205566406,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2060440202,
			"version": 229,
			"versionNonce": 1766418634,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"text": "this always samples a value\nbetween 0 and 1 thus we set\nthe prior to 1 (not sure tbh)",
			"rawText": "this always samples a value\nbetween 0 and 1 thus we set\nthe prior to 1 (not sure tbh)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "this always samples a value\nbetween 0 and 1 thus we set\nthe prior to 1 (not sure tbh)",
			"lineHeight": 1.25
		},
		{
			"id": "6GKYhPrR104a5vntWv3mq",
			"type": "arrow",
			"x": 613.1646014735802,
			"y": 1318.2054731264918,
			"width": 194.92821393707112,
			"height": 111.89550311055132,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
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
			"seed": 2094551242,
			"version": 608,
			"versionNonce": 955637974,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-167.7509637617821,
					0.8782772971821942
				],
				[
					-194.92821393707112,
					111.80522488929614
				],
				[
					-120.94462981655823,
					111.89550311055132
				]
			],
			"lastCommittedPoint": [
				-12.735020809140565,
				159.4073294385521
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "201F3CuA2EQqOKzuoWc10",
				"focus": 0.05055933652438161,
				"gap": 4.131150218325388
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "mxedpwY6",
			"type": "text",
			"x": 260.64355130197396,
			"y": 1377.719024712348,
			"width": 141.82432556152344,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 39148938,
			"version": 68,
			"versionNonce": 1651883914,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"text": "This integral goes\nbetween 0 and 1",
			"rawText": "This integral goes\nbetween 0 and 1",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "This integral goes\nbetween 0 and 1",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 470,
			"versionNonce": 2020562454,
			"isDeleted": false,
			"id": "201F3CuA2EQqOKzuoWc10",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 496.3511218753473,
			"y": 1403.1140791832497,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 699.3006677031804,
			"height": 57.80281045844765,
			"seed": 955894858,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "6GKYhPrR104a5vntWv3mq",
					"type": "arrow"
				}
			],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "431b535372ab29a4fb615e412d4a6c36187a5c27",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "5by3F9P0KEQbknRhh-7_W",
			"type": "arrow",
			"x": 890.075187463673,
			"y": 1593.5522120000612,
			"width": 170.30740228118134,
			"height": 1.4799748588341117,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 598433366,
			"version": 360,
			"versionNonce": 157892170,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					170.30740228118134,
					1.4799748588341117
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "XzCji_l8u1FZGaM58UGr9",
			"type": "arrow",
			"x": 891.6023190112871,
			"y": 1592.9204913186472,
			"width": 2.1007226797266867,
			"height": 109.5376825857511,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1089356054,
			"version": 258,
			"versionNonce": 193471318,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.1007226797266867,
					-109.5376825857511
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "vfNrb4nBsjm5aPW8fYa9C",
			"type": "line",
			"x": 893.7030416910138,
			"y": 1591.7200783588037,
			"width": 145.8501746210277,
			"height": 83.72880394910862,
			"angle": 0,
			"strokeColor": "#2f9e44",
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
			"seed": 2101533770,
			"version": 508,
			"versionNonce": 1795089674,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					34.81197583547146,
					-8.702993958867637
				],
				[
					48.91682811363694,
					-63.021680391801965
				],
				[
					71.12446787074805,
					-83.72880394910862
				],
				[
					91.2313849481327,
					-64.22209335164598
				],
				[
					99.63427566703945,
					-9.603303678750763
				],
				[
					145.8501746210277,
					0
				]
			],
			"lastCommittedPoint": [
				145.8501746210277,
				0.3001032399608903
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "tHn4nrUOOlAq3NrtXoJ3R",
			"type": "line",
			"x": 961.354338367757,
			"y": 1586.7464388767703,
			"width": 0.2560874592761593,
			"height": 16.13350993440895,
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
			"seed": 2067597834,
			"version": 187,
			"versionNonce": 1955940502,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.2560874592761593,
					16.13350993440895
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "8L8x3GGC",
			"type": "text",
			"x": 950.2508408455828,
			"y": 1606.7212607003241,
			"width": 25.280044555664062,
			"height": 20,
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
			"seed": 2143128330,
			"version": 204,
			"versionNonce": 1085387722,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"text": "0.5",
			"rawText": "0.5",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "0.5",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 208,
			"versionNonce": 592168406,
			"isDeleted": false,
			"id": "YFIBaOfAkTFIqUfAfRSHX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1036.387963935723,
			"y": 1590.2100254869229,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.2560874592761593,
			"height": 16.13350993440895,
			"seed": 1356516374,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.2560874592761593,
					16.13350993440895
				]
			]
		},
		{
			"type": "text",
			"version": 228,
			"versionNonce": 1553771146,
			"isDeleted": false,
			"id": "apw0yQtq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1035.7564817944083,
			"y": 1610.1848473104765,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.3360137939453125,
			"height": 20,
			"seed": 1930746198,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338020,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1",
			"rawText": "1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 368,
			"versionNonce": 1220582166,
			"isDeleted": false,
			"id": "GHjlTshcz327xynKzFRLh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 507.03797444600264,
			"y": 1588.1239773008663,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 170.30740228118134,
			"height": 1.4799748588341117,
			"seed": 802038410,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338020,
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
					170.30740228118134,
					1.4799748588341117
				]
			]
		},
		{
			"type": "arrow",
			"version": 266,
			"versionNonce": 360368458,
			"isDeleted": false,
			"id": "GZVGUyHuPKjWTIbs2aIVK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 508.5651059936167,
			"y": 1587.4922566194525,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.1007226797266867,
			"height": 109.5376825857511,
			"seed": 1941782858,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338021,
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
					2.1007226797266867,
					-109.5376825857511
				]
			]
		},
		{
			"type": "line",
			"version": 216,
			"versionNonce": 728287318,
			"isDeleted": false,
			"id": "7g9103uk8FJ9773DEDFJw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 653.3507509180527,
			"y": 1584.7817907877277,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.2560874592761593,
			"height": 16.13350993440895,
			"seed": 1882541130,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.2560874592761593,
					16.13350993440895
				]
			]
		},
		{
			"type": "text",
			"version": 236,
			"versionNonce": 849809418,
			"isDeleted": false,
			"id": "Xjwpv203",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 652.7192687767379,
			"y": 1604.7566126112813,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 4.3360137939453125,
			"height": 20,
			"seed": 2031694602,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1",
			"rawText": "1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"id": "cBqQtdgJyZMIFBORJAhun",
			"type": "line",
			"x": 511.8513996823249,
			"y": 1524.152642183669,
			"width": 143.87162230783963,
			"height": 0.8615067204061688,
			"angle": 0,
			"strokeColor": "#2f9e44",
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
			"seed": 1968917386,
			"version": 88,
			"versionNonce": 2065255830,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					143.87162230783963,
					0.8615067204061688
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "kYnIUbZ602rTRzgselBkN",
			"type": "line",
			"x": 653.5692551891489,
			"y": 1585.750372692714,
			"width": 1.723013440812565,
			"height": 60.73622378863888,
			"angle": 0,
			"strokeColor": "#2f9e44",
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
			"seed": 507824470,
			"version": 89,
			"versionNonce": 1478262474,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.723013440812565,
					-60.73622378863888
				]
			],
			"lastCommittedPoint": [
				1.723013440812565,
				-60.73622378863888
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Y9iXdeOI",
			"type": "text",
			"x": 524.8892375480873,
			"y": 1494.0921079144937,
			"width": 114.75225830078125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1846773078,
			"version": 62,
			"versionNonce": 621226710,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"text": "Prior of theta",
			"rawText": "Prior of theta",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Prior of theta",
			"lineHeight": 1.25
		},
		{
			"id": "HE90N7H2",
			"type": "text",
			"x": 913.5734444737872,
			"y": 1479.6565551640167,
			"width": 150.09632873535156,
			"height": 20,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1151749898,
			"version": 99,
			"versionNonce": 1920341386,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"text": "Posterior of theta",
			"rawText": "Posterior of theta",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Posterior of theta",
			"lineHeight": 1.25
		},
		{
			"id": "YSryjsqSZ6P0CHKrtFex7",
			"type": "arrow",
			"x": 685.7422487898878,
			"y": 1580.9170974733931,
			"width": 196.4553804846455,
			"height": 0.2967603934814633,
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
			"seed": 99829206,
			"version": 43,
			"versionNonce": 667377686,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					196.4553804846455,
					0.2967603934814633
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "OgBsjHUM",
			"type": "text",
			"x": 680.7070956265637,
			"y": 1513.255727759648,
			"width": 198.90614318847656,
			"height": 48.7231050477092,
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
			"seed": 2097387402,
			"version": 158,
			"versionNonce": 586077258,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"text": "our observations shrunk our\nbeliefs of theta into something\nthat reflects the dataset",
			"rawText": "our observations shrunk our\nbeliefs of theta into something\nthat reflects the dataset",
			"fontSize": 12.992828012722454,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 44,
			"containerId": null,
			"originalText": "our observations shrunk our\nbeliefs of theta into something\nthat reflects the dataset",
			"lineHeight": 1.25
		},
		{
			"id": "bRjs9dduaTI1cutb3CcO-",
			"type": "arrow",
			"x": 1141.197423957446,
			"y": 1554.8499305741364,
			"width": 303.97001145494824,
			"height": 3.434689394971201,
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
			"seed": 1883134998,
			"version": 91,
			"versionNonce": 1733225814,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					303.97001145494824,
					3.434689394971201
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "7aQ2MFy9",
				"focus": 1.486931996548799,
				"gap": 15.563166689365971
			},
			"endBinding": {
				"elementId": "sQgW7OoV",
				"focus": -0.22001049798959205,
				"gap": 13.966924051607407
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "7aQ2MFy9",
			"type": "text",
			"x": 1127.6486639060233,
			"y": 1479.2867638847704,
			"width": 291.568603515625,
			"height": 60,
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
			"seed": 985833610,
			"version": 159,
			"versionNonce": 727825162,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "bRjs9dduaTI1cutb3CcO-",
					"type": "arrow"
				}
			],
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"text": "We can do the same with the second\nclass, its the exact same steps\nso its redundant to mention it",
			"rawText": "We can do the same with the second\nclass, its the exact same steps\nso its redundant to mention it",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "We can do the same with the second\nclass, its the exact same steps\nso its redundant to mention it",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 91,
			"versionNonce": 15913622,
			"isDeleted": false,
			"id": "sQgW7OoV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1459.1343594640018,
			"y": 1545.2925139262813,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 261.61943220169616,
			"height": 23.447024584114278,
			"seed": 71343,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "bRjs9dduaTI1cutb3CcO-",
					"type": "arrow"
				}
			],
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3c0652392c8676b475ec5da08967b0cdad56f6a8",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "sVyXO1sLS6WSWynUcTvhM",
			"type": "arrow",
			"x": 1738.4641285697837,
			"y": 1562.6465161185079,
			"width": 210.20053845259076,
			"height": 3.2843834133220753,
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
			"seed": 1911950474,
			"version": 47,
			"versionNonce": 1514785226,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					210.20053845259076,
					3.2843834133220753
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "DnEiRTqi",
			"type": "text",
			"x": 1772.7334506760465,
			"y": 1521.0443262164326,
			"width": 139.47230529785156,
			"height": 20,
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
			"seed": 1527025354,
			"version": 31,
			"versionNonce": 526913494,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"text": "And the classifier",
			"rawText": "And the classifier",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "And the classifier",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 248,
			"versionNonce": 1992425610,
			"isDeleted": false,
			"id": "ZDVXbZhc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1970.7565727585932,
			"y": 1553.0885549472646,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 509.10632578448747,
			"height": 25.758355768857996,
			"seed": 75400,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d8da25b94953ee9528d4d58eb3b799227fc3541b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "rgiEoXYPEN5CwJkXlqonE",
			"type": "arrow",
			"x": 2501.241208532621,
			"y": 1555.5788021585458,
			"width": 51.44032341588854,
			"height": 47.699208985642144,
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
			"seed": 325561878,
			"version": 27,
			"versionNonce": 1321444630,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					14.964457720986047,
					-28.058358226848213
				],
				[
					51.44032341588854,
					-47.699208985642144
				]
			],
			"lastCommittedPoint": [
				51.44032341588854,
				-47.699208985642144
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "nkC14cdd",
				"focus": 0.8886006219212346,
				"gap": 9.210197184054778
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "nkC14cdd",
			"type": "text",
			"x": 2561.8917291325643,
			"y": 1491.9798568443564,
			"width": 327.6326904296875,
			"height": 20,
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
			"seed": 1777936458,
			"version": 95,
			"versionNonce": 746938186,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "rgiEoXYPEN5CwJkXlqonE",
					"type": "arrow"
				}
			],
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"text": "Denominator is constant thus not needed",
			"rawText": "Denominator is constant thus not needed",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Denominator is constant thus not needed",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 86,
			"versionNonce": 1350210134,
			"isDeleted": false,
			"id": "HDvEIfg8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2015.0553978947821,
			"y": 1598.2879900911848,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 353.6848223736749,
			"height": 58.16150412367098,
			"seed": 74412,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "aba446d087156b0bb2ffd209ab1841624165e7b6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 287,
			"versionNonce": 2012145162,
			"isDeleted": false,
			"id": "aCEgcWFiRWX1MsSteXA2Q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1697.438584376418,
			"y": 1663.7654943771013,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 988.9184492119924,
			"height": 68.08388634850206,
			"seed": 198274966,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716338021,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5cf1bd5665aeda9739d51496b7a4d545825c03a7",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "wuckAz3l",
			"type": "text",
			"x": -2070.762018043329,
			"y": 2863.7676959397104,
			"width": 1119.6387939453125,
			"height": 50,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 138231370,
			"version": 358,
			"versionNonce": 186332874,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"text": "This is just a really long way of proving that the posterior of a estimating the mean of a gaussian distribution\nusing bayes estimator is also a gaussian distribution classified by this mean and variance",
			"rawText": "This is just a really long way of proving that the posterior of a estimating the mean of a gaussian distribution\nusing bayes estimator is also a gaussian distribution classified by this mean and variance",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "This is just a really long way of proving that the posterior of a estimating the mean of a gaussian distribution\nusing bayes estimator is also a gaussian distribution classified by this mean and variance",
			"lineHeight": 1.25
		},
		{
			"id": "yPSFRWeL",
			"type": "text",
			"x": -2071.5500983322427,
			"y": 1414.9391485320289,
			"width": 890.9190673828125,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 276640342,
			"version": 142,
			"versionNonce": 1155386762,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"text": "Consider the case where μ is the only unknown parameter. We assume that whatever prior\nknowledge we might have about μ can be expressed by",
			"rawText": "Consider the case where μ is the only unknown parameter. We assume that whatever prior\nknowledge we might have about μ can be expressed by",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "Consider the case where μ is the only unknown parameter. We assume that whatever prior\nknowledge we might have about μ can be expressed by",
			"lineHeight": 1.25
		},
		{
			"id": "RALj1GGBs5DMpZVEvVYVw",
			"type": "image",
			"x": -1733.590564069408,
			"y": 1464.939148674886,
			"width": 215,
			"height": 45,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1456225302,
			"version": 141,
			"versionNonce": 1067420746,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5b34fc25f502e3abbe7179d18950ea1b3c362d5a",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "8QlTBw9H",
			"type": "text",
			"x": -2125.525692989051,
			"y": 1510.0820056748862,
			"width": 1050.298828125,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 638318806,
			"version": 160,
			"versionNonce": 1631286026,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"text": "where both μ0 and σ0 are known. Roughly speaking, μ0 represents our best a priori guess for μ, and σ0^2\nmeasures our uncertainty about this guess. The assumption that the prior distribution for\nμ is normal will simplify the subsequent mathematics.",
			"rawText": "where both μ0 and σ0 are known. Roughly speaking, μ0 represents our best a priori guess for μ, and σ0^2\nmeasures our uncertainty about this guess. The assumption that the prior distribution for\nμ is normal will simplify the subsequent mathematics.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "where both μ0 and σ0 are known. Roughly speaking, μ0 represents our best a priori guess for μ, and σ0^2\nmeasures our uncertainty about this guess. The assumption that the prior distribution for\nμ is normal will simplify the subsequent mathematics.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 168,
			"versionNonce": 472678858,
			"isDeleted": false,
			"id": "fzyIPwul",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1723.6342677643147,
			"y": 1383.273263297879,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 195.73421531544466,
			"height": 28.829070472817428,
			"seed": 83732,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cbe60153323b09ab985e4f2563e9ce7863b19c05",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "78dVLU9C",
			"type": "text",
			"x": -2048.4867031910057,
			"y": 1585.0820059969542,
			"width": 845.4390869140625,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 550821706,
			"version": 129,
			"versionNonce": 1536014474,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"text": "Imagine that a value is drawn for μ from a population governed by the probability\nlaw p(μ). Once this value is drawn, it becomes the true value of μ and completely\ndetermines the density for x. Suppose now that n samples x1, ..., xn are independently\ndrawn from the resulting population.",
			"rawText": "Imagine that a value is drawn for μ from a population governed by the probability\nlaw p(μ). Once this value is drawn, it becomes the true value of μ and completely\ndetermines the density for x. Suppose now that n samples x1, ..., xn are independently\ndrawn from the resulting population.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "Imagine that a value is drawn for μ from a population governed by the probability\nlaw p(μ). Once this value is drawn, it becomes the true value of μ and completely\ndetermines the density for x. Suppose now that n samples x1, ..., xn are independently\ndrawn from the resulting population.",
			"lineHeight": 1.25
		},
		{
			"id": "RZSGIUIYR2x9EM_XC4-5_",
			"type": "arrow",
			"x": -1561.648108424338,
			"y": 1974.8292719274173,
			"width": 102.32565470243571,
			"height": 53.38729810561881,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1774339082,
			"version": 210,
			"versionNonce": 1907448342,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708716948108,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-71.18306414082485,
					0
				],
				[
					-102.32565470243571,
					53.38729810561881
				]
			],
			"lastCommittedPoint": [
				-102.32565470243571,
				53.38729810561881
			],
			"startBinding": {
				"elementId": "ehG2POBTfTcoLtDdw3LUr",
				"focus": -0.12584916632226872,
				"gap": 31.049903251441492
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "rycvpQk7",
			"type": "text",
			"x": -1991.123699623412,
			"y": 2044.900100691042,
			"width": 614.2593994140625,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1833307030,
			"version": 131,
			"versionNonce": 1999412746,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"text": "This equation shows how the observation of a set of training\nsamples affects our ideas about the true value of μ",
			"rawText": "This equation shows how the observation of a set of training\nsamples affects our ideas about the true value of μ",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "This equation shows how the observation of a set of training\nsamples affects our ideas about the true value of μ",
			"lineHeight": 1.25
		},
		{
			"id": "YgNVuJXzLp-B3X2Rx5v6-",
			"type": "arrow",
			"x": -607.0897504345675,
			"y": 2615.0726758412384,
			"width": 873.4608075826883,
			"height": 6.335281250735079,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 467939850,
			"version": 302,
			"versionNonce": 1354779850,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					873.4608075826883,
					-6.335281250735079
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "CX6Gxddc",
			"type": "text",
			"x": -319.61650814196696,
			"y": 2392.734632001893,
			"width": 545.0193481445312,
			"height": 175,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 667236758,
			"version": 497,
			"versionNonce": 24126346,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"text": "From this result we can also show that\nthe variance of the posterior is contained both by\nthe uncertainty of the data mean and of the prior\n\nwhich means we are as confident with our posterior\nmean as we are with either the confidence of the prior\nor the confidence of the empirical",
			"rawText": "From this result we can also show that\nthe variance of the posterior is contained both by\nthe uncertainty of the data mean and of the prior\n\nwhich means we are as confident with our posterior\nmean as we are with either the confidence of the prior\nor the confidence of the empirical",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 168,
			"containerId": null,
			"originalText": "From this result we can also show that\nthe variance of the posterior is contained both by\nthe uncertainty of the data mean and of the prior\n\nwhich means we are as confident with our posterior\nmean as we are with either the confidence of the prior\nor the confidence of the empirical",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 216,
			"versionNonce": 595010122,
			"isDeleted": false,
			"id": "jDczr5JG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 305.14482450864216,
			"y": 2554.930540049638,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 332.75848645191184,
			"height": 98.863028583539,
			"seed": 21183,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "26b978377f0a453705ac8f5e1b3de7f891c00e96",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 291,
			"versionNonce": 1370507530,
			"isDeleted": false,
			"id": "rf7L3w1_Hk0kbuT2hjScx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 298.9935759595837,
			"y": 2664.3876339844674,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 401.5943792502038,
			"height": 81.9172614390963,
			"seed": 1821349962,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7154dcc7583e12821a16a787f840f4278e7d508d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "RZzndPZSwUgg769X38yKq",
			"type": "freedraw",
			"x": 683.1166571977424,
			"y": 2555.7285473326765,
			"width": 65.0688506433562,
			"height": 204.382928302849,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1336040534,
			"version": 194,
			"versionNonce": 328636362,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.6684320677784399,
					0
				],
				[
					5.839512237224426,
					0
				],
				[
					10.010592406670185,
					0
				],
				[
					13.347456542227064,
					0
				],
				[
					17.518536711672823,
					0
				],
				[
					19.186968779451036,
					0
				],
				[
					20.855400847229703,
					0
				],
				[
					22.523832915007915,
					0
				],
				[
					24.192264982786128,
					0.8342160338893336
				],
				[
					25.860697050564795,
					3.3368641355568798
				],
				[
					29.19756118612122,
					7.507944305002638
				],
				[
					31.700209287788766,
					10.844808440559518
				],
				[
					35.037073423345646,
					16.68432067778349
				],
				[
					36.70550549112386,
					20.02118481334037
				],
				[
					37.53972152501319,
					25.02648101667546
				],
				[
					37.53972152501319,
					28.36334515223234
				],
				[
					38.3739375589023,
					32.5344253216781
				],
				[
					38.3739375589023,
					36.70550549112386
				],
				[
					39.208153592791405,
					40.04236962668074
				],
				[
					40.876585660569845,
					42.545017728348284
				],
				[
					40.876585660569845,
					44.2134497961265
				],
				[
					41.71080169445895,
					45.881881863905164
				],
				[
					41.71080169445895,
					48.38452996557271
				],
				[
					41.71080169445895,
					50.05296203335092
				],
				[
					41.71080169445895,
					52.55561013501847
				],
				[
					41.71080169445895,
					54.22404220279668
				],
				[
					41.71080169445895,
					55.89247427057535
				],
				[
					41.71080169445895,
					56.72669030446423
				],
				[
					41.71080169445895,
					58.395122372242895
				],
				[
					41.71080169445895,
					59.229338406131774
				],
				[
					41.71080169445895,
					61.73198650779932
				],
				[
					41.71080169445895,
					63.40041857557799
				],
				[
					41.71080169445895,
					65.90306667724553
				],
				[
					41.71080169445895,
					68.40571477891262
				],
				[
					41.71080169445895,
					70.07414684669129
				],
				[
					41.71080169445895,
					75.07944305002638
				],
				[
					42.545017728348284,
					77.58209115169393
				],
				[
					42.545017728348284,
					80.08473925336148
				],
				[
					43.37923376223739,
					81.75317132113969
				],
				[
					43.37923376223739,
					83.4216033889179
				],
				[
					45.04766583001583,
					84.25581942280724
				],
				[
					45.88188186390494,
					85.09003545669657
				],
				[
					46.71609789779404,
					85.09003545669657
				],
				[
					47.55031393168338,
					85.09003545669657
				],
				[
					49.21874599946159,
					85.09003545669657
				],
				[
					50.88717806724003,
					85.09003545669657
				],
				[
					51.721394101129135,
					85.09003545669657
				],
				[
					52.55561013501847,
					85.09003545669657
				],
				[
					53.389826168907575,
					85.09003545669657
				],
				[
					55.058258236686015,
					85.09003545669657
				],
				[
					55.89247427057512,
					85.09003545669657
				],
				[
					56.72669030446423,
					85.09003545669657
				],
				[
					57.56090633835356,
					85.09003545669657
				],
				[
					59.229338406131774,
					85.09003545669657
				],
				[
					60.06355444002111,
					85.09003545669657
				],
				[
					60.897770473910214,
					85.09003545669657
				],
				[
					62.566202541688654,
					85.09003545669657
				],
				[
					63.40041857557776,
					85.09003545669657
				],
				[
					64.23463460946687,
					85.09003545669657
				],
				[
					62.566202541688654,
					85.09003545669657
				],
				[
					60.897770473910214,
					85.92425149058545
				],
				[
					59.229338406131774,
					87.59268355836412
				],
				[
					56.72669030446423,
					88.426899592253
				],
				[
					55.058258236686015,
					90.09533166003166
				],
				[
					53.389826168907575,
					91.76376372780987
				],
				[
					50.88717806724003,
					94.26641182947742
				],
				[
					50.05296203335092,
					95.93484389725563
				],
				[
					49.21874599946159,
					97.6032759650343
				],
				[
					49.21874599946159,
					98.43749199892318
				],
				[
					49.21874599946159,
					100.10592406670185
				],
				[
					49.21874599946159,
					101.77435613448006
				],
				[
					49.21874599946159,
					104.2770042361476
				],
				[
					49.21874599946159,
					105.94543630392582
				],
				[
					49.21874599946159,
					108.44808440559336
				],
				[
					49.21874599946159,
					110.95073250726091
				],
				[
					49.21874599946159,
					113.45338060892846
				],
				[
					50.05296203335092,
					115.956028710596
				],
				[
					50.88717806724003,
					119.29289284615288
				],
				[
					50.88717806724003,
					121.79554094782043
				],
				[
					53.389826168907575,
					130.1377012867124
				],
				[
					55.058258236686015,
					131.8061333544906
				],
				[
					56.72669030446423,
					135.1429974900475
				],
				[
					56.72669030446423,
					136.8114295578257
				],
				[
					56.72669030446423,
					138.47986162560392
				],
				[
					58.39512237224267,
					139.31407765949325
				],
				[
					59.229338406131774,
					142.65094179505013
				],
				[
					60.897770473910214,
					143.485157828939
				],
				[
					62.566202541688654,
					145.98780593060656
				],
				[
					64.23463460946687,
					148.4904540322741
				],
				[
					64.23463460946687,
					152.66153420171986
				],
				[
					65.0688506433562,
					156.83261437116607
				],
				[
					65.0688506433562,
					161.83791057450117
				],
				[
					65.0688506433562,
					166.00899074394692
				],
				[
					62.566202541688654,
					171.01428694728202
				],
				[
					61.73198650779932,
					174.3511510828389
				],
				[
					58.39512237224267,
					179.356447286174
				],
				[
					55.89247427057512,
					181.85909538784153
				],
				[
					54.22404220279668,
					186.0301755572873
				],
				[
					51.721394101129135,
					188.53282365895484
				],
				[
					48.38452996557248,
					191.86968779451126
				],
				[
					45.04766583001583,
					196.04076796395748
				],
				[
					44.2134497961265,
					198.54341606562502
				],
				[
					41.71080169445895,
					201.04606416729257
				],
				[
					39.208153592791405,
					203.54871226896012
				],
				[
					38.3739375589023,
					203.54871226896012
				],
				[
					37.53972152501319,
					203.54871226896012
				],
				[
					36.70550549112386,
					204.382928302849
				],
				[
					35.87128945723475,
					204.382928302849
				],
				[
					35.87128945723475,
					204.382928302849
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				35.87128945723475,
				204.382928302849
			]
		},
		{
			"type": "image",
			"version": 304,
			"versionNonce": 1229262474,
			"isDeleted": false,
			"id": "VUtt1bBvZtzTjCFV4_ci9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 769.9501357697795,
			"y": 2596.386580491748,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 321.8573669860994,
			"height": 102.21146113747751,
			"seed": 343634582,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "XCPaMMbxJPxcc80r7sUfH",
					"type": "arrow"
				}
			],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e3c161b0345a857204f48519b14ac7ef59193c5f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 388,
			"versionNonce": 1401320458,
			"isDeleted": false,
			"id": "FOyaRs5I2ryd5f2jIWAVQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1229.0746066273773,
			"y": 2590.5836084329285,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 344.60411149790065,
			"height": 95.46465250955356,
			"seed": 1332540234,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "XCPaMMbxJPxcc80r7sUfH",
					"type": "arrow"
				}
			],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "eedeb20788af7e8a7c08bdab1f9ab1132e35296f",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "XCPaMMbxJPxcc80r7sUfH",
			"type": "arrow",
			"x": 1106.898402413446,
			"y": 2630.073342021653,
			"width": 119.59854506470128,
			"height": 1.117390463146421,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1053363158,
			"version": 385,
			"versionNonce": 1076251798,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716948108,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					119.59854506470128,
					1.117390463146421
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "VUtt1bBvZtzTjCFV4_ci9",
				"focus": -0.36236000430470866,
				"gap": 15.090899657567206
			},
			"endBinding": {
				"elementId": "FOyaRs5I2ryd5f2jIWAVQ",
				"focus": 0.11129089564033999,
				"gap": 2.5776591492299303
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "c5qmBx0ihGYgJOdGQ_cz9",
			"type": "arrow",
			"x": -58.24910899284623,
			"y": 2611.4594099814904,
			"width": 10.135798794520724,
			"height": 399.6400667553871,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 481438346,
			"version": 109,
			"versionNonce": 634959946,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					10.135798794520724,
					399.6400667553871
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "9CvkK6Hm",
			"type": "text",
			"x": -35.48575093173349,
			"y": 2800.8255045235333,
			"width": 437.55950927734375,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1469190666,
			"version": 315,
			"versionNonce": 2137988874,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"text": "We can also show that our posterior\nmean always lies between our prior mean\nand our empirical mean, the more datapoints\nwe have the closer it gets to the empirical",
			"rawText": "We can also show that our posterior\nmean always lies between our prior mean\nand our empirical mean, the more datapoints\nwe have the closer it gets to the empirical",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "We can also show that our posterior\nmean always lies between our prior mean\nand our empirical mean, the more datapoints\nwe have the closer it gets to the empirical",
			"lineHeight": 1.25
		},
		{
			"id": "T6eu7fKTZ11EML1POIV4K",
			"type": "arrow",
			"x": 2.3203377593454206,
			"y": 2969.6026861801347,
			"width": 398.3141487095786,
			"height": 4.05065235975826,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1314758474,
			"version": 132,
			"versionNonce": 252358090,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					398.3141487095786,
					-4.05065235975826
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "xnuTGMCv7UqzhUWqfC7KN",
			"type": "line",
			"x": 343.50360788167063,
			"y": 2952.730811034863,
			"width": 0.960964244706247,
			"height": 31.71182007531297,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 83896842,
			"version": 102,
			"versionNonce": 700867722,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.960964244706247,
					31.71182007531297
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "image",
			"version": 135,
			"versionNonce": 1230848842,
			"isDeleted": false,
			"id": "n4CHAzIV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 334.2828846981406,
			"y": 2996.37062884335,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 17,
			"height": 17,
			"seed": 30521,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "110ce5ad4e030538e30d955ef0b56f8f9f358002",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "KO6nKOEjXR_cuZRHpz6IG",
			"type": "line",
			"x": 268.3125037011282,
			"y": 2948.66939672952,
			"width": 0.5762729507084714,
			"height": 31.695012288967064,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1406098186,
			"version": 113,
			"versionNonce": 2016037386,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5762729507084714,
					31.695012288967064
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "image",
			"version": 108,
			"versionNonce": 1026062538,
			"isDeleted": false,
			"id": "2SB3dMhy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 262.33793669234797,
			"y": 3002.0978080718905,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 18,
			"height": 11,
			"seed": 91293,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2294ea9ef22aca465f0b82d6c5616929728a14c0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 129,
			"versionNonce": 133353354,
			"isDeleted": false,
			"id": "GlugqDw2oiFwVUgynKobz",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 74.3429899095704,
			"y": 2951.9051081516814,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.5762729507084714,
			"height": 31.695012288967064,
			"seed": 1777602582,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5762729507084714,
					31.695012288967064
				]
			]
		},
		{
			"type": "image",
			"version": 105,
			"versionNonce": 482627146,
			"isDeleted": false,
			"id": "DKS1zJsN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 71.51531705712819,
			"y": 2998.64017036764,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 17,
			"height": 11,
			"seed": 45176,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6fb39a57a395516d0234ce5029b7602e59c4baef",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 222,
			"versionNonce": 7861514,
			"isDeleted": false,
			"id": "wYx52YIR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -252.41452242724836,
			"y": 3039.989112919725,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 401.08742460242314,
			"height": 30.334343037158053,
			"seed": 26081,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a812e44af232c6754da9ce2aed4f32239ee30f9a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 188,
			"versionNonce": 1686684618,
			"isDeleted": false,
			"id": "oaiGShpV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -202.05764968997437,
			"y": 3095.458562541993,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 317.40960043253864,
			"height": 76.55172716314166,
			"seed": 1912,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6c2a77b2bb531eac96e180150e7235497c6a3f4d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 300,
			"versionNonce": 319928970,
			"isDeleted": false,
			"id": "5S3mMUJrFan--h0u2jQjy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -412.97960165215386,
			"y": 3184.776950505393,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 705.3686922574705,
			"height": 70.67822567710125,
			"seed": 278885322,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "aef1be19afe0a3e6634ac521d9589f10038c9d90",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 334,
			"versionNonce": 1523439946,
			"isDeleted": false,
			"id": "oZ8LjA5zswDb0qjK1j3BE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -389.6780153775528,
			"y": 3265.884179430731,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 661.6040680623811,
			"height": 75.35353850368804,
			"seed": 1637441878,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cfae5783c2c3167c79389b075b2007671e56cfa8",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "GtQiz4hV_PGm_Y8Xt2LKe",
			"type": "line",
			"x": -94.99187325305274,
			"y": 3269.8776684011227,
			"width": 36.65692164079951,
			"height": 69.76639925184463,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 858220106,
			"version": 139,
			"versionNonce": 2065178634,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					36.65692164079951,
					69.76639925184463
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "kJ6dFey1M_hn28of9ech7",
			"type": "line",
			"x": 2.5628375652038358,
			"y": 3261.6002989983617,
			"width": 135.98535447393328,
			"height": 79.22624999785694,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1933636630,
			"version": 128,
			"versionNonce": 267095754,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					135.98535447393328,
					79.22624999785694
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Np3sJprXjRSTSR9F7eShX",
			"type": "line",
			"x": -382.3348396631901,
			"y": 3263.9652616848653,
			"width": 134.21163245905598,
			"height": 77.45252798297952,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 555219274,
			"version": 125,
			"versionNonce": 2112038282,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					134.21163245905598,
					77.45252798297952
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "image",
			"version": 246,
			"versionNonce": 1580852298,
			"isDeleted": false,
			"id": "j7xJJqDLeM_ygcL7C0kPT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -250.01005383907795,
			"y": 3382.4184819537168,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 401.08742460242314,
			"height": 30.334343037158053,
			"seed": 1657336714,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708716947424,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0175b941b7d8f8988fa4f79ce7f144474eecf3c1",
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
		"currentItemStrokeWidth": 1,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1903.4896321220958,
		"scrollY": -733.1051303166346,
		"zoom": {
			"value": 0.24621731917946454
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