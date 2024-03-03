---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Model Selection ^S1gIXWxy

Assume we have a few labeled datapoints Xi
from some unknown data distribution
we would like to find f(x) such that it predicts those 
datapoints well while also generalizing for future unseen datapoints
drawn from the same distribution ^7igo6RxW

The question is always is, among the models that predict the data, which one should we use?
is it always important to fit the training data perfectly? ^r3gdonWb

Model complexity must not be increased beyond what is
necessary to correctly predict the data ^QEj7J6OR

simplicity is desirable
on its own ^nnDFYoyt

Less complex models
are likely to generalize
well for future datapoints ^YHz9S614

How do we know whats complex enough and what isnt?
In other words,
How do we quantify complexity such that we know when to stop? ^EL1qa9dP

a few approaches have been suggested.
 ^bAZubb7G

Counting the parameters
of the model ^SMaaQ0D3

Size of class function (SRM) ^6FD09oGq

Bayesian information criterion ^W86mPURK

Minimum description length ^fsLczgFd

Smoothness / Lipschitzness ^GWTP1Mpf

Idea! ^uDkSMjZ9

Lets count the parameters required for our function f(x)
the fewer parameters there are to tweak, the less variation we have
the less complex the model is!
(i.e Linear v.s polynomial) ^L8wBoTg9

Constant classifier ^xEItq91P

g(x) = C ^iQfKWExO

1 
parameter ^SCp4xoQj

Mean difference classifier ^FOzMTWHm

g(x) = x (m1 - m2) + C ^PMqSmPrO

      2D    + 1
parameters ^EGnd9aca

T ^czlYJgQi

PCA + Fischer ^FIeHcMnO

g(x) = PCA(x)  Sw  (m1-m2) + C ^Qgpip66J

k*d      k^2     2k    +  1
      Parameters  ^SwzhKjfg

V.S ^PeGUVErV

V.S ^WQDQXFPv

does it classify correctly? ^yERIPICG

does it classify correctly? ^QY3wUYH2

can we simplify it? ^ovClwnfJ

can we simplify it? ^eYq7lWJj

Problem ^VtEzzak3

Some functions's complexity cannot be characterized by the
number of their parameters ^vc5yyPn0

by setting w very high we get
 ^8XIHncQt

Other models have wayy more parameters but are
a lot more rigid ^Mw0hX9Bk

2 k ^5rsqq2wS

Never exceeds slope 1 ^ny8vTX3J

Structural Risk Minimization ^A8Cp2OrQ

Sn+1 ^ZCUayLvj

Sn ^8dwgchIM

Sn-1 ^RfayJiXW

= Datapoints ^I1s5Xst7

If there are two solutions to a problem, always choose one with the smallest region ^R7ogWtgO

= Mean estimator per solution ^qmJkVJgB

Models with the lowest generalization error are preferred!
that we means we look at our test error not the training error! ^48fAXD6o

How do we find out the test error? ^cEUj5hbk

Holdout Selection ^GTatqIF7

Split data into two parts, one used to train the model and finding out the
training accuracy, the other should only be used for testing the model on unseen
datapoints ^miqfw1kx

But how much data do I need to use?
On one hand you want to have as many tests as possible in order to ensure
it is fit for the real world, on the other hand you do not want to take away
from your training data because your model improves with larger N ^tKCFNytd

Very Dataset scarcity dependent  ^7QEzFsnj

Which datapoints do I use?
some datapoints may give false "hope" of high accuracy purely because they
were picked (randomly) to very similar training datapoints that the model
recognizes. ^vEBaCLbU

Idea! ^ZJwMrEiW

K-Fold procedure ^D80mfd4x

Retain more data for training, and make up for the lower amount of
holdout data by repeating the model selection procedure over multiple data
splits ^fzP6UXvw

The model now generalizes well across any possible datapoint in the dataset if treated as unseen
Assuming that the dataset is representative of the real world (Which is not always true) ^eZyocAvl

If k is too low      ->         Training data is heavily reduced
if k is too high      ->         The procedure is very computationally costly ^KhsznTTW

Quick intermission onto a completely
different tangent ^YHvPyQJE

Bias-Variance decomposition ^EWZKxNDT

Unknown ^nYJRHDf7

Known ^ogiOz80A

Build
dataset ^AfEviwMP

Model ^XSwuMKiB

dataset ^1RS3yF5i

Parameters assumptions
initialization
model class ^QbfjahqN

Estimate ^D88MRJn9

D ^5OigWUXe

Is it close? ^uycYLdEZ

A good machine learning model is one that can produce an estimate close to the truth!
Closeness is measured by an error function
e.g ^M0QDMwk6

Assume we have a dataset D ^DlGGwPKh

is the ground truth representing R for our problem ^TwWA2jx5

h ^wy4LH3cf

Is an estimator of the dataset D such that its trying to mimic the truth over m iterations ^FSI4hIAN

We can actually show that MSE can be
rewritten using Bias and Variance, meaning
its definition is dependent on it and thus
a good model needs to optimize the bias
and variance to get good results! ^Oz674auu

And then we have to find out what the
actual values of our Bias and variance
are/should be, but this is obviously dependant
on what we are trying to estimate
for example Estimating the mean of a Gaussian
distribution ^afBK3Ja2

Gaussian Mean estimation ^bM9rktwG

James stein Estimator suggests
that instead of always prioritizing heading towards
Bias=0, we should consider cases where the bias
is not 0 but very close to it, and see how much it
affects our variance, in some cases this achieves better results! ^SpGgv3ER

Real world
Data ^0HV6yOfU

Real
Mean ^5DMNPwEa

Our
Dataset ^Kze3hxHF

mean
estimate ^6vDFhFbI

We have M different mean estimates depending on which i.i.d random
datapoints we sample or the method we use (Like Bayesian estimator)

The Bias of the mean estimate can be interpreted as the difference
between the mean of the mean estimates (Expected value of mean estimates)
and the Real mean of the data

The variance of the mean estimate is the expected square deviation from the mean
of the mean estimates

MSE error is then related to how far the mean of our estimates is from the truth (squared)
plus the deviation of our estimates from their mean ^JKxdJSDO

The mean
of the
mean
estimates ^d40vdsSV

The bias-variance decomposition usually
applies to regression data
Lets attempt to define this over
C class classification ^oOUJKPux

Some clarification ^p8hhXJbb

Given C classes
The true probability of each class associated to
a particular input is


We are trying to estimate this distribution of probabilities with ^PNxgXkXK

Just like in the Regression case earlier,
given Multiple estimates      for the same input pattern 
   (whether its multiple iterations, approximations
up to an arbitrary accuracy, Bayesian estimator etc...)
 ^wrD0Qdsn

Just like in the MSE case, the error is evaluated by the distance between
the estimate and ground truth, the closer it is to the truth the lower the error ^xRkuOBQA

we can calculate the mean of such estimates by calculating the point
such that minimizes the distance to all estimates
EXCEPT in this case we are not dealing with number or vectors
but instead with distributions... and as such Closeness is defined using a KL divergence
which is just a fancy way of defining how close/far apart are two distributions
We define R as the mean of our estimates ^DNQKxI6s

such that ^ukbdgyvC

and ^U8gJxxwi

We can get rid of this constraint by
enforcing that Ri = exp(zi)
and build our lagrangian according to zi ^cEOpYRbA

Remember that this is expectation over
the estimate, meaning that the
mean R is a constant in this term
and can be taken out of
the expectation ^5motVAIe

This is the equivalent of this equation ^3DEPJRRI

No matter which x_i we are currently
at the mean is always the same
and thus it is a constant to be
taken out of the expectation ^U9qBtlpK

Alright well now that we have defined our mean
of estimates lets decompose our error function
into Bias and variance terms ^MsHGQXvD

Constants taken out
of the expectation ^yr0yZoap

E(logRi - logPi) is independent
value of i ^uKjVNk20

Proof ^qV4HBhxK

Sum of probabilities
is always 1 we just
exchange the probability ^d7qHQkHX


