---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Regression Models ^pGzYTkmm

What is regression? ^ElStZInL

Regression is the prediction of a real values associated with
the given input, unlike classification, there is not a set amount of
possible outputs, instead it is a continuous function that maps
input values to some output value ^8NMDeYNP

Linear Regression ^oEAfm07H

Given a set of samples (X1,Y1)...(Xt,Yt), Predict Y for a given X input ^ozZw5Ow8

1xd ^HJNQm5RE

x1 ^9YrYYmLs

dx1 ^wG7g0tVG

xt ^Jfx0yOOO

dx1 ^0hiww77J

Tx1 ^Qf9bJ8Zy

x ^3CvKIrDP

y ^kIpVTff4

Next step is to minimize the discrepancy between our predicted output
and the true output for a given input by adjusting w ^x1Nyhz7t

Using the least square error loss function we can derive the following ^0wqxFuOG

Problem:
This model is not very robust and is quite influenced by outliers ^NjZTVi0J

Ridge Regression ^kQT4ovcc

Lets Introduce a regularization term in the loss function
that controls the complexity of the model ^BS3fd1Xl

We add the squared euclidean norm of W scaled by lambda ^D5LgQcAb

By computing its derivative we get the following ^RoNylDEq

The scale of lambda determines the the values of w
a low value of lambda gets us closer to the linear model
while a high value of lambda shrinks the values of w towards zero  ^wlOsAiTg

Problem:
If the relationship between input and output is not linear, the linear
model gives poor predictions ^tYZGpiWr

Kernel Ridge Regression ^vA7aTpQy

We project the data via a mapping function into higher dimensional
feature space the non-linear relationship can be approximated via a
linear function in higher dimensions ^E7EbuIQm

As we know from before, doing this in infinite dimensions
is not an easy task, thus we use the kernel trick!

The prediction of the new datapoint x has to lie somewhere in the span of our current data
since its part of the same distribution, it can be thought of as a linear
combination of all previous datapoints, thus we only need to compare
with previous datapoints to know the answer, since the solution must lie
within the span of the datapoints ^eqwserXF

all previously seen
datapoints ^5ttCCzIs

The kernel function k corresponds to an inner product in feature space and
measures the similarity between two data points ^ERPYJTdb

Lets take a moment to rewrite our model using the Kernel trick ^aqU5SaVL

Kernel matrix
describing similarities
between xi and xj ^XP0cXnhz

Bayesian Regression ^rHvnlkzU

Alright, lets have a bit of fun and apply the Bayesian inference to our model.
hows that fun you say?
......
idk, its not
 ^TPaosvHq

We can calculate the likelihood of the observed data being plausible by our model ^CaPYcKlA

Obviously we are interested in the Posterior of W, which is, given the knowledge
of X and y, what W helps us achieve the highest prediction
using bayes rule: ^PPzzjuCq

such that ^MOvv08WF

Now  that we have our posterior which describes what is
the most likely w that describes our data we just need to make a prediction.
Keep in mind when predicting using this model, we do not just predict
a value of y, instead we predict an entire distribution describing the possible
values of y, with our variance describing our confidence in the mean ^92GSdVZg

Gaussian Process ^P0T8vcRd

The model we have just seen is called the Gaussian Process, which is an enhancement
to the Bayesian linear regression model using kernels
(Same algorithm as before but its a different way to view it)
The Gaussian process model is quite a useful modelling process as it instead of outputting
a single output for each input, it outputs a distribution based off of how certain/uncertain
it is with its prediction (mean).
This model can be used for a wide variety of different domains and areas, it also offers
efficient hyper-parameter selection.

GP can be thought of as a model that outputs potential functions that describe our data
and we try to minimize it to only output the most likely functions.
(i.e it works in the function space) ^w0GU2lIm

mean of distribution
of output functions ^wj09WR4o

Variance of distribution
of output functions ^ee7tMv1S

There are many GP kernels and distributions to describe the output functions
Assuming that the mean is 0 (Not necessary), our covariance determines the functions that have
higher prior probability (more likely to be included) ^aKTCKsW2

1) Firstly we specify what kind of distributions we use by setting the covariance function to something prior ^MlSi5VUh

2) then incorperate our current observed m datapoints into the prior knowledge (cov function) in order
to then eliminate all the functions that do not agree with its y outputs.
Keep in mind we also add a bit of i.i.d noise to allow fluctuations because we assume that our ys
are some noisy output of a true function ^NmnNUoTu

Determining what functions get samples
is something that is determined by
the kernel choice
GP will sample functions with nearby y's
for x's determined "similar" by the kernel
function provided (remember that kernels
measure similarities between 2 objects) ^8tLISFhV

Kernels also have hyperparameters that
change the function outputs depending
on their values, for example RBF has
 a hyperparameter called "length scale"
which scales up or down the distances between x's ^Ht1wvleG

small length means x values
are quite similar which means
the functions fluctuates less
/slowly ^re3l9jdM

large length means x values
are distant which means
the functions will fluctuate
more frequently ^Y5eFXo6N

picking the right kernel is not
always just finding a good kernel function
there are a plethora of ways to find good
kernels to describe your data, like combining
two kernels with addition, multiplication, scalar
multiplication etc... ^4G8nqwrv

matrix of input datapoints ^US23Wxos

previously unobserved datapoint
 ^1PAcu8c3

output functions of observed datapoints ^jm7gVgbr

unobserved true function output estimate ^EOCI0S6O

matrix containing all
kernel similarities
between previously observed
data and new data ^IR3uJjFE

if a vector is normally distributed and we only observe it partially (using a well known
mathematical result) we can know the distribution over the unobserved elements given the observed elements
(Bayesian updating) where y is the observed part and f* is the unobserved part
this leads us to be able to infer f* from the following distribution
think of it as slicing the multivariate distribution over specific values and getting another multivariate (smaller dimensional)
distribution of possible values in it ^niLrHNBZ

Some Cons:

1) requires inverting Kxx matrix which takes O(N^3) time

2) Designing the kernels is complex and requires time and understanding

3) certain kernels dont work in higher dimensions ^eoovYAsW

Meaning we figure out how similar our point
is to all previously seen datapoints and quantify
that similarity, after that we just have to
figure out the correct linear combination
of the similarities through minimizing the error ^ub04JIU1

K "Covariance" gram matrix
in feature space, explaining
similarities and structure
in our observed dataset ^I5JPQGOb

How our current point
compares to the dataset
(similarities) ^PhWi6SUW

A key note to keep in mind here
we are no longer thinking about
predicting a single points, instead
we are trying to produce an entire function
as an output and everytime we speak
of outputs we are talking about a distribution
of all possible functions ^zGoqLIA7

Likelihood of predicting y
given X and w ^YEXFHVOi

How did we
derive this? ^FdKztXUC

Im glad you asked because
I dont really get it ^X0FElNLB

The posterior mean value of the weights w is the choice of w that minimizes the
quadratic form ^SJrvZSui

 Let                And t be the vector of targets ^kExQub7F

The solution is then given by ^8Yz4gS1i

nxn ^zrKLT5Xr

1xn ^LhfWegPy

nx1 ^Mov3M2Ak

1x1 ^IsaQgw4W

I encourage you to read about the first few
sections of this paper if you want to understand
more because quite frankly my brain is currently too fried
to actually properly get it and thus properly explain it ^OSWY0Tc7

ALso this video is kinda nice ^rVQUmrw3

Weird Note: we assume that y and f* are distributed as N+M dimensional multivariate Normal
meaning that our entire dataset (N size) counts as partial observation of one sample of this normal
our entire dataset, given one function f* is ONE conditional observation from it!!
and obviously the more likely observations are ones which y is most likely described by out f*
this assumption is so alien...
(its because y is normally distributed, f* is normally distributed, their joint is then
normally distributed and a marginalized normal distribution is another normal distribution) ^UfpLi2xj

Lets explain visually ^RDTH5fqM

y (Observed) ^GYKemLWU

f* (Unobserved) ^0tmcyFxG

given this assumption
that its a Normal distribution
at mean 0 and covariance
governed by the similarities 
in data ^2juBYsLO

If we have a known value y ^GGIZTn1F

f* ^QLf1KAzR

Then we can infer
the distribution of f*
given that value of y ^jwOyGG2v

This also works in higher dimension
and is easy to analytically compute
ONLY because we are dealing with
Gaussians, other distributions or families
are way harder to infer ^Qg9OBqgF

Which make sense why
the kernel choice then
determines our function
shape since the distribution
that we sample our functions
from has a covariance matrix
governed by the similarities
calculated by the kernel fucntion ^YfeiNX0j

The posterior predictive distribution
for an unobserved xi is an independent normal
distribution which has a mean of
equal to the xi-th element of the mean f*
The variance is similarly selected from the
diagonal of k(x*,x*) (including the noise) ^U8ta4RMD

This is the posterior
distribution over f*
(after we condition it
to include what we previously
believe to be true) ^rt9AvdXX

Anyway as always we make a few assumptions beforehand in order to
get our model
Lets assume that y is part of a parametric model + a bit of i.i.d noise ^lcPM6aI1

We can assume a prior on p(w) according to our problem  ^7DFPZsaJ

As you'll see moving forward, Bayesian regression will be
an expanded Idea on Kernel ridge regression, where Kernel ridge gives us
one answer as its "best prediction" Bayesian regression expands on the idea by giving us
the best prediction alongside a confidence estimation for each areas, the more data we observe
in each area the more confident we are the less the variance etc... We also can always
include our prior knowledge is this sort of approach! ^stk8rg74

%%***>>>text element-link:[[Bayes Estimator]]<<<***%%its good to be familiar
with its classification alternative
Parameter estimation ^W67BxozR

%%***>>>text element-link:[[Regularization]]<<<***%%these ideas are similar
to Bayesian Neural networks that
provide confidence estimation ^dCusToqw

Through some shitty math proof that tells us
how to infer the parameters of a Gaussian given
that its 2 Gaussians multiplied ^q2nLzyox

Note that there is a version of this model
called Bayesian Linear regression which has the 
exact same ideas but does not use Kernels and feature spaces
and as such its not as good, and we all know the conclusion
of our lectures every single time...
if its linear then KERNELIZE IT!!!
so I just skipped the bs and went straight
to the kernelized version ^WageIrBv

Which simplifies to ^Yt88XHgW

We start off with our Prior knowledge ^KK5lBeRY

Using different kernels we will describe the possible functions
as prior knowledge and limit our space to specific types of solutions ^2PgrdROR

Then after Observing a few points (Black dots)
our posterior will eliminate functions that do not agree
with the true prediction with some variance ^28nKFHjv

observing data ^9wubAUvZ

as you can see intuitively the more we observe the closer we get to the
real function, and in certain regions where we dont have a lot of datapoints
our variance will be high (same as prior) because we are not confident on what
to predict there whereas in areas that we observe a lot of data we will
get more confident
our Mean of the distribution of outputs is always just the kernel ridge regression answer
but we provide this confidence estimate to compensate for the messyness of the real
world data! ^1778tctZ

high fluctuations ^AqPMcbGn

small 
fluctuations ^mYFuxNvz

True function is sampled
from a distribution
of functions ^CIbJaBN9

Once we get our posterior we can use that
optimized distribution of functions to sample
a function from it ^LLlD1WjD

3) if we want to make a prediction (or use this point to train our model) we sample accordingly ^R1qx1qHu

Proof from cookbook ^AFzj5o2w

Note, that the covariance matrix is the Schur complement of the block matrix ^swv8flC4

can be interpereted
as the lambda of the
regularization parameter
in kernel ridge regression ^xcGyCWMq


