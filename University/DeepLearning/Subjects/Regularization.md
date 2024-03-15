---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - DeepLearning
---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Regularization ^gAuzuRO3

This note emphasizes on the importance of data and training
on that data such that our model is applicable to the real
world data.
More often than not, we find our models really good at predicting 
datapoints it has already seen before (training data), but it will reach
a point trying too hard to fit solutions that exactly match the training data
that it diverges from giving a general solution to the overall problem,
making it bad at predicting datapoints it has never seen before. ^jcrh7ipp

Training error ^11HP8S49

True error ^T61Yixg2

the true probability distribution from
which the data is coming,
which is unknown making the true
error hard to minimize ^Z2NjEUJe

So what makes the dataset we have
not be able to fully represent the true
distribution? ^druYSTwG

Finite Data:
The fact the dataset is composed
of few data points drawn randomly
from the underlying data distribution
 ^u5sUn9R4

Dataset bias:
The fact that the dataset may
over-represent certain parts of the
underlying distribution due to randomness ^ZOHm2JC4

Distribution shift:
The fact that the dataset may have
been generated from an underlying
distribution that is now obsolete ^7gStXyzB

Image and text data may suffer from this ^wCw1OPmO

Sensor data may suffer from this ^XkLB1sil

games may suffer from this ^R2SlTmqa

simulated data may suffer from this ^7IT443Zj

medical data may suffer from this ^dQXb31S5

medical and social data may suffer from this ^8MjI0CKa

Overfitting ^SPGrJNax

When we have a finite and limited amount of data we 
find ourselves struggling to represent the data distribution
the way we want to leading our model to focus on perfection of 
the finite data and "overfitting" it causing it to generalize
less for overall data ^I4j3ahWK

one class or target value
may be locally predominant in our
dataset in areas that the other class
is more common in the real world
we do not want to teach this to our model ^dRQM8ZQY

Although the model is much less complex
it is often preferred over a complex one as
long as it classifies correctly ^TOQIGk6E

%%***>>>text element-link:[[SVM]]<<<***%%VC Theory ^xct4X5WU

According to VC theory, we have a few factors that make the
gap between training error and the true error

1) Increasing the amount of datapoints N (Which is our issue here)

2) Reducing the model complexity/ VC dimension h (Which is our alternative)

We have previously used solution 2 in linear models, but can we do the same in neural networks? ^oq5rCSRF

Feature extraction ^SQ8q1XSf

We can extract the most representative features from our data,
whether its manually or methods like PCA, then we proceed to train
our model on this low dimensional data. ^rEsEBSdP

this is often helpful in noisy data but can sometimes
be harmful and ends up deleting class relevant data ^3kqHQVHL

Reducing Sensitivity ^FsJiZbGU

Decaying weights by including in the objective
a term that makes the weights tend to zero if
they are not necessary for the prediction task ^ZoEFip9Q

the higher the parameter λ, the more the exposure of the model to
variations in the input domain is being reduced ^UC03YsX7

an alternative ^rRkRIovB

Dropout ^IOXdw3oV

Dropout consists of adding artificial multiplicative noise
to the input and intermediate neurons, and training
the model subject to that noise.
This is achieved by inserting layers between hidden layers
that include a dropout term that multiplies its input
by some random noise, often drawn from a bernouli
distribution ^vufZSiDT

This noise basically makes
some neurons die out in certain
predictions which reduces the amount
of features the model takes into account
while classifying
In image classification this is superior to weight decay ^BNJo3AXQ

Choosing appropriate complexity ^8ux7oyqG

often when choosing a model we want a balance of a model
classifying data correctly but also not being overly complex, but how do
we know what to prioritize more, and which to choose? ^FNVmhIsW

Holdout ^pBlZe4uH

Train many different models using different regularization terms
and pick out the best performing one ^HAG1R7db

How do I find the best
performing one? ^jV8yv8FF

Validation ^4jXmGQuH

to simulate how your model will perform in
the real world, shard a small dataset from
the original dataset such that the model will never see
and test it on that dataset after training

How do i pick the size of the dataset? ^8fRy3Ium

%%***>>>text element-link:[[Model Selection]]<<<***%%More about this in validation note ^qADEqQ8V

This is quite costly
for bigger models
can we improve? ^MbUuNcEc

Early stopping ^Xkl3JmZ8

Think of our procedure of training our model as a way to generate
different versions of our model per epoch.
We can use validation testing on our network per iteration and monitor
when our model had the lowest error rate to keep in the background
such that if it starts over-fitting we can just stop it and keep the minimum
model ^cQAHpDZD

We are only training one model here ^yn8fKA66

Double Descent ^yZv8a3u3

An interesting phenomenon we have observed with very large neural networks
is that there is often a second descent in test error after the first initial convexity ^5W2tUqv6

This can be interpreted as some implicit averaging between the many
components of the model, thus allowing us to achieve lower test results
without any regularization IF our machine can handle a big enough model ^FFmiWwnS

Multiple domains ^6iJbDMKd

Sometimes our dataset is often shifted away from the actual distribution
whether due to a result of distribution shift or because the subgroup
represented only a certain local domains of the distribution ^hrQxVVjD

Domains may e.g. correspond to different acquisition devices, or
different ways they are configured/calibrated. ^n9cihrda

And we dont want our model to learn to classify a certain
domain on the expense of another one ^MEdtqgo0

Simple Approach
for one layer NN ^yd7R5NUL

We can try to "combine" both domains
on average by telling the error model
to minimize such that both domains produce
the same output on average ^DSsYLIcC

Moment Matching ^nhg3viss

can also be enhanced to
include variance ^AF4S1EUo

normal
error ^RTFHAMZu

scaling
factor ^1Q0C1014

distance between
point x as if it belonged to
each group at a time ^V1qDERQ6

There are more advanced techniques that improve
upon this with Wasserstein distance ^RX4Xse0G

Domain Critic ^1kHAJ5qG

We can create a neural network with two objective functions that compete
with each other in order to achieve minimum error.
First we start by mapping the data to some feature space with a feature extractor
this helps us make a representation of the data that we want.


On one hand we have a normal NN classifier (whether is regression or classification)
that is trying to minimize the prediction loss using the representation of the data.


on the other hand we have a Domain critic which adjusts the representation of the data
but meassuring the distance between the two domains, if the distance is large, the error
that this critic produces is too. The main point of this domain is to create a representation
of the data that not only does it keep the prediction at a minimum but also has the smallest
distance between both domains (Using the triangle inequality)


Note: This usually requires having the true distribution of one class in order to understand each
domain, which for labeled data is quite hard to get, but we can use nonlabeled data which is
a lot more common in order to infer the true distribution.
Our classifier will predict our unlabeled data distribution (Called the inferred distribution)



and a fraction of it alongside the dataset distribution will contribute to the real distribution ^V2quCxv8

Spurious Correlations ^Wa2qZG9U

Artefact of the distribution of available data (P) where one or several
task-irrelevant input variables are spuriously correlated to the
task-relevant variables

The model in this case is technically able to classify the classes correctly, using the correct
or spurious features. But it does not know which feature is actually correct and which is spurious
rendering it reliant on both, which results in the model mis-classifying the data if we use images
from the deal world where that artefact will not exist. ^too8yG3L

Well what
do we do? ^Y9yS7g3N

Its quite hard to detect this with model statistics as everything bahaves quite normal
within our dataset due to its bias.
One thing we can do is manually generate heatmaps on the weight of aretfacts of importance in the picture.
By generating heatmaps we can see which features play a major role into the decision and whether
they make sense or not. ^UnDEwLr8

Any solutions? ^DjuUcOWK

1) Crop the feature out pre-training such that your dataset is no longer biased
2) actively look for neurons that respond to that tag and manually kill them
3) Manually photoshop all the aretfacts out with random noise to avoid making a new one
4) add the artefacts to all classes such that it is no longer relevant
5) include an extra term in the objective that penalizes terms that are based off of this artefact ^opafK4B6

Worst case Analysis ^y3FnoEK5

In some cases, one big error can often be more harmful than many small errors.
Thus we compromise our model to not be so perfect (making very minor amount of error) for one
that makes more mistakes but only on the smaller scale. ^P25kv4wC

This is especially relevant to protect against adversarial attacks
craft inputs that steer the ML system towards the
worst-case decision behavior ^J95T8a81

So what causes large errors?
Typically they're either cause by:

1) high dimensionality of the data allows for the NN to craft some very specific patterns it
reacts highly to, some of those patterns might coincidentally appear in a random image

2) High depth/nonlinearity implies that the function is locally steeper than
necessary ^gbwhofzd

Very minor perturbations that are non-noticeable to the human eye can cause mis-classification
of images in NN without a trace, and this is especially dangerous in certain fields ^kzutc5o9

What can we do
about this? ^FEi9UAoM

Enhanced Regularization

1) Search for high local variations of the decision function and add these variations as a term of the error function to minimize

2) In practice, this can take the form of generating adversarial examples, and forcing them to be predicted in the same way as the original data

3) More generic approaches based on Lipschitz-continuity (e.g. spectral norm regularization) can also be used

4) In practice, one can also address worst-case behavior by applying dimensionality reduction (e.g. blurring images) before applying the neural network ^Kuq2D8eH

Predictive uncertainty ^0IX7JKFr

It is often useful to know when we can trust our model and when we should take the result
with a grain of salt. We can implement a way to output our "confidence" of the prediction. ^Iur16cIm

Approach 1 ^EI5G3A1g

In regression based models, Explicitly encoding
the uncertainty estimate in the neural network, i.e.
have one output neuron for predicting the actual value of interest, and
a second output neuron for predicting the uncertainty associated to
this prediction. The user can then know that the prediction is
a number out of a gaussian distribution built from the outputs
the more variance the less confidence. ^57YyBpD2

Approach 2 ^bJhb15Fe

Train an ensemble of neural networks and measure prediction
uncertainty as the discrepancy of predictions of each network in the
ensemble.
at the end we reach a distribution with the mean representing the avg
of the ensemble and the variance is the standard deviation! ^JMiV1u9O

Each model can have diff initialization, different subsets of data, and different feature inputs
which can make us understand the effects of these values on the prediction
The more heterogeneous the ensemble, the higher the estimate of uncertainty. ^x4KC1FXo

The objective has a gradient w.r.t the mean and variance
if we set sigma to a constant we are back at the squared
error loss, but having it is whats providing us the uncertainty
term
If we choose different data distributions,
we recover different lossfunctions ^dSZXQesk

Prior knowledge ^ULXRPzRy

We dont need the model to learn things that we already know, instead we should incorporate it in our prediction! ^C8dIbrz5

Remove features in the dataset that do not contribute to the prediction!
that way the model does not have to build a relation that has those features ^7V4jYpd5

for example, for rotation/translation invariance in images

this can be counteracted by pre-processing our data and randomly rotating
or translating some images.
Another solution would be for atoms is to encode distances instead of coordinates of molecules.
add noise and distortions to the data such that its not shaped perfectly anymore ^LGOUfHwW

Transfer learning ^snA5GDpX

If your model has barely in data, but shares very basic features with something that may
have a lot more data, then perhaps its better to train the first few layers of our network
on the general data but when we get into details we actually apply it to our original dataset ^5pVKZn0K

train on abundant
data ^O1dTCcHi

retrain on 
original task data ^zhPO2vUz

If we minimize the distance between the inferred distributions by representing them in a way
that there is no difference between the domains
+
minimize the distance between domain Q and its true distribution (by predicting correctly)
+
minimize the distance between domain P and its true distribution (by predicting correctly)
=
We minimize the distance between the true domains P and Q such that our model is invariant to them! ^GkBdcfmh