# Embedded files
7b19ec2b8d215f664336b4de89eed1074180ecba: $$\color{red} \mu$$
e5bb6ffba29b952e6989f6a79f02b299cbf953d4: $$\color{blue} \hat{\mu}$$
f7f8e275ec17066d1763efb7bf709218ea3ce377: $$\color{orange} \mu$$
0be3ba62b2da0141f4d9a27e95f64bd40402265d: $$Error(\hat{θ}) = E[(\hat{θ} − θ)^2] = Bias(\hat{θ})^2 + Var(\hat{θ})$$
231762a8a6e51311fb13d9b10685c6eac13a7089: $$P = \left[P_1....P_C\right]$$
e3b18d25624a32b3f22aa91d8f38c74700190074: $$\hat{P} = \left[\hat{P_1}....\hat{P_C}\right]$$
918fe75016407ddf7425853963e1676a682f0032: $$\hat{P}$$
b66c5f796a7e14bc678ad77572c8f5d7425941ad: $$Error = E\left[DKL(P \| \hat{P} )\right] = E\left[ \sum^C_{i=1} P_i log(\frac{P_i}{ \hat{P_i}})\right]$$
9c6a58f061b8d33db8f15175756530bff3b10a00: $$min_R E\left[ D_{KL} (R\| \hat{P}) \right]$$
df9859ab31bfe1d689789a130f3bc8a058172627: $$R = [ R_1 .... R_C]$$
947453ecbd71a27be1784d3102f26170d2e89e73: $$\color{white} min_R E\left[ D_{KL} (R\| \hat{P}) \right] = E\left[ \sum^C_{i=1} R_i log(\frac{R_i}{ \hat{P_i}})\right]$$
8617d18e2d6b7da45854dc5bff2fa7774b4ad8a9: $$\color{white} R_i \geq 0$$
c78aca2b8c2468d5ffaa71bd660f81b9da9d50ea: $$\color{white} \sum_{i=1}^C R_i = 1$$
5ce9a8470b0aaadcc8b583802f59905a5658e9f3: $$\color{white} \mathcal{L}(z, \lambda) =  E\left[ \sum^C_{i=1} exp(z_i) log(\frac{exp(z_i)}{ \hat{P_i}})\right] + \lambda \left(\sum_{i=1}^C exp(z_i)  - 1 \right)$$
4228c01f6e86270430cb31e61accf26b8e31b6de: $$\color{white} \mathcal{L}(z, \lambda) =  E\left[ \sum^C_{i=1} exp(z_i) \left( log(exp(z_i)) -log(\hat{P_i})\right) \right] + \lambda \left(\sum_{i=1}^C exp(z_i)  - 1 \right)$$
df8fd5ac91381c09e55b6a899e32132dcc5d239d: $$\color{white} \mathcal{L}(z, \lambda) =  E\left[ \sum^C_{i=1} exp(z_i)z_i -exp(z_i)log(\hat{P_i}) \right] + \lambda \left(\sum_{i=1}^C exp(z_i)  - 1 \right)$$
9e2e687b4a36b0386338e08e8ce32d5a1c8b001d: $$\color{white} \mathcal{L}(z, \lambda) = \sum^C_{i=1} exp(z_i)z_i  -exp(z_i) E\left[log(\hat{P_i}) \right] + \lambda \left(\sum_{i=1}^C exp(z_i)  - 1 \right)$$
6aae1c1d08954b8b7467abe68c5b7f4b6fcad8c7: $$\color{red} E[\mu + x_i] = \mu E[x_i]$$
b8dba8a37b10ea06169552b18a2bed3f5be96bb0: $$\color{white} \frac{\partial\mathcal{L}(z, \lambda) }{\partial z_i }=  exp(z_i)z_i + exp(z_i) -exp(z_i) E\left[log(\hat{P_i}) \right] + \lambda exp(z_i) = 0 $$
65efc70b43f45ddd64af0d1ff594a002c911483e: $$\color{white} \frac{\partial\mathcal{L}(z, \lambda) }{\partial \lambda } = \sum_{i=1}^C exp(z_i) - 1 = 0$$
1780209197cc0175c1e5599ffcb137493737e437: $$\color{white} exp(z_i) \left( z_i +1-E\left[log(\hat{P_i}) \right] + \lambda \right)= 0 $$
64b75979621d9d570659115f66d1cb431d774b53: $$\color{white} z_i  = E\left[log(\hat{P_i}) \right] - 1 - \lambda$$
8bd2540c6bc2be881539514f695424da72fdd6fc: $$\color{white} exp(z_i)  = exp(E\left[log(\hat{P_i}) \right]) exp(- 1(1 + \lambda)) = \frac{exp(E\left[log(\hat{P_i}) \right])}{exp(1 + \lambda)}$$
7694e24dd565b76a14c3ac279285ee5f11746155: $$\color{white} = \sum_{i=1}^C exp(z_i) = 1$$
5c2a348afba75bd508ee45ac467a04982a812554: $$\color{white}  \sum_{i=1}^C \frac{exp(E\left[log(\hat{P_i}) \right])}{exp(1 + \lambda)} = 1$$
fe41afea4630c63569157f45fdff277d342a6a3f: $$\color{white}  \frac{1}{exp(1 + \lambda) } \sum_{i=1}^C exp(E\left[log(\hat{P_i}) \right])= 1$$
f2ff9f3cb737e2da37ab85e7c4dc99cd010534c4: $$\color{white} \sum_{i=1}^C exp(E\left[log(\hat{P_i}) \right])=exp(1 + \lambda) $$
6d04a7d9e1f996334181d04bad7e84142c542c37: $$\color{white} R_i = exp(z_i) = \frac{exp(E\left[log(\hat{P_i}) \right])}{ \sum_{i=1}^C exp(E\left[log(\hat{P_i}) \right])}$$
456b06746e40203ac8d0288f837c66b94d2d25db: $$\color{white} Error = E\left[ \sum^C_{i=1} P_i log(\frac{P_i}{ \hat{P_i}})\right] = E\left[ \sum^C_{i=1} P_i log(P_i) - P_ilog(\hat{P_i}) \right] = E\left[ \sum^C_{i=1} P_i log(P_i) - P_ilog(\hat{P_i}) +\color{red} P_ilog(R_i) - P_i log(R_i) \color{white} \right]$$
db54025755589a96a3cfc013519885fd0b4ffafc: $$\color{white} Error = \sum^C_{i=1} P_i log(P_i) - P_i log(R_i) + E\left[ \sum^C_{i=1}  - P_ilog(\hat{P_i}) + P_ilog(R_i) \right]$$
2a8e839458336430d6c08badef3de8f8ff208318: $$\color{white} Error = D_{KL}(P\|R) + E\left[ \sum^C_{i=1}  P_i (log(R_i) - log(\hat{P_i})) \right]$$
bad5fd2db45dca9af1f9861bb84e6d37081521e8: $$\color{white} Error = D_{KL}(P\|R) +  E\left[ log(R_i) - log(\hat{P_i}) \right] \sum^C_{i=1}  P_i$$
a04db8853f041d459f61af9e9737b08ef6f2ee11: $$\color{white} Error = D_{KL}(P\|R) +  E\left[ log(R_i) - log(\hat{P_i}) \right] \sum^C_{i=1}  R_i$$
37a92c40c90e02a3e639eb4c2ab47d71fc895b63: $$\color{white} Error = D_{KL}(P\|R) + E\left[ \sum^C_{i=1}  R_i (log(R_i) - log(\hat{P_i})) \right]$$
92a02b6ab66c716b080f6b846747e830ff79fb96: $$\color{white} Error = D_{KL}(P\|R) + E\left[ D_{KL}(R\|\hat{P}) \right]$$
ab6220a15c9d1689fd5f968b60d9d6a15f819f49: $$\color{white} Error = Bias(\hat{P}) + Var(\hat{P})$$
3f7033b628aec6663353f2a1073cb254bee8a726: $$E\left[ log(R_i) - log(\hat{P_i}) \right] = E\left[ log( exp(E[log(\hat{P_i})] )) - log(Z) - log(\hat{P_i}) \right] 
$$
8645ceec0dbad0d7d1e9ff888de9e068694e7c2f: $$=  - log(Z) E[ E[log(\hat{P_i})]  - log(\hat{P_i}) ]
$$
ff96b112342a866dff1f1caf25fddaa0e860122b: $$=  - log(Z) \left( E[log(\hat{P_i})]  - E[ log(\hat{P_i}) ] \right)
$$
e0ace05baa197b5ba77625088e5d5b8d302b25c7: $$=  - log(Z)
$$
a62744e90ad1f1ec575a8bcd5c88e4f442beee38: [[Pasted Image 20231229104003_445.png]]
ac81ec161d252535f1e24b61f2a6d25499806fd6: [[Pasted Image 20231229104907_499.png]]
afb106f4fb3e9c29f93f217b00259098bb32c283: [[Pasted Image 20231229105827_647.png]]
810c641cc3af09fea5680a4b2d02023baeb506f0: [[Pasted Image 20231229105842_661.png]]
bda3ab84934eef00750f29bfc9b370797b09688b: [[Pasted Image 20231229105957_667.png]]
05fe94680ecd9ee217806365bb52e3ca5c60aed7: [[Pasted Image 20231229110027_670.png]]
ed1e58ad69663e8decc50e3a1ba3dbae31ad68e0: [[Pasted Image 20231229111358_711.png]]
6b04f622f52b2d997fe2a15d0024d9d4d737294e: [[Pasted Image 20231229112430_815.png]]
27212147e0f7ff709a3c8f18c2dfaefe0b26c2d4: [[Pasted Image 20231229112838_842.png]]
ac52072e6e98681be4ffeac7cf3aa66bf841322d: [[Pasted Image 20231229113438_022.png]]
64a9924df1d3bc96f52fd61da1cc81555291ba39: [[Pasted Image 20231229114917_217.png]]
24697b204650f595ce1efcd22ce52feb35a84b2e: [[Pasted Image 20231229115228_253.png]]
84eac6406ca07f23a07928242a8784e29e270ca9: [[Pasted Image 20231229115415_273.png]]
24dfb7486b6be02043f2c0b3a762b2a829d74b37: [[Pasted Image 20231229115634_303.png]]
dfa7e74f81c4b7fca2fef6d8d90d9a89bf68e21a: [[Pasted Image 20231229115704_316.png]]
3247e6db80945068709dfefcf914bcecc9b48cf3: [[Pasted Image 20231229115749_335.png]]
110bccb4790eb4371efa8ecec27ff7d3f70df6c0: [[Pasted Image 20231229120113_415.png]]
390f78561cb2f653451590a2384fd56d8eb1f973: [[Pasted Image 20231229120355_449.png]]
bb3df2b0d8381749fcbd467ce2b1651b84bfb2a4: [[Pasted Image 20231229120733_580.png]]
579caa87f001c3fb6392b9fba54e631702eb11d2: [[Pasted Image 20231229120748_590.png]]
1a22454755940e9b4ebf2677e02bc5515fd858ec: [[Pasted Image 20231229120806_605.png]]
4d7e87dc0271b0dadbb715a5a15c3a1b8378c705: [[Pasted Image 20231229120806_616.png]]

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
			"version": 276,
			"versionNonce": 64719174,
			"isDeleted": false,
			"id": "uZG2jjV53pzsLGMF_3fg4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3183.576519690019,
			"y": 3231.9014468194773,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 188,
			"height": 163,
			"seed": 74933973,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1a22454755940e9b4ebf2677e02bc5515fd858ec",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 941,
			"versionNonce": 1618023962,
			"isDeleted": false,
			"id": "JhWLVMWC-9jKKihWQSEZK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1987.5665644931323,
			"y": 1060.1640340497706,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 204.69157438117628,
			"height": 199.2238049094899,
			"seed": 2098651291,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					65.41044383458203,
					-13.424784697404919
				],
				[
					119.6768861269758,
					38.66337992852635
				],
				[
					136.15062753716694,
					114.9161570097867
				],
				[
					93.02818678696036,
					168.61529579940665
				],
				[
					14.535654185462334,
					185.79902021208497
				],
				[
					-29.08632822544496,
					184.0858215883054
				],
				[
					0,
					144.45068334407785
				],
				[
					-62.50331299748935,
					113.3051828460983
				],
				[
					-31.70128955841892,
					68.71095604537743
				],
				[
					-68.54094684400934,
					40.22821216369425
				],
				[
					-46.68915807065105,
					10.485499666622786
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "image",
			"version": 303,
			"versionNonce": 1801875590,
			"isDeleted": false,
			"id": "lOLglJVT5xMjjFaKkHJ3U",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1375.31421742049,
			"y": 1179.0710725436313,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 485,
			"height": 305,
			"seed": 1997934997,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "05fe94680ecd9ee217806365bb52e3ca5c60aed7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 690,
			"versionNonce": 953893594,
			"isDeleted": false,
			"id": "NKW5cF9opTReMbdwuNQdj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 92.38931255828322,
			"y": 136.76205228712433,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 197.59878476364247,
			"height": 115.43571618494576,
			"seed": 881640501,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.413718560012654,
					-39.72346704011366
				],
				[
					31.914580357014444,
					-33.61216441855771
				],
				[
					25.803277735458465,
					-76.39128276944939
				],
				[
					63.4896439017202,
					-65.52674477557213
				],
				[
					54.66220678169492,
					-101.17601006798185
				],
				[
					93.02760657257397,
					-84.87920307716598
				],
				[
					98.45987556951258,
					-113.39861531109378
				],
				[
					125.28170374189705,
					-85.21871988947464
				],
				[
					133.76962404961364,
					-115.43571618494576
				],
				[
					153.46159916351615,
					-87.25582076332662
				],
				[
					150.74546466504682,
					-74.3541818955974
				],
				[
					174.5116415266533,
					-89.29292163717861
				],
				[
					176.20922558819666,
					-62.131576652485506
				],
				[
					160.25193540968945,
					-33.95168123086637
				],
				[
					196.5802343267165,
					-55.34124040631221
				],
				[
					181.64149458513526,
					-16.975840615433185
				],
				[
					196.24071751440783,
					-35.309748480101035
				],
				[
					197.59878476364247,
					-3.7346849353952507
				]
			]
		},
		{
			"type": "ellipse",
			"version": 77,
			"versionNonce": 1200779206,
			"isDeleted": false,
			"id": "3aePKNrNxVNkD166AH7Pg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -205,
			"y": -411,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 391,
			"height": 176,
			"seed": 9164245,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "S1gIXWxy"
				}
			],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 46,
			"versionNonce": 81909658,
			"isDeleted": false,
			"id": "S1gIXWxy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -114.33382762626692,
			"y": -340.7253967444162,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 209.18890380859375,
			"height": 35,
			"seed": 662754325,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Model Selection",
			"rawText": "Model Selection",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "3aePKNrNxVNkD166AH7Pg",
			"originalText": "Model Selection",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 332,
			"versionNonce": 343705350,
			"isDeleted": false,
			"id": "7igo6RxW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -349.4196472167969,
			"y": -221,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 672.6392211914062,
			"height": 125,
			"seed": 1949353339,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Assume we have a few labeled datapoints Xi\nfrom some unknown data distribution\nwe would like to find f(x) such that it predicts those \ndatapoints well while also generalizing for future unseen datapoints\ndrawn from the same distribution",
			"rawText": "Assume we have a few labeled datapoints Xi\nfrom some unknown data distribution\nwe would like to find f(x) such that it predicts those \ndatapoints well while also generalizing for future unseen datapoints\ndrawn from the same distribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assume we have a few labeled datapoints Xi\nfrom some unknown data distribution\nwe would like to find f(x) such that it predicts those \ndatapoints well while also generalizing for future unseen datapoints\ndrawn from the same distribution",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "arrow",
			"version": 185,
			"versionNonce": 1689769050,
			"isDeleted": false,
			"id": "xa80ttMr1FivifECTiSTx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -311.5494358714451,
			"y": 153.2417585184989,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 251.22607108402286,
			"height": 2.844068729253081,
			"seed": 1533469435,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
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
					251.22607108402286,
					2.844068729253081
				]
			]
		},
		{
			"type": "arrow",
			"version": 196,
			"versionNonce": 1117894214,
			"isDeleted": false,
			"id": "soj7vWTrWO0Q-Zx7I6JNE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -312.35837133106685,
			"y": 153.3808459686283,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 0.948022909751046,
			"height": 213.3051546939817,
			"seed": 981026389,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
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
					0.948022909751046,
					-213.3051546939817
				]
			]
		},
		{
			"type": "ellipse",
			"version": 101,
			"versionNonce": 2049980698,
			"isDeleted": false,
			"id": "vOCsEdj5HPTO-yP65LS3S",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -292.0329964064648,
			"y": 128.16709216951264,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 933721589,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 719256966,
			"isDeleted": false,
			"id": "GDvyiDtb_cCm7Kz8ta0yh",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -288.46946391090034,
			"y": 91.58149188171751,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1404843989,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 884868570,
			"isDeleted": false,
			"id": "yVgwxHCdDrBPjg5jGnfes",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -263.28716760891155,
			"y": 94.43231787816904,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 2126715195,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 40983750,
			"isDeleted": false,
			"id": "k-jVobumAbLsfdNBO_2XZ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -267.5634066035889,
			"y": 51.669927931395534,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1662366389,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 494156442,
			"isDeleted": false,
			"id": "utWylkNYmvHXyqbqTjiXX",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -229.0772556514927,
			"y": 61.64781891897604,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1785001051,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 1324733446,
			"isDeleted": false,
			"id": "Xe2OYa3uI0v6GbhDXbR2v",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -237.62973364084735,
			"y": 28.863319959782984,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1355178389,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 587585370,
			"isDeleted": false,
			"id": "qi4DU0ugCYOwfItF2uMD8",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -200.09385802090173,
			"y": 42.642312275965594,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1104796539,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 1516856134,
			"isDeleted": false,
			"id": "b-OsUwk8SpbGtNFCGuoAx",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -194.86734369407384,
			"y": 16.034602975750914,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1003340917,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 1707465754,
			"isDeleted": false,
			"id": "t6dZaXAIVlZJvOLZEL9LH",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -167.30935906170873,
			"y": 43.11744994204082,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 62541467,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 657001094,
			"isDeleted": false,
			"id": "b8J0R3jAEJgREcX_JWbMV",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -160.18229407057981,
			"y": 14.134052311449864,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1937464149,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 61294810,
			"isDeleted": false,
			"id": "Ke-E4qwui3hGBjqM65wOA",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -144.9778887561714,
			"y": 52.620203263546045,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 2135870907,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 1676790214,
			"isDeleted": false,
			"id": "ekvrVQhr18q6PvY5p80vq",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -119.32045478810721,
			"y": 35.9903849509119,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1164879413,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 1681726874,
			"isDeleted": false,
			"id": "7Hwf2skJpfv3-asflBmq-",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -139.7513744293435,
			"y": 38.36607328128821,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1720703195,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 1608556806,
			"isDeleted": false,
			"id": "ovFHjozPhE4Q526xD5ZRA",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -115.04421579342988,
			"y": 67.8246085779544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 194454805,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 79321690,
			"isDeleted": false,
			"id": "Qc8j6ZpbLu3qAuK5Czbay",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -132.1491717721393,
			"y": 92.05662954779274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 539357179,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 2121437254,
			"isDeleted": false,
			"id": "yBQpd8iDbHGRJNtH97YY5",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -98.41439748079574,
			"y": 74.00139823693286,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 2050250741,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 1139932954,
			"isDeleted": false,
			"id": "e5Wlce-bnc-aUcZlWz_zX",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -96.98898448256995,
			"y": 95.8577308763949,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 490512053,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 730109830,
			"isDeleted": false,
			"id": "DHb2sgAw5TXPIY0Pdorae",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -109.81770146660199,
			"y": 107.26103486220114,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 151898203,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 103,
			"versionNonce": 777456602,
			"isDeleted": false,
			"id": "23AMRj7jAiDFpW-G18jb5",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -95.08843381826892,
			"y": 121.0400271783837,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 957992341,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085657,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 243,
			"versionNonce": 1330886342,
			"isDeleted": false,
			"id": "TcBuDliKmogTPW_rr07q0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -286.80648207963696,
			"y": 132.91846883026525,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 196.7069937551583,
			"height": 107.85625019908439,
			"seed": 2035997109,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					33.73477429134357,
					-69.37009924698819
				],
				[
					108.33138786515963,
					-107.85625019908439
				],
				[
					169.14900912279313,
					-66.04413558446137
				],
				[
					196.7069937551583,
					-8.077340323279458
				]
			]
		},
		{
			"type": "ellipse",
			"version": 106,
			"versionNonce": 1241284762,
			"isDeleted": false,
			"id": "BS6DFr-WN57DZMM5JkHR3",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -253.62359144472748,
			"y": 72.47838183648582,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 591521339,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 108,
			"versionNonce": 1115483654,
			"isDeleted": false,
			"id": "26kWSAzlzwvi8waOC1Be_",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -212.40045927861104,
			"y": 32.67673698644232,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 379285691,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 108,
			"versionNonce": 1653955930,
			"isDeleted": false,
			"id": "rkcbD6I8yVumQleZw4hKM",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -114.79166357493301,
			"y": 49.7345847793181,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1800565557,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 108,
			"versionNonce": 1107115334,
			"isDeleted": false,
			"id": "DAsTKO_ijBGS3lxUCEmKN",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -116.68697999636362,
			"y": 83.37645125971198,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 177642459,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 108,
			"versionNonce": 1433707034,
			"isDeleted": false,
			"id": "rE6F2IbESdNtjfE4Cu6kR",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -284.89631239833307,
			"y": 106.59407742223732,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 679137813,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 174,
			"versionNonce": 1664197766,
			"isDeleted": false,
			"id": "h33zqjS4HYD5SyQ9RDDox",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 70.11903732039332,
			"y": 157.82454962730074,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 251.22607108402286,
			"height": 2.844068729253081,
			"seed": 1801173499,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
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
					251.22607108402286,
					2.844068729253081
				]
			]
		},
		{
			"type": "arrow",
			"version": 185,
			"versionNonce": 1569541850,
			"isDeleted": false,
			"id": "YWR4CNoX3_5qH-teRkEVw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 69.31010186077157,
			"y": 157.96363707743015,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 0.948022909751046,
			"height": 213.3051546939817,
			"seed": 90751643,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
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
					0.948022909751046,
					-213.3051546939817
				]
			]
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 131539910,
			"isDeleted": false,
			"id": "rDIOtBpvyci2-PnaFb3sF",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 89.63547678537361,
			"y": 132.74988327831448,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 906737467,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 1601332122,
			"isDeleted": false,
			"id": "F7zpjKfcHOgOcn7d1JYOR",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 93.19900928093807,
			"y": 96.16428299051935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 195499995,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 1376434950,
			"isDeleted": false,
			"id": "ywt5Xe5lYSMAJK8f-pGru",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 118.38130558292687,
			"y": 99.01510898697089,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 609051771,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 894885978,
			"isDeleted": false,
			"id": "qybEfCznEYtDnUzHmBQYv",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 114.10506658824954,
			"y": 56.25271904019738,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 935402779,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 407464518,
			"isDeleted": false,
			"id": "AgIpE5a39wvdevDGp7pmD",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 152.59121754034572,
			"y": 66.23061002777789,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1635041723,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 2064499994,
			"isDeleted": false,
			"id": "wLB2zqUwFd7AeQW23ney4",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 144.03873955099107,
			"y": 33.44611106858483,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 713740891,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 1500524934,
			"isDeleted": false,
			"id": "MdWbR20YFKBJ7FH1CTm7m",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 181.57461517093668,
			"y": 47.225103384767436,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1406521083,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 1510609370,
			"isDeleted": false,
			"id": "uICRCjBusJ5uBlmup6AOu",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 186.80112949776458,
			"y": 20.617394084552757,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1608005531,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 817631430,
			"isDeleted": false,
			"id": "DdzQaq8MtQEkJVVdXKobw",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 214.35911413012968,
			"y": 47.70024105084266,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1556384827,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 1432274586,
			"isDeleted": false,
			"id": "OCgaS1oziORPyOT0HD1XJ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 221.4861791212586,
			"y": 18.716843420251706,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1853705435,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 1237977094,
			"isDeleted": false,
			"id": "LrTAk-uxAyU9XYU2IWfw-",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 236.690584435667,
			"y": 57.20299437234789,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 412416379,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 364831578,
			"isDeleted": false,
			"id": "vFxmPEOuBqJLRHUjEqnGh",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 262.3480184037312,
			"y": 40.573176059713745,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1213075995,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 1419188038,
			"isDeleted": false,
			"id": "WKKPcPHL_c7zQmLwAroAT",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 241.9170987624949,
			"y": 42.94886439009005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 513480379,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 897411098,
			"isDeleted": false,
			"id": "zXBFjS1CC7NiUb05lLGAj",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 266.62425739840853,
			"y": 72.40739968675624,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 2048821083,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 2038447750,
			"isDeleted": false,
			"id": "R0jRccayc0qvnFcRV_-eX",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 249.5193014196991,
			"y": 96.63942065659458,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1093329915,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 210588890,
			"isDeleted": false,
			"id": "-FM6Q4TkmHjp7Wrk_DMqQ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 283.2540757110427,
			"y": 78.5841893457347,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1807920283,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 1296203206,
			"isDeleted": false,
			"id": "Tqy4ULgQ5RpI90BWLdyzV",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 284.67948870926847,
			"y": 100.44052198519674,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1301831995,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 2088872346,
			"isDeleted": false,
			"id": "typzexEMZPk7IQ8QQLqna",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 271.8507717252364,
			"y": 111.84382597100299,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 537821659,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 1157289222,
			"isDeleted": false,
			"id": "3myd2MjKzOvwFaVqVcodi",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 286.5800393735695,
			"y": 125.62281828718554,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1278709371,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 121,
			"versionNonce": 1015899738,
			"isDeleted": false,
			"id": "v4QHV49Zfg7yLC-8X3pdP",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 134.09308938739878,
			"y": 82.80697020356115,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1079798715,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 114,
			"versionNonce": 707150918,
			"isDeleted": false,
			"id": "knBwh3Au83Icbyde5PSPh",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 169.26801391322738,
			"y": 27.50818301019501,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1659714651,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 122,
			"versionNonce": 629377818,
			"isDeleted": false,
			"id": "MsUsXmQSoBlQ538V23jMf",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 246.01049325791226,
			"y": 72.76440919099792,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1750792443,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 120,
			"versionNonce": 245484422,
			"isDeleted": false,
			"id": "CUGR5r7g6PzjG97knEXrH",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 280.40442267820885,
			"y": 65.88328448146312,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 1042817435,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 97,
			"versionNonce": 2111248346,
			"isDeleted": false,
			"id": "g2X3QK7iz3GuqgwY63wXL",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 96.77216079350535,
			"y": 111.17686853103916,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 7.127064991128918,
			"height": 7.602202657204174,
			"seed": 2106013243,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 88,
			"versionNonce": 1084910278,
			"isDeleted": false,
			"id": "2H84IWIA4jf4Se2ax3vLJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 277.4388054833107,
			"y": -50.94445751012523,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 25.274449763614257,
			"height": 35.26667408876409,
			"seed": 1040135221,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-25.274449763614257,
					35.26667408876409
				]
			]
		},
		{
			"type": "line",
			"version": 86,
			"versionNonce": 1167789210,
			"isDeleted": false,
			"id": "TvzvJy6B5zPcpAfl9-6nM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 243.93546509898488,
			"y": -49.76890170716641,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 40.55667520207862,
			"height": 32.91556248284644,
			"seed": 819653499,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					40.55667520207862,
					32.91556248284644
				]
			]
		},
		{
			"type": "line",
			"version": 125,
			"versionNonce": 1054679558,
			"isDeleted": false,
			"id": "eC_hltFpGgJUHigNlruWi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -127.80966993345083,
			"y": -9.722452832485715,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 11.75555802958803,
			"height": 10.580002226629233,
			"seed": 853123189,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					11.75555802958803,
					10.580002226629233
				]
			]
		},
		{
			"type": "line",
			"version": 116,
			"versionNonce": 42101082,
			"isDeleted": false,
			"id": "AInvN1cHL3WtXW0CwRe1r",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -114.878556100904,
			"y": 0.2697714926641197,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 37.617785694681686,
			"height": 32.32778458136707,
			"seed": 1451394491,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					37.617785694681686,
					-32.32778458136707
				]
			]
		},
		{
			"type": "text",
			"version": 189,
			"versionNonce": 741798214,
			"isDeleted": false,
			"id": "r3gdonWb",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -495.8468502165343,
			"y": 204.8607327877491,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 929.879150390625,
			"height": 50,
			"seed": 1272426811,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085658,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The question is always is, among the models that predict the data, which one should we use?\nis it always important to fit the training data perfectly?",
			"rawText": "The question is always is, among the models that predict the data, which one should we use?\nis it always important to fit the training data perfectly?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The question is always is, among the models that predict the data, which one should we use?\nis it always important to fit the training data perfectly?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 53,
			"versionNonce": 199241242,
			"isDeleted": false,
			"id": "QEj7J6OR",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -297.6084219129282,
			"y": 267.8419781844697,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 543.159423828125,
			"height": 50,
			"seed": 300280565,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Model complexity must not be increased beyond what is\nnecessary to correctly predict the data",
			"rawText": "Model complexity must not be increased beyond what is\nnecessary to correctly predict the data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Model complexity must not be increased beyond what is\nnecessary to correctly predict the data",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 284,
			"versionNonce": 1142216838,
			"isDeleted": false,
			"id": "-LrZKyydWi7aNdukT-6DM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -891.0567965998584,
			"y": 443.1822397717608,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 836.0379881580764,
			"height": 432.8423626634012,
			"seed": 1702521723,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a62744e90ad1f1ec575a8bcd5c88e4f442beee38",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 248,
			"versionNonce": 1453808346,
			"isDeleted": false,
			"id": "6Z6itoIGQohk3EKigQ5rg",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -23.926355709089933,
			"y": 326.6053656359771,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 202.20757991297063,
			"height": 67.76745067165075,
			"seed": 1834578677,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.9430248586051,
					63.911361292505035
				],
				[
					202.20757991297063,
					67.76745067165075
				]
			]
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 1312020422,
			"isDeleted": false,
			"id": "nnDFYoyt",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 145.59596658577686,
			"y": 358.36785120540935,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 203.5997314453125,
			"height": 50,
			"seed": 1715856565,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "simplicity is desirable\non its own",
			"rawText": "simplicity is desirable\non its own",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "simplicity is desirable\non its own",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 197,
			"versionNonce": 1097527194,
			"isDeleted": false,
			"id": "oaOHmymoYsT8Z8pSAmnMO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -25.80610162945777,
			"y": 328.48511155634486,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 176.69611651457262,
			"height": 64.53794326596096,
			"seed": 618958805,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-19.42404117713386,
					62.03161537213725
				],
				[
					-176.69611651457262,
					64.53794326596096
				]
			]
		},
		{
			"type": "text",
			"version": 136,
			"versionNonce": 313585414,
			"isDeleted": false,
			"id": "YHz9S614",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -457.8152963004142,
			"y": 346.6559887865669,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 262.49969482421875,
			"height": 75,
			"seed": 220248181,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Less complex models\nare likely to generalize\nwell for future datapoints",
			"rawText": "Less complex models\nare likely to generalize\nwell for future datapoints",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Less complex models\nare likely to generalize\nwell for future datapoints",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 210,
			"versionNonce": 1616768090,
			"isDeleted": false,
			"id": "EL1qa9dP",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -424.03035806197863,
			"y": 922.9125129104763,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 890.8238525390625,
			"height": 105,
			"seed": 1992028469,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YwY0or2kFG9IE9JuR7Dhr",
					"type": "arrow"
				}
			],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "How do we know whats complex enough and what isnt?\nIn other words,\nHow do we quantify complexity such that we know when to stop?",
			"rawText": "How do we know whats complex enough and what isnt?\nIn other words,\nHow do we quantify complexity such that we know when to stop?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we know whats complex enough and what isnt?\nIn other words,\nHow do we quantify complexity such that we know when to stop?",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 1309220422,
			"isDeleted": false,
			"id": "bAZubb7G",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -165.11307083955614,
			"y": 1035.2097234943808,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 393.1395568847656,
			"height": 50,
			"seed": 873167797,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "a few approaches have been suggested.\n",
			"rawText": "a few approaches have been suggested.\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a few approaches have been suggested.\n",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 224,
			"versionNonce": 1230197018,
			"isDeleted": false,
			"id": "D7_63HgcHwFqx7CCYAWGZ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 21.863997385199696,
			"y": 1075.7491627821341,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 247.11854561403453,
			"height": 135.48056576686827,
			"seed": 206248085,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-57.11266806184369,
					117.45812865548987
				],
				[
					-247.11854561403453,
					135.48056576686827
				]
			]
		},
		{
			"type": "ellipse",
			"version": 316,
			"versionNonce": 622421382,
			"isDeleted": false,
			"id": "izS_jJC1ZIHp688Ee8yTb",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 316.05493619527954,
			"y": 1118.2539289510537,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 210.13151456716082,
			"height": 150.8636514841155,
			"seed": 1229365083,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "SMaaQ0D3"
				},
				{
					"id": "_OLY58VTQsQVWJFzKq37e",
					"type": "arrow"
				}
			],
			"updated": 1708894085659,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 299,
			"versionNonce": 1606295002,
			"isDeleted": false,
			"id": "SMaaQ0D3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 359.20805758050363,
			"y": 1156.3473991936205,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 124.23985290527344,
			"height": 75,
			"seed": 1883546619,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Counting the\nparameters\nof the model",
			"rawText": "Counting the parameters\nof the model",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "izS_jJC1ZIHp688Ee8yTb",
			"originalText": "Counting the parameters\nof the model",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "line",
			"version": 245,
			"versionNonce": 421446854,
			"isDeleted": false,
			"id": "30JQdkMCddrxhemv7_cIh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 21.86399738519981,
			"y": 1076.8267602927351,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 159.7447238828438,
			"height": 276.99455534202184,
			"seed": 1271833301,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-63.57825312544878,
					212.28670958836233
				],
				[
					-159.7447238828438,
					276.99455534202184
				]
			]
		},
		{
			"type": "ellipse",
			"version": 318,
			"versionNonce": 548491930,
			"isDeleted": false,
			"id": "JaLwsPtiuyr_vEvusV2Y1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 27.324841448032544,
			"y": 1420.2992124682587,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 197.20034443995098,
			"height": 164.8724191219262,
			"seed": 78765589,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "6FD09oGq"
				},
				{
					"id": "cSJLyikncSWdhgBRQhQBQ",
					"type": "arrow"
				}
			],
			"updated": 1708894085659,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 2075540486,
			"isDeleted": false,
			"id": "6FD09oGq",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 87.4242026327777,
			"y": 1452.9442192333495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.55992126464844,
			"height": 100,
			"seed": 107155477,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Size of\nclass\nfunction\n(SRM)",
			"rawText": "Size of class function (SRM)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "JaLwsPtiuyr_vEvusV2Y1",
			"originalText": "Size of class function (SRM)",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "line",
			"version": 290,
			"versionNonce": 1860169562,
			"isDeleted": false,
			"id": "RQIeSsGtqkMxs0KEAbesV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 20.786399874599397,
			"y": 1077.9043578033363,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 297.4169129258278,
			"height": 125.00131122969606,
			"seed": 2009826875,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.93993776502066,
					105.60455603888113
				],
				[
					297.4169129258278,
					125.00131122969606
				]
			]
		},
		{
			"type": "ellipse",
			"version": 264,
			"versionNonce": 1658637126,
			"isDeleted": false,
			"id": "7uz9fYu535aEgy_uewzuG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -416.18181863913446,
			"y": 1148.2433102623188,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 191.81235688694676,
			"height": 139.0100788675063,
			"seed": 668180533,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "W86mPURK"
				}
			],
			"updated": 1708894085659,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 156,
			"versionNonce": 1587344410,
			"isDeleted": false,
			"id": "W86mPURK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -372.7014889059235,
			"y": 1180.1008649858268,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 105.21987915039062,
			"height": 75,
			"seed": 80785083,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Bayesian\ninformation\ncriterion",
			"rawText": "Bayesian information criterion",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "7uz9fYu535aEgy_uewzuG",
			"originalText": "Bayesian information criterion",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "line",
			"version": 366,
			"versionNonce": 485454470,
			"isDeleted": false,
			"id": "3iZ8iBL0bwllIDzA8ggGN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 18.631204853397662,
			"y": 1075.7491627821346,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 252.15781748059328,
			"height": 267.24418262900485,
			"seed": 1333104405,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					7.543182574205844,
					120.69092118729259
				],
				[
					112.07014110248599,
					205.8211245247578
				],
				[
					252.15781748059328,
					267.24418262900485
				]
			]
		},
		{
			"type": "ellipse",
			"version": 195,
			"versionNonce": 31154394,
			"isDeleted": false,
			"id": "eJOtYWC1xxA-3XnxIEZh6",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 262.8537603527153,
			"y": 1288.5260958011017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 245.6922324169882,
			"height": 172.41560169613194,
			"seed": 1757685403,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "fsLczgFd"
				}
			],
			"updated": 1708894085659,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 615199174,
			"isDeleted": false,
			"id": "fsLczgFd",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 334.75461395185414,
			"y": 1337.2757760783209,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 102.15988159179688,
			"height": 75,
			"seed": 6145659,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Minimum\ndescription\nlength",
			"rawText": "Minimum description length",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "eJOtYWC1xxA-3XnxIEZh6",
			"originalText": "Minimum description length",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "line",
			"version": 276,
			"versionNonce": 875443610,
			"isDeleted": false,
			"id": "golRpv7oDd1O9BwpFeaDK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 16.476009832196155,
			"y": 1080.059552824538,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 67.08690483386863,
			"height": 347.095683178208,
			"seed": 61132725,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.0250488642406026,
					197.78351324444975
				],
				[
					67.08690483386863,
					347.095683178208
				]
			]
		},
		{
			"type": "ellipse",
			"version": 249,
			"versionNonce": 355272966,
			"isDeleted": false,
			"id": "w9movn3CVHUyg-167I_q-",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -324.5653881455079,
			"y": 1316.5322694895256,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 198.27794195055176,
			"height": 133.6220913145021,
			"seed": 1621390805,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "GWTP1Mpf"
				}
			],
			"updated": 1708894085659,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 227,
			"versionNonce": 1724412506,
			"isDeleted": false,
			"id": "GWTP1Mpf",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -288.58818472074887,
			"y": 1345.6007717043703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 126.11985778808594,
			"height": 75,
			"seed": 1726066293,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Smoothness\n/\nLipschitzness",
			"rawText": "Smoothness / Lipschitzness",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "w9movn3CVHUyg-167I_q-",
			"originalText": "Smoothness / Lipschitzness",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 879,
			"versionNonce": 347569111,
			"isDeleted": false,
			"id": "_OLY58VTQsQVWJFzKq37e",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 527.1646546212761,
			"y": 1195.2351745820379,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 957.5355573984087,
			"height": 911.26999153582,
			"seed": 848929275,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709384558614,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "izS_jJC1ZIHp688Ee8yTb",
				"gap": 1,
				"focus": 0.2579706817267893
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
					545.7757150136257,
					-95.08252184208231
				],
				[
					586.4190406761064,
					-820.7977289935761
				],
				[
					957.5355573984087,
					-911.26999153582
				]
			]
		},
		{
			"type": "text",
			"version": 277,
			"versionNonce": 1820137242,
			"isDeleted": false,
			"id": "uDkSMjZ9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1630.373133439437,
			"y": 295.28813855827184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 52.479949951171875,
			"height": 25,
			"seed": 1991845531,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_OLY58VTQsQVWJFzKq37e",
					"type": "arrow"
				}
			],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Idea!",
			"rawText": "Idea!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea!",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 360,
			"versionNonce": 1993801606,
			"isDeleted": false,
			"id": "Lw6IazYwOboDNnbhjm05J",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1590.3779257777524,
			"y": 287.6576625066625,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 34.30686937101874,
			"height": 37.301913522456886,
			"seed": 263322043,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ac81ec161d252535f1e24b61f2a6d25499806fd6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 449,
			"versionNonce": 1170154458,
			"isDeleted": false,
			"id": "L8wBoTg9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1279.9973770760353,
			"y": 338.1532097208624,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 698.499267578125,
			"height": 100,
			"seed": 1571392757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets count the parameters required for our function f(x)\nthe fewer parameters there are to tweak, the less variation we have\nthe less complex the model is!\n(i.e Linear v.s polynomial)",
			"rawText": "Lets count the parameters required for our function f(x)\nthe fewer parameters there are to tweak, the less variation we have\nthe less complex the model is!\n(i.e Linear v.s polynomial)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets count the parameters required for our function f(x)\nthe fewer parameters there are to tweak, the less variation we have\nthe less complex the model is!\n(i.e Linear v.s polynomial)",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 310,
			"versionNonce": 1410932422,
			"isDeleted": false,
			"id": "xEItq91P",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1182.2542566888835,
			"y": 468.6122250727967,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 187.8197784423828,
			"height": 25,
			"seed": 919063803,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Constant classifier",
			"rawText": "Constant classifier",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Constant classifier",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 354,
			"versionNonce": 1822529690,
			"isDeleted": false,
			"id": "iQfKWExO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1230.7558005104586,
			"y": 500.2177575378794,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 81.53990173339844,
			"height": 25,
			"seed": 816317077,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "g(x) = C",
			"rawText": "g(x) = C",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "g(x) = C",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 436,
			"versionNonce": 1515542022,
			"isDeleted": false,
			"id": "SCp4xoQj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1261.3565036740954,
			"y": 524.2174195157343,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 99.57987976074219,
			"height": 50,
			"seed": 532489365,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1 \nparameter",
			"rawText": "1 \nparameter",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1 \nparameter",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 448,
			"versionNonce": 550991194,
			"isDeleted": false,
			"id": "FOzMTWHm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1466.5146894496027,
			"y": 468.0016484105213,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 253.3197021484375,
			"height": 25,
			"seed": 722316859,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Mean difference classifier",
			"rawText": "Mean difference classifier",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mean difference classifier",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 431,
			"versionNonce": 310945094,
			"isDeleted": false,
			"id": "PMqSmPrO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1476.766279047545,
			"y": 499.6071808756037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 223.53973388671875,
			"height": 25,
			"seed": 458370779,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "g(x) = x (m1 - m2) + C",
			"rawText": "g(x) = x (m1 - m2) + C",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "g(x) = x (m1 - m2) + C",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 531,
			"versionNonce": 867416602,
			"isDeleted": false,
			"id": "EGnd9aca",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1535.1839420019755,
			"y": 522.6222194904578,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 157.75979614257812,
			"height": 50,
			"seed": 1551735675,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "      2D    + 1\nparameters",
			"rawText": "      2D    + 1\nparameters",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "      2D    + 1\nparameters",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 414,
			"versionNonce": 1578110086,
			"isDeleted": false,
			"id": "czlYJgQi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1555.179434870882,
			"y": 492.19712458446884,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.864028930664062,
			"height": 20,
			"seed": 903168411,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "T",
			"rawText": "T",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "T",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 441,
			"versionNonce": 1411999450,
			"isDeleted": false,
			"id": "FIeHcMnO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1897.6654647790383,
			"y": 473.57400491934004,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 137.8998565673828,
			"height": 25,
			"seed": 1995844021,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085659,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "PCA + Fischer",
			"rawText": "PCA + Fischer",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PCA + Fischer",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 449,
			"versionNonce": 1789430726,
			"isDeleted": false,
			"id": "Qgpip66J",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1805.8971340278595,
			"y": 505.17953738442293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 312.15972900390625,
			"height": 25,
			"seed": 441527061,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "g(x) = PCA(x)  Sw  (m1-m2) + C",
			"rawText": "g(x) = PCA(x)  Sw  (m1-m2) + C",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "g(x) = PCA(x)  Sw  (m1-m2) + C",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 416,
			"versionNonce": 1523284890,
			"isDeleted": false,
			"id": "SwzhKjfg",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1889.7476464565634,
			"y": 527.6928292338903,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 222.5604705810547,
			"height": 40,
			"seed": 1532140981,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "k*d      k^2     2k    +  1\n      Parameters ",
			"rawText": "k*d      k^2     2k    +  1\n      Parameters ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "k*d      k^2     2k    +  1\n      Parameters ",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 277,
			"versionNonce": 644817670,
			"isDeleted": false,
			"id": "PeGUVErV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1414.3425236839391,
			"y": 508.73459684158047,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 22.384048461914062,
			"height": 20,
			"seed": 272676603,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "V.S",
			"rawText": "V.S",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V.S",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 285,
			"versionNonce": 365754458,
			"isDeleted": false,
			"id": "WQDQXFPv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1750.020533376269,
			"y": 512.7495477071673,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 22.384048461914062,
			"height": 20,
			"seed": 1331588955,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "V.S",
			"rawText": "V.S",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V.S",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 335,
			"versionNonce": 870371910,
			"isDeleted": false,
			"id": "yERIPICG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1169.080883536161,
			"y": 579.9772637416495,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 206.67242431640625,
			"height": 20,
			"seed": 35841051,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "does it classify correctly?",
			"rawText": "does it classify correctly?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "does it classify correctly?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 411,
			"versionNonce": 352378138,
			"isDeleted": false,
			"id": "QY3wUYH2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1482.6894596291809,
			"y": 580.48847689084,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 206.67242431640625,
			"height": 20,
			"seed": 642608699,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "does it classify correctly?",
			"rawText": "does it classify correctly?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "does it classify correctly?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 351,
			"versionNonce": 1574607238,
			"isDeleted": false,
			"id": "ovClwnfJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1904.865803979496,
			"y": 575.3056134531203,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 141.87229919433594,
			"height": 20,
			"seed": 1003926901,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "can we simplify it?",
			"rawText": "can we simplify it?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "can we simplify it?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 363,
			"versionNonce": 1977231834,
			"isDeleted": false,
			"id": "eYq7lWJj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1531.440298200068,
			"y": 607.3504660498825,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 141.87229919433594,
			"height": 20,
			"seed": 1507327605,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "can we simplify it?",
			"rawText": "can we simplify it?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "can we simplify it?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 299,
			"versionNonce": 194607302,
			"isDeleted": false,
			"id": "VtEzzak3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1553.4112430320583,
			"y": 661.6599739966557,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 100.68843078613281,
			"height": 35,
			"seed": 2077134325,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Problem",
			"rawText": "Problem",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 424,
			"versionNonce": 795598490,
			"isDeleted": false,
			"id": "vc5yyPn0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1311.8954916106238,
			"y": 692.8650663618694,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 587.9993896484375,
			"height": 50,
			"seed": 480260187,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Some functions's complexity cannot be characterized by the\nnumber of their parameters",
			"rawText": "Some functions's complexity cannot be characterized by the\nnumber of their parameters",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Some functions's complexity cannot be characterized by the\nnumber of their parameters",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 265,
			"versionNonce": 884633606,
			"isDeleted": false,
			"id": "2PcbwvUQsStPnKs7o5nq0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1505.7256214750141,
			"y": 747.2872331280932,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 201,
			"height": 44,
			"seed": 1590775803,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "afb106f4fb3e9c29f93f217b00259098bb32c283",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 281,
			"versionNonce": 1583938394,
			"isDeleted": false,
			"id": "8XIHncQt",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1457.4345917284659,
			"y": 795.6944223495714,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 288.7796630859375,
			"height": 50,
			"seed": 843457659,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "by setting w very high we get\n",
			"rawText": "by setting w very high we get\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "by setting w very high we get\n",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 318,
			"versionNonce": 1429897030,
			"isDeleted": false,
			"id": "xT6VZ-nQtP9z5MKCyNewD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1230.1739739450923,
			"y": 828.4354608221754,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 740,
			"height": 236,
			"seed": 1357177595,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "810c641cc3af09fea5680a4b2d02023baeb506f0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 348,
			"versionNonce": 287604762,
			"isDeleted": false,
			"id": "Mw0hX9Bk",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1354.027343695207,
			"y": 1059.3877516899236,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 495.73944091796875,
			"height": 50,
			"seed": 1861937307,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Other models have wayy more parameters but are\na lot more rigid",
			"rawText": "Other models have wayy more parameters but are\na lot more rigid",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Other models have wayy more parameters but are\na lot more rigid",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 295,
			"versionNonce": 1635165830,
			"isDeleted": false,
			"id": "1aAsteq_etiqC47NdG-Hc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1448.5686517169543,
			"y": 1114.2900873681572,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 356,
			"height": 43,
			"seed": 1844537077,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bda3ab84934eef00750f29bfc9b370797b09688b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 319,
			"versionNonce": 328297690,
			"isDeleted": false,
			"id": "5rsqq2wS",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1746.4661872021427,
			"y": 1164.4409632474951,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 33.97996520996094,
			"height": 25,
			"seed": 1932895861,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2 k",
			"rawText": "2 k",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2 k",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 291,
			"versionNonce": 975955398,
			"isDeleted": false,
			"id": "ny8vTX3J",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1504.6574772687557,
			"y": 1483.5798862367844,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 213.5797576904297,
			"height": 25,
			"seed": 907098805,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Never exceeds slope 1",
			"rawText": "Never exceeds slope 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Never exceeds slope 1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 131,
			"versionNonce": 994230682,
			"isDeleted": false,
			"id": "K1wTHg29ooNODyIB73qmZ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 52.126696203820075,
			"y": 440.0114420394473,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 773,
			"height": 448,
			"seed": 2090268757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ed1e58ad69663e8decc50e3a1ba3dbae31ad68e0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 84,
			"versionNonce": 544685318,
			"isDeleted": false,
			"id": "jyVKcJaVLrsRFcQA7ULoW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -74.1216733623562,
			"y": 620.8433345270815,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 135.70347258980541,
			"height": 1.4135778394770568,
			"seed": 1788589461,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
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
					135.70347258980541,
					1.4135778394770568
				]
			]
		},
		{
			"type": "arrow",
			"version": 321,
			"versionNonce": 1244129527,
			"isDeleted": false,
			"id": "cSJLyikncSWdhgBRQhQBQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 141.3884830197573,
			"y": 1588.9029007419313,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 627.6285607278501,
			"height": 197.90225080982214,
			"seed": 1048379099,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709384558614,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JaLwsPtiuyr_vEvusV2Y1",
				"gap": 4.712992257509768,
				"focus": -0.15683004404140902
			},
			"endBinding": {
				"elementId": "A8Cp2OrQ",
				"focus": 0.08958045994810306,
				"gap": 14.948486642218768
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
					137.11840371230505
				],
				[
					306.7463911665394,
					87.64317933060511
				],
				[
					612.0792044936015,
					42.40868846733656
				],
				[
					627.6285607278501,
					197.90225080982214
				]
			]
		},
		{
			"type": "text",
			"version": 41,
			"versionNonce": 701869126,
			"isDeleted": false,
			"id": "A8Cp2OrQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 563.732905551602,
			"y": 1801.7536381939722,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 382.4815673828125,
			"height": 35,
			"seed": 198426037,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "cSJLyikncSWdhgBRQhQBQ",
					"type": "arrow"
				}
			],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Structural Risk Minimization",
			"rawText": "Structural Risk Minimization",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Structural Risk Minimization",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "ellipse",
			"version": 98,
			"versionNonce": 1222550298,
			"isDeleted": false,
			"id": "40561zKBEbqkrOkOt--aX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 497.5325967404287,
			"y": 1861.960050617574,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 466.3109231216411,
			"height": 392.21661409367744,
			"seed": 911845307,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 131,
			"versionNonce": 874787718,
			"isDeleted": false,
			"id": "GuysFFKmv6_KGbRZMT0de",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 522.4991573911557,
			"y": 1995.6519560375955,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 244.02799603774997,
			"height": 226.3097917049763,
			"seed": 2110116725,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 133,
			"versionNonce": 906964954,
			"isDeleted": false,
			"id": "MK1LBx7AHnrrn30hjicdA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 535.3851241786275,
			"y": 2091.491334019418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 125.6381761778515,
			"height": 109.53071769351163,
			"seed": 2038009205,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 49,
			"versionNonce": 1503646406,
			"isDeleted": false,
			"id": "ZCUayLvj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 709.0027514610633,
			"y": 1875.90001289324,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 55.188232421875,
			"height": 35,
			"seed": 1014214197,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Sn+1",
			"rawText": "Sn+1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sn+1",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 49,
			"versionNonce": 1863328922,
			"isDeleted": false,
			"id": "8dwgchIM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 627.9146226720256,
			"y": 2006.2478168362065,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 21.499984741210938,
			"height": 25,
			"seed": 496681589,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Sn",
			"rawText": "Sn",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sn",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 34,
			"versionNonce": 1692764678,
			"isDeleted": false,
			"id": "RfayJiXW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 584.1481743647213,
			"y": 2102.7665549584563,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.112075805664062,
			"height": 20,
			"seed": 1844815541,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Sn-1",
			"rawText": "Sn-1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sn-1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "ellipse",
			"version": 48,
			"versionNonce": 1838448986,
			"isDeleted": false,
			"id": "BA85_q3C5LU8P_uccfcK2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 604.4126826047784,
			"y": 2143.4672795457027,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1338256859,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1156733254,
			"isDeleted": false,
			"id": "kZiaulurKsuykst_Qw_vT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 624.4204401126287,
			"y": 2125.4461078896957,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1320644885,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 2096055834,
			"isDeleted": false,
			"id": "6ofEZldNRiZZg-8jiyppR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 542.1190262505495,
			"y": 2128.284087678043,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 2068253397,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 19087494,
			"isDeleted": false,
			"id": "788UfHe1Qff80BxYLm4ft",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 610.230541170891,
			"y": 2166.0292188630656,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1249211541,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 101937882,
			"isDeleted": false,
			"id": "2qPTn7zaNvkjUoUJs3UOG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 580.7155513720763,
			"y": 2129.9868755510515,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 721333845,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 758464454,
			"isDeleted": false,
			"id": "wCbSDT1MOu2dhf-JnILqe",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 560.2820968959738,
			"y": 2161.204653222874,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 393678837,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1536427930,
			"isDeleted": false,
			"id": "lDzIX_uZql3tl3TIxg00V",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 637.7589451178621,
			"y": 2149.8527340694845,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 873566677,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1564825350,
			"isDeleted": false,
			"id": "bdZo7I6vJRd6x1xs6H_L0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 588.0942988217801,
			"y": 2165.745420884231,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1393769365,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 94635098,
			"isDeleted": false,
			"id": "A6I1bGc9RjGbF-0Q-n3iA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 563.4038746631563,
			"y": 2134.5276432124083,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1885320533,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 433096262,
			"isDeleted": false,
			"id": "BF4xFltJJdcTf25im4TIu",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 561.1334908324782,
			"y": 2100.755683731072,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 330497813,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 236349722,
			"isDeleted": false,
			"id": "bQrY2tThaUkWMAcbu6wVr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 562.8362787054868,
			"y": 2059.8887747788667,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1414057845,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1404292486,
			"isDeleted": false,
			"id": "WIYSEEx7D4wtmRK8EZbkg",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 628.3936118163153,
			"y": 2077.7680474454573,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1878389685,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1281242586,
			"isDeleted": false,
			"id": "nfCGHQqZziLMbvXly7WCa",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 582.1345412662502,
			"y": 2076.0652595724478,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 354136635,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1479290054,
			"isDeleted": false,
			"id": "pyT7_ehdspcNFr0C957Eq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 600.865207869344,
			"y": 2056.4831990328503,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 653542933,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 831416986,
			"isDeleted": false,
			"id": "RIAWq1usQlYFZF-l--hQQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 657.9086016151298,
			"y": 2109.837219053784,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 191733717,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1154917382,
			"isDeleted": false,
			"id": "5iP2TDrNaKwHs-aLP6PEH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 644.853894588731,
			"y": 2070.673097974588,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1939913429,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 341444442,
			"isDeleted": false,
			"id": "vgSNlxx-Kzrs5DXLT1WWq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 648.8270662924176,
			"y": 2095.3635221332115,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 808377147,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 2075145030,
			"isDeleted": false,
			"id": "tkj1qACiyB8PPwBwRqWxW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 674.9364803452152,
			"y": 2085.998188831665,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 65401045,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085660,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 2098465818,
			"isDeleted": false,
			"id": "K8Ds_oYUU1uKChXvp6ABT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 667.2739349166766,
			"y": 2128.5678856568775,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1207903957,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 387308166,
			"isDeleted": false,
			"id": "V-fxVJbIn8sDcdhAsF5zA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 674.9364803452152,
			"y": 2107.2830372442713,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1559924885,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1907325146,
			"isDeleted": false,
			"id": "rPFTSCB7sVovuBXyYvPeq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 672.666096514537,
			"y": 2163.475037053553,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 386976341,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1573165510,
			"isDeleted": false,
			"id": "pJ3KXgNzuQT7b1jYNKwXa",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 650.8136521442609,
			"y": 2173.4079663127686,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 972936213,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1103056282,
			"isDeleted": false,
			"id": "RvYnTiqyKB44ru4-Ow7zM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 624.7042380914634,
			"y": 2161.4884512017097,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1316859349,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 920219910,
			"isDeleted": false,
			"id": "3ZD7bdf45xf0OoXJod6pT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 621.8662583031157,
			"y": 2106.715441286602,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1649170325,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1383500378,
			"isDeleted": false,
			"id": "PgQLhIrHSO38VjOF2jEMD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 576.4585816895549,
			"y": 2178.5163299317946,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1210437973,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 500260934,
			"isDeleted": false,
			"id": "tiWVro7Xd8A2NhVvzQlzU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 634.9209653295145,
			"y": 2197.2469965348882,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1472600853,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1789407002,
			"isDeleted": false,
			"id": "YrBBrNL6K7RyiUuis2OVL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 667.8415308743463,
			"y": 2182.2057036566466,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 770258133,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 378103686,
			"isDeleted": false,
			"id": "luQ-rVJQ5cdzgvmNLKqHm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 664.1521571494943,
			"y": 2149.8527340694845,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 1816862357,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 140,
			"versionNonce": 2126986202,
			"isDeleted": false,
			"id": "JDxHJq06Sz_EhhweQ6i-E",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 671.6132049888346,
			"y": 2269.908741722247,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 13.3385050052334,
			"height": 12.203313089894436,
			"seed": 2041043029,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 175,
			"versionNonce": 557745862,
			"isDeleted": false,
			"id": "I1s5Xst7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 696.006043052606,
			"y": 2266.1371561643077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 132.73983764648438,
			"height": 25,
			"seed": 230560027,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "= Datapoints",
			"rawText": "= Datapoints",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "= Datapoints",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 194,
			"versionNonce": 2095493274,
			"isDeleted": false,
			"id": "R7ogWtgO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 332.5233555279217,
			"y": 2331.885362166145,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 838.9591064453125,
			"height": 25,
			"seed": 1571854491,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "If there are two solutions to a problem, always choose one with the smallest region",
			"rawText": "If there are two solutions to a problem, always choose one with the smallest region",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If there are two solutions to a problem, always choose one with the smallest region",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 781041158,
			"isDeleted": false,
			"id": "4BhFv1InISi2QCcHCgpts",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 669.154370526112,
			"y": 2298.993414097414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 16.500692917928177,
			"height": 15.500650922901968,
			"seed": 245999963,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 295,
			"versionNonce": 414813530,
			"isDeleted": false,
			"id": "qmJkVJgB",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 697.762055847228,
			"y": 2294.493750057622,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 299.79962158203125,
			"height": 25,
			"seed": 2103969371,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "= Mean estimator per solution",
			"rawText": "= Mean estimator per solution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "= Mean estimator per solution",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "ellipse",
			"version": 162,
			"versionNonce": 326372678,
			"isDeleted": false,
			"id": "CC4AhIIpX_jpaL3dye000",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 591.7126725142332,
			"y": 2143.59937045425,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 10.001275266967696,
			"height": 9.0012332719416,
			"seed": 394197653,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 164,
			"versionNonce": 395498010,
			"isDeleted": false,
			"id": "6WbQGIQrZvelL6yu8-_ZY",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 626.3251306916156,
			"y": 2117.1331263959605,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 10.001275266967696,
			"height": 9.0012332719416,
			"seed": 1486493659,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 164,
			"versionNonce": 2102293638,
			"isDeleted": false,
			"id": "4bf2hXQX0eVBYWxzTXe9s",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 616.2882284186699,
			"y": 2113.2727793679046,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 10.001275266967696,
			"height": 9.0012332719416,
			"seed": 275050773,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 124,
			"versionNonce": 476413658,
			"isDeleted": false,
			"id": "pahb3go0R9riNfWgFCSoi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 567.3895534540144,
			"y": 2371.138948012854,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 476.50726790678914,
			"height": 281.25287095519906,
			"seed": 929954043,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6b04f622f52b2d997fe2a15d0024d9d4d737294e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 191,
			"versionNonce": 1708782534,
			"isDeleted": false,
			"id": "48fAXD6o",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 491.1508451625102,
			"y": 2660.7331624671197,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 642.5393676757812,
			"height": 50,
			"seed": 456387029,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Models with the lowest generalization error are preferred!\nthat we means we look at our test error not the training error!",
			"rawText": "Models with the lowest generalization error are preferred!\nthat we means we look at our test error not the training error!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Models with the lowest generalization error are preferred!\nthat we means we look at our test error not the training error!",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 388,
			"versionNonce": 1942262682,
			"isDeleted": false,
			"id": "KpcSgomAio0VDQUKHr6Mw",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1130.0484551980217,
			"y": 2513.4847914687844,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 750.3142679305524,
			"height": 802.8526849410073,
			"seed": 1174781205,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "GTatqIF7",
				"focus": 0.0526764155163531,
				"gap": 10.291844996395866
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
					198.66088932078083,
					-3.283651063153684
				],
				[
					231.49739995231494,
					-735.5378381463624
				],
				[
					689.5667232622145,
					-802.8526849410073
				],
				[
					750.3142679305524,
					-705.9849785779818
				]
			]
		},
		{
			"type": "text",
			"version": 135,
			"versionNonce": 120818438,
			"isDeleted": false,
			"id": "cEUj5hbk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1409.484812582589,
			"y": 1645.6283025611365,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 352.07958984375,
			"height": 25,
			"seed": 213542997,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How do we find out the test error?",
			"rawText": "How do we find out the test error?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we find out the test error?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 1608716378,
			"isDeleted": false,
			"id": "GTatqIF7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1773.4770726068737,
			"y": 1817.7916578871984,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 235.08901977539062,
			"height": 35,
			"seed": 292241723,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "KpcSgomAio0VDQUKHr6Mw",
					"type": "arrow"
				}
			],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Holdout Selection",
			"rawText": "Holdout Selection",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Holdout Selection",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 300,
			"versionNonce": 1339570758,
			"isDeleted": false,
			"id": "miqfw1kx",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1484.8590553174433,
			"y": 1854.3047754608297,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 800.5992431640625,
			"height": 75,
			"seed": 225335317,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Split data into two parts, one used to train the model and finding out the\ntraining accuracy, the other should only be used for testing the model on unseen\ndatapoints",
			"rawText": "Split data into two parts, one used to train the model and finding out the\ntraining accuracy, the other should only be used for testing the model on unseen\ndatapoints",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Split data into two parts, one used to train the model and finding out the\ntraining accuracy, the other should only be used for testing the model on unseen\ndatapoints",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 119,
			"versionNonce": 1687418138,
			"isDeleted": false,
			"id": "cxZZsx2DpUihY7OYgRK7U",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1648.193529038351,
			"y": 1935.2434720362414,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 523.0321300811617,
			"height": 243.71970075292884,
			"seed": 1227991515,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "27212147e0f7ff709a3c8f18c2dfaefe0b26c2d4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 450,
			"versionNonce": 1453654406,
			"isDeleted": false,
			"id": "tKCFNytd",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1524.2722715041687,
			"y": 2188.8007621517354,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 775.9990844726562,
			"height": 100,
			"seed": 1369447675,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "But how much data do I need to use?\nOn one hand you want to have as many tests as possible in order to ensure\nit is fit for the real world, on the other hand you do not want to take away\nfrom your training data because your model improves with larger N",
			"rawText": "But how much data do I need to use?\nOn one hand you want to have as many tests as possible in order to ensure\nit is fit for the real world, on the other hand you do not want to take away\nfrom your training data because your model improves with larger N",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But how much data do I need to use?\nOn one hand you want to have as many tests as possible in order to ensure\nit is fit for the real world, on the other hand you do not want to take away\nfrom your training data because your model improves with larger N",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 101,
			"versionNonce": 323633626,
			"isDeleted": false,
			"id": "7QEzFsnj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1741.1768276330336,
			"y": 2295.107354264736,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 339.29962158203125,
			"height": 25,
			"seed": 1838180245,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Very Dataset scarcity dependent ",
			"rawText": "Very Dataset scarcity dependent ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Very Dataset scarcity dependent ",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 280,
			"versionNonce": 1322705094,
			"isDeleted": false,
			"id": "vEBaCLbU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1536.4818102533936,
			"y": 2354.7405294232994,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 753.5391235351562,
			"height": 100,
			"seed": 934462587,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "RO2Ys-9jHjQ0_jslr8SH3",
					"type": "arrow"
				}
			],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Which datapoints do I use?\nsome datapoints may give false \"hope\" of high accuracy purely because they\nwere picked (randomly) to very similar training datapoints that the model\nrecognizes.",
			"rawText": "Which datapoints do I use?\nsome datapoints may give false \"hope\" of high accuracy purely because they\nwere picked (randomly) to very similar training datapoints that the model\nrecognizes.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which datapoints do I use?\nsome datapoints may give false \"hope\" of high accuracy purely because they\nwere picked (randomly) to very similar training datapoints that the model\nrecognizes.",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 69,
			"versionNonce": 1461253786,
			"isDeleted": false,
			"id": "RO2Ys-9jHjQ0_jslr8SH3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1910.9922497514679,
			"y": 2468.8262040332484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 1.1295611347520662,
			"height": 106.17874666668558,
			"seed": 1546834523,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "vEBaCLbU",
				"focus": 0.007794522277990718,
				"gap": 14.08567460994891
			},
			"endBinding": {
				"elementId": "ZJwMrEiW",
				"focus": -0.9389200803990059,
				"gap": 15.332100425535373
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
					1.1295611347520662,
					106.17874666668558
				]
			]
		},
		{
			"type": "text",
			"version": 42,
			"versionNonce": 2081085446,
			"isDeleted": false,
			"id": "ZJwMrEiW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1910.4020457852105,
			"y": 2590.3370511254693,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 73.47192993164062,
			"height": 35,
			"seed": 452495931,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "RO2Ys-9jHjQ0_jslr8SH3",
					"type": "arrow"
				}
			],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Idea!",
			"rawText": "Idea!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea!",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 163,
			"versionNonce": 1085477722,
			"isDeleted": false,
			"id": "4CbMQ-vERi8Qee4wbW3na",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1867.858908966663,
			"y": 2586.8521445770084,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 34.30686937101874,
			"height": 37.301913522456886,
			"seed": 65476245,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ac81ec161d252535f1e24b61f2a6d25499806fd6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 86,
			"versionNonce": 641591110,
			"isDeleted": false,
			"id": "D80mfd4x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1813.0696096663155,
			"y": 2634.871690841788,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 227.47299194335938,
			"height": 35,
			"seed": 918826037,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "K-Fold procedure",
			"rawText": "K-Fold procedure",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "K-Fold procedure",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 64,
			"versionNonce": 1382783002,
			"isDeleted": false,
			"id": "fzP6UXvw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1533.333560831573,
			"y": 2675.8515969410832,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 750.7991333007812,
			"height": 75,
			"seed": 364626357,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Retain more data for training, and make up for the lower amount of\nholdout data by repeating the model selection procedure over multiple data\nsplits",
			"rawText": "Retain more data for training, and make up for the lower amount of\nholdout data by repeating the model selection procedure over multiple data\nsplits",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Retain more data for training, and make up for the lower amount of\nholdout data by repeating the model selection procedure over multiple data\nsplits",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 98,
			"versionNonce": 231542406,
			"isDeleted": false,
			"id": "_zCeW3ppYXqaeIlWE7uky",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1616.8891343018179,
			"y": 2753.7756006152717,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 670.2770411596184,
			"height": 393.87413758864176,
			"seed": 1328159483,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ac52072e6e98681be4ffeac7cf3aa66bf841322d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 256,
			"versionNonce": 1278575834,
			"isDeleted": false,
			"id": "eZyocAvl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1446.169532474089,
			"y": 3140.3138942017945,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 983.2589111328125,
			"height": 50,
			"seed": 1794291131,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The model now generalizes well across any possible datapoint in the dataset if treated as unseen\nAssuming that the dataset is representative of the real world (Which is not always true)",
			"rawText": "The model now generalizes well across any possible datapoint in the dataset if treated as unseen\nAssuming that the dataset is representative of the real world (Which is not always true)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The model now generalizes well across any possible datapoint in the dataset if treated as unseen\nAssuming that the dataset is representative of the real world (Which is not always true)",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 296,
			"versionNonce": 1601523142,
			"isDeleted": false,
			"id": "KhsznTTW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1602.526043785725,
			"y": 3195.7756483921385,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 755.839111328125,
			"height": 50,
			"seed": 757686165,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "If k is too low      ->         Training data is heavily reduced\nif k is too high      ->         The procedure is very computationally costly",
			"rawText": "If k is too low      ->         Training data is heavily reduced\nif k is too high      ->         The procedure is very computationally costly",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If k is too low      ->         Training data is heavily reduced\nif k is too high      ->         The procedure is very computationally costly",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 130,
			"versionNonce": 2007226778,
			"isDeleted": false,
			"id": "YwY0or2kFG9IE9JuR7Dhr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -435.6480595026278,
			"y": 969.035402275911,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 821.6068702328339,
			"height": 0.26367044320204513,
			"seed": 485158901,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "EL1qa9dP",
				"focus": 0.11835281749642233,
				"gap": 11.61770144064917
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
					-821.6068702328339,
					-0.26367044320204513
				]
			]
		},
		{
			"type": "text",
			"version": 124,
			"versionNonce": 676570374,
			"isDeleted": false,
			"id": "YHvPyQJE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1004.224231954553,
			"y": 905.2200770061058,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"width": 350.599609375,
			"height": 50,
			"seed": 576846517,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Quick intermission onto a completely\ndifferent tangent",
			"rawText": "Quick intermission onto a completely\ndifferent tangent",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Quick intermission onto a completely\ndifferent tangent",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 172,
			"versionNonce": 1944688218,
			"isDeleted": false,
			"id": "EWZKxNDT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1802.1357086502326,
			"y": 944.4441915325035,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 378.05755615234375,
			"height": 35,
			"seed": 1290258267,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Bias-Variance decomposition",
			"rawText": "Bias-Variance decomposition",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bias-Variance decomposition",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "line",
			"version": 565,
			"versionNonce": 1239749702,
			"isDeleted": false,
			"id": "M16vSvG1z94_GnVa02xHO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1891.3886477168753,
			"y": 1037.851078198819,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 218.37199486494637,
			"height": 207.20920918494932,
			"seed": 472640533,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.372089259997665,
					187.6743342449542
				],
				[
					-209.9999056049487,
					207.20920918494932
				]
			]
		},
		{
			"type": "text",
			"version": 277,
			"versionNonce": 31046426,
			"isDeleted": false,
			"id": "nYJRHDf7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1983.2880192403104,
			"y": 1133.359008264206,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 75.29994201660156,
			"height": 25,
			"seed": 1127533749,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Unknown",
			"rawText": "Unknown",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Unknown",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 272,
			"versionNonce": 1845926790,
			"isDeleted": false,
			"id": "ogiOz80A",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1876.269004204913,
			"y": 1055.5984707677983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 54.19996643066406,
			"height": 25,
			"seed": 78219579,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Known",
			"rawText": "Known",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Known",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 770,
			"versionNonce": 223195671,
			"isDeleted": false,
			"id": "BCCX32ZbvmfwwBrGiAz9i",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1856.1894503812096,
			"y": 1115.3413068778175,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 178.31993181925873,
			"height": 66.4326252702715,
			"seed": 1862332821,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709384558615,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "RT_VdiMBUjXxpfZZVSe4O",
				"gap": 3.9467208437090093,
				"focus": -0.023367189008532012
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
					178.31993181925873,
					-66.4326252702715
				]
			]
		},
		{
			"type": "text",
			"version": 364,
			"versionNonce": 2062891718,
			"isDeleted": false,
			"id": "AfEviwMP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.942768244567222,
			"x": -1800.3801698259363,
			"y": 1034.522528243475,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 65.96815490722656,
			"height": 40,
			"seed": 496421915,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Build\ndataset",
			"rawText": "Build\ndataset",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Build\ndataset",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "ellipse",
			"version": 232,
			"versionNonce": 1176845466,
			"isDeleted": false,
			"id": "RT_VdiMBUjXxpfZZVSe4O",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1677.3769213879996,
			"y": 994.8781873916419,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 80.75307867307176,
			"height": 75.70601125600433,
			"seed": 1561199733,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "BCCX32ZbvmfwwBrGiAz9i",
					"type": "arrow"
				},
				{
					"id": "qwJxm-9jj-blb_taBb1Xs",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "1RS3yF5i"
				}
			],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 179,
			"versionNonce": 122548742,
			"isDeleted": false,
			"id": "1RS3yF5i",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1656.7949558894393,
			"y": 1012.9650760517911,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 39.48809814453125,
			"height": 40,
			"seed": 1014685435,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "data\nset",
			"rawText": "dataset",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "RT_VdiMBUjXxpfZZVSe4O",
			"originalText": "dataset",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 501,
			"versionNonce": 924669751,
			"isDeleted": false,
			"id": "qwJxm-9jj-blb_taBb1Xs",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1600.6937432700688,
			"y": 1051.3663763495601,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 109.55431268947086,
			"height": 106.4062002558652,
			"seed": 160516571,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709384558615,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "RT_VdiMBUjXxpfZZVSe4O",
				"gap": 1,
				"focus": -0.30507728787944477
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
					109.55431268947086,
					106.4062002558652
				]
			]
		},
		{
			"type": "diamond",
			"version": 306,
			"versionNonce": 1309524294,
			"isDeleted": false,
			"id": "6TqrO4rtaX2Ivr1YRWUN1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1523.3658172393016,
			"y": 1124.9143000122367,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 116.89963787961506,
			"height": 109.94884860028662,
			"seed": 883795003,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "XSwuMKiB"
				}
			],
			"updated": 1708894085661,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 197,
			"versionNonce": 866016794,
			"isDeleted": false,
			"id": "XSwuMKiB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1486.732948785023,
			"y": 1169.9015121623083,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 43.18408203125,
			"height": 20,
			"seed": 726784213,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085661,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Model",
			"rawText": "Model",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "6TqrO4rtaX2Ivr1YRWUN1",
			"originalText": "Model",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 249,
			"versionNonce": 579971206,
			"isDeleted": false,
			"id": "gOib5kXvNUEZH4Nqv3B0I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1292.0941012180078,
			"y": 1135.0245389639867,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 183.24808100047744,
			"height": 96.67915997611397,
			"seed": 2035214421,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "QbfjahqN"
				},
				{
					"id": "zfaOYL5hsNCgoqwkSuUcR",
					"type": "arrow"
				}
			],
			"updated": 1708894085662,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 242,
			"versionNonce": 1193249498,
			"isDeleted": false,
			"id": "QbfjahqN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1247.526182543941,
			"y": 1143.3641189520438,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 94.11224365234375,
			"height": 80,
			"seed": 486623765,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Parameters\nassumptions\ninitialization\nmodel class",
			"rawText": "Parameters assumptions\ninitialization\nmodel class",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "gOib5kXvNUEZH4Nqv3B0I",
			"originalText": "Parameters assumptions\ninitialization\nmodel class",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 416,
			"versionNonce": 234575959,
			"isDeleted": false,
			"id": "zfaOYL5hsNCgoqwkSuUcR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1294.6216609559451,
			"y": 1181.1525041813484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 115.00396807616153,
			"height": 0.6318899344845477,
			"seed": 1515258005,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709384558615,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "gOib5kXvNUEZH4Nqv3B0I",
				"gap": 2.5275597379371675,
				"focus": 0.03468865510378091
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
					-115.00396807616153,
					-0.6318899344845477
				]
			]
		},
		{
			"type": "arrow",
			"version": 423,
			"versionNonce": 1398611866,
			"isDeleted": false,
			"id": "94AKnsCBL5qzrXzansnnC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1495.8116496062325,
			"y": 1203.3244821667058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 109.81648631286635,
			"height": 100.53996950767305,
			"seed": 240390459,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085662,
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
					-109.81648631286635,
					100.53996950767305
				]
			]
		},
		{
			"type": "line",
			"version": 577,
			"versionNonce": 1949941510,
			"isDeleted": false,
			"id": "F1t4Miuyo_Zq-mvVYlAvY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1659.9644876278462,
			"y": 1288.377207929733,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 89.92133198653119,
			"height": 81.36783943171451,
			"seed": 286163963,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					29.608243458979814,
					-5.483008047959174
				],
				[
					54.17211951383706,
					15.7910631781225
				],
				[
					61.62901045906165,
					46.93454889053078
				],
				[
					42.10950180832651,
					68.86658108236759
				],
				[
					6.579609657550918,
					75.88483138375534
				],
				[
					0,
					58.9971665960411
				],
				[
					-28.29232152746954,
					46.276587924775754
				],
				[
					-21.49339154800009,
					24.34455573293883
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 198,
			"versionNonce": 1418337370,
			"isDeleted": false,
			"id": "D88MRJn9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1675.1872911598498,
			"y": 1320.184701336961,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 70.60816955566406,
			"height": 20,
			"seed": 1083348821,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Estimate",
			"rawText": "Estimate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Estimate",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 184,
			"versionNonce": 637005382,
			"isDeleted": false,
			"id": "5OigWUXe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1644.0509313193315,
			"y": 1076.9240649743374,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 12.480026245117188,
			"height": 20,
			"seed": 1559823605,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "D",
			"rawText": "D",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "D",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 488,
			"versionNonce": 1215922458,
			"isDeleted": false,
			"id": "HamXf90nUH6sh0a2m4Rez",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1674.4446108939555,
			"y": 1299.6377637034525,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 191.3028280670951,
			"height": 95.85663923165714,
			"seed": 1521897435,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085662,
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
					-191.3028280670951,
					-95.85663923165714
				]
			]
		},
		{
			"type": "text",
			"version": 271,
			"versionNonce": 917386630,
			"isDeleted": false,
			"id": "uycYLdEZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.5304673444888977,
			"x": -1795.8711270738663,
			"y": 1224.8887539777666,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 91.95217895507812,
			"height": 20,
			"seed": 353641755,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Is it close?",
			"rawText": "Is it close?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Is it close?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 169,
			"versionNonce": 2057194970,
			"isDeleted": false,
			"id": "7Y0JUhcQdUhV2u0LZPLdC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2067.986383252866,
			"y": 1127.8515130832113,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 22,
			"height": 35,
			"seed": 1857414683,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "64a9924df1d3bc96f52fd61da1cc81555291ba39",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 191,
			"versionNonce": 1067029702,
			"isDeleted": false,
			"id": "mlGHBmjDdtuyYIdyeprNY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1647.949082312808,
			"y": 1375.2364644459974,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 22,
			"height": 35,
			"seed": 1330926645,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "64a9924df1d3bc96f52fd61da1cc81555291ba39",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 241,
			"versionNonce": 1342931610,
			"isDeleted": false,
			"id": "o2Bg53E4nV3knTg8DeEZM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1642.0566158519723,
			"y": 1378.3878820038017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 15.560123562438093,
			"height": 12.19577252191084,
			"seed": 1538469653,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.21027194003318073,
					0
				],
				[
					0.4205438800659067,
					0
				],
				[
					0.6308158200986327,
					-0.21027194003295335
				],
				[
					1.0513597001645394,
					-0.4205438800659067
				],
				[
					1.6821755202636268,
					-1.0513597001647668
				],
				[
					2.3129913403622595,
					-1.4719035802306735
				],
				[
					2.733535220428166,
					-1.8924474602965802
				],
				[
					2.943807160461347,
					-2.312991340362487
				],
				[
					3.154079100494073,
					-2.5232632803954402
				],
				[
					3.3643510405272536,
					-2.7335352204283936
				],
				[
					3.3643510405272536,
					-2.943807160461347
				],
				[
					3.5746229805599796,
					-3.1540791004943003
				],
				[
					3.9951668606258863,
					-3.5746229805600933
				],
				[
					4.415710740691793,
					-3.7848949205930467
				],
				[
					4.8362546207577,
					-4.205438800658953
				],
				[
					5.2567985008236064,
					-4.62598268072486
				],
				[
					5.677342380889513,
					-5.046526560790767
				],
				[
					5.887614320922694,
					-5.25679850082372
				],
				[
					6.308158200988601,
					-5.4670704408566735
				],
				[
					6.518430141021327,
					-5.88761432092258
				],
				[
					6.728702081054507,
					-6.0978862609555335
				],
				[
					6.938974021087233,
					-6.308158200988487
				],
				[
					7.35951790115314,
					-6.72870208105428
				],
				[
					7.569789841185866,
					-6.72870208105428
				],
				[
					7.780061781219047,
					-6.938974021087233
				],
				[
					7.780061781219047,
					-7.149245961120187
				],
				[
					8.200605661284953,
					-7.569789841186093
				],
				[
					8.41087760131768,
					-7.569789841186093
				],
				[
					8.41087760131768,
					-7.780061781219047
				],
				[
					8.62114954135086,
					-7.780061781219047
				],
				[
					8.831421481383586,
					-7.990333721252
				],
				[
					9.041693421416767,
					-7.990333721252
				],
				[
					9.041693421416767,
					-8.200605661284953
				],
				[
					9.251965361449493,
					-8.200605661284953
				],
				[
					9.251965361449493,
					-7.990333721252
				],
				[
					9.462237301482674,
					-7.780061781219047
				],
				[
					9.462237301482674,
					-7.35951790115314
				],
				[
					9.462237301482674,
					-7.149245961120187
				],
				[
					9.6725092415154,
					-6.72870208105428
				],
				[
					9.88278118154858,
					-6.308158200988487
				],
				[
					10.093053121581306,
					-5.88761432092258
				],
				[
					10.093053121581306,
					-5.25679850082372
				],
				[
					10.303325061614487,
					-5.046526560790767
				],
				[
					10.513597001647213,
					-4.415710740691907
				],
				[
					10.723868941680394,
					-4.205438800658953
				],
				[
					10.93414088171312,
					-3.7848949205930467
				],
				[
					10.93414088171312,
					-3.5746229805600933
				],
				[
					11.1444128217463,
					-3.1540791004943003
				],
				[
					11.564956701812207,
					-2.7335352204283936
				],
				[
					11.775228641844933,
					-2.312991340362487
				],
				[
					11.775228641844933,
					-2.1027194003295335
				],
				[
					11.985500581878114,
					-1.6821755202636268
				],
				[
					12.19577252191084,
					-1.4719035802306735
				],
				[
					12.40604446194402,
					-0.8410877601318134
				],
				[
					12.616316401976746,
					-0.6308158200988601
				],
				[
					12.616316401976746,
					0
				],
				[
					12.826588342009927,
					0.21027194003295335
				],
				[
					13.036860282042653,
					0.8410877601316997
				],
				[
					13.036860282042653,
					1.2616316401976064
				],
				[
					13.247132222075834,
					1.4719035802305598
				],
				[
					13.45740416210856,
					1.8924474602964665
				],
				[
					13.45740416210856,
					2.10271940032942
				],
				[
					13.66767610214174,
					2.312991340362373
				],
				[
					13.877948042174467,
					2.5232632803953265
				],
				[
					14.088219982207647,
					2.5232632803953265
				],
				[
					14.088219982207647,
					2.9438071604612333
				],
				[
					14.298491922240373,
					2.9438071604612333
				],
				[
					14.5087638622731,
					3.3643510405270263
				],
				[
					14.71903580230628,
					3.3643510405270263
				],
				[
					14.929307742339006,
					3.784894920592933
				],
				[
					15.139579682372187,
					3.784894920592933
				],
				[
					15.139579682372187,
					3.9951668606258863
				],
				[
					15.349851622404913,
					3.9951668606258863
				],
				[
					15.560123562438093,
					3.9951668606258863
				],
				[
					15.560123562438093,
					3.9951668606258863
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 272,
			"versionNonce": 710347782,
			"isDeleted": false,
			"id": "M0QDMwk6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2064.5182893916253,
			"y": 1421.7612177380029,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 867.6392211914062,
			"height": 75,
			"seed": 1711933813,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "A good machine learning model is one that can produce an estimate close to the truth!\nCloseness is measured by an error function\ne.g",
			"rawText": "A good machine learning model is one that can produce an estimate close to the truth!\nCloseness is measured by an error function\ne.g",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A good machine learning model is one that can produce an estimate close to the truth!\nCloseness is measured by an error function\ne.g",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 226,
			"versionNonce": 326377306,
			"isDeleted": false,
			"id": "cn_fQtAqETWL4duuBErKd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1738.9557138305981,
			"y": 1501.9553482739316,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 219.15694606140835,
			"height": 66.32381262384726,
			"seed": 362191957,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "624iEDZDO7ssbIaeX7oy_",
					"type": "arrow"
				}
			],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "24697b204650f595ce1efcd22ce52feb35a84b2e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 269,
			"versionNonce": 618896198,
			"isDeleted": false,
			"id": "624iEDZDO7ssbIaeX7oy_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1625.3211518321978,
			"y": 1580.3487133104145,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 0,
			"height": 125.94873939202625,
			"seed": 1467354875,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "cn_fQtAqETWL4duuBErKd",
				"focus": -0.03701538135651646,
				"gap": 12.069552412635517
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
					0,
					125.94873939202625
				]
			]
		},
		{
			"type": "text",
			"version": 179,
			"versionNonce": 1093346330,
			"isDeleted": false,
			"id": "DlGGwPKh",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1773.4679637562872,
			"y": 1723.7215115888907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 298.93963623046875,
			"height": 25,
			"seed": 1435830229,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Assume we have a dataset D",
			"rawText": "Assume we have a dataset D",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assume we have a dataset D",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 245,
			"versionNonce": 362562182,
			"isDeleted": false,
			"id": "exwgnvPUSz-0JzkhsINEC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1714.6266590821947,
			"y": 1752.4624833166595,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 171.56746252670158,
			"height": 25.672503516769215,
			"seed": 1950490619,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "84eac6406ca07f23a07928242a8784e29e270ca9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 239,
			"versionNonce": 1394839770,
			"isDeleted": false,
			"id": "TwWA2jx5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1844.5592133164937,
			"y": 1789.4721268589135,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 499.259521484375,
			"height": 25,
			"seed": 1812179701,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "is the ground truth representing R for our problem",
			"rawText": "is the ground truth representing R for our problem",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "is the ground truth representing R for our problem",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 184,
			"versionNonce": 255721926,
			"isDeleted": false,
			"id": "SsImhYWHjoi8dKzTsnj42",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1873.084584092503,
			"y": 1783.045914693865,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 22,
			"height": 35,
			"seed": 1165928187,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "64a9924df1d3bc96f52fd61da1cc81555291ba39",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 159,
			"versionNonce": 217081242,
			"isDeleted": false,
			"id": "wy4LH3cf",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1506.434362528917,
			"y": 1777.706227284278,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 9.879989624023438,
			"height": 25,
			"seed": 1119845979,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "h",
			"rawText": "h",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "h",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 293,
			"versionNonce": 1155913990,
			"isDeleted": false,
			"id": "OexWL5DpvQztZwjRzvZBA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2061.6608335581886,
			"y": 1821.6901780111452,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 22,
			"height": 35,
			"seed": 308486523,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "64a9924df1d3bc96f52fd61da1cc81555291ba39",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 343,
			"versionNonce": 1204068954,
			"isDeleted": false,
			"id": "y0nIbdyGsCSNZ8LVHk-9c",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2055.768367097353,
			"y": 1824.8415955689497,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 15.560123562438093,
			"height": 12.19577252191084,
			"seed": 907491867,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.21027194003318073,
					0
				],
				[
					0.4205438800659067,
					0
				],
				[
					0.6308158200986327,
					-0.21027194003295335
				],
				[
					1.0513597001645394,
					-0.4205438800659067
				],
				[
					1.6821755202636268,
					-1.0513597001647668
				],
				[
					2.3129913403622595,
					-1.4719035802306735
				],
				[
					2.733535220428166,
					-1.8924474602965802
				],
				[
					2.943807160461347,
					-2.312991340362487
				],
				[
					3.154079100494073,
					-2.5232632803954402
				],
				[
					3.3643510405272536,
					-2.7335352204283936
				],
				[
					3.3643510405272536,
					-2.943807160461347
				],
				[
					3.5746229805599796,
					-3.1540791004943003
				],
				[
					3.9951668606258863,
					-3.5746229805600933
				],
				[
					4.415710740691793,
					-3.7848949205930467
				],
				[
					4.8362546207577,
					-4.205438800658953
				],
				[
					5.2567985008236064,
					-4.62598268072486
				],
				[
					5.677342380889513,
					-5.046526560790767
				],
				[
					5.887614320922694,
					-5.25679850082372
				],
				[
					6.308158200988601,
					-5.4670704408566735
				],
				[
					6.518430141021327,
					-5.88761432092258
				],
				[
					6.728702081054507,
					-6.0978862609555335
				],
				[
					6.938974021087233,
					-6.308158200988487
				],
				[
					7.35951790115314,
					-6.72870208105428
				],
				[
					7.569789841185866,
					-6.72870208105428
				],
				[
					7.780061781219047,
					-6.938974021087233
				],
				[
					7.780061781219047,
					-7.149245961120187
				],
				[
					8.200605661284953,
					-7.569789841186093
				],
				[
					8.41087760131768,
					-7.569789841186093
				],
				[
					8.41087760131768,
					-7.780061781219047
				],
				[
					8.62114954135086,
					-7.780061781219047
				],
				[
					8.831421481383586,
					-7.990333721252
				],
				[
					9.041693421416767,
					-7.990333721252
				],
				[
					9.041693421416767,
					-8.200605661284953
				],
				[
					9.251965361449493,
					-8.200605661284953
				],
				[
					9.251965361449493,
					-7.990333721252
				],
				[
					9.462237301482674,
					-7.780061781219047
				],
				[
					9.462237301482674,
					-7.35951790115314
				],
				[
					9.462237301482674,
					-7.149245961120187
				],
				[
					9.6725092415154,
					-6.72870208105428
				],
				[
					9.88278118154858,
					-6.308158200988487
				],
				[
					10.093053121581306,
					-5.88761432092258
				],
				[
					10.093053121581306,
					-5.25679850082372
				],
				[
					10.303325061614487,
					-5.046526560790767
				],
				[
					10.513597001647213,
					-4.415710740691907
				],
				[
					10.723868941680394,
					-4.205438800658953
				],
				[
					10.93414088171312,
					-3.7848949205930467
				],
				[
					10.93414088171312,
					-3.5746229805600933
				],
				[
					11.1444128217463,
					-3.1540791004943003
				],
				[
					11.564956701812207,
					-2.7335352204283936
				],
				[
					11.775228641844933,
					-2.312991340362487
				],
				[
					11.775228641844933,
					-2.1027194003295335
				],
				[
					11.985500581878114,
					-1.6821755202636268
				],
				[
					12.19577252191084,
					-1.4719035802306735
				],
				[
					12.40604446194402,
					-0.8410877601318134
				],
				[
					12.616316401976746,
					-0.6308158200988601
				],
				[
					12.616316401976746,
					0
				],
				[
					12.826588342009927,
					0.21027194003295335
				],
				[
					13.036860282042653,
					0.8410877601316997
				],
				[
					13.036860282042653,
					1.2616316401976064
				],
				[
					13.247132222075834,
					1.4719035802305598
				],
				[
					13.45740416210856,
					1.8924474602964665
				],
				[
					13.45740416210856,
					2.10271940032942
				],
				[
					13.66767610214174,
					2.312991340362373
				],
				[
					13.877948042174467,
					2.5232632803953265
				],
				[
					14.088219982207647,
					2.5232632803953265
				],
				[
					14.088219982207647,
					2.9438071604612333
				],
				[
					14.298491922240373,
					2.9438071604612333
				],
				[
					14.5087638622731,
					3.3643510405270263
				],
				[
					14.71903580230628,
					3.3643510405270263
				],
				[
					14.929307742339006,
					3.784894920592933
				],
				[
					15.139579682372187,
					3.784894920592933
				],
				[
					15.139579682372187,
					3.9951668606258863
				],
				[
					15.349851622404913,
					3.9951668606258863
				],
				[
					15.560123562438093,
					3.9951668606258863
				],
				[
					15.560123562438093,
					3.9951668606258863
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 347,
			"versionNonce": 2115029062,
			"isDeleted": false,
			"id": "FSI4hIAN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2030.0936356455752,
			"y": 1831.6901782800378,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 927.7190551757812,
			"height": 25,
			"seed": 395673013,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Is an estimator of the dataset D such that its trying to mimic the truth over m iterations",
			"rawText": "Is an estimator of the dataset D such that its trying to mimic the truth over m iterations",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Is an estimator of the dataset D such that its trying to mimic the truth over m iterations",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 224,
			"versionNonce": 1047742234,
			"isDeleted": false,
			"id": "zSSG-xoIl7jowpUyzCing",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1908.0710985271671,
			"y": 1866.7529017356349,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 627.8242653501591,
			"height": 123.25756853586294,
			"seed": 1325296597,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "24dfb7486b6be02043f2c0b3a762b2a829d74b37",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 227,
			"versionNonce": 177983366,
			"isDeleted": false,
			"id": "B7fqp4xxwS5bKOH0jL9VW",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1825.132888811264,
			"y": 1999.1380448680752,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 414.1768906024544,
			"height": 215.2629891946967,
			"seed": 618762133,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dfa7e74f81c4b7fca2fef6d8d90d9a89bf68e21a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 187,
			"versionNonce": 1500468186,
			"isDeleted": false,
			"id": "uCptoTC91AK9QEmXtwXXk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3340.6626520689506,
			"y": 1765.9396496020204,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"width": 877,
			"height": 356,
			"seed": 1990309467,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3247e6db80945068709dfefcf914bcecc9b48cf3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 364,
			"versionNonce": 918810310,
			"isDeleted": false,
			"id": "fehuktjl0RdAU96CFQ32H",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1979.5409534571377,
			"y": 1927.0110836266963,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 451.9471103234814,
			"height": 1.309991624126269,
			"seed": 2031943861,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Oz674auu",
				"focus": 1.415027151575285,
				"gap": 26.199832482520492
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
					-451.9471103234814,
					-1.309991624126269
				]
			]
		},
		{
			"type": "text",
			"version": 375,
			"versionNonce": 2060175514,
			"isDeleted": false,
			"id": "Oz674auu",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2392.1883150568374,
			"y": 1953.210916109217,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 416.1995544433594,
			"height": 125,
			"seed": 1584616699,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "fehuktjl0RdAU96CFQ32H",
					"type": "arrow"
				}
			],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can actually show that MSE can be\nrewritten using Bias and Variance, meaning\nits definition is dependent on it and thus\na good model needs to optimize the bias\nand variance to get good results!",
			"rawText": "We can actually show that MSE can be\nrewritten using Bias and Variance, meaning\nits definition is dependent on it and thus\na good model needs to optimize the bias\nand variance to get good results!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can actually show that MSE can be\nrewritten using Bias and Variance, meaning\nits definition is dependent on it and thus\na good model needs to optimize the bias\nand variance to get good results!",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "rectangle",
			"version": 205,
			"versionNonce": 1059464710,
			"isDeleted": false,
			"id": "VBRQKzsWVoTcfZ58u-ZYD",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3341.545841513853,
			"y": 1763.4789710883747,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 876.1309771649421,
			"height": 354.6578195563686,
			"seed": 1157774293,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "p6TJGDHjn46GaQXL-4-Vc",
					"type": "arrow"
				}
			],
			"updated": 1708894085662,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 367,
			"versionNonce": 1245422938,
			"isDeleted": false,
			"id": "Rjl8AG4_xkSYwYJHEwpw4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3320.989191765107,
			"y": 2139.6433035675223,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 835.0176773281447,
			"height": 416.6933917135566,
			"seed": 1815899477,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "110bccb4790eb4371efa8ecec27ff7d3f70df6c0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 630,
			"versionNonce": 1153398086,
			"isDeleted": false,
			"id": "p6TJGDHjn46GaQXL-4-Vc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3345.3780590827714,
			"y": 1918.1981634955773,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 570.671460963345,
			"height": 6.750129624122337,
			"seed": 204477909,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "VBRQKzsWVoTcfZ58u-ZYD",
				"focus": 0.1525208475587295,
				"gap": 3.8322175689186224
			},
			"endBinding": {
				"elementId": "fZl_cvW6iPYUU-Y17qL-y",
				"focus": 0.03415986011945444,
				"gap": 7.33119647333433
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
					-570.671460963345,
					6.750129624122337
				]
			]
		},
		{
			"type": "text",
			"version": 587,
			"versionNonce": 17951258,
			"isDeleted": false,
			"id": "afBK3Ja2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3847.20123512189,
			"y": 1951.5731358053638,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 476.49945068359375,
			"height": 150,
			"seed": 2009725115,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "And then we have to find out what the\nactual values of our Bias and variance\nare/should be, but this is obviously dependant\non what we are trying to estimate\nfor example Estimating the mean of a Gaussian\ndistribution",
			"rawText": "And then we have to find out what the\nactual values of our Bias and variance\nare/should be, but this is obviously dependant\non what we are trying to estimate\nfor example Estimating the mean of a Gaussian\ndistribution",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "And then we have to find out what the\nactual values of our Bias and variance\nare/should be, but this is obviously dependant\non what we are trying to estimate\nfor example Estimating the mean of a Gaussian\ndistribution",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 252,
			"versionNonce": 1089264774,
			"isDeleted": false,
			"id": "8UXjecLOVeqTacc7DGhxQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4933.371969762667,
			"y": 1745.905194830967,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 1007.3472489354052,
			"height": 363.02714345195847,
			"seed": 33353659,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "p6TJGDHjn46GaQXL-4-Vc",
					"type": "arrow"
				}
			],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "390f78561cb2f653451590a2384fd56d8eb1f973",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 164,
			"versionNonce": 910268122,
			"isDeleted": false,
			"id": "fZl_cvW6iPYUU-Y17qL-y",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4935.487221340392,
			"y": 1743.0808089614425,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1012.1065048209412,
			"height": 363.06867693715185,
			"seed": 933913211,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "p6TJGDHjn46GaQXL-4-Vc",
					"type": "arrow"
				},
				{
					"id": "r8BWpmIESqwNbctEQc152",
					"type": "arrow"
				}
			],
			"updated": 1708894085662,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 180,
			"versionNonce": 2037078982,
			"isDeleted": false,
			"id": "bM9rktwG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4618.67825999755,
			"y": 1698.8301411844532,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 360.8934326171875,
			"height": 35,
			"seed": 149922389,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Gaussian Mean estimation",
			"rawText": "Gaussian Mean estimation",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gaussian Mean estimation",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "arrow",
			"version": 273,
			"versionNonce": 710781850,
			"isDeleted": false,
			"id": "xmaPYzvtGhIbR2GThYBU4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2852.6234885699137,
			"y": 2543.7413109138924,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.11686857017775765,
			"height": 319.8537416466361,
			"seed": 1408194325,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "ey2dCVU_QE7oKKMfEOse3",
				"focus": -0.028921785230455656,
				"gap": 18.908103635978478
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
					0.11686857017775765,
					319.8537416466361
				]
			]
		},
		{
			"type": "text",
			"version": 425,
			"versionNonce": 1951920902,
			"isDeleted": false,
			"id": "SpGgv3ER",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2827.863476979193,
			"y": 2616.8479380505923,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 914.81982421875,
			"height": 175,
			"seed": 1092794299,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "James stein Estimator suggests\nthat instead of always prioritizing heading towards\nBias=0, we should consider cases where the bias\nis not 0 but very close to it, and see how much it\naffects our variance, in some cases this achieves better results!",
			"rawText": "James stein Estimator suggests\nthat instead of always prioritizing heading towards\nBias=0, we should consider cases where the bias\nis not 0 but very close to it, and see how much it\naffects our variance, in some cases this achieves better results!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "James stein Estimator suggests\nthat instead of always prioritizing heading towards\nBias=0, we should consider cases where the bias\nis not 0 but very close to it, and see how much it\naffects our variance, in some cases this achieves better results!",
			"lineHeight": 1.25,
			"baseline": 165
		},
		{
			"type": "image",
			"version": 236,
			"versionNonce": 328804442,
			"isDeleted": false,
			"id": "ey2dCVU_QE7oKKMfEOse3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3279.7438619559302,
			"y": 2882.503156196507,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 880,
			"height": 161,
			"seed": 345777691,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xmaPYzvtGhIbR2GThYBU4",
					"type": "arrow"
				}
			],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bb3df2b0d8381749fcbd467ce2b1651b84bfb2a4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 237,
			"versionNonce": 1815061062,
			"isDeleted": false,
			"id": "PWeNkGVtZjOPw4Fw1AUlQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3185.1024452839815,
			"y": 3050.187257504693,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 659,
			"height": 194,
			"seed": 2055601237,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "579caa87f001c3fb6392b9fba54e631702eb11d2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 231,
			"versionNonce": 1774652698,
			"isDeleted": false,
			"id": "fnaEmqwicnoowTeoDGzc7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2702.8596451708177,
			"y": 3247.736858220791,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 178.00000000000003,
			"height": 142,
			"seed": 443141621,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4d7e87dc0271b0dadbb715a5a15c3a1b8378c705",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 501,
			"versionNonce": 1137666438,
			"isDeleted": false,
			"id": "Ugx8V72D",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4667.920463265558,
			"y": 2307.9574515969052,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 45.034032970150115,
			"height": 29.139668392450076,
			"seed": 19716,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7b19ec2b8d215f664336b4de89eed1074180ecba",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 844782042,
			"isDeleted": false,
			"id": "dpyRnGNqpHXlJNw5y7RP3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4467.098480315738,
			"y": 2353.9640007971243,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1628610778,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 2054441158,
			"isDeleted": false,
			"id": "8uLDs8YuJEr6j6WLrF6rl",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4449.501567513989,
			"y": 2323.3606741853864,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 133977882,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 1281756826,
			"isDeleted": false,
			"id": "1hPAmQ4BffVvYl2HE1kJZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4474.749311968672,
			"y": 2337.897254325962,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 2107553114,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 532365318,
			"isDeleted": false,
			"id": "MGS8naSLBFSvzoRMowl9c",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4448.736484348696,
			"y": 2347.8433354747767,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 500874138,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 251,
			"versionNonce": 1016933210,
			"isDeleted": false,
			"id": "_dPTXK_VJLkjrKmx50ceu",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4497.701806927476,
			"y": 2360.084666119472,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 1680959962,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 1201753926,
			"isDeleted": false,
			"id": "oj_XQ_WVp0WLW080vWSw5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4491.581141605128,
			"y": 2319.5352583589192,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 2085137626,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 2035462170,
			"isDeleted": false,
			"id": "nLo1KFIxmYojFjkVfXNlM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4480.104894125727,
			"y": 2370.79583043358,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1574822682,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 2122544774,
			"isDeleted": false,
			"id": "Vsvzh3ey2eKmSpRSloit4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4446.441234852815,
			"y": 2305.7637613836373,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 870039898,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 913939674,
			"isDeleted": false,
			"id": "BnCqVR3IlomUk8_ZKuZwi",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4447.2063180181085,
			"y": 2384.5673274088626,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 2015578010,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 1025422790,
			"isDeleted": false,
			"id": "kFDGzOhE1utjlxKNmuDw-",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4438.025320034588,
			"y": 2328.716256342441,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 70612442,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 832893338,
			"isDeleted": false,
			"id": "f0pMS3I7KHgMua_z2oZol",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4430.3744883816535,
			"y": 2362.379915615352,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 892554266,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 299,
			"versionNonce": 1552944390,
			"isDeleted": false,
			"id": "wpZQPGCQd3gkX2tCA0a0z",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4408.952159753435,
			"y": 2335.2195132474353,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 231869894,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 299,
			"versionNonce": 2114432602,
			"isDeleted": false,
			"id": "qtF5XEuCSaU_ok3KQxF57",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4391.355246951687,
			"y": 2304.616186635698,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1830315270,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 299,
			"versionNonce": 173308998,
			"isDeleted": false,
			"id": "YlqkElGxlnOlykcDIGyw4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4416.602991406371,
			"y": 2319.152766776273,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 403821638,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 299,
			"versionNonce": 1349833498,
			"isDeleted": false,
			"id": "TT6AjeJtdENq07MUn4LC0",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4390.5901637863935,
			"y": 2329.098847925088,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1486576518,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 300,
			"versionNonce": 1011417990,
			"isDeleted": false,
			"id": "1jddhSnnpNY64VevfTQ2N",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4439.555486365174,
			"y": 2341.3401785697824,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 888273606,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085662,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 299,
			"versionNonce": 1264541658,
			"isDeleted": false,
			"id": "kK_8QPSl_hO1j3T05yLLg",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4433.434821042827,
			"y": 2300.79077080923,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1672655366,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 299,
			"versionNonce": 615162566,
			"isDeleted": false,
			"id": "TjnM9vyRLd9TjSiA_DZjw",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4421.958573563425,
			"y": 2352.0513428838913,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1071284550,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 299,
			"versionNonce": 1255822490,
			"isDeleted": false,
			"id": "tdb2-XQBsk_pv_5M4K7pd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4388.294914290513,
			"y": 2287.0192738339483,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1019635846,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 299,
			"versionNonce": 638999046,
			"isDeleted": false,
			"id": "05hrGHSZnufMZ7EqBJ9MO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4389.059997455806,
			"y": 2365.8228398591727,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1513318342,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 299,
			"versionNonce": 815313242,
			"isDeleted": false,
			"id": "yg2vqZBnSezFS3Vwgag0Z",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4379.878999472285,
			"y": 2309.9717687927514,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 406748934,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 299,
			"versionNonce": 1200171334,
			"isDeleted": false,
			"id": "YM_6rldnZWSGHiGacNkv7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4372.228167819352,
			"y": 2343.6354280656633,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1801760326,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 804091418,
			"isDeleted": false,
			"id": "sCAPQEAUL7BVuV2ZtglZl",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4491.581141605129,
			"y": 2293.1399391562964,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 549077830,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 677384326,
			"isDeleted": false,
			"id": "bnLlNuhZkUZwzd5IqO9nN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4473.98422880338,
			"y": 2262.536612544558,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 811461254,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 432775898,
			"isDeleted": false,
			"id": "p07wxU2FUcwXly67dSzA0",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4499.231973258062,
			"y": 2277.073192685134,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 864725446,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 1951928262,
			"isDeleted": false,
			"id": "FiVzZnaKBzATgXhmtuVSc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4473.219145638086,
			"y": 2287.0192738339483,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 157122822,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 267,
			"versionNonce": 684079002,
			"isDeleted": false,
			"id": "3WiT3aSN3zuBfSemTQODb",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4522.184468216867,
			"y": 2299.2606044786435,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 626225222,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 1468933894,
			"isDeleted": false,
			"id": "LoyBcvOqmpxRtorFTjMOD",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4516.063802894518,
			"y": 2258.711196718091,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 55146374,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 1292907610,
			"isDeleted": false,
			"id": "ONGvUeRaD01RncwkWfNhs",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4504.587555415117,
			"y": 2309.9717687927514,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 461149894,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 1920947782,
			"isDeleted": false,
			"id": "M-B8jj0nXNF9jxud6CPJO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4470.923896142205,
			"y": 2244.9396997428094,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1451871750,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 2021431578,
			"isDeleted": false,
			"id": "6QaWl-LwYQxtONL1qpu5r",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4471.688979307499,
			"y": 2323.743265768034,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 23993670,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 1309187462,
			"isDeleted": false,
			"id": "81PtANeVOx3SR3T6HMN1S",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4462.507981323979,
			"y": 2267.8921947016124,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1099334790,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 1786668506,
			"isDeleted": false,
			"id": "s3QG4Ok6zYzOxOwctQkb2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4454.857149671043,
			"y": 2301.5558539745234,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 143655878,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 333,
			"versionNonce": 1332149446,
			"isDeleted": false,
			"id": "EvKhDzfblNLyhFp-HDng5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4428.844322051065,
			"y": 2277.073192685133,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1573384454,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 333,
			"versionNonce": 2083035802,
			"isDeleted": false,
			"id": "jZT59AHrqwhUZ1zQ5chX2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4411.247409249318,
			"y": 2246.4698660733957,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1659887686,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 333,
			"versionNonce": 741831686,
			"isDeleted": false,
			"id": "7BBYdkQvTbNxMXcXWddAA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4436.4951537040015,
			"y": 2261.006446213971,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 869787526,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 333,
			"versionNonce": 1814968154,
			"isDeleted": false,
			"id": "wqvY2e3atvCY0TZt1hQQi",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4410.482326084024,
			"y": 2270.952527362786,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 280823494,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 334,
			"versionNonce": 1584857926,
			"isDeleted": false,
			"id": "IGXWOtp35RmKEgITYfa0b",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4459.447648662805,
			"y": 2283.193858007481,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 708591110,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 333,
			"versionNonce": 719469594,
			"isDeleted": false,
			"id": "D-b5W19DChlI9M1GV3yY1",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4453.326983340457,
			"y": 2242.6444502469285,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 357731654,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 333,
			"versionNonce": 411216518,
			"isDeleted": false,
			"id": "1roMA9P0LcxUTjA58d-tJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4441.850735861055,
			"y": 2293.905022321589,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1063056518,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 333,
			"versionNonce": 641181914,
			"isDeleted": false,
			"id": "Tdy7cUiiLK0hO-oH52_mx",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4408.187076588143,
			"y": 2228.872953271646,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1645769670,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 333,
			"versionNonce": 957835718,
			"isDeleted": false,
			"id": "b9y_Po72WzkbtoeEnTQif",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4408.952159753437,
			"y": 2307.6765192968705,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 2007108358,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 333,
			"versionNonce": 365002138,
			"isDeleted": false,
			"id": "E_X51Na6JKs5ggqkEb0Aw",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4399.771161769915,
			"y": 2251.82544823045,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 779532870,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 333,
			"versionNonce": 1062355206,
			"isDeleted": false,
			"id": "hkPcoZddC_qdg1roBTuTp",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4392.120330116983,
			"y": 2285.489107503361,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1567850886,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 1186118234,
			"isDeleted": false,
			"id": "x9P9L8GRHIPORgbYNxrvi",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4356.161421348188,
			"y": 2263.3016957098525,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1897747782,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 1051734086,
			"isDeleted": false,
			"id": "pL6eV9r7ia1U0KuYJaZQw",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4338.56450854644,
			"y": 2232.698369098114,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1720630406,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 1742626586,
			"isDeleted": false,
			"id": "Cl7tfTML39h7ZRyfSFcpV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4363.812253001124,
			"y": 2247.23494923869,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1339112390,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 1393440646,
			"isDeleted": false,
			"id": "HuBjHF1zfBAgosAp8lJA6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4337.799425381147,
			"y": 2257.1810303875045,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1124193030,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 294,
			"versionNonce": 1438084058,
			"isDeleted": false,
			"id": "9I-ls_RRicjwdqD8W-D7B",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4386.764747959927,
			"y": 2269.4223610321997,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 178094662,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 346642118,
			"isDeleted": false,
			"id": "GISulfBbne8VvE6CEX3LL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4380.64408263758,
			"y": 2228.872953271647,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 427903366,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 1716576410,
			"isDeleted": false,
			"id": "UFyRbPxDlTP_GZcrrAy7m",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4369.167835158178,
			"y": 2280.1335253463076,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 2129275078,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 203329030,
			"isDeleted": false,
			"id": "AhoyAwWwCHzxJC27xzYMx",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4335.504175885266,
			"y": 2215.1014562963646,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1517625350,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 895335770,
			"isDeleted": false,
			"id": "jfBYA9nwHOP-xWFmI2513",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4336.269259050559,
			"y": 2293.90502232159,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1344220998,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 644537670,
			"isDeleted": false,
			"id": "2BS7OZnkIrK9yaekJAWat",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4327.088261067038,
			"y": 2238.0539512551686,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 2084918918,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 1882259994,
			"isDeleted": false,
			"id": "mAIxBGjtSJ8GBnPqf92qc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4319.437429414105,
			"y": 2271.7176105280796,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1738839494,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 295,
			"versionNonce": 686507142,
			"isDeleted": false,
			"id": "_eTqk4IyjrpJxcrV-KtMf",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4449.5015675139875,
			"y": 2205.155375147549,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 2146006086,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 295,
			"versionNonce": 566079194,
			"isDeleted": false,
			"id": "kEEAqrF9O7Y1Q2eysI-p-",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4431.90465471224,
			"y": 2174.5520485358115,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 612301702,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 295,
			"versionNonce": 626836422,
			"isDeleted": false,
			"id": "21LmkXBWX9k27v_BmVFB1",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4457.152399166924,
			"y": 2189.0886286763866,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 56728262,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 295,
			"versionNonce": 2123809690,
			"isDeleted": false,
			"id": "O9p32tNII_X_21qNy-Ff4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4431.139571546946,
			"y": 2199.034709825202,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 53367302,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 296,
			"versionNonce": 1843157766,
			"isDeleted": false,
			"id": "OAvk8YM8Y5_lYq4bhxt8W",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4480.104894125727,
			"y": 2211.276040469897,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 786571590,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 295,
			"versionNonce": 820985946,
			"isDeleted": false,
			"id": "TM-EZtCsv-wD819znIkrL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4473.98422880338,
			"y": 2170.7266327093444,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 702154886,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 295,
			"versionNonce": 149359174,
			"isDeleted": false,
			"id": "FTkv3gxoxotnXlG_p9Fny",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4462.507981323977,
			"y": 2221.9872047840054,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 601032646,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 295,
			"versionNonce": 614081818,
			"isDeleted": false,
			"id": "6tt693jzVHyJJ7xVNeGCS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4428.844322051065,
			"y": 2156.955135734062,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1290411782,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 295,
			"versionNonce": 626643334,
			"isDeleted": false,
			"id": "wune3plRve3txzYaX-l6s",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4429.609405216359,
			"y": 2235.7587017592873,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1234980422,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 295,
			"versionNonce": 1393193434,
			"isDeleted": false,
			"id": "SzOY7rDyuGo4fK9_ZwgRT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4420.428407232837,
			"y": 2179.907630692866,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 650548614,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 295,
			"versionNonce": 242331846,
			"isDeleted": false,
			"id": "DUFUG_2h3kDE84crt1lVU",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4412.777575579905,
			"y": 2213.571289965777,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1302721734,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 253,
			"versionNonce": 257107610,
			"isDeleted": false,
			"id": "pNlkxEXht_rIaHfAT2iUr",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4372.228167819351,
			"y": 2182.9679633540395,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1468030106,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 253,
			"versionNonce": 533440518,
			"isDeleted": false,
			"id": "ALrwojHz7LT72eIjCJFPd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4354.631255017602,
			"y": 2152.364636742302,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1262336346,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 253,
			"versionNonce": 1378304858,
			"isDeleted": false,
			"id": "6lDmVm-ARtihounmGc-K4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4379.878999472284,
			"y": 2166.901216882877,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1085373978,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 253,
			"versionNonce": 962901830,
			"isDeleted": false,
			"id": "LCZ8QceOp6k8nGV_uOCKX",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4353.866171852308,
			"y": 2176.8472980316924,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 80653018,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 254,
			"versionNonce": 98158618,
			"isDeleted": false,
			"id": "OFFA-3S3CGMZotildt_6I",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4402.831494431089,
			"y": 2189.0886286763866,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 1311260570,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 253,
			"versionNonce": 865721990,
			"isDeleted": false,
			"id": "edq-1w339gEKXlHzxOYb2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4396.71082910874,
			"y": 2148.539220915834,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 150027354,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 253,
			"versionNonce": 1381872858,
			"isDeleted": false,
			"id": "7PT0qsXVN1wMLhKERV7Jz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4385.234581629339,
			"y": 2199.7997929904955,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 586981658,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 253,
			"versionNonce": 1395137990,
			"isDeleted": false,
			"id": "rX4FJslvLDdvdpNQMWjKr",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4351.570922356427,
			"y": 2134.7677239405525,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1472032218,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 253,
			"versionNonce": 1766197658,
			"isDeleted": false,
			"id": "WtbiEm4A0o4M_byGqk7Fl",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4352.336005521721,
			"y": 2213.571289965777,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 2085003930,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 253,
			"versionNonce": 1026323718,
			"isDeleted": false,
			"id": "CObSrszBv6ytFJn8HY7O8",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4343.155007538201,
			"y": 2157.7202188993556,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1263222618,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 253,
			"versionNonce": 1371915866,
			"isDeleted": false,
			"id": "HV9nauVCScUkxTKfnPlZM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4335.504175885265,
			"y": 2191.3838781722675,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 824067098,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 278,
			"versionNonce": 1797514310,
			"isDeleted": false,
			"id": "otQCBHCY2rt11_2NQzTOG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4531.365466200388,
			"y": 2218.9268721228314,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1520559002,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 278,
			"versionNonce": 883944218,
			"isDeleted": false,
			"id": "yhJfF5LkylL9xMnkgQzVy",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4513.768553398639,
			"y": 2188.323545511093,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 513171546,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 278,
			"versionNonce": 518744966,
			"isDeleted": false,
			"id": "VBimpkPKNLXYaBrCALf1X",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4539.016297853321,
			"y": 2202.860125651669,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 274547994,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 278,
			"versionNonce": 678918106,
			"isDeleted": false,
			"id": "mSHHYQK23T_JM5bY4S1c6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4513.003470233345,
			"y": 2212.8062068004833,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 426349018,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 279,
			"versionNonce": 1455426246,
			"isDeleted": false,
			"id": "qwdSoLbM52vEpJ-NBY_Le",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4561.968792812126,
			"y": 2225.0475374451803,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 2093893274,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 278,
			"versionNonce": 2100259994,
			"isDeleted": false,
			"id": "nNzMzD97_JiTY8t1FjXHH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4555.848127489777,
			"y": 2184.4981296846267,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 591291226,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 278,
			"versionNonce": 1094631942,
			"isDeleted": false,
			"id": "JmjrG2TBv1qiiPINzc62G",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4544.371880010376,
			"y": 2235.7587017592873,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1728899098,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 278,
			"versionNonce": 143313242,
			"isDeleted": false,
			"id": "M1HcoAH1IFAsSy5aPjuZs",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4510.708220737464,
			"y": 2170.7266327093444,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1613550810,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 278,
			"versionNonce": 828674374,
			"isDeleted": false,
			"id": "04Cbl4U3WIoadqbCA9u0a",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4511.473303902758,
			"y": 2249.5301987345697,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 808528282,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 278,
			"versionNonce": 1910279706,
			"isDeleted": false,
			"id": "KWA1qA1MbgFyvftfpaW7J",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4502.292305919238,
			"y": 2193.6791276681483,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1313662554,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 278,
			"versionNonce": 311326854,
			"isDeleted": false,
			"id": "I9bzQm4PYTOd2UkLGU8Qk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4494.641474266302,
			"y": 2227.3427869410593,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1397951258,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 2115484378,
			"isDeleted": false,
			"id": "_sPTVEbwvyF5tKEfexGnA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4553.552877993897,
			"y": 2312.267018288632,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 863356122,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 1551464390,
			"isDeleted": false,
			"id": "q7WgOqEyexqd0jboDjP-Y",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4535.955965192147,
			"y": 2281.6636916768944,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 215751066,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085663,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 1540312986,
			"isDeleted": false,
			"id": "ujyhRase7LCDK7oaUIvOc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4561.203709646829,
			"y": 2296.2002718174695,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 941217370,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 121802502,
			"isDeleted": false,
			"id": "NhIW0V3ZFL2fcvn5SfUb2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4535.190882026854,
			"y": 2306.1463529662847,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1442970394,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 306,
			"versionNonce": 1865829466,
			"isDeleted": false,
			"id": "BCebuwzlEle9-fAW2VmPN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4584.156204605634,
			"y": 2318.387683610979,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 1963427802,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 2137439814,
			"isDeleted": false,
			"id": "010-BNfGxYv28TWdW_T_N",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4578.035539283285,
			"y": 2277.8382758504263,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1564310682,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 505393434,
			"isDeleted": false,
			"id": "JoTYSNDtjWNMMAQ7IeUNZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4566.559291803885,
			"y": 2329.0988479250877,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1549195610,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 432211334,
			"isDeleted": false,
			"id": "QBsRgyHAT6MsOzdyV4tX_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4532.895632530973,
			"y": 2264.066778875145,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 296132122,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 469663194,
			"isDeleted": false,
			"id": "Q0roDRGGy5lc8qbQltSYq",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4533.660715696266,
			"y": 2342.870344900369,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 975162074,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 127165638,
			"isDeleted": false,
			"id": "mnFCAS7KDAhRlEh8LXoiB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4524.479717712747,
			"y": 2287.019273833948,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 2085969818,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 305,
			"versionNonce": 904245914,
			"isDeleted": false,
			"id": "v1xTlgE-fglNtzR7tujqE",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4516.82888605981,
			"y": 2320.6829331068598,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 880434266,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 290,
			"versionNonce": 1249369094,
			"isDeleted": false,
			"id": "JbthKgvJck85dQpO64CSY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4333.520117636688,
			"y": 2353.22908581294,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 568621510,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 290,
			"versionNonce": 512249690,
			"isDeleted": false,
			"id": "rhTglYs-_M8dn094em0zK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4315.923204834939,
			"y": 2322.6257592012016,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 738021638,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 290,
			"versionNonce": 678062918,
			"isDeleted": false,
			"id": "QNS2fMUo4Z36eNvhdukbJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4341.170949289621,
			"y": 2337.1623393417776,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 58277958,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 290,
			"versionNonce": 976835610,
			"isDeleted": false,
			"id": "9jk4NJr9H6ilStvzxwPxQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4315.158121669645,
			"y": 2347.108420490592,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1010124678,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 291,
			"versionNonce": 533271174,
			"isDeleted": false,
			"id": "iNadQcUfw8gVXl6rtTSyZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4364.123444248426,
			"y": 2359.349751135288,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 1718511302,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 290,
			"versionNonce": 1793835226,
			"isDeleted": false,
			"id": "J5mcK0PMXVxer2IgQzWeZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4358.002778926077,
			"y": 2318.8003433747353,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 46243334,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 290,
			"versionNonce": 1532023238,
			"isDeleted": false,
			"id": "qf6HcSg0DD9D9yTOmew1e",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4346.526531446676,
			"y": 2370.060915449395,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1982590278,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 290,
			"versionNonce": 1546818970,
			"isDeleted": false,
			"id": "FVhD7mSwtN854kyNYoE-m",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4312.862872173764,
			"y": 2305.028846399453,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 2114606214,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 290,
			"versionNonce": 639543558,
			"isDeleted": false,
			"id": "V4FY61T7T1Yk_qiec3DPX",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4313.627955339058,
			"y": 2383.8324124246783,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 605672390,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 290,
			"versionNonce": 1329648218,
			"isDeleted": false,
			"id": "AnDboqviARXK8odCM-5br",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4304.446957355538,
			"y": 2327.981341358257,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 846686982,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 290,
			"versionNonce": 1605343302,
			"isDeleted": false,
			"id": "B6DJPjqnfg55EHtk7vv6Z",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4296.796125702602,
			"y": 2361.645000631167,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 664803910,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 302,
			"versionNonce": 1726576410,
			"isDeleted": false,
			"id": "qkIod7v5KXYFLsYESgV57",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4391.627052773492,
			"y": 2417.253231240205,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 980267482,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 302,
			"versionNonce": 1876991878,
			"isDeleted": false,
			"id": "HfZfEdwLCRzUOfwuf7LWH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4374.030139971743,
			"y": 2386.6499046284675,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 676226714,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 302,
			"versionNonce": 1939833818,
			"isDeleted": false,
			"id": "v0uo2NAYY0ftT4mg4DIsz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4399.277884426425,
			"y": 2401.1864847690426,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 700089178,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 302,
			"versionNonce": 988724934,
			"isDeleted": false,
			"id": "0AQbHoK_qxpGl246V7xYk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4373.265056806449,
			"y": 2411.132565917858,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 151324698,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 303,
			"versionNonce": 1064695962,
			"isDeleted": false,
			"id": "cHzbNrtpdiQ2CSPSbgUJA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4422.23037938523,
			"y": 2423.373896562552,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 1310782682,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 302,
			"versionNonce": 360117766,
			"isDeleted": false,
			"id": "pzBCNTNhMooNC_RCBS9V3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4416.109714062881,
			"y": 2382.8244888019995,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 178342298,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 302,
			"versionNonce": 1512035674,
			"isDeleted": false,
			"id": "SJUzcLABHsQi11C06lW9E",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4404.63346658348,
			"y": 2434.085060876661,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 632882778,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 302,
			"versionNonce": 947275078,
			"isDeleted": false,
			"id": "qca5YrqhtLLx6qVED7Qzg",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4370.969807310568,
			"y": 2369.052991826717,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 674966298,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 302,
			"versionNonce": 1693456922,
			"isDeleted": false,
			"id": "WaOUYZakz1eP_rmvD2yH-",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4371.734890475862,
			"y": 2447.8565578519424,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 144357338,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 302,
			"versionNonce": 894020742,
			"isDeleted": false,
			"id": "ltu-ZOtlDZgGTs6Mt25FQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4362.553892492342,
			"y": 2392.005486785521,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1995091098,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 302,
			"versionNonce": 1591330522,
			"isDeleted": false,
			"id": "OuyGCT0aidEGZMMIV_xlO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4354.903060839406,
			"y": 2425.669146058433,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 685640026,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 263,
			"versionNonce": 1773022150,
			"isDeleted": false,
			"id": "h4lyrMqPuZ9NRZCqnwSb2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4315.768272899992,
			"y": 2437.2769589734003,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1459088390,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 263,
			"versionNonce": 1886378906,
			"isDeleted": false,
			"id": "BpzL2pArmGWF_CpYmDUg_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4298.171360098242,
			"y": 2406.673632361662,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1248361286,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 263,
			"versionNonce": 1942012678,
			"isDeleted": false,
			"id": "fJjqBsZrrLiE1ftCiXG7M",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4323.419104552924,
			"y": 2421.210212502238,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 2005213830,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 263,
			"versionNonce": 937777242,
			"isDeleted": false,
			"id": "CKnuITXdAVYwPS1xI3FKs",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4297.4062769329485,
			"y": 2431.1562936510522,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 17490374,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 264,
			"versionNonce": 637432390,
			"isDeleted": false,
			"id": "7hXwwz6SFGUeYBjTomBBd",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4346.371599511729,
			"y": 2443.3976242957483,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 0.7650831652936221,
			"seed": 706132230,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7650831652936221
				],
				[
					0,
					-0.7650831652936221
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 263,
			"versionNonce": 353189146,
			"isDeleted": false,
			"id": "T9JQ4ffuPIFCKH5Ol1IKc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4340.25093418938,
			"y": 2402.8482165351957,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1243981894,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 263,
			"versionNonce": 2068068742,
			"isDeleted": false,
			"id": "NfA2Q-8bT6-JJBBMJImS6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4328.7746867099795,
			"y": 2454.1087886098553,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1091874694,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 263,
			"versionNonce": 1968867802,
			"isDeleted": false,
			"id": "n1zfX6s8B3eyGeiZn158G",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4295.111027437068,
			"y": 2389.0767195599133,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1797312198,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 263,
			"versionNonce": 181344454,
			"isDeleted": false,
			"id": "JoE1oFFnN-Ur5EQRfWJtO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4295.876110602361,
			"y": 2467.8802855851377,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 350684678,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 263,
			"versionNonce": 534789786,
			"isDeleted": false,
			"id": "5OyN2RX8VQq85I-K8S1EN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4286.695112618841,
			"y": 2412.0292145187173,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 1868846406,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 263,
			"versionNonce": 2084311046,
			"isDeleted": false,
			"id": "tF46i66I1H9ADvs0HoUTA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4279.044280965905,
			"y": 2445.6928737916273,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 0.00010000000000000057,
			"height": 0.00010000000000000057,
			"seed": 66436230,
			"groupIds": [
				"f8vkno81qVZu82M5SFL46"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.00010000000000000057,
					-0.00010000000000000057
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "rectangle",
			"version": 322,
			"versionNonce": 22109018,
			"isDeleted": false,
			"id": "Sg_CHTdYp3gEhaEfIUXov",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4600.43668709221,
			"y": 2118.732285051637,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 341.46289873902424,
			"height": 362.86513170842085,
			"seed": 1254916550,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false
		},
		{
			"type": "freedraw",
			"version": 121,
			"versionNonce": 2072518470,
			"isDeleted": false,
			"id": "gsqfdu_GocurC-H1h3JTL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4411.919670072975,
			"y": 2295.2697463596437,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 377350278,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
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
			"type": "line",
			"version": 271,
			"versionNonce": 2013323290,
			"isDeleted": false,
			"id": "hAY-bWGVcZeFO8c9LgvwY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4411.717650242828,
			"y": 2295.529239005769,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 211.85386884971376,
			"height": 18.687306110272402,
			"seed": 1183400218,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-211.85386884971376,
					18.687306110272402
				]
			]
		},
		{
			"type": "line",
			"version": 240,
			"versionNonce": 756041350,
			"isDeleted": false,
			"id": "-AGU15nNzzvH6IGvYYpQ3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4602.325613244858,
			"y": 2233.72780872626,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 64.63678431324843,
			"height": 1.0862189619247147,
			"seed": 1685487494,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-64.63678431324843,
					-1.0862189619247147
				]
			]
		},
		{
			"type": "text",
			"version": 253,
			"versionNonce": 534891738,
			"isDeleted": false,
			"id": "0HV6yOfU",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4750.371101289274,
			"y": 2202.3089317904387,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 101.59988403320312,
			"height": 50,
			"seed": 2127829018,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Real world\nData",
			"rawText": "Real world\nData",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Real world\nData",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 295,
			"versionNonce": 563185094,
			"isDeleted": false,
			"id": "5DMNPwEa",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4716.061985540169,
			"y": 2303.023294939291,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 48.93995666503906,
			"height": 50,
			"seed": 1220349722,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Real\nMean",
			"rawText": "Real\nMean",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Real\nMean",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "ellipse",
			"version": 224,
			"versionNonce": 512172442,
			"isDeleted": false,
			"id": "aC-QqTfG4818uan2ohwkN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4475.70940802513,
			"y": 2195.793764450032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 168.76294425011656,
			"height": 151.50309767908175,
			"seed": 900245658,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false
		},
		{
			"type": "freedraw",
			"version": 119,
			"versionNonce": 1244192006,
			"isDeleted": false,
			"id": "7B4mi0GUUjEdsCgr-dBau",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4392.549802744005,
			"y": 2265.516972525339,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 73461190,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
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
			"type": "line",
			"version": 172,
			"versionNonce": 1864621658,
			"isDeleted": false,
			"id": "duGbI5NwPCxtStk3sVPxh",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4386.86568617184,
			"y": 2266.0649000449207,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 158.48811933695197,
			"height": 19.077273623892324,
			"seed": 2098256582,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					158.48811933695197,
					19.077273623892324
				]
			]
		},
		{
			"type": "image",
			"version": 429,
			"versionNonce": 1817398342,
			"isDeleted": false,
			"id": "27kMWPkgKwayYpTmYv4xc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4220.0755608307945,
			"y": 2266.295751823521,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 36.22536110413308,
			"height": 36.22536110413308,
			"seed": 1242777606,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e5bb6ffba29b952e6989f6a79f02b299cbf953d4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 151,
			"versionNonce": 780862234,
			"isDeleted": false,
			"id": "hBkt2_D-AiKnyRM02FoRy",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4310.867111265429,
			"y": 2244.474960061605,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 122.31227283739736,
			"height": 10.812134615460309,
			"seed": 766469638,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					122.31227283739736,
					-10.812134615460309
				]
			]
		},
		{
			"type": "text",
			"version": 157,
			"versionNonce": 367907718,
			"isDeleted": false,
			"id": "Kze3hxHF",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4204.188694037439,
			"y": 2212.71431462869,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 86.67990112304688,
			"height": 50,
			"seed": 1958244058,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Our\nDataset",
			"rawText": "Our\nDataset",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Our\nDataset",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 158,
			"versionNonce": 1731170266,
			"isDeleted": false,
			"id": "6vDFhFbI",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4192.084035869892,
			"y": 2266.526318428875,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 85.71989440917969,
			"height": 50,
			"seed": 352077914,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "mean\nestimate",
			"rawText": "mean\nestimate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "mean\nestimate",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "ellipse",
			"version": 263,
			"versionNonce": 288715462,
			"isDeleted": false,
			"id": "vbfWu6cNvnoJvNZ71nFJE",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4464.101074434626,
			"y": 2277.2679288257705,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 168.76294425011656,
			"height": 151.50309767908175,
			"seed": 210652934,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 328,
			"versionNonce": 1562674330,
			"isDeleted": false,
			"id": "dvHw0YcV02mQ29dIQitgm",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4585.215525953085,
			"y": 2272.7190292382215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 168.76294425011656,
			"height": 151.50309767908175,
			"seed": 605667226,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false
		},
		{
			"type": "freedraw",
			"version": 37,
			"versionNonce": 1489447430,
			"isDeleted": false,
			"id": "sjzLSCAEPSkn3Ye3spobU",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4377.445152515795,
			"y": 2353.5880901137543,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.1372248968873464,
			"height": 0,
			"seed": 412071066,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.5686124484436732,
					0
				],
				[
					-1.1372248968873464,
					0
				],
				[
					-1.1372248968873464,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 35,
			"versionNonce": 1511842138,
			"isDeleted": false,
			"id": "jKmmdQLNNLgKO6ehpY_et",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4479.7953932356195,
			"y": 2313.216606274268,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2104071258,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
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
			"type": "line",
			"version": 74,
			"versionNonce": 195033414,
			"isDeleted": false,
			"id": "H0FaowEMXNF6m5NVqH_GX",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4478.289736067138,
			"y": 2314.2716244878147,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 248.684008804109,
			"height": 24.131062848916372,
			"seed": 1952977926,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					248.684008804109,
					-24.131062848916372
				]
			]
		},
		{
			"type": "line",
			"version": 69,
			"versionNonce": 2037098010,
			"isDeleted": false,
			"id": "Cg8WYGYbTsCP-EcIGc7mD",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4373.051489753809,
			"y": 2354.490062569342,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 145.4566843948569,
			"height": 66.3604228345198,
			"seed": 954947738,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					145.4566843948569,
					-66.3604228345198
				]
			]
		},
		{
			"type": "text",
			"version": 650,
			"versionNonce": 1629282438,
			"isDeleted": false,
			"id": "JKxdJSDO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4877.955665269498,
			"y": 2505.7241846604675,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 935.5590209960938,
			"height": 300,
			"seed": 977274502,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We have M different mean estimates depending on which i.i.d random\ndatapoints we sample or the method we use (Like Bayesian estimator)\n\nThe Bias of the mean estimate can be interpreted as the difference\nbetween the mean of the mean estimates (Expected value of mean estimates)\nand the Real mean of the data\n\nThe variance of the mean estimate is the expected square deviation from the mean\nof the mean estimates\n\nMSE error is then related to how far the mean of our estimates is from the truth (squared)\nplus the deviation of our estimates from their mean",
			"rawText": "We have M different mean estimates depending on which i.i.d random\ndatapoints we sample or the method we use (Like Bayesian estimator)\n\nThe Bias of the mean estimate can be interpreted as the difference\nbetween the mean of the mean estimates (Expected value of mean estimates)\nand the Real mean of the data\n\nThe variance of the mean estimate is the expected square deviation from the mean\nof the mean estimates\n\nMSE error is then related to how far the mean of our estimates is from the truth (squared)\nplus the deviation of our estimates from their mean",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We have M different mean estimates depending on which i.i.d random\ndatapoints we sample or the method we use (Like Bayesian estimator)\n\nThe Bias of the mean estimate can be interpreted as the difference\nbetween the mean of the mean estimates (Expected value of mean estimates)\nand the Real mean of the data\n\nThe variance of the mean estimate is the expected square deviation from the mean\nof the mean estimates\n\nMSE error is then related to how far the mean of our estimates is from the truth (squared)\nplus the deviation of our estimates from their mean",
			"lineHeight": 1.25,
			"baseline": 293
		},
		{
			"type": "freedraw",
			"version": 11,
			"versionNonce": 1946407642,
			"isDeleted": false,
			"id": "PdP7Gb067sqmbqCVGpleK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4404.476807646306,
			"y": 2314.722502150386,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 969070362,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
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
			"version": 11,
			"versionNonce": 486203334,
			"isDeleted": false,
			"id": "Et59F2iYAWWXRJhGTb_Zj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4403.256079540981,
			"y": 2315.5363208872695,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 908518726,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
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
			"type": "line",
			"version": 71,
			"versionNonce": 1819830170,
			"isDeleted": false,
			"id": "td40FCNhaCBIcsI6PtgIv",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4399.593895225005,
			"y": 2316.3501396241527,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 213.2205090634834,
			"height": 78.94041747770189,
			"seed": 1594538074,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					213.2205090634834,
					78.94041747770189
				]
			]
		},
		{
			"type": "text",
			"version": 56,
			"versionNonce": 56030982,
			"isDeleted": false,
			"id": "d40vdsSV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4186.241111197323,
			"y": 2398.95274141783,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 96.57987976074219,
			"height": 100,
			"seed": 1752800198,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The mean\nof the\nmean\nestimates",
			"rawText": "The mean\nof the\nmean\nestimates",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The mean\nof the\nmean\nestimates",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 451,
			"versionNonce": 989619290,
			"isDeleted": false,
			"id": "yO-4NrOpdNKWnO-R1Qkg_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4162.0958252757955,
			"y": 2377.8484214813343,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 36.895845601315,
			"height": 23.873782447909708,
			"seed": 440970054,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f7f8e275ec17066d1763efb7bf709218ea3ce377",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 32,
			"versionNonce": 1286481478,
			"isDeleted": false,
			"id": "4c47K7lkeakXNElTBogbR",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4148.972072861552,
			"y": 2370.2472631989212,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 15.026549195566986,
			"height": 0,
			"seed": 1247351302,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5008849731857481,
					0
				],
				[
					1.0017699463714962,
					0
				],
				[
					2.0035398927429924,
					0
				],
				[
					3.005309839113579,
					0
				],
				[
					4.507964758670823,
					0
				],
				[
					5.50973470504141,
					0
				],
				[
					7.262832111191528,
					0
				],
				[
					8.264602057562115,
					0
				],
				[
					9.516814490526485,
					0
				],
				[
					10.268141950304198,
					0
				],
				[
					11.01946941008282,
					0
				],
				[
					11.770796869861442,
					0
				],
				[
					12.27168184304719,
					0
				],
				[
					12.772566816232029,
					0
				],
				[
					13.273451789417777,
					0
				],
				[
					13.523894276010651,
					0
				],
				[
					13.774336762603525,
					0
				],
				[
					14.0247792491964,
					0
				],
				[
					14.275221735789273,
					0
				],
				[
					14.525664222382147,
					0
				],
				[
					14.776106708974112,
					0
				],
				[
					15.026549195566986,
					0
				],
				[
					15.026549195566986,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "image",
			"version": 57,
			"versionNonce": 962775322,
			"isDeleted": false,
			"id": "LxGVReBk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4627.379046177491,
			"y": 2811.9277205256394,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 425.74933379888444,
			"height": 29.36202302061272,
			"seed": 47176,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0be3ba62b2da0141f4d9a27e95f64bd40402265d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 734,
			"versionNonce": 433941894,
			"isDeleted": false,
			"id": "r8BWpmIESqwNbctEQc152",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4936.487221340392,
			"y": 1931.7291162640217,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 547.0218572862095,
			"height": 2.775773952539339,
			"seed": 1407013786,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "fZl_cvW6iPYUU-Y17qL-y",
				"gap": 1,
				"focus": -0.023708598246192234
			},
			"endBinding": {
				"elementId": "3LfdDpxWFFw_jbxTr__x6",
				"gap": 4.417744145235247,
				"focus": -0.5041361305603689
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
					-547.0218572862095,
					2.775773952539339
				]
			]
		},
		{
			"type": "text",
			"version": 102,
			"versionNonce": 253662682,
			"isDeleted": false,
			"id": "oOUJKPux",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5401.413549976856,
			"y": 1803.7832889791227,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 389.4995422363281,
			"height": 100,
			"seed": 546426374,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "UbJOh3PqIQHsSk6s5iZ2s",
					"type": "arrow"
				}
			],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The bias-variance decomposition usually\napplies to regression data\nLets attempt to define this over\nC class classification",
			"rawText": "The bias-variance decomposition usually\napplies to regression data\nLets attempt to define this over\nC class classification",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The bias-variance decomposition usually\napplies to regression data\nLets attempt to define this over\nC class classification",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "rectangle",
			"version": 338,
			"versionNonce": 1747045574,
			"isDeleted": false,
			"id": "3LfdDpxWFFw_jbxTr__x6",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6484.953134768917,
			"y": 1756.0282524346253,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 997.0263119970798,
			"height": 735.2983977707325,
			"seed": 1190126982,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "r8BWpmIESqwNbctEQc152",
					"type": "arrow"
				},
				{
					"id": "5pemRsTCen_RuvUvsBTyM",
					"type": "arrow"
				},
				{
					"id": "oWYXvzhmIXpPf-PLTwUUn",
					"type": "arrow"
				}
			],
			"updated": 1708894085664,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 59,
			"versionNonce": 2101529242,
			"isDeleted": false,
			"id": "UbJOh3PqIQHsSk6s5iZ2s",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5210.828689305203,
			"y": 1790.8482467898602,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 4.085469590556386,
			"height": 261.4700537956005,
			"seed": 947295430,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oOUJKPux",
				"focus": -0.016271333285681203,
				"gap": 12.935042189262504
			},
			"endBinding": {
				"elementId": "tl9k-zAHr__qgMdZpvoIe",
				"focus": -0.07647818378870683,
				"gap": 5.49360011770807
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
					-4.085469590556386,
					-261.4700537956005
				]
			]
		},
		{
			"type": "text",
			"version": 94,
			"versionNonce": 85476358,
			"isDeleted": false,
			"id": "p8hhXJbb",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5204.925520978625,
			"y": 1642.749974132196,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 172.039794921875,
			"height": 25,
			"seed": 1085322458,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Some clarification",
			"rawText": "Some clarification",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Some clarification",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 316,
			"versionNonce": 713189210,
			"isDeleted": false,
			"id": "PNxgXkXK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5540.30790839592,
			"y": 1325.266330052749,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 628.0391845703125,
			"height": 150,
			"seed": 179157466,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rnSwgmDQ2dzNem0GQ4LOV",
					"type": "arrow"
				}
			],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Given C classes\nThe true probability of each class associated to\na particular input is\n\n\nWe are trying to estimate this distribution of probabilities with",
			"rawText": "Given C classes\nThe true probability of each class associated to\na particular input is\n\n\nWe are trying to estimate this distribution of probabilities with",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given C classes\nThe true probability of each class associated to\na particular input is\n\n\nWe are trying to estimate this distribution of probabilities with",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 183,
			"versionNonce": 45994822,
			"isDeleted": false,
			"id": "1X119f2q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5317.063609417595,
			"y": 1407.8639666130462,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 185.44381454369528,
			"height": 28.147721850382318,
			"seed": 91391,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "231762a8a6e51311fb13d9b10685c6eac13a7089",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 275,
			"versionNonce": 1865444378,
			"isDeleted": false,
			"id": "tl9k-zAHr__qgMdZpvoIe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5317.386805275445,
			"y": 1476.1167416692901,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 189.47914312213646,
			"height": 47.767851207261295,
			"seed": 1802335130,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "UbJOh3PqIQHsSk6s5iZ2s",
					"type": "arrow"
				}
			],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e3b18d25624a32b3f22aa91d8f38c74700190074",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 234,
			"versionNonce": 728726150,
			"isDeleted": false,
			"id": "rnSwgmDQ2dzNem0GQ4LOV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5219.3733110149915,
			"y": 1309.1424026000172,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 444.0399455403649,
			"height": 290.80672657940886,
			"seed": 2031355910,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PNxgXkXK",
				"focus": 0.017560637596469416,
				"gap": 16.123927452731778
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
					4.338875754512628,
					-286.36579979782846
				],
				[
					-439.70106978585227,
					-290.80672657940886
				]
			]
		},
		{
			"type": "text",
			"version": 883,
			"versionNonce": 557832410,
			"isDeleted": false,
			"id": "wrD0Qdsn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6323.546768209985,
			"y": 952.0642648215361,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 575.6393432617188,
			"height": 125,
			"seed": 1793830214,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Just like in the Regression case earlier,\ngiven Multiple estimates      for the same input pattern \n   (whether its multiple iterations, approximations\nup to an arbitrary accuracy, Bayesian estimator etc...)\n",
			"rawText": "Just like in the Regression case earlier,\ngiven Multiple estimates      for the same input pattern \n   (whether its multiple iterations, approximations\nup to an arbitrary accuracy, Bayesian estimator etc...)\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Just like in the Regression case earlier,\ngiven Multiple estimates      for the same input pattern \n   (whether its multiple iterations, approximations\nup to an arbitrary accuracy, Bayesian estimator etc...)\n",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 297,
			"versionNonce": 1978284486,
			"isDeleted": false,
			"id": "SZF7VyZi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6070.543049654268,
			"y": 978.8882007414743,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 26.86740428863777,
			"height": 22.837293645342104,
			"seed": 15893,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "918fe75016407ddf7425853963e1676a682f0032",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 565,
			"versionNonce": 1615048090,
			"isDeleted": false,
			"id": "eME_k3SxtUiJcL_0aeKCz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6024.659268431358,
			"y": 1414.689438569254,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 0.9418015142418881,
			"height": 72.35143338914963,
			"seed": 860474970,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "pjlgwucJgbZpzgXdQTPK5",
				"focus": -0.02972039238170212,
				"gap": 8.011903433423868
			},
			"endBinding": {
				"elementId": "xRkuOBQA",
				"focus": -0.0008405184952117393,
				"gap": 14.490168339127194
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
					-0.9418015142418881,
					72.35143338914963
				]
			]
		},
		{
			"type": "text",
			"version": 323,
			"versionNonce": 2034962694,
			"isDeleted": false,
			"id": "xRkuOBQA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6429.844793649037,
			"y": 1501.5310402975308,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 808.13916015625,
			"height": 50,
			"seed": 1079625242,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "eME_k3SxtUiJcL_0aeKCz",
					"type": "arrow"
				}
			],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Just like in the MSE case, the error is evaluated by the distance between\nthe estimate and ground truth, the closer it is to the truth the lower the error",
			"rawText": "Just like in the MSE case, the error is evaluated by the distance between\nthe estimate and ground truth, the closer it is to the truth the lower the error",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Just like in the MSE case, the error is evaluated by the distance between\nthe estimate and ground truth, the closer it is to the truth the lower the error",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 207,
			"versionNonce": 1634658906,
			"isDeleted": false,
			"id": "uuKXb15X",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6263.131609777348,
			"y": 1559.6252417025364,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 481.80886210305226,
			"height": 70.85424442691945,
			"seed": 1306,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "5pemRsTCen_RuvUvsBTyM",
					"type": "arrow"
				}
			],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b66c5f796a7e14bc678ad77572c8f5d7425941ad",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 153,
			"versionNonce": 1628373062,
			"isDeleted": false,
			"id": "DNQKxI6s",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6459.374512942937,
			"y": 1169.6745413063613,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 865.2391357421875,
			"height": 150,
			"seed": 487569946,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Pa9PrBw4InrfG72pR13zW",
					"type": "arrow"
				}
			],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "we can calculate the mean of such estimates by calculating the point\nsuch that minimizes the distance to all estimates\nEXCEPT in this case we are not dealing with number or vectors\nbut instead with distributions... and as such Closeness is defined using a KL divergence\nwhich is just a fancy way of defining how close/far apart are two distributions\nWe define R as the mean of our estimates",
			"rawText": "we can calculate the mean of such estimates by calculating the point\nsuch that minimizes the distance to all estimates\nEXCEPT in this case we are not dealing with number or vectors\nbut instead with distributions... and as such Closeness is defined using a KL divergence\nwhich is just a fancy way of defining how close/far apart are two distributions\nWe define R as the mean of our estimates",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "we can calculate the mean of such estimates by calculating the point\nsuch that minimizes the distance to all estimates\nEXCEPT in this case we are not dealing with number or vectors\nbut instead with distributions... and as such Closeness is defined using a KL divergence\nwhich is just a fancy way of defining how close/far apart are two distributions\nWe define R as the mean of our estimates",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "arrow",
			"version": 117,
			"versionNonce": 999591706,
			"isDeleted": false,
			"id": "Pa9PrBw4InrfG72pR13zW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6026.754945071844,
			"y": 1062.1537059459495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 0,
			"height": 95.96901007375595,
			"seed": 622006150,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085664,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "DNQKxI6s",
				"focus": -2.1022967274654748e-15,
				"gap": 11.551825286655912
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
					95.96901007375595
				]
			]
		},
		{
			"type": "image",
			"version": 417,
			"versionNonce": 1628637062,
			"isDeleted": false,
			"id": "pjlgwucJgbZpzgXdQTPK5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6144.937201945587,
			"y": 1360.4177778589528,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 234.38277020284448,
			"height": 46.2597572768772,
			"seed": 1006166234,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "eME_k3SxtUiJcL_0aeKCz",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9c6a58f061b8d33db8f15175756530bff3b10a00",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 78,
			"versionNonce": 858233818,
			"isDeleted": false,
			"id": "rc1VK0o7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6139.306179416456,
			"y": 1319.674540589627,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 223.12072548134176,
			"height": 32.698727010196635,
			"seed": 21761,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "df9859ab31bfe1d689789a130f3bc8a058172627",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 240,
			"versionNonce": 697575110,
			"isDeleted": false,
			"id": "5pemRsTCen_RuvUvsBTyM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6023.756545620804,
			"y": 1636.4811555518927,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 1.1449508447258268,
			"height": 113.11512868189425,
			"seed": 88876122,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "uuKXb15X",
				"gap": 6.001669422436748,
				"focus": 0.008074146115418835
			},
			"endBinding": {
				"elementId": "3LfdDpxWFFw_jbxTr__x6",
				"gap": 6.431968200838469,
				"focus": -0.06448216534535908
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
					1.1449508447258268,
					113.11512868189425
				]
			]
		},
		{
			"type": "image",
			"version": 238,
			"versionNonce": 104534170,
			"isDeleted": false,
			"id": "ny9Y2ytl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6477.96359888212,
			"y": 1763.9733686010886,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 373.29186908356536,
			"height": 59.63128899098488,
			"seed": 95185,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "947453ecbd71a27be1784d3102f26170d2e89e73",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 152,
			"versionNonce": 1529830918,
			"isDeleted": false,
			"id": "ukbdgyvC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6090.54587880821,
			"y": 1787.0996108510108,
			"strokeColor": "#ffffff",
			"backgroundColor": "#336645",
			"width": 137.1445770263672,
			"height": 35,
			"seed": 712450630,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "such that",
			"rawText": "such that",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "such that",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 61,
			"versionNonce": 948039002,
			"isDeleted": false,
			"id": "ehkJ5nL5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5929.406709445495,
			"y": 1787.0996112582109,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 94.45724772892058,
			"height": 26.98778506540588,
			"seed": 88843,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VZy4XbvQUFUqA_NXJJHXg",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8617d18e2d6b7da45854dc5bff2fa7774b4ad8a9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 137,
			"versionNonce": 2061610310,
			"isDeleted": false,
			"id": "Pp2wxTf55lj_B2xjQmuvW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5739.276087125424,
			"y": 1759.6683221515577,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 106.2686802270987,
			"height": 70.8457868180658,
			"seed": 1888355738,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c78aca2b8c2468d5ffaa71bd660f81b9da9d50ea",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 56,
			"versionNonce": 43836377,
			"isDeleted": false,
			"id": "U8gJxxwi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5810.95463402918,
			"y": 1787.0996110324634,
			"strokeColor": "#ffffff",
			"backgroundColor": "#336645",
			"width": 47.68395385742187,
			"height": 35,
			"seed": 1001986010,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709390646920,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "arrow",
			"version": 158,
			"versionNonce": 1711805574,
			"isDeleted": false,
			"id": "VZy4XbvQUFUqA_NXJJHXg",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5860.807742781234,
			"y": 1771.3678926261034,
			"strokeColor": "#e03131",
			"backgroundColor": "#336645",
			"width": 106.24022779238476,
			"height": 65.9688275342794,
			"seed": 1514062598,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ehkJ5nL5",
				"focus": 0.47445315661652077,
				"gap": 15.731718632107572
			},
			"endBinding": {
				"elementId": "cEOpYRbA",
				"focus": 0.5212440812298706,
				"gap": 5.6691034385839885
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
					-2.8790307649205715,
					-63.33867682824007
				],
				[
					103.36119702746419,
					-65.9688275342794
				]
			]
		},
		{
			"type": "text",
			"version": 174,
			"versionNonce": 1838538458,
			"isDeleted": false,
			"id": "cEOpYRbA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5751.777442315186,
			"y": 1689.0421327605995,
			"strokeColor": "#e03131",
			"backgroundColor": "#336645",
			"width": 312.8326721191406,
			"height": 60,
			"seed": 258647430,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VZy4XbvQUFUqA_NXJJHXg",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can get rid of this constraint by\nenforcing that Ri = exp(zi)\nand build our lagrangian according to zi",
			"rawText": "We can get rid of this constraint by\nenforcing that Ri = exp(zi)\nand build our lagrangian according to zi",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can get rid of this constraint by\nenforcing that Ri = exp(zi)\nand build our lagrangian according to zi",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 230,
			"versionNonce": 1180668870,
			"isDeleted": false,
			"id": "GVUSAjLb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6477.963598698045,
			"y": 1831.811693800836,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 567.0869929423235,
			"height": 63.861147853865255,
			"seed": 26882,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5ce9a8470b0aaadcc8b583802f59905a5658e9f3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 341,
			"versionNonce": 2145973146,
			"isDeleted": false,
			"id": "G0vn9FvKC3omaUOQ3GV45",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6477.963598773009,
			"y": 1904.6892034399684,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 687.8499354927533,
			"height": 65.01417159666855,
			"seed": 839779718,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4228c01f6e86270430cb31e61accf26b8e31b6de",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 402,
			"versionNonce": 101001990,
			"isDeleted": false,
			"id": "IgoLBuljCYW6ydE1sMFhN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6477.963598933568,
			"y": 1978.7197360843238,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 659.3014023509621,
			"height": 67.82936238178623,
			"seed": 947241050,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ukqnIKC8WNxmrNQz-rteD",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "df8fd5ac91381c09e55b6a899e32132dcc5d239d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 414,
			"versionNonce": 679178330,
			"isDeleted": false,
			"id": "eg_NGzrC7AazDXazRuPiH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6476.604208444409,
			"y": 2052.152532849209,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 656.5826220993323,
			"height": 68.11023050822949,
			"seed": 663630086,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ukqnIKC8WNxmrNQz-rteD",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9e2e687b4a36b0386338e08e8ce32d5a1c8b001d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 97,
			"versionNonce": 1131797062,
			"isDeleted": false,
			"id": "ukqnIKC8WNxmrNQz-rteD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5802.954345923102,
			"y": 2021.3104120219066,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 55.70602814191079,
			"height": 67.46618963853666,
			"seed": 288752538,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "IgoLBuljCYW6ydE1sMFhN",
				"focus": -0.6867127531874133,
				"gap": 15.707850659504402
			},
			"endBinding": {
				"elementId": "eg_NGzrC7AazDXazRuPiH",
				"focus": 0.4156750521785016,
				"gap": 2.8312554523749895
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
					41.47004317231131,
					11.141205628382295
				],
				[
					37.75630796284986,
					64.37141029731924
				],
				[
					-14.235984969599485,
					67.46618963853666
				]
			]
		},
		{
			"type": "text",
			"version": 257,
			"versionNonce": 991974682,
			"isDeleted": false,
			"id": "5motVAIe",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5768.8127237637855,
			"y": 2008.6732285648325,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 278.01641845703125,
			"height": 88.61888451496841,
			"seed": 1606547930,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"fontSize": 14.179021522394947,
			"fontFamily": 1,
			"text": "Remember that this is expectation over\nthe estimate, meaning that the\nmean R is a constant in this term\nand can be taken out of\nthe expectation",
			"rawText": "Remember that this is expectation over\nthe estimate, meaning that the\nmean R is a constant in this term\nand can be taken out of\nthe expectation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Remember that this is expectation over\nthe estimate, meaning that the\nmean R is a constant in this term\nand can be taken out of\nthe expectation",
			"lineHeight": 1.25,
			"baseline": 83
		},
		{
			"type": "arrow",
			"version": 61,
			"versionNonce": 1166975366,
			"isDeleted": false,
			"id": "KQ-wy38qBDJHBEvcWC_Kz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5496.493515602201,
			"y": 2055.2899747335355,
			"strokeColor": "#e03131",
			"backgroundColor": "#336645",
			"width": 78.69742096827576,
			"height": 2.098597892487305,
			"seed": 112531078,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085665,
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
					78.69742096827576,
					2.098597892487305
				]
			]
		},
		{
			"type": "image",
			"version": 122,
			"versionNonce": 424321498,
			"isDeleted": false,
			"id": "8qCQoSeo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5394.375923942446,
			"y": 2052.696380130166,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 136,
			"height": 17,
			"seed": 22397,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6aae1c1d08954b8b7467abe68c5b7f4b6fcad8c7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 125,
			"versionNonce": 1871478982,
			"isDeleted": false,
			"id": "3DEPJRRI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5474.358975923815,
			"y": 2017.515212668763,
			"strokeColor": "#e03131",
			"backgroundColor": "#336645",
			"width": 309.34466552734375,
			"height": 20,
			"seed": 1067057670,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is the equivalent of this equation",
			"rawText": "This is the equivalent of this equation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is the equivalent of this equation",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 175,
			"versionNonce": 2114803354,
			"isDeleted": false,
			"id": "U9qBtlpK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5474.358975877997,
			"y": 2076.9494460564047,
			"strokeColor": "#e03131",
			"backgroundColor": "#336645",
			"width": 297.13665771484375,
			"height": 80,
			"seed": 257866906,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "No matter which x_i we are currently\nat the mean is always the same\nand thus it is a constant to be\ntaken out of the expectation",
			"rawText": "No matter which x_i we are currently\nat the mean is always the same\nand thus it is a constant to be\ntaken out of the expectation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "No matter which x_i we are currently\nat the mean is always the same\nand thus it is a constant to be\ntaken out of the expectation",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "image",
			"version": 584,
			"versionNonce": 890009606,
			"isDeleted": false,
			"id": "XLGmTTrSWGOnp8Muyg9zD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6476.604207623761,
			"y": 2120.262763419543,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 637.2500436321725,
			"height": 49.419391138821545,
			"seed": 1288102426,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b8dba8a37b10ea06169552b18a2bed3f5be96bb0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 255,
			"versionNonce": 1243312986,
			"isDeleted": false,
			"id": "DhOtBRqO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5818.662196682456,
			"y": 2115.669147131514,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 264.9019348759641,
			"height": 58.60662276016905,
			"seed": 48863,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "65efc70b43f45ddd64af0d1ff594a002c911483e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 727,
			"versionNonce": 235636550,
			"isDeleted": false,
			"id": "CgIhK-v3cMTL1zv-OB2jw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6476.604207593398,
			"y": 2174.2757704006485,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 415.007048682321,
			"height": 44.78493331104183,
			"seed": 1657137626,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1780209197cc0175c1e5599ffcb137493737e437",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 892,
			"versionNonce": 1338505242,
			"isDeleted": false,
			"id": "d9s6L-mzFwL6cTlm1gHr-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6476.604207554967,
			"y": 2227.5240994255605,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 257.32641994682496,
			"height": 44.11310056231285,
			"seed": 1225295258,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "64b75979621d9d570659115f66d1cb431d774b53",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 949,
			"versionNonce": 1793502854,
			"isDeleted": false,
			"id": "MQK7gbgYrfzwjO9tyRSXU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6477.963599312309,
			"y": 2271.6372002401818,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 563.7552020503194,
			"height": 65.81283195741615,
			"seed": 1299895878,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "zJ2blCjXNmsEq9P8zUfMk",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8bd2540c6bc2be881539514f695424da72fdd6fc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 438,
			"versionNonce": 520479962,
			"isDeleted": false,
			"id": "j32rNBX5HZJyU-qMv1DaW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5731.606917792823,
			"y": 2174.275770256821,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 144.60536786831184,
			"height": 57.38308248742534,
			"seed": 394154330,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Dr_b-ljdDMamRS2_WGngU",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7694e24dd565b76a14c3ac279285ee5f11746155",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 80,
			"versionNonce": 677047750,
			"isDeleted": false,
			"id": "zJ2blCjXNmsEq9P8zUfMk",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5908.502662846946,
			"y": 2303.6776832712326,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 103.09433873781472,
			"height": 4.547473508864641e-13,
			"seed": 453840346,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "MQK7gbgYrfzwjO9tyRSXU",
				"focus": -0.02631501857316374,
				"gap": 5.705734415043935
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
					103.09433873781472,
					-4.547473508864641e-13
				]
			]
		},
		{
			"type": "arrow",
			"version": 179,
			"versionNonce": 1365784986,
			"isDeleted": false,
			"id": "Dr_b-ljdDMamRS2_WGngU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5645.512963404262,
			"y": 2232.6588527442464,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 0.16304367923385144,
			"height": 29.984551784154974,
			"seed": 619794438,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "j32rNBX5HZJyU-qMv1DaW",
				"focus": -0.1881046811070156,
				"gap": 1.0000000000002274
			},
			"endBinding": {
				"elementId": "e0HGRaaXP7nMHnv6NEWol",
				"focus": 0.24658286826062964,
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
					0.16304367923385144,
					29.984551784154974
				]
			]
		},
		{
			"type": "image",
			"version": 509,
			"versionNonce": 59065606,
			"isDeleted": false,
			"id": "e0HGRaaXP7nMHnv6NEWol",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5787.208313318538,
			"y": 2263.3075406956727,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 227.83742691090566,
			"height": 71.8183193523507,
			"seed": 1536468186,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Dr_b-ljdDMamRS2_WGngU",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5c2a348afba75bd508ee45ac467a04982a812554",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 652,
			"versionNonce": 1445066330,
			"isDeleted": false,
			"id": "BNBAeDVpVcnprK31SmF2e",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5796.9560402055195,
			"y": 2342.270439181715,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 293.9321651941004,
			"height": 55.66897068070082,
			"seed": 1444915354,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fe41afea4630c63569157f45fdff277d342a6a3f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 663,
			"versionNonce": 232961094,
			"isDeleted": false,
			"id": "W-_TV4EeHe32GpyK6ExSI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5790.020330432602,
			"y": 2400.916626999255,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 283.15758037336013,
			"height": 57.787261300685735,
			"seed": 959552346,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ObB3JgNdDWpwEDcVfTTiY",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f2ff9f3cb737e2da37ab85e7c4dc99cd010534c4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 206,
			"versionNonce": 1040587546,
			"isDeleted": false,
			"id": "ObB3JgNdDWpwEDcVfTTiY",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5804.594814263635,
			"y": 2429.4394852103546,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 121.53148628612507,
			"height": 0.7217950931108135,
			"seed": 904451718,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "W-_TV4EeHe32GpyK6ExSI",
				"gap": 14.574483831033376,
				"focus": 0.04104538627192077
			},
			"endBinding": {
				"elementId": "gUYPAeA5",
				"gap": 13.234975520639182,
				"focus": 0.5816721280751918
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
					-121.53148628612507,
					0.7217950931108135
				]
			]
		},
		{
			"type": "image",
			"version": 151,
			"versionNonce": 558906246,
			"isDeleted": false,
			"id": "gUYPAeA5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6292.373390957545,
			"y": 2364.3496736904003,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 353.0121148871446,
			"height": 83.8716726859528,
			"seed": 57014,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ObB3JgNdDWpwEDcVfTTiY",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6d04a7d9e1f996334181d04bad7e84142c542c37",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 360,
			"versionNonce": 126330842,
			"isDeleted": false,
			"id": "oWYXvzhmIXpPf-PLTwUUn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6005.896900039357,
			"y": 2494.7586987557993,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 1.1028570141825185,
			"height": 266.6788386339649,
			"seed": 1482862106,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "3LfdDpxWFFw_jbxTr__x6",
				"gap": 3.4320485504413227,
				"focus": 0.03584102912137774
			},
			"endBinding": {
				"elementId": "kUJ5JYn1HBiuGckVjLZHr",
				"gap": 6.270292040555887,
				"focus": -0.0027784144962506446
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
					-1.1028570141825185,
					266.6788386339649
				]
			]
		},
		{
			"type": "text",
			"version": 186,
			"versionNonce": 1409997510,
			"isDeleted": false,
			"id": "MsHGQXvD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5995.618926676554,
			"y": 2586.0761869768726,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 469.99951171875,
			"height": 75,
			"seed": 1381314586,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Alright well now that we have defined our mean\nof estimates lets decompose our error function\ninto Bias and variance terms",
			"rawText": "Alright well now that we have defined our mean\nof estimates lets decompose our error function\ninto Bias and variance terms",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Alright well now that we have defined our mean\nof estimates lets decompose our error function\ninto Bias and variance terms",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 513,
			"versionNonce": 1790549146,
			"isDeleted": false,
			"id": "kUJ5JYn1HBiuGckVjLZHr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6505.203236906171,
			"y": 2767.70782943032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#336645",
			"width": 997.0263119970798,
			"height": 508.9525794838809,
			"seed": 687258522,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "oWYXvzhmIXpPf-PLTwUUn",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 533,
			"versionNonce": 1823445510,
			"isDeleted": false,
			"id": "6w8nW4j1x26Ygim-LjDMa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6484.953135279358,
			"y": 2780.7761970842384,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 953.94321953532,
			"height": 56.18040162163251,
			"seed": 1867384666,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "pyEKkzwnPEsFtDsfBRTzz",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "456b06746e40203ac8d0288f837c66b94d2d25db",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 761,
			"versionNonce": 625932634,
			"isDeleted": false,
			"id": "5IpGhBRfYpGrrm7CCmcn4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6484.953134577312,
			"y": 2843.9049787630574,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 597.3087053704197,
			"height": 60.21257110588908,
			"seed": 1455648518,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "pyEKkzwnPEsFtDsfBRTzz",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "db54025755589a96a3cfc013519885fd0b4ffafc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 74,
			"versionNonce": 1446732102,
			"isDeleted": false,
			"id": "pyEKkzwnPEsFtDsfBRTzz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5756.612297675663,
			"y": 2843.0388273588305,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 116.86611231716324,
			"height": 44.275267221480135,
			"seed": 2030327002,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6w8nW4j1x26Ygim-LjDMa",
				"focus": -0.5270108800783357,
				"gap": 6.082228652959884
			},
			"endBinding": {
				"elementId": "5IpGhBRfYpGrrm7CCmcn4",
				"focus": 0.5319666232443033,
				"gap": 14.166019214066637
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
					42.2159524669928
				],
				[
					-116.86611231716324,
					44.275267221480135
				]
			]
		},
		{
			"type": "text",
			"version": 83,
			"versionNonce": 1184546330,
			"isDeleted": false,
			"id": "yr0yZoap",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5742.789854359139,
			"y": 2845.5388273588305,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 166.96035766601562,
			"height": 40,
			"seed": 113718662,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Constants taken out\nof the expectation",
			"rawText": "Constants taken out\nof the expectation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Constants taken out\nof the expectation",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 868,
			"versionNonce": 336283782,
			"isDeleted": false,
			"id": "AsYf3yACPQadMrHOwGq6K",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6484.379801628774,
			"y": 2904.117550218498,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 477.6897209199987,
			"height": 63.18647102116384,
			"seed": 1478369690,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2a8e839458336430d6c08badef3de8f8ff208318",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 982,
			"versionNonce": 2073029338,
			"isDeleted": false,
			"id": "bhitw0SvZmtKk62oRZEKf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6484.37980225115,
			"y": 2967.3040206958713,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 469.4036133952754,
			"height": 64.30186484866786,
			"seed": 2122012698,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bad5fd2db45dca9af1f9861bb84e6d37081521e8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 148,
			"versionNonce": 903628742,
			"isDeleted": false,
			"id": "1qIQ9UnMc1WOTdtlAgxlA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5985.2129671901575,
			"y": 2931.7730526479104,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 62.48148484569174,
			"height": 66.0454696893812,
			"seed": 1319054790,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085665,
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
					51.72375498497877,
					3.5671555162052755
				],
				[
					47.96126321269094,
					57.83146276991283
				],
				[
					-10.75772986071297,
					66.0454696893812
				]
			]
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 1522630554,
			"isDeleted": false,
			"id": "uKjVNk20",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5915.48112662433,
			"y": 2949.608830228937,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 231.52049255371094,
			"height": 40,
			"seed": 1900670170,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "hzMiWg8WwdeuuG4cmPRQ3",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "E(logRi - logPi) is independent\nvalue of i",
			"rawText": "E(logRi - logPi) is independent\nvalue of i",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "E(logRi - logPi) is independent\nvalue of i",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 79,
			"versionNonce": 1271619334,
			"isDeleted": false,
			"id": "hzMiWg8WwdeuuG4cmPRQ3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5676.632788924632,
			"y": 2960.6299264452737,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 303.1427326731482,
			"height": 0.5708902686878901,
			"seed": 819927110,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "uKjVNk20",
				"focus": -0.4555695999493253,
				"gap": 7.32784514598643
			},
			"endBinding": {
				"elementId": "dW2xnbQc",
				"focus": 0.022599396343103952,
				"gap": 8.30618751621978
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
					303.1427326731482,
					0.5708902686878901
				]
			]
		},
		{
			"type": "text",
			"version": 28,
			"versionNonce": 811760730,
			"isDeleted": false,
			"id": "qV4HBhxK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5565.666288093001,
			"y": 2937.7943156977676,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 42.9600830078125,
			"height": 20,
			"seed": 683863706,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Proof",
			"rawText": "Proof",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Proof",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 1047,
			"versionNonce": 1515556422,
			"isDeleted": false,
			"id": "I_GEQ-kdgXDdgWIBucB4g",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6484.701091697148,
			"y": 3031.6498382605164,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 470.04619222231935,
			"height": 64.2139606861092,
			"seed": 1289986970,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8Rk4NMOe18EvbJeoS8Yi_",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a04db8853f041d459f61af9e9737b08ef6f2ee11",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 147,
			"versionNonce": 1246093594,
			"isDeleted": false,
			"id": "8Rk4NMOe18EvbJeoS8Yi_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5993.876093055808,
			"y": 3017.0324032765243,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 63.055805790305385,
			"height": 53.0996259286776,
			"seed": 1560876378,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "I_GEQ-kdgXDdgWIBucB4g",
				"focus": -0.4503617492115171,
				"gap": 13.90952148803217
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
					55.86523144579587,
					-2.2124844136947104
				],
				[
					53.09962592867669,
					50.887141514982886
				],
				[
					-7.190574344509514,
					45.35593048074543
				]
			]
		},
		{
			"type": "text",
			"version": 125,
			"versionNonce": 1314379142,
			"isDeleted": false,
			"id": "d7qHQkHX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5933.538510485943,
			"y": 3016.266650978181,
			"strokeColor": "#3bc9db",
			"backgroundColor": "#336645",
			"width": 188.60842895507812,
			"height": 60,
			"seed": 748290138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Sum of probabilities\nis always 1 we just\nexchange the probability",
			"rawText": "Sum of probabilities\nis always 1 we just\nexchange the probability",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sum of probabilities\nis always 1 we just\nexchange the probability",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 944,
			"versionNonce": 1138666970,
			"isDeleted": false,
			"id": "bZQChMLb-WpDvf7FEyrkp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6484.553609651261,
			"y": 3089.120504824905,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 478.9517831483113,
			"height": 63.019971466883064,
			"seed": 1954104602,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "37a92c40c90e02a3e639eb4c2ab47d71fc895b63",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 1106,
			"versionNonce": 1896821958,
			"isDeleted": false,
			"id": "hKy1U4Addpsg2d_Ad6EQx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6484.953134588331,
			"y": 3152.1404756784805,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 374.1948816086867,
			"height": 40.52652147386499,
			"seed": 1373253574,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "92a02b6ab66c716b080f6b846747e830ff79fb96",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 1173,
			"versionNonce": 1379918490,
			"isDeleted": false,
			"id": "KeUbPgMue2QM2L6t33Ifs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6484.953134713802,
			"y": 3202.104875250276,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 371.29768631510865,
			"height": 40.84274549466195,
			"seed": 388237254,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ab6220a15c9d1689fd5f968b60d9d6a15f819f49",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 83,
			"versionNonce": 1545120774,
			"isDeleted": false,
			"id": "dW2xnbQc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5367.054003527539,
			"y": 2943.5760809649696,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 605.2944985047571,
			"height": 37.287135431504545,
			"seed": 68561,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "hzMiWg8WwdeuuG4cmPRQ3",
					"type": "arrow"
				}
			],
			"updated": 1708894085665,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3f7033b628aec6663353f2a1073cb254bee8a726",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 504,
			"versionNonce": 56317466,
			"isDeleted": false,
			"id": "0G3NBQeuvaoWHG0PuAaRp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5168.3153414900235,
			"y": 2982.2452713933944,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 252.986641688588,
			"height": 23.190442154787235,
			"seed": 2006960794,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894204420,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8645ceec0dbad0d7d1e9ff888de9e068694e7c2f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 537,
			"versionNonce": 915038470,
			"isDeleted": false,
			"id": "DRazOdoYjsnKhZbUpvCd5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5168.315341190558,
			"y": 3009.6416130282996,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 264.6338515333099,
			"height": 30.186370897335728,
			"seed": 1558591002,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894206320,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ff96b112342a866dff1f1caf25fddaa0e860122b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 681,
			"versionNonce": 318301126,
			"isDeleted": false,
			"id": "mq3u5sF9XUxdA0_cSRj-7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5168.31534129001,
			"y": 3044.0338831079125,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 75.80641432721552,
			"height": 16.956697941614,
			"seed": 2129407258,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708894207420,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0ace05baa197b5ba77625088e5d5b8d302b25c7",
			"scale": [
				1,
				1
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#3bc9db",
		"currentItemBackgroundColor": "#336645",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 7270.022813316301,
		"scrollY": 1739.6638599235944,
		"zoom": {
			"value": 0.15000000000000002
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