# Embedded files
2b902bad96b731902a64ec26ebb922751f929ec5: $$\beta = \frac{1}{\sigma_v^2}$$
a7fd1de0ad9d204648c6ccd417353ae9092d55ce: $$A = \sigma^{-2} \phi(X)\phi(X)^T + \Sigma^{-1}$$
f9d014528bec0eb074298c7ec33a910a3b6ba0f6: $$\phi(x)$$
1b611a69fde84eaa8012debe1db6a78b922fc0e1: $$\phi(X)$$
1f0dd65fea8fdc617ee612e6a2333d40ee220b8a: $$\propto \mathcal{N} ( \sigma^{-2} A^{-1} \phi(X)y, A^{-1})$$
f03d687bfe1f48932952cc638c21e171d450cf82: $$p(f^*|y) =$$
d814557a59d38dce0b7c2203ab721e44b667cd91: [[Pasted Image 20240203170019_364.png]]
0ff33a64ea633e86d509fe911108ae8a067f0afe: [[Pasted Image 20240203170134_378.png]]
75beba5c2c49cdaa96b77a692fc493a82a49e9d9: [[Pasted Image 20240203184602_737.png]]
6c976f75eac42d157aa3f560b8b2cff211fcb3c6: [[Pasted Image 20240203184947_757.png]]
0162a0018bbf3fe4d8959980fa830f08607025e2: [[Pasted Image 20240203185003_146.png]]
e162573fb0d8a806fd865e14146b03964493c550: [[Pasted Image 20240203185046_916.png]]
15438de668e7bc407739936cff7c2e9d76697be9: [[Pasted Image 20240203185116_964.png]]
b93d8ce41da7acc3f6ac11611a9aa13c68782a77: [[Pasted Image 20240203185247_993.png]]
c5b5d5752e9e6b857e1b64122c1315bcdea4c3f7: [[Pasted Image 20240203185521_030.png]]
18de4621dc7d40fe0f40f48b52b3e749d2791e06: [[Pasted Image 20240203185617_072.png]]
ad001f7ee61335afdbd189e14037a31f8c506acf: [[Pasted Image 20240203185632_087.png]]
cb6eb8e5bac166ab2b0be44ea51304a876122079: [[Pasted Image 20240203185719_099.png]]
50c862e840583a763785b00663ee7b73f9b88fd9: [[Pasted Image 20240203185736_114.png]]
40f9503bba93e9f1d7f81e424aa67cfff39e912c: [[Pasted Image 20240203190315_144.png]]
3a086c8fe6cab6035fdd8b152b3cd5658c35ad7b: [[Pasted Image 20240203190430_149.png]]
699e4dbb71d0adaac511632e8c8376a3d094f4d7: [[Pasted Image 20240203190511_170.png]]
380013beb6e21e593c6b97fa36f7a19282e7bf9b: [[Pasted Image 20240203190816_233.png]]
0cbe4042d56f847a3e32f02510db1bebf8509da3: [[Pasted Image 20240203190948_249.png]]
9a8d69aa4b66b05147a84ace85f307d0a8802cd5: [[Pasted Image 20240203191308_289.png]]
9af29d0d3cbee0671658956a104be8e0ab097d4c: [[Pasted Image 20240203191408_302.png]]
e74b26d8eeae19b329fc2ed5a52a9cbd8c01ee02: [[Pasted Image 20240203191712_340.png]]
6dfb6e5dcb946b9539d8215b87e074c35ca8e2ab: [[Pasted Image 20240203191729_343.png]]
3e924c0cc29cb2c13245f68692503d6c971b3951: [[Pasted Image 20240203194157_001.png]]
83b2a5ec525db0e2fbd29efebd439f5653a17375: [[Pasted Image 20240203194326_458.png]]
6aa651356a13f3f36c9a5c505143a0a91555162a: [[Pasted Image 20240203194458_476.png]]
b6ff724ce65571a9a8d6ee399c2bcd9a6c07a4ea: [[Pasted Image 20240203194513_489.png]]
bae80243c920d6aa6fcb608324c045c56b07501d: [[Pasted Image 20240203195117_569.png]]
a1a11069d27eab66aedd5df69068aeba6905802c: [[Pasted Image 20240203195132_584.png]]
bb4aa9fe7c626f662eacc6835bc8f5025993f38c: [[Pasted Image 20240203195232_600.png]]
55aeefe0303692ee0b0198cbac8630cec0e99f88: [[Pasted Image 20240203195317_604.png]]
300a01edc8b8a096065d3a9ec925eff22ba95dc7: [[Pasted Image 20240203195418_622.png]]
e864a3a7d9439ebad047375155c2c76886fe7b0c: [[Pasted Image 20240204193153_815.png]]
7b03ae2880e769e85dbf4632e264920cb6349940: [[Pasted Image 20240204193210_833.png]]
ab50265c9d47e4f16cf82cdef52af805a9dfb5c9: [[Pasted Image 20240204193433_882.png]]
7e6a7d7d704abc9aab8c5614cc2b52febdb53790: [[Pasted Image 20240204193707_907.png]]
50aa512acc69f5a5e2c6f812a7cc214d7c32100e: [[Pasted Image 20240204193953_937.png]]
81996919842e04d9784ec7d10f21bf4fa2117353: [[Pasted Image 20240204194053_952.png]]
df4dfd813b0edf8966f765547ad297ed10eccca4: [[Pasted Image 20240204194215_967.png]]
24a024f158ce93378f6328aaafecfb77d8285316: [[Pasted Image 20240204195024_209.png]]
1d766f0140a7af9de03ed0db474d02152c731562: [[Pasted Image 20240204195055_227.png]]
ffbe3f8eb4f7bed6df413eaa5d89168d558d6cd1: [[Pasted Image 20240227211223_341.png]]
4bd0d0e7809ad36b48ded0eb1af78ee3bd021327: [[Pasted Image 20240227211323_352.png]]
5035c4a7758ca2c64f5653d13056b527aa4bade4: [[Pasted Image 20240227211529_371.png]]
25e018f8a616ec7fa4f22805d926126b3c9ecf9b: [[Pasted Image 20240227211659_391.png]]
9358745cf6b740fb530b306eb935d3b26ffa1b36: [[Pasted Image 20240228180526_398.png]]
cac06548860057e30cdebdba3d4a58793ef9597e: [[Pasted Image 20240228184749_878.png]]
176cf6773a998146dc657481c9d7dcf6783327a7: [[Pasted Image 20240228184935_271.png]]
62eb819452ec065f990c4e4738609366e9982cb2: [[Pasted Image 20240228191303_295.png]]
db6d03f9aba761e2a519a33fbfdb08772c6b170a: [[Pasted Image 20240303150451_190 1.png]]
b1e06c18595b1c68dccada501e953065ac6a9a39: [[Pasted Image 20240303150636_204 1.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.23",
	"elements": [
		{
			"type": "image",
			"version": 130,
			"versionNonce": 1822309542,
			"isDeleted": false,
			"id": "92fuiEVFnALvh8dgib53G",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3150.684506773943,
			"y": 1033.8337109178487,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 573,
			"height": 304,
			"seed": 1182910054,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "176cf6773a998146dc657481c9d7dcf6783327a7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 121,
			"versionNonce": 1626196154,
			"isDeleted": false,
			"id": "OowcLKFwMbnB8rZ1VLAAz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2345.298438885919,
			"y": 1037.3504874243054,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 569,
			"height": 299,
			"seed": 1016998714,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "uLOkulI1gX70J3ybqHerd",
					"type": "arrow"
				}
			],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cac06548860057e30cdebdba3d4a58793ef9597e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 411,
			"versionNonce": 2020123002,
			"isDeleted": false,
			"id": "mrD5TEyNC6dz9CgcqfNCj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1108.8293545496674,
			"y": 379.03269855298595,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 458.3738115157801,
			"height": 76.8052633236897,
			"seed": 340136750,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "d0YVJ6B-1gp7SH2rM3nHc",
					"type": "arrow"
				}
			],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "83b2a5ec525db0e2fbd29efebd439f5653a17375",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 327,
			"versionNonce": 419941158,
			"isDeleted": false,
			"id": "0MDSRU3bQsEH-iDTr_eDM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 609.6127427896706,
			"y": 181.3405136935674,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 188.56290399213208,
			"height": 43.78614250004565,
			"seed": 2111322414,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6aa651356a13f3f36c9a5c505143a0a91555162a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 237,
			"versionNonce": 881484346,
			"isDeleted": false,
			"id": "1T4H2ouk6rGO5ozJ19Twy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -150.56322198735523,
			"y": 1203.6114478630363,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 312.75233203392327,
			"height": 78.3584274159067,
			"seed": 1935344494,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "380013beb6e21e593c6b97fa36f7a19282e7bf9b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 227,
			"versionNonce": 2037347942,
			"isDeleted": false,
			"id": "GPdwW-wW5yoQhQUbUwM1x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 100.18244317293657,
			"y": 1259.6616179346536,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 150.05949639784296,
			"height": 26.4976058770485,
			"seed": 1475725934,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					46.95450138677397,
					26.4976058770485
				],
				[
					150.05949639784296,
					8.542646323669715
				]
			]
		},
		{
			"type": "text",
			"version": 193,
			"versionNonce": 808848122,
			"isDeleted": false,
			"id": "5ttCCzIs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 221.43279645103138,
			"y": 1225.5964169576978,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 142.49627685546875,
			"height": 40,
			"seed": 740844782,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "all previously seen\ndatapoints",
			"rawText": "all previously seen\ndatapoints",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "all previously seen\ndatapoints",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 360,
			"versionNonce": 507492774,
			"isDeleted": false,
			"id": "2SCGJQHdJvBhXheyY35CR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1109.0094566011455,
			"y": 2330.511114325891,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 459.3193490483622,
			"height": 84.85136066389592,
			"seed": 1289720700,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "50aa512acc69f5a5e2c6f812a7cc214d7c32100e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 277,
			"versionNonce": 837721018,
			"isDeleted": false,
			"id": "ziURKVaOqjXrQlsdL2vBh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1569.9686435885617,
			"y": 432.3532616794277,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 670.2043596337953,
			"height": 117.98218555900553,
			"seed": 1930284590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "75beba5c2c49cdaa96b77a692fc493a82a49e9d9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 319,
			"versionNonce": 514168038,
			"isDeleted": false,
			"id": "4CDR4Zof2Iql6A36p4yvX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1448.7366033737928,
			"y": 187.5021396221582,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 449.4741115069918,
			"height": 193.5788208850171,
			"seed": 758610226,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0ff33a64ea633e86d509fe911108ae8a067f0afe",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 59,
			"versionNonce": 936842362,
			"isDeleted": false,
			"id": "qYQYmd1uCxsubqOuuQTeE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -207.02954400000002,
			"y": -406.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 389,
			"height": 159,
			"seed": 1812275058,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "pGzYTkmm"
				}
			],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 44,
			"versionNonce": 606996518,
			"isDeleted": false,
			"id": "pGzYTkmm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -135.35633045787336,
			"y": -344.4728016043305,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 245.5890350341797,
			"height": 35,
			"seed": 506084654,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Regression Models",
			"rawText": "Regression Models",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "qYQYmd1uCxsubqOuuQTeE",
			"originalText": "Regression Models",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 70,
			"versionNonce": 62027066,
			"isDeleted": false,
			"id": "ElStZInL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -138.75,
			"y": -236.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 265.4691162109375,
			"height": 35,
			"seed": 916098094,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is regression?",
			"rawText": "What is regression?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is regression?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 516297574,
			"isDeleted": false,
			"id": "8NMDeYNP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -335.04507505078124,
			"y": -190.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 658.0592651367188,
			"height": 100,
			"seed": 1319946354,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Regression is the prediction of a real values associated with\nthe given input, unlike classification, there is not a set amount of\npossible outputs, instead it is a continuous function that maps\ninput values to some output value",
			"rawText": "Regression is the prediction of a real values associated with\nthe given input, unlike classification, there is not a set amount of\npossible outputs, instead it is a continuous function that maps\ninput values to some output value",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Regression is the prediction of a real values associated with\nthe given input, unlike classification, there is not a set amount of\npossible outputs, instead it is a continuous function that maps\ninput values to some output value",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 200,
			"versionNonce": 652459514,
			"isDeleted": false,
			"id": "oEAfm07H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1362.0443968447264,
			"y": 56.341513500000005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 236.82498168945312,
			"height": 35,
			"seed": 1227139634,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Linear Regression",
			"rawText": "Linear Regression",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Linear Regression",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 304,
			"versionNonce": 2025502374,
			"isDeleted": false,
			"id": "ozZw5Ow8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1573.9461453964843,
			"y": 106.3415135,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 678.1593627929688,
			"height": 25,
			"seed": 1149454386,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Given a set of samples (X1,Y1)...(Xt,Yt), Predict Y for a given X input",
			"rawText": "Given a set of samples (X1,Y1)...(Xt,Yt), Predict Y for a given X input",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given a set of samples (X1,Y1)...(Xt,Yt), Predict Y for a given X input",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 169,
			"versionNonce": 242085562,
			"isDeleted": false,
			"id": "H4LwLeJqBfiBJyc5NfMoH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1335.366464,
			"y": 146.34151350000002,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 200.99999999999997,
			"height": 71,
			"seed": 1918693106,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d814557a59d38dce0b7c2203ab721e44b667cd91",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 159,
			"versionNonce": 1253634534,
			"isDeleted": false,
			"id": "HJNQm5RE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1288.942201985406,
			"y": 291.86802135624504,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 22.432052612304688,
			"height": 20,
			"seed": 1148495026,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1xd",
			"rawText": "1xd",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1xd",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 188,
			"versionNonce": 250873722,
			"isDeleted": false,
			"id": "_pHX28nPk9CPdd_gGvqej",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1182.5056202992262,
			"y": 238.3237188557053,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 17.901743945087674,
			"height": 76.72175976466144,
			"seed": 423504046,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 206,
			"versionNonce": 265143590,
			"isDeleted": false,
			"id": "9YrYYmLs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1176.7480187752471,
			"y": 269.0124227615699,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.95245361328125,
			"height": 11.96248231036879,
			"seed": 1226343534,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 9.569985848295032,
			"fontFamily": 1,
			"text": "x1",
			"rawText": "x1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x1",
			"lineHeight": 1.25,
			"baseline": 7
		},
		{
			"type": "text",
			"version": 178,
			"versionNonce": 1891174458,
			"isDeleted": false,
			"id": "wG7g0tVG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1179.4733197919413,
			"y": 322.05314017670827,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 12.924606323242188,
			"height": 11.53097159099833,
			"seed": 503330866,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 9.224777272798665,
			"fontFamily": 1,
			"text": "dx1",
			"rawText": "dx1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dx1",
			"lineHeight": 1.25,
			"baseline": 8
		},
		{
			"type": "rectangle",
			"version": 188,
			"versionNonce": 1499869286,
			"isDeleted": false,
			"id": "F9wz-6jD9OhMzEBAW0NU7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1045.3198070057483,
			"y": 238.68906056887027,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 17.901743945087674,
			"height": 76.72175976466144,
			"seed": 411148658,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 218,
			"versionNonce": 2074079482,
			"isDeleted": false,
			"id": "Jfx0yOOO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1040.6525104186117,
			"y": 269.2419907301914,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.759201049804688,
			"height": 11.96248231036879,
			"seed": 1777138158,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 9.569985848295032,
			"fontFamily": 1,
			"text": "xt",
			"rawText": "xt",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "xt",
			"lineHeight": 1.25,
			"baseline": 7
		},
		{
			"type": "text",
			"version": 185,
			"versionNonce": 55522214,
			"isDeleted": false,
			"id": "0hiww77J",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1040.0253916510233,
			"y": 320.93619689997814,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 12.924606323242188,
			"height": 11.53097159099833,
			"seed": 120019758,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 9.224777272798665,
			"fontFamily": 1,
			"text": "dx1",
			"rawText": "dx1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dx1",
			"lineHeight": 1.25,
			"baseline": 8
		},
		{
			"type": "text",
			"version": 153,
			"versionNonce": 53199290,
			"isDeleted": false,
			"id": "Qf9bJ8Zy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1395.2919727800324,
			"y": 356.85782177319135,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 26.192062377929688,
			"height": 20,
			"seed": 1008759790,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Tx1",
			"rawText": "Tx1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Tx1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 594,
			"versionNonce": 1739968230,
			"isDeleted": false,
			"id": "kl0zO-KGgRnc5kSRTqgot",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1649.965594270481,
			"y": 341.72855160883984,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 163.01169264754685,
			"height": 2.4330103380231094,
			"seed": 1404088238,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "3CvKIrDP",
				"focus": 1.923777308150786,
				"gap": 13.112682316354949
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
					120.43401173214272,
					2.4330103380229957
				],
				[
					163.01169264754685,
					2.4330103380231094
				]
			]
		},
		{
			"type": "arrow",
			"version": 383,
			"versionNonce": 1920957050,
			"isDeleted": false,
			"id": "wiRb7gmnRYTl8XT3RbOKM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1649.9655942704812,
			"y": 342.94505677785133,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.2165051690115547,
			"height": 163.01169264754697,
			"seed": 1754321518,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "kIpVTff4",
				"focus": -4.628773314301017,
				"gap": 15.608805341113111
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
					-124.6917798236833
				],
				[
					1.2165051690115547,
					-163.01169264754697
				]
			]
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 321323558,
			"isDeleted": false,
			"id": "TOH1MCHMJ2tQMpqOemHsP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1612.269095850449,
			"y": 206.13104219578588,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 529829102,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 1482562362,
			"isDeleted": false,
			"id": "iV2wsRTwuUgrgG-oxXj1l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1616.81207660621,
			"y": 219.38140273342208,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 18905074,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 2022690150,
			"isDeleted": false,
			"id": "_ljvE9Ex4JaHXIg0mzl8K",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1595.2329180163454,
			"y": 211.43118641084038,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 1654403374,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 1932174330,
			"isDeleted": false,
			"id": "7SfWhUPQ0iw_NbCkLZb5P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1595.9900814756388,
			"y": 231.87459981176465,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 905652782,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 624767142,
			"isDeleted": false,
			"id": "IqBGmlb8DRnyp9tIQMmC_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1581.6039757490626,
			"y": 223.16722002988956,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 1905593710,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 1021842618,
			"isDeleted": false,
			"id": "X0wl3Ebq8ObGVFlnvCu_w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1578.9539036415354,
			"y": 235.66041710823214,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 956762606,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 1960586214,
			"isDeleted": false,
			"id": "WQZuJo3SonkknY4VOcHb2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1560.7819806184914,
			"y": 240.58197959363991,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 2145307378,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 2000252282,
			"isDeleted": false,
			"id": "-p-eUbo4eVSISf9bcVTrZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1562.6748892667251,
			"y": 257.9967391573903,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 1759131250,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 1165606694,
			"isDeleted": false,
			"id": "XTthv9gmVPZFGtBgxVSzL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1562.2963075370783,
			"y": 260.2682295352708,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 897768110,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 929148474,
			"isDeleted": false,
			"id": "fnhrERzgoYypkdbVqKhTF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1532.0097691653384,
			"y": 260.2682295352708,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 1502463538,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 729999974,
			"isDeleted": false,
			"id": "NCYfMF1uXcK9o_Hmg1jPM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1546.017293162268,
			"y": 264.8112102910317,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 1958282990,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 1917048570,
			"isDeleted": false,
			"id": "ysrzZLuxEcLXjThnNqt5s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1544.5029662436812,
			"y": 243.61063343081395,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 30776818,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810009,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 633646502,
			"isDeleted": false,
			"id": "MSS_Yo90jqK01HFI6eiXi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1532.0097691653384,
			"y": 274.27575353220044,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 1825008430,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 140699578,
			"isDeleted": false,
			"id": "selZO90Z9_SQ3xHAB-8Tu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1516.8664999794685,
			"y": 258.37532088703705,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 35700146,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 1366034662,
			"isDeleted": false,
			"id": "Xs1CYPfj5Uj1uSQDEwmxo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1516.4879182498219,
			"y": 289.4190227180704,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 925828974,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 1373757562,
			"isDeleted": false,
			"id": "TLjgWz5zx4ZTH_5KuUvn9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1505.1304663604194,
			"y": 279.1973160176082,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 1206551534,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 503708710,
			"isDeleted": false,
			"id": "XF06RzdEtKuPgUlIuCF7p",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1505.1304663604194,
			"y": 303.80512844464687,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 633663730,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 713277754,
			"isDeleted": false,
			"id": "iQeejsHhbRiG46ml-7bKA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1487.3371250670223,
			"y": 303.0479649853533,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 1767131182,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 217,
			"versionNonce": 25134950,
			"isDeleted": false,
			"id": "Oy-rb-7R4cIRIyFLPxdzz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1489.230033715256,
			"y": 280.7116429361951,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 1883943090,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 218,
			"versionNonce": 2108393978,
			"isDeleted": false,
			"id": "OiuRRiDBYnwUtw9jpxdRF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1523.68097111311,
			"y": 269.7327727764395,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 5.6787259447012275,
			"height": 5.300144215054389,
			"seed": 1833649262,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 237,
			"versionNonce": 740666022,
			"isDeleted": false,
			"id": "35CMm0BIcFirhU-PSVDzJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1619.6514395785607,
			"y": 209.53827776260658,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 146.5111293732915,
			"height": 99.188413167448,
			"seed": 1618463602,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					146.5111293732915,
					99.188413167448
				]
			]
		},
		{
			"type": "text",
			"version": 202,
			"versionNonce": 1381776058,
			"isDeleted": false,
			"id": "3CvKIrDP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1509.0586035926094,
			"y": 353.3993350283708,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 8.992019653320312,
			"height": 20,
			"seed": 1017196078,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "kl0zO-KGgRnc5kSRTqgot",
					"type": "arrow"
				}
			],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "x",
			"rawText": "x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 186,
			"versionNonce": 1017472486,
			"isDeleted": false,
			"id": "kIpVTff4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1671.8619075041063,
			"y": 186.44479225415495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 7.5040130615234375,
			"height": 20,
			"seed": 1526132142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "wiRb7gmnRYTl8XT3RbOKM",
					"type": "arrow"
				}
			],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "y",
			"rawText": "y",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "y",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 407,
			"versionNonce": 1463341946,
			"isDeleted": false,
			"id": "x1Nyhz7t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1573.3225886447815,
			"y": 393.46144857926464,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 699.3192138671875,
			"height": 50,
			"seed": 1620016050,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Next step is to minimize the discrepancy between our predicted output\nand the true output for a given input by adjusting w",
			"rawText": "Next step is to minimize the discrepancy between our predicted output\nand the true output for a given input by adjusting w",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Next step is to minimize the discrepancy between our predicted output\nand the true output for a given input by adjusting w",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 349,
			"versionNonce": 1946925350,
			"isDeleted": false,
			"id": "0wqxFuOG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1581.936104741859,
			"y": 555.9479933703701,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 694.1392822265625,
			"height": 25,
			"seed": 663007726,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Using the least square error loss function we can derive the following",
			"rawText": "Using the least square error loss function we can derive the following",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Using the least square error loss function we can derive the following",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 260,
			"versionNonce": 1854166074,
			"isDeleted": false,
			"id": "icUXi5ANEaziSu7BStzvj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1506.431488500625,
			"y": 601.6077481453135,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 543.1300485050024,
			"height": 41.64388060891487,
			"seed": 2034689458,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6c976f75eac42d157aa3f560b8b2cff211fcb3c6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 304,
			"versionNonce": 1774560358,
			"isDeleted": false,
			"id": "QiipkoJlmUzlD-A64JMNM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1536.3011421976043,
			"y": 643.2516294779323,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 312.3015942087262,
			"height": 67.13024922243648,
			"seed": 2096529262,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0162a0018bbf3fe4d8959980fa830f08607025e2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 237,
			"versionNonce": 975289594,
			"isDeleted": false,
			"id": "hrgZOVbLitYotpdh3EmXo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1437.7873839922345,
			"y": 710.3818789926813,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 221.67216555553776,
			"height": 31.14402325986894,
			"seed": 1560641902,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e162573fb0d8a806fd865e14146b03964493c550",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 196,
			"versionNonce": 1067460518,
			"isDeleted": false,
			"id": "yldtB_gcv_S5hhQtsbLxi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1443.6603616454229,
			"y": 755.8150248959511,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 208.79389764542287,
			"height": 65.28658746435052,
			"seed": 1347833714,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "15438de668e7bc407739936cff7c2e9d76697be9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 253,
			"versionNonce": 664014266,
			"isDeleted": false,
			"id": "NjZTVi0J",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1534.3348525287242,
			"y": 825.0279649975167,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 636.4392700195312,
			"height": 50,
			"seed": 1480685170,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Problem:\nThis model is not very robust and is quite influenced by outliers",
			"rawText": "Problem:\nThis model is not very robust and is quite influenced by outliers",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem:\nThis model is not very robust and is quite influenced by outliers",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 206,
			"versionNonce": 1439187686,
			"isDeleted": false,
			"id": "s41tBTiN2qPm6Xp2rFzMA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1433.6800116085167,
			"y": 901.5723343817542,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 435.1295875752994,
			"height": 191.3872116474245,
			"seed": 1406901230,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b93d8ce41da7acc3f6ac11611a9aa13c68782a77",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 473,
			"versionNonce": 2080261754,
			"isDeleted": false,
			"id": "Arc2DfWe-hGCwD20C9QEJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -742.9570033882458,
			"y": 546.4624726870816,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 199.74895397489533,
			"height": 64.43514644351465,
			"seed": 13661106,
			"groupIds": [
				"JJur0H5sNY-sZzSBGvWkr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 497,
			"versionNonce": 2127230502,
			"isDeleted": false,
			"id": "KjHRQhaGTYu--v-_sU6We",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -549.6515640577011,
			"y": 630.22816306365,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 57.99163179916319,
			"height": 103.09623430962344,
			"seed": 631975282,
			"groupIds": [
				"JJur0H5sNY-sZzSBGvWkr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					57.99163179916319,
					-51.54811715481172
				],
				[
					0,
					-103.09623430962344
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 323,
			"versionNonce": 1612932922,
			"isDeleted": false,
			"id": "kQT4ovcc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -114.07272977729787,
			"y": 48.35253955532531,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 225.2049560546875,
			"height": 35,
			"seed": 1607360498,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Ridge Regression",
			"rawText": "Ridge Regression",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Ridge Regression",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 277,
			"versionNonce": 865419622,
			"isDeleted": false,
			"id": "BS3fd1Xl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -286.8199224889979,
			"y": 100.7955784270881,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 570.6993408203125,
			"height": 50,
			"seed": 579816498,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets Introduce a regularization term in the loss function\nthat controls the complexity of the model",
			"rawText": "Lets Introduce a regularization term in the loss function\nthat controls the complexity of the model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets Introduce a regularization term in the loss function\nthat controls the complexity of the model",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 174,
			"versionNonce": 1818652666,
			"isDeleted": false,
			"id": "D5LgQcAb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -301.60015059338804,
			"y": 150.79557841064425,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 583.359375,
			"height": 25,
			"seed": 646176370,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We add the squared euclidean norm of W scaled by lambda",
			"rawText": "We add the squared euclidean norm of W scaled by lambda",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We add the squared euclidean norm of W scaled by lambda",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 152,
			"versionNonce": 1198793894,
			"isDeleted": false,
			"id": "5NAxZ9OYV-ZEirecFjRcr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -290.9702521319678,
			"y": 186.8609243455015,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 579,
			"height": 65,
			"seed": 1180233518,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c5b5d5752e9e6b857e1b64122c1315bcdea4c3f7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 91,
			"versionNonce": 885678266,
			"isDeleted": false,
			"id": "RoNylDEq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -246.17020392806916,
			"y": 262.9262698614689,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 472.4994812011719,
			"height": 25,
			"seed": 1560364658,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "By computing its derivative we get the following",
			"rawText": "By computing its derivative we get the following",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "By computing its derivative we get the following",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 147,
			"versionNonce": 471113702,
			"isDeleted": false,
			"id": "ShcOhZDUMbgYrC6eOhMvI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -223.71529839072866,
			"y": 300.40227866506564,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 427.5896700822191,
			"height": 85.07019614201216,
			"seed": 1166033202,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "18de4621dc7d40fe0f40f48b52b3e749d2791e06",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 385,
			"versionNonce": 1425160570,
			"isDeleted": false,
			"id": "6rSirHL8iCYfUNm7zoufr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -128.5785194451196,
			"y": 375.0569617129112,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 237.31611306767277,
			"height": 41.87931407076578,
			"seed": 532760050,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ad001f7ee61335afdbd189e14037a31f8c506acf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 115,
			"versionNonce": 1434694438,
			"isDeleted": false,
			"id": "Yb828j2f5VmR0RdCnRydZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -146.47971175782874,
			"y": 419.86593202670565,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 253.47990434796986,
			"height": 36.95042337433963,
			"seed": 1377453422,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cb6eb8e5bac166ab2b0be44ea51304a876122079",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 194,
			"versionNonce": 2082535994,
			"isDeleted": false,
			"id": "pCfqE8qIIqK4ImT4KpVfd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -126.65027186017284,
			"y": 464.11192364356293,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 228.2414562504511,
			"height": 41.67329959629023,
			"seed": 1701090478,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "50c862e840583a763785b00663ee7b73f9b88fd9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 193,
			"versionNonce": 237919846,
			"isDeleted": false,
			"id": "wlOsAiTg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -346.82011245657446,
			"y": 527.1319294857274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 670.21923828125,
			"height": 75,
			"seed": 1339070834,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The scale of lambda determines the the values of w\na low value of lambda gets us closer to the linear model\nwhile a high value of lambda shrinks the values of w towards zero ",
			"rawText": "The scale of lambda determines the the values of w\na low value of lambda gets us closer to the linear model\nwhile a high value of lambda shrinks the values of w towards zero ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The scale of lambda determines the the values of w\na low value of lambda gets us closer to the linear model\nwhile a high value of lambda shrinks the values of w towards zero ",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 95,
			"versionNonce": 2033820410,
			"isDeleted": false,
			"id": "tYZGpiWr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -338.37960789097764,
			"y": 614.4679224050332,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 682.2592163085938,
			"height": 75,
			"seed": 1841380206,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Problem:\nIf the relationship between input and output is not linear, the linear\nmodel gives poor predictions",
			"rawText": "Problem:\nIf the relationship between input and output is not linear, the linear\nmodel gives poor predictions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem:\nIf the relationship between input and output is not linear, the linear\nmodel gives poor predictions",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 110,
			"versionNonce": 182559142,
			"isDeleted": false,
			"id": "vA7aTpQy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -161.2109437371419,
			"y": 723.0289902559508,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 319.48138427734375,
			"height": 35,
			"seed": 1141608690,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Kernel Ridge Regression",
			"rawText": "Kernel Ridge Regression",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kernel Ridge Regression",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 270,
			"versionNonce": 1186935738,
			"isDeleted": false,
			"id": "E7EbuIQm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -357.5572455122414,
			"y": 791.5900576880457,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 675.7392578125,
			"height": 75,
			"seed": 763269042,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We project the data via a mapping function into higher dimensional\nfeature space the non-linear relationship can be approximated via a\nlinear function in higher dimensions",
			"rawText": "We project the data via a mapping function into higher dimensional\nfeature space the non-linear relationship can be approximated via a\nlinear function in higher dimensions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We project the data via a mapping function into higher dimensional\nfeature space the non-linear relationship can be approximated via a\nlinear function in higher dimensions",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 101,
			"versionNonce": 1858764006,
			"isDeleted": false,
			"id": "ok8qe8B1hyCJqjN2D7uL3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -95.1770967786976,
			"y": 869.2851265176535,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 169,
			"height": 37,
			"seed": 963767982,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "40f9503bba93e9f1d7f81e424aa67cfff39e912c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 109,
			"versionNonce": 383036538,
			"isDeleted": false,
			"id": "-U3zq2mfiWNYsqR4L2LeG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -124.67709675556705,
			"y": 906.2851266926733,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 228,
			"height": 68,
			"seed": 1592719726,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3a086c8fe6cab6035fdd8b152b3cd5658c35ad7b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 164,
			"versionNonce": 1870000166,
			"isDeleted": false,
			"id": "t0NsaHNNVA0wMvJGzcGg8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -203.0083274926528,
			"y": 965.1511262107384,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 384.6624614772538,
			"height": 36.90488560298376,
			"seed": 375128114,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "699e4dbb71d0adaac511632e8c8376a3d094f4d7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 614,
			"versionNonce": 1597836602,
			"isDeleted": false,
			"id": "eqwserXF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -473.6166110676128,
			"y": 1013.9801964760198,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 925.8790283203125,
			"height": 200,
			"seed": 508875822,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "As we know from before, doing this in infinite dimensions\nis not an easy task, thus we use the kernel trick!\n\nThe prediction of the new datapoint x has to lie somewhere in the span of our current data\nsince its part of the same distribution, it can be thought of as a linear\ncombination of all previous datapoints, thus we only need to compare\nwith previous datapoints to know the answer, since the solution must lie\nwithin the span of the datapoints",
			"rawText": "As we know from before, doing this in infinite dimensions\nis not an easy task, thus we use the kernel trick!\n\nThe prediction of the new datapoint x has to lie somewhere in the span of our current data\nsince its part of the same distribution, it can be thought of as a linear\ncombination of all previous datapoints, thus we only need to compare\nwith previous datapoints to know the answer, since the solution must lie\nwithin the span of the datapoints",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "As we know from before, doing this in infinite dimensions\nis not an easy task, thus we use the kernel trick!\n\nThe prediction of the new datapoint x has to lie somewhere in the span of our current data\nsince its part of the same distribution, it can be thought of as a linear\ncombination of all previous datapoints, thus we only need to compare\nwith previous datapoints to know the answer, since the solution must lie\nwithin the span of the datapoints",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "text",
			"version": 126,
			"versionNonce": 147913574,
			"isDeleted": false,
			"id": "ERPYJTdb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -358.5190494641641,
			"y": 1287.6928384070309,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 750.959228515625,
			"height": 50,
			"seed": 1713787954,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The kernel function k corresponds to an inner product in feature space and\nmeasures the similarity between two data points",
			"rawText": "The kernel function k corresponds to an inner product in feature space and\nmeasures the similarity between two data points",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The kernel function k corresponds to an inner product in feature space and\nmeasures the similarity between two data points",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 267,
			"versionNonce": 1700484602,
			"isDeleted": false,
			"id": "z4oBqpgZXMTmFJSXHgFOz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -246.4914275518626,
			"y": 1338.8442145303245,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 526.9039846440248,
			"height": 47.04499862893079,
			"seed": 321559278,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0cbe4042d56f847a3e32f02510db1bebf8509da3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 824745638,
			"isDeleted": false,
			"id": "aqU5SaVL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -300.60008907360475,
			"y": 1387.0405888474475,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 632.8793334960938,
			"height": 25,
			"seed": 1580718382,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "B2wiizTR81T-uJz-oUADT",
					"type": "arrow"
				}
			],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets take a moment to rewrite our model using the Kernel trick",
			"rawText": "Lets take a moment to rewrite our model using the Kernel trick",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets take a moment to rewrite our model using the Kernel trick",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 193,
			"versionNonce": 1244825274,
			"isDeleted": false,
			"id": "fhBzIVkA6YfvvIx_uavat",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -353.11159334654354,
			"y": 1413.1919645676348,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 228,
			"height": 68,
			"seed": 688213106,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3a086c8fe6cab6035fdd8b152b3cd5658c35ad7b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 248,
			"versionNonce": 220846566,
			"isDeleted": false,
			"id": "eW-jIJKtbGys8v3xwcsVf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -431.4428240836293,
			"y": 1472.0579640857,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 384.6624614772538,
			"height": 36.90488560298376,
			"seed": 1262939698,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "699e4dbb71d0adaac511632e8c8376a3d094f4d7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 581,
			"versionNonce": 375758714,
			"isDeleted": false,
			"id": "mIVHkQugZfysGsuQsL2cf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -46.7803628715959,
			"y": 1441.3876529544534,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 117.13887565365165,
			"height": 37.78673408182313,
			"seed": 2037053170,
			"groupIds": [
				"VM2z6xEtZue1IkjIK886D"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 605,
			"versionNonce": 601992486,
			"isDeleted": false,
			"id": "fgOPVPpZcdmKfc1VbLJSZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 66.57983937387392,
			"y": 1490.510407260823,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 34.00806067364081,
			"height": 60.458774530917005,
			"seed": 110315698,
			"groupIds": [
				"VM2z6xEtZue1IkjIK886D"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					34.00806067364081,
					-30.229387265458502
				],
				[
					0,
					-60.458774530917005
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "image",
			"version": 328,
			"versionNonce": 1178050618,
			"isDeleted": false,
			"id": "rQy38kpRFxoHaqTOA4lel",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 178.91913043683962,
			"y": 1415.379311343106,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 204.3721975625249,
			"height": 63.625306788333226,
			"seed": 394675442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9a8d69aa4b66b05147a84ace85f307d0a8802cd5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 221,
			"versionNonce": 314382438,
			"isDeleted": false,
			"id": "JltoAnVeGPSx3G-pNVs92",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 117.52092190031777,
			"y": 1468.6674094700104,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 347.8430314039874,
			"height": 63.40888593301854,
			"seed": 1782291506,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Gum3lDD4RqSCFYPvgAb0V",
					"type": "arrow"
				}
			],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9af29d0d3cbee0671658956a104be8e0ab097d4c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 353,
			"versionNonce": 1435207930,
			"isDeleted": false,
			"id": "Gum3lDD4RqSCFYPvgAb0V",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 270.32999722723355,
			"y": 1546.3620090508819,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 254.49820541632738,
			"height": 76.64713903399729,
			"seed": 733980782,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JltoAnVeGPSx3G-pNVs92",
				"focus": -0.040644580580430564,
				"gap": 14.285713647852845
			},
			"endBinding": {
				"elementId": "e7iNHCnWR5g1om0aInwv1",
				"gap": 15.403004391113427,
				"focus": -0.1151266518160023
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
					-25.753296531652722,
					40.85005656744897
				],
				[
					-230.00357936889827,
					29.305475363604955
				],
				[
					-254.49820541632738,
					76.64713903399729
				]
			]
		},
		{
			"type": "image",
			"version": 150,
			"versionNonce": 1099504550,
			"isDeleted": false,
			"id": "e7iNHCnWR5g1om0aInwv1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -92.36132432518096,
			"y": 1638.4121524759923,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 192.94922423989033,
			"height": 64.89583517978294,
			"seed": 1361486958,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Gum3lDD4RqSCFYPvgAb0V",
					"type": "arrow"
				},
				{
					"id": "AdYgp5Ingjy_VdztU7yRO",
					"type": "arrow"
				}
			],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e74b26d8eeae19b329fc2ed5a52a9cbd8c01ee02",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 69,
			"versionNonce": 1273256378,
			"isDeleted": false,
			"id": "krwnVc-ziUGlYTzo057PA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -372.0962307422636,
			"y": 1718.1358210780438,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 798,
			"height": 239,
			"seed": 725328046,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6dfb6e5dcb946b9539d8215b87e074c35ca8e2ab",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 116,
			"versionNonce": 376616678,
			"isDeleted": false,
			"id": "BVk5RY7OWzWF4Z0fqrnXE",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -409.7436574215218,
			"y": 1722.3576924587405,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 832.9335610995996,
			"height": 243.24608421492738,
			"seed": 539745458,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1709142810010,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 46,
			"versionNonce": 1214583418,
			"isDeleted": false,
			"id": "l-n_504eWk0Q3S9aZ9ABN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 167.65593496972178,
			"y": 1942.3237720644925,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 87.60370509322058,
			"height": 67.72201315717075,
			"seed": 138188846,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.349120111010961,
					51.56813845913007
				],
				[
					87.60370509322058,
					67.72201315717075
				]
			]
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 705096230,
			"isDeleted": false,
			"id": "XP0cXnhz",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 265.75298280922635,
			"y": 1976.4954300795787,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 201.4397430419922,
			"height": 75,
			"seed": 138995438,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Kernel matrix\ndescribing similarities\nbetween xi and xj",
			"rawText": "Kernel matrix\ndescribing similarities\nbetween xi and xj",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kernel matrix\ndescribing similarities\nbetween xi and xj",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 517,
			"versionNonce": 231781178,
			"isDeleted": false,
			"id": "rrPgJWRk2yWiYNS__9gsS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 497.1599324617409,
			"y": 546.4624723687107,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 199.74895397489533,
			"height": 64.43514644351465,
			"seed": 726927086,
			"groupIds": [
				"t8N1fJJP0nQ1HNGyhEcaM"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 539,
			"versionNonce": 2066920806,
			"isDeleted": false,
			"id": "CJ-R4xnffvklBO86jDZ8E",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 690.4653717922856,
			"y": 630.228162745279,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 57.99163179916319,
			"height": 103.09623430962344,
			"seed": 223410478,
			"groupIds": [
				"t8N1fJJP0nQ1HNGyhEcaM"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					57.99163179916319,
					-51.54811715481172
				],
				[
					0,
					-103.09623430962344
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 171,
			"versionNonce": 243940346,
			"isDeleted": false,
			"id": "rHvnlkzU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1159.914032272789,
			"y": -11.814577123705703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 275.381103515625,
			"height": 35,
			"seed": 2104624750,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Bayesian Regression",
			"rawText": "Bayesian Regression",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bayesian Regression",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 463,
			"versionNonce": 591599782,
			"isDeleted": false,
			"id": "TPaosvHq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 912.1065630875773,
			"y": 41.69380617743052,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 775.5391235351562,
			"height": 125,
			"seed": 2094549486,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Alright, lets have a bit of fun and apply the Bayesian inference to our model.\nhows that fun you say?\n......\nidk, its not\n",
			"rawText": "Alright, lets have a bit of fun and apply the Bayesian inference to our model.\nhows that fun you say?\n......\nidk, its not\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Alright, lets have a bit of fun and apply the Bayesian inference to our model.\nhows that fun you say?\n......\nidk, its not\n",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 394,
			"versionNonce": 2023009466,
			"isDeleted": false,
			"id": "f1Gl8k0JSJf79_DSaLN8J",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1564.1223853996048,
			"y": 203.36047187432942,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 712.4752355884339,
			"height": 55.39764250795598,
			"seed": 1252120882,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "iu3YzeNePbKLIvADGzCef",
					"type": "arrow"
				},
				{
					"id": "G_YdRCZhtEzJKYJLnKsGm",
					"type": "arrow"
				}
			],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3e924c0cc29cb2c13245f68692503d6c971b3951",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 420,
			"versionNonce": 166007782,
			"isDeleted": false,
			"id": "CaPYcKlA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 908.927376803264,
			"y": 354.3107536544627,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 809.8192138671875,
			"height": 25,
			"seed": 1556288818,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can calculate the likelihood of the observed data being plausible by our model",
			"rawText": "We can calculate the likelihood of the observed data being plausible by our model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can calculate the likelihood of the observed data being plausible by our model",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 920,
			"versionNonce": 1100154234,
			"isDeleted": false,
			"id": "PPzzjuCq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 916.9912096006599,
			"y": 464.1781206510402,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 785.0792236328125,
			"height": 75,
			"seed": 1970578350,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "d0YVJ6B-1gp7SH2rM3nHc",
					"type": "arrow"
				}
			],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Obviously we are interested in the Posterior of W, which is, given the knowledge\nof X and y, what W helps us achieve the highest prediction\nusing bayes rule:",
			"rawText": "Obviously we are interested in the Posterior of W, which is, given the knowledge\nof X and y, what W helps us achieve the highest prediction\nusing bayes rule:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Obviously we are interested in the Posterior of W, which is, given the knowledge\nof X and y, what W helps us achieve the highest prediction\nusing bayes rule:",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 249,
			"versionNonce": 421898022,
			"isDeleted": false,
			"id": "9R-PzQgsqJIkJpVNXbIFj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1074.3602280665707,
			"y": 546.0658898756175,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 439.15531411398507,
			"height": 53.4448487899913,
			"seed": 731599086,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b6ff724ce65571a9a8d6ee399c2bcd9a6c07a4ea",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 442,
			"versionNonce": 851985978,
			"isDeleted": false,
			"id": "MOvv08WF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1287.4212797774424,
			"y": 668.8239141096415,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 78.36817932128906,
			"height": 20,
			"seed": 1807563314,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "such that",
			"rawText": "such that",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "such that",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 716,
			"versionNonce": 1903284838,
			"isDeleted": false,
			"id": "92GSdVZg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 946.3334241835203,
			"y": 699.4698776458058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 774.5191650390625,
			"height": 125,
			"seed": 116445294,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Now  that we have our posterior which describes what is\nthe most likely w that describes our data we just need to make a prediction.\nKeep in mind when predicting using this model, we do not just predict\na value of y, instead we predict an entire distribution describing the possible\nvalues of y, with our variance describing our confidence in the mean",
			"rawText": "Now  that we have our posterior which describes what is\nthe most likely w that describes our data we just need to make a prediction.\nKeep in mind when predicting using this model, we do not just predict\na value of y, instead we predict an entire distribution describing the possible\nvalues of y, with our variance describing our confidence in the mean",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Now  that we have our posterior which describes what is\nthe most likely w that describes our data we just need to make a prediction.\nKeep in mind when predicting using this model, we do not just predict\na value of y, instead we predict an entire distribution describing the possible\nvalues of y, with our variance describing our confidence in the mean",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 374,
			"versionNonce": 1964470010,
			"isDeleted": false,
			"id": "xs2tdIPyyor1tLUg_OQut",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 954.372244943422,
			"y": 828.4245598520291,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 328.2015035755601,
			"height": 45.061991337605505,
			"seed": 659387826,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bae80243c920d6aa6fcb608324c045c56b07501d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 403,
			"versionNonce": 496407974,
			"isDeleted": false,
			"id": "yRHKBj4pUf6onENNkvKN-",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1308.3383222976142,
			"y": 828.4245592340679,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 423.7610804527739,
			"height": 45.37550589240229,
			"seed": 1788249134,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a1a11069d27eab66aedd5df69068aeba6905802c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 537,
			"versionNonce": 486768570,
			"isDeleted": false,
			"id": "YzB74rS_S65cog-Lxqmts",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 992.9579694812246,
			"y": 898.174807228554,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 459.9715866039448,
			"height": 71.69310223302226,
			"seed": 624532850,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bb4aa9fe7c626f662eacc6835bc8f5025993f38c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 421,
			"versionNonce": 1187049702,
			"isDeleted": false,
			"id": "fLqiwnxd3TKmVtfSIhKmL",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 985.7559482181262,
			"y": 974.188100226004,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 201.2546310101817,
			"height": 42.33511655553984,
			"seed": 239261678,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "55aeefe0303692ee0b0198cbac8630cec0e99f88",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 537,
			"versionNonce": 917469306,
			"isDeleted": false,
			"id": "qRK6U-Rf3feykOT-T1VLY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1219.3671819505646,
			"y": 972.2416056395803,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 453.7161997405064,
			"height": 44.28161108578516,
			"seed": 1926069038,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "300a01edc8b8a096065d3a9ec925eff22ba95dc7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 1753080870,
			"isDeleted": false,
			"id": "P0T8vcRd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1189.255349257034,
			"y": 1063.0193234432638,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 244.8049774169922,
			"height": 35,
			"seed": 135938866,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Gaussian Process",
			"rawText": "Gaussian Process",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gaussian Process",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 896,
			"versionNonce": 1373526330,
			"isDeleted": false,
			"id": "w0GU2lIm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 852.6683360190785,
			"y": 1108.9768136149164,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 917.97900390625,
			"height": 300,
			"seed": 318163378,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "iu3YzeNePbKLIvADGzCef",
					"type": "arrow"
				}
			],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The model we have just seen is called the Gaussian Process, which is an enhancement\nto the Bayesian linear regression model using kernels\n(Same algorithm as before but its a different way to view it)\nThe Gaussian process model is quite a useful modelling process as it instead of outputting\na single output for each input, it outputs a distribution based off of how certain/uncertain\nit is with its prediction (mean).\nThis model can be used for a wide variety of different domains and areas, it also offers\nefficient hyper-parameter selection.\n\nGP can be thought of as a model that outputs potential functions that describe our data\nand we try to minimize it to only output the most likely functions.\n(i.e it works in the function space)",
			"rawText": "The model we have just seen is called the Gaussian Process, which is an enhancement\nto the Bayesian linear regression model using kernels\n(Same algorithm as before but its a different way to view it)\nThe Gaussian process model is quite a useful modelling process as it instead of outputting\na single output for each input, it outputs a distribution based off of how certain/uncertain\nit is with its prediction (mean).\nThis model can be used for a wide variety of different domains and areas, it also offers\nefficient hyper-parameter selection.\n\nGP can be thought of as a model that outputs potential functions that describe our data\nand we try to minimize it to only output the most likely functions.\n(i.e it works in the function space)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The model we have just seen is called the Gaussian Process, which is an enhancement\nto the Bayesian linear regression model using kernels\n(Same algorithm as before but its a different way to view it)\nThe Gaussian process model is quite a useful modelling process as it instead of outputting\na single output for each input, it outputs a distribution based off of how certain/uncertain\nit is with its prediction (mean).\nThis model can be used for a wide variety of different domains and areas, it also offers\nefficient hyper-parameter selection.\n\nGP can be thought of as a model that outputs potential functions that describe our data\nand we try to minimize it to only output the most likely functions.\n(i.e it works in the function space)",
			"lineHeight": 1.25,
			"baseline": 293
		},
		{
			"type": "image",
			"version": 186,
			"versionNonce": 79327078,
			"isDeleted": false,
			"id": "3B3rvjLG1GYcZ4d8tDXc_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1030.9076944516557,
			"y": 1465.8917960265312,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 763,
			"height": 116,
			"seed": 556692292,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e864a3a7d9439ebad047375155c2c76886fe7b0c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 31,
			"versionNonce": 234037754,
			"isDeleted": false,
			"id": "d0C557kYfDlrVCFJcx1Fu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1086.1429049693068,
			"y": 1417.3225377499245,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 470,
			"height": 54,
			"seed": 257331196,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7b03ae2880e769e85dbf4632e264920cb6349940",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 63,
			"versionNonce": 1472434854,
			"isDeleted": false,
			"id": "yhxW2VI8cLjAGfpuaClEJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1104.7386647518965,
			"y": 1492.7198390558046,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 109.00063450415223,
			"height": 19.355252855877552,
			"seed": 745380092,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-69.27143127366685,
					-8.149580149843132
				],
				[
					-109.00063450415223,
					-19.355252855877552
				]
			]
		},
		{
			"type": "text",
			"version": 93,
			"versionNonce": 636539578,
			"isDeleted": false,
			"id": "wj09WR4o",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 787.9188172434162,
			"y": 1439.7475680818238,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 195.59976196289062,
			"height": 50,
			"seed": 1287983996,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "mean of distribution\nof output functions",
			"rawText": "mean of distribution\nof output functions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "mean of distribution\nof output functions",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 47,
			"versionNonce": 205934054,
			"isDeleted": false,
			"id": "zusqzXFPg9vsLqhzT30Te",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1053.8037888153767,
			"y": 1546.7108075485157,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 118.16891217272587,
			"height": 16.299160299686264,
			"seed": 1880407748,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-75.3836163860492,
					0
				],
				[
					-118.16891217272587,
					16.299160299686264
				]
			]
		},
		{
			"type": "text",
			"version": 67,
			"versionNonce": 2088397690,
			"isDeleted": false,
			"id": "ee7tMv1S",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 800.4410639023203,
			"y": 1563.009967848202,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 229.6397247314453,
			"height": 50,
			"seed": 1234891844,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Variance of distribution\nof output functions",
			"rawText": "Variance of distribution\nof output functions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Variance of distribution\nof output functions",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 319,
			"versionNonce": 1867489574,
			"isDeleted": false,
			"id": "aKTCKsW2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 826.9082961810053,
			"y": 1618.9086736405993,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 969.4990844726562,
			"height": 75,
			"seed": 531992828,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "There are many GP kernels and distributions to describe the output functions\nAssuming that the mean is 0 (Not necessary), our covariance determines the functions that have\nhigher prior probability (more likely to be included)",
			"rawText": "There are many GP kernels and distributions to describe the output functions\nAssuming that the mean is 0 (Not necessary), our covariance determines the functions that have\nhigher prior probability (more likely to be included)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "There are many GP kernels and distributions to describe the output functions\nAssuming that the mean is 0 (Not necessary), our covariance determines the functions that have\nhigher prior probability (more likely to be included)",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 237,
			"versionNonce": 668134458,
			"isDeleted": false,
			"id": "zh3E6DRswjNw0zc9G5RGU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 972.1117291405303,
			"y": 1699.8073799428182,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 679.092218585347,
			"height": 242.85921270036516,
			"seed": 1758553028,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ab50265c9d47e4f16cf82cdef52af805a9dfb5c9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 154,
			"versionNonce": 608996454,
			"isDeleted": false,
			"id": "MlSi5VUh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 780.1483779306542,
			"y": 1948.5652989397333,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 1063.0189208984375,
			"height": 25,
			"seed": 554296572,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Firstly we specify what kind of distributions we use by setting the covariance function to something prior",
			"rawText": "1) Firstly we specify what kind of distributions we use by setting the covariance function to something prior",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Firstly we specify what kind of distributions we use by setting the covariance function to something prior",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 154,
			"versionNonce": 990210598,
			"isDeleted": false,
			"id": "nzdH7XorsjBYWokqcXf_X",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1140.6660258125742,
			"y": 1975.0634403764475,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 341.0174285104256,
			"height": 146.06302045518228,
			"seed": 975417540,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142952071,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7e6a7d7d704abc9aab8c5614cc2b52febdb53790",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 559,
			"versionNonce": 1493831590,
			"isDeleted": false,
			"id": "NmnNUoTu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 818.8651490007401,
			"y": 2168.0626747090605,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 1014.4990234375,
			"height": 100,
			"seed": 921403588,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2) then incorperate our current observed m datapoints into the prior knowledge (cov function) in order\nto then eliminate all the functions that do not agree with its y outputs.\nKeep in mind we also add a bit of i.i.d noise to allow fluctuations because we assume that our ys\nare some noisy output of a true function",
			"rawText": "2) then incorperate our current observed m datapoints into the prior knowledge (cov function) in order\nto then eliminate all the functions that do not agree with its y outputs.\nKeep in mind we also add a bit of i.i.d noise to allow fluctuations because we assume that our ys\nare some noisy output of a true function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2) then incorperate our current observed m datapoints into the prior knowledge (cov function) in order\nto then eliminate all the functions that do not agree with its y outputs.\nKeep in mind we also add a bit of i.i.d noise to allow fluctuations because we assume that our ys\nare some noisy output of a true function",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 483,
			"versionNonce": 1254931558,
			"isDeleted": false,
			"id": "n5Ao9yh8q3lFxHWiFqsMG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1189.537875050907,
			"y": 2641.277743062005,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 318.59015458573043,
			"height": 38.7848883843498,
			"seed": 80248444,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709144308851,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "81996919842e04d9784ec7d10f21bf4fa2117353",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 721,
			"versionNonce": 537149350,
			"isDeleted": false,
			"id": "6tUK2POmiI7B3rVbB99O8",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1120.737671284471,
			"y": 2682.62091740995,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 483.52925952722865,
			"height": 58.41293068114172,
			"seed": 635490756,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8tFtdcZOvAXAH8hRklKAU",
					"type": "arrow"
				},
				{
					"id": "FZADRbDKWA9zjzAPXmYa_",
					"type": "arrow"
				}
			],
			"updated": 1709144308851,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "df4dfd813b0edf8966f765547ad297ed10eccca4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 59,
			"versionNonce": 1692065318,
			"isDeleted": false,
			"id": "AbE5r7WCrYAL6E4YqKPSR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1631.9102467517596,
			"y": 1991.077886863502,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 460.8358448597942,
			"height": 92.00524025696222,
			"seed": 1839134276,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "8tLISFhV",
				"focus": -0.47598713586880226,
				"gap": 21.661201049256988
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
					267.9652622484027,
					37.952161605996935
				],
				[
					460.8358448597942,
					-54.05307865096529
				]
			]
		},
		{
			"type": "text",
			"version": 362,
			"versionNonce": 291897146,
			"isDeleted": false,
			"id": "8tLISFhV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1939.1193460706077,
			"y": 1740.3636071632798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 399.9395751953125,
			"height": 175,
			"seed": 274687868,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "AbE5r7WCrYAL6E4YqKPSR",
					"type": "arrow"
				}
			],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Determining what functions get samples\nis something that is determined by\nthe kernel choice\nGP will sample functions with nearby y's\nfor x's determined \"similar\" by the kernel\nfunction provided (remember that kernels\nmeasure similarities between 2 objects)",
			"rawText": "Determining what functions get samples\nis something that is determined by\nthe kernel choice\nGP will sample functions with nearby y's\nfor x's determined \"similar\" by the kernel\nfunction provided (remember that kernels\nmeasure similarities between 2 objects)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Determining what functions get samples\nis something that is determined by\nthe kernel choice\nGP will sample functions with nearby y's\nfor x's determined \"similar\" by the kernel\nfunction provided (remember that kernels\nmeasure similarities between 2 objects)",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "arrow",
			"version": 65,
			"versionNonce": 526920038,
			"isDeleted": false,
			"id": "hFjCGOnM2VuAO0gWcpvcj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1975.7798322121562,
			"y": 2004.8786729020464,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 203.5615940685293,
			"height": 54.05307865096529,
			"seed": 1583924676,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
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
					69.00393019272133,
					-18.40104805139231
				],
				[
					203.5615940685293,
					35.65203059957298
				]
			]
		},
		{
			"type": "text",
			"version": 327,
			"versionNonce": 160827386,
			"isDeleted": false,
			"id": "Ht1wvleG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2138.4936188613674,
			"y": 1979.5772318313818,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 500.3194580078125,
			"height": 125,
			"seed": 676636612,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Kernels also have hyperparameters that\nchange the function outputs depending\non their values, for example RBF has\n a hyperparameter called \"length scale\"\nwhich scales up or down the distances between x's",
			"rawText": "Kernels also have hyperparameters that\nchange the function outputs depending\non their values, for example RBF has\n a hyperparameter called \"length scale\"\nwhich scales up or down the distances between x's",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Kernels also have hyperparameters that\nchange the function outputs depending\non their values, for example RBF has\n a hyperparameter called \"length scale\"\nwhich scales up or down the distances between x's",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 85,
			"versionNonce": 145362086,
			"isDeleted": false,
			"id": "z7WVFgbcZ39Gkey2w8YK8",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2103.8195290537074,
			"y": 2110.2783692660823,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 270.00117871798665,
			"height": 203.44626631691432,
			"seed": 2073552580,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "24a024f158ce93378f6328aaafecfb77d8285316",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 178,
			"versionNonce": 944175290,
			"isDeleted": false,
			"id": "re3l9jdM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2079.4965012810835,
			"y": 2326.4330199941364,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 292.93963623046875,
			"height": 100,
			"seed": 1716907460,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "small length means x values\nare quite similar which means\nthe functions fluctuates less\n/slowly",
			"rawText": "small length means x values\nare quite similar which means\nthe functions fluctuates less\n/slowly",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "small length means x values\nare quite similar which means\nthe functions fluctuates less\n/slowly",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 110,
			"versionNonce": 239962086,
			"isDeleted": false,
			"id": "dYs4w7mxFD04D2h2C0Z3B",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2443.288066462711,
			"y": 2124.6521932269534,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 233.54456323340133,
			"height": 192.37257336246736,
			"seed": 1639656444,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1d766f0140a7af9de03ed0db474d02152c731562",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 321,
			"versionNonce": 1830539642,
			"isDeleted": false,
			"id": "Y5eFXo6N",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2422.310500489573,
			"y": 2317.0247671483144,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 275.49969482421875,
			"height": 100,
			"seed": 1066820420,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "large length means x values\nare distant which means\nthe functions will fluctuate\nmore frequently",
			"rawText": "large length means x values\nare distant which means\nthe functions will fluctuate\nmore frequently",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "large length means x values\nare distant which means\nthe functions will fluctuate\nmore frequently",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "line",
			"version": 47,
			"versionNonce": 1616878374,
			"isDeleted": false,
			"id": "SBOb04nnj-ad6Ib37Oy15",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2361.0517757881853,
			"y": 1795.5667513174571,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 194.36107004283258,
			"height": 5.750327516060224,
			"seed": 1565024508,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					194.36107004283258,
					5.750327516060224
				]
			]
		},
		{
			"type": "text",
			"version": 343,
			"versionNonce": 190288442,
			"isDeleted": false,
			"id": "4G8nqwrv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2573.717253313879,
			"y": 1731.1630831375835,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 460.219482421875,
			"height": 150,
			"seed": 390721860,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "picking the right kernel is not\nalways just finding a good kernel function\nthere are a plethora of ways to find good\nkernels to describe your data, like combining\ntwo kernels with addition, multiplication, scalar\nmultiplication etc...",
			"rawText": "picking the right kernel is not\nalways just finding a good kernel function\nthere are a plethora of ways to find good\nkernels to describe your data, like combining\ntwo kernels with addition, multiplication, scalar\nmultiplication etc...",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "picking the right kernel is not\nalways just finding a good kernel function\nthere are a plethora of ways to find good\nkernels to describe your data, like combining\ntwo kernels with addition, multiplication, scalar\nmultiplication etc...",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "line",
			"version": 327,
			"versionNonce": 625821286,
			"isDeleted": false,
			"id": "tAmV6_lbh9jF8iSrgtyIl",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1311.5703906436916,
			"y": 2336.758822354894,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 109.11722716922236,
			"height": 42.10857772809368,
			"seed": 1439216124,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-50.858526644545464,
					-39.654028061127974
				],
				[
					-109.11722716922236,
					-42.10857772809368
				]
			]
		},
		{
			"type": "text",
			"version": 222,
			"versionNonce": 366820090,
			"isDeleted": false,
			"id": "US23Wxos",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 979.850444765169,
			"y": 2292.2992211483147,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 211.79248046875,
			"height": 20,
			"seed": 746005628,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "matrix of input datapoints",
			"rawText": "matrix of input datapoints",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "matrix of input datapoints",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 291,
			"versionNonce": 769886630,
			"isDeleted": false,
			"id": "tGv-uP4weZJYOLxUP1SLf",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1336.6146989510016,
			"y": 2403.045619487418,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 136.88835977300846,
			"height": 44.248908361177655,
			"seed": 1210458364,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-54.986884795947844,
					38.31232638796564
				],
				[
					-136.88835977300846,
					44.248908361177655
				]
			]
		},
		{
			"type": "text",
			"version": 266,
			"versionNonce": 1842369658,
			"isDeleted": false,
			"id": "1PAcu8c3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 942.1744109889423,
			"y": 2434.8812066663813,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 250.0965118408203,
			"height": 40,
			"seed": 1601806404,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709143611381,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "previously unobserved datapoint\n",
			"rawText": "previously unobserved datapoint\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "previously unobserved datapoint\n",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 164,
			"versionNonce": 693069030,
			"isDeleted": false,
			"id": "qnRpmBKlRcLtzlCNmtfJf",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1131.5120495577357,
			"y": 2354.2637244863727,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 47.4720344353359,
			"height": 3.4615025109101225,
			"seed": 1539234372,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-47.4720344353359,
					-3.4615025109101225
				]
			]
		},
		{
			"type": "text",
			"version": 272,
			"versionNonce": 1232451706,
			"isDeleted": false,
			"id": "jm7gVgbr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 753.1494967499615,
			"y": 2338.720594677598,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 324.0646667480469,
			"height": 20,
			"seed": 642267332,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709143092539,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "output functions of observed datapoints",
			"rawText": "output functions of observed datapoints",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "output functions of observed datapoints",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 147,
			"versionNonce": 1495128102,
			"isDeleted": false,
			"id": "bxKxrsuxQP4kyWtgTPNDT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1124.589044535916,
			"y": 2382.450244932353,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 62.30704519637834,
			"height": 1.4835010761044032,
			"seed": 1608354500,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-62.30704519637834,
					1.4835010761044032
				]
			]
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 845653306,
			"isDeleted": false,
			"id": "EOCI0S6O",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 720.3900421665506,
			"y": 2377.0107409866378,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 332.68865966796875,
			"height": 20,
			"seed": 1484298692,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "unobserved true function output estimate",
			"rawText": "unobserved true function output estimate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "unobserved true function output estimate",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 159,
			"versionNonce": 1161552742,
			"isDeleted": false,
			"id": "Tvw9L1cSyP66sKBAjblPi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1469.7807275962618,
			"y": 2334.440323091077,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 100.27772527403704,
			"height": 34.071196232105194,
			"seed": 1288991484,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					47.235067503600476,
					-29.812296703092215
				],
				[
					100.27772527403704,
					-34.071196232105194
				]
			]
		},
		{
			"type": "text",
			"version": 265,
			"versionNonce": 314829030,
			"isDeleted": false,
			"id": "IR3uJjFE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1545.5018853741308,
			"y": 2269.008139418057,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 217.92042541503906,
			"height": 80,
			"seed": 1772313084,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709143309365,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "matrix containing all\nkernel similarities\nbetween previously observed\ndata and new data",
			"rawText": "matrix containing all\nkernel similarities\nbetween previously observed\ndata and new data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "matrix containing all\nkernel similarities\nbetween previously observed\ndata and new data",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 790,
			"versionNonce": 1170813862,
			"isDeleted": false,
			"id": "niLrHNBZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 860.1814456563535,
			"y": 2474.244475289966,
			"strokeColor": "#1971c2",
			"backgroundColor": "#b2f2bb",
			"width": 983.3461303710938,
			"height": 120,
			"seed": 14337860,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "7mkgS5WvVNXZ-t5R2Vhvx",
					"type": "arrow"
				}
			],
			"updated": 1709143637050,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "if a vector is normally distributed and we only observe it partially (using a well known\nmathematical result) we can know the distribution over the unobserved elements given the observed elements\n(Bayesian updating) where y is the observed part and f* is the unobserved part\nthis leads us to be able to infer f* from the following distribution\nthink of it as slicing the multivariate distribution over specific values and getting another multivariate (smaller dimensional)\ndistribution of possible values in it",
			"rawText": "if a vector is normally distributed and we only observe it partially (using a well known\nmathematical result) we can know the distribution over the unobserved elements given the observed elements\n(Bayesian updating) where y is the observed part and f* is the unobserved part\nthis leads us to be able to infer f* from the following distribution\nthink of it as slicing the multivariate distribution over specific values and getting another multivariate (smaller dimensional)\ndistribution of possible values in it",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "if a vector is normally distributed and we only observe it partially (using a well known\nmathematical result) we can know the distribution over the unobserved elements given the observed elements\n(Bayesian updating) where y is the observed part and f* is the unobserved part\nthis leads us to be able to infer f* from the following distribution\nthink of it as slicing the multivariate distribution over specific values and getting another multivariate (smaller dimensional)\ndistribution of possible values in it",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "text",
			"version": 453,
			"versionNonce": 1595091046,
			"isDeleted": false,
			"id": "eoovYAsW",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1014.1072672696384,
			"y": 3165.606468011312,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 705.5792236328125,
			"height": 175,
			"seed": 913897340,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709144078676,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Some Cons:\n\n1) requires inverting Kxx matrix which takes O(N^3) time\n\n2) Designing the kernels is complex and requires time and understanding\n\n3) certain kernels dont work in higher dimensions",
			"rawText": "Some Cons:\n\n1) requires inverting Kxx matrix which takes O(N^3) time\n\n2) Designing the kernels is complex and requires time and understanding\n\n3) certain kernels dont work in higher dimensions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Some Cons:\n\n1) requires inverting Kxx matrix which takes O(N^3) time\n\n2) Designing the kernels is complex and requires time and understanding\n\n3) certain kernels dont work in higher dimensions",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "ellipse",
			"version": 39,
			"versionNonce": 167428582,
			"isDeleted": false,
			"id": "L-Bfg5c-vz2aoJsDSY4Cc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -444.1228751112662,
			"y": 1466.2619152029856,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 56.32795755910422,
			"height": 54.36302880704238,
			"seed": 368685103,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "B2wiizTR81T-uJz-oUADT",
					"type": "arrow"
				}
			],
			"updated": 1709142810011,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 390,
			"versionNonce": 964114298,
			"isDeleted": false,
			"id": "B2wiizTR81T-uJz-oUADT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -397.61956131247086,
			"y": 1514.7301577538428,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 718.5089470039228,
			"height": 127.06539263332775,
			"seed": 617370735,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "L-Bfg5c-vz2aoJsDSY4Cc",
				"focus": 0.7201941290598345,
				"gap": 1
			},
			"endBinding": {
				"elementId": "aqU5SaVL",
				"focus": -1.5118400402316639,
				"gap": 10.337917559492098
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
					391.02082166029345,
					34.713741286424465
				],
				[
					545.5952168224866,
					-88.42179384278006
				],
				[
					718.5089470039228,
					-92.35165134690328
				]
			]
		},
		{
			"type": "line",
			"version": 57,
			"versionNonce": 643142950,
			"isDeleted": false,
			"id": "c1gcNkU0jbpg7BasMnUL_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 317.442151597685,
			"y": 1326.4577611357277,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 135.86162898889938,
			"height": 34.83631512535885,
			"seed": 2098846945,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					118.44347142621996,
					-4.877084117550112
				],
				[
					135.86162898889938,
					-34.83631512535885
				]
			]
		},
		{
			"type": "text",
			"version": 481,
			"versionNonce": 1129723962,
			"isDeleted": false,
			"id": "ub04JIU1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 409.01108136655944,
			"y": 1221.0619038151472,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 250.82716369628906,
			"height": 64.57499732387247,
			"seed": 994850433,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810011,
			"link": null,
			"locked": false,
			"fontSize": 10.331999571819596,
			"fontFamily": 1,
			"text": "Meaning we figure out how similar our point\nis to all previously seen datapoints and quantify\nthat similarity, after that we just have to\nfigure out the correct linear combination\nof the similarities through minimizing the error",
			"rawText": "Meaning we figure out how similar our point\nis to all previously seen datapoints and quantify\nthat similarity, after that we just have to\nfigure out the correct linear combination\nof the similarities through minimizing the error",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Meaning we figure out how similar our point\nis to all previously seen datapoints and quantify\nthat similarity, after that we just have to\nfigure out the correct linear combination\nof the similarities through minimizing the error",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 170,
			"versionNonce": 1853096038,
			"isDeleted": false,
			"id": "I5JPQGOb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 279.2991422942017,
			"y": 1535.136913224637,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 214.5604705810547,
			"height": 80,
			"seed": 1263423535,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "K \"Covariance\" gram matrix\nin feature space, explaining\nsimilarities and structure\nin our observed dataset",
			"rawText": "K \"Covariance\" gram matrix\nin feature space, explaining\nsimilarities and structure\nin our observed dataset",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "K \"Covariance\" gram matrix\nin feature space, explaining\nsimilarities and structure\nin our observed dataset",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 44,
			"versionNonce": 1662460154,
			"isDeleted": false,
			"id": "AdYgp5Ingjy_VdztU7yRO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -41.00468356711946,
			"y": 1637.516872540997,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 108.18414528601022,
			"height": 42.040470966066096,
			"seed": 145964815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "e7iNHCnWR5g1om0aInwv1",
				"focus": -0.1382814686699089,
				"gap": 1
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
					-35.31399561149556,
					-42.040470966066096
				],
				[
					-108.18414528601022,
					-38.677233288780826
				]
			]
		},
		{
			"type": "text",
			"version": 124,
			"versionNonce": 1445135270,
			"isDeleted": false,
			"id": "PhWi6SUW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -372.5621461617576,
			"y": 1575.296975511219,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 203.47244262695312,
			"height": 60,
			"seed": 1104952481,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "How our current point\ncompares to the dataset\n(similarities)",
			"rawText": "How our current point\ncompares to the dataset\n(similarities)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How our current point\ncompares to the dataset\n(similarities)",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 1044,
			"versionNonce": 1413280186,
			"isDeleted": false,
			"id": "iu3YzeNePbKLIvADGzCef",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1795.1519152377487,
			"y": 1347.5407118450207,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 130.6222015762171,
			"height": 69.12862127817402,
			"seed": 1912823713,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "w0GU2lIm",
				"focus": 0.8766440862178345,
				"gap": 24.504575312419945
			},
			"endBinding": {
				"elementId": "zGoqLIA7",
				"focus": 0.024527366650685136,
				"gap": 5.746354597211166
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
					130.6222015762171,
					-69.12862127817402
				]
			]
		},
		{
			"type": "text",
			"version": 609,
			"versionNonce": 1334812390,
			"isDeleted": false,
			"id": "zGoqLIA7",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1890.1604914669142,
			"y": 1132.6657359696355,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 373.120849609375,
			"height": 140,
			"seed": 948440897,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "iu3YzeNePbKLIvADGzCef",
					"type": "arrow"
				}
			],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "A key note to keep in mind here\nwe are no longer thinking about\npredicting a single points, instead\nwe are trying to produce an entire function\nas an output and everytime we speak\nof outputs we are talking about a distribution\nof all possible functions",
			"rawText": "A key note to keep in mind here\nwe are no longer thinking about\npredicting a single points, instead\nwe are trying to produce an entire function\nas an output and everytime we speak\nof outputs we are talking about a distribution\nof all possible functions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A key note to keep in mind here\nwe are no longer thinking about\npredicting a single points, instead\nwe are trying to produce an entire function\nas an output and everytime we speak\nof outputs we are talking about a distribution\nof all possible functions",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "arrow",
			"version": 776,
			"versionNonce": 1501774502,
			"isDeleted": false,
			"id": "uLOkulI1gX70J3ybqHerd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2211.2616743171416,
			"y": 1164.4662787804002,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 131.0388106908581,
			"height": 1.9066540042256293,
			"seed": 1373488993,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143319490,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "OowcLKFwMbnB8rZ1VLAAz",
				"focus": 0.10605584350442708,
				"gap": 2.9979538779193717
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
					131.0388106908581,
					1.9066540042256293
				]
			]
		},
		{
			"type": "arrow",
			"version": 1005,
			"versionNonce": 126655866,
			"isDeleted": false,
			"id": "d0YVJ6B-1gp7SH2rM3nHc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1102.4063196881175,
			"y": 419.3350990219068,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 66.41113789019437,
			"height": 5.57434732056015,
			"seed": 1653252751,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "mrD5TEyNC6dz9CgcqfNCj",
				"focus": 0.31014304597929965,
				"gap": 6.423034861549809
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
					-66.41113789019437,
					5.57434732056015
				]
			]
		},
		{
			"type": "text",
			"version": 366,
			"versionNonce": 2066845478,
			"isDeleted": false,
			"id": "YEXFHVOi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 822.9772034203431,
			"y": 408.44676416535674,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 192.41641235351562,
			"height": 40,
			"seed": 1681198561,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Likelihood of predicting y\ngiven X and w",
			"rawText": "Likelihood of predicting y\ngiven X and w",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Likelihood of predicting y\ngiven X and w",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 539,
			"versionNonce": 193660666,
			"isDeleted": false,
			"id": "OIAGE9HZ0KOC0wEEoq9T7",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1515.0288973476522,
			"y": 629.618506545938,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 150.81416200657827,
			"height": 0.8768265232940848,
			"seed": 969366319,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "q2nLzyox",
				"focus": -0.09986518479995746,
				"gap": 15.27783430283057
			},
			"endBinding": {
				"elementId": "X0FElNLB",
				"focus": -0.1697348136413679,
				"gap": 13.289840976299047
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
					150.81416200657827,
					0.8768265232940848
				]
			]
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 197688742,
			"isDeleted": false,
			"id": "FdKztXUC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1537.568442534361,
			"y": 583.1467008113528,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 89.95219421386719,
			"height": 40,
			"seed": 1708475233,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "How did we\nderive this?",
			"rawText": "How did we\nderive this?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How did we\nderive this?",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 291,
			"versionNonce": 1363417018,
			"isDeleted": false,
			"id": "X0FElNLB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1679.1329003305295,
			"y": 607.6978434635865,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 215.4244384765625,
			"height": 40,
			"seed": 2131097889,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "OIAGE9HZ0KOC0wEEoq9T7",
					"type": "arrow"
				},
				{
					"id": "WhNZvnkV4Y8eUNKMeWbQK",
					"type": "arrow"
				}
			],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Im glad you asked because\nI dont really get it",
			"rawText": "Im glad you asked because\nI dont really get it",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Im glad you asked because\nI dont really get it",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 754,
			"versionNonce": 1718999270,
			"isDeleted": false,
			"id": "WhNZvnkV4Y8eUNKMeWbQK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1899.078914550451,
			"y": 631.372159592526,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 159.58242723951912,
			"height": 1.1368683772161603e-13,
			"seed": 1313222991,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "X0FElNLB",
				"focus": 0.18371580644697005,
				"gap": 4.521575743358881
			},
			"endBinding": {
				"elementId": "DqzQVvBKeXIYmQkVTEtVV",
				"focus": 0.04496546273302286,
				"gap": 17.33711039339687
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
					159.58242723951912,
					1.1368683772161603e-13
				]
			]
		},
		{
			"type": "image",
			"version": 268,
			"versionNonce": 1193087098,
			"isDeleted": false,
			"id": "DqzQVvBKeXIYmQkVTEtVV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2075.9984521833667,
			"y": 594.1258126391142,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 409,
			"height": 78,
			"seed": 1279284033,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "WhNZvnkV4Y8eUNKMeWbQK",
					"type": "arrow"
				}
			],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ffbe3f8eb4f7bed6df413eaa5d89168d558d6cd1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 256,
			"versionNonce": 290835494,
			"isDeleted": false,
			"id": "SJrvZSui",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1968.2789243328261,
			"y": 570.945644027977,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 641.26513671875,
			"height": 40,
			"seed": 1605079137,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The posterior mean value of the weights w is the choice of w that minimizes the\nquadratic form",
			"rawText": "The posterior mean value of the weights w is the choice of w that minimizes the\nquadratic form",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The posterior mean value of the weights w is the choice of w that minimizes the\nquadratic form",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 323,
			"versionNonce": 819523898,
			"isDeleted": false,
			"id": "7hMXxv-0_vfzJrLhWaMrT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2067.8324722548937,
			"y": 724.3094950758104,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 506,
			"height": 114,
			"seed": 1675247631,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4bd0d0e7809ad36b48ded0eb1af78ee3bd021327",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 353,
			"versionNonce": 441800550,
			"isDeleted": false,
			"id": "kExQub7F",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2129.405618265331,
			"y": 687.4890570833459,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 417.728759765625,
			"height": 20,
			"seed": 2085488737,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": " Let                And t be the vector of targets",
			"rawText": " Let                And t be the vector of targets",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " Let                And t be the vector of targets",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 337,
			"versionNonce": 1641724410,
			"isDeleted": false,
			"id": "RNux4LzR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2177.3105778109007,
			"y": 681.8675117707936,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 56,
			"height": 38,
			"seed": 67867,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2b902bad96b731902a64ec26ebb922751f929ec5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 303,
			"versionNonce": 1237416614,
			"isDeleted": false,
			"id": "8Yz4gS1i",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2219.1205955527835,
			"y": 844.4410047529827,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 226.35247802734375,
			"height": 20,
			"seed": 240644751,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The solution is then given by",
			"rawText": "The solution is then given by",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The solution is then given by",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 258,
			"versionNonce": 1227188922,
			"isDeleted": false,
			"id": "d-nVFq7jP16AIM73VY90t",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2200.2458292440692,
			"y": 870.5432900574499,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 278,
			"height": 46,
			"seed": 1571173295,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5035c4a7758ca2c64f5653d13056b527aa4bade4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 378,
			"versionNonce": 1447507430,
			"isDeleted": false,
			"id": "CxpjL-JS-X2FMKobbuLB-",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2113.179637656231,
			"y": 911.2096171478538,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 461.793187360046,
			"height": 33.88698209404654,
			"seed": 1378231617,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "25e018f8a616ec7fa4f22805d926126b3c9ecf9b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 107,
			"versionNonce": 2103182202,
			"isDeleted": false,
			"id": "zrKLT5Xr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1324.9351101009693,
			"y": 2315.9682678294735,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 23.936050415039062,
			"height": 20,
			"seed": 1935995137,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "nxn",
			"rawText": "nxn",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "nxn",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 102,
			"versionNonce": 418613542,
			"isDeleted": false,
			"id": "LhfWegPy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1349.3804001773483,
			"y": 2408.7698320083205,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 20.800048828125,
			"height": 20,
			"seed": 1707345615,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1xn",
			"rawText": "1xn",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1xn",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 105,
			"versionNonce": 1220641850,
			"isDeleted": false,
			"id": "Mov3M2Ak",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1461.6476583059045,
			"y": 2304.198313348254,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 20.800048828125,
			"height": 20,
			"seed": 1789302561,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "nx1",
			"rawText": "nx1",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "nx1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 1093891174,
			"isDeleted": false,
			"id": "IsaQgw4W",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1497.8629028635035,
			"y": 2407.41176033741,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 17.664047241210938,
			"height": 20,
			"seed": 410987599,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1x1",
			"rawText": "1x1",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1x1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 540,
			"versionNonce": 179066086,
			"isDeleted": false,
			"id": "OSWY0Tc7",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2500.0366493959054,
			"y": 2777.2833209242926,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 457.2809143066406,
			"height": 80,
			"seed": 59184335,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709144211831,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "I encourage you to read about the first few\nsections of this paper if you want to understand\nmore because quite frankly my brain is currently too fried\nto actually properly get it and thus properly explain it",
			"rawText": "I encourage you to read about the first few\nsections of this paper if you want to understand\nmore because quite frankly my brain is currently too fried\nto actually properly get it and thus properly explain it",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "I encourage you to read about the first few\nsections of this paper if you want to understand\nmore because quite frankly my brain is currently too fried\nto actually properly get it and thus properly explain it",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "embeddable",
			"version": 91,
			"versionNonce": 1581751782,
			"isDeleted": false,
			"id": "9rEH8yMKaLCrCNfwTfa50",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2296.933303586502,
			"y": 2876.4816739989174,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 900.3055716610456,
			"height": 999.404627316363,
			"seed": 1231644673,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "_kzljuGp_BbcnJcdqR8po",
					"type": "arrow"
				}
			],
			"updated": 1709144199277,
			"link": "https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=28667c276ba78ab1d855064d5456d50d9932b775",
			"locked": false,
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 350,
			"versionNonce": 2123052218,
			"isDeleted": false,
			"id": "_kzljuGp_BbcnJcdqR8po",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3214.584558724202,
			"y": 3486.244695844648,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 240.13522721040772,
			"height": 3.136150502032251,
			"seed": 1663938849,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143950401,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9rEH8yMKaLCrCNfwTfa50",
				"focus": 0.2021867911112012,
				"gap": 17.34568347665413
			},
			"endBinding": {
				"elementId": "gww8m6w24ECTAxnvxBi3U",
				"focus": -0.18501637313036406,
				"gap": 26.250000000000057
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
					240.13522721040772,
					3.136150502032251
				]
			]
		},
		{
			"type": "text",
			"version": 170,
			"versionNonce": 1400852134,
			"isDeleted": false,
			"id": "rVQUmrw3",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3235.930006356064,
			"y": 3425.901427428831,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.8196716308594,
			"height": 25,
			"seed": 1124901807,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709143954201,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ALso this video is kinda nice",
			"rawText": "ALso this video is kinda nice",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ALso this video is kinda nice",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "embeddable",
			"version": 241,
			"versionNonce": 38353722,
			"isDeleted": false,
			"id": "gww8m6w24ECTAxnvxBi3U",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3480.96978593461,
			"y": 3206.0347765393067,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 864.9999999999999,
			"height": 486.56249999999994,
			"seed": 297241825,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "_kzljuGp_BbcnJcdqR8po",
					"type": "arrow"
				}
			],
			"updated": 1709143950401,
			"link": "https://youtu.be/UBDgSHPxVME?si=hLyZy6YUvOOXwwEF",
			"locked": false,
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 1080,
			"versionNonce": 1431968870,
			"isDeleted": false,
			"id": "UfpLi2xj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -107.71097552720437,
			"y": 2311.1703694237167,
			"strokeColor": "#e03131",
			"backgroundColor": "#b2f2bb",
			"width": 807.0255126953125,
			"height": 140,
			"seed": 1028017071,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709143832450,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Weird Note: we assume that y and f* are distributed as N+M dimensional multivariate Normal\nmeaning that our entire dataset (N size) counts as partial observation of one sample of this normal\nour entire dataset, given one function f* is ONE conditional observation from it!!\nand obviously the more likely observations are ones which y is most likely described by out f*\nthis assumption is so alien...\n(its because y is normally distributed, f* is normally distributed, their joint is then\nnormally distributed and a marginalized normal distribution is another normal distribution)",
			"rawText": "Weird Note: we assume that y and f* are distributed as N+M dimensional multivariate Normal\nmeaning that our entire dataset (N size) counts as partial observation of one sample of this normal\nour entire dataset, given one function f* is ONE conditional observation from it!!\nand obviously the more likely observations are ones which y is most likely described by out f*\nthis assumption is so alien...\n(its because y is normally distributed, f* is normally distributed, their joint is then\nnormally distributed and a marginalized normal distribution is another normal distribution)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Weird Note: we assume that y and f* are distributed as N+M dimensional multivariate Normal\nmeaning that our entire dataset (N size) counts as partial observation of one sample of this normal\nour entire dataset, given one function f* is ONE conditional observation from it!!\nand obviously the more likely observations are ones which y is most likely described by out f*\nthis assumption is so alien...\n(its because y is normally distributed, f* is normally distributed, their joint is then\nnormally distributed and a marginalized normal distribution is another normal distribution)",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "freedraw",
			"version": 114,
			"versionNonce": 1033572710,
			"isDeleted": false,
			"id": "BbmH-kXcwevyY0nSU08s0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 733.7114089728103,
			"y": 2310.238989412456,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 45.36927721809343,
			"height": 128.2554567511488,
			"seed": 1487894497,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8724861003479418,
					-0.8724861003479418
				],
				[
					-1.7449722006958837,
					-1.7449722006958837
				],
				[
					-3.4899444013917673,
					-1.7449722006958837
				],
				[
					-6.1074027024357065,
					-1.7449722006958837
				],
				[
					-6.979888802783648,
					-1.7449722006958837
				],
				[
					-8.724861003479532,
					-1.7449722006958837
				],
				[
					-10.469833204175416,
					-1.7449722006958837
				],
				[
					-11.342319304523357,
					-1.7449722006958837
				],
				[
					-12.2148054048713,
					-1.7449722006958837
				],
				[
					-14.832263705915125,
					-1.7449722006958837
				],
				[
					-15.704749806263067,
					-1.7449722006958837
				],
				[
					-16.57723590661101,
					-0.8724861003479418
				],
				[
					-18.322208107307006,
					0.8724861003479418
				],
				[
					-19.194694207654948,
					1.7449722006958837
				],
				[
					-20.06718030800289,
					3.4899444013917673
				],
				[
					-20.06718030800289,
					4.362430501739709
				],
				[
					-20.06718030800289,
					5.234916602087651
				],
				[
					-20.06718030800289,
					6.979888802783535
				],
				[
					-20.06718030800289,
					8.724861003479418
				],
				[
					-20.06718030800289,
					10.469833204175302
				],
				[
					-20.06718030800289,
					13.087291505219127
				],
				[
					-20.06718030800289,
					14.832263705915011
				],
				[
					-20.06718030800289,
					16.577235906610895
				],
				[
					-20.06718030800289,
					19.194694207655175
				],
				[
					-20.06718030800289,
					21.812152508698546
				],
				[
					-20.06718030800289,
					24.429610809742826
				],
				[
					-20.06718030800289,
					26.17458301043871
				],
				[
					-20.06718030800289,
					28.792041311482535
				],
				[
					-20.06718030800289,
					30.53701351217842
				],
				[
					-19.194694207654948,
					33.154471813222244
				],
				[
					-19.194694207654948,
					34.89944401391813
				],
				[
					-19.194694207654948,
					37.51690231496195
				],
				[
					-19.194694207654948,
					38.389388415309895
				],
				[
					-18.322208107307006,
					40.13436061600578
				],
				[
					-18.322208107307006,
					42.751818917049604
				],
				[
					-18.322208107307006,
					44.49679111774549
				],
				[
					-19.194694207654948,
					46.24176331844137
				],
				[
					-19.194694207654948,
					47.986735519137255
				],
				[
					-20.06718030800289,
					49.73170771983314
				],
				[
					-20.06718030800289,
					51.47667992052902
				],
				[
					-20.93966640835083,
					54.09413822157285
				],
				[
					-21.812152508698773,
					55.83911042226873
				],
				[
					-22.684638609046715,
					57.584082622964615
				],
				[
					-23.557124709394657,
					58.45656872331256
				],
				[
					-23.557124709394657,
					59.3290548236605
				],
				[
					-25.30209691009054,
					61.07402702435638
				],
				[
					-26.174583010438482,
					61.946513124704325
				],
				[
					-27.919555211134366,
					61.946513124704325
				],
				[
					-28.792041311482308,
					62.818999225052266
				],
				[
					-30.537013512178305,
					63.69148532540021
				],
				[
					-31.409499612526247,
					64.56397142574815
				],
				[
					-33.15447181322213,
					64.56397142574815
				],
				[
					-34.899444013918014,
					64.56397142574815
				],
				[
					-35.771930114265956,
					65.43645752609609
				],
				[
					-36.6444162146139,
					65.43645752609609
				],
				[
					-37.51690231496184,
					65.43645752609609
				],
				[
					-38.38938841530978,
					65.43645752609609
				],
				[
					-39.26187451565772,
					66.30894362644403
				],
				[
					-40.134360616005665,
					66.30894362644403
				],
				[
					-41.00684671635361,
					66.30894362644403
				],
				[
					-41.87933281670155,
					67.18142972679198
				],
				[
					-42.751818917049604,
					67.18142972679198
				],
				[
					-43.624305017397546,
					67.18142972679198
				],
				[
					-44.49679111774549,
					67.18142972679198
				],
				[
					-45.36927721809343,
					67.18142972679198
				],
				[
					-44.49679111774549,
					68.05391582713992
				],
				[
					-43.624305017397546,
					68.92640192748831
				],
				[
					-42.751818917049604,
					69.7988880278358
				],
				[
					-42.751818917049604,
					70.6713741281842
				],
				[
					-41.00684671635361,
					73.28883242922757
				],
				[
					-40.134360616005665,
					74.16131852957596
				],
				[
					-39.26187451565772,
					75.0338046299239
				],
				[
					-38.38938841530978,
					76.77877683061979
				],
				[
					-37.51690231496184,
					77.65126293096773
				],
				[
					-35.771930114265956,
					80.26872123201156
				],
				[
					-34.899444013918014,
					82.01369343270744
				],
				[
					-34.02695791357007,
					83.75866563340333
				],
				[
					-33.15447181322213,
					86.37612393444715
				],
				[
					-33.15447181322213,
					88.12109613514303
				],
				[
					-32.28198571287419,
					89.86606833583892
				],
				[
					-31.409499612526247,
					92.48352663688274
				],
				[
					-31.409499612526247,
					94.22849883757863
				],
				[
					-31.409499612526247,
					95.10098493792657
				],
				[
					-31.409499612526247,
					97.7184432389704
				],
				[
					-31.409499612526247,
					99.46341543966628
				],
				[
					-31.409499612526247,
					100.33590154001422
				],
				[
					-31.409499612526247,
					102.95335984105805
				],
				[
					-32.28198571287419,
					105.57081814210187
				],
				[
					-32.28198571287419,
					108.1882764431457
				],
				[
					-32.28198571287419,
					110.80573474418952
				],
				[
					-32.28198571287419,
					112.5507069448854
				],
				[
					-33.15447181322213,
					115.16816524592923
				],
				[
					-33.15447181322213,
					117.78562354697306
				],
				[
					-30.537013512178305,
					120.40308184801734
				],
				[
					-29.66452741183025,
					121.27556794836482
				],
				[
					-27.047069110786424,
					123.02054014906071
				],
				[
					-26.174583010438482,
					123.02054014906071
				],
				[
					-23.557124709394657,
					124.76551234975705
				],
				[
					-22.684638609046715,
					124.76551234975705
				],
				[
					-19.194694207654948,
					125.63799845010499
				],
				[
					-16.57723590661101,
					126.51048455045293
				],
				[
					-15.704749806263067,
					126.51048455045293
				],
				[
					-13.959777605567183,
					126.51048455045293
				],
				[
					-13.087291505219241,
					126.51048455045293
				],
				[
					-12.2148054048713,
					126.51048455045293
				],
				[
					-11.342319304523357,
					126.51048455045293
				],
				[
					-10.469833204175416,
					126.51048455045293
				],
				[
					-10.469833204175416,
					126.51048455045293
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "arrow",
			"version": 70,
			"versionNonce": 1248174074,
			"isDeleted": false,
			"id": "9vkhhmaJ0lUaqOfCElpWg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 907.3974516428541,
			"y": 2525.2613882134287,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 316.9415567118798,
			"height": 99.0012671724744,
			"seed": 1852358561,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810012,
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
					-255.0657647290834,
					15.125193595794372
				],
				[
					-316.9415567118798,
					99.0012671724744
				]
			]
		},
		{
			"type": "text",
			"version": 59,
			"versionNonce": 809497766,
			"isDeleted": false,
			"id": "RDTH5fqM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 657.1442485124328,
			"y": 2496.386018621457,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 199.73976135253906,
			"height": 25,
			"seed": 1771626831,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810012,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets explain visually",
			"rawText": "Lets explain visually",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets explain visually",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 99,
			"versionNonce": 1595151674,
			"isDeleted": false,
			"id": "_XvDUvp74hV9oO3zuORcf",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 206.060375133724,
			"y": 2886.0583064979514,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 391.19250709123554,
			"height": 0.6875087998091658,
			"seed": 1305954511,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143866954,
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
					391.19250709123554,
					0.6875087998091658
				]
			]
		},
		{
			"type": "arrow",
			"version": 223,
			"versionNonce": 1695636986,
			"isDeleted": false,
			"id": "ZHt1CvaqliUyESJjroF2l",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 206.74788393353282,
			"y": 2885.3707976981427,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 2.549696011612639,
			"height": 370.1053824018886,
			"seed": 108718529,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143866954,
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
					2.549696011612639,
					-370.1053824018886
				]
			]
		},
		{
			"type": "text",
			"version": 108,
			"versionNonce": 1978109626,
			"isDeleted": false,
			"id": "GYKemLWU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 549.814775038149,
			"y": 2905.3085528925994,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 122.29986572265625,
			"height": 25,
			"seed": 576499983,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "y (Observed)",
			"rawText": "y (Observed)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "y (Observed)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 107,
			"versionNonce": 372877178,
			"isDeleted": false,
			"id": "0tmcyFxG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 46.5583335780708,
			"y": 2595.9295929786167,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 153.13983154296875,
			"height": 25,
			"seed": 706156801,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "f* (Unobserved)",
			"rawText": "f* (Unobserved)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f* (Unobserved)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "ellipse",
			"version": 191,
			"versionNonce": 1045080122,
			"isDeleted": false,
			"id": "06jkCGWoqpmull4qyBhmg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.7400958468396803,
			"x": 345.6347506750409,
			"y": 2619.9539656931506,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 96.85704093344691,
			"height": 139.82369818963753,
			"seed": 1437117185,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 283,
			"versionNonce": 1711116538,
			"isDeleted": false,
			"id": "h7WgdBjgLFm4BLsHKrjBt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.7400958468396803,
			"x": 327.3736601551709,
			"y": 2587.516886617918,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 131.92272511704454,
			"height": 208.33909848045738,
			"seed": 1469716783,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 408,
			"versionNonce": 282419642,
			"isDeleted": false,
			"id": "2cghwCQd5o88v0wQtIo5B",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.7400958468396803,
			"x": 301.45275320478095,
			"y": 2546.034655495143,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 185.9492843020378,
			"height": 297.1295481505739,
			"seed": 2068468513,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 278,
			"versionNonce": 1509235322,
			"isDeleted": false,
			"id": "eLzNFXN3v2MH9EsyW1e-6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.7400958468396803,
			"x": 363.6462634591941,
			"y": 2651.3365510258295,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 51.01231193890658,
			"height": 75.49684779146538,
			"seed": 1986841903,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 2079546,
			"isDeleted": false,
			"id": "GGIZTn1F",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 316.36246065138886,
			"y": 2899.4335223665676,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 219.2964324951172,
			"height": 20,
			"seed": 1554696385,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "If we have a known value y",
			"rawText": "If we have a known value y",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If we have a known value y",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 150,
			"versionNonce": 1907901434,
			"isDeleted": false,
			"id": "Oo890a7ZLRhAV7Wztg5lE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 459.3956545537571,
			"y": 2883.2453496368544,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 10.578384963221879,
			"height": 321.4201584978955,
			"seed": 161761071,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					10.578384963221879,
					-321.4201584978955
				]
			]
		},
		{
			"type": "arrow",
			"version": 147,
			"versionNonce": 1489089722,
			"isDeleted": false,
			"id": "LB0l9PwM2HhY-kR5HU3wZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 324.78265125150364,
			"y": 2935.7861656829605,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 82.08295892289544,
			"height": 238.64860279434424,
			"seed": 281413359,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143866954,
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
					-81.32293152546123,
					66.12238357677688
				],
				[
					-82.08295892289544,
					184.6866575765148
				],
				[
					-29.641068499934477,
					238.64860279434424
				]
			]
		},
		{
			"type": "arrow",
			"version": 148,
			"versionNonce": 652152186,
			"isDeleted": false,
			"id": "7SDXLtM1ho3-4dPk2TSRS",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 231.04081982232594,
			"y": 3229.3471247174275,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 362.0036620094521,
			"height": 3.022995089849246,
			"seed": 2117197199,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143866954,
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
					362.0036620094521,
					3.022995089849246
				]
			]
		},
		{
			"type": "text",
			"version": 115,
			"versionNonce": 559107642,
			"isDeleted": false,
			"id": "QLf1KAzR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 550.7225505738882,
			"y": 3248.996592801448,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 16.032028198242188,
			"height": 20,
			"seed": 539291617,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "f*",
			"rawText": "f*",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f*",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 154,
			"versionNonce": 1828812538,
			"isDeleted": false,
			"id": "jwOyGG2v",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 42.550748559700025,
			"y": 3021.5534857155944,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 170.00035095214844,
			"height": 60,
			"seed": 1279386721,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Then we can infer\nthe distribution of f*\ngiven that value of y",
			"rawText": "Then we can infer\nthe distribution of f*\ngiven that value of y",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Then we can infer\nthe distribution of f*\ngiven that value of y",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 645,
			"versionNonce": 443320250,
			"isDeleted": false,
			"id": "UiabLF2Ooej0QKEpCamk9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 618.945475397575,
			"y": 3226.3241296275787,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 394.5008592253319,
			"height": 110.33932077949885,
			"seed": 1202666351,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-50.84070305705359,
					-6.8017389521605764
				],
				[
					-68.97867359614929,
					-37.03168985065395
				],
				[
					-85.39961128824234,
					-64.23864565929716
				],
				[
					-121.67555236643364,
					-108.82782323457468
				],
				[
					-169.28772503156006,
					-110.33932077949885
				],
				[
					-231.2591243734704,
					-40.81043371296528
				],
				[
					-279.62704581105896,
					-15.114975449246685
				],
				[
					-371.072647279,
					-3.778743862311785
				],
				[
					-394.5008592253319,
					-3.022995089849246
				]
			]
		},
		{
			"type": "text",
			"version": 327,
			"versionNonce": 834109562,
			"isDeleted": false,
			"id": "Qg9OBqgF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 219.3643475531061,
			"y": 3264.629942719547,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 326.12872314453125,
			"height": 100,
			"seed": 1908655023,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709143866954,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This also works in higher dimension\nand is easy to analytically compute\nONLY because we are dealing with\nGaussians, other distributions or families\nare way harder to infer",
			"rawText": "This also works in higher dimension\nand is easy to analytically compute\nONLY because we are dealing with\nGaussians, other distributions or families\nare way harder to infer",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This also works in higher dimension\nand is easy to analytically compute\nONLY because we are dealing with\nGaussians, other distributions or families\nare way harder to infer",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 444,
			"versionNonce": 226337126,
			"isDeleted": false,
			"id": "3PDS951JKEQ5r9Dbx7S5Q",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1.8298302923511613,
			"y": 2710.3442461280183,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 104.95464568447852,
			"height": 69.21152829118455,
			"seed": 2089025327,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143867294,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "2juBYsLO",
				"focus": 0.1354761303022374,
				"gap": 14.651109315757097
			},
			"endBinding": {
				"elementId": "YfeiNX0j",
				"focus": -0.22736729090989374,
				"gap": 3.695725694197563
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
					-88.3133080303334,
					8.384222930552369
				],
				[
					-104.95464568447852,
					69.21152829118455
				]
			]
		},
		{
			"type": "text",
			"version": 408,
			"versionNonce": 1553541626,
			"isDeleted": false,
			"id": "YfeiNX0j",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -174.46627122565414,
			"y": 2783.2515001134,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 155.78982543945312,
			"height": 95.9999644024161,
			"seed": 1127853519,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "3PDS951JKEQ5r9Dbx7S5Q",
					"type": "arrow"
				}
			],
			"updated": 1709143866954,
			"link": null,
			"locked": false,
			"fontSize": 9.59999644024161,
			"fontFamily": 1,
			"text": "Which make sense why\nthe kernel choice then\ndetermines our function\nshape since the distribution\nthat we sample our functions\nfrom has a covariance matrix\ngoverned by the similarities\ncalculated by the kernel fucntion",
			"rawText": "Which make sense why\nthe kernel choice then\ndetermines our function\nshape since the distribution\nthat we sample our functions\nfrom has a covariance matrix\ngoverned by the similarities\ncalculated by the kernel fucntion",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which make sense why\nthe kernel choice then\ndetermines our function\nshape since the distribution\nthat we sample our functions\nfrom has a covariance matrix\ngoverned by the similarities\ncalculated by the kernel fucntion",
			"lineHeight": 1.25,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 247,
			"versionNonce": 269738106,
			"isDeleted": false,
			"id": "WhvGQu8ypMfN_Bso0QFgj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1506.3198991816864,
			"y": 2663.203613724781,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 136.86715444908418,
			"height": 15.245150149700748,
			"seed": 273305121,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709144309240,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "U8ta4RMD",
				"focus": 0.08356615373356105,
				"gap": 7.41333357077383
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
					136.86715444908418,
					15.245150149700748
				]
			]
		},
		{
			"type": "text",
			"version": 459,
			"versionNonce": 688667814,
			"isDeleted": false,
			"id": "U8ta4RMD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1650.6003872015444,
			"y": 2646.0212809472364,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 360.1287841796875,
			"height": 120,
			"seed": 194402369,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "WhvGQu8ypMfN_Bso0QFgj",
					"type": "arrow"
				}
			],
			"updated": 1709144308851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The posterior predictive distribution\nfor an unobserved xi is an independent normal\ndistribution which has a mean of\nequal to the xi-th element of the mean f*\nThe variance is similarly selected from the\ndiagonal of k(x*,x*) (including the noise)",
			"rawText": "The posterior predictive distribution\nfor an unobserved xi is an independent normal\ndistribution which has a mean of\nequal to the xi-th element of the mean f*\nThe variance is similarly selected from the\ndiagonal of k(x*,x*) (including the noise)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The posterior predictive distribution\nfor an unobserved xi is an independent normal\ndistribution which has a mean of\nequal to the xi-th element of the mean f*\nThe variance is similarly selected from the\ndiagonal of k(x*,x*) (including the noise)",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "line",
			"version": 105,
			"versionNonce": 301320998,
			"isDeleted": false,
			"id": "p2_RKBGhij3JrhwA455mB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1968.5018227106475,
			"y": 2706.5739532693606,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 15.566113512943957,
			"height": 0.5021326939659048,
			"seed": 1834907681,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709144308851,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					15.566113512943957,
					-0.5021326939659048
				]
			]
		},
		{
			"type": "arrow",
			"version": 564,
			"versionNonce": 1383448890,
			"isDeleted": false,
			"id": "7mkgS5WvVNXZ-t5R2Vhvx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1120.1760606823602,
			"y": 2663.4529465065316,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 94.58432985709192,
			"height": 7.470142212950577,
			"seed": 616631055,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709144309241,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "h38BAyZa",
				"focus": 0.06680442036433547,
				"gap": 6.675008066214787
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
					-94.58432985709192,
					7.470142212950577
				]
			]
		},
		{
			"type": "text",
			"version": 376,
			"versionNonce": 867023270,
			"isDeleted": false,
			"id": "rt9AvdXX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 855.5979278062676,
			"y": 2651.5168029343236,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 229.66445922851562,
			"height": 100,
			"seed": 1777221057,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709144308851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is the posterior\ndistribution over f*\n(after we condition it\nto include what we previously\nbelieve to be true)",
			"rawText": "This is the posterior\ndistribution over f*\n(after we condition it\nto include what we previously\nbelieve to be true)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is the posterior\ndistribution over f*\n(after we condition it\nto include what we previously\nbelieve to be true)",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 606,
			"versionNonce": 319588070,
			"isDeleted": false,
			"id": "Cl9JLQL1H3wJvyZKE8ABa",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 792.9612576014904,
			"y": 198.25789343824596,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 57.18309578459616,
			"height": 2.2013191095140883,
			"seed": 1226468838,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "KLkaVnvl8GwB-X06Ill1r",
				"focus": -0.29101278400852193,
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
					57.18309578459616,
					2.2013191095140883
				]
			]
		},
		{
			"type": "image",
			"version": 365,
			"versionNonce": 1460683386,
			"isDeleted": false,
			"id": "KLkaVnvl8GwB-X06Ill1r",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 851.1443533860866,
			"y": 175.48409890830737,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 174.58813706921268,
			"height": 42.44131508864839,
			"seed": 1709399738,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Cl9JLQL1H3wJvyZKE8ABa",
					"type": "arrow"
				}
			],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9358745cf6b740fb530b306eb935d3b26ffa1b36",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 317110822,
			"isDeleted": false,
			"id": "lcPM6aI1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1617.5349576786543,
			"y": 136.78204282435726,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 573.8731689453125,
			"height": 60,
			"seed": 1239847994,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Anyway as always we make a few assumptions beforehand in order to\nget our model\nLets assume that y is part of a parametric model + a bit of i.i.d noise",
			"rawText": "Anyway as always we make a few assumptions beforehand in order to\nget our model\nLets assume that y is part of a parametric model + a bit of i.i.d noise",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Anyway as always we make a few assumptions beforehand in order to\nget our model\nLets assume that y is part of a parametric model + a bit of i.i.d noise",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "rectangle",
			"version": 189,
			"versionNonce": 2140529466,
			"isDeleted": false,
			"id": "Bbnnfdf6yKIOssRwP-ndJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1551.9161794489773,
			"y": 128.52390323510275,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 730.8913570389277,
			"height": 120.6011209289039,
			"seed": 907399354,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "G_YdRCZhtEzJKYJLnKsGm",
					"type": "arrow"
				},
				{
					"id": "edOrKshDLnRcb7hKwJeD4",
					"type": "arrow"
				}
			],
			"updated": 1709142810013,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 238,
			"versionNonce": 1469613414,
			"isDeleted": false,
			"id": "G_YdRCZhtEzJKYJLnKsGm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1303.0985443844102,
			"y": 150.34895884955927,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 244.84923339097395,
			"height": 50.3844678538658,
			"seed": 81114170,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "Bbnnfdf6yKIOssRwP-ndJ",
				"focus": -0.3393405818234424,
				"gap": 3.9684016735932346
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
					29.804320292317016,
					42.889143835285665
				],
				[
					244.84923339097395,
					50.3844678538658
				]
			]
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 1881762810,
			"isDeleted": false,
			"id": "7DFPZsaJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 602.5236545544346,
			"y": 160.0666471258185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 449.744873046875,
			"height": 20,
			"seed": 141082746,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can assume a prior on p(w) according to our problem ",
			"rawText": "We can assume a prior on p(w) according to our problem ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can assume a prior on p(w) according to our problem ",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 149,
			"versionNonce": 309258406,
			"isDeleted": false,
			"id": "byuxC28PA6jUXFS-pBkuZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 547.9198620761947,
			"y": 149.98806351746774,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 547.8372765581807,
			"height": 75.39045090250198,
			"seed": 2040497594,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "IBCYSpFXM6LmpQMhsSb-D",
					"type": "arrow"
				}
			],
			"updated": 1709142810013,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 99,
			"versionNonce": 1053678778,
			"isDeleted": false,
			"id": "IBCYSpFXM6LmpQMhsSb-D",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1303.431019513095,
			"y": 153.35261516381485,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 205.8155614721943,
			"height": 41.625619174151666,
			"seed": 1351919738,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "byuxC28PA6jUXFS-pBkuZ",
				"focus": 0.28441935668050083,
				"gap": 1.8583194065251973
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
					-27.750412782767853,
					38.54223997606633
				],
				[
					-205.8155614721943,
					41.625619174151666
				]
			]
		},
		{
			"type": "text",
			"version": 520,
			"versionNonce": 1125573606,
			"isDeleted": false,
			"id": "stk8rg74",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 910.8949335054695,
			"y": 227.35371591786225,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 768.1135864257812,
			"height": 120,
			"seed": 1135282810,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Za23gMH3E9CZS7WfAM2WR",
					"type": "arrow"
				},
				{
					"id": "-VPlBAejWj25aM3jtHG1R",
					"type": "arrow"
				}
			],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "As you'll see moving forward, Bayesian regression will be\nan expanded Idea on Kernel ridge regression, where Kernel ridge gives us\none answer as its \"best prediction\" Bayesian regression expands on the idea by giving us\nthe best prediction alongside a confidence estimation for each areas, the more data we observe\nin each area the more confident we are the less the variance etc... We also can always\ninclude our prior knowledge is this sort of approach!",
			"rawText": "As you'll see moving forward, Bayesian regression will be\nan expanded Idea on Kernel ridge regression, where Kernel ridge gives us\none answer as its \"best prediction\" Bayesian regression expands on the idea by giving us\nthe best prediction alongside a confidence estimation for each areas, the more data we observe\nin each area the more confident we are the less the variance etc... We also can always\ninclude our prior knowledge is this sort of approach!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "As you'll see moving forward, Bayesian regression will be\nan expanded Idea on Kernel ridge regression, where Kernel ridge gives us\none answer as its \"best prediction\" Bayesian regression expands on the idea by giving us\nthe best prediction alongside a confidence estimation for each areas, the more data we observe\nin each area the more confident we are the less the variance etc... We also can always\ninclude our prior knowledge is this sort of approach!",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "arrow",
			"version": 56,
			"versionNonce": 1227240826,
			"isDeleted": false,
			"id": "Za23gMH3E9CZS7WfAM2WR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 905.1730047369642,
			"y": 298.6371130454049,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 141.04696290610127,
			"height": 0.8760680925844326,
			"seed": 1168570086,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "stk8rg74",
				"focus": -0.14205895535329524,
				"gap": 5.721928768505222
			},
			"endBinding": {
				"elementId": "W67BxozR",
				"focus": 0.10569368199136045,
				"gap": 3.0702479541103003
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
					-141.04696290610127,
					0.8760680925844326
				]
			]
		},
		{
			"type": "text",
			"version": 116,
			"versionNonce": 1805481766,
			"isDeleted": false,
			"id": "W67BxozR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 495.6151810837839,
			"y": 267.09866171236354,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 265.44061279296875,
			"height": 60,
			"seed": 319154746,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Za23gMH3E9CZS7WfAM2WR",
					"type": "arrow"
				}
			],
			"updated": 1709142810013,
			"link": "[[Bayes Estimator]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "its good to be familiar\nwith its classification alternative\nParameter estimation",
			"rawText": "its good to be familiar\nwith its classification alternative\nParameter estimation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "its good to be familiar\nwith its classification alternative\nParameter estimation",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 284,
			"versionNonce": 1081439802,
			"isDeleted": false,
			"id": "-VPlBAejWj25aM3jtHG1R",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1683.1214709519832,
			"y": 300.5210384755444,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 53.66656302766296,
			"height": 0.3937888365069284,
			"seed": 363996026,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "stk8rg74",
				"focus": 0.195163751145698,
				"gap": 4.112951020732453
			},
			"endBinding": {
				"elementId": "dCusToqw",
				"focus": -0.15469319113931987,
				"gap": 6.357150646712512
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
					53.66656302766296,
					0.3937888365069284
				]
			]
		},
		{
			"type": "text",
			"version": 318,
			"versionNonce": 1148166758,
			"isDeleted": false,
			"id": "dCusToqw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1743.1451846263585,
			"y": 267.1660702153535,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 272.59259033203125,
			"height": 60,
			"seed": 902990630,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-VPlBAejWj25aM3jtHG1R",
					"type": "arrow"
				}
			],
			"updated": 1709142810013,
			"link": "[[Regularization]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "these ideas are similar\nto Bayesian Neural networks that\nprovide confidence estimation",
			"rawText": "these ideas are similar\nto Bayesian Neural networks that\nprovide confidence estimation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "these ideas are similar\nto Bayesian Neural networks that\nprovide confidence estimation",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 245,
			"versionNonce": 899587834,
			"isDeleted": false,
			"id": "oFzt3uOX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1379.0326462398846,
			"y": 668.949928419209,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 210.44814338128901,
			"height": 20.717692871733117,
			"seed": 19462,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "OIAGE9HZ0KOC0wEEoq9T7",
					"type": "arrow"
				}
			],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a7fd1de0ad9d204648c6ccd417353ae9092d55ce",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 7,
			"versionNonce": 1884972454,
			"isDeleted": false,
			"id": "SmIVFXZABXrdO3P_l-Nwt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1967.624600203841,
			"y": 228.58320068649772,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 0.32878878792189425,
			"height": 0.3287887879219227,
			"seed": 1907520230,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.32878878792189425,
					0.3287887879219227
				],
				[
					0.32878878792189425,
					0.3287887879219227
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 6,
			"versionNonce": 623161274,
			"isDeleted": false,
			"id": "rhD0HowqZ2MPYsCwOPMEB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1972.8852208105916,
			"y": 232.19987735363878,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 426168294,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
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
			"version": 8,
			"versionNonce": 814399718,
			"isDeleted": false,
			"id": "I7wxr3g0K8KlWAWefcQdY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1972.2276432347478,
			"y": 228.58320068649772,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 0.6575775758437885,
			"height": 0.6575775758438169,
			"seed": 1294061990,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.32878878792189425,
					-0.32878878792189425
				],
				[
					0.6575775758437885,
					-0.6575775758438169
				],
				[
					0.6575775758437885,
					-0.6575775758438169
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 73,
			"versionNonce": 53127290,
			"isDeleted": false,
			"id": "dLfpKSYiorN2zHx--zI1d",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1974.529164750201,
			"y": 225.6241015952005,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 9.534874849735388,
			"height": 12.165185153110855,
			"seed": 1900808678,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.32878878792189425,
					0
				],
				[
					0.6575775758440159,
					0
				],
				[
					0.6575775758440159,
					0.6575775758438454
				],
				[
					0.6575775758440159,
					0.9863663637657396
				],
				[
					0.6575775758440159,
					1.643943939609585
				],
				[
					0.6575775758440159,
					2.6303103033753246
				],
				[
					0.6575775758440159,
					3.2878878792191415
				],
				[
					0,
					4.274254242984881
				],
				[
					-0.6575775758437885,
					4.931831818828698
				],
				[
					-0.9863663637656828,
					5.260620606750649
				],
				[
					-1.315155151687577,
					5.918198182594466
				],
				[
					-1.6439439396094713,
					6.575775758438283
				],
				[
					-1.9727327275313655,
					7.233353334282128
				],
				[
					-2.630310303375154,
					7.890930910125945
				],
				[
					-2.630310303375154,
					8.219719698047868
				],
				[
					-2.9590990912972757,
					8.548508485969762
				],
				[
					-3.616676667141064,
					8.877297273891685
				],
				[
					-3.9454654550629584,
					8.877297273891685
				],
				[
					-4.603043030906747,
					8.877297273891685
				],
				[
					-4.603043030906747,
					8.548508485969762
				],
				[
					-4.931831818828641,
					7.562142122204023
				],
				[
					-4.931831818828641,
					6.575775758438283
				],
				[
					-5.260620606750535,
					5.589409394672543
				],
				[
					-5.260620606750535,
					4.603043030906804
				],
				[
					-5.260620606750535,
					3.616676667141064
				],
				[
					-5.260620606750535,
					2.6303103033753246
				],
				[
					-5.260620606750535,
					1.643943939609585
				],
				[
					-5.260620606750535,
					0.9863663637657396
				],
				[
					-4.931831818828641,
					0.32878878792189425
				],
				[
					-4.603043030906747,
					0.32878878792189425
				],
				[
					-4.274254242984853,
					0
				],
				[
					-3.616676667141064,
					0
				],
				[
					-2.630310303375154,
					-0.3287887879219227
				],
				[
					-1.9727327275313655,
					-0.3287887879219227
				],
				[
					-1.315155151687577,
					-0.3287887879219227
				],
				[
					-0.6575775758437885,
					0
				],
				[
					0.32878878792189425,
					0.32878878792189425
				],
				[
					0.9863663637659101,
					0.6575775758438454
				],
				[
					1.6439439396096986,
					1.643943939609585
				],
				[
					1.972732727531593,
					2.6303103033753246
				],
				[
					2.301521515453487,
					3.9454654550629584
				],
				[
					2.301521515453487,
					5.260620606750649
				],
				[
					2.6303103033753814,
					6.904564546360206
				],
				[
					2.6303103033753814,
					8.219719698047868
				],
				[
					2.6303103033753814,
					9.206086061813608
				],
				[
					2.301521515453487,
					10.192452425579347
				],
				[
					1.6439439396096986,
					10.850030001423193
				],
				[
					0.9863663637659101,
					11.836396365188932
				],
				[
					0.32878878792189425,
					11.836396365188932
				],
				[
					-0.6575775758437885,
					11.836396365188932
				],
				[
					-1.315155151687577,
					11.50760757726701
				],
				[
					-1.9727327275313655,
					11.178818789345087
				],
				[
					-2.30152151545326,
					10.850030001423193
				],
				[
					-2.9590990912972757,
					10.192452425579347
				],
				[
					-3.616676667141064,
					9.206086061813608
				],
				[
					-4.274254242984853,
					8.548508485969762
				],
				[
					-4.931831818828641,
					8.219719698047868
				],
				[
					-5.260620606750535,
					8.219719698047868
				],
				[
					-5.58940939467243,
					8.219719698047868
				],
				[
					-5.918198182594324,
					8.219719698047868
				],
				[
					-6.246986970516218,
					7.562142122204023
				],
				[
					-6.5757757584381125,
					6.904564546360206
				],
				[
					-6.5757757584381125,
					6.246986970516389
				],
				[
					-6.5757757584381125,
					5.918198182594466
				],
				[
					-6.5757757584381125,
					5.589409394672543
				],
				[
					-6.904564546360007,
					5.589409394672543
				],
				[
					-6.904564546360007,
					5.260620606750649
				],
				[
					-6.904564546360007,
					5.260620606750649
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "image",
			"version": 88,
			"versionNonce": 411939878,
			"isDeleted": false,
			"id": "qiOzeuwQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1957.2922178488761,
			"y": 222.82176347497574,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 32,
			"height": 17,
			"seed": 72957,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f9d014528bec0eb074298c7ec33a910a3b6ba0f6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 134,
			"versionNonce": 1198754106,
			"isDeleted": false,
			"id": "s4HR5hEQVywxBj8zA96W5",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1466.9734347145077,
			"y": 406.77000505490156,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 15.151069299225355,
			"height": 16.933548040310825,
			"seed": 37809062,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.29707979018076003,
					0.2970797901808737
				],
				[
					0.8912393705425075,
					0.891239370542678
				],
				[
					1.1883191607234949,
					1.1883191607235517
				],
				[
					1.1883191607234949,
					1.4853989509044254
				],
				[
					1.4853989509042549,
					1.4853989509044254
				],
				[
					2.0795585312662297,
					0.891239370542678
				],
				[
					2.673718111627977,
					0.2970797901808737
				],
				[
					2.970797901808737,
					-0.29707979018093056
				],
				[
					3.564957482170712,
					-1.1883191607235517
				],
				[
					3.862037272351472,
					-1.782478741085356
				],
				[
					4.159117062532459,
					-2.3766383214471603
				],
				[
					4.456196852713219,
					-2.3766383214471603
				],
				[
					4.753276642894207,
					-2.673718111628034
				],
				[
					5.347436223255954,
					-2.673718111628034
				],
				[
					5.941595803617702,
					-2.3766383214471603
				],
				[
					6.535755383979449,
					-1.782478741085356
				],
				[
					7.129914964341424,
					-0.891239370542678
				],
				[
					7.426994754522184,
					0.5941595803618043
				],
				[
					7.724074544703171,
					2.3766383214471603
				],
				[
					7.724074544703171,
					4.45619685271339
				],
				[
					7.724074544703171,
					5.347436223256011
				],
				[
					7.724074544703171,
					6.53575538397962
				],
				[
					7.724074544703171,
					8.021154334884045
				],
				[
					7.724074544703171,
					9.209473495607597
				],
				[
					7.724074544703171,
					10.397792656331205
				],
				[
					7.129914964341424,
					10.694872446512079
				],
				[
					7.129914964341424,
					10.991952236692953
				],
				[
					7.129914964341424,
					10.694872446512079
				],
				[
					6.8328351741604365,
					10.100712866150332
				],
				[
					6.535755383979449,
					8.021154334884045
				],
				[
					6.535755383979449,
					5.941595803617815
				],
				[
					6.535755383979449,
					3.2678776919897814
				],
				[
					6.535755383979449,
					1.782478741085356
				],
				[
					6.8328351741604365,
					0
				],
				[
					7.129914964341424,
					-0.5941595803618043
				],
				[
					7.724074544703171,
					-1.4853989509044254
				],
				[
					8.021154334883931,
					-1.782478741085356
				],
				[
					8.615313915245679,
					-2.0795585312662297
				],
				[
					8.912393705426666,
					-2.3766383214471603
				],
				[
					9.209473495607654,
					-2.3766383214471603
				],
				[
					9.803633075969401,
					-1.1883191607235517
				],
				[
					10.100712866150161,
					-0.891239370542678
				],
				[
					10.694872446511908,
					0
				],
				[
					10.694872446511908,
					1.1883191607235517
				],
				[
					10.694872446511908,
					2.3766383214471603
				],
				[
					10.991952236692896,
					3.564957482170655
				],
				[
					10.991952236692896,
					5.050356433075137
				],
				[
					10.991952236692896,
					6.53575538397962
				],
				[
					10.991952236692896,
					7.129914964341367
				],
				[
					10.991952236692896,
					7.724074544703171
				],
				[
					10.694872446511908,
					8.912393705426723
				],
				[
					10.397792656331148,
					9.506553285788527
				],
				[
					10.397792656331148,
					10.397792656331205
				],
				[
					10.100712866150161,
					10.991952236692953
				],
				[
					9.803633075969401,
					11.586111817054757
				],
				[
					9.506553285788414,
					12.477351187597435
				],
				[
					9.209473495607654,
					12.477351187597435
				],
				[
					8.021154334883931,
					10.397792656331205
				],
				[
					7.129914964341424,
					7.129914964341367
				],
				[
					7.129914964341424,
					5.941595803617815
				],
				[
					7.129914964341424,
					3.8620372723515857
				],
				[
					7.724074544703171,
					2.3766383214471603
				],
				[
					8.021154334883931,
					1.4853989509044254
				],
				[
					8.021154334883931,
					0.5941595803618043
				],
				[
					8.615313915245679,
					-0.29707979018093056
				],
				[
					9.209473495607654,
					-0.891239370542678
				],
				[
					9.506553285788414,
					-1.1883191607235517
				],
				[
					9.803633075969401,
					-0.891239370542678
				],
				[
					10.397792656331148,
					0
				],
				[
					10.991952236692896,
					0.5941595803618043
				],
				[
					11.586111817054643,
					1.4853989509044254
				],
				[
					11.88319160723563,
					2.0795585312662297
				],
				[
					12.477351187597378,
					3.2678776919897814
				],
				[
					12.774430977778138,
					3.8620372723515857
				],
				[
					12.774430977778138,
					4.159117062532459
				],
				[
					12.477351187597378,
					4.159117062532459
				],
				[
					11.88319160723563,
					3.2678776919897814
				],
				[
					11.88319160723563,
					1.782478741085356
				],
				[
					11.586111817054643,
					-0.29707979018093056
				],
				[
					10.991952236692896,
					-2.673718111628034
				],
				[
					10.991952236692896,
					-3.2678776919897814
				],
				[
					10.991952236692896,
					-3.564957482170712
				],
				[
					10.991952236692896,
					-4.159117062532516
				],
				[
					10.991952236692896,
					-4.45619685271339
				],
				[
					11.88319160723563,
					-4.159117062532516
				],
				[
					12.18027139741639,
					-2.9707979018089077
				],
				[
					12.18027139741639,
					-2.0795585312662297
				],
				[
					12.774430977778138,
					-1.1883191607235517
				],
				[
					12.774430977778138,
					-0.5941595803618043
				],
				[
					13.071510767959126,
					0.2970797901808737
				],
				[
					13.071510767959126,
					1.1883191607235517
				],
				[
					13.368590558140113,
					2.0795585312662297
				],
				[
					13.368590558140113,
					2.9707979018089077
				],
				[
					13.96275013850186,
					3.564957482170655
				],
				[
					14.556909718863608,
					4.753276642894264
				],
				[
					14.853989509044368,
					6.238675593798746
				],
				[
					15.151069299225355,
					7.724074544703171
				],
				[
					15.151069299225355,
					8.912393705426723
				],
				[
					15.151069299225355,
					10.100712866150332
				],
				[
					14.853989509044368,
					10.991952236692953
				],
				[
					13.96275013850186,
					11.586111817054757
				],
				[
					13.665670348320873,
					11.586111817054757
				],
				[
					13.665670348320873,
					11.88319160723563
				],
				[
					13.071510767959126,
					11.88319160723563
				],
				[
					12.774430977778138,
					11.586111817054757
				],
				[
					11.88319160723563,
					11.289032026873826
				],
				[
					11.289032026873883,
					10.694872446512079
				],
				[
					10.397792656331148,
					10.100712866150332
				],
				[
					9.803633075969401,
					9.803633075969401
				],
				[
					9.506553285788414,
					9.209473495607597
				],
				[
					8.615313915245679,
					8.912393705426723
				],
				[
					8.615313915245679,
					8.318234125064976
				],
				[
					8.021154334883931,
					8.021154334884045
				],
				[
					7.129914964341424,
					7.724074544703171
				],
				[
					6.8328351741604365,
					7.724074544703171
				],
				[
					6.535755383979449,
					7.724074544703171
				],
				[
					5.941595803617702,
					7.724074544703171
				],
				[
					5.347436223255954,
					7.724074544703171
				],
				[
					4.753276642894207,
					7.724074544703171
				],
				[
					4.456196852713219,
					7.724074544703171
				],
				[
					4.159117062532459,
					7.724074544703171
				],
				[
					3.564957482170712,
					8.021154334884045
				],
				[
					3.2678776919897246,
					8.318234125064976
				],
				[
					2.970797901808737,
					8.318234125064976
				],
				[
					2.673718111627977,
					8.61531391524585
				],
				[
					2.673718111627977,
					8.912393705426723
				],
				[
					2.970797901808737,
					8.912393705426723
				],
				[
					3.2678776919897246,
					8.912393705426723
				],
				[
					3.2678776919897246,
					8.912393705426723
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "image",
			"version": 70,
			"versionNonce": 1112555366,
			"isDeleted": false,
			"id": "8Nm4uG9Y",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1461.9597145372506,
			"y": 403.2956637538153,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 29.887560317434055,
			"height": 13.732122308010242,
			"seed": 34324,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1b611a69fde84eaa8012debe1db6a78b922fc0e1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 161,
			"versionNonce": 2036486650,
			"isDeleted": false,
			"id": "q2nLzyox",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1108.0702769120091,
			"y": 601.5007377275857,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 391.6807861328125,
			"height": 60,
			"seed": 893198394,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "OIAGE9HZ0KOC0wEEoq9T7",
					"type": "arrow"
				}
			],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Through some shitty math proof that tells us\nhow to infer the parameters of a Gaussian given\nthat its 2 Gaussians multiplied",
			"rawText": "Through some shitty math proof that tells us\nhow to infer the parameters of a Gaussian given\nthat its 2 Gaussians multiplied",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Through some shitty math proof that tells us\nhow to infer the parameters of a Gaussian given\nthat its 2 Gaussians multiplied",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 185,
			"versionNonce": 35611302,
			"isDeleted": false,
			"id": "levOxN9V",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1043.2207407476337,
			"y": 666.8328903467476,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 230.81391649569719,
			"height": 23.964286412121567,
			"seed": 15313,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1f0dd65fea8fdc617ee612e6a2333d40ee220b8a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 44,
			"versionNonce": 1006240442,
			"isDeleted": false,
			"id": "edOrKshDLnRcb7hKwJeD4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1960.3294738685295,
			"y": 113.83917265901715,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 97.34880452204288,
			"height": 49.710027841043086,
			"seed": 50651898,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Bbnnfdf6yKIOssRwP-ndJ",
				"focus": -0.21483188305298626,
				"gap": 14.684730576085613
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
					97.34880452204288,
					-49.710027841043086
				]
			]
		},
		{
			"type": "text",
			"version": 426,
			"versionNonce": 447225318,
			"isDeleted": false,
			"id": "WageIrBv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1953.3197870772733,
			"y": -35.682267879157564,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 513.5050048828125,
			"height": 160,
			"seed": 1650754746,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Note that there is a version of this model\ncalled Bayesian Linear regression which has the \nexact same ideas but does not use Kernels and feature spaces\nand as such its not as good, and we all know the conclusion\nof our lectures every single time...\nif its linear then KERNELIZE IT!!!\nso I just skipped the bs and went straight\nto the kernelized version",
			"rawText": "Note that there is a version of this model\ncalled Bayesian Linear regression which has the \nexact same ideas but does not use Kernels and feature spaces\nand as such its not as good, and we all know the conclusion\nof our lectures every single time...\nif its linear then KERNELIZE IT!!!\nso I just skipped the bs and went straight\nto the kernelized version",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note that there is a version of this model\ncalled Bayesian Linear regression which has the \nexact same ideas but does not use Kernels and feature spaces\nand as such its not as good, and we all know the conclusion\nof our lectures every single time...\nif its linear then KERNELIZE IT!!!\nso I just skipped the bs and went straight\nto the kernelized version",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 1507695482,
			"isDeleted": false,
			"id": "Yt88XHgW",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1263.6808515140713,
			"y": 877.754745833096,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 139.82431030273438,
			"height": 20,
			"seed": 280929702,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Which simplifies to",
			"rawText": "Which simplifies to",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which simplifies to",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 67,
			"versionNonce": 1895264550,
			"isDeleted": false,
			"id": "KK5lBeRY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2487.9602994190127,
			"y": 1019.4801756833131,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 301.85662841796875,
			"height": 20,
			"seed": 1169785318,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We start off with our Prior knowledge",
			"rawText": "We start off with our Prior knowledge",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We start off with our Prior knowledge",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 174,
			"versionNonce": 1364204602,
			"isDeleted": false,
			"id": "2PgrdROR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2387.459475491455,
			"y": 1346.853602201293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 541.5850830078125,
			"height": 40,
			"seed": 700652154,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Using different kernels we will describe the possible functions\nas prior knowledge and limit our space to specific types of solutions",
			"rawText": "Using different kernels we will describe the possible functions\nas prior knowledge and limit our space to specific types of solutions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Using different kernels we will describe the possible functions\nas prior knowledge and limit our space to specific types of solutions",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 407,
			"versionNonce": 1081760870,
			"isDeleted": false,
			"id": "OHf2a3MJsYcDnLoYms7vv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2580.2181766975355,
			"y": 1385.2816608092537,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 174.58813706921268,
			"height": 42.44131508864839,
			"seed": 332973478,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9358745cf6b740fb530b306eb935d3b26ffa1b36",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 53,
			"versionNonce": 1614054650,
			"isDeleted": false,
			"id": "rIQTgKXpjSzqFjbtSqsgY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2901.8124503432778,
			"y": 1169.810251482424,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 253.5476816546643,
			"height": 4.712782186889854,
			"seed": 1294053542,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
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
					253.5476816546643,
					4.712782186889854
				]
			]
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 269342138,
			"isDeleted": false,
			"id": "28nKFHjv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3235.644653791157,
			"y": 981.2989640068372,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 438.8968505859375,
			"height": 60,
			"seed": 2039267302,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Then after Observing a few points (Black dots)\nour posterior will eliminate functions that do not agree\nwith the true prediction with some variance",
			"rawText": "Then after Observing a few points (Black dots)\nour posterior will eliminate functions that do not agree\nwith the true prediction with some variance",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Then after Observing a few points (Black dots)\nour posterior will eliminate functions that do not agree\nwith the true prediction with some variance",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 32,
			"versionNonce": 548338406,
			"isDeleted": false,
			"id": "9wubAUvZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2976.6327764828043,
			"y": 1141.533558361086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 116.16026306152344,
			"height": 20,
			"seed": 960837862,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "observing data",
			"rawText": "observing data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "observing data",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 663,
			"versionNonce": 1792773350,
			"isDeleted": false,
			"id": "1778tctZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3109.597832220442,
			"y": 1333.724997038583,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 713.7293701171875,
			"height": 160,
			"seed": 1981337318,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142871782,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "as you can see intuitively the more we observe the closer we get to the\nreal function, and in certain regions where we dont have a lot of datapoints\nour variance will be high (same as prior) because we are not confident on what\nto predict there whereas in areas that we observe a lot of data we will\nget more confident\nour Mean of the distribution of outputs is always just the kernel ridge regression answer\nbut we provide this confidence estimate to compensate for the messyness of the real\nworld data!",
			"rawText": "as you can see intuitively the more we observe the closer we get to the\nreal function, and in certain regions where we dont have a lot of datapoints\nour variance will be high (same as prior) because we are not confident on what\nto predict there whereas in areas that we observe a lot of data we will\nget more confident\nour Mean of the distribution of outputs is always just the kernel ridge regression answer\nbut we provide this confidence estimate to compensate for the messyness of the real\nworld data!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "as you can see intuitively the more we observe the closer we get to the\nreal function, and in certain regions where we dont have a lot of datapoints\nour variance will be high (same as prior) because we are not confident on what\nto predict there whereas in areas that we observe a lot of data we will\nget more confident\nour Mean of the distribution of outputs is always just the kernel ridge regression answer\nbut we provide this confidence estimate to compensate for the messyness of the real\nworld data!",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "line",
			"version": 68,
			"versionNonce": 986394426,
			"isDeleted": false,
			"id": "9-DitPtJzta5Vr39Ooe2z",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3264.633026823271,
			"y": 1227.8725479151237,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 51.0292567372876,
			"height": 3.2571866002526804,
			"seed": 634357818,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					51.0292567372876,
					-3.2571866002526804
				]
			]
		},
		{
			"type": "line",
			"version": 53,
			"versionNonce": 237893990,
			"isDeleted": false,
			"id": "jFA_Myj3pcVoek5SklnKK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3288.1571522695385,
			"y": 1227.8725479151237,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.7238192445001914,
			"height": 94.45841140731909,
			"seed": 2030594598,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.7238192445001914,
					-94.45841140731909
				]
			]
		},
		{
			"type": "line",
			"version": 61,
			"versionNonce": 785725434,
			"isDeleted": false,
			"id": "SSl9mC4kwXUeIMFaCYuO2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3261.0139306007686,
			"y": 1132.328407641054,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 59.353178049043436,
			"height": 1.0857288667507419,
			"seed": 1412395322,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					59.353178049043436,
					1.0857288667507419
				]
			]
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 1043717286,
			"isDeleted": false,
			"id": "AqPMcbGn",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3228.909469363418,
			"y": 1237.6441077158806,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 130.80029296875,
			"height": 20,
			"seed": 2002406118,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "high fluctuations",
			"rawText": "high fluctuations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "high fluctuations",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 17,
			"versionNonce": 1310730426,
			"isDeleted": false,
			"id": "fsAQuI9svbEj2qZZzcph6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3449.2069341709052,
			"y": 1146.080973286564,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 20.26693884601491,
			"height": 0.3619096222503231,
			"seed": 1624058362,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					20.26693884601491,
					0.3619096222503231
				]
			]
		},
		{
			"type": "line",
			"version": 25,
			"versionNonce": 1105156070,
			"isDeleted": false,
			"id": "nXarn__U5ma5B_kIKR55v",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3458.2546747271617,
			"y": 1122.5568478402968,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.7238192445006462,
			"height": 24.9717639352682,
			"seed": 1323653990,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.7238192445006462,
					24.9717639352682
				]
			]
		},
		{
			"type": "line",
			"version": 30,
			"versionNonce": 1347355002,
			"isDeleted": false,
			"id": "3BBysyPcXerj9Hx2RArEc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3448.1212053041545,
			"y": 1122.9187574625469,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 25.333673557518523,
			"height": 1.0857288667507419,
			"seed": 1511759674,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142810013,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					25.333673557518523,
					-1.0857288667507419
				]
			]
		},
		{
			"type": "text",
			"version": 34,
			"versionNonce": 730318758,
			"isDeleted": false,
			"id": "mYFuxNvz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3414.8614909510006,
			"y": 1163.4526351545767,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 95.47219848632812,
			"height": 40,
			"seed": 1149122362,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142811572,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "small \nfluctuations",
			"rawText": "small \nfluctuations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "small \nfluctuations",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 98,
			"versionNonce": 1390241446,
			"isDeleted": false,
			"id": "9pJ0vveMImddlSd29x_3G",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1108.028438233444,
			"y": 1445.1569985689778,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 181.0089279610629,
			"height": 44.95254833470108,
			"seed": 493307386,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142902389,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-72.52344464665111,
					-11.98734622258712
				],
				[
					-119.2740949147402,
					-37.160773290019506
				],
				[
					-181.0089279610629,
					-44.95254833470108
				]
			]
		},
		{
			"type": "text",
			"version": 84,
			"versionNonce": 122480442,
			"isDeleted": false,
			"id": "CIbJaBN9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 733.2891725579975,
			"y": 1369.0373500555506,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 194.4644012451172,
			"height": 60,
			"seed": 1225414522,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709142915557,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "True function is sampled\nfrom a distribution\nof functions",
			"rawText": "True function is sampled\nfrom a distribution\nof functions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "True function is sampled\nfrom a distribution\nof functions",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 336,
			"versionNonce": 659615034,
			"isDeleted": false,
			"id": "6uCt4-Is8aqQIL8j8-p1_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 843.9985674529057,
			"y": 2034.7180481980088,
			"strokeColor": "transparent",
			"backgroundColor": "#b2f2bb",
			"width": 188.56290399213208,
			"height": 43.78614250004565,
			"seed": 1567855590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Pu0AsG0BAhFtY5Ro_MVdP",
					"type": "arrow"
				}
			],
			"updated": 1709142971482,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6aa651356a13f3f36c9a5c505143a0a91555162a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 64,
			"versionNonce": 507841062,
			"isDeleted": false,
			"id": "Pu0AsG0BAhFtY5Ro_MVdP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1041.2025471709771,
			"y": 2054.4212784326696,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 101.46263371176406,
			"height": 0.7299470051202661,
			"seed": 1306199782,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709142978812,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6uCt4-Is8aqQIL8j8-p1_",
				"focus": -0.12982343528108645,
				"gap": 8.641075725939345
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
					101.46263371176406,
					0.7299470051202661
				]
			]
		},
		{
			"type": "text",
			"version": 496,
			"versionNonce": 1329492858,
			"isDeleted": false,
			"id": "2juBYsLO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 16.480939608108258,
			"y": 2671.3293181483737,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 169.04400634765625,
			"height": 70.99122521805576,
			"seed": 1804315169,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "3PDS951JKEQ5r9Dbx7S5Q",
					"type": "arrow"
				}
			],
			"updated": 1709143866954,
			"link": null,
			"locked": false,
			"fontSize": 11.358596034888922,
			"fontFamily": 1,
			"text": "given this assumption\nthat its a Normal distribution\nat mean 0 and covariance\ngoverned by the similarities \nin data",
			"rawText": "given this assumption\nthat its a Normal distribution\nat mean 0 and covariance\ngoverned by the similarities \nin data",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "given this assumption\nthat its a Normal distribution\nat mean 0 and covariance\ngoverned by the similarities \nin data",
			"lineHeight": 1.25,
			"baseline": 67
		},
		{
			"type": "arrow",
			"version": 58,
			"versionNonce": 1873565306,
			"isDeleted": false,
			"id": "wz7I0RUs8lKH63YdiwcZU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3705.7331855150014,
			"y": 1164.7287171670741,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 235.88910597976883,
			"height": 0,
			"seed": 1759727910,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709143373060,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "LLlD1WjD",
				"focus": 0.029262938354865275,
				"gap": 9.626385463674524
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
					235.88910597976883,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 168,
			"versionNonce": 1401911098,
			"isDeleted": false,
			"id": "LLlD1WjD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3951.248676958445,
			"y": 1135.60660531772,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 351.56878662109375,
			"height": 60,
			"seed": 1560593978,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "wz7I0RUs8lKH63YdiwcZU",
					"type": "arrow"
				}
			],
			"updated": 1709143373060,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Once we get our posterior we can use that\noptimized distribution of functions to sample\na function from it",
			"rawText": "Once we get our posterior we can use that\noptimized distribution of functions to sample\na function from it",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Once we get our posterior we can use that\noptimized distribution of functions to sample\na function from it",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 181,
			"versionNonce": 839257530,
			"isDeleted": false,
			"id": "R1qx1qHu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 881.0287277299626,
			"y": 2615.7688335946773,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 948.339111328125,
			"height": 25,
			"seed": 1430900070,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709144311146,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3) if we want to make a prediction (or use this point to train our model) we sample accordingly",
			"rawText": "3) if we want to make a prediction (or use this point to train our model) we sample accordingly",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3) if we want to make a prediction (or use this point to train our model) we sample accordingly",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 52,
			"versionNonce": 907806758,
			"isDeleted": false,
			"id": "h38BAyZa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1126.851068748575,
			"y": 2653.239610447084,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 63.804388563797076,
			"height": 15.719921820065945,
			"seed": 52121,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "7mkgS5WvVNXZ-t5R2Vhvx",
					"type": "arrow"
				}
			],
			"updated": 1709144308851,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f03d687bfe1f48932952cc638c21e171d450cf82",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 167,
			"versionNonce": 634272442,
			"isDeleted": false,
			"id": "8tFtdcZOvAXAH8hRklKAU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1339.8870052462473,
			"y": 2751.813016202057,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.0602867845320816,
			"height": 91.14642413358752,
			"seed": 1083762490,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709144309242,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6tUK2POmiI7B3rVbB99O8",
				"focus": 0.0895595389701853,
				"gap": 10.779168110965202
			},
			"endBinding": {
				"elementId": "xj4X5KC7zeQJig_BmHmuy",
				"focus": 0.0049435446943087115,
				"gap": 9.30553964269484
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
					-2.0602867845320816,
					91.14642413358752
				]
			]
		},
		{
			"type": "text",
			"version": 74,
			"versionNonce": 996602342,
			"isDeleted": false,
			"id": "AFzj5o2w",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1357.1219045640391,
			"y": 2776.947171892697,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 159.80831909179688,
			"height": 20,
			"seed": 554346854,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709144308851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Proof from cookbook",
			"rawText": "Proof from cookbook",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Proof from cookbook",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 160,
			"versionNonce": 985384230,
			"isDeleted": false,
			"id": "xj4X5KC7zeQJig_BmHmuy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1099.6802659963544,
			"y": 2852.2649799783394,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 471.32191272593104,
			"height": 97.742330501688,
			"seed": 408568378,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8tFtdcZOvAXAH8hRklKAU",
					"type": "arrow"
				}
			],
			"updated": 1709144308851,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "62eb819452ec065f990c4e4738609366e9982cb2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 160,
			"versionNonce": 2140359566,
			"isDeleted": false,
			"id": "swv8flC4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1110.8503334099198,
			"y": 3000.846830733237,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 427.71588134765625,
			"height": 13.77541041448997,
			"seed": 771830138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709474822377,
			"link": null,
			"locked": false,
			"fontSize": 11.020328331591976,
			"fontFamily": 1,
			"text": "Note, that the covariance matrix is the Schur complement of the block matrix",
			"rawText": "Note, that the covariance matrix is the Schur complement of the block matrix",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note, that the covariance matrix is the Schur complement of the block matrix",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "arrow",
			"version": 83,
			"versionNonce": 1818940282,
			"isDeleted": false,
			"id": "FZADRbDKWA9zjzAPXmYa_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1487.4273197331763,
			"y": 2743.5304060241147,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 124.68490440208484,
			"height": 75.29281666792576,
			"seed": 814008038,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709144309243,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6tUK2POmiI7B3rVbB99O8",
				"focus": -0.24962836746097083,
				"gap": 2.496557933022814
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
					124.68490440208484,
					75.29281666792576
				]
			]
		},
		{
			"type": "text",
			"version": 147,
			"versionNonce": 247319910,
			"isDeleted": false,
			"id": "xcGyCWMq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1579.6798194799312,
			"y": 2817.919708892025,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 194.3684539794922,
			"height": 80,
			"seed": 1554676154,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709144308851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "can be interpereted\nas the lambda of the\nregularization parameter\nin kernel ridge regression",
			"rawText": "can be interpereted\nas the lambda of the\nregularization parameter\nin kernel ridge regression",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "can be interpereted\nas the lambda of the\nregularization parameter\nin kernel ridge regression",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"id": "-kroPH6BpK3SGoPMamUwJ",
			"type": "image",
			"x": 1102.304977226339,
			"y": 2945.3620467443548,
			"width": 446.30052987940513,
			"height": 43.89841277502345,
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
			"seed": 1109628946,
			"version": 158,
			"versionNonce": 346938834,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709474694376,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "db6d03f9aba761e2a519a33fbfdb08772c6b170a",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "XTbHm6hCr9rSZA6zOnDve",
			"type": "image",
			"x": 1143.4305738774206,
			"y": 3015.703636895861,
			"width": 363.4291262253112,
			"height": 86.4412606327007,
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
			"seed": 499746574,
			"version": 183,
			"versionNonce": 182300174,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709474800807,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b1e06c18595b1c68dccada501e953065ac6a9a39",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 293,
			"versionNonce": 27898450,
			"isDeleted": true,
			"id": "5x5psR_p56arMh3f6LPB2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1088.7456276284881,
			"y": 2935.719106734255,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 485.51196688321124,
			"height": 125.13195022763176,
			"seed": 1793046074,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709474684100,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7aa5dba15d8eae22a43e434b577efb7a02eb9b74",
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
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": -975.8760881937953,
		"scrollY": -2775.046741187609,
		"zoom": {
			"value": 2.0820803989873795
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