# Embedded files
80a04926262db12dab7c9e5898fa1a667885bbf3: [[Pasted Image 20240107154053_357.png]]
2e9e546ddb697144430d5b56ba85a9dc6353dd0c: [[Pasted Image 20240107154138_371.png]]
6360f3b66543c8b9a276321520a17e1ac400db23: [[Pasted Image 20240107154308_398.png]]
26cf177774c13ed8cabaf34d13849d67af041492: [[Pasted Image 20240107155307_526.png]]
244b1cd24c8adac9844b872ba031c2e861aa483a: [[Pasted Image 20240107160522_713.png]]
0fdc80e774a62a845dfaea0b8b417ed27861b2f9: [[Pasted Image 20240107160958_787.png]]
5ed62ecb832b5a40d3dc008ce7c8dd81bfa9c1ca: [[Pasted Image 20240107161511_872.png]]
548f46234a29dc6f56d1a49c0154d00f1c6b472c: [[Pasted Image 20240107162117_991.png]]
38323ce16eb37fb8af0fb4a75a52cd3532118c8d: [[Pasted Image 20240107162346_054.png]]
ab7de493ef823794c1f16b9cebb7a31e5bf4ff0f: [[Pasted Image 20240107162829_134.png]]
750d80275d885495d45c520babdb41e25f504387: [[Pasted Image 20240107163418_199.png]]
652f08ba71960bbeec186afda56104abafd6485d: [[Pasted Image 20240107163434_211.png]]
2719b7dc93f1a4ca35cbe860d717d5d5d47c2402: [[Pasted Image 20240107181438_006.png]]
566f13643e27fa4a452e2b9d336ede15324484e4: [[Pasted Image 20240107193129_878.png]]
38f54407e60769df37e516529c78f2a1e14a59af: [[Pasted Image 20240107193627_932.png]]
2cdd84d5233cbe3e69a0790b3cb0c775b6671d09: [[Pasted Image 20240107194230_003.png]]
6822a80ae10b868e0f9aa54e70b21ada06f581f1: [[Pasted Image 20240107194731_042.png]]
cd1d976756a25b5fcbb6325c368f871a36455e7a: [[Pasted Image 20240107195946_601.png]]
b1fae05270cc9149254934120f48156dc656ba3d: [[Pasted Image 20240212172216_682.png]]
c99652a216ca3f7a65759d66c01cccddde3c1df2: [[Pasted Image 20240212172246_698.png]]
b57d88f59b8bcc44e21c20627905c316c694dc7a: [[Pasted Image 20240212172419_715.png]]
d59696b75add2c6287b54f5515b97221d1f84427: [[Pasted Image 20240212172722_735.png]]
6a7de7bfb9ec25ec9f48205d373c2d8c52f7a93a: [[Pasted Image 20240212172837_740.png]]
70fd0deef588f16e890e4e0c40a2996281e95b15: [[Pasted Image 20240212173024_773.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.18",
	"elements": [
		{
			"type": "image",
			"version": 286,
			"versionNonce": 1792366876,
			"isDeleted": false,
			"id": "uWYOlRIrYcq-JQNbNYSxA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1012.3259196960855,
			"y": 2263.5554472715976,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 497.63438029223073,
			"height": 49.667922793082525,
			"seed": 1247783332,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755566662,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6a7de7bfb9ec25ec9f48205d373c2d8c52f7a93a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 1869,
			"versionNonce": 1436863140,
			"isDeleted": false,
			"id": "V2quCxv8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 775.7476328240236,
			"y": 1892.1558170456042,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 967.1790161132812,
			"height": 625,
			"seed": 2006317849,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "fg7bSnOGXJf7dhheEFPAU",
					"type": "arrow"
				}
			],
			"updated": 1707755555367,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can create a neural network with two objective functions that compete\nwith each other in order to achieve minimum error.\nFirst we start by mapping the data to some feature space with a feature extractor\nthis helps us make a representation of the data that we want.\n\n\nOn one hand we have a normal NN classifier (whether is regression or classification)\nthat is trying to minimize the prediction loss using the representation of the data.\n\n\non the other hand we have a Domain critic which adjusts the representation of the data\nbut meassuring the distance between the two domains, if the distance is large, the error\nthat this critic produces is too. The main point of this domain is to create a representation\nof the data that not only does it keep the prediction at a minimum but also has the smallest\ndistance between both domains (Using the triangle inequality)\n\n\nNote: This usually requires having the true distribution of one class in order to understand each\ndomain, which for labeled data is quite hard to get, but we can use nonlabeled data which is\na lot more common in order to infer the true distribution.\nOur classifier will predict our unlabeled data distribution (Called the inferred distribution)\n\n\n\nand a fraction of it alongside the dataset distribution will contribute to the real distribution",
			"rawText": "We can create a neural network with two objective functions that compete\nwith each other in order to achieve minimum error.\nFirst we start by mapping the data to some feature space with a feature extractor\nthis helps us make a representation of the data that we want.\n\n\nOn one hand we have a normal NN classifier (whether is regression or classification)\nthat is trying to minimize the prediction loss using the representation of the data.\n\n\non the other hand we have a Domain critic which adjusts the representation of the data\nbut meassuring the distance between the two domains, if the distance is large, the error\nthat this critic produces is too. The main point of this domain is to create a representation\nof the data that not only does it keep the prediction at a minimum but also has the smallest\ndistance between both domains (Using the triangle inequality)\n\n\nNote: This usually requires having the true distribution of one class in order to understand each\ndomain, which for labeled data is quite hard to get, but we can use nonlabeled data which is\na lot more common in order to infer the true distribution.\nOur classifier will predict our unlabeled data distribution (Called the inferred distribution)\n\n\n\nand a fraction of it alongside the dataset distribution will contribute to the real distribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can create a neural network with two objective functions that compete\nwith each other in order to achieve minimum error.\nFirst we start by mapping the data to some feature space with a feature extractor\nthis helps us make a representation of the data that we want.\n\n\nOn one hand we have a normal NN classifier (whether is regression or classification)\nthat is trying to minimize the prediction loss using the representation of the data.\n\n\non the other hand we have a Domain critic which adjusts the representation of the data\nbut meassuring the distance between the two domains, if the distance is large, the error\nthat this critic produces is too. The main point of this domain is to create a representation\nof the data that not only does it keep the prediction at a minimum but also has the smallest\ndistance between both domains (Using the triangle inequality)\n\n\nNote: This usually requires having the true distribution of one class in order to understand each\ndomain, which for labeled data is quite hard to get, but we can use nonlabeled data which is\na lot more common in order to infer the true distribution.\nOur classifier will predict our unlabeled data distribution (Called the inferred distribution)\n\n\n\nand a fraction of it alongside the dataset distribution will contribute to the real distribution",
			"lineHeight": 1.25,
			"baseline": 618
		},
		{
			"type": "image",
			"version": 315,
			"versionNonce": 1883111324,
			"isDeleted": false,
			"id": "qoNFj1JWuK0QKqbdAcwOv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1862.9172338053722,
			"y": 2221.958718780947,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 820.0707570165058,
			"height": 300.57678170308367,
			"seed": 1656497188,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755841623,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "70fd0deef588f16e890e4e0c40a2996281e95b15",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 89,
			"versionNonce": 1803709348,
			"isDeleted": false,
			"id": "yu9D8qAUsWdu6lhNOsmyz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -230.09730762793902,
			"y": -24.69242796979296,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 479.44428917262064,
			"height": 271.7371541238958,
			"seed": 851916249,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547112,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6360f3b66543c8b9a276321520a17e1ac400db23",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 99,
			"versionNonce": 1424396444,
			"isDeleted": false,
			"id": "hRLQ5wkE-P4NY6B6y2Vx2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -231.75,
			"y": -419.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 470,
			"height": 145,
			"seed": 209932761,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "gAuzuRO3"
				}
			],
			"updated": 1707755547113,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 20,
			"versionNonce": 1056790308,
			"isDeleted": false,
			"id": "gAuzuRO3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -93.75849537327227,
			"y": -364.0230541360247,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 193.6768035888672,
			"height": 35,
			"seed": 1826269305,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Regularization",
			"rawText": "Regularization",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "hRLQ5wkE-P4NY6B6y2Vx2",
			"originalText": "Regularization",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 689,
			"versionNonce": 998382876,
			"isDeleted": false,
			"id": "jcrh7ipp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -391.45312740391853,
			"y": -262.7064344727952,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 778.9992065429688,
			"height": 200,
			"seed": 2067173881,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This note emphasizes on the importance of data and training\non that data such that our model is applicable to the real\nworld data.\nMore often than not, we find our models really good at predicting \ndatapoints it has already seen before (training data), but it will reach\na point trying too hard to fit solutions that exactly match the training data\nthat it diverges from giving a general solution to the overall problem,\nmaking it bad at predicting datapoints it has never seen before.",
			"rawText": "This note emphasizes on the importance of data and training\non that data such that our model is applicable to the real\nworld data.\nMore often than not, we find our models really good at predicting \ndatapoints it has already seen before (training data), but it will reach\na point trying too hard to fit solutions that exactly match the training data\nthat it diverges from giving a general solution to the overall problem,\nmaking it bad at predicting datapoints it has never seen before.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This note emphasizes on the importance of data and training\non that data such that our model is applicable to the real\nworld data.\nMore often than not, we find our models really good at predicting \ndatapoints it has already seen before (training data), but it will reach\na point trying too hard to fit solutions that exactly match the training data\nthat it diverges from giving a general solution to the overall problem,\nmaking it bad at predicting datapoints it has never seen before.",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "line",
			"version": 288,
			"versionNonce": 1259262628,
			"isDeleted": false,
			"id": "3GpKuP4Cg6D5ecXkaZGj8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 172.75375068835672,
			"y": 99.4607278447296,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 200.15603369631674,
			"height": 126.93201666187065,
			"seed": 274853401,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					67.13645182756329,
					44.80929219160879
				],
				[
					126.57427068791822,
					-82.12272447026186
				],
				[
					200.15603369631674,
					-43.64231816317016
				]
			]
		},
		{
			"type": "line",
			"version": 315,
			"versionNonce": 1341659548,
			"isDeleted": false,
			"id": "E_h7IBDiyDtjGkOEZeprE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -120.97387888665389,
			"y": 56.55059279536982,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 242.7647638112643,
			"height": 98.73641513219332,
			"seed": 1540098105,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-109.21500828905289,
					17.356013257535807
				],
				[
					-203.81370096094952,
					-45.29193354687766
				],
				[
					-242.7647638112643,
					53.44448158531566
				]
			]
		},
		{
			"type": "image",
			"version": 194,
			"versionNonce": 1583668772,
			"isDeleted": false,
			"id": "Lhbuf0H6bkSpelitcoyNG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -562.8101919372921,
			"y": 139.64586126597123,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 276.7607165731154,
			"height": 61.923630648779245,
			"seed": 1677204665,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "80a04926262db12dab7c9e5898fa1a667885bbf3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 131,
			"versionNonce": 1299875356,
			"isDeleted": false,
			"id": "11HP8S49",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -489.26808154079276,
			"y": 107.27755836787281,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 133.2998504638672,
			"height": 25,
			"seed": 2025394937,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Training error",
			"rawText": "Training error",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Training error",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 127,
			"versionNonce": 1106082212,
			"isDeleted": false,
			"id": "T61Yixg2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 360.8716068994953,
			"y": 67.54290170696544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 104.79988098144531,
			"height": 25,
			"seed": 1702698073,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "True error",
			"rawText": "True error",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "True error",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 182,
			"versionNonce": 955998876,
			"isDeleted": false,
			"id": "5agJMroUr3vzv7ahOtCkW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 264.14734803085094,
			"y": 98.61269771927776,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 320.8943654921728,
			"height": 46.16375082518978,
			"seed": 1105154103,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2e9e546ddb697144430d5b56ba85a9dc6353dd0c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 145,
			"versionNonce": 1893115172,
			"isDeleted": false,
			"id": "GvWSUIEO2-Naw1-Jrq1qB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 507.5413656259136,
			"y": 146.75321530906592,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 138.17731261616666,
			"height": 30.77057801956653,
			"seed": 1785630423,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					35.41519356968979,
					30.77057801956653
				],
				[
					138.17731261616666,
					12.772692762838915
				]
			]
		},
		{
			"type": "text",
			"version": 238,
			"versionNonce": 690794268,
			"isDeleted": false,
			"id": "Z2NjEUJe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 606.8439281406028,
			"y": 136.480522546227,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 290.24066162109375,
			"height": 80,
			"seed": 432148537,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "the true probability distribution from\nwhich the data is coming,\nwhich is unknown making the true\nerror hard to minimize",
			"rawText": "the true probability distribution from\nwhich the data is coming,\nwhich is unknown making the true\nerror hard to minimize",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the true probability distribution from\nwhich the data is coming,\nwhich is unknown making the true\nerror hard to minimize",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 173,
			"versionNonce": 1351508132,
			"isDeleted": false,
			"id": "druYSTwG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -278.66800769951294,
			"y": 233.6542355045496,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 548.21435546875,
			"height": 105,
			"seed": 1339750647,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "So what makes the dataset we have\nnot be able to fully represent the true\ndistribution?",
			"rawText": "So what makes the dataset we have\nnot be able to fully represent the true\ndistribution?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "So what makes the dataset we have\nnot be able to fully represent the true\ndistribution?",
			"lineHeight": 1.25,
			"baseline": 95
		},
		{
			"type": "text",
			"version": 97,
			"versionNonce": 243297180,
			"isDeleted": false,
			"id": "u5sUn9R4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -685.347271613634,
			"y": 437.81560152427863,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 362.0595703125,
			"height": 125,
			"seed": 1540794391,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Finite Data:\nThe fact the dataset is composed\nof few data points drawn randomly\nfrom the underlying data distribution\n",
			"rawText": "Finite Data:\nThe fact the dataset is composed\nof few data points drawn randomly\nfrom the underlying data distribution\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Finite Data:\nThe fact the dataset is composed\nof few data points drawn randomly\nfrom the underlying data distribution\n",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 1757588516,
			"isDeleted": false,
			"id": "ZOHm2JC4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -203.44330068295093,
			"y": 450.3156019082261,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 402.97955322265625,
			"height": 100,
			"seed": 1123646711,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Dataset bias:\nThe fact that the dataset may\nover-represent certain parts of the\nunderlying distribution due to randomness",
			"rawText": "Dataset bias:\nThe fact that the dataset may\nover-represent certain parts of the\nunderlying distribution due to randomness",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Dataset bias:\nThe fact that the dataset may\nover-represent certain parts of the\nunderlying distribution due to randomness",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 182,
			"versionNonce": 2066257948,
			"isDeleted": false,
			"id": "7gStXyzB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 319.3806525841689,
			"y": 450.31560181011713,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 381.69952392578125,
			"height": 100,
			"seed": 1963625017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "cF8rHBSOHwLfQyuj4U_4o",
					"type": "arrow"
				}
			],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Distribution shift:\nThe fact that the dataset may have\nbeen generated from an underlying\ndistribution that is now obsolete",
			"rawText": "Distribution shift:\nThe fact that the dataset may have\nbeen generated from an underlying\ndistribution that is now obsolete",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Distribution shift:\nThe fact that the dataset may have\nbeen generated from an underlying\ndistribution that is now obsolete",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 70,
			"versionNonce": 459376548,
			"isDeleted": false,
			"id": "wCw1OPmO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -171.38800075149857,
			"y": 568.4083252496715,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 344.8967590332031,
			"height": 20,
			"seed": 1566774647,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Image and text data may suffer from this",
			"rawText": "Image and text data may suffer from this",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Image and text data may suffer from this",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 48,
			"versionNonce": 1796682908,
			"isDeleted": false,
			"id": "XkLB1sil",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 375.2701179724759,
			"y": 568.4083247220443,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 269.92059326171875,
			"height": 20,
			"seed": 319805785,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Sensor data may suffer from this",
			"rawText": "Sensor data may suffer from this",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sensor data may suffer from this",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 127,
			"versionNonce": 1553527588,
			"isDeleted": false,
			"id": "R2SlTmqa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -111.10576128473825,
			"y": 606.5010478611789,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 218.30447387695312,
			"height": 20,
			"seed": 720132343,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "games may suffer from this",
			"rawText": "games may suffer from this",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "games may suffer from this",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 101,
			"versionNonce": 201212188,
			"isDeleted": false,
			"id": "7IT443Zj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -650.677807062797,
			"y": 568.4083254165758,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 292.72064208984375,
			"height": 20,
			"seed": 1661949751,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "simulated data may suffer from this",
			"rawText": "simulated data may suffer from this",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "simulated data may suffer from this",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 86,
			"versionNonce": 1792470692,
			"isDeleted": false,
			"id": "dQXb31S5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -641.2857786704656,
			"y": 606.5010479456299,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 273.93658447265625,
			"height": 20,
			"seed": 1194436281,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "medical data may suffer from this",
			"rawText": "medical data may suffer from this",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "medical data may suffer from this",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 211,
			"versionNonce": 89111964,
			"isDeleted": false,
			"id": "8MjI0CKa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 329.6540449475304,
			"y": 606.5010477784401,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 361.1527404785156,
			"height": 20,
			"seed": 1491157945,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "medical and social data may suffer from this",
			"rawText": "medical and social data may suffer from this",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "medical and social data may suffer from this",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 327,
			"versionNonce": 113867300,
			"isDeleted": false,
			"id": "NsYEGPtXcYht1d_JxAKa_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -505.4636115255272,
			"y": 661.4898679587545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 531.3037170195989,
			"height": 478.4834550651217,
			"seed": 1016582935,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547113,
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
					48.38756260033176,
					126.18717305576695
				],
				[
					-74.00450750638959,
					224.8598497309531
				],
				[
					-272.53142411066983,
					93.32994453146034
				],
				[
					-430.14533125925925,
					180.27908771135935
				],
				[
					-377.61274343003936,
					435.48806340298506
				],
				[
					-482.9161544192672,
					478.4834550651217
				]
			]
		},
		{
			"type": "text",
			"version": 139,
			"versionNonce": 1077783068,
			"isDeleted": false,
			"id": "SPGrJNax",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1189.9918764189424,
			"y": 1131.3464190928019,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 146.94461059570312,
			"height": 35,
			"seed": 1769689975,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Overfitting",
			"rawText": "Overfitting",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Overfitting",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 356,
			"versionNonce": 727618980,
			"isDeleted": false,
			"id": "I4j3ahWK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1427.2009538306365,
			"y": 1172.3547969239671,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 648.559326171875,
			"height": 125,
			"seed": 270752919,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ziZYlR_s-RM0lg3c4_9Om",
					"type": "arrow"
				}
			],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "When we have a finite and limited amount of data we \nfind ourselves struggling to represent the data distribution\nthe way we want to leading our model to focus on perfection of \nthe finite data and \"overfitting\" it causing it to generalize\nless for overall data",
			"rawText": "When we have a finite and limited amount of data we \nfind ourselves struggling to represent the data distribution\nthe way we want to leading our model to focus on perfection of \nthe finite data and \"overfitting\" it causing it to generalize\nless for overall data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "When we have a finite and limited amount of data we \nfind ourselves struggling to represent the data distribution\nthe way we want to leading our model to focus on perfection of \nthe finite data and \"overfitting\" it causing it to generalize\nless for overall data",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 185,
			"versionNonce": 800720540,
			"isDeleted": false,
			"id": "afXeI5af_ikpnfvQrMpgv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1292.8152856942922,
			"y": 1303.3631750403692,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 379.7879898389816,
			"height": 199.47467512888298,
			"seed": 1110540343,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "26cf177774c13ed8cabaf34d13849d67af041492",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 32,
			"versionNonce": 1170489636,
			"isDeleted": false,
			"id": "HilClwQpk03G2sYnjXcUG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1152.7515267746262,
			"y": 1465.776524303393,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#a5d8ff",
			"width": 19.48536491338359,
			"height": 14.072763548554803,
			"seed": 935482617,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.278617583201367,
					5.412601364828788
				],
				[
					19.48536491338359,
					-8.660162183726015
				]
			]
		},
		{
			"type": "line",
			"version": 26,
			"versionNonce": 410440476,
			"isDeleted": false,
			"id": "UOyVXqFOzZb2S_ZqCUdJl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -993.1880385394738,
			"y": 1443.0435985711124,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 11.041706784250778,
			"height": 13.42325138477554,
			"seed": 838745143,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					11.041706784250778,
					13.42325138477554
				]
			]
		},
		{
			"type": "line",
			"version": 47,
			"versionNonce": 1835564196,
			"isDeleted": false,
			"id": "netpI4MoT4AkauDejVuSW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -981.0638114822573,
			"y": 1442.8270945165193,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 11.907723002623356,
			"height": 12.990243275589137,
			"seed": 526455161,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547113,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.907723002623356,
					12.990243275589137
				]
			]
		},
		{
			"type": "arrow",
			"version": 113,
			"versionNonce": 1491472284,
			"isDeleted": false,
			"id": "6XihSR8va8HTVOqcDdCZu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -954.9005838213707,
			"y": 1420.1799062419338,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 102.16290563532289,
			"height": 35.869107934658814,
			"seed": 316758905,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547113,
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
					47.7187239487871,
					1.6012994613688534
				],
				[
					102.16290563532289,
					35.869107934658814
				]
			]
		},
		{
			"type": "text",
			"version": 244,
			"versionNonce": 469321764,
			"isDeleted": false,
			"id": "dRQM8ZQY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -989.8689059447483,
			"y": 1478.4051274975648,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 346.00067138671875,
			"height": 100,
			"seed": 634274841,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "one class or target value\nmay be locally predominant in our\ndataset in areas that the other class\nis more common in the real world\nwe do not want to teach this to our model",
			"rawText": "one class or target value\nmay be locally predominant in our\ndataset in areas that the other class\nis more common in the real world\nwe do not want to teach this to our model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "one class or target value\nmay be locally predominant in our\ndataset in areas that the other class\nis more common in the real world\nwe do not want to teach this to our model",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 90,
			"versionNonce": 825867292,
			"isDeleted": false,
			"id": "us1csCkBO20YLOLG253hS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1268.5454866536984,
			"y": 1426.8501637691666,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 86.6761179072846,
			"height": 111.7158853027222,
			"seed": 1290253367,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "TOQIGk6E",
				"focus": -0.019015249705232353,
				"gap": 14.124996992298065
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
					-80.2556647289673,
					50.72158010870726
				],
				[
					-86.6761179072846,
					111.7158853027222
				]
			]
		},
		{
			"type": "text",
			"version": 140,
			"versionNonce": 1701094308,
			"isDeleted": false,
			"id": "TOQIGk6E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1530.0820501771152,
			"y": 1552.6910460641868,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 347.1527099609375,
			"height": 60,
			"seed": 471977113,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "us1csCkBO20YLOLG253hS",
					"type": "arrow"
				}
			],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Although the model is much less complex\nit is often preferred over a complex one as\nlong as it classifies correctly",
			"rawText": "Although the model is much less complex\nit is often preferred over a complex one as\nlong as it classifies correctly",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Although the model is much less complex\nit is often preferred over a complex one as\nlong as it classifies correctly",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 81,
			"versionNonce": 191092892,
			"isDeleted": false,
			"id": "-2vM6JeEai725fl68ohXP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1108.433859138176,
			"y": 1539.038627024823,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.0296942681120527,
			"height": 190.49343960067768,
			"seed": 1006078263,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547114,
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
					-1.0296942681120527,
					190.49343960067768
				]
			]
		},
		{
			"type": "text",
			"version": 16,
			"versionNonce": 802721572,
			"isDeleted": false,
			"id": "xct4X5WU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1178.33437654153,
			"y": 1742.499491456462,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 138.85260009765625,
			"height": 35,
			"seed": 99311991,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": "[[SVM]]",
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "VC Theory",
			"rawText": "VC Theory",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "VC Theory",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 464,
			"versionNonce": 1125541148,
			"isDeleted": false,
			"id": "oq5rCSRF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1588.791384614673,
			"y": 1784.4068665690181,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 955.9590454101562,
			"height": 200,
			"seed": 442562135,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "uPPrVwG8kd7CHgjkuTVUH",
					"type": "arrow"
				},
				{
					"id": "QaEDXJk5tdY9xAIkfamws",
					"type": "arrow"
				}
			],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "According to VC theory, we have a few factors that make the\ngap between training error and the true error\n\n1) Increasing the amount of datapoints N (Which is our issue here)\n\n2) Reducing the model complexity/ VC dimension h (Which is our alternative)\n\nWe have previously used solution 2 in linear models, but can we do the same in neural networks?",
			"rawText": "According to VC theory, we have a few factors that make the\ngap between training error and the true error\n\n1) Increasing the amount of datapoints N (Which is our issue here)\n\n2) Reducing the model complexity/ VC dimension h (Which is our alternative)\n\nWe have previously used solution 2 in linear models, but can we do the same in neural networks?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "According to VC theory, we have a few factors that make the\ngap between training error and the true error\n\n1) Increasing the amount of datapoints N (Which is our issue here)\n\n2) Reducing the model complexity/ VC dimension h (Which is our alternative)\n\nWe have previously used solution 2 in linear models, but can we do the same in neural networks?",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "arrow",
			"version": 218,
			"versionNonce": 1807944356,
			"isDeleted": false,
			"id": "kOYdKoTOUETgwDemZPHsz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1119.6700497654056,
			"y": 2018.139194368032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 5.482184200384381,
			"height": 187.49069965315357,
			"seed": 653875543,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547114,
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
					5.482184200384381,
					187.49069965315357
				]
			]
		},
		{
			"type": "text",
			"version": 207,
			"versionNonce": 1841521052,
			"isDeleted": false,
			"id": "SQ8q1XSf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1244.6595579249063,
			"y": 2223.655067662801,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 265.3291320800781,
			"height": 35,
			"seed": 1235386903,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Feature extraction",
			"rawText": "Feature extraction",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Feature extraction",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 467,
			"versionNonce": 1272059428,
			"isDeleted": false,
			"id": "rEsEBSdP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1448.060939399767,
			"y": 2263.662031723085,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 669.4193115234375,
			"height": 75,
			"seed": 876990199,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can extract the most representative features from our data,\nwhether its manually or methods like PCA, then we proceed to train\nour model on this low dimensional data.",
			"rawText": "We can extract the most representative features from our data,\nwhether its manually or methods like PCA, then we proceed to train\nour model on this low dimensional data.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can extract the most representative features from our data,\nwhether its manually or methods like PCA, then we proceed to train\nour model on this low dimensional data.",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 580701724,
			"isDeleted": false,
			"id": "3kqHQVHL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1311.6076825487953,
			"y": 2344.168555700874,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 420.5289001464844,
			"height": 40,
			"seed": 1180320601,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "this is often helpful in noisy data but can sometimes\nbe harmful and ends up deleting class relevant data",
			"rawText": "this is often helpful in noisy data but can sometimes\nbe harmful and ends up deleting class relevant data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "this is often helpful in noisy data but can sometimes\nbe harmful and ends up deleting class relevant data",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 60,
			"versionNonce": 2096345508,
			"isDeleted": false,
			"id": "uPPrVwG8kd7CHgjkuTVUH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1450.2408128209822,
			"y": 2009.7722339205557,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 192.18827303467447,
			"height": 142.44542589628782,
			"seed": 401418999,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oq5rCSRF",
				"focus": 0.27783514034286866,
				"gap": 25.365367351537543
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
					-192.18827303467447,
					142.44542589628782
				]
			]
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 1117039260,
			"isDeleted": false,
			"id": "FsJiZbGU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2009.3771132488882,
			"y": 2137.9345442979725,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 265.861083984375,
			"height": 35,
			"seed": 2065483223,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Reducing Sensitivity",
			"rawText": "Reducing Sensitivity",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Reducing Sensitivity",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 93,
			"versionNonce": 1582685476,
			"isDeleted": false,
			"id": "ZoEFip9Q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2103.8388895765856,
			"y": 2174.3328115102763,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 473.37945556640625,
			"height": 75,
			"seed": 1825148793,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Decaying weights by including in the objective\na term that makes the weights tend to zero if\nthey are not necessary for the prediction task",
			"rawText": "Decaying weights by including in the objective\na term that makes the weights tend to zero if\nthey are not necessary for the prediction task",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Decaying weights by including in the objective\na term that makes the weights tend to zero if\nthey are not necessary for the prediction task",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 120,
			"versionNonce": 1079834396,
			"isDeleted": false,
			"id": "dDIj1B8TuePyo1kKaOMVB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2027.8046951039355,
			"y": 2255.658828428962,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 335.14473260110145,
			"height": 76.36209097240287,
			"seed": 526395671,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "244b1cd24c8adac9844b872ba031c2e861aa483a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 963025060,
			"isDeleted": false,
			"id": "UC03YsX7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2135.97499498527,
			"y": 2329.3150665143758,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 537.2650146484375,
			"height": 40,
			"seed": 499164759,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "KvGYWFik4Wqy_bwWRIxgM",
					"type": "arrow"
				}
			],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "the higher the parameter λ, the more the exposure of the model to\nvariations in the input domain is being reduced",
			"rawText": "the higher the parameter λ, the more the exposure of the model to\nvariations in the input domain is being reduced",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the higher the parameter λ, the more the exposure of the model to\nvariations in the input domain is being reduced",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 77,
			"versionNonce": 1751626652,
			"isDeleted": false,
			"id": "KvGYWFik4Wqy_bwWRIxgM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1865.414960548288,
			"y": 2384.8783261247313,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.451152904574883,
			"height": 112.46435010456253,
			"seed": 1802806713,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "UC03YsX7",
				"focus": -0.005461873704033151,
				"gap": 15.563259610355544
			},
			"endBinding": {
				"elementId": "IOXdw3oV",
				"focus": -0.03220576195960786,
				"gap": 12.816140664049726
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
					1.451152904574883,
					112.46435010456253
				]
			]
		},
		{
			"type": "text",
			"version": 48,
			"versionNonce": 2043929636,
			"isDeleted": false,
			"id": "rRkRIovB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1854.688479086625,
			"y": 2413.9013842162312,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 113.50425720214844,
			"height": 20,
			"seed": 128956663,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "an alternative",
			"rawText": "an alternative",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "an alternative",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 45,
			"versionNonce": 686219292,
			"isDeleted": false,
			"id": "IOXdw3oV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1917.00331821605,
			"y": 2510.1588168933436,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 110.43247985839844,
			"height": 35,
			"seed": 492043863,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "KvGYWFik4Wqy_bwWRIxgM",
					"type": "arrow"
				}
			],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Dropout",
			"rawText": "Dropout",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Dropout",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 297,
			"versionNonce": 1703657380,
			"isDeleted": false,
			"id": "vufZSiDT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2149.3202245005737,
			"y": 2545.7191930345193,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 566.359375,
			"height": 175,
			"seed": 1809506233,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Dropout consists of adding artificial multiplicative noise\nto the input and intermediate neurons, and training\nthe model subject to that noise.\nThis is achieved by inserting layers between hidden layers\nthat include a dropout term that multiplies its input\nby some random noise, often drawn from a bernouli\ndistribution",
			"rawText": "Dropout consists of adding artificial multiplicative noise\nto the input and intermediate neurons, and training\nthe model subject to that noise.\nThis is achieved by inserting layers between hidden layers\nthat include a dropout term that multiplies its input\nby some random noise, often drawn from a bernouli\ndistribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Dropout consists of adding artificial multiplicative noise\nto the input and intermediate neurons, and training\nthe model subject to that noise.\nThis is achieved by inserting layers between hidden layers\nthat include a dropout term that multiplies its input\nby some random noise, often drawn from a bernouli\ndistribution",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "image",
			"version": 147,
			"versionNonce": 1506573468,
			"isDeleted": false,
			"id": "nuuVzgHn8OSlttQXCpo8C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2010.5318858593976,
			"y": 2735.814761821406,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 362.79149616894256,
			"height": 157.2096483398751,
			"seed": 874276473,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0fdc80e774a62a845dfaea0b8b417ed27861b2f9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 70,
			"versionNonce": 1421617956,
			"isDeleted": false,
			"id": "oxcFgnQvsZIUEdGjW3JRE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1927.0889589927226,
			"y": 2803.5359390946187,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 137.85952593462457,
			"height": 44.98574004182501,
			"seed": 2033335895,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-92.87378589279979,
					-44.98574004182501
				],
				[
					-137.85952593462457,
					-14.51152904574974
				]
			]
		},
		{
			"type": "text",
			"version": 270,
			"versionNonce": 80382236,
			"isDeleted": false,
			"id": "BNJo3AXQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2402.0290731876,
			"y": 2793.701139405731,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 434.720947265625,
			"height": 120,
			"seed": 1868163033,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This noise basically makes\nsome neurons die out in certain\npredictions which reduces the amount\nof features the model takes into account\nwhile classifying\nIn image classification this is superior to weight decay",
			"rawText": "This noise basically makes\nsome neurons die out in certain\npredictions which reduces the amount\nof features the model takes into account\nwhile classifying\nIn image classification this is superior to weight decay",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This noise basically makes\nsome neurons die out in certain\npredictions which reduces the amount\nof features the model takes into account\nwhile classifying\nIn image classification this is superior to weight decay",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "arrow",
			"version": 77,
			"versionNonce": 1775445668,
			"isDeleted": false,
			"id": "X8TiZyXurdnvaInqXhh1s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -769.4678765070028,
			"y": 2030.8599251454375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 226.81462306396543,
			"height": 121.42601032717312,
			"seed": 176853913,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547114,
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
					226.81462306396543,
					121.42601032717312
				]
			]
		},
		{
			"type": "text",
			"version": 107,
			"versionNonce": 760415644,
			"isDeleted": false,
			"id": "8ux7oyqG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -511.9750454791941,
			"y": 2132.1683456207384,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 429.5498046875,
			"height": 35,
			"seed": 131987641,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Choosing appropriate complexity",
			"rawText": "Choosing appropriate complexity",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Choosing appropriate complexity",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 223,
			"versionNonce": 1233039908,
			"isDeleted": false,
			"id": "FNVmhIsW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -642.4188036247899,
			"y": 2173.008868506937,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 712.4591674804688,
			"height": 75,
			"seed": 721620183,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "often when choosing a model we want a balance of a model\nclassifying data correctly but also not being overly complex, but how do\nwe know what to prioritize more, and which to choose?",
			"rawText": "often when choosing a model we want a balance of a model\nclassifying data correctly but also not being overly complex, but how do\nwe know what to prioritize more, and which to choose?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "often when choosing a model we want a balance of a model\nclassifying data correctly but also not being overly complex, but how do\nwe know what to prioritize more, and which to choose?",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 39,
			"versionNonce": 412611100,
			"isDeleted": false,
			"id": "xK3dhFsYCBghBQmoBK1BG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -305.65307550283103,
			"y": 2271.682427321087,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0,
			"height": 88.29101397058594,
			"seed": 611731671,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547114,
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
					0,
					88.29101397058594
				]
			]
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 1387056548,
			"isDeleted": false,
			"id": "pBlZe4uH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -354.5449149671014,
			"y": 2376.3147327640413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 101.47244262695312,
			"height": 35,
			"seed": 1253160505,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Holdout",
			"rawText": "Holdout",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Holdout",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 144,
			"versionNonce": 361451164,
			"isDeleted": false,
			"id": "HAG1R7db",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -620.9147797079904,
			"y": 2416.2828861564653,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 634.979248046875,
			"height": 50,
			"seed": 487094807,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Train many different models using different regularization terms\nand pick out the best performing one",
			"rawText": "Train many different models using different regularization terms\nand pick out the best performing one",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Train many different models using different regularization terms\nand pick out the best performing one",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 107,
			"versionNonce": 1451981092,
			"isDeleted": false,
			"id": "MKDSckwwddwYyOcGwJ3TO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -610.7819228114378,
			"y": 2483.430918280119,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 639.3734429291404,
			"height": 196.96927250586737,
			"seed": 1424482615,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "JOJMngYamzlzGZ4ayME0H",
					"type": "arrow"
				},
				{
					"id": "-2JEujXdCzA7OPWXptEKI",
					"type": "arrow"
				}
			],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5ed62ecb832b5a40d3dc008ce7c8dd81bfa9c1ca",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 229,
			"versionNonce": 1155472156,
			"isDeleted": false,
			"id": "JOJMngYamzlzGZ4ayME0H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -18.576550829361963,
			"y": 2547.310094700261,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 130.7641443713735,
			"height": 1.90896561126101,
			"seed": 255499671,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547114,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8fRy3Ium",
				"focus": -1.2300077577165844,
				"gap": 26.59687795148602
			},
			"endBinding": {
				"elementId": "jV8yv8FF",
				"focus": -1.2306725822416038,
				"gap": 8.645420993108019
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
					130.7641443713735,
					1.90896561126101
				]
			]
		},
		{
			"type": "text",
			"version": 114,
			"versionNonce": 1351136420,
			"isDeleted": false,
			"id": "jV8yv8FF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -58.71875716871,
			"y": 2490.573639318414,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 227.83973693847656,
			"height": 50,
			"seed": 320692759,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "JOJMngYamzlzGZ4ayME0H",
					"type": "arrow"
				}
			],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How do I find the best\nperforming one?",
			"rawText": "How do I find the best\nperforming one?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do I find the best\nperforming one?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 98,
			"versionNonce": 1627740060,
			"isDeleted": false,
			"id": "4jXmGQuH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 208.1917381654912,
			"y": 2533.3514170961907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 131.79652404785156,
			"height": 35,
			"seed": 1178804217,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Validation",
			"rawText": "Validation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Validation",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 384,
			"versionNonce": 508723236,
			"isDeleted": false,
			"id": "8fRy3Ium",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5.628092908601047,
			"y": 2573.906972651747,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 552.4793701171875,
			"height": 150,
			"seed": 1997858263,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "JOJMngYamzlzGZ4ayME0H",
					"type": "arrow"
				}
			],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "to simulate how your model will perform in\nthe real world, shard a small dataset from\nthe original dataset such that the model will never see\nand test it on that dataset after training\n\nHow do i pick the size of the dataset?",
			"rawText": "to simulate how your model will perform in\nthe real world, shard a small dataset from\nthe original dataset such that the model will never see\nand test it on that dataset after training\n\nHow do i pick the size of the dataset?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "to simulate how your model will perform in\nthe real world, shard a small dataset from\nthe original dataset such that the model will never see\nand test it on that dataset after training\n\nHow do i pick the size of the dataset?",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 103810076,
			"isDeleted": false,
			"id": "qADEqQ8V",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 109.52574373325376,
			"y": 2738.351417096191,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 340.2396240234375,
			"height": 25,
			"seed": 1348865593,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": "[[Model Selection]]",
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "More about this in validation note",
			"rawText": "More about this in validation note",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "More about this in validation note",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 72,
			"versionNonce": 936827812,
			"isDeleted": false,
			"id": "-2JEujXdCzA7OPWXptEKI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -312.85924028456856,
			"y": 2699.1208351034197,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 3.980027215802636,
			"height": 167.6143377187882,
			"seed": 1600558233,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "MKDSckwwddwYyOcGwJ3TO",
				"focus": 0.07622723795943902,
				"gap": 18.720644317433198
			},
			"endBinding": {
				"elementId": "Xkl3JmZ8",
				"focus": -0.002323839963375376,
				"gap": 14.456355665519823
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
					3.980027215802636,
					167.6143377187882
				]
			]
		},
		{
			"type": "text",
			"version": 85,
			"versionNonce": 2052137116,
			"isDeleted": false,
			"id": "MbUuNcEc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -292.29463461302515,
			"y": 2740.3686883353903,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 154.60833740234375,
			"height": 60,
			"seed": 1927962263,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is quite costly\nfor bigger models\ncan we improve?",
			"rawText": "This is quite costly\nfor bigger models\ncan we improve?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is quite costly\nfor bigger models\ncan we improve?",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 66,
			"versionNonce": 1732495140,
			"isDeleted": false,
			"id": "Xkl3JmZ8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -403.629371245225,
			"y": 2881.1915284877277,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 191.4647979736328,
			"height": 35,
			"seed": 1051265687,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-2JEujXdCzA7OPWXptEKI",
					"type": "arrow"
				}
			],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Early stopping",
			"rawText": "Early stopping",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Early stopping",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 410,
			"versionNonce": 1964682524,
			"isDeleted": false,
			"id": "cQAHpDZD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -700.1268096114741,
			"y": 2920.158191963044,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 763.539306640625,
			"height": 150,
			"seed": 458370969,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Think of our procedure of training our model as a way to generate\ndifferent versions of our model per epoch.\nWe can use validation testing on our network per iteration and monitor\nwhen our model had the lowest error rate to keep in the background\nsuch that if it starts over-fitting we can just stop it and keep the minimum\nmodel",
			"rawText": "Think of our procedure of training our model as a way to generate\ndifferent versions of our model per epoch.\nWe can use validation testing on our network per iteration and monitor\nwhen our model had the lowest error rate to keep in the background\nsuch that if it starts over-fitting we can just stop it and keep the minimum\nmodel",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Think of our procedure of training our model as a way to generate\ndifferent versions of our model per epoch.\nWe can use validation testing on our network per iteration and monitor\nwhen our model had the lowest error rate to keep in the background\nsuch that if it starts over-fitting we can just stop it and keep the minimum\nmodel",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 96,
			"versionNonce": 17253028,
			"isDeleted": false,
			"id": "5UI6qqMq88kZQRp8YGHFP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -594.3993016882073,
			"y": 3090.629295937342,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 599.6925286515294,
			"height": 234.68532702528933,
			"seed": 864740119,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "548f46234a29dc6f56d1a49c0154d00f1c6b472c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 83,
			"versionNonce": 1744742812,
			"isDeleted": false,
			"id": "yn8fKA66",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -458.04249708073263,
			"y": 3331.801479650381,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 278.0325927734375,
			"height": 20,
			"seed": 1666985657,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We are only training one model here",
			"rawText": "We are only training one model here",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We are only training one model here",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 177,
			"versionNonce": 466570788,
			"isDeleted": false,
			"id": "QaEDXJk5tdY9xAIkfamws",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1597.0230385594134,
			"y": 1887.866831762365,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 587.1939264782211,
			"height": 274.10028989901366,
			"seed": 652394551,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oq5rCSRF",
				"focus": -0.4682858312988405,
				"gap": 8.231653944740401
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
					-277.5408793119718,
					-45.87452550611124
				],
				[
					-363.55561463592994,
					-274.10028989901366
				],
				[
					-587.1939264782211,
					-245.42871145769413
				]
			]
		},
		{
			"type": "text",
			"version": 93,
			"versionNonce": 1177490972,
			"isDeleted": false,
			"id": "yZv8a3u3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2509.5154161477176,
			"y": 1626.9100783411018,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 214.78890991210938,
			"height": 35,
			"seed": 767385081,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Double Descent",
			"rawText": "Double Descent",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Double Descent",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 212,
			"versionNonce": 1216997796,
			"isDeleted": false,
			"id": "5W2tUqv6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2834.1542504552494,
			"y": 1672.2565618836431,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 859.4791259765625,
			"height": 50,
			"seed": 1586352087,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "An interesting phenomenon we have observed with very large neural networks\nis that there is often a second descent in test error after the first initial convexity",
			"rawText": "An interesting phenomenon we have observed with very large neural networks\nis that there is often a second descent in test error after the first initial convexity",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "An interesting phenomenon we have observed with very large neural networks\nis that there is often a second descent in test error after the first initial convexity",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 72,
			"versionNonce": 1285419676,
			"isDeleted": false,
			"id": "e5w9GNla4KVlcBxg_b98t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2608.1081238432603,
			"y": 1750.2379056991012,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 469.31748218583436,
			"height": 173.71162326962533,
			"seed": 12489431,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "38323ce16eb37fb8af0fb4a75a52cd3532118c8d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 150,
			"versionNonce": 1248138532,
			"isDeleted": false,
			"id": "FFmiWwnS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2663.6970716119167,
			"y": 1923.6140337880297,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 573.089111328125,
			"height": 60,
			"seed": 413286647,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This can be interpreted as some implicit averaging between the many\ncomponents of the model, thus allowing us to achieve lower test results\nwithout any regularization IF our machine can handle a big enough model",
			"rawText": "This can be interpreted as some implicit averaging between the many\ncomponents of the model, thus allowing us to achieve lower test results\nwithout any regularization IF our machine can handle a big enough model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This can be interpreted as some implicit averaging between the many\ncomponents of the model, thus allowing us to achieve lower test results\nwithout any regularization IF our machine can handle a big enough model",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 1082,
			"versionNonce": 1241333532,
			"isDeleted": false,
			"id": "_26Qe2lChkgsOIHhMBYtu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 520.5418608532345,
			"y": 683.1143807279184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 717.3508146702025,
			"height": 355.364756157903,
			"seed": 1805654425,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "6iJbDMKd",
				"focus": 0.08087582836652468,
				"gap": 9.054988311356965
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
					58.89427810719087,
					225.2315291403828
				],
				[
					282.2534513689591,
					148.32691204441176
				],
				[
					428.89512727378883,
					325.33132860504145
				],
				[
					686.6206186632901,
					262.0176005309339
				],
				[
					717.3508146702025,
					355.364756157903
				]
			]
		},
		{
			"type": "text",
			"version": 59,
			"versionNonce": 1322176676,
			"isDeleted": false,
			"id": "6iJbDMKd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1127.5918451677637,
			"y": 1047.5341251971784,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 219.40890502929688,
			"height": 35,
			"seed": 1993649785,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_26Qe2lChkgsOIHhMBYtu",
					"type": "arrow"
				}
			],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Multiple domains",
			"rawText": "Multiple domains",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Multiple domains",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 229,
			"versionNonce": 1723792284,
			"isDeleted": false,
			"id": "hrQxVVjD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 877.1980849935528,
			"y": 1089.108940974115,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 742.13916015625,
			"height": 75,
			"seed": 1680192985,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Sometimes our dataset is often shifted away from the actual distribution\nwhether due to a result of distribution shift or because the subgroup\nrepresented only a certain local domains of the distribution",
			"rawText": "Sometimes our dataset is often shifted away from the actual distribution\nwhether due to a result of distribution shift or because the subgroup\nrepresented only a certain local domains of the distribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sometimes our dataset is often shifted away from the actual distribution\nwhether due to a result of distribution shift or because the subgroup\nrepresented only a certain local domains of the distribution",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 81,
			"versionNonce": 628431908,
			"isDeleted": false,
			"id": "0Wqc0psg5Qjb46MXJAy4q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1043.414508405696,
			"y": 1165.3989460176726,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 418.1624081668424,
			"height": 263.819201718995,
			"seed": 528678009,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ab7de493ef823794c1f16b9cebb7a31e5bf4ff0f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 82,
			"versionNonce": 1830103068,
			"isDeleted": false,
			"id": "n9cihrda",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1040.5976382759982,
			"y": 1417.0723495616703,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 433.29241943359375,
			"height": 34.41828537519936,
			"seed": 1036226681,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 13.767314150079745,
			"fontFamily": 1,
			"text": "Domains may e.g. correspond to different acquisition devices, or\ndifferent ways they are configured/calibrated.",
			"rawText": "Domains may e.g. correspond to different acquisition devices, or\ndifferent ways they are configured/calibrated.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Domains may e.g. correspond to different acquisition devices, or\ndifferent ways they are configured/calibrated.",
			"lineHeight": 1.25,
			"baseline": 29
		},
		{
			"type": "text",
			"version": 179,
			"versionNonce": 2017851300,
			"isDeleted": false,
			"id": "MEdtqgo0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 959.2392519531898,
			"y": 1458.185362092342,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 585.9393310546875,
			"height": 50,
			"seed": 1795803065,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "And we dont want our model to learn to classify a certain\ndomain on the expense of another one",
			"rawText": "And we dont want our model to learn to classify a certain\ndomain on the expense of another one",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "And we dont want our model to learn to classify a certain\ndomain on the expense of another one",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 213,
			"versionNonce": 284279964,
			"isDeleted": false,
			"id": "YDwSpq7vMn8wLzSOjKmcF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1496.6912685037262,
			"y": 1287.9061326383412,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 350.75227818638564,
			"height": 2.3647491742478906,
			"seed": 1109293465,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547115,
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
					350.75227818638564,
					2.3647491742478906
				]
			]
		},
		{
			"type": "text",
			"version": 74,
			"versionNonce": 57631524,
			"isDeleted": false,
			"id": "yd7R5NUL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1570.2274322699814,
			"y": 1230.2524847404452,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 164.03981018066406,
			"height": 50,
			"seed": 413794839,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Simple Approach\nfor one layer NN",
			"rawText": "Simple Approach\nfor one layer NN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Simple Approach\nfor one layer NN",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 317,
			"versionNonce": 939970844,
			"isDeleted": false,
			"id": "DSsYLIcC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1834.3122617806534,
			"y": 1316.4709284578587,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 429.2395324707031,
			"height": 100,
			"seed": 1191806423,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can try to \"combine\" both domains\non average by telling the error model\nto minimize such that both domains produce\nthe same output on average",
			"rawText": "We can try to \"combine\" both domains\non average by telling the error model\nto minimize such that both domains produce\nthe same output on average",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can try to \"combine\" both domains\non average by telling the error model\nto minimize such that both domains produce\nthe same output on average",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 1298095780,
			"isDeleted": false,
			"id": "nhg3viss",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1918.860662134774,
			"y": 1268.321116011173,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 229.9649658203125,
			"height": 35,
			"seed": 2106771545,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Moment Matching",
			"rawText": "Moment Matching",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Moment Matching",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 54,
			"versionNonce": 1103515036,
			"isDeleted": false,
			"id": "EEz6LWv_iOLji0k1oWRn6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1902.555010286183,
			"y": 1418.539528372458,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 285.2378332482431,
			"height": 175.7315352918792,
			"seed": 924842937,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "750d80275d885495d45c520babdb41e25f504387",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 108,
			"versionNonce": 1589897764,
			"isDeleted": false,
			"id": "m8uMvTnKWkbVO0yD7x9bJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1829.7743845115042,
			"y": 1591.8450236266176,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 440.46113885721945,
			"height": 55.87939821322934,
			"seed": 1301467831,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "5qOjH9kBq8InR8AJRN0H1",
					"type": "arrow"
				}
			],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "652f08ba71960bbeec186afda56104abafd6485d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 80,
			"versionNonce": 1331837468,
			"isDeleted": false,
			"id": "5qOjH9kBq8InR8AJRN0H1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2286.1560456507937,
			"y": 1621.2674937859063,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 105.17738023354377,
			"height": 3.3260055900427687,
			"seed": 687106297,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "m8uMvTnKWkbVO0yD7x9bJ",
				"focus": -0.1713266302149196,
				"gap": 15.920522282070124
			},
			"endBinding": {
				"elementId": "AF4S1EUo",
				"focus": -0.09193023741011105,
				"gap": 3.351863544507978
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
					105.17738023354377,
					3.3260055900427687
				]
			]
		},
		{
			"type": "text",
			"version": 64,
			"versionNonce": 2055931300,
			"isDeleted": false,
			"id": "AF4S1EUo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2394.6852894288454,
			"y": 1605.6398890885264,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 193.55239868164062,
			"height": 40,
			"seed": 611371321,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "5qOjH9kBq8InR8AJRN0H1",
					"type": "arrow"
				}
			],
			"updated": 1707755547115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "can also be enhanced to\ninclude variance",
			"rawText": "can also be enhanced to\ninclude variance",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "can also be enhanced to\ninclude variance",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 36,
			"versionNonce": 197957276,
			"isDeleted": false,
			"id": "4-Pc4dC3wdRZEVYdmpDLT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1937.2431698300506,
			"y": 1644.1032467822106,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.3957930922697415,
			"height": 53.50604572735733,
			"seed": 1325243577,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.3957930922697415,
					53.50604572735733
				]
			]
		},
		{
			"type": "text",
			"version": 64,
			"versionNonce": 1440919844,
			"isDeleted": false,
			"id": "RTFHAMZu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1913.9297146099934,
			"y": 1704.796671786377,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 48.22410583496094,
			"height": 40,
			"seed": 346629977,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "normal\nerror",
			"rawText": "normal\nerror",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "normal\nerror",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 51,
			"versionNonce": 1941398300,
			"isDeleted": false,
			"id": "RjS7laG23xTwluPmXgpK1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1996.7386982880823,
			"y": 1635.7179709592665,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0,
			"height": 34.33970098919963,
			"seed": 1799727319,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					34.33970098919963
				]
			]
		},
		{
			"type": "text",
			"version": 17,
			"versionNonce": 1345907876,
			"isDeleted": false,
			"id": "1Q0C1014",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1971.5059399468525,
			"y": 1670.4569707971777,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 51.26411437988281,
			"height": 40,
			"seed": 323990711,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "scaling\nfactor",
			"rawText": "scaling\nfactor",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scaling\nfactor",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 32,
			"versionNonce": 496279452,
			"isDeleted": false,
			"id": "egXgIbVPvAkQG7SsfZQlh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2139.6876861268433,
			"y": 1645.3011433283455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0,
			"height": 72.27309161680341,
			"seed": 1058689241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					72.27309161680341
				]
			]
		},
		{
			"type": "text",
			"version": 91,
			"versionNonce": 725334052,
			"isDeleted": false,
			"id": "V1qDERQ6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2030.6154510194215,
			"y": 1717.5742349451489,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 218.14447021484375,
			"height": 60,
			"seed": 17293081,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "distance between\npoint x as if it belonged to\neach group at a time",
			"rawText": "distance between\npoint x as if it belonged to\neach group at a time",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "distance between\npoint x as if it belonged to\neach group at a time",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 126,
			"versionNonce": 789452956,
			"isDeleted": false,
			"id": "fg7bSnOGXJf7dhheEFPAU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2034.9454532999432,
			"y": 1806.1647364770497,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 251.87160499742527,
			"height": 60.047590082074294,
			"seed": 1830091831,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755552167,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "V2quCxv8",
				"focus": -1.0830191695567368,
				"gap": 25.943490486480187
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
					-124.71422555507729,
					60.047590082074294
				],
				[
					-251.87160499742527,
					60.047590082074294
				]
			]
		},
		{
			"type": "text",
			"version": 85,
			"versionNonce": 1121522596,
			"isDeleted": false,
			"id": "RX4Xse0G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1550.0881908730182,
			"y": 1813.7076632462197,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 397.26483154296875,
			"height": 40,
			"seed": 1076220345,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "There are more advanced techniques that improve\nupon this with Wasserstein distance",
			"rawText": "There are more advanced techniques that improve\nupon this with Wasserstein distance",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "There are more advanced techniques that improve\nupon this with Wasserstein distance",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 134,
			"versionNonce": 1101949084,
			"isDeleted": false,
			"id": "ORiLTg_Z3_yDJuRULyvh6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1256.2978331892896,
			"y": 1542.1565053787635,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 6.16992509604097,
			"height": 280.01471891727283,
			"seed": 9368183,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547116,
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
					6.16992509604097,
					280.01471891727283
				]
			]
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 1161756452,
			"isDeleted": false,
			"id": "1kHAJ5qG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1158.2268407324668,
			"y": 1855.6964439087592,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 230.3640899658203,
			"height": 45,
			"seed": 1124224057,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Domain Critic",
			"rawText": "Domain Critic",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Domain Critic",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "arrow",
			"version": 87,
			"versionNonce": 1792768676,
			"isDeleted": false,
			"id": "jpywLShl5ye9T-IZtfx9k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 4.994478098849754,
			"y": 646.0595427804251,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 6.155606986410817,
			"height": 208.05951614068704,
			"seed": 1426418809,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547116,
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
					6.155606986410817,
					208.05951614068704
				]
			]
		},
		{
			"type": "text",
			"version": 32,
			"versionNonce": 1588195740,
			"isDeleted": false,
			"id": "Wa2qZG9U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -130.02068964986847,
			"y": 886.3052207767948,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 290.24920654296875,
			"height": 35,
			"seed": 1175570809,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Spurious Correlations",
			"rawText": "Spurious Correlations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Spurious Correlations",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 461,
			"versionNonce": 777815588,
			"isDeleted": false,
			"id": "too8yG3L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -477.13417091938254,
			"y": 931.1315128598179,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 983.47900390625,
			"height": 200,
			"seed": 622300761,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "iDz4CN90m9ZN4dJnP65vs",
					"type": "arrow"
				}
			],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Artefact of the distribution of available data (P) where one or several\ntask-irrelevant input variables are spuriously correlated to the\ntask-relevant variables\n\nThe model in this case is technically able to classify the classes correctly, using the correct\nor spurious features. But it does not know which feature is actually correct and which is spurious\nrendering it reliant on both, which results in the model mis-classifying the data if we use images\nfrom the deal world where that artefact will not exist.",
			"rawText": "Artefact of the distribution of available data (P) where one or several\ntask-irrelevant input variables are spuriously correlated to the\ntask-relevant variables\n\nThe model in this case is technically able to classify the classes correctly, using the correct\nor spurious features. But it does not know which feature is actually correct and which is spurious\nrendering it reliant on both, which results in the model mis-classifying the data if we use images\nfrom the deal world where that artefact will not exist.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Artefact of the distribution of available data (P) where one or several\ntask-irrelevant input variables are spuriously correlated to the\ntask-relevant variables\n\nThe model in this case is technically able to classify the classes correctly, using the correct\nor spurious features. But it does not know which feature is actually correct and which is spurious\nrendering it reliant on both, which results in the model mis-classifying the data if we use images\nfrom the deal world where that artefact will not exist.",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "arrow",
			"version": 58,
			"versionNonce": 1479630364,
			"isDeleted": false,
			"id": "iDz4CN90m9ZN4dJnP65vs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 9.172073431373065,
			"y": 1153.9611836866013,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 3.983668626975259,
			"height": 137.03820076794864,
			"seed": 1219121465,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "too8yG3L",
				"focus": 0.01820267192031101,
				"gap": 22.82967082678323
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
					3.983668626975259,
					137.03820076794864
				]
			]
		},
		{
			"type": "text",
			"version": 52,
			"versionNonce": 78651812,
			"isDeleted": false,
			"id": "Y9yS7g3N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 40.962232796858984,
			"y": 1192.2044025055636,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 97.35989379882812,
			"height": 50,
			"seed": 850535735,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Well what\ndo we do?",
			"rawText": "Well what\ndo we do?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Well what\ndo we do?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 435,
			"versionNonce": 1998011036,
			"isDeleted": false,
			"id": "UnDEwLr8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -517.6961921677661,
			"y": 1323.665467195747,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1082.4189453125,
			"height": 125,
			"seed": 60019513,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Its quite hard to detect this with model statistics as everything bahaves quite normal\nwithin our dataset due to its bias.\nOne thing we can do is manually generate heatmaps on the weight of aretfacts of importance in the picture.\nBy generating heatmaps we can see which features play a major role into the decision and whether\nthey make sense or not.",
			"rawText": "Its quite hard to detect this with model statistics as everything bahaves quite normal\nwithin our dataset due to its bias.\nOne thing we can do is manually generate heatmaps on the weight of aretfacts of importance in the picture.\nBy generating heatmaps we can see which features play a major role into the decision and whether\nthey make sense or not.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Its quite hard to detect this with model statistics as everything bahaves quite normal\nwithin our dataset due to its bias.\nOne thing we can do is manually generate heatmaps on the weight of aretfacts of importance in the picture.\nBy generating heatmaps we can see which features play a major role into the decision and whether\nthey make sense or not.",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 42,
			"versionNonce": 352603428,
			"isDeleted": false,
			"id": "AyEZp4QVxpEZIfZVAHg9D",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -324.83244735598544,
			"y": 1462.8888510888669,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 719,
			"height": 198,
			"seed": 76460793,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HRPKK0FezydNWAmuwZuPm",
					"type": "arrow"
				}
			],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2719b7dc93f1a4ca35cbe860d717d5d5d47c2402",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 65,
			"versionNonce": 1712162588,
			"isDeleted": false,
			"id": "HRPKK0FezydNWAmuwZuPm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 29.252316007920854,
			"y": 1670.8157307412037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 3.971756479670944,
			"height": 132.06090294905857,
			"seed": 37560025,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "AyEZp4QVxpEZIfZVAHg9D",
				"focus": 0.023977307194843575,
				"gap": 9.926879652336766
			},
			"endBinding": {
				"elementId": "opafK4B6",
				"focus": -0.0723243675489207,
				"gap": 26.779183572430156
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
					3.971756479670944,
					132.06090294905857
				]
			]
		},
		{
			"type": "text",
			"version": 58,
			"versionNonce": 1892092068,
			"isDeleted": false,
			"id": "DjuUcOWK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 57.2274829666012,
			"y": 1701.5968434586537,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 136.6798553466797,
			"height": 25,
			"seed": 1182867481,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Any solutions?",
			"rawText": "Any solutions?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Any solutions?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 480,
			"versionNonce": 696664988,
			"isDeleted": false,
			"id": "opafK4B6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -429.35071444189066,
			"y": 1829.6558172626924,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1003.3589477539062,
			"height": 125,
			"seed": 1863150745,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HRPKK0FezydNWAmuwZuPm",
					"type": "arrow"
				}
			],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Crop the feature out pre-training such that your dataset is no longer biased\n2) actively look for neurons that respond to that tag and manually kill them\n3) Manually photoshop all the aretfacts out with random noise to avoid making a new one\n4) add the artefacts to all classes such that it is no longer relevant\n5) include an extra term in the objective that penalizes terms that are based off of this artefact",
			"rawText": "1) Crop the feature out pre-training such that your dataset is no longer biased\n2) actively look for neurons that respond to that tag and manually kill them\n3) Manually photoshop all the aretfacts out with random noise to avoid making a new one\n4) add the artefacts to all classes such that it is no longer relevant\n5) include an extra term in the objective that penalizes terms that are based off of this artefact",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Crop the feature out pre-training such that your dataset is no longer biased\n2) actively look for neurons that respond to that tag and manually kill them\n3) Manually photoshop all the aretfacts out with random noise to avoid making a new one\n4) add the artefacts to all classes such that it is no longer relevant\n5) include an extra term in the objective that penalizes terms that are based off of this artefact",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 278,
			"versionNonce": 1269191716,
			"isDeleted": false,
			"id": "y3FnoEK5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2479.3846009964027,
			"y": 553.3006101033508,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 277.87310791015625,
			"height": 35,
			"seed": 1761396473,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Worst case Analysis",
			"rawText": "Worst case Analysis",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Worst case Analysis",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "arrow",
			"version": 274,
			"versionNonce": 1739812892,
			"isDeleted": false,
			"id": "ziZYlR_s-RM0lg3c4_9Om",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1442.0208716045292,
			"y": 1227.6867040947361,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 670.8242448038775,
			"height": 655.1228760384283,
			"seed": 321431033,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "I4j3ahWK",
				"focus": -0.4301867597184501,
				"gap": 14.819917773892712
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
					-317.218988706715,
					-54.12267105896558
				],
				[
					-291.66106070664773,
					-589.3357515309584
				],
				[
					-670.8242448038775,
					-655.1228760384283
				]
			]
		},
		{
			"type": "text",
			"version": 276,
			"versionNonce": 865087396,
			"isDeleted": false,
			"id": "P25kv4wC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2777.8537894268934,
			"y": 589.6058236201632,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 952.7989501953125,
			"height": 75,
			"seed": 1472568761,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "In some cases, one big error can often be more harmful than many small errors.\nThus we compromise our model to not be so perfect (making very minor amount of error) for one\nthat makes more mistakes but only on the smaller scale.",
			"rawText": "In some cases, one big error can often be more harmful than many small errors.\nThus we compromise our model to not be so perfect (making very minor amount of error) for one\nthat makes more mistakes but only on the smaller scale.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In some cases, one big error can often be more harmful than many small errors.\nThus we compromise our model to not be so perfect (making very minor amount of error) for one\nthat makes more mistakes but only on the smaller scale.",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 93,
			"versionNonce": 814156956,
			"isDeleted": false,
			"id": "J95T8a81",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2652.600381201358,
			"y": 664.3206824503494,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 665.3792724609375,
			"height": 75,
			"seed": 832284761,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This is especially relevant to protect against adversarial attacks\ncraft inputs that steer the ML system towards the\nworst-case decision behavior",
			"rawText": "This is especially relevant to protect against adversarial attacks\ncraft inputs that steer the ML system towards the\nworst-case decision behavior",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is especially relevant to protect against adversarial attacks\ncraft inputs that steer the ML system towards the\nworst-case decision behavior",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 366,
			"versionNonce": 1219664676,
			"isDeleted": false,
			"id": "gbwhofzd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2776.7144508379943,
			"y": 761.4773203076198,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 913.6389770507812,
			"height": 200,
			"seed": 2111752825,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "So what causes large errors?\nTypically they're either cause by:\n\n1) high dimensionality of the data allows for the NN to craft some very specific patterns it\nreacts highly to, some of those patterns might coincidentally appear in a random image\n\n2) High depth/nonlinearity implies that the function is locally steeper than\nnecessary",
			"rawText": "So what causes large errors?\nTypically they're either cause by:\n\n1) high dimensionality of the data allows for the NN to craft some very specific patterns it\nreacts highly to, some of those patterns might coincidentally appear in a random image\n\n2) High depth/nonlinearity implies that the function is locally steeper than\nnecessary",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "So what causes large errors?\nTypically they're either cause by:\n\n1) high dimensionality of the data allows for the NN to craft some very specific patterns it\nreacts highly to, some of those patterns might coincidentally appear in a random image\n\n2) High depth/nonlinearity implies that the function is locally steeper than\nnecessary",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "image",
			"version": 54,
			"versionNonce": 1169365276,
			"isDeleted": false,
			"id": "HF_AVONDLW1IdsaUjh4Mo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2501.406603197785,
			"y": 967.348733709786,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 379.00000000000006,
			"height": 142,
			"seed": 509349815,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "566f13643e27fa4a452e2b9d336ede15324484e4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 247,
			"versionNonce": 1971033764,
			"isDeleted": false,
			"id": "kzutc5o9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2787.7019395446932,
			"y": 1116.9235023264587,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 945.93896484375,
			"height": 50,
			"seed": 1486546135,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "X4sH5ewK_XQNG5FX0tCNk",
					"type": "arrow"
				}
			],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Very minor perturbations that are non-noticeable to the human eye can cause mis-classification\nof images in NN without a trace, and this is especially dangerous in certain fields",
			"rawText": "Very minor perturbations that are non-noticeable to the human eye can cause mis-classification\nof images in NN without a trace, and this is especially dangerous in certain fields",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Very minor perturbations that are non-noticeable to the human eye can cause mis-classification\nof images in NN without a trace, and this is especially dangerous in certain fields",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 68,
			"versionNonce": 1655281052,
			"isDeleted": false,
			"id": "X4sH5ewK_XQNG5FX0tCNk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2315.2923546752822,
			"y": 1181.459638511328,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0,
			"height": 94.76145284429708,
			"seed": 1358353559,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547116,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "kzutc5o9",
				"focus": 0.0011837921330505546,
				"gap": 14.536136184869292
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
					94.76145284429708
				]
			]
		},
		{
			"type": "text",
			"version": 49,
			"versionNonce": 647569956,
			"isDeleted": false,
			"id": "FEi9UAoM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2302.4331795158505,
			"y": 1199.6538374574332,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 157.7398223876953,
			"height": 50,
			"seed": 692977495,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "What can we do\nabout this?",
			"rawText": "What can we do\nabout this?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What can we do\nabout this?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 102,
			"versionNonce": 77365788,
			"isDeleted": false,
			"id": "Kuq2D8eH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3050.0838321346855,
			"y": 1290.006144097541,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1473.0186767578125,
			"height": 225,
			"seed": 532937497,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Enhanced Regularization\n\n1) Search for high local variations of the decision function and add these variations as a term of the error function to minimize\n\n2) In practice, this can take the form of generating adversarial examples, and forcing them to be predicted in the same way as the original data\n\n3) More generic approaches based on Lipschitz-continuity (e.g. spectral norm regularization) can also be used\n\n4) In practice, one can also address worst-case behavior by applying dimensionality reduction (e.g. blurring images) before applying the neural network",
			"rawText": "Enhanced Regularization\n\n1) Search for high local variations of the decision function and add these variations as a term of the error function to minimize\n\n2) In practice, this can take the form of generating adversarial examples, and forcing them to be predicted in the same way as the original data\n\n3) More generic approaches based on Lipschitz-continuity (e.g. spectral norm regularization) can also be used\n\n4) In practice, one can also address worst-case behavior by applying dimensionality reduction (e.g. blurring images) before applying the neural network",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Enhanced Regularization\n\n1) Search for high local variations of the decision function and add these variations as a term of the error function to minimize\n\n2) In practice, this can take the form of generating adversarial examples, and forcing them to be predicted in the same way as the original data\n\n3) More generic approaches based on Lipschitz-continuity (e.g. spectral norm regularization) can also be used\n\n4) In practice, one can also address worst-case behavior by applying dimensionality reduction (e.g. blurring images) before applying the neural network",
			"lineHeight": 1.25,
			"baseline": 218
		},
		{
			"type": "image",
			"version": 30,
			"versionNonce": 49888676,
			"isDeleted": false,
			"id": "hCHCTyWNcuZccQJH9-96z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3457.4251739532965,
			"y": 1290.543629248713,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 387.99999999999994,
			"height": 302,
			"seed": 980430169,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "38f54407e60769df37e516529c78f2a1e14a59af",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 77,
			"versionNonce": 847109788,
			"isDeleted": false,
			"id": "WWVz95OyX0PpXzxlVxX1H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2993.633063965463,
			"y": 1351.4465903279556,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 140.3026930792612,
			"height": 54.86195049894195,
			"seed": 189024599,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
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
					-86.34011881800689,
					-8.993762376875793
				],
				[
					-140.3026930792612,
					45.86818812206616
				]
			]
		},
		{
			"type": "text",
			"version": 156,
			"versionNonce": 600434980,
			"isDeleted": false,
			"id": "0IX7JKFr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1543.6476339052833,
			"y": 304.5539452677412,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 300.94525146484375,
			"height": 35,
			"seed": 506584377,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Predictive uncertainty",
			"rawText": "Predictive uncertainty",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Predictive uncertainty",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "arrow",
			"version": 122,
			"versionNonce": 1157606172,
			"isDeleted": false,
			"id": "cF8rHBSOHwLfQyuj4U_4o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 707.0421933998689,
			"y": 560.3779586153362,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 735.1729903737375,
			"height": 246.3751777775787,
			"seed": 92987513,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "7gStXyzB",
				"focus": 1.188960957769419,
				"gap": 10.062356805218968
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
					322.791008318218,
					-6.5875715983308964
				],
				[
					407.1119247768547,
					-246.3751777775787
				],
				[
					735.1729903737375,
					-243.7401491382463
				]
			]
		},
		{
			"type": "text",
			"version": 257,
			"versionNonce": 1283007652,
			"isDeleted": false,
			"id": "Iur16cIm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1243.1140878407653,
			"y": 350.51022038575985,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 923.0992431640625,
			"height": 50,
			"seed": 240194809,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "It is often useful to know when we can trust our model and when we should take the result\nwith a grain of salt. We can implement a way to output our \"confidence\" of the prediction.",
			"rawText": "It is often useful to know when we can trust our model and when we should take the result\nwith a grain of salt. We can implement a way to output our \"confidence\" of the prediction.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "It is often useful to know when we can trust our model and when we should take the result\nwith a grain of salt. We can implement a way to output our \"confidence\" of the prediction.",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 232,
			"versionNonce": 781445020,
			"isDeleted": false,
			"id": "vm1wlxnaXTl84278lXJrI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1578.1036645333866,
			"y": 426.4542521471642,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 132.18676149317503,
			"height": 93.94255520894035,
			"seed": 1865109975,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "57YyBpD2",
				"focus": -0.04213256147015274,
				"gap": 28.325024665684282
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
					-132.18676149317503,
					93.94255520894035
				]
			]
		},
		{
			"type": "text",
			"version": 32,
			"versionNonce": 582283300,
			"isDeleted": false,
			"id": "EI5G3A1g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1286.4669001789305,
			"y": 519.1607211033553,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 101.19989013671875,
			"height": 25,
			"seed": 1641913305,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Approach 1",
			"rawText": "Approach 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Approach 1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 351,
			"versionNonce": 1131189276,
			"isDeleted": false,
			"id": "57YyBpD2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 944.0994024913666,
			"y": 548.7218320217888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 718.3192138671875,
			"height": 175,
			"seed": 1725492343,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "vm1wlxnaXTl84278lXJrI",
					"type": "arrow"
				}
			],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "In regression based models, Explicitly encoding\nthe uncertainty estimate in the neural network, i.e.\nhave one output neuron for predicting the actual value of interest, and\na second output neuron for predicting the uncertainty associated to\nthis prediction. The user can then know that the prediction is\na number out of a gaussian distribution built from the outputs\nthe more variance the less confidence.",
			"rawText": "In regression based models, Explicitly encoding\nthe uncertainty estimate in the neural network, i.e.\nhave one output neuron for predicting the actual value of interest, and\na second output neuron for predicting the uncertainty associated to\nthis prediction. The user can then know that the prediction is\na number out of a gaussian distribution built from the outputs\nthe more variance the less confidence.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In regression based models, Explicitly encoding\nthe uncertainty estimate in the neural network, i.e.\nhave one output neuron for predicting the actual value of interest, and\na second output neuron for predicting the uncertainty associated to\nthis prediction. The user can then know that the prediction is\na number out of a gaussian distribution built from the outputs\nthe more variance the less confidence.",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "image",
			"version": 162,
			"versionNonce": 1718307748,
			"isDeleted": false,
			"id": "NGBLcBpkjoG18FRzF2grd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 880.1516764204976,
			"y": 740.8527909990329,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 420.30219707298966,
			"height": 158.9333684911682,
			"seed": 883804313,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2cdd84d5233cbe3e69a0790b3cb0c775b6671d09",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 87,
			"versionNonce": 24883356,
			"isDeleted": false,
			"id": "bJhb15Fe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2032.4380511577226,
			"y": 525.1319643174405,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 110.01988220214844,
			"height": 25,
			"seed": 1308090199,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Approach 2",
			"rawText": "Approach 2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Approach 2",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 223,
			"versionNonce": 701118244,
			"isDeleted": false,
			"id": "JMiV1u9O",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1739.468285340087,
			"y": 559.8508260448968,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 703.399169921875,
			"height": 125,
			"seed": 1691960985,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Train an ensemble of neural networks and measure prediction\nuncertainty as the discrepancy of predictions of each network in the\nensemble.\nat the end we reach a distribution with the mean representing the avg\nof the ensemble and the variance is the standard deviation!",
			"rawText": "Train an ensemble of neural networks and measure prediction\nuncertainty as the discrepancy of predictions of each network in the\nensemble.\nat the end we reach a distribution with the mean representing the avg\nof the ensemble and the variance is the standard deviation!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Train an ensemble of neural networks and measure prediction\nuncertainty as the discrepancy of predictions of each network in the\nensemble.\nat the end we reach a distribution with the mean representing the avg\nof the ensemble and the variance is the standard deviation!",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 260,
			"versionNonce": 1483947292,
			"isDeleted": false,
			"id": "x4KC1FXo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1694.8754899958922,
			"y": 695.2692915461862,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 764.017578125,
			"height": 60,
			"seed": 665858937,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Each model can have diff initialization, different subsets of data, and different feature inputs\nwhich can make us understand the effects of these values on the prediction\nThe more heterogeneous the ensemble, the higher the estimate of uncertainty.",
			"rawText": "Each model can have diff initialization, different subsets of data, and different feature inputs\nwhich can make us understand the effects of these values on the prediction\nThe more heterogeneous the ensemble, the higher the estimate of uncertainty.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Each model can have diff initialization, different subsets of data, and different feature inputs\nwhich can make us understand the effects of these values on the prediction\nThe more heterogeneous the ensemble, the higher the estimate of uncertainty.",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 288,
			"versionNonce": 155169444,
			"isDeleted": false,
			"id": "7f7uLD3chRAdnvpa5veV_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1835.4749761880837,
			"y": 420.4922675089628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 132.18676149317503,
			"height": 93.94255520894035,
			"seed": 612544023,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
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
					132.18676149317503,
					93.94255520894035
				]
			]
		},
		{
			"type": "image",
			"version": 283,
			"versionNonce": 1908750748,
			"isDeleted": false,
			"id": "rgkFHMW0OcGqp4m2mLiTS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1289.4700199319084,
			"y": 741.1069704993124,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 361.9037151508956,
			"height": 63.80383417400182,
			"seed": 854982647,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6822a80ae10b868e0f9aa54e70b21ada06f581f1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 1668922916,
			"isDeleted": false,
			"id": "dSZXQesk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1283.274938775909,
			"y": 791.1058772595934,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 490.321044921875,
			"height": 120,
			"seed": 1912749943,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The objective has a gradient w.r.t the mean and variance\nif we set sigma to a constant we are back at the squared\nerror loss, but having it is whats providing us the uncertainty\nterm\nIf we choose different data distributions,\nwe recover different lossfunctions",
			"rawText": "The objective has a gradient w.r.t the mean and variance\nif we set sigma to a constant we are back at the squared\nerror loss, but having it is whats providing us the uncertainty\nterm\nIf we choose different data distributions,\nwe recover different lossfunctions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The objective has a gradient w.r.t the mean and variance\nif we set sigma to a constant we are back at the squared\nerror loss, but having it is whats providing us the uncertainty\nterm\nIf we choose different data distributions,\nwe recover different lossfunctions",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "arrow",
			"version": 296,
			"versionNonce": 2023990812,
			"isDeleted": false,
			"id": "7dATTpsxciXeAbHoc6GA9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -762.3996316586954,
			"y": 522.6187369434336,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1196.4894446247765,
			"height": 1181.4527729688098,
			"seed": 806677465,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
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
					-433.91538207218105,
					-47.258110918752436
				],
				[
					-573.541618877586,
					-869.9788600952145
				],
				[
					-850.6459965375432,
					-1177.156581067105
				],
				[
					-1196.4894446247765,
					-1181.4527729688098
				]
			]
		},
		{
			"type": "text",
			"version": 100,
			"versionNonce": 291920292,
			"isDeleted": false,
			"id": "ULXRPzRy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2262.263154662014,
			"y": -669.9914555374605,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 205.4648895263672,
			"height": 35,
			"seed": 1431944121,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Prior knowledge",
			"rawText": "Prior knowledge",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Prior knowledge",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 167,
			"versionNonce": 1644200604,
			"isDeleted": false,
			"id": "C8dIbrz5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2711.669867870185,
			"y": -629.4326751099446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1119.9989013671875,
			"height": 25,
			"seed": 377187001,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We dont need the model to learn things that we already know, instead we should incorporate it in our prediction!",
			"rawText": "We dont need the model to learn things that we already know, instead we should incorporate it in our prediction!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We dont need the model to learn things that we already know, instead we should incorporate it in our prediction!",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 120,
			"versionNonce": 506692900,
			"isDeleted": false,
			"id": "7W8l5tyc1_bK8MRN5iztT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2163.9679276422467,
			"y": -582.8748172467479,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.809702755107537,
			"height": 62.03666042218515,
			"seed": 2114086201,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "7V4jYpd5",
				"focus": -0.01397965988170187,
				"gap": 14.770633433853618
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
					-2.809702755107537,
					62.03666042218515
				]
			]
		},
		{
			"type": "text",
			"version": 192,
			"versionNonce": 881708828,
			"isDeleted": false,
			"id": "7V4jYpd5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2562.1227451138434,
			"y": -506.06752339070914,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 798.279052734375,
			"height": 50,
			"seed": 2128622263,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "7W8l5tyc1_bK8MRN5iztT",
					"type": "arrow"
				}
			],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Remove features in the dataset that do not contribute to the prediction!\nthat way the model does not have to build a relation that has those features",
			"rawText": "Remove features in the dataset that do not contribute to the prediction!\nthat way the model does not have to build a relation that has those features",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Remove features in the dataset that do not contribute to the prediction!\nthat way the model does not have to build a relation that has those features",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 455,
			"versionNonce": 2135900324,
			"isDeleted": false,
			"id": "LGOUfHwW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2640.159735716379,
			"y": -446.1791168494031,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 963.0590209960938,
			"height": 150,
			"seed": 754208631,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mWfZbw9X7zPbg4Ml6EMMJ",
					"type": "arrow"
				}
			],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "for example, for rotation/translation invariance in images\n\nthis can be counteracted by pre-processing our data and randomly rotating\nor translating some images.\nAnother solution would be for atoms is to encode distances instead of coordinates of molecules.\nadd noise and distortions to the data such that its not shaped perfectly anymore",
			"rawText": "for example, for rotation/translation invariance in images\n\nthis can be counteracted by pre-processing our data and randomly rotating\nor translating some images.\nAnother solution would be for atoms is to encode distances instead of coordinates of molecules.\nadd noise and distortions to the data such that its not shaped perfectly anymore",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "for example, for rotation/translation invariance in images\n\nthis can be counteracted by pre-processing our data and randomly rotating\nor translating some images.\nAnother solution would be for atoms is to encode distances instead of coordinates of molecules.\nadd noise and distortions to the data such that its not shaped perfectly anymore",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "arrow",
			"version": 43,
			"versionNonce": 1354599324,
			"isDeleted": false,
			"id": "mWfZbw9X7zPbg4Ml6EMMJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2153.0975803142433,
			"y": -276.96313277816876,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.1030777613350438,
			"height": 122.4416315081836,
			"seed": 2001791895,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "LGOUfHwW",
				"focus": -0.013233863376741933,
				"gap": 19.215984071234345
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
					-1.1030777613350438,
					122.4416315081836
				]
			]
		},
		{
			"type": "text",
			"version": 27,
			"versionNonce": 1281854500,
			"isDeleted": false,
			"id": "snA5GDpX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2271.188072562778,
			"y": -135.76917932729037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 236.1809844970703,
			"height": 35,
			"seed": 1086081591,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Transfer learning",
			"rawText": "Transfer learning",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Transfer learning",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 303,
			"versionNonce": 952219676,
			"isDeleted": false,
			"id": "5pVKZn0K",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2645.2854876403135,
			"y": -75.05110345806338,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 942.4990234375,
			"height": 75,
			"seed": 3213849,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "If your model has barely in data, but shares very basic features with something that may\nhave a lot more data, then perhaps its better to train the first few layers of our network\non the general data but when we get into details we actually apply it to our original dataset",
			"rawText": "If your model has barely in data, but shares very basic features with something that may\nhave a lot more data, then perhaps its better to train the first few layers of our network\non the general data but when we get into details we actually apply it to our original dataset",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If your model has barely in data, but shares very basic features with something that may\nhave a lot more data, then perhaps its better to train the first few layers of our network\non the general data but when we get into details we actually apply it to our original dataset",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 82,
			"versionNonce": 2003462052,
			"isDeleted": false,
			"id": "ZCs3D3kacCBDwqJGGIBi3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2422.192236665983,
			"y": 16.73303266029137,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 498.0474657822932,
			"height": 268.0076049052699,
			"seed": 1400606073,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cd1d976756a25b5fcbb6325c368f871a36455e7a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 36,
			"versionNonce": 1485591708,
			"isDeleted": false,
			"id": "wRx2XWteXVN8GQ47LKB6m",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2294.271650212044,
			"y": 160.42024512289785,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 39.54059087405085,
			"height": 44.38229587903646,
			"seed": 888877913,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-39.54059087405085,
					44.38229587903646
				]
			]
		},
		{
			"type": "text",
			"version": 25,
			"versionNonce": 75879204,
			"isDeleted": false,
			"id": "O1dTCcHi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2452.946274822912,
			"y": 216.09985268023453,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 176.93980407714844,
			"height": 50,
			"seed": 1325563863,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "train on abundant\ndata",
			"rawText": "train on abundant\ndata",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "train on abundant\ndata",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 36,
			"versionNonce": 1305436444,
			"isDeleted": false,
			"id": "CUQHQQ_Qn_yu56v4t0qJP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1948.0897423555593,
			"y": 74.88345670148212,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 83.11593591892279,
			"height": 25.01547585909327,
			"seed": 74868473,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					83.11593591892279,
					25.01547585909327
				]
			]
		},
		{
			"type": "text",
			"version": 33,
			"versionNonce": 1109905060,
			"isDeleted": false,
			"id": "zhPO2vUz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1930.4807630689947,
			"y": 105.39756961091331,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 180.99977111816406,
			"height": 50,
			"seed": 112132535,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "retrain on \noriginal task data",
			"rawText": "retrain on \noriginal task data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "retrain on \noriginal task data",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 1946,
			"versionNonce": 805100956,
			"isDeleted": false,
			"id": "K_ffeARh7VULBTC2B1Ki9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -775.9962101834816,
			"y": 1382.1901132590729,
			"strokeColor": "#8a6e63",
			"backgroundColor": "#8a6e63",
			"width": 141.1515420634331,
			"height": 73.7114086101356,
			"seed": 1884461111,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.8441550807520348,
					3.817139337101947
				],
				[
					-1.3605996648399032,
					7.939194908586224
				],
				[
					-2.121564139111694,
					13.426242926065104
				],
				[
					-2.676584698668595,
					20.378791600207624
				],
				[
					-3.036353281162383,
					28.697154070371326
				],
				[
					-3.360927380835285,
					36.63126685090683
				],
				[
					-3.771208485991302,
					42.808117479456044
				],
				[
					-3.921791497282916,
					45.172570212228
				],
				[
					-4.644528571005106,
					47.89730152705204
				],
				[
					-5.753413728730011,
					47.52103750529257
				],
				[
					-6.6289526503195315,
					48.088348264391875
				],
				[
					-6.3463519656537395,
					50.490466495544894
				],
				[
					-5.322023493610377,
					52.49163255152287
				],
				[
					-2.873040590620455,
					55.15807272209663
				],
				[
					0.4371860140277297,
					57.84578844948162
				],
				[
					5.191665926468417,
					60.876196800684525
				],
				[
					8.298797618361398,
					62.4218836047763
				],
				[
					15.671705530531927,
					65.24490717967956
				],
				[
					24.0856805064566,
					67.33479736242323
				],
				[
					31.705683204813166,
					68.68064332174053
				],
				[
					42.94931851980973,
					69.56274623101275
				],
				[
					55.850939833759575,
					69.55636446662349
				],
				[
					69.5962809486022,
					69.20201857855291
				],
				[
					80.4711527331362,
					68.33948295323384
				],
				[
					88.84503407118807,
					66.9524940206685
				],
				[
					97.14620662259807,
					64.55036676297456
				],
				[
					103.22272047956274,
					62.70076761124232
				],
				[
					107.62522848417946,
					61.00737274912341
				],
				[
					110.55478555096896,
					59.610109356422036
				],
				[
					112.6767718563818,
					58.89658612428469
				],
				[
					117.00916846148986,
					57.408779756833916
				],
				[
					122.54043863096825,
					54.42035836044962
				],
				[
					127.8623923444026,
					50.70114595925932
				],
				[
					132.88813560618695,
					46.80914074298685
				],
				[
					134.52258941311356,
					44.68395227220319
				],
				[
					134.29763898829677,
					42.800600627553465
				],
				[
					132.64369687964958,
					39.92270583906899
				],
				[
					129.50347163232212,
					31.31517813239776
				],
				[
					126.48482486386212,
					21.685039253082
				],
				[
					124.69830994957736,
					14.489101187777331
				],
				[
					121.45911469939406,
					3.961237541025701
				],
				[
					110.48013220022168,
					-0.38498734384017314
				],
				[
					8.40286353332017,
					-4.148662379122852
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1315,
			"versionNonce": 16669220,
			"isDeleted": false,
			"id": "EkoJXeu8G3i86CniUgoN5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -750.0476747088907,
			"y": 1360.7888642410185,
			"strokeColor": "#000000",
			"backgroundColor": "#ac9a90",
			"width": 115.86472831511117,
			"height": 38.85991191486271,
			"seed": 1356888407,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.561023274336404,
					-2.323540630665236
				],
				[
					16.543703080725003,
					-4.830695510207256
				],
				[
					31.540088735896596,
					-6.59777674491574
				],
				[
					47.64236425933099,
					-8.11556903680128
				],
				[
					65.36276529733887,
					-8.967943535219701
				],
				[
					78.292093578464,
					-8.704078522640573
				],
				[
					89.57394258704079,
					-6.397608360147903
				],
				[
					97.8752513723545,
					-2.824160218273391
				],
				[
					105.52541191088842,
					2.5454620723984456
				],
				[
					108.94562340561606,
					6.713149129766121
				],
				[
					108.59556713035285,
					9.0378191388505
				],
				[
					106.6617310456121,
					10.625980999600078
				],
				[
					103.71905665978979,
					13.663704944276109
				],
				[
					102.72178369776654,
					15.382275831807576
				],
				[
					100.00184037781612,
					17.99584178559714
				],
				[
					97.8209794625811,
					22.970158002402815
				],
				[
					97.41015601276176,
					27.97978863801135
				],
				[
					96.05398076543091,
					29.387237980600677
				],
				[
					94.2053120996191,
					28.170706830722995
				],
				[
					88.59323132160102,
					26.539465720131435
				],
				[
					78.1478462794875,
					24.703275662007517
				],
				[
					63.48692791364036,
					23.704798659728176
				],
				[
					48.43033079480013,
					24.261749185658545
				],
				[
					29.20369996870579,
					26.50524476645904
				],
				[
					17.122331371726855,
					28.346025739981094
				],
				[
					8.910035562486428,
					29.891968379643004
				],
				[
					2.0065437977134826,
					29.820164169406347
				],
				[
					-2.188013015164537,
					26.284553197347414
				],
				[
					-5.432921982134206,
					19.69230174339218
				],
				[
					-6.919104909495108,
					11.183472115033158
				],
				[
					-6.216825905582682,
					4.378343067505674
				],
				[
					-4.456539528091128,
					2.1326011735063535
				],
				[
					-2.5525505365007497,
					0.8701752034599969
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1284,
			"versionNonce": 1481034268,
			"isDeleted": false,
			"id": "L-XURSJEDfTlkK8TQlL6m",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -737.3487400076017,
			"y": 1356.7298943764602,
			"strokeColor": "#000000",
			"backgroundColor": "#ac9a90",
			"width": 51.67514881866889,
			"height": 52.45589804954586,
			"seed": 1666528887,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.553036223252189,
					-4.937757362456763
				],
				[
					-23.313388060759273,
					-12.213143245176814
				],
				[
					-36.16453470197359,
					-19.459980640934862
				],
				[
					-39.43285897562367,
					-21.08290683716069
				],
				[
					-44.63044275242894,
					-25.593512489590882
				],
				[
					-46.916191434237746,
					-24.62215022070949
				],
				[
					-49.72065305617634,
					-20.28939963159562
				],
				[
					-51.451364869109895,
					-14.31443251298829
				],
				[
					-51.67514881866889,
					-8.846899671703943
				],
				[
					-50.65333413568106,
					-2.6691830081038006
				],
				[
					-47.89018740156424,
					6.174540141811448
				],
				[
					-47.13581876430424,
					12.279528529647564
				],
				[
					-46.3007252592456,
					18.027836745431376
				],
				[
					-44.35303489311687,
					22.015271269714987
				],
				[
					-40.80414131679223,
					26.060235016140638
				],
				[
					-38.43544621238945,
					25.580630487463498
				],
				[
					-32.68419770349427,
					24.736499978961604
				],
				[
					-25.394673283129134,
					25.037812169962283
				],
				[
					-17.143978319119885,
					26.862385559954976
				],
				[
					-17.98321683154974,
					24.3312656483932
				],
				[
					-19.071851820270272,
					19.326278956228307
				],
				[
					-19.530467872920863,
					14.933140656656063
				],
				[
					-19.502196863664473,
					11.665207208880783
				],
				[
					-18.620829228397493,
					7.873134320691711
				],
				[
					-16.833813185465203,
					5.974772939258988
				],
				[
					-13.872275784737583,
					4.502046672811772
				],
				[
					-9.308908985838062,
					2.938758425299541
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1045,
			"versionNonce": 1274508708,
			"isDeleted": false,
			"id": "ao-w6ZLncgYQ1Zo--PFYh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -652.6933439540876,
			"y": 1389.0658801108627,
			"strokeColor": "#000000",
			"backgroundColor": "#8a6e63",
			"width": 141.2391803217707,
			"height": 69.42979636568235,
			"seed": 2121617303,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2240867444838575,
					6.196004281524639
				],
				[
					4.135107604464899,
					17.352649950354316
				],
				[
					8.97939380283155,
					31.428607100510703
				],
				[
					11.432492911028689,
					36.96645064322307
				],
				[
					8.60280005589488,
					40.996763185512464
				],
				[
					-3.0751042940232236,
					49.0702652460765
				],
				[
					-12.248306135103721,
					52.727055014234374
				],
				[
					-20.752769721383984,
					56.12915005909802
				],
				[
					-42.989135954650166,
					61.65914276789585
				],
				[
					-81.62600983666803,
					62.66628111603701
				],
				[
					-102.77333673674981,
					59.71982092831489
				],
				[
					-118.18516203104407,
					54.1685977954102
				],
				[
					-126.61714362252175,
					47.980914292083725
				],
				[
					-129.75823236211713,
					43.70730448526097
				],
				[
					-129.806687410742,
					40.794148800657105
				],
				[
					-128.23565402743046,
					40.74129131912633
				],
				[
					-128.9174036782947,
					42.654058413729004
				],
				[
					-127.82177904701433,
					39.97173216099715
				],
				[
					-127.17713120804638,
					35.3120372251919
				],
				[
					-126.63153296643189,
					23.12184965660962
				],
				[
					-125.71235742317687,
					8.671043883585282
				],
				[
					-124.54446821252635,
					-1.2530742933378984
				],
				[
					-123.63167318379476,
					-6.763515249645333
				]
			]
		},
		{
			"type": "line",
			"version": 785,
			"versionNonce": 698295964,
			"isDeleted": false,
			"id": "dO-6wnq7o2NSKLW_RIYuZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -744.3556161312666,
			"y": 1390.8265446563998,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 10.522243503585951,
			"height": 61.09218640309978,
			"seed": 745882807,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8097026617177536,
					3.0609582171652217
				],
				[
					4.03491146228412,
					7.546201956706303
				],
				[
					4.770723583018769,
					11.05475571677099
				],
				[
					5.366839111038438,
					18.4028296661185
				],
				[
					4.9645014644152985,
					25.17899398765924
				],
				[
					4.170270494392016,
					30.979076492914075
				],
				[
					3.798748124804798,
					34.92042632055075
				],
				[
					3.992103810267406,
					41.23052654015298
				],
				[
					5.677891965372409,
					50.54697845639254
				],
				[
					7.548506442845802,
					56.6392507047896
				],
				[
					10.522243503585951,
					61.09218640309978
				]
			]
		},
		{
			"type": "line",
			"version": 824,
			"versionNonce": 541139236,
			"isDeleted": false,
			"id": "v0qnE4ps6gVoimcQuqa6A",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -746.5962085393135,
			"y": 1403.6950281822208,
			"strokeColor": "#000000",
			"backgroundColor": "#aac195",
			"width": 10.948835361399391,
			"height": 9.875976079745373,
			"seed": 1022989783,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.6050608378717715,
					0.13619224643602307
				],
				[
					-5.7555244054907355,
					1.6918258270217448
				],
				[
					-9.32393389133983,
					5.326857651206428
				],
				[
					-10.740808892351646,
					7.498143824143189
				],
				[
					-9.37176505983074,
					8.62982247109347
				],
				[
					-7.487451044464385,
					9.738060841800706
				],
				[
					-5.271007310550134,
					9.875976079745373
				],
				[
					-3.999399968145048,
					8.451725552821419
				],
				[
					-3.9755388462748567,
					6.864455933701307
				],
				[
					-2.786753923287053,
					7.772368485149479
				],
				[
					-0.9734935031536024,
					7.443184685991354
				],
				[
					0.2080264690477451,
					5.426989203710791
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 519,
			"versionNonce": 1488450332,
			"isDeleted": false,
			"id": "ZqsjS_28MyB1fqLeX0_Qn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -749.3414126213914,
			"y": 1394.846122967305,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.134365809787793,
			"height": 8.81150111572737,
			"seed": 387367671,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.3218348554080448,
					1.5894666808499105
				],
				[
					2.590247071797036,
					3.888887969432115
				],
				[
					3.134365809787793,
					5.3310681704464065
				],
				[
					2.753089573867279,
					8.81150111572737
				]
			]
		},
		{
			"type": "line",
			"version": 524,
			"versionNonce": 625564836,
			"isDeleted": false,
			"id": "88gKlOUaDDbSdryXc9fKk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -766.9246053320832,
			"y": 1405.6856494533727,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.68100242663828,
			"height": 5.87036657563159,
			"seed": 1263619095,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.3933241496431308,
					1.6057034827754206
				],
				[
					3.1700815753426936,
					3.138670812996996
				],
				[
					5.527987203094509,
					4.618888857202885
				],
				[
					9.68100242663828,
					5.87036657563159
				]
			]
		},
		{
			"type": "line",
			"version": 989,
			"versionNonce": 872624028,
			"isDeleted": false,
			"id": "QfyhquG1qFsgCiSifv3oJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -714.546399189313,
			"y": 1417.4299631569017,
			"strokeColor": "#000000",
			"backgroundColor": "#aac195",
			"width": 14.477291578822246,
			"height": 9.6720117612243,
			"seed": 1704833335,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.0901794833782525,
					1.1484133505121012
				],
				[
					-4.621989383723485,
					2.1212201326246376
				],
				[
					-6.465365186858586,
					1.4292343623815826
				],
				[
					-7.57248536248271,
					-0.26507290248770754
				],
				[
					-7.134665364342356,
					-2.581466977730405
				],
				[
					-8.174936242059744,
					-1.4981978566889196
				],
				[
					-9.889849327619194,
					-0.6026969405262868
				],
				[
					-12.281362982669224,
					-0.9255020233751948
				],
				[
					-13.759583822872179,
					-2.278199215372777
				],
				[
					-14.477291578822246,
					-5.513923730506199
				],
				[
					-13.281213714687624,
					-6.696809982161958
				],
				[
					-11.501047076325893,
					-7.4666428522995805
				],
				[
					-9.001602515231184,
					-7.550791628599662
				],
				[
					-6.216697209998609,
					-6.689885767799547
				],
				[
					-2.8046274846269337,
					-4.665830209504361
				],
				[
					-1.0118641279618017,
					-2.3956366332218266
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 790,
			"versionNonce": 1690183716,
			"isDeleted": false,
			"id": "GBGid9j98qWqMflGdmU6F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -729.1242499988193,
			"y": 1411.9830988170409,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 7.423447785252022,
			"height": 15.785372093384835,
			"seed": 2137027159,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.692708931564181,
					-0.5940029399845228
				],
				[
					-0.9460564477378441,
					-2.7043491147618224
				],
				[
					-0.46825911870364184,
					-6.163756051384394
				],
				[
					0.9010368911185144,
					-8.235914000799363
				],
				[
					2.424540971042418,
					-10.823135308063737
				],
				[
					4.091076187376721,
					-13.680671884518407
				],
				[
					6.477391337514178,
					-15.785372093384835
				]
			]
		},
		{
			"type": "line",
			"version": 753,
			"versionNonce": 1806883868,
			"isDeleted": false,
			"id": "shs3J6lI-6jKlwad1VuJv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -714.5264271101348,
			"y": 1417.415617140112,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.6540131061057877,
			"height": 2.9797099269312928,
			"seed": 292425591,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.6282701713945861,
					1.3998921470637693
				],
				[
					0.7816002749994276,
					2.9797099269312928
				],
				[
					-0.8462668199276865,
					2.297512266802573
				],
				[
					-1.8724128311063601,
					1.0916131200159485
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 970,
			"versionNonce": 42828708,
			"isDeleted": false,
			"id": "SR9PQQCnjFFeb_vv50uYg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -714.2285896921934,
			"y": 1420.4099620538846,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 15.284212070529454,
			"height": 5.949437925747575,
			"seed": 101386391,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1142699879248177,
					-0.08914939371546143
				],
				[
					2.3699384853017125,
					-1.295893853859435
				],
				[
					3.9472662827459604,
					-3.0696249589887863
				],
				[
					5.87218221350173,
					-4.2867230044342275
				],
				[
					7.736365076917951,
					-5.12127895136471
				],
				[
					10.222674771778381,
					-5.618508988274959
				],
				[
					12.341168035393451,
					-5.949437925747575
				],
				[
					14.022703431369566,
					-5.780531033304099
				],
				[
					15.284212070529454,
					-5.3345666424772205
				]
			]
		},
		{
			"type": "line",
			"version": 530,
			"versionNonce": 1505294492,
			"isDeleted": false,
			"id": "zBDP3XCWIVfsFm2tWa5XY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -652.9374856441268,
			"y": 1363.2479712839245,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 10.09003075570218,
			"height": 1.9228887962784773,
			"seed": 183229879,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.477052263827196,
					0.36198011401914837
				],
				[
					10.09003075570218,
					1.9228887962784773
				]
			]
		},
		{
			"type": "line",
			"version": 1609,
			"versionNonce": 1961193252,
			"isDeleted": false,
			"id": "a9t7yyPIt0KNGsEGdgP2-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -754.7424664990521,
			"y": 1292.574513229565,
			"strokeColor": "#000000",
			"backgroundColor": "#aac195",
			"width": 44.22185696267758,
			"height": 49.41479569247436,
			"seed": 590679767,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.835054846589967,
					-0.6624921383420006
				],
				[
					-10.985752866149827,
					-1.0491510590426345
				],
				[
					-17.827842012694333,
					-1.0742319943766367
				],
				[
					-27.161791550818418,
					-1.6516784851421042
				],
				[
					-37.12828074428183,
					-4.386533957277448
				],
				[
					-44.22185696267758,
					-2.284141451281428
				],
				[
					-43.54649619823145,
					2.3783193558002087
				],
				[
					-41.92414865687807,
					4.62173527495112
				],
				[
					-40.692751956219915,
					5.5846734054546685
				],
				[
					-40.21517442199986,
					10.261414454961033
				],
				[
					-39.875088139061,
					14.980559281648738
				],
				[
					-39.086145319030564,
					18.79632495070349
				],
				[
					-37.8481069769599,
					23.36266030428077
				],
				[
					-32.577764767538135,
					32.14975164161401
				],
				[
					-26.821412778837743,
					38.65339886434472
				],
				[
					-20.57558394563143,
					43.54334837409239
				],
				[
					-17.991989003113858,
					45.028261735196914
				],
				[
					-18.82724139911535,
					43.010911309837915
				],
				[
					-19.822018031900285,
					39.40099728823538
				],
				[
					-19.7828494688763,
					34.24942703141993
				],
				[
					-19.07857152562724,
					30.566936491117165
				],
				[
					-17.824203734369483,
					27.33554252593336
				],
				[
					-15.635372690908815,
					22.80134173061874
				],
				[
					-12.806447214175677,
					17.325756036935328
				],
				[
					-11.213819413020628,
					13.09462204260493
				],
				[
					-9.321529454666601,
					9.393405069748141
				],
				[
					-6.019385243824011,
					5.4046678018665375
				],
				[
					-1.1632895571944084,
					0.9045562476792659
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 771,
			"versionNonce": 1237812508,
			"isDeleted": false,
			"id": "vLBYbRz1oca3s3gcE1y38",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -792.6505729659146,
			"y": 1296.457142963656,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 25.81151232242816,
			"height": 9.689972708790293,
			"seed": 2038111223,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5826669683994212,
					0.6002135799610949
				],
				[
					5.912980767970641,
					0.9180018293700275
				],
				[
					9.29944375984534,
					2.4094939635275976
				],
				[
					13.601580913405513,
					5.54020061639458
				],
				[
					16.376660187562585,
					7.686150169334207
				],
				[
					18.258553151019544,
					8.899160755019015
				],
				[
					20.978846730095782,
					9.689972708790293
				],
				[
					24.106444479882928,
					9.554331120860851
				],
				[
					25.81151232242816,
					9.638459166149811
				]
			]
		},
		{
			"type": "line",
			"version": 3254,
			"versionNonce": 1409458468,
			"isDeleted": false,
			"id": "VXqisrsIImJbcYpdFh-kU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -753.9598955173548,
			"y": 1291.6698438878936,
			"strokeColor": "#000000",
			"backgroundColor": "#aac195",
			"width": 176.28696253729166,
			"height": 84.35032340504834,
			"seed": 1908573463,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707756362650,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.537553373412301,
					-1.6656886129639148
				],
				[
					5.649170076508822,
					-3.3910676891603684
				],
				[
					9.305610527792748,
					-5.178145172346541
				],
				[
					12.830841027248274,
					-6.467232499160701
				],
				[
					18.746650453682665,
					-7.348121697697203
				],
				[
					22.37791747240527,
					-7.49003230599439
				],
				[
					19.835368113774518,
					-5.326449033357769
				],
				[
					17.924499264456166,
					-2.858083018620603
				],
				[
					16.39640631682165,
					0.42380932554953776
				],
				[
					17.66884957416846,
					-2.315025959371
				],
				[
					19.429381488007998,
					-4.890888587646775
				],
				[
					23.63809694309928,
					-7.9270553590479444
				],
				[
					27.102606620197783,
					-9.547551415582545
				],
				[
					32.020662388707855,
					-11.56840157441249
				],
				[
					37.905346173833436,
					-12.5386568355028
				],
				[
					45.050203984665785,
					-12.557449999550572
				],
				[
					50.871542044737915,
					-11.564149039375417
				],
				[
					56.520574288966145,
					-10.846254728496621
				],
				[
					61.05525451753815,
					-10.185866055554863
				],
				[
					68.1991391255028,
					-7.90060142989009
				],
				[
					72.36415253303973,
					-6.020149503629791
				],
				[
					75.4291589210166,
					-4.0432250332104775
				],
				[
					73.98192899565001,
					-3.6802806127572953
				],
				[
					71.88224912430462,
					-2.7870944421429473
				],
				[
					70.24300974629779,
					-1.5306859956317125
				],
				[
					72.07087327694705,
					-2.8862860002867987
				],
				[
					74.56116119695224,
					-3.803560536714813
				],
				[
					78.57404024328054,
					-3.899423500053454
				],
				[
					85.2837558736351,
					-2.0727819663045604
				],
				[
					92.99700030887136,
					3.658618823054959
				],
				[
					96.68540657266111,
					7.517307944943127
				],
				[
					100.77703779046304,
					13.484049459863046
				],
				[
					103.07332108562656,
					18.633348906938032
				],
				[
					104.74541970511153,
					19.19491666105114
				],
				[
					107.3368813132676,
					20.824334912345243
				],
				[
					109.13368060531036,
					21.729154011457183
				],
				[
					110.76217123053523,
					23.041226826751632
				],
				[
					112.7758905663245,
					24.028400011170714
				],
				[
					108.47596983508882,
					24.343323497513197
				],
				[
					112.88635795201554,
					24.523833137095508
				],
				[
					116.34936107524726,
					25.391201149996213
				],
				[
					124.49404129781045,
					27.878464131502426
				],
				[
					131.678135557843,
					30.6211411932212
				],
				[
					133.92583866393386,
					31.358283179597663
				],
				[
					138.275611765238,
					33.25096358064069
				],
				[
					141.68575147267453,
					34.17704726873809
				],
				[
					146.32615286231746,
					34.92216484045279
				],
				[
					151.75400792046534,
					36.02759004116505
				],
				[
					154.0406958464642,
					36.88382994354529
				],
				[
					156.33460234348019,
					38.7109534714312
				],
				[
					156.55605880263425,
					41.89648958152484
				],
				[
					155.18334517085447,
					45.15712888394871
				],
				[
					148.97949089310563,
					51.06108357436965
				],
				[
					147.98193314500386,
					53.362863587377205
				],
				[
					144.95071738129332,
					57.890384785384306
				],
				[
					140.14115306110585,
					62.02330021865375
				],
				[
					133.05708109028882,
					66.32430685432759
				],
				[
					130.41935683428136,
					67.96447052697371
				],
				[
					125.81370722191916,
					69.60428546268538
				],
				[
					118.34822478468085,
					71.79287340549777
				],
				[
					112.90161731934239,
					71.61366798534515
				],
				[
					111.53726203295126,
					70.63967408002566
				],
				[
					109.14021446112733,
					69.71917868865837
				],
				[
					106.42583997030839,
					67.7185222017727
				],
				[
					101.71334635944979,
					64.71912536309232
				],
				[
					96.4497172240982,
					62.48368042739817
				],
				[
					89.24117056583802,
					60.50452244389952
				],
				[
					84.40993672936172,
					59.65779923969048
				],
				[
					79.37103989721751,
					59.29515938581125
				],
				[
					72.48400787574488,
					59.10780729478529
				],
				[
					64.19544195758083,
					59.35491069181614
				],
				[
					51.9882099845469,
					59.979025799176924
				],
				[
					46.07251060417047,
					60.5871831699968
				],
				[
					30.576489229643673,
					62.14013806165128
				],
				[
					22.74230269123877,
					63.023429623830694
				],
				[
					17.352236719556114,
					64.11292633594351
				],
				[
					14.676857007346545,
					62.260737695301465
				],
				[
					8.71748045237519,
					59.01109770799885
				],
				[
					1.030946625049471,
					55.21743392269929
				],
				[
					-5.451426994832613,
					52.18764056397773
				],
				[
					-11.692924343175585,
					48.551587070801055
				],
				[
					-17.038108287210804,
					45.4959817498274
				],
				[
					-18.444115457543344,
					43.53695510831103
				],
				[
					-19.107894141011624,
					41.647795534254094
				],
				[
					-19.730903734657396,
					37.79588169921938
				],
				[
					-19.607459018466574,
					33.52180106134893
				],
				[
					-18.532088842802537,
					28.933820208374424
				],
				[
					-15.564103534929139,
					22.92376425850483
				],
				[
					-13.393098599366155,
					18.675935058095707
				],
				[
					-11.76103005586212,
					15.022824015636246
				],
				[
					-11.039861343614705,
					12.804407174196765
				],
				[
					-8.609183137175046,
					8.540524270864946
				],
				[
					-5.127626017064324,
					4.498775511601024
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 838,
			"versionNonce": 1095795100,
			"isDeleted": false,
			"id": "I6bt-FSqKijBpI4qBC2wq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -657.0497612306425,
			"y": 1352.9435911360986,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 52.75075316240605,
			"height": 21.44291632572066,
			"seed": 2071972407,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.12229731747860421,
					-1.5893871969557345
				],
				[
					2.1260021382212466,
					-5.131491795647361
				],
				[
					4.510751298858231,
					-6.5679585084078695
				],
				[
					7.941864272353278,
					-7.856591192748733
				],
				[
					12.632667505380951,
					-11.208223994605905
				],
				[
					15.52469356924811,
					-14.277573244266241
				],
				[
					20.39674909086357,
					-17.67802619266937
				],
				[
					29.3462844824175,
					-20.610579268665678
				],
				[
					37.50144080029507,
					-21.44291632572066
				],
				[
					46.68931473192455,
					-21.295353820664886
				],
				[
					51.22670849297935,
					-19.725246011156226
				],
				[
					52.75075316240605,
					-18.077773700745418
				],
				[
					51.554064923578316,
					-16.530214616562855
				],
				[
					48.14239965744371,
					-15.16464375985945
				]
			]
		},
		{
			"type": "line",
			"version": 660,
			"versionNonce": 455538212,
			"isDeleted": false,
			"id": "YmVIstMgcKWRq4PQhirsh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -762.3933252183036,
			"y": 1309.7481895098072,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 19.17281906532366,
			"height": 10.639531979591446,
			"seed": 597125975,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.0624820759258204,
					-1.9072707317319553
				],
				[
					6.208737187273493,
					-3.3454306192259713
				],
				[
					8.844435586799454,
					-3.939552419218591
				],
				[
					12.265811512783054,
					-3.822167846377319
				],
				[
					14.86086447660428,
					-2.562837643659037
				],
				[
					16.16332392941479,
					-0.612472319710064
				],
				[
					17.29794684537998,
					2.896413090714251
				],
				[
					18.10627411845153,
					5.155131180466434
				],
				[
					19.17281906532366,
					6.699979560372854
				]
			]
		},
		{
			"type": "line",
			"version": 831,
			"versionNonce": 922569244,
			"isDeleted": false,
			"id": "C_cRcHZZOG1T5hqx9uKGt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -710.9951442694793,
			"y": 1319.0766184007723,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 26.140941679757283,
			"height": 7.980273537815243,
			"seed": 1717430391,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707756362008,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.36178214410300064,
					-1.4602941739693247
				],
				[
					3.2476125759864387,
					-3.717539734841384
				],
				[
					6.324901162027739,
					-4.9835601025674725
				],
				[
					10.894420132137155,
					-5.582597032336996
				],
				[
					14.320239607466302,
					-5.313880412556733
				],
				[
					18.126822621183152,
					-3.6334759488705575
				],
				[
					22.134976462919656,
					-0.9431888634725528
				],
				[
					26.140941679757283,
					2.397676505478247
				]
			]
		},
		{
			"type": "line",
			"version": 899,
			"versionNonce": 1319932324,
			"isDeleted": false,
			"id": "26W8MHo5wgIAJHpjqH8r1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -745.0774873641898,
			"y": 1333.9896803777588,
			"strokeColor": "#000000",
			"backgroundColor": "#000000",
			"width": 21.59023556550021,
			"height": 26.339782755439348,
			"seed": 1100464535,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.1714501876487524,
					-9.68608037266778
				],
				[
					-1.656916424381059,
					-17.560014122035888
				],
				[
					-5.517128612301544,
					-22.068638846222434
				],
				[
					-10.472984798221269,
					-23.82815862070234
				],
				[
					-16.174763503784927,
					-22.42627162926407
				],
				[
					-19.199103762893557,
					-19.981599005315463
				],
				[
					-20.890478160776304,
					-16.647085152601516
				],
				[
					-21.418785377851457,
					-13.207808279367693
				],
				[
					-21.21768723466274,
					-8.749343196511926
				],
				[
					-19.5725470611535,
					-4.801755926565394
				],
				[
					-17.70993325945509,
					-1.6739726374982213
				],
				[
					-14.687763037185519,
					1.315674675966909
				],
				[
					-10.407742018669984,
					2.5116241347370107
				],
				[
					-4.2532687490760965,
					2.444705450939004
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1163,
			"versionNonce": 760859292,
			"isDeleted": false,
			"id": "_cZpOmDvGyau-vn-Q_UOL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -681.8873166653289,
			"y": 1332.4683669129645,
			"strokeColor": "#000000",
			"backgroundColor": "#000000",
			"width": 33.371065066590525,
			"height": 26.296683540644132,
			"seed": 108623543,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4629416741189298,
					-2.7837236666779357
				],
				[
					-4.265079170733388,
					-6.512635315866771
				],
				[
					-6.860244604555182,
					-9.240305584637303
				],
				[
					-10.706776448180191,
					-11.770011567973174
				],
				[
					-14.719453561017039,
					-12.525771050436196
				],
				[
					-19.388987873412624,
					-12.247080780282413
				],
				[
					-23.59780068673739,
					-10.923373666114921
				],
				[
					-26.586572613791805,
					-9.184422144793285
				],
				[
					-29.82265195221704,
					-5.453053270592096
				],
				[
					-31.87954893710886,
					-0.6119217209885388
				],
				[
					-33.04978903928459,
					3.4905546799256384
				],
				[
					-33.371065066590525,
					6.889457938420951
				],
				[
					-31.161220158490718,
					9.24371907971693
				],
				[
					-29.02391560428753,
					10.888665362815022
				],
				[
					-25.648527989160723,
					12.54305558071073
				],
				[
					-21.32003807929546,
					13.77091249020794
				],
				[
					-15.07591807434387,
					13.737107217100142
				],
				[
					-9.754584350540142,
					12.191613021002999
				],
				[
					-6.12668000701635,
					10.154639011742717
				],
				[
					-2.118589714202508,
					4.948274750893208
				],
				[
					-0.2837439629291172,
					-0.09969371412719323
				]
			]
		},
		{
			"type": "line",
			"version": 658,
			"versionNonce": 1173536036,
			"isDeleted": false,
			"id": "uXrwYOnHB1PzNu2MfZg2L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.02298967014377773,
			"x": -714.5096206592549,
			"y": 1342.106721389869,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9619137500561056,
			"height": 3.0077591734840943,
			"seed": 1806141399,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.7552897220491769,
					-1.1871029284639565
				],
				[
					-0.9619137500561056,
					-3.0077591734840943
				]
			]
		},
		{
			"type": "line",
			"version": 468,
			"versionNonce": 1434326812,
			"isDeleted": false,
			"id": "NXeutAYmYkDe_FQ4CM1kb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -682.0469044610504,
			"y": 1332.2963131104032,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.4028476429764128,
			"height": 1.0189636038981538,
			"seed": 1597404407,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4028476429764128,
					1.0189636038981538
				]
			]
		},
		{
			"type": "line",
			"version": 455,
			"versionNonce": 1516730532,
			"isDeleted": false,
			"id": "Ftzmb5_QLfSv_Lh_cRzXu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -744.353412131545,
			"y": 1342.7497340933628,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.26829815012407504,
			"height": 1.5547663369736033,
			"seed": 413842967,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.26829815012407504,
					1.5547663369736033
				]
			]
		},
		{
			"type": "line",
			"version": 686,
			"versionNonce": 2086982556,
			"isDeleted": false,
			"id": "YMqUfmcKktMyT2oONi-hu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -744.1109237409,
			"y": 1343.7175600380092,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 13.818889914489468,
			"height": 4.134274304772682,
			"seed": 1794695991,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1389104479630037,
					-0.8671777963097798
				],
				[
					4.020294227935588,
					-1.3100521453099836
				],
				[
					8.16868401942594,
					-0.7787138829288556
				],
				[
					11.572117751232787,
					0.9116461549928374
				],
				[
					13.818889914489468,
					2.824222159462698
				]
			]
		},
		{
			"type": "line",
			"version": 455,
			"versionNonce": 129549348,
			"isDeleted": false,
			"id": "nDxShEJFh-gGMfGzcoc3U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -728.8941278373779,
			"y": 1346.2909348992753,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.06384188326766727,
			"height": 1.0568751436057828,
			"seed": 1451582551,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.06384188326766727,
					1.0568751436057828
				]
			]
		},
		{
			"type": "line",
			"version": 881,
			"versionNonce": 4194332,
			"isDeleted": false,
			"id": "VBAiKuPPdEuMqdZVUn4zZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -730.4744323765741,
			"y": 1346.7233350385716,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.208898286123299,
			"height": 4.227832681093464,
			"seed": 1529135479,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.9940307969990476,
					-1.8659305893441833
				],
				[
					-5.1655537990497296,
					-3.4511799797650684
				],
				[
					-8.208898286123299,
					-4.227832681093464
				]
			]
		},
		{
			"type": "line",
			"version": 657,
			"versionNonce": 601137060,
			"isDeleted": false,
			"id": "hPbF5pxLksVG6lhZIfn0B",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -739.4719873290248,
			"y": 1334.9332780692794,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.267274377738003,
			"height": 3.494539918610977,
			"seed": 169573015,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5885492694824244,
					-0.6172777401985369
				],
				[
					-0.3312567487578329,
					-2.180470391974114
				],
				[
					1.1534354620955753,
					-3.2539021179881717
				],
				[
					2.7037698064135167,
					-3.494539918610977
				],
				[
					4.356336119791142,
					-2.6661216089025026
				],
				[
					5.678725108255579,
					-1.3027250453029033
				]
			]
		},
		{
			"type": "line",
			"version": 485,
			"versionNonce": 687971484,
			"isDeleted": false,
			"id": "obsbHM8H8MQiwWfLY-_FL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -735.3253885277458,
			"y": 1335.759524367593,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.9805558304492603,
			"height": 0.24285720135722205,
			"seed": 1478365111,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.9805558304492603,
					0.24285720135722205
				]
			]
		},
		{
			"type": "line",
			"version": 855,
			"versionNonce": 384371492,
			"isDeleted": false,
			"id": "lCyhMKEZ4JQCcOUu480-i",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -762.6178609548376,
			"y": 1315.389486699094,
			"strokeColor": "#ffffff",
			"backgroundColor": "#ffffff",
			"width": 8.412595161374218,
			"height": 5.822794516016948,
			"seed": 793837783,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.077633992715186,
					-1.5405342996346258
				],
				[
					4.155923184308474,
					-2.8388405837367077
				],
				[
					6.859008045799023,
					-2.7745312459753055
				],
				[
					8.330139125209024,
					-1.781181255909316
				],
				[
					8.16146749860937,
					0.06742937171466817
				],
				[
					5.8470756583267285,
					1.9266494350795516
				],
				[
					3.1494139291136483,
					2.9839539322802406
				],
				[
					0.9498386781594048,
					2.5335434872614764
				],
				[
					-0.08245603616519406,
					1.5168844257656058
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 478,
			"versionNonce": 1885055260,
			"isDeleted": false,
			"id": "eSsYNdAtWrlinEPHtA_ZL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -753.0335358458111,
			"y": 1313.3210584981753,
			"strokeColor": "#ffffff",
			"backgroundColor": "#ffffff",
			"width": 1.7654424546425493,
			"height": 1.76730737840198,
			"seed": 1095290359,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 787,
			"versionNonce": 325322404,
			"isDeleted": false,
			"id": "q_REiG_X-dmotOHaMnDSi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -696.7709085132877,
			"y": 1324.6809355874714,
			"strokeColor": "#ffffff",
			"backgroundColor": "#ffffff",
			"width": 8.43342498121814,
			"height": 8.20251972748343,
			"seed": 420083479,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.8782754568320082,
					1.5832244043533872
				],
				[
					-0.8664731882836574,
					3.389999190487214
				],
				[
					0.020973499550486954,
					5.443167878457715
				],
				[
					2.9758075356177582,
					6.144879251347007
				],
				[
					4.937885085596387,
					5.913941475516506
				],
				[
					6.717520182825111,
					4.101376130234019
				],
				[
					7.555149524386131,
					2.5548886852421617
				],
				[
					7.3874525898503505,
					0.07004283762116453
				],
				[
					6.24044705581912,
					-1.6317945282542854
				],
				[
					4.7919812074239685,
					-2.0576404761364246
				],
				[
					2.2076844170979317,
					-1.4364188510762717
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 536,
			"versionNonce": 1237329308,
			"isDeleted": false,
			"id": "8uCQRIFDWQyz50EddaY-P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.8182906806839592,
			"x": -700.2773564963294,
			"y": 1323.1830114743748,
			"strokeColor": "#ffffff",
			"backgroundColor": "#ffffff",
			"width": 2.0001706430672104,
			"height": 2.866096197749097,
			"seed": 1829305399,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 645,
			"versionNonce": 1307808292,
			"isDeleted": false,
			"id": "vTwQNktNx4rlkSXEWGYQ4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -733.3206128312756,
			"y": 1333.8011084407005,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.858088881310438,
			"height": 1.9966351024054316,
			"seed": 824859991,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.1733434733035923,
					-1.293502380644497
				],
				[
					-2.7010548461195327,
					-1.9966351024054316
				],
				[
					-4.411071972253515,
					-1.949093236536849
				],
				[
					-5.858088881310438,
					-1.2255711867060006
				]
			]
		},
		{
			"type": "line",
			"version": 883,
			"versionNonce": 1784746524,
			"isDeleted": false,
			"id": "3MfiCqI9ExV59wfqxMcuO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -766.9552731539897,
			"y": 1306.2105051331241,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 14.840467930784854,
			"height": 6.202915577750426,
			"seed": 1757583991,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.139342238462797,
					0.13244722896735645
				],
				[
					-7.053937881292521,
					-0.3472119594031975
				],
				[
					-8.79768671634355,
					-1.2489789632810169
				],
				[
					-11.47785807575811,
					-3.5615011246416004
				],
				[
					-14.840467930784854,
					-6.07046834878307
				]
			]
		},
		{
			"type": "line",
			"version": 3976,
			"versionNonce": 897953188,
			"isDeleted": false,
			"id": "OEHk1cWj7mE-UPKTMAERK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2526.9281497981838,
			"y": 131.39952917579484,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 56.14068205026643,
			"height": 68.33403314946682,
			"seed": 375538041,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.6815733931344985,
					-1.7382137312506645
				],
				[
					-11.739707219899687,
					-4.943682599077448
				],
				[
					-16.14267578501295,
					-8.754875901573543
				],
				[
					-18.746578391769223,
					-12.376530792096412
				],
				[
					-22.038228622514275,
					-20.3953042261815
				],
				[
					-24.72509750950933,
					-32.03960493926122
				],
				[
					-26.499691687435593,
					-48.080961323175195
				],
				[
					-24.45231274787279,
					-46.58367302759563
				],
				[
					-24.483451895317984,
					-48.97262377995427
				],
				[
					-25.364255946194167,
					-50.66354150160103
				],
				[
					-23.148663880839848,
					-52.22852372022889
				],
				[
					-21.05363884489254,
					-49.24613300688791
				],
				[
					-19.250557605500248,
					-50.3700058818882
				],
				[
					-19.25848242707382,
					-51.521905704299925
				],
				[
					-18.500763172574015,
					-56.0789124529022
				],
				[
					-17.41020141198464,
					-56.83778342146407
				],
				[
					-17.36041764284959,
					-58.241642843302955
				],
				[
					-15.80553507061226,
					-58.37060052404056
				],
				[
					-14.423326729999964,
					-58.03047335506205
				],
				[
					-12.05094722823429,
					-54.22735634025685
				],
				[
					-10.614654052324596,
					-53.63056840651091
				],
				[
					-9.067699159512092,
					-54.448322542653614
				],
				[
					-8.89896304693805,
					-57.78442379206262
				],
				[
					-10.159435496973737,
					-59.63155023523844
				],
				[
					-8.024426263898448,
					-59.848915545034174
				],
				[
					-6.793366819140491,
					-56.925095064559876
				],
				[
					-5.884470090273656,
					-63.32575739596975
				],
				[
					-3.3502047454297355,
					-64.02307596386396
				],
				[
					-2.9082208993133314,
					-61.3462152720188
				],
				[
					-2.3794641150656406,
					-64.3275228597282
				],
				[
					-0.6269268332463843,
					-64.49517870452193
				],
				[
					0.3526759939080425,
					-60.045767198409024
				],
				[
					0.5897233254048732,
					-63.74234065999244
				],
				[
					-0.295784748662841,
					-67.6841149027479
				],
				[
					1.8807604947803267,
					-67.83470937545574
				],
				[
					2.090561072262585,
					-66.67067511654876
				],
				[
					2.290976466171978,
					-68.25911457840627
				],
				[
					3.6167908276601968,
					-68.33403314946682
				],
				[
					3.5995322638366343,
					-67.34886179911149
				],
				[
					4.567303586730521,
					-63.7558211444362
				],
				[
					5.463311406366635,
					-60.63760819160543
				],
				[
					6.318463384237299,
					-56.95339207891638
				],
				[
					5.4934217273543915,
					-61.249056902369894
				],
				[
					6.465708455255926,
					-61.4710633626292
				],
				[
					8.366625375048248,
					-58.41383409806323
				],
				[
					8.479361891973559,
					-55.4021589827517
				],
				[
					9.268997629464172,
					-62.53026735015117
				],
				[
					9.88439874853597,
					-63.387587008210645
				],
				[
					9.74381818668055,
					-64.76347949751478
				],
				[
					11.366208921633593,
					-64.95676741035511
				],
				[
					11.225331143246004,
					-63.054938836007445
				],
				[
					12.664599342328465,
					-63.39675070831004
				],
				[
					13.967956708531794,
					-60.18881122805977
				],
				[
					14.977189737660504,
					-63.8943026145333
				],
				[
					20.33739844373524,
					-62.05672568137842
				],
				[
					19.015560782290162,
					-61.40357806272363
				],
				[
					20.32328637416068,
					-60.387014645085664
				],
				[
					20.29358901268155,
					-59.02554858899586
				],
				[
					21.011792757661805,
					-51.7201491312436
				],
				[
					21.60791052528478,
					-55.399698372807656
				],
				[
					24.728118258302462,
					-54.67416995502067
				],
				[
					24.822750287428075,
					-53.421679483583965
				],
				[
					25.653799147681916,
					-47.02266470343163
				],
				[
					27.119799687550227,
					-40.78754769365211
				],
				[
					28.60334457636913,
					-35.496504704030066
				],
				[
					29.46191454435953,
					-31.98736198910777
				],
				[
					29.640990362830845,
					-26.747720312439967
				],
				[
					28.96995259522168,
					-21.034218316582724
				],
				[
					28.125194622422445,
					-17.679178086802995
				],
				[
					25.931505129206545,
					-11.958857257813944
				],
				[
					23.437566923643033,
					-7.876739654858539
				],
				[
					19.315093602894528,
					-4.391155636885977
				],
				[
					12.351318828186631,
					-1.498504311295232
				],
				[
					10.633535103277698,
					-1.0777875902252352
				],
				[
					8.608070476215289,
					-0.9496114159513261
				],
				[
					4.76828954678417,
					-0.42193443604858893
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "freedraw",
			"version": 315,
			"versionNonce": 288386716,
			"isDeleted": false,
			"id": "ZAInp59pB9AcupVJ2NER-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2513.526361720054,
			"y": 107.22516680769006,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9132196186207135,
			"height": 1.6075673202167449,
			"seed": 393063001,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.05538619684419179
				],
				[
					0.009920381174468616,
					0.08514941880488346
				],
				[
					0.08621981400807865,
					0.22154686581402744
				],
				[
					0.23780648071617047,
					0.4678749394100047
				],
				[
					0.4316914246674277,
					0.7203676580014812
				],
				[
					0.9132196186207135,
					1.577804098256053
				],
				[
					0.9132196186207135,
					1.6075673202167449
				],
				[
					0.9132196186207135,
					1.6075673202167449
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 325,
			"versionNonce": 726161700,
			"isDeleted": false,
			"id": "NwGoUNXjAVJaPjbzCmqFq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2520.2885033964067,
			"y": 107.78573173638488,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.4006090057254876,
			"height": 1.921151546007311,
			"seed": 953743161,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.007781669205351266,
					0.007783747642662638
				],
				[
					0.007781669205351266,
					0.031134990570625
				],
				[
					0.007781669205351266,
					0.07646570781664194
				],
				[
					0.007781669205351266,
					0.12179642506264612
				],
				[
					-0.0021366335318187533,
					0.38138285011724055
				],
				[
					-0.018340130627193463,
					0.46239410028219274
				],
				[
					-0.034539470847970974,
					0.6244145221748241
				],
				[
					-0.044461930459738196,
					0.7095639409797203
				],
				[
					-0.28896097924249237,
					1.2175111512977046
				],
				[
					-0.43585245611752865,
					1.420071492488073
				],
				[
					-0.7804033190584023,
					1.7207278383487616
				],
				[
					-0.8614124907860559,
					1.7531306756649139
				],
				[
					-1.0234308342414142,
					1.8341398473925932
				],
				[
					-1.159838673437,
					1.8895302011113437
				],
				[
					-1.3772598412348367,
					1.921151546007311
				],
				[
					-1.3928273365201365,
					1.921151546007311
				],
				[
					-1.3928273365201365,
					1.921151546007311
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 401,
			"versionNonce": 1323318044,
			"isDeleted": false,
			"id": "5jyz0INdwBBEj9Ytr006F",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2513.4230363671677,
			"y": 107.96273145581036,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.830474459062159,
			"height": 1.519626560134408,
			"seed": 755476505,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.007783747642662638
				],
				[
					-0.007783747642649863,
					0.0155674952853125
				],
				[
					-0.03113499057059945,
					0.038918738213274864
				],
				[
					-0.07646570781662917,
					0.0743290742848232
				],
				[
					-0.09203320310192889,
					0.09768031721278557
				],
				[
					-0.12317027210982695,
					0.12881738622069638
				],
				[
					-0.31489571971910857,
					0.2631530234403879
				],
				[
					-0.34465686324253997,
					0.27307548305214235
				],
				[
					-0.6047753682427778,
					0.46123225383834465
				],
				[
					-0.6851506165976805,
					0.5176223358925087
				],
				[
					-0.8037836601083532,
					0.5986398213693311
				],
				[
					-1.0047186633396878,
					0.7379741002660893
				],
				[
					-1.0850939116945906,
					0.7943641823202534
				],
				[
					-1.235416888531727,
					0.8992878534808767
				],
				[
					-1.320566307336623,
					0.9369013330774412
				],
				[
					-1.431338701024981,
					0.9784409807105786
				],
				[
					-1.5677361480341252,
					1.0385389948861126
				],
				[
					-1.6785106201598072,
					1.0939251917303043
				],
				[
					-1.925680460857309,
					1.18406909533767
				],
				[
					-2.041964870232831,
					1.2255422329776102
				],
				[
					-2.0872955874788346,
					1.2354626141520788
				],
				[
					-2.1426817843230266,
					1.2631557125741748
				],
				[
					-2.227831203127897,
					1.2770022617852164
				],
				[
					-2.3386056752535795,
					1.3031240616177608
				],
				[
					-2.409559367383071,
					1.346386733762455
				],
				[
					-2.469085811304454,
					1.3662274961113923
				],
				[
					-2.514416528550484,
					1.3839337033658095
				],
				[
					-2.625188922238842,
					1.4116268017879054
				],
				[
					-2.703928440448282,
					1.4271942970732179
				],
				[
					-2.7492591576943113,
					1.4349780447158675
				],
				[
					-2.8179411178682656,
					1.4448984258903363
				],
				[
					-2.8335086131535907,
					1.4448984258903363
				],
				[
					-2.871055582756945,
					1.4548188070648178
				],
				[
					-2.9163863000029493,
					1.4548188070648178
				],
				[
					-3.005179219373278,
					1.4872237228182559
				],
				[
					-3.1159536914989348,
					1.503425141476332
				],
				[
					-3.186907383628452,
					1.503425141476332
				],
				[
					-3.357206221238219,
					1.519626560134408
				],
				[
					-3.4281599133677103,
					1.519626560134408
				],
				[
					-3.5188213478597445,
					1.519626560134408
				],
				[
					-3.5641520651057483,
					1.519626560134408
				],
				[
					-3.6236785090271573,
					1.519626560134408
				],
				[
					-3.7385911497927324,
					1.519626560134408
				],
				[
					-3.8237405685976285,
					1.519626560134408
				],
				[
					-3.908889987402499,
					1.519626560134408
				],
				[
					-3.9684143528866094,
					1.519626560134408
				],
				[
					-4.053563771691506,
					1.519626560134408
				],
				[
					-4.124519542258296,
					1.519626560134408
				],
				[
					-4.221096209271274,
					1.519626560134408
				],
				[
					-4.306245628076171,
					1.519626560134408
				],
				[
					-4.365772071997554,
					1.4997857977854707
				],
				[
					-4.436725764127071,
					1.4997857977854707
				],
				[
					-4.754851375391364,
					1.4558892022680128
				],
				[
					-4.921009965923913,
					1.4234863649518605
				],
				[
					-4.991963658053431,
					1.4096398157408065
				],
				[
					-5.037298532174006,
					1.4018560680981567
				],
				[
					-5.082625092545439,
					1.4018560680981567
				],
				[
					-5.167774511350336,
					1.364242588501592
				],
				[
					-5.227300955271718,
					1.3543201288898248
				],
				[
					-5.286827399193127,
					1.3344793665408874
				],
				[
					-5.454361915210194,
					1.3027083741602132
				],
				[
					-5.525315607339686,
					1.2810801557437947
				],
				[
					-5.6237587110370715,
					1.247806453204078
				],
				[
					-5.694716560041135,
					1.2400227055614155
				],
				[
					-5.7400472772871645,
					1.220181943212478
				],
				[
					-5.803215143336708,
					1.1985495679214881
				],
				[
					-5.834354290781905,
					1.190767898716124
				],
				[
					-5.865489281352529,
					1.1752004034308114
				],
				[
					-5.881056776637829,
					1.167414577350863
				],
				[
					-5.993695607010618,
					1.1199472265730401
				],
				[
					-6.017048928375867,
					1.112165557367676
				],
				[
					-6.062379645621871,
					1.0845389689387903
				],
				[
					-6.092138710708004,
					1.074618587764322
				],
				[
					-6.137473584828605,
					1.0569123805099048
				],
				[
					-6.210060928666261,
					1.0005243768930139
				],
				[
					-6.241200076111458,
					0.9927406292503639
				],
				[
					-6.270963298072163,
					0.9728977884641281
				],
				[
					-6.3085081892382435,
					0.9551936596470096
				],
				[
					-6.371680212162358,
					0.9275005612249136
				],
				[
					-6.395029376653035,
					0.9119330659396012
				],
				[
					-6.418382698018308,
					0.9041493182969514
				],
				[
					-6.463713415264313,
					0.8786614418371702
				],
				[
					-6.494848405834937,
					0.8630939465518578
				],
				[
					-6.569942345041646,
					0.8276836104803094
				],
				[
					-6.615273062287651,
					0.8099774032259051
				],
				[
					-6.638626383652899,
					0.78662616029793
				],
				[
					-6.683957100898929,
					0.7788424126552801
				],
				[
					-6.6995245961842285,
					0.7710586650126174
				],
				[
					-6.722873760674904,
					0.7554911697273178
				],
				[
					-6.768204477920909,
					0.7377870409101864
				],
				[
					-6.791557799286182,
					0.7300032932675367
				],
				[
					-6.807125294571482,
					0.722219545624874
				],
				[
					-6.814906963776859,
					0.7144357979822241
				],
				[
					-6.830474459062159,
					0.7066520503395615
				],
				[
					-6.830474459062159,
					0.7066520503395615
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "line",
			"version": 453,
			"versionNonce": 984192164,
			"isDeleted": false,
			"id": "y6gHm-6-2ThG17GLEaAt1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2528.0467122641953,
			"y": 113.26197146702314,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.119173332229642,
			"height": 12.582959105079286,
			"seed": 233651449,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.4432039704091446,
					6.392835552572648
				],
				[
					4.049766265627715,
					10.423788675474286
				],
				[
					4.119173332229642,
					12.582959105079286
				]
			]
		},
		{
			"type": "line",
			"version": 402,
			"versionNonce": 1306687388,
			"isDeleted": false,
			"id": "3U3jg0UX1k1gCSm7zs4es",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2521.1021071261125,
			"y": 116.94038890729526,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.637031046068943,
			"height": 5.303699951956071,
			"seed": 1796027865,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.0930783291050856,
					2.326462036644852
				],
				[
					1.637031046068943,
					3.7913648850589463
				],
				[
					1.6137574428306245,
					5.303699951956071
				]
			]
		},
		{
			"type": "line",
			"version": 380,
			"versionNonce": 1364680740,
			"isDeleted": false,
			"id": "YYuV6dO1PDa1u-xBOstMh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2540.0741360576767,
			"y": 118.40883622879504,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.97905542270826,
			"height": 7.944681980495526,
			"seed": 393941689,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.5245836330657072,
					3.0687835572532784
				],
				[
					3.7332284463585195,
					6.634943862103571
				],
				[
					4.97905542270826,
					7.944681980495526
				]
			]
		},
		{
			"type": "line",
			"version": 431,
			"versionNonce": 443098140,
			"isDeleted": false,
			"id": "NROOrVHVBO5qcI3q90Am5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2545.765130538814,
			"y": 110.12016335659176,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.446948419427871,
			"height": 17.24411379002851,
			"seed": 937055129,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.6969723131243404,
					7.482723413394655
				],
				[
					5.272804182812638,
					13.202854702312331
				],
				[
					8.446948419427871,
					17.24411379002851
				]
			]
		},
		{
			"type": "line",
			"version": 360,
			"versionNonce": 2000665508,
			"isDeleted": false,
			"id": "KHevBKb_VW0bpIBznK1un",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2517.7078913789255,
			"y": 121.2606458174992,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.551200965296246,
			"height": 1.9157766401348013,
			"seed": 274626681,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.551200965296246,
					0.7978139859397543
				],
				[
					0.5364610903296545,
					1.9157766401348013
				]
			]
		},
		{
			"type": "line",
			"version": 389,
			"versionNonce": 1785086108,
			"isDeleted": false,
			"id": "a0_h4doJpyyaH-Z19sr0b",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2507.280330339774,
			"y": 109.73080011184597,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.431128577719842,
			"height": 12.077214568961772,
			"seed": 315294041,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.07479900225094567,
					4.900236253418242
				],
				[
					-0.19763203114925026,
					9.716739308380932
				],
				[
					-1.3563295754688962,
					12.077214568961772
				]
			]
		},
		{
			"type": "line",
			"version": 516,
			"versionNonce": 110143268,
			"isDeleted": false,
			"id": "7PD3kbhVhqGGpWxX0fgXd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2520.8619657557656,
			"y": 95.46855284992206,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.3540373943723079,
			"height": 4.538186691719931,
			"seed": 745762361,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.0841706832606577,
					2.0576130893405464
				],
				[
					1.3540373943723079,
					4.538186691719931
				]
			]
		},
		{
			"type": "line",
			"version": 470,
			"versionNonce": 1703660828,
			"isDeleted": false,
			"id": "fcq67vTsvHnrMGIqPHw0X",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2547.531647691539,
			"y": 90.94641640407075,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.278040645222425,
			"height": 17.110598113080425,
			"seed": 1413168921,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.053236704968872,
					5.736043251660254
				],
				[
					5.046272084594368,
					13.097610733908716
				],
				[
					6.084121239440042,
					15.35007470416841
				],
				[
					6.278040645222425,
					17.110598113080425
				]
			]
		},
		{
			"type": "line",
			"version": 848,
			"versionNonce": 1673011876,
			"isDeleted": false,
			"id": "BNWIepHCbYKYI2Zl7mV6m",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2547.8438732898076,
			"y": 82.23246373423943,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.436661347129595,
			"height": 10.155594637054723,
			"seed": 1486222329,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.4323211313984674,
					2.0021737247296176
				],
				[
					3.153833211068353,
					3.545945524359089
				],
				[
					3.945427775133121,
					4.0473391202001485
				],
				[
					4.480050253019492,
					5.228661996463415
				],
				[
					6.436661347129595,
					10.155594637054723
				]
			]
		},
		{
			"type": "line",
			"version": 382,
			"versionNonce": 1833683356,
			"isDeleted": false,
			"id": "lXFIj3aQPJWKv4SKYVc_I",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2540.8273432259643,
			"y": 81.41612534074066,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.3921403940317747,
			"height": 9.613038026530976,
			"seed": 1837567193,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.9753363317735719,
					3.1262341116487566
				],
				[
					3.3921403940317747,
					9.613038026530976
				]
			]
		},
		{
			"type": "line",
			"version": 378,
			"versionNonce": 895757860,
			"isDeleted": false,
			"id": "l-acN6ytGzC9ktp6BL46O",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2526.9933753992377,
			"y": 85.34602779275154,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.734003428002166,
			"height": 6.834241928354877,
			"seed": 2057439673,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.329429635534344,
					2.4263887422875094
				],
				[
					2.734003428002166,
					6.834241928354877
				]
			]
		},
		{
			"type": "line",
			"version": 367,
			"versionNonce": 1691891228,
			"isDeleted": false,
			"id": "96oezsCJRAav3wxbUs7Ck",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2516.8753340341445,
			"y": 78.056907393347,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.012744172892151987,
			"height": 3.834303455079486,
			"seed": 688548505,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.012744172892151987,
					3.834303455079486
				]
			]
		},
		{
			"type": "line",
			"version": 324,
			"versionNonce": 478333348,
			"isDeleted": false,
			"id": "0vrW4nwk8FD0O2E-boSNZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2516.7368783308034,
			"y": 84.54796600344996,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.07050669401988992,
			"height": 3.07817795970122,
			"seed": 829665145,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.07050669401988992,
					3.07817795970122
				]
			]
		},
		{
			"type": "line",
			"version": 360,
			"versionNonce": 2032341660,
			"isDeleted": false,
			"id": "1qhDg0-xNDXN6PNp4dmIl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2511.766376549137,
			"y": 81.63614817565188,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.7050359647787806,
			"height": 7.997045928384203,
			"seed": 1780570201,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.6232874057475711,
					3.180425609330661
				],
				[
					0.7050359647787806,
					7.997045928384203
				]
			]
		},
		{
			"type": "line",
			"version": 351,
			"versionNonce": 1816261924,
			"isDeleted": false,
			"id": "fwLKbKJP1HPiGXVoaUCwG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2504.102734556334,
			"y": 80.21355775126374,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.32297015415266,
			"height": 5.819272546404671,
			"seed": 350676281,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.2839195955082806,
					3.014364168979722
				],
				[
					1.32297015415266,
					5.819272546404671
				]
			]
		},
		{
			"type": "line",
			"version": 499,
			"versionNonce": 1759403804,
			"isDeleted": false,
			"id": "PGXuQP0xyhDZ3X0zNzxjE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2520.679328040535,
			"y": 74.28564334348339,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.6114851745041743,
			"height": 8.021780907698089,
			"seed": 1831327257,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.6114851745041743,
					8.021780907698089
				]
			]
		},
		{
			"type": "line",
			"version": 329,
			"versionNonce": 1645195428,
			"isDeleted": false,
			"id": "5ywcvgAomqSjK4qFDbooB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2547.8617531443774,
			"y": 103.83305007029195,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.48320549284451625,
			"height": 1.7026180945009413,
			"seed": 1977068281,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.48320549284451625,
					1.7026180945009413
				]
			]
		},
		{
			"type": "line",
			"version": 389,
			"versionNonce": 1283201948,
			"isDeleted": false,
			"id": "6aj18SY99GBd0hXBaQVsC",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2506.925779867297,
			"y": 89.41787503128948,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.25585858789919197,
			"height": 2.7096545351760764,
			"seed": 125428697,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.25585858789919197,
					1.2088288792275694
				],
				[
					0.17682361183531345,
					2.7096545351760764
				]
			]
		},
		{
			"type": "ellipse",
			"version": 490,
			"versionNonce": 1570372644,
			"isDeleted": false,
			"id": "zPKY_mUEyCwdOlTTXjlyc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2510.8823562407915,
			"y": 95.61579073157462,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 11.111800583336853,
			"height": 11.224954346547683,
			"seed": 505544889,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 655,
			"versionNonce": 1580091420,
			"isDeleted": false,
			"id": "SJ2J7MZgjpUXFv0HyGTkO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2536.70628019693,
			"y": 97.45694624410716,
			"strokeColor": "#000000",
			"backgroundColor": "#000",
			"width": 12.315865204661488,
			"height": 11.970051571158484,
			"seed": 1735623065,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 444,
			"versionNonce": 416208804,
			"isDeleted": false,
			"id": "S_gcMajHPJ5g8dCgNKAZX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2528.5274290602824,
			"y": 109.69855985622773,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.251779190849051,
			"height": 0.913671758670707,
			"seed": 279045753,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.1424141743749725,
					0.5833419633521634
				],
				[
					-2.737422297460753,
					0.913671758670707
				],
				[
					-4.285093851438034,
					0.7865008944813977
				],
				[
					-5.251779190849051,
					0.36750736266394446
				]
			]
		},
		{
			"type": "line",
			"version": 419,
			"versionNonce": 1105650844,
			"isDeleted": false,
			"id": "p_JWyuyM3cR9lITsdbqaF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2504.99760871911,
			"y": 107.87315791907274,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.797813473528297,
			"height": 2.1628781193279694,
			"seed": 1416671065,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1362517676965447,
					-0.045257812061151176
				],
				[
					2.656907394108077,
					-0.40691669201703246
				],
				[
					4.797813473528297,
					-2.1628781193279694
				]
			]
		},
		{
			"type": "line",
			"version": 792,
			"versionNonce": 1608270628,
			"isDeleted": false,
			"id": "rsJLHTb05mHdYUeH3wh45",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2499.860419691487,
			"y": 104.21419202153355,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 9.702007602755934,
			"height": 23.61873205122785,
			"seed": 1228102713,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.023852945713244943,
					2.4040640591341313
				],
				[
					-0.09788096635093896,
					5.416460012470013
				],
				[
					-0.6270354315946867,
					9.028289830159025
				],
				[
					-1.4522518570745384,
					12.595790417615149
				],
				[
					-1.8642599210476243,
					14.198907803598809
				],
				[
					-2.6544725048254687,
					15.930296106676279
				],
				[
					-3.6884061623212867,
					17.60364804548787
				],
				[
					-5.769576994812548,
					20.38679508394044
				],
				[
					-7.143313565085061,
					21.856117546158803
				],
				[
					-8.684234434691591,
					22.93867776285974
				],
				[
					-9.702007602755934,
					23.61873205122785
				]
			]
		},
		{
			"type": "line",
			"version": 463,
			"versionNonce": 1297608988,
			"isDeleted": false,
			"id": "GYZZ-Lu_AGE9NNYfFZ67l",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -2517.833669486373,
			"y": 130.3946401383655,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 6.636286782725969,
			"height": 11.440025241442488,
			"seed": 1858956569,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.07494868841625764,
					1.7698743266354038
				],
				[
					-0.501275906263666,
					3.424773339627011
				],
				[
					-1.8360595240475168,
					5.389298993993588
				],
				[
					-3.4772091947412234,
					7.5019756582315855
				],
				[
					-5.079089350959401,
					9.387490078683292
				],
				[
					-6.636286782725969,
					11.440025241442488
				]
			]
		},
		{
			"type": "line",
			"version": 618,
			"versionNonce": 1227898532,
			"isDeleted": false,
			"id": "13W14Ek-UrauCVQ1IAIus",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -2513.8696996861054,
			"y": 129.70669026644066,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 12.163754839719015,
			"height": 19.384304411326305,
			"seed": 2092065273,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.11158259116537118,
					2.712667139509047
				],
				[
					-1.2287772098883676,
					5.922997295624636
				],
				[
					-3.1410640503275338,
					8.165001843194307
				],
				[
					-6.6701341386352,
					11.606212966064648
				],
				[
					-9.322825573625153,
					13.868813161834943
				],
				[
					-10.943609454681129,
					15.190991445294213
				],
				[
					-11.922403790159624,
					17.672875340411075
				],
				[
					-12.163754839719015,
					19.384304411326305
				]
			]
		},
		{
			"type": "line",
			"version": 779,
			"versionNonce": 1341353372,
			"isDeleted": false,
			"id": "vjbhSFtKlGn6FV1jq5er7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -2513.672037447844,
			"y": 129.60360581242998,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 11.506645633997891,
			"height": 19.71310477775121,
			"seed": 1877326553,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.9992806719959515,
					1.0288607516556658
				],
				[
					1.480515566472009,
					2.612284025029002
				],
				[
					1.2881883313280145,
					4.581436760437507
				],
				[
					0.7320522327337662,
					6.518877898807815
				],
				[
					-0.25730158295618766,
					8.285333355984656
				],
				[
					-3.51534436209704,
					11.090761082282196
				],
				[
					-5.214651745818245,
					12.687090851663326
				],
				[
					-6.388827639545987,
					13.924112213841303
				],
				[
					-8.438827668393408,
					15.41801307632628
				],
				[
					-9.55904293343665,
					17.593912445382266
				],
				[
					-10.026130067525882,
					19.71310477775121
				]
			]
		},
		{
			"type": "line",
			"version": 472,
			"versionNonce": 1836632612,
			"isDeleted": false,
			"id": "RBsOOzM6jI7WoPm3_do0N",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -2512.181531712669,
			"y": 133.4984829356685,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.1722659697400664,
			"height": 2.410783087306189,
			"seed": 1492842425,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.6141751008766815,
					0.2740213318978457
				],
				[
					1.1722659697400664,
					1.0617779222606265
				],
				[
					0.8883890079832472,
					2.410783087306189
				]
			]
		},
		{
			"type": "line",
			"version": 692,
			"versionNonce": 1525373468,
			"isDeleted": false,
			"id": "ZjhPgJ1bOcQFMxzdb9ezV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -2511.243637685967,
			"y": 135.5111260120446,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 10.411018467811504,
			"height": 14.11401425829296,
			"seed": 1779800217,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.7281690723610796,
					0.3060204727407963
				],
				[
					1.0364582393413775,
					1.2561654483360558
				],
				[
					0.9443044069368569,
					2.518883729801036
				],
				[
					0.22886112644934406,
					3.7473077960180023
				],
				[
					-0.06275313787075826,
					5.087652352705164
				],
				[
					-1.4754875069133446,
					6.447879640186487
				],
				[
					-4.02145575271065,
					7.785050662954906
				],
				[
					-6.766027075042311,
					9.656143046886546
				],
				[
					-8.42511828428745,
					11.611252339945324
				],
				[
					-9.374560228470125,
					14.11401425829296
				]
			]
		},
		{
			"type": "line",
			"version": 526,
			"versionNonce": 530834852,
			"isDeleted": false,
			"id": "eekXtTvYCn_7tYe7gqUSE",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -2514.8303667761106,
			"y": 143.09771868937577,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.627045046676744,
			"height": 5.696015903105609,
			"seed": 1156128121,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.11236367725184085,
					0.9397168961433096
				],
				[
					-0.5892062741595738,
					2.0908048689594505
				],
				[
					-1.533202033159199,
					3.1745178988960374
				],
				[
					-2.212354119864627,
					3.793821303960574
				],
				[
					-2.627045046676744,
					5.696015903105609
				]
			]
		},
		{
			"type": "line",
			"version": 450,
			"versionNonce": 154252956,
			"isDeleted": false,
			"id": "5QX9xiokVK389D98Ekdq2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -2512.3033325838005,
			"y": 141.7564939662231,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.1442562798997824,
			"height": 8.008495398290568,
			"seed": 146343513,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.11360882106698379,
					0.9721011874036237
				],
				[
					-0.08356972652630275,
					2.4757231409031335
				],
				[
					-0.6860003776888164,
					4.05596892333292
				],
				[
					-1.620844857250329,
					5.942535912391102
				],
				[
					-3.0306474588327985,
					8.008495398290568
				]
			]
		},
		{
			"type": "line",
			"version": 683,
			"versionNonce": 618631460,
			"isDeleted": false,
			"id": "MgfWhE8bhkCeXEWWyNOWA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -2510.082514034006,
			"y": 137.38436133131108,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.998089983624833,
			"height": 12.353714522750249,
			"seed": 542692153,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.7194363406300024,
					1.272343770759496
				],
				[
					1.1851016613834364,
					3.9862560646594334
				],
				[
					0.4126372650611025,
					7.496854208231456
				],
				[
					-3.8129883222413965,
					12.353714522750249
				]
			]
		},
		{
			"type": "line",
			"version": 469,
			"versionNonce": 1199080220,
			"isDeleted": false,
			"id": "CuKXESGxUUYUhxyNWNT65",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 80,
			"angle": 0,
			"x": -2509.010747533276,
			"y": 143.34760216977213,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 2.356858808320191,
			"height": 6.349383783211458,
			"seed": 1345061913,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.3514619175651929,
					1.4889676766649151
				],
				[
					0.3671365993460722,
					2.7010019449693767
				],
				[
					0.14731728712407546,
					3.9517439240831496
				],
				[
					-1.9897222089741189,
					6.349383783211458
				]
			]
		},
		{
			"type": "line",
			"version": 525,
			"versionNonce": 1822018724,
			"isDeleted": false,
			"id": "jNyfY9zA7HO7OulAmmzrV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2521.562263192932,
			"y": 130.83568221257093,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.22496902857474,
			"height": 8.12168267982941,
			"seed": 69605625,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.11043432974456337,
					1.728796016279231
				],
				[
					-0.7712195877176452,
					3.792723190950601
				],
				[
					-1.6171186976277623,
					5.626567342130576
				],
				[
					-3.444124493559497,
					7.478124019933364
				],
				[
					-5.22496902857474,
					8.12168267982941
				]
			]
		},
		{
			"type": "line",
			"version": 708,
			"versionNonce": 473022364,
			"isDeleted": false,
			"id": "MRWix-l3lm52LeAktZ5Mh",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2526.8709180207616,
			"y": 137.2986381173837,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.9986167423396564,
			"height": 11.41368992214859,
			"seed": 1573556697,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.028638307748645238,
					3.486516117156229
				],
				[
					-1.8366847339716676,
					7.8790933152146465
				],
				[
					-1.9986167423396564,
					11.41368992214859
				]
			]
		},
		{
			"type": "line",
			"version": 423,
			"versionNonce": 1216387108,
			"isDeleted": false,
			"id": "goQWAJmxl_2_0W4OvAVZ_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2524.9543488693944,
			"y": 138.39343081686195,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.9625225028737716,
			"height": 2.567351665070562,
			"seed": 36499129,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.560159103659946,
					1.0790066642662044
				],
				[
					-1.2992906251485083,
					1.8955597342974055
				],
				[
					-1.9625225028737716,
					2.567351665070562
				]
			]
		},
		{
			"type": "line",
			"version": 369,
			"versionNonce": 1871670300,
			"isDeleted": false,
			"id": "MQDK9sYJJ9VLwDE56D5--",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2528.3457565756016,
			"y": 137.32437196890248,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.4543505575270612,
			"height": 2.0034770240452717,
			"seed": 670085017,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.40826996543113775,
					1.0554437861690207
				],
				[
					1.4543505575270612,
					2.0034770240452717
				]
			]
		},
		{
			"type": "line",
			"version": 1404,
			"versionNonce": 612496292,
			"isDeleted": false,
			"id": "A7puQvXABstSJ3vYMoO-2",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2526.9286404610566,
			"y": 137.25135167058983,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 21.48438671898626,
			"height": 6.473376070215108,
			"seed": 1699304569,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-15.91904760407496,
					0.11668211035651141
				],
				[
					-20.722290115678653,
					-0.3293115209273305
				],
				[
					-18.75845034561704,
					-0.8543111100929612
				],
				[
					-21.368794109468002,
					-1.4791991962098163
				],
				[
					-20.80758246701702,
					-2.267296090708524
				],
				[
					-18.69408274161307,
					-2.2212785298787963
				],
				[
					-20.02480908993144,
					-2.869299383188714
				],
				[
					-21.48438671898626,
					-3.8747503759127544
				],
				[
					-20.657991100105185,
					-4.522710554841861
				],
				[
					-17.176447644159943,
					-4.138678656461469
				],
				[
					-17.47683331353385,
					-5.846715236971597
				],
				[
					-16.58439231211823,
					-6.356693959858597
				],
				[
					-14.710070995920145,
					-4.5627635602349885
				],
				[
					-8.291639534565485,
					-4.403102884123004
				],
				[
					-2.703908935113783,
					-5.047934375414855
				],
				[
					-0.7929297408321492,
					-6.060903715327898
				]
			]
		},
		{
			"type": "line",
			"version": 419,
			"versionNonce": 1401129116,
			"isDeleted": false,
			"id": "83BMf9Doow85wEJcbGbtn",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2524.2651221974556,
			"y": 132.4177112941935,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.3145965781013556,
			"height": 4.826865949876498,
			"seed": 1039818073,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.3084500859902981,
					1.029385716950626
				],
				[
					-1.527266495904713,
					3.005977659051371
				],
				[
					-3.3145965781013556,
					4.826865949876498
				]
			]
		},
		{
			"type": "line",
			"version": 625,
			"versionNonce": 1053548324,
			"isDeleted": false,
			"id": "lV1iXwKw1JHCuajISHLYn",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2525.7574270599234,
			"y": 131.32020143766107,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.592703174194641,
			"height": 6.084374293563817,
			"seed": 1901546041,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.39496217425908275,
					0.7663497916945093
				],
				[
					-1.7737812845070882,
					1.9460864419839548
				],
				[
					-3.5085939278523433,
					3.287224806443387
				],
				[
					-5.0503396005776375,
					4.507438552124618
				],
				[
					-7.566912793151411,
					6.0404477655896605
				],
				[
					-8.592703174194641,
					6.084374293563817
				]
			]
		},
		{
			"type": "line",
			"version": 496,
			"versionNonce": 1270879516,
			"isDeleted": false,
			"id": "tA8OpgyxgM0vQq1XZ4w1w",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2530.2861443784664,
			"y": 132.3278195609871,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.303325947915372,
			"height": 5.11861607204929,
			"seed": 138648345,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6907540835254965,
					0.9616111145625874
				],
				[
					-1.5642805062235856,
					1.7978966575178614
				],
				[
					-3.7525099646694855,
					3.216120739016684
				],
				[
					-6.08633155692605,
					4.648927776045599
				],
				[
					-7.350474367332098,
					5.11861607204929
				],
				[
					-8.303325947915372,
					5.064726669811867
				]
			]
		},
		{
			"type": "line",
			"version": 413,
			"versionNonce": 1607228068,
			"isDeleted": false,
			"id": "0do0kOpyDg36sJka5mbHm",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2534.642607129852,
			"y": 132.79343739744252,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.931946063412941,
			"height": 3.2164584051360565,
			"seed": 590532601,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.384598134956053,
					1.787460664016251
				],
				[
					-4.931946063412941,
					3.2164584051360565
				]
			]
		},
		{
			"type": "line",
			"version": 521,
			"versionNonce": 364319132,
			"isDeleted": false,
			"id": "jLYPMBDCRDIxw8RdVAUZq",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2543.988139555188,
			"y": 132.94868335284542,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.4302692651005362,
			"height": 2.245189511956323,
			"seed": 136866009,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.14237902964351384,
					0.8703766309283536
				],
				[
					0.5961231535734325,
					1.7369175857820622
				],
				[
					1.4302692651005362,
					2.245189511956323
				]
			]
		},
		{
			"type": "line",
			"version": 1294,
			"versionNonce": 305227300,
			"isDeleted": false,
			"id": "T2RUPZezTxTOQbhvxXvpl",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2513.1546287961223,
			"y": 129.37449241924514,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 18.660417201918776,
			"height": 11.651814676505895,
			"seed": 1891100089,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.9786417326917771,
					0.43401884651615125
				],
				[
					4.226532056344864,
					0.5734080206095059
				],
				[
					6.11856946413034,
					0.4609754445722856
				],
				[
					6.895547274016465,
					-0.14147036225398368
				],
				[
					8.188066659548014,
					-0.4228470015724204
				],
				[
					9.187448507237844,
					-0.4992699791636347
				],
				[
					10.293614471982869,
					-1.0625887761342854
				],
				[
					10.809605234604486,
					-1.952564680391434
				],
				[
					11.701968957652722,
					-2.114326459102755
				],
				[
					13.99254145814213,
					-4.028932150263789
				],
				[
					14.852464198436925,
					-5.156302699001573
				],
				[
					15.926407049560694,
					-5.08965222788486
				],
				[
					15.667706283312713,
					-3.951033176545715
				],
				[
					17.72079336051641,
					-5.404541712292124
				],
				[
					17.77465276178122,
					-3.958517384696904
				],
				[
					18.591496588239753,
					-4.444735388998502
				],
				[
					18.660417201918776,
					-2.433962666361701
				],
				[
					16.206418644625124,
					-0.8454028385330219
				],
				[
					15.038656234681094,
					-0.5670911606479324
				],
				[
					14.766461030950847,
					0.32225601632966067
				],
				[
					12.677958115929833,
					0.3894175384971371
				],
				[
					12.787918818726842,
					1.2999424020437593
				],
				[
					12.15036111497135,
					2.0578203513435147
				],
				[
					10.937022365398315,
					2.285755844336059
				],
				[
					10.799571150684274,
					3.2284244741039787
				],
				[
					8.96376818667842,
					3.3927569740877046
				],
				[
					7.668803825330379,
					4.723356387256415
				],
				[
					6.153089617737632,
					4.937734233820902
				],
				[
					5.070839497296749,
					5.925720987950087
				],
				[
					2.388822064996998,
					6.247272964213771
				]
			]
		},
		{
			"type": "line",
			"version": 446,
			"versionNonce": 1889173020,
			"isDeleted": false,
			"id": "G5GNIgPSEhId4EqYy5YPy",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2501.9495628443456,
			"y": 131.5556347686205,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.045323376716293,
			"height": 1.661616592840832,
			"seed": 402966169,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.8585452241999176,
					-0.34332947538176317
				],
				[
					-5.797137181402248,
					-0.9541107938200738
				],
				[
					-7.0973129185968045,
					-1.6320052190631564
				],
				[
					-8.045323376716293,
					-1.661616592840832
				]
			]
		},
		{
			"type": "line",
			"version": 445,
			"versionNonce": 1525219748,
			"isDeleted": false,
			"id": "0we1BHGiPvHw_9BpcDY24",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2504.105660330056,
			"y": 132.68002373793848,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 8.086272014593604,
			"height": 1.1877014701505706,
			"seed": 146967417,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.4626290841309575,
					-0.23704430553663763
				],
				[
					-5.528612131139117,
					-0.8157907923197553
				],
				[
					-7.116332086911996,
					-1.1870451730117062
				],
				[
					-8.086272014593604,
					-1.1877014701505706
				]
			]
		},
		{
			"type": "line",
			"version": 447,
			"versionNonce": 1700551324,
			"isDeleted": false,
			"id": "4vr33hdlqjMV3yRx6xucJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2500.5631674154038,
			"y": 129.7567683578967,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.035229998028667,
			"height": 0.6802960313347941,
			"seed": 724874329,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.5341682692256453,
					-0.007824813668182908
				],
				[
					-3.4576240540250445,
					-0.1874647135779064
				],
				[
					-5.035229998028667,
					-0.6802960313347941
				]
			]
		},
		{
			"type": "line",
			"version": 435,
			"versionNonce": 1897999652,
			"isDeleted": false,
			"id": "rOt0zqBVkC3ogFaEapfdS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2502.468609154302,
			"y": 127.54226076067418,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.23203881541686,
			"height": 0.4761785408966429,
			"seed": 321831225,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.6645748210149881,
					0.3156130251054417
				],
				[
					3.23203881541686,
					0.4761785408966429
				]
			]
		},
		{
			"type": "line",
			"version": 403,
			"versionNonce": 246327068,
			"isDeleted": false,
			"id": "ppfeCQcrzVzwHTYalyYgo",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2497.5879842029676,
			"y": 125.45289712809405,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.39690645369747807,
			"height": 2.4143335989635633,
			"seed": 236204569,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.21171500161581194,
					0.536927044812728
				],
				[
					-0.39690645369747807,
					1.4870106218657364
				],
				[
					-0.13305886541992867,
					2.4143335989635633
				]
			]
		},
		{
			"type": "line",
			"version": 349,
			"versionNonce": 1984424100,
			"isDeleted": false,
			"id": "f02zhrHMQnYa26jQenFFl",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2495.4577324517136,
			"y": 125.44063862723185,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.5559307471092799,
			"height": 0.5559778176008018,
			"seed": 1893238521,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5559307471092799,
					0.5559778176008018
				]
			]
		},
		{
			"type": "line",
			"version": 374,
			"versionNonce": 2066308124,
			"isDeleted": false,
			"id": "X7hroanGSl20aCpdcBEGQ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2523.9181697107947,
			"y": 128.710206431424,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.9775433304645279,
			"height": 2.1301376107350407,
			"seed": 637485017,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707756368099,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.0110770315251085,
					0.6447334591926885
				],
				[
					0.18515004306399932,
					1.5347446771641884
				],
				[
					0.9664662989394194,
					2.1301376107350407
				]
			]
		},
		{
			"type": "line",
			"version": 879,
			"versionNonce": 772486180,
			"isDeleted": false,
			"id": "ocm9JGlYZQREAUOkgVFl5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2507.9636465080775,
			"y": 145.52600565412718,
			"strokeColor": "#000000",
			"backgroundColor": "#964b00",
			"width": 42.10838330546363,
			"height": 4.272468762979137,
			"seed": 2073812153,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.945234919190211,
					0.5032333145493564
				],
				[
					7.880236608651394,
					1.8909949571981752
				],
				[
					8.884636638518218,
					2.962663835800384
				],
				[
					6.118773884550646,
					3.904435173360138
				],
				[
					-6.3663811007469855,
					4.272468762979137
				],
				[
					-17.87778315618683,
					3.9567442889832205
				],
				[
					-29.93064315670204,
					2.5828255808718996
				],
				[
					-33.22374666694542,
					1.4403704598921114
				],
				[
					-32.00824039432883,
					0.5781959959229975
				],
				[
					-28.98221426822568,
					0.5179022923584845
				],
				[
					-20.702636433539478,
					0.11512866269324816
				]
			]
		},
		{
			"type": "line",
			"version": 804,
			"versionNonce": 1921814556,
			"isDeleted": false,
			"id": "_tFcNXsmWYHduB5NwVt8k",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2497.8403440547077,
			"y": 148.65778619373827,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 42.55753315151403,
			"height": 31.16119117033695,
			"seed": 827448729,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4392074386793567,
					9.548234176725801
				],
				[
					-3.0497413214736215,
					16.989914869732765
				],
				[
					-6.081174005163295,
					24.60699109004645
				],
				[
					-12.300334513009073,
					28.75940624281215
				],
				[
					-22.757317680116444,
					29.609234789291982
				],
				[
					-30.97916791317034,
					29.022767923282853
				],
				[
					-38.2481220634486,
					26.80955346593135
				],
				[
					-38.72310589095063,
					25.034613115238106
				],
				[
					-40.000144932039134,
					16.51084853956341
				],
				[
					-41.407060639430384,
					10.35744942603496
				],
				[
					-42.55753315151403,
					1.4360419335066912
				],
				[
					-42.43170618471623,
					-1.5519563810449657
				]
			]
		},
		{
			"type": "ellipse",
			"version": 675,
			"versionNonce": 911806372,
			"isDeleted": false,
			"id": "wJX0t2OusxvO3TcV7ebte",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2504.6979168480907,
			"y": 97.89415396124609,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.642978666684277,
			"height": 2.5527189301680524,
			"seed": 1179959929,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 745,
			"versionNonce": 1128017052,
			"isDeleted": false,
			"id": "Hvh-6VxCu-7-iLgNur10j",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2508.1030929770054,
			"y": 101.1051588119485,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 7.285420627783487,
			"height": 4.459022596024318,
			"seed": 124259161,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.6310843264044677,
					0.9144688584038597
				],
				[
					1.3081806026192695,
					1.5897143357005392
				],
				[
					2.87126738541392,
					1.8812532699922566
				],
				[
					4.865485800433121,
					1.891382583600757
				],
				[
					5.572568285237678,
					2.5835073470309293
				],
				[
					5.560789583181538,
					3.583791219037782
				],
				[
					4.649071882934234,
					4.114229100273402
				],
				[
					1.5355915318077031,
					4.046793608632854
				],
				[
					-0.4328844476705886,
					2.762406659164237
				],
				[
					-1.4508107881883754,
					1.5399441753810699
				],
				[
					-1.7128523425458082,
					0.15697387718474826
				],
				[
					-0.9278936827918913,
					-0.3447934957509159
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 742,
			"versionNonce": 1063222052,
			"isDeleted": false,
			"id": "N6JeTSTd_qh6tY3_3zGjr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2530.417157712185,
			"y": 99.61017252035519,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 2.642978666684277,
			"height": 2.5527189301680524,
			"seed": 1558132793,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 781,
			"versionNonce": 79968540,
			"isDeleted": false,
			"id": "ydhgcXfw3-dUcqCiYRVpA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2533.880299521859,
			"y": 103.4251818145422,
			"strokeColor": "#000000",
			"backgroundColor": "#868e96",
			"width": 7.285420627783487,
			"height": 4.459022596024318,
			"seed": 1486735641,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.6310843264044677,
					0.9144688584038597
				],
				[
					1.3081806026192695,
					1.5897143357005392
				],
				[
					2.87126738541392,
					1.8812532699922566
				],
				[
					4.865485800433121,
					1.891382583600757
				],
				[
					5.572568285237678,
					2.5835073470309293
				],
				[
					5.560789583181538,
					3.583791219037782
				],
				[
					4.649071882934234,
					4.114229100273402
				],
				[
					1.5355915318077031,
					4.046793608632854
				],
				[
					-0.4328844476705886,
					2.762406659164237
				],
				[
					-1.4508107881883754,
					1.5399441753810699
				],
				[
					-1.7128523425458082,
					0.15697387718474826
				],
				[
					-0.9278936827918913,
					-0.3447934957509159
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 701,
			"versionNonce": 1133278884,
			"isDeleted": false,
			"id": "p0vh2wvZIf5UC5hPODQJ8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2483.769601663751,
			"y": 60.04102330892751,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 100.91260311771457,
			"height": 53.47338087092163,
			"seed": 68632057,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.000179356303235,
					5.814509891167719
				],
				[
					5.445749910308372,
					3.812847998381813
				],
				[
					17.3984270647495,
					7.468497029769262
				],
				[
					49.059875408173426,
					11.30380202343599
				],
				[
					82.67081271158592,
					2.9003989603855302
				],
				[
					92.1131075842521,
					-15.804597695395508
				],
				[
					88.47556589851557,
					-37.20806325647923
				],
				[
					40.965183155083025,
					-41.11840399310859
				],
				[
					-0.32114246298746807,
					-42.169578847485646
				],
				[
					-8.799495533462462,
					-11.806052237148247
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 355,
			"versionNonce": 1654044060,
			"isDeleted": false,
			"id": "hXGabmQ_wJj-WZxogBQr9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2473.9555467196146,
			"y": 34.52573757123294,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1.4304999031195917,
			"height": 15.413182302720175,
			"seed": 1850676953,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4304999031195917,
					15.413182302720175
				]
			]
		},
		{
			"type": "line",
			"version": 508,
			"versionNonce": 1066271268,
			"isDeleted": false,
			"id": "tb0__RdGjOh3USrUSO7zq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2465.158061480389,
			"y": 50.068738176187665,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.394656708824775,
			"height": 15.110942484565808,
			"seed": 2044253113,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8749333360394176,
					-14.652242658102809
				],
				[
					3.5641487989900007,
					-7.758331323822129
				],
				[
					4.394656708824775,
					0.45869982646299956
				]
			]
		},
		{
			"type": "line",
			"version": 575,
			"versionNonce": 1239786012,
			"isDeleted": false,
			"id": "4kFd71iS8j_9XwQOjbOSy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2456.7095541755266,
			"y": 50.61561332922692,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 5.489171285985979,
			"height": 16.387794505027067,
			"seed": 1792537753,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.09912987876119499,
					-15.432896577314176
				],
				[
					1.134237076765621,
					-12.03684822312271
				],
				[
					2.4588462415465373,
					-7.108838080413604
				],
				[
					5.489171285985979,
					-14.392557061897644
				],
				[
					5.013383141982225,
					-9.439463150321426
				],
				[
					4.7338069009332235,
					0.9548979277128917
				]
			]
		},
		{
			"type": "line",
			"version": 321,
			"versionNonce": 1783766436,
			"isDeleted": false,
			"id": "-TOaXfeMzs5z0-fLsxLjR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2464.1986661113046,
			"y": 43.52518634322793,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.000322505271025,
			"height": 0.1607810794299067,
			"seed": 889190777,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.000322505271025,
					-0.1607810794299067
				]
			]
		},
		{
			"type": "line",
			"version": 701,
			"versionNonce": 832765596,
			"isDeleted": false,
			"id": "LWWl9PfrgtYYoyALDYgra",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2439.4137704278937,
			"y": 38.2160197915761,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.002546450026202,
			"height": 14.080297303138723,
			"seed": 160719449,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.5925415776045029,
					-0.4381362989672291
				],
				[
					-2.6350857211441263,
					0.3784063280714161
				],
				[
					-3.317651401275008,
					4.7710494765437765
				],
				[
					-3.9318634343834913,
					8.788785625908307
				],
				[
					-2.8194989066154648,
					13.308718349315054
				],
				[
					-0.8646600490481752,
					13.642161004171493
				],
				[
					-0.3701875874864351,
					12.162104452580504
				],
				[
					0.07068301564271032,
					7.466796388428519
				],
				[
					-1.8696731310237034,
					6.885963178822568
				]
			]
		},
		{
			"type": "line",
			"version": 751,
			"versionNonce": 1829161252,
			"isDeleted": false,
			"id": "XOGI8HnjezF40d1qFYvrm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2435.230997324673,
			"y": 50.970124177850536,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.1522530391503905,
			"height": 16.383515265311253,
			"seed": 627617593,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.8088528087734421,
					-14.510067132593717
				],
				[
					3.1522530391503905,
					-10.42832083046878
				],
				[
					2.0331325509785056,
					-6.671485837653201
				],
				[
					0.23806516621860546,
					-6.063576026100666
				],
				[
					1.848642863026959,
					-5.226543924459621
				],
				[
					2.83100857285603,
					-3.4083912568046744
				],
				[
					2.9313059623736515,
					1.8734481327175387
				]
			]
		},
		{
			"type": "ellipse",
			"version": 453,
			"versionNonce": 1652607772,
			"isDeleted": false,
			"id": "1rFz-PbYvB1UQ6OzQbWwP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.06135700878540096,
			"x": -2429.1760595854776,
			"y": 38.10251286133503,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.908430084326565,
			"height": 14.364458306502803,
			"seed": 1591762969,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 516,
			"versionNonce": 454689956,
			"isDeleted": false,
			"id": "-3COG5DvgZYkmSmNTDo2y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.06135700878540096,
			"x": -2422.2906516829644,
			"y": 38.462657624688845,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 3.908430084326565,
			"height": 14.364458306502803,
			"seed": 1945040121,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 320,
			"versionNonce": 1055983516,
			"isDeleted": false,
			"id": "1dyLwVuNw52cdQKUyFAil",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2415.286091118253,
			"y": 39.54779738949263,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 4.762833373975349,
			"height": 0.23816277283122952,
			"seed": 404221401,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.762833373975349,
					0.23816277283122952
				]
			]
		},
		{
			"type": "line",
			"version": 353,
			"versionNonce": 708431908,
			"isDeleted": false,
			"id": "XxCrsikF3Bm6oz9zV142g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2413.2238586066283,
			"y": 39.58404637500972,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 0.46141547607925937,
			"height": 13.16510868494743,
			"seed": 1114557113,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.46141547607925937,
					13.16510868494743
				]
			]
		},
		{
			"type": "image",
			"version": 299,
			"versionNonce": 187020316,
			"isDeleted": false,
			"id": "Z2xgyg8oDPl8Xay6l4jnU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1173.158020053483,
			"y": 2094.258463915642,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 181.19938138699288,
			"height": 54.35981441609787,
			"seed": 2055423268,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b1fae05270cc9149254934120f48156dc656ba3d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 429,
			"versionNonce": 1123242524,
			"isDeleted": false,
			"id": "vY0OCyicyI2As7ksxe5yK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1139.5883435048493,
			"y": 2438.321148229824,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 225.4214025647381,
			"height": 40.14353744303555,
			"seed": 1100682268,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755571875,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c99652a216ca3f7a65759d66c01cccddde3c1df2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 326,
			"versionNonce": 620602268,
			"isDeleted": false,
			"id": "jsX15bnQjVfhA0GmLzxRj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1137.0832300072818,
			"y": 2531.093864388471,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 249.00090069279727,
			"height": 41.3321333133793,
			"seed": 863735204,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755574806,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b57d88f59b8bcc44e21c20627905c316c694dc7a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 427,
			"versionNonce": 2107053860,
			"isDeleted": false,
			"id": "EdeUSmGYUI7Ja7g_g_5uh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1136.5777180813855,
			"y": 2000.9202941119095,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 238.5042739768383,
			"height": 38.51621815775028,
			"seed": 529798812,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755547118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d59696b75add2c6287b54f5515b97221d1f84427",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 238,
			"versionNonce": 269426980,
			"isDeleted": false,
			"id": "z2XORFs683A1Q8Fp-Yb7j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1563.7958461264982,
			"y": 2283.6225938325993,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 416.6655194096313,
			"height": 55.23955884517591,
			"seed": 2075050660,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707755836643,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					281.3303115473002,
					-55.23955884517591
				],
				[
					416.6655194096313,
					-11.79624287473598
				]
			]
		},
		{
			"type": "text",
			"version": 709,
			"versionNonce": 2014555164,
			"isDeleted": false,
			"id": "GkBdcfmh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1707.880013103842,
			"y": 2525.0858374250147,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1017.39892578125,
			"height": 200,
			"seed": 118644132,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707755841623,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "If we minimize the distance between the inferred distributions by representing them in a way\nthat there is no difference between the domains\n+\nminimize the distance between domain Q and its true distribution (by predicting correctly)\n+\nminimize the distance between domain P and its true distribution (by predicting correctly)\n=\nWe minimize the distance between the true domains P and Q such that our model is invariant to them!",
			"rawText": "If we minimize the distance between the inferred distributions by representing them in a way\nthat there is no difference between the domains\n+\nminimize the distance between domain Q and its true distribution (by predicting correctly)\n+\nminimize the distance between domain P and its true distribution (by predicting correctly)\n=\nWe minimize the distance between the true domains P and Q such that our model is invariant to them!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If we minimize the distance between the inferred distributions by representing them in a way\nthat there is no difference between the domains\n+\nminimize the distance between domain Q and its true distribution (by predicting correctly)\n+\nminimize the distance between domain P and its true distribution (by predicting correctly)\n=\nWe minimize the distance between the true domains P and Q such that our model is invariant to them!",
			"lineHeight": 1.25,
			"baseline": 193
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#a5d8ff",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 2883.394546105534,
		"scrollY": 248.23420669258562,
		"zoom": {
			"value": 1.0500000000000003
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