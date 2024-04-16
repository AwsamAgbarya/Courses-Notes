---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Representation Learning ^XOqDgFLX

Motivation ^6R68N6Eb

Labeled data is scarce, often times we find
ourselves having a lot more unlabeled data
than labeled because labelling correctly is
expensive and sometimes even requires 
experts, thus we want to be able to make
use of of unlabeled data. ^XX0hnDx6

Can we make use of patterns in the data
in order to represent it in such a way
that helps us get over the hurdle
of not having labels? ^whO7Gmoq

Learn semantic representations of data from patterns in
observation space and encode it into latent space ^uIbttZDj

Since we have a large amount of unlabeled data
we can use this in order to greatly improve and generalize
our feature extractor to be actually meaningful ^e1zWpLd0

By mapping the data to latent space we can
cluster the data according to "distances" in 
latent space in order to measure similarity
and dissimilarity  ^m1HQPOF2

By mapping data into latent space
We have a general purpose space that
represents different types of modalities
(Text, Image...) which we can use to corrolate
them together (Obviously the way we map each
modality to the latent space will be different) ^x44rMRro

By mapping our data into latent space
we can Use this space to search for semantics
/ features and get the K-closest results ^X4GrHQxl

Pretext Task ^wg04LwkJ

Pretext tasks are tasks
that use unlabeled data
alongside an objective goal
in order to define right and
wrong solutions.
These objectives are
performed on a property
that is inherent in
the dataset itself. ^M2a3KLlx

Re-arrange ^ywminjdp

Fill in
the blank ^80zRGUwH

Color ^DEy6N4TM

Self-Supervised Learning ^QsQPcv8s

Usually in supervised learning we have labeled data and we learn
by telling our model to adjust its parameters such that it outputs
as close as possible to our label.
supervised learning usually learns both the features and
the given task together.

Self supervised learning requires pretext tasks (so unlabeled data)
learns by fine tuning its feature extractor.
Our feature extractor's job is to represent all the meaningful semantic
details of the data in feature/latent space such that the latent space
accurately describes similarity and difference.

We then use This latent space in order to preform another (downstream)
task according to our description of the data.
Self-supervised learning separates the task of learning features from the
actual downstream task.
Hence the name "self-supervised" I.e we developed an understanding of the
data and "labeled" it accordingly to be able to use it for something else. ^tyCIcf92

Encode data into
latent space ^lqsiSjic

Feature extractor ^BGWQeaxI

Target Task ^5s0Y3vqW

output ^w6mOEkrh

The first part teaches the model
lots of semantic information
about the general purpose data
(for example animals)
This part does not change its
parameters after we are done
learning and have moved on to
the next part ^FySJECv8

The second part (Linear Probing)
 uses all that learnt features
and semantics about animals in order to
to vastly reduce the amount of labeled
data on the current task (Classifying
the name of an animal) ^YBwC2LUC

In-painting/Masking ^bWgorpsM

Occlude a random part of the image with a mask
The model has to predict the missing content ^2XsFKIOj

Fill in the blanks ^QD7y5RbU

This works really well in vision, especially with a high masking
ratio (75%) ^BQpokJpj

This masking Technique can also be done with text
which s used to train language models in NLP.
 ^ZSXvoddN

it is necessary to learn
semantic properties of an
image in order to be able to
understand whats missing
and fill it out correctly ^nVKbNrTV

words/tokens are already separate semantic entities which
makes the task generally better suited for masked predictions. ^WCTdpIBH

Contrastive Learning ^Li73Gg6F

When learning semantics, instead of only correlating
and changing your result according to one pretext task
we can try to use multiple objectives to learn about the
semantics in different ways ^UA1hW2Gj

Self-supervised learning ^hqjYCgdl

Self-supervised learning ^eVNPh5KX

How similar
are they? ^56e9Sc54

By training the model on two different augmentations of the data
and telling it that theyre the same object thus their encoding needs to
be really close to each other, we can teach the model the semantics
of said object. ^ftt3iT3N

Problem: Representation collapse!
The optimal result for this model is to always encode into a constant
number, by encoding a constant number, both encodings are always as close
as possible to each other ^UO9Zqeqe

Contrastive learning solves this issue by not only making sure that both augmentations
of the same object are as close as possible to each other in latent space, but also that
every two different objects representations in latent space is as far as possible from eachother

this will turn our latent space into clusters of similar objects ^lDECn21z

Features ^zJmlMmMC

Features ^gybi8t3w

Animal
space ^pz955cP0

Furniture
space ^CF2oy3PA

Dog
space ^EfmMhD6w

referred to
as views ^Jk8S579e

How similar the first is
to the second ^96RQ3iZw

How similar the second is
to the first ^bWZB0n4y

Similarity function usually
cosine similarity ^okFul1fL

Similarity result normalized using softmax
to reflect a ratio according to other samples ^DmsqZLpJ

Log keeps the same ratios
but turns the probability distribution
to a concave one to navigate easily
(I think) ^hc7fmOAj

High similarity will result in high
ratio, thus high log, and we want high
similarity to not affect our loss unlike
low similarity thus we negate it ^0X1HZZMe

The representations (Not the encoding) will be saved
after pretraining in order to be transferred into assisting
in the downstream task (Transfer Learning)

In cases where we have a very large amount of labeled data
the transfer learning in self-supervised models is slightly better
than supervised, whereas in models where data is scarce
the difference is drastically in favour of self-supervised ^WFcHREc8

needs a lot of negatives samples in one batch to learn good
representation, because the larger the batch the more the model learns
where not to put the representation we have gotten
therefore, training with multiple GPUs or TPUs is necessary

THe alternative would be storing representations in a
memory bank and use them as negatives
in future iterations ^U6GXoC0n

Augmentation of views
which ones do we pick?

This is very task data and domain specific and you
might have to test and handcraft your own.

for example SimCLR optimized its augmentation on ImageNet
performance which lead to
random cropping followed by resize back to the original size,
random color distortions, and random Gaussian blur ^ntXJ0Ukw

Performance ^oHiOoCON

Based off of ImageNet ^rN4n2ez5

Image-Text Models ^S1Uxa7AK

As we have mentioned before, self-supervised representation of
the data allows us to mix and match different modalities of data
with each other, a good example of this is matching an image to a caption/word
Obviously we have different encoders for different modalities
This is great as it allows to attach naunced text to an image to get a better
    understanding of the entire image not just one object in it (and thus generalize) ^IqqC5UHX

(Both encoded into the same dimensions) ^DJN1WoW3

Contrastive Pre-training Stage ^sbXkmyVy

Create dataset classifier from label text ^HH6mysEN

Zero-shot classification ^YoBtOjfs

Zero-shot classification term comes
from N-shot classification.

N-shot classification means that you need
N training examples in order for your model
to perform on a particular new domain
The smaller the number N, the more robust a model
is because it requires little to no extra supervised
dataset in order to perform the downstream task ^3YSc8HGj

This allows things like
image Search
image generation
zero-shot image classification ^WozFX0VN

Because our model already learnt the semantics
of a picture of a dog AND the semantics of the
word dog, it does not need an extra labelled data
of dogs in order to be able to associate the
word dog to the image of a dog ^xltrGmLX

This is not the only solution to Representation Collapse ^S55F5emS

Non-contrastive learning ^MZ2RBCh7

Bootstrap your own latent (BYOL) uses the idea of predicting the
representations of a random initialized model to improve the
representations.
This on its own is not good, but we build upon this idea moving forward.
Both networks have the exact same architecture but different weights
and the weight of the target network after each iteration is the exponential
moving average of the online network. ^ubHmK3nt

%%***>>>text element-link:[[Regularization]]<<<***%%This idea is very similar to
the auxiliary domain critic described
here ^20vANlVm

Why are crops and color distortions important?

For starters, Cropping images is intuitively very good
in making the model to associate different parts of an object
to belong to the same object because it associates different
features of objects to be subparts









Coloration is important with cropping images because if you take two
cropped versions of the same dog, the RGB values in each pixel will be
somewhat similar or have a similar curve.
Neural nets may exploit this shortcut to solve the predictive task.
Therefore, it is critical to compose cropping with color distortion
in order to learn generalizable features. ^gDGlQmRA

This is quite a bit requirement as it
not everyone has a lot of resources
to run such large batches, perhaps
there are better ways? ^APXEePKH

Only train
this network ^I16agvne

Randomly initialize
this network and freeze
its weights which will result
in a random projection
of the input image ^uTC3cDoz

This model does not guarantee non-collapse but instead making it extremely implausible
and removed the need for negative samples and "important" combinations of different augmentations ^Q3I5gFZS

DinoV2 and iBOT ^GLa3SnDQ

Dinov2 takes the idea of BYOL and builds upon it using transformers
which results in something great that i wont get into now :] ^g7HL6bSM


# Embedded files
68ed0870d4486a1971db79b56ab1b7d5d99cf209: [[Pasted Image 20240416201044_141.png]]
3187e5f535cff0aaa01c3b6765c034797449d321: [[Pasted Image 20240416203626_351.png]]
7af7db0fe8f12cb0229995fc05f3cc483f14c204: [[Pasted Image 20240416203711_363.png]]
5067d7a646624a43e96765ac79fae9d9002bb47f: [[Pasted Image 20240416203811_367.png]]
e8e22ff39be5ff6b28c879752b38a3faf43251e3: [[Pasted Image 20240416203916_373.png]]
6a758ac29208db3d41d8f7912f72596729642bf0: [[Pasted Image 20240416204021_389.png]]
628ef8b824a61ee3577f37ac993257563acb977c: [[Pasted Image 20240416204051_407.png]]
8a14068ec4715e1db9baf1da3152a60c1b0ebd81: [[Pasted Image 20240416210525_552.png]]
d0a9d19100ef3cd08b1be324b71b3b9d2c00e3cc: [[Pasted Image 20240416210708_624.png]]
9a0582fead62dcfdc21de0dfd0dfcb9c3e4c105f: [[Pasted Image 20240416220150_088.png]]
0220811c694bbc4649363c0ba08f62fdf9a5818f: [[Pasted Image 20240416220636_116.png]]
9444c80b3a42b4f0aa8c0fd6c19faf384cd6adf5: [[Pasted Image 20240416221147_182.png]]
da4dc7fe07f90efe656d5a0b241750dcefc623ff: [[Pasted Image 20240416221218_200.png]]
00ce334e0731ae23b97d07760b1513042e4daa00: [[Pasted Image 20240416221248_203.png]]
cbe5fdb02d4582f3742a71d80e984064768eade4: [[Pasted Image 20240416222255_308.png]]
90e063de1f2f13e275058785dd97657c52f8346d: [[Pasted Image 20240416222310_326.png]]
aa8e3cef428f5c97511a8dc3a406255c9f746fbf: [[Pasted Image 20240416222355_328.png]]
f1e3004e06538d525acd816a7daad177b4b3b018: [[Pasted Image 20240416222410_329.png]]
f7515745eac029dbd3121589d1c37608aa75ff80: [[Pasted Image 20240416222455_331.png]]
edc4764348121c501d935d68654f965c54a9ce9d: [[Pasted Image 20240416224545_396.png]]
17c893838b9b90d50ccd9dd6c8cd3b460beba4c4: [[Pasted Image 20240416224847_444.png]]
25dc7135aa9762b3f29c542557c6e5065d66e21d: [[Pasted Image 20240416225341_596.png]]
da8efcd14d7a38006291a91bf23878536a82b4fb: [[Pasted Image 20240416230128_712.png]]
b6dc79d7ad78e828f2bb3ba46192eef566916c7e: [[Pasted Image 20240416230858_787.png]]
0a1200e495bea4dc2b2829782f47b103247b4a02: [[Pasted Image 20240416231547_835.png]]
770d0d99622d8b3f35d5d8d1f9e74b1f064c4183: [[Pasted Image 20240416233316_088.png]]
f0878ffe6dabcb5f51513bca659d37c805f26f90: [[Pasted Image 20240416235608_213.png]]
c60de26b76fe746163a5031ea329698fce3eb6fd: [[Pasted Image 20240416235849_340.png]]
d14b71bafd79ec96f2c400d3e55432a299246434: [[Pasted Image 20240417001726_479.png]]
56c1246d3a64f87f221b7480740f9e27e43e7f39: [[Pasted Image 20240417002428_528.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.23",
	"elements": [
		{
			"id": "kInSkD53Rhldgp4UvSYI_",
			"type": "image",
			"x": 983.1591715110517,
			"y": 1840.803248090323,
			"width": 116.28314894016285,
			"height": 93.49793732350932,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2047920783,
			"version": 317,
			"versionNonce": 1375564655,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322178,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "00ce334e0731ae23b97d07760b1513042e4daa00",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "x8vpe8GwBYZWxoHEFBs2s",
			"type": "image",
			"x": 984.7946411342664,
			"y": 1722.7123728484808,
			"width": 111.64530376785297,
			"height": 82.45698905730318,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1607660783,
			"version": 352,
			"versionNonce": 1834548993,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "15KVaHxv-F6U2OkPMrzBj",
					"type": "arrow"
				}
			],
			"updated": 1713301322178,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "da4dc7fe07f90efe656d5a0b241750dcefc623ff",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "LJllZmVd51wVZ1CQZpOuv",
			"type": "image",
			"x": -649.2452813114162,
			"y": -18.502006664816975,
			"width": 830,
			"height": 215,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 506621761,
			"version": 72,
			"versionNonce": 1878732175,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322178,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "68ed0870d4486a1971db79b56ab1b7d5d99cf209",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "XOqDgFLX",
			"type": "text",
			"x": -453.1515952643318,
			"y": -574.8538074124058,
			"width": 420.6961669921875,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": null,
			"seed": 2008798145,
			"version": 306,
			"versionNonce": 46364385,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322178,
			"link": null,
			"locked": false,
			"text": "Representation Learning",
			"rawText": "Representation Learning",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 32,
			"containerId": null,
			"originalText": "Representation Learning",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 874,
			"versionNonce": 377267119,
			"isDeleted": false,
			"id": "scflCi9MDW2_L5PVb3dqQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -524.3296756042332,
			"y": -764.5396287252845,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.2054244668892746,
			"height": 81.92428347898584,
			"seed": 378253839,
			"groupIds": [
				"XgaKTANad-dz3fumovZyN",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322178,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2054244668892746,
					81.92428347898584
				]
			]
		},
		{
			"type": "line",
			"version": 877,
			"versionNonce": 399766209,
			"isDeleted": false,
			"id": "VFTuCE-HGNw7pste1yDHc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -521.0329389578742,
			"y": -680.2501385363021,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 14.258299831927323,
			"height": 38.26560725851409,
			"seed": 294164527,
			"groupIds": [
				"XgaKTANad-dz3fumovZyN",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322178,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					14.258299831927323,
					16.0366265728015
				],
				[
					10.279007799465164,
					38.26560725851409
				]
			]
		},
		{
			"type": "line",
			"version": 899,
			"versionNonce": 1974097359,
			"isDeleted": false,
			"id": "7cDaGR2Y6atapEdvcU1tv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -523.9191394833553,
			"y": -681.2071232867962,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 2.7149140336203086,
			"height": 41.152219625069336,
			"seed": 71547471,
			"groupIds": [
				"XgaKTANad-dz3fumovZyN",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322178,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.7688958227821843,
					24.640007381376137
				],
				[
					-0.9460182108381245,
					41.152219625069336
				]
			]
		},
		{
			"type": "line",
			"version": 1114,
			"versionNonce": 1361703585,
			"isDeleted": false,
			"id": "57qsH_9fVpJQqQJ5ZQa6v",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -523.2938334240082,
			"y": -746.3499208873363,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 22.841430892366258,
			"height": 16.95219849944301,
			"seed": 1402312815,
			"groupIds": [
				"XgaKTANad-dz3fumovZyN",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322178,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.18651040904472,
					4.494414512469318
				],
				[
					11.36960868432226,
					16.95219849944301
				],
				[
					-6.654920483321541,
					16.343910262428004
				]
			]
		},
		{
			"type": "line",
			"version": 1207,
			"versionNonce": 614253551,
			"isDeleted": false,
			"id": "R_rCr7NbNV7Vn1IHLbwjw",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -525.2577428198778,
			"y": -749.3622554248768,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 24.45227004168292,
			"height": 23.403636280171128,
			"seed": 893825679,
			"groupIds": [
				"XgaKTANad-dz3fumovZyN",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-9.84173002755563,
					23.403636280171128
				],
				[
					5.972230607880152,
					21.04307785046711
				],
				[
					14.610540014127288,
					10.735452595356795
				]
			]
		},
		{
			"type": "line",
			"version": 1204,
			"versionNonce": 326432385,
			"isDeleted": false,
			"id": "jRaV2SxV43Dl8KZ2soluk",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -507.717021759883,
			"y": -777.9291593727027,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"width": 32.932053466043534,
			"height": 43.90284351522353,
			"seed": 303007919,
			"groupIds": [
				"XgaKTANad-dz3fumovZyN",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.037133019667525,
					21.986841076106213
				],
				[
					-32.932053466043534,
					-3.0474701178143424
				],
				[
					-4.921110791296756,
					-21.91600243911732
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 751,
			"versionNonce": 1130130959,
			"isDeleted": false,
			"id": "yurSYtTmTv-_q0c1KXqW3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -548.186833680412,
			"y": -706.4499504223706,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.2054244668892746,
			"height": 76.89107434939548,
			"seed": 1510117711,
			"groupIds": [
				"nRxaYx5sMWTz4QvCrdtUZ",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2054244668892746,
					76.89107434939548
				]
			]
		},
		{
			"type": "line",
			"version": 747,
			"versionNonce": 24411745,
			"isDeleted": false,
			"id": "2-TAu2XSLXSqBnuAzIH0v",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -544.8900970340528,
			"y": -627.1936693629787,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 10.279007799465164,
			"height": 38.26560725851409,
			"seed": 1499565935,
			"groupIds": [
				"nRxaYx5sMWTz4QvCrdtUZ",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.3489711997136835,
					25.74352989415452
				],
				[
					10.279007799465164,
					38.26560725851409
				]
			]
		},
		{
			"type": "line",
			"version": 775,
			"versionNonce": 1558303791,
			"isDeleted": false,
			"id": "ONo0lF38gtfg3l2rp9VCt",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -548.1358124973622,
			"y": -628.1506541134731,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.2643133068082566,
			"height": 41.152219625069336,
			"seed": 746310031,
			"groupIds": [
				"nRxaYx5sMWTz4QvCrdtUZ",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.2643133068082566,
					24.640007381376137
				],
				[
					-0.9460182108381245,
					41.152219625069336
				]
			]
		},
		{
			"type": "line",
			"version": 876,
			"versionNonce": 972556865,
			"isDeleted": false,
			"id": "ON5qtROyKyvEDFITww_xA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -547.6820399533602,
			"y": -693.2934517140131,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 23.715867809566895,
			"height": 38.633836407757244,
			"seed": 1773475567,
			"groupIds": [
				"nRxaYx5sMWTz4QvCrdtUZ",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.384935489123276,
					28.58191534693801
				],
				[
					23.715867809566895,
					38.633836407757244
				]
			]
		},
		{
			"type": "line",
			"version": 988,
			"versionNonce": 152401487,
			"isDeleted": false,
			"id": "jlAeKZ1ZIZWyBD2V68sQK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -549.4744158338846,
			"y": -696.3057862515539,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 11.998819654523029,
			"height": 57.47239451298276,
			"seed": 541157167,
			"groupIds": [
				"nRxaYx5sMWTz4QvCrdtUZ",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.998819654523029,
					26.63927072062204
				],
				[
					-9.83647575816935,
					57.47239451298276
				]
			]
		},
		{
			"id": "GFsBTQm_zz-XIoLEmoJ4l",
			"type": "line",
			"x": -531.5741798360617,
			"y": -724.8726901993796,
			"width": 30.868261233617087,
			"height": 44.98138832870696,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"nRxaYx5sMWTz4QvCrdtUZ",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1865644207,
			"version": 1069,
			"versionNonce": 1440684577,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-30.037133019667525,
					21.986841076106213
				],
				[
					-28.25835927428095,
					-3.0474701178143424
				],
				[
					0.8311282139495616,
					-22.99454725260075
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				0.9228987735282317,
				2.153430471565798
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "line",
			"version": 954,
			"versionNonce": 1322243183,
			"isDeleted": false,
			"id": "MCpeFJZ3K5KHDm_lt-59Z",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -464.64351748311356,
			"y": -735.2725955104697,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 12.22193021766494,
			"height": 65.964078683216,
			"seed": 469975343,
			"groupIds": [
				"KxuDvenuGJptweIVeT905",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.149068871126531,
					48.91697292393011
				],
				[
					9.072861346538412,
					65.964078683216
				]
			]
		},
		{
			"type": "line",
			"version": 1135,
			"versionNonce": 639184385,
			"isDeleted": false,
			"id": "t4MFlcyEcpOzRc9Uj4ey1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -455.81493158451303,
			"y": -669.1287092504931,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 21.013511724250353,
			"height": 28.447596585436024,
			"seed": 461456207,
			"groupIds": [
				"KxuDvenuGJptweIVeT905",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					17.5916757897218,
					-17.51573356766348
				],
				[
					21.013511724250353,
					10.931863017772546
				]
			]
		},
		{
			"type": "line",
			"version": 1113,
			"versionNonce": 1171877519,
			"isDeleted": false,
			"id": "1Gkc3jrqh8aDeJvYSe6Nl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -454.38947179300635,
			"y": -669.3617228418658,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 23.65060010723741,
			"height": 22.618282398180686,
			"seed": 473563503,
			"groupIds": [
				"KxuDvenuGJptweIVeT905",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.431757340288288,
					22.618282398180686
				],
				[
					17.218842766949123,
					16.48141131181724
				]
			]
		},
		{
			"type": "line",
			"version": 1284,
			"versionNonce": 832947681,
			"isDeleted": false,
			"id": "E31ntmBy0Nn4AWwcEPnFW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -464.1387237560616,
			"y": -721.679016975465,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 44.05448854433752,
			"height": 37.59408983764892,
			"seed": 527825807,
			"groupIds": [
				"KxuDvenuGJptweIVeT905",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					27.357227401309277,
					-0.9715844572412188
				],
				[
					44.05448854433752,
					-37.59408983764892
				]
			]
		},
		{
			"type": "line",
			"version": 1321,
			"versionNonce": 2028651695,
			"isDeleted": false,
			"id": "FLZPdqHE19ibP3QVgkLbN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -465.49401980993866,
			"y": -724.9782428454814,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 37.199037590264524,
			"height": 51.34033443033582,
			"seed": 1768796591,
			"groupIds": [
				"KxuDvenuGJptweIVeT905",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-27.74902534930628,
					-3.8386388010941017
				],
				[
					-37.199037590264524,
					-51.34033443033582
				]
			]
		},
		{
			"type": "line",
			"version": 1226,
			"versionNonce": 1939104193,
			"isDeleted": false,
			"id": "XIM8rc8qdzXWdaZJn4uN1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -448.03086363876326,
			"y": -753.2582554608312,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"width": 30.868261233617087,
			"height": 44.98138832870696,
			"seed": 592028623,
			"groupIds": [
				"KxuDvenuGJptweIVeT905",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.037133019667525,
					21.986841076106213
				],
				[
					-28.25835927428095,
					-3.0474701178143424
				],
				[
					0.8311282139495616,
					-22.99454725260075
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 753,
			"versionNonce": 128734927,
			"isDeleted": false,
			"id": "axL2a8MYJIMrltb0QrY0T",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -502.7867795398928,
			"y": -683.6522715333997,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.2054244668892746,
			"height": 76.89107434939548,
			"seed": 1991897263,
			"groupIds": [
				"tZ_Cy-dLfF_Z1OnsyfPAL",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2054244668892746,
					76.89107434939548
				]
			]
		},
		{
			"type": "line",
			"version": 749,
			"versionNonce": 1493467553,
			"isDeleted": false,
			"id": "4phq3Fwxya4yvGFHfKi-s",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -499.4900428935341,
			"y": -604.3959904740076,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 10.279007799465164,
			"height": 38.26560725851409,
			"seed": 1521877711,
			"groupIds": [
				"tZ_Cy-dLfF_Z1OnsyfPAL",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.3489711997136835,
					25.74352989415452
				],
				[
					10.279007799465164,
					38.26560725851409
				]
			]
		},
		{
			"type": "line",
			"version": 777,
			"versionNonce": 146187503,
			"isDeleted": false,
			"id": "jaqn0gG4jQvzgqsBMEWAn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -502.7357583568429,
			"y": -605.3529752245021,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.2643133068082566,
			"height": 41.152219625069336,
			"seed": 631951599,
			"groupIds": [
				"tZ_Cy-dLfF_Z1OnsyfPAL",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.2643133068082566,
					24.640007381376137
				],
				[
					-0.9460182108381245,
					41.152219625069336
				]
			]
		},
		{
			"type": "line",
			"version": 878,
			"versionNonce": 2133173633,
			"isDeleted": false,
			"id": "_MLtnMmlRMZvKTuLcWOvB",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -502.28198581284136,
			"y": -670.4957728250424,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 23.715867809566895,
			"height": 38.633836407757244,
			"seed": 1897978639,
			"groupIds": [
				"tZ_Cy-dLfF_Z1OnsyfPAL",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.384935489123276,
					28.58191534693801
				],
				[
					23.715867809566895,
					38.633836407757244
				]
			]
		},
		{
			"type": "line",
			"version": 990,
			"versionNonce": 731000591,
			"isDeleted": false,
			"id": "h2Upwmqc4Qd19nk7qvFeh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -504.07436169336535,
			"y": -673.5081073625834,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 11.998819654523029,
			"height": 57.47239451298276,
			"seed": 294691119,
			"groupIds": [
				"tZ_Cy-dLfF_Z1OnsyfPAL",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.998819654523029,
					26.63927072062204
				],
				[
					-9.83647575816935,
					57.47239451298276
				]
			]
		},
		{
			"type": "line",
			"version": 1071,
			"versionNonce": 825707873,
			"isDeleted": false,
			"id": "S89IPuqu1Aaa24l9YVwi2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -486.17412569554295,
			"y": -702.0750113104089,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"width": 30.868261233617087,
			"height": 44.98138832870696,
			"seed": 945988431,
			"groupIds": [
				"tZ_Cy-dLfF_Z1OnsyfPAL",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.037133019667525,
					21.986841076106213
				],
				[
					-28.25835927428095,
					-3.0474701178143424
				],
				[
					0.8311282139495616,
					-22.99454725260075
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 750,
			"versionNonce": 448230703,
			"isDeleted": false,
			"id": "4Cl2htj565-hml7cdaBRs",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -476.1952025921411,
			"y": -648.4973053990836,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.2054244668892746,
			"height": 76.89107434939548,
			"seed": 1093120495,
			"groupIds": [
				"G4LEL1S_8_c92LeQRBuVi",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2054244668892746,
					76.89107434939548
				]
			]
		},
		{
			"type": "line",
			"version": 746,
			"versionNonce": 646510913,
			"isDeleted": false,
			"id": "BoKW-ZnZpyXTFPkhGy10h",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -472.89846594578194,
			"y": -569.2410243396915,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 10.279007799465164,
			"height": 38.26560725851409,
			"seed": 744070159,
			"groupIds": [
				"G4LEL1S_8_c92LeQRBuVi",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.3489711997136835,
					25.74352989415452
				],
				[
					10.279007799465164,
					38.26560725851409
				]
			]
		},
		{
			"type": "line",
			"version": 774,
			"versionNonce": 495908687,
			"isDeleted": false,
			"id": "I__WUhTOksLytKHZDLIX2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -476.1441814090911,
			"y": -570.1980090901864,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.2643133068082566,
			"height": 41.152219625069336,
			"seed": 1242120751,
			"groupIds": [
				"G4LEL1S_8_c92LeQRBuVi",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.2643133068082566,
					24.640007381376137
				],
				[
					-0.9460182108381245,
					41.152219625069336
				]
			]
		},
		{
			"type": "line",
			"version": 875,
			"versionNonce": 8005921,
			"isDeleted": false,
			"id": "MM6R0e5tqrLIefnT9CGwl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -475.69040886508947,
			"y": -635.3408066907266,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 23.715867809566895,
			"height": 38.633836407757244,
			"seed": 2065638479,
			"groupIds": [
				"G4LEL1S_8_c92LeQRBuVi",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.384935489123276,
					28.58191534693801
				],
				[
					23.715867809566895,
					38.633836407757244
				]
			]
		},
		{
			"type": "line",
			"version": 987,
			"versionNonce": 2054239599,
			"isDeleted": false,
			"id": "y4AGBwdflAKmOIJWijzUB",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -477.4827847456137,
			"y": -638.3531412282673,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 11.998819654523029,
			"height": 57.47239451298276,
			"seed": 1869857391,
			"groupIds": [
				"G4LEL1S_8_c92LeQRBuVi",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.998819654523029,
					26.63927072062204
				],
				[
					-9.83647575816935,
					57.47239451298276
				]
			]
		},
		{
			"type": "line",
			"version": 1068,
			"versionNonce": 142236929,
			"isDeleted": false,
			"id": "RDPT1u3m4Yv5hyapVRq6r",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -459.5825487477908,
			"y": -666.9200451760928,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"width": 30.868261233617087,
			"height": 44.98138832870696,
			"seed": 1204788367,
			"groupIds": [
				"G4LEL1S_8_c92LeQRBuVi",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.037133019667525,
					21.986841076106213
				],
				[
					-28.25835927428095,
					-3.0474701178143424
				],
				[
					0.8311282139495616,
					-22.99454725260075
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 928,
			"versionNonce": 413577103,
			"isDeleted": false,
			"id": "4YOttUBJta2pGNEO1SmTl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -580.9676518349604,
			"y": -740.0887110016199,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.5129753067599889,
			"height": 81.04576931017097,
			"seed": 971605103,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5129753067599889,
					81.04576931017097
				]
			]
		},
		{
			"type": "line",
			"version": 915,
			"versionNonce": 772347105,
			"isDeleted": false,
			"id": "ovF5MxtX5XlOqEZkGekKt",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -578.3633643487307,
			"y": -656.6777349814523,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 10.279007799465164,
			"height": 38.26560725851409,
			"seed": 37559951,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.3489711997136835,
					25.74352989415452
				],
				[
					10.279007799465164,
					38.26560725851409
				]
			]
		},
		{
			"type": "line",
			"version": 943,
			"versionNonce": 1650976175,
			"isDeleted": false,
			"id": "bY-OddiRSGSGW2NSBUqku",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -581.6090798120398,
			"y": -657.6347197319471,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.2643133068082566,
			"height": 41.152219625069336,
			"seed": 1297642671,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.2643133068082566,
					24.640007381376137
				],
				[
					-0.9460182108381245,
					41.152219625069336
				]
			]
		},
		{
			"type": "line",
			"version": 1044,
			"versionNonce": 1152766145,
			"isDeleted": false,
			"id": "kVuJAnXs3cwXz7R9TnKjG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -581.1553072680382,
			"y": -722.7775173324866,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 23.715867809566895,
			"height": 38.633836407757244,
			"seed": 1659111119,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.384935489123276,
					28.58191534693801
				],
				[
					23.715867809566895,
					38.633836407757244
				]
			]
		},
		{
			"type": "line",
			"version": 1156,
			"versionNonce": 1725781967,
			"isDeleted": false,
			"id": "eDwX7WsIELb-2bDXaRHBJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -582.9476831485623,
			"y": -725.7898518700276,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 11.998819654523029,
			"height": 57.47239451298276,
			"seed": 24663279,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.998819654523029,
					26.63927072062204
				],
				[
					-9.83647575816935,
					57.47239451298276
				]
			]
		},
		{
			"type": "line",
			"version": 1237,
			"versionNonce": 35655841,
			"isDeleted": false,
			"id": "3-MStc8zaMFH3Uqr3G5VE",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -565.0474471507395,
			"y": -754.356755817853,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"width": 30.868261233617087,
			"height": 44.98138832870696,
			"seed": 10346255,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.037133019667525,
					21.986841076106213
				],
				[
					-28.25835927428095,
					-3.0474701178143424
				],
				[
					0.8311282139495616,
					-22.99454725260075
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 900,
			"versionNonce": 1008698863,
			"isDeleted": false,
			"id": "3MruGwNKgXLeppZ92puOz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -593.0938462805747,
			"y": -682.2745947668691,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.2054244668892746,
			"height": 81.92428347898584,
			"seed": 949836463,
			"groupIds": [
				"tN9LJnWPb8LjvhSPFDtB9",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2054244668892746,
					81.92428347898584
				]
			]
		},
		{
			"type": "line",
			"version": 903,
			"versionNonce": 1006064769,
			"isDeleted": false,
			"id": "soS-0N2TkmPeVhijI7yv1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -589.7971096342153,
			"y": -597.9851045778861,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 14.258299831927323,
			"height": 38.26560725851409,
			"seed": 547105999,
			"groupIds": [
				"tN9LJnWPb8LjvhSPFDtB9",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					14.258299831927323,
					16.0366265728015
				],
				[
					10.279007799465164,
					38.26560725851409
				]
			]
		},
		{
			"type": "line",
			"version": 925,
			"versionNonce": 557248527,
			"isDeleted": false,
			"id": "4Z1CbssWt2zRjCBtmgYZD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -592.6833101596968,
			"y": -598.9420893283802,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 2.7149140336203086,
			"height": 41.152219625069336,
			"seed": 1631304431,
			"groupIds": [
				"tN9LJnWPb8LjvhSPFDtB9",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.7688958227821843,
					24.640007381376137
				],
				[
					-0.9460182108381245,
					41.152219625069336
				]
			]
		},
		{
			"type": "line",
			"version": 1140,
			"versionNonce": 1710955617,
			"isDeleted": false,
			"id": "NNED9MvmetYDJf8_SOFaJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -592.0580041003496,
			"y": -664.084886928921,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 22.841430892366258,
			"height": 16.95219849944301,
			"seed": 520389903,
			"groupIds": [
				"tN9LJnWPb8LjvhSPFDtB9",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.18651040904472,
					4.494414512469318
				],
				[
					11.36960868432226,
					16.95219849944301
				],
				[
					-6.654920483321541,
					16.343910262428004
				]
			]
		},
		{
			"type": "line",
			"version": 1233,
			"versionNonce": 1612453423,
			"isDeleted": false,
			"id": "w0ttLm_LfHQgkcv-nX9hS",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -594.0219134962192,
			"y": -667.0972214664607,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 24.45227004168292,
			"height": 23.403636280171128,
			"seed": 1500449583,
			"groupIds": [
				"tN9LJnWPb8LjvhSPFDtB9",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-9.84173002755563,
					23.403636280171128
				],
				[
					5.972230607880152,
					21.04307785046711
				],
				[
					14.610540014127288,
					10.735452595356795
				]
			]
		},
		{
			"type": "line",
			"version": 1230,
			"versionNonce": 1341843521,
			"isDeleted": false,
			"id": "CLK6tSZFZOFaErWf2xvi8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -576.4811924362242,
			"y": -695.6641254142875,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"width": 32.932053466043534,
			"height": 43.90284351522353,
			"seed": 216255823,
			"groupIds": [
				"tN9LJnWPb8LjvhSPFDtB9",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.037133019667525,
					21.986841076106213
				],
				[
					-32.932053466043534,
					-3.0474701178143424
				],
				[
					-4.921110791296756,
					-21.91600243911732
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 741,
			"versionNonce": 1874294863,
			"isDeleted": false,
			"id": "UizyV_EFOyz5S9IkEYGop",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -577.6037587488228,
			"y": -644.4409631528164,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.2054244668892746,
			"height": 76.89107434939548,
			"seed": 1997595439,
			"groupIds": [
				"MN5SLZWmhci12DfUnzhLa",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2054244668892746,
					76.89107434939548
				]
			]
		},
		{
			"type": "line",
			"version": 737,
			"versionNonce": 601241633,
			"isDeleted": false,
			"id": "QDjs2xznzqBR9Jtc82vlK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -574.3070221024635,
			"y": -565.1846820934243,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 10.279007799465164,
			"height": 38.26560725851409,
			"seed": 1217045839,
			"groupIds": [
				"MN5SLZWmhci12DfUnzhLa",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.3489711997136835,
					25.74352989415452
				],
				[
					10.279007799465164,
					38.26560725851409
				]
			]
		},
		{
			"type": "line",
			"version": 765,
			"versionNonce": 1440847471,
			"isDeleted": false,
			"id": "_975qXn2FSIARFazjb9uM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -577.5527375657729,
			"y": -566.1416668439184,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.2643133068082566,
			"height": 41.152219625069336,
			"seed": 1707549551,
			"groupIds": [
				"MN5SLZWmhci12DfUnzhLa",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.2643133068082566,
					24.640007381376137
				],
				[
					-0.9460182108381245,
					41.152219625069336
				]
			]
		},
		{
			"type": "line",
			"version": 866,
			"versionNonce": 595364865,
			"isDeleted": false,
			"id": "pYO8DpNxt3LfMJbojDA9W",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -577.0989650217709,
			"y": -631.2844644444592,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 23.715867809566895,
			"height": 38.633836407757244,
			"seed": 1057938831,
			"groupIds": [
				"MN5SLZWmhci12DfUnzhLa",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.384935489123276,
					28.58191534693801
				],
				[
					23.715867809566895,
					38.633836407757244
				]
			]
		},
		{
			"type": "line",
			"version": 978,
			"versionNonce": 1231220879,
			"isDeleted": false,
			"id": "whNJ9BMzSs3EaRvwW2-RF",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -578.8913409022953,
			"y": -634.2967989819997,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 11.998819654523029,
			"height": 57.47239451298276,
			"seed": 664425391,
			"groupIds": [
				"MN5SLZWmhci12DfUnzhLa",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.998819654523029,
					26.63927072062204
				],
				[
					-9.83647575816935,
					57.47239451298276
				]
			]
		},
		{
			"type": "line",
			"version": 1059,
			"versionNonce": 653091809,
			"isDeleted": false,
			"id": "F5meJVrO_vvZvf-tSukkh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -560.9911049044723,
			"y": -662.8637029298256,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"width": 30.868261233617087,
			"height": 44.98138832870696,
			"seed": 2006058447,
			"groupIds": [
				"MN5SLZWmhci12DfUnzhLa",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.037133019667525,
					21.986841076106213
				],
				[
					-28.25835927428095,
					-3.0474701178143424
				],
				[
					0.8311282139495616,
					-22.99454725260075
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 718,
			"versionNonce": 334759599,
			"isDeleted": false,
			"id": "JIq57Yde9amge1pCTGlpo",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -531.285655377729,
			"y": -649.5298517398202,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0.8591998868246886,
			"height": 82.43066763042943,
			"seed": 707106223,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.8591998868246886,
					82.43066763042943
				]
			]
		},
		{
			"type": "line",
			"version": 703,
			"versionNonce": 1513635777,
			"isDeleted": false,
			"id": "qjnsg8P-ALtc0cRnFkfGH",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -528.3351433114345,
			"y": -564.7339773993941,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 10.279007799465164,
			"height": 38.26560725851409,
			"seed": 1264912335,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.3489711997136835,
					25.74352989415452
				],
				[
					10.279007799465164,
					38.26560725851409
				]
			]
		},
		{
			"type": "line",
			"version": 731,
			"versionNonce": 876435663,
			"isDeleted": false,
			"id": "2OKbVvjbViYfLVJsjJCKX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -531.5808587747437,
			"y": -565.690962149889,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.2643133068082566,
			"height": 41.152219625069336,
			"seed": 338769391,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.2643133068082566,
					24.640007381376137
				],
				[
					-0.9460182108381245,
					41.152219625069336
				]
			]
		},
		{
			"type": "line",
			"version": 832,
			"versionNonce": 998023073,
			"isDeleted": false,
			"id": "vK5j8nJf_l6pp8sPqEg5o",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -531.1270862307417,
			"y": -630.8337597504293,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 23.715867809566895,
			"height": 38.633836407757244,
			"seed": 1804771343,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.384935489123276,
					28.58191534693801
				],
				[
					23.715867809566895,
					38.633836407757244
				]
			]
		},
		{
			"type": "line",
			"version": 944,
			"versionNonce": 1071081199,
			"isDeleted": false,
			"id": "aH3uzamOTU1BOvAJzJhoY",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -532.9194621112662,
			"y": -633.8460942879701,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 11.998819654523029,
			"height": 57.47239451298276,
			"seed": 1132578351,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.998819654523029,
					26.63927072062204
				],
				[
					-9.83647575816935,
					57.47239451298276
				]
			]
		},
		{
			"type": "line",
			"version": 1025,
			"versionNonce": 1491731329,
			"isDeleted": false,
			"id": "b6HsonbL0QRMUhj-UeHwP",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -515.0192261134433,
			"y": -662.4129982357954,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"width": 30.868261233617087,
			"height": 44.98138832870696,
			"seed": 988227663,
			"groupIds": [
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.037133019667525,
					21.986841076106213
				],
				[
					-28.25835927428095,
					-3.0474701178143424
				],
				[
					0.8311282139495616,
					-22.99454725260075
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 989,
			"versionNonce": 88781071,
			"isDeleted": false,
			"id": "pDvzx8VRfV-CHvRiAb1Im",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -568.3050881089415,
			"y": -620.0773469907708,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.2054244668892746,
			"height": 81.92428347898584,
			"seed": 1046830881,
			"groupIds": [
				"IFwWxynkehGw_AfEoGTNs",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2054244668892746,
					81.92428347898584
				]
			]
		},
		{
			"type": "line",
			"version": 992,
			"versionNonce": 1321200481,
			"isDeleted": false,
			"id": "TS_N5ZzZbE2CSWzfKNPxA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -565.0083514625825,
			"y": -535.7878568017878,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 14.258299831927323,
			"height": 38.26560725851409,
			"seed": 261018369,
			"groupIds": [
				"IFwWxynkehGw_AfEoGTNs",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					14.258299831927323,
					16.0366265728015
				],
				[
					10.279007799465164,
					38.26560725851409
				]
			]
		},
		{
			"type": "line",
			"version": 1014,
			"versionNonce": 1846523695,
			"isDeleted": false,
			"id": "1lINg4glHfCcfvocQ20BQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -567.8945519880635,
			"y": -536.7448415522819,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 2.7149140336203086,
			"height": 41.152219625069336,
			"seed": 119458529,
			"groupIds": [
				"IFwWxynkehGw_AfEoGTNs",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.7688958227821843,
					24.640007381376137
				],
				[
					-0.9460182108381245,
					41.152219625069336
				]
			]
		},
		{
			"type": "line",
			"version": 1229,
			"versionNonce": 88987457,
			"isDeleted": false,
			"id": "43_p4MFiprRrcTK2eh-o2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -567.2692459287165,
			"y": -601.8876391528227,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 22.841430892366258,
			"height": 16.95219849944301,
			"seed": 497338049,
			"groupIds": [
				"IFwWxynkehGw_AfEoGTNs",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.18651040904472,
					4.494414512469318
				],
				[
					11.36960868432226,
					16.95219849944301
				],
				[
					-6.654920483321541,
					16.343910262428004
				]
			]
		},
		{
			"type": "line",
			"version": 1322,
			"versionNonce": 546240847,
			"isDeleted": false,
			"id": "rX8qmlRGp6AhB_1CzxKS8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -569.233155324586,
			"y": -604.8999736903626,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 24.45227004168292,
			"height": 23.403636280171128,
			"seed": 230704801,
			"groupIds": [
				"IFwWxynkehGw_AfEoGTNs",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-9.84173002755563,
					23.403636280171128
				],
				[
					5.972230607880152,
					21.04307785046711
				],
				[
					14.610540014127288,
					10.735452595356795
				]
			]
		},
		{
			"type": "line",
			"version": 1319,
			"versionNonce": 787695393,
			"isDeleted": false,
			"id": "AoVDUkBQs_x5JKP_17CKN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -551.6924342645913,
			"y": -633.4668776381891,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"width": 32.932053466043534,
			"height": 43.90284351522353,
			"seed": 304138881,
			"groupIds": [
				"IFwWxynkehGw_AfEoGTNs",
				"vXkaeThSsIlhFvKIMOjqN",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.037133019667525,
					21.986841076106213
				],
				[
					-32.932053466043534,
					-3.0474701178143424
				],
				[
					-4.921110791296756,
					-21.91600243911732
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "l5wbxgAL4k31n51TpRW7f",
			"type": "line",
			"x": -324.08598304595716,
			"y": -608.1395540374243,
			"width": 55.90422473165685,
			"height": 30.636778525258645,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1605050049,
			"version": 828,
			"versionNonce": 1646327663,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					11.686193870459357,
					0
				],
				[
					21.793172353018733,
					4.42180308611988
				],
				[
					9.475292327399492,
					28.741720059778913
				],
				[
					-8.527763094659628,
					30.636778525258645
				],
				[
					-34.11105237863812,
					28.741720059778302
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				-0.11690582513170966,
				0.1169058251317665
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "k_q-Z4UGXPXa7iDsoI7BT",
			"type": "line",
			"x": -304.7876237323108,
			"y": -683.1419593426197,
			"width": 108.06433275951939,
			"height": 108.70840157468066,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1061133679,
			"version": 3863,
			"versionNonce": 102742785,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-8.060893490390427,
					46.79414506371379
				],
				[
					-15.439116132003067,
					66.56866119700231
				],
				[
					-36.820081990013165,
					72.4431348040128
				],
				[
					-67.79197507810777,
					72.30836123614966
				],
				[
					-98.23826194615229,
					79.37193796341084
				],
				[
					-108.06433275951939,
					93.37729342344025
				],
				[
					-99.81916892879889,
					105.19736692665262
				],
				[
					-73.07780188398745,
					108.70840157468066
				],
				[
					-39.451414866746525,
					90.74415012062325
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				0.5383847004735003,
				0.13459617511830402
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "_ad3jjfdUn57LT1IUWtgN",
			"type": "diamond",
			"x": -312.5072573490359,
			"y": -694.5011434441521,
			"width": 13.611854429709739,
			"height": 18.88038314275068,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1030676417,
			"version": 1424,
			"versionNonce": 957231503,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322179,
			"link": null,
			"locked": false
		},
		{
			"id": "XVwUBqT8FpUjFCnuDky7G",
			"type": "line",
			"x": -305.91420225933877,
			"y": -678.7963106153763,
			"width": 43.73924158814847,
			"height": 92.76832117867873,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1558554337,
			"version": 1229,
			"versionNonce": 1263710945,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-13.22106966792835,
					62.68937202228006
				],
				[
					-43.73924158814847,
					92.76832117867873
				],
				[
					-18.57751826474811,
					46.340299606985816
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				-0.2451478198020709,
				0.5393252035645446
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "8-eN3QfTCHPm9po6MMcj4",
			"type": "line",
			"x": -316.3491719386875,
			"y": -723.1480984044699,
			"width": 39.20292327419151,
			"height": 46.59057675207195,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"nlmothphUjqK64YYjVnxX",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1368016929,
			"version": 1266,
			"versionNonce": 1318004655,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					23.477033054074223,
					-17.2362579954615
				],
				[
					11.48974234097901,
					-42.42299053898832
				],
				[
					9.546833718653463,
					-25.53842785657537
				],
				[
					-7.871543445506042,
					-46.59057675207195
				],
				[
					-1.936583151591113,
					-17.522147406911447
				],
				[
					-15.725890220117291,
					-24.792417218473968
				],
				[
					-1.0937549554608808,
					-2.187509910921301
				]
			],
			"lastCommittedPoint": [
				-0.3036309831603887,
				-0.303630983160474
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "88jAvWsSG4PPSwPjwS2EQ",
			"type": "ellipse",
			"x": -341.06754011675207,
			"y": -755.158517185944,
			"width": 9.326109294499041,
			"height": 8.503217297925525,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"nlmothphUjqK64YYjVnxX",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1841795169,
			"version": 609,
			"versionNonce": 52145857,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322179,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 568,
			"versionNonce": 281827791,
			"isDeleted": false,
			"id": "DqsDq0BTaFuoKyMw7LHRf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -310.34623891134345,
			"y": -774.4964791054198,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 9.326109294499041,
			"height": 8.503217297925525,
			"seed": 794273487,
			"groupIds": [
				"nlmothphUjqK64YYjVnxX",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 592,
			"versionNonce": 1947872929,
			"isDeleted": false,
			"id": "mCyNB9OGARHlEs8YK8AMv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -332.2900254866354,
			"y": -777.7880470917132,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 9.326109294499041,
			"height": 8.503217297925525,
			"seed": 2036247759,
			"groupIds": [
				"nlmothphUjqK64YYjVnxX",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 891,
			"versionNonce": 350111727,
			"isDeleted": false,
			"id": "IFRhpPY9vIHMJKy3vA6ag",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -304.82057432998806,
			"y": -699.6582416601767,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.1310468214590967,
			"height": 76.89107434939548,
			"seed": 1393785921,
			"groupIds": [
				"AwBJMYz-bWrgXx_OjAX2U",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.1310468214590967,
					19.998282065958417
				],
				[
					1.2054244668892746,
					76.89107434939548
				]
			]
		},
		{
			"type": "line",
			"version": 853,
			"versionNonce": 1694347905,
			"isDeleted": false,
			"id": "T-fl_t88N3TK9H58xzely",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -301.523837683629,
			"y": -620.4019606007846,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 10.279007799465164,
			"height": 38.26560725851409,
			"seed": 1589398561,
			"groupIds": [
				"AwBJMYz-bWrgXx_OjAX2U",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.3489711997136835,
					25.74352989415452
				],
				[
					10.279007799465164,
					38.26560725851409
				]
			]
		},
		{
			"type": "line",
			"version": 881,
			"versionNonce": 952988175,
			"isDeleted": false,
			"id": "d9iFqh_aaiVy46ikHQv5H",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -304.7695531469381,
			"y": -621.3589453512791,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 3.2643133068082566,
			"height": 41.152219625069336,
			"seed": 1082138625,
			"groupIds": [
				"AwBJMYz-bWrgXx_OjAX2U",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.2643133068082566,
					24.640007381376137
				],
				[
					-0.9460182108381245,
					41.152219625069336
				]
			]
		},
		{
			"type": "line",
			"version": 1089,
			"versionNonce": 444971617,
			"isDeleted": false,
			"id": "AipTf52K-j07OYWBONoyr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -297.8446699969504,
			"y": -687.1829124892918,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 13.747274564067748,
			"height": 31.140971495562837,
			"seed": 106854369,
			"groupIds": [
				"AwBJMYz-bWrgXx_OjAX2U",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					13.747274564067748,
					4.4003967666747155
				],
				[
					0.21551876677563864,
					31.140971495562837
				]
			]
		},
		{
			"type": "line",
			"version": 1155,
			"versionNonce": 93476911,
			"isDeleted": false,
			"id": "3F4imoHDf3tLvK_E5Dji6",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -303.0428935648356,
			"y": -687.470568876944,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 16.466904183270145,
			"height": 33.972045470191716,
			"seed": 1382470593,
			"groupIds": [
				"AwBJMYz-bWrgXx_OjAX2U",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-15.064082573147955,
					20.84932965210831
				],
				[
					1.4028216101221884,
					33.972045470191716
				]
			]
		},
		{
			"type": "line",
			"version": 1175,
			"versionNonce": 360826433,
			"isDeleted": false,
			"id": "lJAqMAKDXV65RtfdDST1c",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -288.2079204856377,
			"y": -718.080981437186,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"width": 30.868261233617087,
			"height": 44.98138832870696,
			"seed": 1488499617,
			"groupIds": [
				"AwBJMYz-bWrgXx_OjAX2U",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.037133019667525,
					21.986841076106213
				],
				[
					-28.25835927428095,
					-3.0474701178143424
				],
				[
					0.8311282139495616,
					-22.99454725260075
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
			"versionNonce": 1360362063,
			"isDeleted": false,
			"id": "MSkTmgO9L-jyJjyJTv6A0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 91.28396894821265,
			"y": -756.3660056661874,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 20.065336918286928,
			"height": 49.072834854506645,
			"seed": 253800353,
			"groupIds": [
				"t3YXTIQX0M7kCZ9h-tcho",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.143928276602724,
					49.072834854506645
				],
				[
					-15.921408641684202,
					27.262686030281746
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1131,
			"versionNonce": 282154529,
			"isDeleted": false,
			"id": "N3U4ULku2IRs4ViVAoINi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 85.19507895192737,
			"y": -708.695171304655,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 7.747667414383345,
			"height": 65.69970949780479,
			"seed": 1032590209,
			"groupIds": [
				"t3YXTIQX0M7kCZ9h-tcho",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.4658478227637544,
					39.979886603663516
				],
				[
					7.747667414383345,
					65.69970949780479
				]
			]
		},
		{
			"type": "line",
			"version": 1154,
			"versionNonce": 539973743,
			"isDeleted": false,
			"id": "QhTnjRoQHY0xUAR3hAUtp",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 90.42891105059675,
			"y": -643.4280963097514,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 7.684668291712845,
			"height": 38.06479252616504,
			"seed": 1956641633,
			"groupIds": [
				"t3YXTIQX0M7kCZ9h-tcho",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.684668291712845,
					21.711489372683705
				],
				[
					-3.2504921672504796,
					38.06479252616504
				]
			]
		},
		{
			"type": "line",
			"version": 1188,
			"versionNonce": 1063512577,
			"isDeleted": false,
			"id": "31XebOY10FKx0dOWWtxF4",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 93.70551432339664,
			"y": -646.0637857879838,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 8.17534857540178,
			"height": 40.348960695673604,
			"seed": 346810177,
			"groupIds": [
				"t3YXTIQX0M7kCZ9h-tcho",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5768807216113507,
					26.490945685353065
				],
				[
					8.17534857540178,
					40.348960695673604
				]
			]
		},
		{
			"type": "line",
			"version": 1566,
			"versionNonce": 1218998927,
			"isDeleted": false,
			"id": "ahHcKPzc7wk2UI88OrEX2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 85.29333752468449,
			"y": -696.1990173045383,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 17.4638871682726,
			"height": 25.930518056190447,
			"seed": 1208964897,
			"groupIds": [
				"t3YXTIQX0M7kCZ9h-tcho",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.489633136459709,
					6.435787541147749
				],
				[
					-17.4638871682726,
					13.64412978300814
				],
				[
					-1.9389041120057688,
					25.930518056190447
				]
			]
		},
		{
			"type": "line",
			"version": 1871,
			"versionNonce": 1245250017,
			"isDeleted": false,
			"id": "oZbBdoOi5Hdu3Cw5AOj9M",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 89.72709223817071,
			"y": -694.2587665302748,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 17.503639228295274,
			"height": 22.880153790327004,
			"seed": 1094306561,
			"groupIds": [
				"t3YXTIQX0M7kCZ9h-tcho",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					13.295440116762581,
					11.045184100406003
				],
				[
					6.632767732899404,
					18.462579262629056
				],
				[
					-4.208199111532694,
					22.880153790327004
				]
			]
		},
		{
			"id": "hxIcodh3FtNxYQ1cK1-rI",
			"type": "line",
			"x": 8.872221533062657,
			"y": -791.6907520423265,
			"width": 20.065336918286928,
			"height": 49.072834854506645,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"s4-Vygq_tin6YnSXWgMGA",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 553823137,
			"version": 923,
			"versionNonce": 1396263087,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					4.143928276602724,
					49.072834854506645
				],
				[
					-15.921408641684202,
					27.262686030281746
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				0.4036392793657342,
				0.32291142349265556
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "line",
			"version": 872,
			"versionNonce": 241180097,
			"isDeleted": false,
			"id": "OzwsNJjOyA3JLbOaxdXyT",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2.7833315367776095,
			"y": -744.019917680793,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 8.729639613409434,
			"height": 65.69970949780479,
			"seed": 142378607,
			"groupIds": [
				"s4-Vygq_tin6YnSXWgMGA",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.729639613409434,
					41.96092072838508
				],
				[
					7.747667414383345,
					65.69970949780479
				]
			]
		},
		{
			"type": "line",
			"version": 874,
			"versionNonce": 495606479,
			"isDeleted": false,
			"id": "rckJum00D7RcSLqq4IbEf",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 8.017163635446877,
			"y": -678.7528426858896,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 12.50422186808863,
			"height": 38.265607258514116,
			"seed": 1260380303,
			"groupIds": [
				"s4-Vygq_tin6YnSXWgMGA",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.50422186808863,
					20.70741571093892
				],
				[
					-10.279007799465175,
					38.265607258514116
				]
			]
		},
		{
			"type": "line",
			"version": 903,
			"versionNonce": 452509089,
			"isDeleted": false,
			"id": "KstbQiVN5zweA-mcu-4q7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 10.96359455412653,
			"y": -681.3885321641229,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 6.075228542722968,
			"height": 41.15221962506937,
			"seed": 814937775,
			"groupIds": [
				"s4-Vygq_tin6YnSXWgMGA",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.129210331884843,
					25.759143866535023
				],
				[
					0.9460182108381254,
					41.15221962506937
				]
			]
		},
		{
			"type": "line",
			"version": 1158,
			"versionNonce": 1010051311,
			"isDeleted": false,
			"id": "NiUlMUA4jUwZaQeYCJTrB",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2.551417755414491,
			"y": -730.863418972436,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 30.010436624842523,
			"height": 37.29491439364201,
			"seed": 1065240783,
			"groupIds": [
				"s4-Vygq_tin6YnSXWgMGA",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-18.093080218864948,
					5.115098124666717
				],
				[
					-30.010436624842523,
					-7.156728526568123
				],
				[
					-4.250110590847652,
					-32.179816268975294
				]
			]
		},
		{
			"type": "line",
			"version": 1389,
			"versionNonce": 1865572737,
			"isDeleted": false,
			"id": "5k7vhYf-mF2e3iuZHa43j",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4.343793635938482,
			"y": -733.875753509977,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 19.45084824260107,
			"height": 46.93570934348526,
			"seed": 360339183,
			"groupIds": [
				"s4-Vygq_tin6YnSXWgMGA",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322179,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.50541819281376,
					23.59173355697581
				],
				[
					-19.45084824260107,
					-0.02707256810509419
				],
				[
					-1.8969926326908864,
					-23.343975786509443
				]
			]
		},
		{
			"type": "line",
			"version": 1017,
			"versionNonce": 482292495,
			"isDeleted": false,
			"id": "HbbUcwQxTQ0H96Hyzy9xs",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 39.395077931722426,
			"y": -773.130205607576,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 20.065336918286928,
			"height": 49.072834854506645,
			"seed": 1813352737,
			"groupIds": [
				"jhdysgn95-JIcwwQs3zGb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.143928276602724,
					49.072834854506645
				],
				[
					-15.921408641684202,
					27.262686030281746
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 985,
			"versionNonce": 2018281825,
			"isDeleted": false,
			"id": "hiqD0QwTwkkrgc80DGF_N",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 33.306187935437265,
			"y": -725.4593712460426,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 7.747667414383345,
			"height": 65.69970949780479,
			"seed": 1013499137,
			"groupIds": [
				"jhdysgn95-JIcwwQs3zGb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.4658478227637544,
					39.979886603663516
				],
				[
					7.747667414383345,
					65.69970949780479
				]
			]
		},
		{
			"type": "line",
			"version": 1008,
			"versionNonce": 1738799407,
			"isDeleted": false,
			"id": "lTbfuCmPaS-E9ZTev7VnD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 38.54002003410653,
			"y": -660.1922962511393,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 7.684668291712845,
			"height": 38.06479252616504,
			"seed": 669678817,
			"groupIds": [
				"jhdysgn95-JIcwwQs3zGb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.684668291712845,
					21.711489372683705
				],
				[
					-3.2504921672504796,
					38.06479252616504
				]
			]
		},
		{
			"type": "line",
			"version": 1042,
			"versionNonce": 1335276865,
			"isDeleted": false,
			"id": "dLqogelrD1GAoZKYY9D2c",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 41.81662330690665,
			"y": -662.8279857293721,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 8.17534857540178,
			"height": 40.348960695673604,
			"seed": 1311389889,
			"groupIds": [
				"jhdysgn95-JIcwwQs3zGb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5768807216113507,
					26.490945685353065
				],
				[
					8.17534857540178,
					40.348960695673604
				]
			]
		},
		{
			"type": "line",
			"version": 1420,
			"versionNonce": 575339343,
			"isDeleted": false,
			"id": "xtn-TrcwVheo72ZpSC0If",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 33.40444650819427,
			"y": -712.9632172459262,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 17.4638871682726,
			"height": 25.930518056190447,
			"seed": 818378913,
			"groupIds": [
				"jhdysgn95-JIcwwQs3zGb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.489633136459709,
					6.435787541147749
				],
				[
					-17.4638871682726,
					13.64412978300814
				],
				[
					-1.9389041120057688,
					25.930518056190447
				]
			]
		},
		{
			"type": "line",
			"version": 1725,
			"versionNonce": 946890017,
			"isDeleted": false,
			"id": "GgF_vLcD2mXhsmSrP5mGi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 37.838201221680606,
			"y": -711.0229664716633,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 17.503639228295274,
			"height": 22.880153790327004,
			"seed": 1903279233,
			"groupIds": [
				"jhdysgn95-JIcwwQs3zGb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					13.295440116762581,
					11.045184100406003
				],
				[
					6.632767732899404,
					18.462579262629056
				],
				[
					-4.208199111532694,
					22.880153790327004
				]
			]
		},
		{
			"type": "line",
			"version": 1416,
			"versionNonce": 286046575,
			"isDeleted": false,
			"id": "V6DVwitYqbDW6i6yAJ3Y5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 35.45452951864445,
			"y": -675.8491817570477,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 21.66680211687129,
			"height": 15.690976890482055,
			"seed": 294304271,
			"groupIds": [
				"E45Y2U1MJmSyG9NlhDU64",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					21.66680211687129,
					14.357707435106652
				],
				[
					0.6096044151729537,
					15.690976890482055
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1132,
			"versionNonce": 1581848833,
			"isDeleted": false,
			"id": "tKj6FpYqqgM5wPjEl9Bs8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 46.55789310149055,
			"y": -657.9341708978573,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 22.625579165554786,
			"height": 62.06288662529636,
			"seed": 1734778927,
			"groupIds": [
				"E45Y2U1MJmSyG9NlhDU64",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					18.978867708660886,
					38.324097855876644
				],
				[
					22.625579165554786,
					62.06288662529636
				]
			]
		},
		{
			"type": "line",
			"version": 1226,
			"versionNonce": 1496429455,
			"isDeleted": false,
			"id": "-oS6DVIJJZmKkkKWkRIl_",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 69.64521930156548,
			"y": -595.642678253188,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 3.3359823155851984,
			"height": 30.0001007300856,
			"seed": 18924111,
			"groupIds": [
				"E45Y2U1MJmSyG9NlhDU64",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.2712722060143578,
					14.425630749333408
				],
				[
					-3.3359823155851984,
					30.0001007300856
				]
			]
		},
		{
			"type": "line",
			"version": 1273,
			"versionNonce": 1386238177,
			"isDeleted": false,
			"id": "K1j134_paWDINA1_ItX97",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 69.94668813114811,
			"y": -600.5927095593815,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 7.103739330189503,
			"height": 36.85415623028664,
			"seed": 905599617,
			"groupIds": [
				"E45Y2U1MJmSyG9NlhDU64",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					7.103739330189503,
					14.518054987872238
				],
				[
					6.566562650169516,
					36.85415623028664
				]
			]
		},
		{
			"type": "line",
			"version": 1632,
			"versionNonce": 1660053935,
			"isDeleted": false,
			"id": "GKfQHabeKckEtDA8CzDYr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 53.93024532628169,
			"y": -647.7532545397345,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 10.201275291316296,
			"height": 46.17718562052729,
			"seed": 1417788047,
			"groupIds": [
				"E45Y2U1MJmSyG9NlhDU64",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.521371079064951,
					15.694946481055382
				],
				[
					-7.858879128654014,
					28.550259676243204
				],
				[
					-10.201275291316296,
					46.17718562052729
				]
			]
		},
		{
			"type": "line",
			"version": 1906,
			"versionNonce": 1258654913,
			"isDeleted": false,
			"id": "BwVzApj4ziwMUSjI1_pwz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 54.730760423394486,
			"y": -645.4756648990813,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1.2357521104166522,
			"height": 47.07813983570218,
			"seed": 615092399,
			"groupIds": [
				"E45Y2U1MJmSyG9NlhDU64",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.5623927089337457,
					20.61615120674212
				],
				[
					-0.2748730966467437,
					36.01053589584283
				],
				[
					-1.2357521104166522,
					47.07813983570218
				]
			]
		},
		{
			"type": "line",
			"version": 1014,
			"versionNonce": 2071419855,
			"isDeleted": false,
			"id": "rIcUv3qcWMUEM1U5BAATA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 106.02210656879072,
			"y": -710.2322319375027,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 20.065336918286928,
			"height": 49.072834854506645,
			"seed": 155280577,
			"groupIds": [
				"MbEviooSL2Lw0Xq2vKpDG",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.143928276602724,
					49.072834854506645
				],
				[
					-15.921408641684202,
					27.262686030281746
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 963,
			"versionNonce": 521686177,
			"isDeleted": false,
			"id": "RWRHAgy3B4GbTpfqeIZ0s",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 99.93321657250544,
			"y": -662.5613975759695,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 8.729639613409434,
			"height": 65.69970949780479,
			"seed": 1478042785,
			"groupIds": [
				"MbEviooSL2Lw0Xq2vKpDG",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.729639613409434,
					41.96092072838508
				],
				[
					7.747667414383345,
					65.69970949780479
				]
			]
		},
		{
			"type": "line",
			"version": 965,
			"versionNonce": 920193519,
			"isDeleted": false,
			"id": "Y3jKHcdeTvUUG1gEue2Zk",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 105.16704867117471,
			"y": -597.2943225810659,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 12.50422186808863,
			"height": 38.265607258514116,
			"seed": 430827649,
			"groupIds": [
				"MbEviooSL2Lw0Xq2vKpDG",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.50422186808863,
					20.70741571093892
				],
				[
					-10.279007799465175,
					38.265607258514116
				]
			]
		},
		{
			"type": "line",
			"version": 994,
			"versionNonce": 109580417,
			"isDeleted": false,
			"id": "JiS5i6jf70EKvbIdHtmyz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 108.11347958985448,
			"y": -599.9300120592991,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 6.075228542722968,
			"height": 41.15221962506937,
			"seed": 2009018465,
			"groupIds": [
				"MbEviooSL2Lw0Xq2vKpDG",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.129210331884843,
					25.759143866535023
				],
				[
					0.9460182108381254,
					41.15221962506937
				]
			]
		},
		{
			"type": "line",
			"version": 1249,
			"versionNonce": 304083983,
			"isDeleted": false,
			"id": "tOaBI59PtU5wYnSI1jr-k",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 99.70130279114244,
			"y": -649.4048988676124,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 30.010436624842523,
			"height": 37.29491439364201,
			"seed": 941390913,
			"groupIds": [
				"MbEviooSL2Lw0Xq2vKpDG",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-18.093080218864948,
					5.115098124666717
				],
				[
					-30.010436624842523,
					-7.156728526568123
				],
				[
					-4.250110590847652,
					-32.179816268975294
				]
			]
		},
		{
			"type": "line",
			"version": 1480,
			"versionNonce": 387209313,
			"isDeleted": false,
			"id": "bturrmpOYNnAyy1Rzulm2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 101.49367867166654,
			"y": -652.4172334051536,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 19.45084824260107,
			"height": 46.93570934348526,
			"seed": 983911457,
			"groupIds": [
				"MbEviooSL2Lw0Xq2vKpDG",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.50541819281376,
					23.59173355697581
				],
				[
					-19.45084824260107,
					-0.02707256810509419
				],
				[
					-1.8969926326908864,
					-23.343975786509443
				]
			]
		},
		{
			"type": "line",
			"version": 932,
			"versionNonce": 1430559279,
			"isDeleted": false,
			"id": "fqJQORus8VARD7WDIPqTz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 45.92218541304601,
			"y": -641.7020063343032,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 20.065336918286928,
			"height": 49.072834854506645,
			"seed": 1741461377,
			"groupIds": [
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.143928276602724,
					49.072834854506645
				],
				[
					-15.921408641684202,
					27.262686030281746
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 892,
			"versionNonce": 42771521,
			"isDeleted": false,
			"id": "7q4F2HI_7RTMrgiUQwYyj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 41.79050414394294,
			"y": -597.2931865180738,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 6.772430886227228,
			"height": 68.96172404310839,
			"seed": 204472161,
			"groupIds": [
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.772430886227228,
					45.22293527368868
				],
				[
					5.79045868720114,
					68.96172404310839
				]
			]
		},
		{
			"type": "line",
			"version": 883,
			"versionNonce": 892304463,
			"isDeleted": false,
			"id": "0JLabUW74iOKXMMAq0lQs",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 45.06712751543,
			"y": -528.7640969778666,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 12.50422186808863,
			"height": 38.265607258514116,
			"seed": 1134259009,
			"groupIds": [
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.50422186808863,
					20.70741571093892
				],
				[
					-10.279007799465175,
					38.265607258514116
				]
			]
		},
		{
			"type": "line",
			"version": 912,
			"versionNonce": 349205537,
			"isDeleted": false,
			"id": "KlKCK1uwtG8TyOTnxiidR",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 48.01355843410988,
			"y": -531.3997864560997,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 6.075228542722968,
			"height": 41.15221962506937,
			"seed": 1986943777,
			"groupIds": [
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.129210331884843,
					25.759143866535023
				],
				[
					0.9460182108381254,
					41.15221962506937
				]
			]
		},
		{
			"type": "line",
			"version": 1176,
			"versionNonce": 901323375,
			"isDeleted": false,
			"id": "2uZZ-rRlko_Lf3kkShryv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 42.21099327164052,
			"y": -581.8532776280042,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 30.010436624842523,
			"height": 37.29491439364201,
			"seed": 1427656449,
			"groupIds": [
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-18.093080218864948,
					5.115098124666717
				],
				[
					-30.010436624842523,
					-7.156728526568123
				],
				[
					-4.250110590847652,
					-32.179816268975294
				]
			]
		},
		{
			"type": "line",
			"version": 1402,
			"versionNonce": 1909409793,
			"isDeleted": false,
			"id": "JzNKOiUB6tm_aWcp9x7Tr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 42.698563334043286,
			"y": -583.887007801954,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 19.45084824260107,
			"height": 46.93570934348526,
			"seed": 1444464353,
			"groupIds": [
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.50541819281376,
					23.59173355697581
				],
				[
					-19.45084824260107,
					-0.02707256810509419
				],
				[
					-1.8969926326908864,
					-23.343975786509443
				]
			]
		},
		{
			"type": "line",
			"version": 1033,
			"versionNonce": 1269429391,
			"isDeleted": false,
			"id": "zyI55tgd5rK1XOBDKLOer",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -26.4930611116755,
			"y": -729.6856704235387,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 20.065336918286928,
			"height": 49.072834854506645,
			"seed": 1039882817,
			"groupIds": [
				"DSWsWva2ZK3f-_gh4KhWU",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.143928276602724,
					49.072834854506645
				],
				[
					-15.921408641684202,
					27.262686030281746
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 982,
			"versionNonce": 327720929,
			"isDeleted": false,
			"id": "zBrhPB4LHsLfQk09g4W4R",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -32.581951107960776,
			"y": -682.0148360620049,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 8.729639613409434,
			"height": 65.69970949780479,
			"seed": 486042145,
			"groupIds": [
				"DSWsWva2ZK3f-_gh4KhWU",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.729639613409434,
					41.96092072838508
				],
				[
					7.747667414383345,
					65.69970949780479
				]
			]
		},
		{
			"type": "line",
			"version": 984,
			"versionNonce": 1052412591,
			"isDeleted": false,
			"id": "JmNStWY5nzV5ggPPBUq6D",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -27.348119009291395,
			"y": -616.7477610671014,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 12.50422186808863,
			"height": 38.265607258514116,
			"seed": 1569226241,
			"groupIds": [
				"DSWsWva2ZK3f-_gh4KhWU",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.50422186808863,
					20.70741571093892
				],
				[
					-10.279007799465175,
					38.265607258514116
				]
			]
		},
		{
			"type": "line",
			"version": 1013,
			"versionNonce": 135003073,
			"isDeleted": false,
			"id": "MVJrIj-sRHhKuthuW4iBo",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -24.401688090611742,
			"y": -619.3834505453352,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 6.075228542722968,
			"height": 41.15221962506937,
			"seed": 1588270561,
			"groupIds": [
				"DSWsWva2ZK3f-_gh4KhWU",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.129210331884843,
					25.759143866535023
				],
				[
					0.9460182108381254,
					41.15221962506937
				]
			]
		},
		{
			"type": "line",
			"version": 1268,
			"versionNonce": 1267948751,
			"isDeleted": false,
			"id": "up0D3DB6o6NHgWXS56Gst",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -32.81386488932378,
			"y": -668.8583373536479,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 30.010436624842523,
			"height": 37.29491439364201,
			"seed": 1936699841,
			"groupIds": [
				"DSWsWva2ZK3f-_gh4KhWU",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-18.093080218864948,
					5.115098124666717
				],
				[
					-30.010436624842523,
					-7.156728526568123
				],
				[
					-4.250110590847652,
					-32.179816268975294
				]
			]
		},
		{
			"type": "line",
			"version": 1499,
			"versionNonce": 1870191521,
			"isDeleted": false,
			"id": "llUxLGuSdBZHZ2ossbiGD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -31.021489008799676,
			"y": -671.8706718911889,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 19.45084824260107,
			"height": 46.93570934348526,
			"seed": 1626722721,
			"groupIds": [
				"DSWsWva2ZK3f-_gh4KhWU",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.50541819281376,
					23.59173355697581
				],
				[
					-19.45084824260107,
					-0.02707256810509419
				],
				[
					-1.8969926326908864,
					-23.343975786509443
				]
			]
		},
		{
			"type": "line",
			"version": 1097,
			"versionNonce": 97315567,
			"isDeleted": false,
			"id": "mpfM23QKqy8FtWjb3Oytm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1.1295012744857331,
			"y": -687.5813157690982,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 20.065336918286928,
			"height": 49.072834854506645,
			"seed": 1996165775,
			"groupIds": [
				"kAMa2cFd4ascYRB4U6CQb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.143928276602724,
					49.072834854506645
				],
				[
					-15.921408641684202,
					27.262686030281746
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1065,
			"versionNonce": 972996481,
			"isDeleted": false,
			"id": "TyY8RolaMxDEJyHjgw2F0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -7.218391270771008,
			"y": -639.9104814075656,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 7.747667414383345,
			"height": 65.69970949780479,
			"seed": 1580722351,
			"groupIds": [
				"kAMa2cFd4ascYRB4U6CQb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.4658478227637544,
					39.979886603663516
				],
				[
					7.747667414383345,
					65.69970949780479
				]
			]
		},
		{
			"type": "line",
			"version": 1088,
			"versionNonce": 2045752591,
			"isDeleted": false,
			"id": "LynT1Kp4MQc0ooslz77TI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1.9845591721016262,
			"y": -574.643406412662,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 7.684668291712845,
			"height": 38.06479252616504,
			"seed": 263518927,
			"groupIds": [
				"kAMa2cFd4ascYRB4U6CQb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.684668291712845,
					21.711489372683705
				],
				[
					-3.2504921672504796,
					38.06479252616504
				]
			]
		},
		{
			"type": "line",
			"version": 1122,
			"versionNonce": 635250529,
			"isDeleted": false,
			"id": "HA3qRneoI1PQxsvJiX173",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1.2920441006982628,
			"y": -577.2790958908943,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 8.17534857540178,
			"height": 40.348960695673604,
			"seed": 1342884079,
			"groupIds": [
				"kAMa2cFd4ascYRB4U6CQb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.5768807216113507,
					26.490945685353065
				],
				[
					8.17534857540178,
					40.348960695673604
				]
			]
		},
		{
			"type": "line",
			"version": 1500,
			"versionNonce": 259275567,
			"isDeleted": false,
			"id": "PYHKUTth5t-eONFrQ8JwU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -7.12013269801389,
			"y": -627.4143274074489,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 17.4638871682726,
			"height": 25.930518056190447,
			"seed": 1019335439,
			"groupIds": [
				"kAMa2cFd4ascYRB4U6CQb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.489633136459709,
					6.435787541147749
				],
				[
					-17.4638871682726,
					13.64412978300814
				],
				[
					-1.9389041120057688,
					25.930518056190447
				]
			]
		},
		{
			"type": "line",
			"version": 1805,
			"versionNonce": 2103677761,
			"isDeleted": false,
			"id": "4RwwPoJ6MGt4pJz60n8wf",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2.6863779845277804,
			"y": -625.4740766331854,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 17.503639228295274,
			"height": 22.880153790327004,
			"seed": 777165103,
			"groupIds": [
				"kAMa2cFd4ascYRB4U6CQb",
				"ys1vSTNDd1oJtwAGhku0z",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					13.295440116762581,
					11.045184100406003
				],
				[
					6.632767732899404,
					18.462579262629056
				],
				[
					-4.208199111532694,
					22.880153790327004
				]
			]
		},
		{
			"type": "line",
			"version": 1908,
			"versionNonce": 717421903,
			"isDeleted": false,
			"id": "0eYfuipvteW35liH2VbOT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -185.74097710717,
			"y": -671.9141338513174,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 20.67433958520481,
			"height": 32.1161123400157,
			"seed": 1017770511,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.297659578597369,
					14.294395870200773
				],
				[
					11.550367767724731,
					24.373588217826434
				],
				[
					20.67433958520481,
					32.1161123400157
				]
			]
		},
		{
			"type": "line",
			"version": 1114,
			"versionNonce": 351372065,
			"isDeleted": false,
			"id": "hKyg-G6u4jSMdHP1HB-rl",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -167.38722904662,
			"y": -610.1441510683592,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"width": 52.73501630132866,
			"height": 28.899980684909288,
			"seed": 896665025,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.02370397259414,
					0
				],
				[
					-20.55771821916198,
					4.171131232873576
				],
				[
					-8.938138356157424,
					27.11235301367796
				],
				[
					8.04432452054176,
					28.899980684909288
				],
				[
					32.177298082166686,
					27.11235301367738
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 4151,
			"versionNonce": 255097711,
			"isDeleted": false,
			"id": "c__LFmNiAByILHjrQkmS4",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -184.9507226349058,
			"y": -680.894672793573,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 101.9381697361849,
			"height": 102.54572631405966,
			"seed": 1468900769,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					7.603921736853943,
					44.141386712484156
				],
				[
					14.56387321007319,
					62.794886258276904
				],
				[
					34.73275290516771,
					68.33633617399316
				],
				[
					63.94885052075252,
					68.20920291470256
				],
				[
					92.66913851344268,
					74.87234573880598
				],
				[
					101.9381697361849,
					88.08373811631839
				],
				[
					94.16042393777205,
					99.2337320902413
				],
				[
					68.93502400070098,
					102.54572631405966
				],
				[
					37.21491561853735,
					85.59986760985277
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "diamond",
			"version": 1711,
			"versionNonce": 150370049,
			"isDeleted": false,
			"id": "LnL41NAqOIjAF0C2brCHq",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -191.1497561184883,
			"y": -691.6099051689342,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 12.840198906033226,
			"height": 17.81005492138554,
			"seed": 418007425,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1529,
			"versionNonce": 17905039,
			"isDeleted": false,
			"id": "Npb-5JI8LZ7qvoSHdPdGH",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -184.12151770683144,
			"y": -673.9914358009331,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 40.852331055471886,
			"height": 86.08361757324775,
			"seed": 1925673313,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.064233171552601,
					56.33157091239136
				],
				[
					40.852331055471886,
					84.70534555470914
				],
				[
					17.117024895727315,
					40.909326807037985
				],
				[
					2.067408027807886,
					-1.3782720185386097
				]
			]
		},
		{
			"type": "line",
			"version": 1106,
			"versionNonce": 1005711073,
			"isDeleted": false,
			"id": "A24P0gX7sP9b5JlNPgIOm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -179.67053229193044,
			"y": -734.7459851800278,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 23.722192148486045,
			"height": 43.848755954222256,
			"seed": 1865068943,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.711151946688034,
					43.848755954222256
				],
				[
					-18.01104020179801,
					30.397133370452437
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1061,
			"versionNonce": 663858095,
			"isDeleted": false,
			"id": "BoIBIPX5tOTejXSX2dG9V",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -185.49821834320142,
			"y": -692.2992297187784,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 7.486463469369171,
			"height": 70.92378839808917,
			"seed": 219916207,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.2046438777495811,
					45.20396550394791
				],
				[
					7.486463469369171,
					70.92378839808917
				]
			]
		},
		{
			"type": "line",
			"version": 1151,
			"versionNonce": 343108289,
			"isDeleted": false,
			"id": "IIyd3axA-Dy-RsanXidTj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -180.52559018954634,
			"y": -621.8080758235907,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 11.87022235271978,
			"height": 27.877838670610657,
			"seed": 1237899727,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-10.557911686869254,
					11.524535517129312
				],
				[
					-11.87022235271978,
					27.877838670610657
				]
			]
		},
		{
			"type": "line",
			"version": 1142,
			"versionNonce": 786324943,
			"isDeleted": false,
			"id": "YnVYTUBhvfOu0CtFtP7EH",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -180.90584214694542,
			"y": -624.1825613568101,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 14.183039310728883,
			"height": 29.900802895104828,
			"seed": 2051721199,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.6216965016681604,
					16.82639971982719
				],
				[
					14.183039310728883,
					29.900802895104828
				]
			]
		},
		{
			"type": "line",
			"version": 1984,
			"versionNonce": 2065328801,
			"isDeleted": false,
			"id": "mBfESN_RFfYjBvi1bf97O",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -183.50550964020397,
			"y": -672.0920033296993,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 33.72424489813949,
			"height": 24.44737746041251,
			"seed": 1507776559,
			"groupIds": [
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.645691264431798,
					14.702039330604894
				],
				[
					-20.010034658550868,
					22.119434492827942
				],
				[
					-33.72424489813949,
					24.44737746041251
				]
			]
		},
		{
			"type": "line",
			"version": 1841,
			"versionNonce": 705678319,
			"isDeleted": false,
			"id": "sc-Bf2pxxU5NXAD8PmCNa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.078747094486726,
			"x": -180.48461678534449,
			"y": -711.8839023390608,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 36.187473304419434,
			"height": 48.57589022349837,
			"seed": 401727905,
			"groupIds": [
				"ziAEJOTZ-ZAu3-La2qYu8",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1248667544420905,
					-22.982700172820177
				],
				[
					-15.965425711898154,
					-9.843793477200643
				],
				[
					-6.993584968575021,
					-44.40830401041475
				],
				[
					-5.0506763462494755,
					-27.523741328001794
				],
				[
					12.367700817910029,
					-48.57589022349837
				],
				[
					6.4327405239951005,
					-19.50746087833787
				],
				[
					20.22204759252128,
					-26.777730689900395
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 949,
			"versionNonce": 412511873,
			"isDeleted": false,
			"id": "qudu-wDGjthAgvkgY3DcX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.078747094486726,
			"x": -162.17085609759403,
			"y": -750.318295712691,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 9.326109294499041,
			"height": 8.503217297925525,
			"seed": 963052929,
			"groupIds": [
				"ziAEJOTZ-ZAu3-La2qYu8",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 908,
			"versionNonce": 892237327,
			"isDeleted": false,
			"id": "aIBYS2_uCajxAvXXEFJKe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.078747094486726,
			"x": -196.17832910918435,
			"y": -763.0165986827149,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 9.326109294499041,
			"height": 8.503217297925525,
			"seed": 1548528993,
			"groupIds": [
				"ziAEJOTZ-ZAu3-La2qYu8",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 932,
			"versionNonce": 1403450977,
			"isDeleted": false,
			"id": "HuZs1w8OZC2_14LwxtnvH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.078747094486726,
			"x": -175.35976228738565,
			"y": -770.6945843923031,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 9.326109294499041,
			"height": 8.503217297925525,
			"seed": 133323073,
			"groupIds": [
				"ziAEJOTZ-ZAu3-La2qYu8",
				"W6unNs7Cu_tZH7ICZoA3P"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"id": "6R68N6Eb",
			"type": "text",
			"x": -318.92056964661924,
			"y": -490.8864411429697,
			"width": 142.7725830078125,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1074308463,
			"version": 192,
			"versionNonce": 1462950959,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"text": "Motivation",
			"rawText": "Motivation",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Motivation",
			"lineHeight": 1.25
		},
		{
			"id": "6FbL0OxAnoyQ4dfRXzAGQ",
			"type": "rectangle",
			"x": -489.5414999236362,
			"y": -500.24440496536243,
			"width": 471.79229974929234,
			"height": 218.31957400163338,
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
			"seed": 551232609,
			"version": 324,
			"versionNonce": 253461057,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"id": "XX0hnDx6",
			"type": "text",
			"x": -472.13066574120614,
			"y": -449.91534087180287,
			"width": 438.01953125,
			"height": 150,
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
			"seed": 1740693569,
			"version": 406,
			"versionNonce": 604339791,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"text": "Labeled data is scarce, often times we find\nourselves having a lot more unlabeled data\nthan labeled because labelling correctly is\nexpensive and sometimes even requires \nexperts, thus we want to be able to make\nuse of of unlabeled data.",
			"rawText": "Labeled data is scarce, often times we find\nourselves having a lot more unlabeled data\nthan labeled because labelling correctly is\nexpensive and sometimes even requires \nexperts, thus we want to be able to make\nuse of of unlabeled data.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 143,
			"containerId": null,
			"originalText": "Labeled data is scarce, often times we find\nourselves having a lot more unlabeled data\nthan labeled because labelling correctly is\nexpensive and sometimes even requires \nexperts, thus we want to be able to make\nuse of of unlabeled data.",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 589,
			"versionNonce": 668176929,
			"isDeleted": false,
			"id": "PQVQb5Bu3-QX1GXtuEZKf",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.5928278171268317,
			"x": -39.08868430935861,
			"y": -491.62670069465656,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 15.381645937330841,
			"height": 5.132018991705377,
			"seed": 692292641,
			"groupIds": [
				"xXfbvPyrx9ACLB4E1mGFR"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"id": "FTHKyfKVi88w4AaDhMiBJ",
			"type": "line",
			"x": -28.043813689134694,
			"y": -485.57777835753603,
			"width": 11.986413616909797,
			"height": 10.68286691096095,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"xXfbvPyrx9ACLB4E1mGFR"
			],
			"frameId": null,
			"roundness": null,
			"seed": 829247073,
			"version": 1283,
			"versionNonce": 511630447,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"points": [
				[
					-0.9717118709906426,
					-2.611974854654252
				],
				[
					-4.910679355141868,
					-5.168324678092191
				],
				[
					3.3350533381525977,
					-13.294841765615201
				],
				[
					4.974814638878886,
					-12.176758959978716
				],
				[
					5.433295376797243,
					-11.811226543179986
				],
				[
					7.075734261767929,
					-10.439322908768437
				],
				[
					-0.576209250894247,
					-2.65599694720454
				]
			],
			"lastCommittedPoint": [
				0.4966568201844552,
				-0.2483284100921992
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "1rmYHUC40t3fuK_6l6jhQ",
			"type": "ellipse",
			"x": -28.106058644893714,
			"y": -500.95237093075593,
			"width": 12.16565107650104,
			"height": 5.132018991705377,
			"angle": 0.7217900033290414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"xXfbvPyrx9ACLB4E1mGFR"
			],
			"frameId": null,
			"roundness": null,
			"seed": 320404833,
			"version": 427,
			"versionNonce": 851355137,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"id": "9GDr0M8ykIGghLdyVU-YZ",
			"type": "ellipse",
			"x": -40.26759164376618,
			"y": -484.7265685070202,
			"width": 5.2167086904138555,
			"height": 5.13999238614305,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"xXfbvPyrx9ACLB4E1mGFR"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1619402849,
			"version": 358,
			"versionNonce": 1516729999,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"id": "hBnjBJZjDHKa10D7DD0xz",
			"type": "line",
			"x": -35.171556485057735,
			"y": -488.35529992467985,
			"width": 7.2952162353694865,
			"height": 7.179419152268396,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"xXfbvPyrx9ACLB4E1mGFR"
			],
			"frameId": null,
			"roundness": null,
			"seed": 112624769,
			"version": 385,
			"versionNonce": 2061254113,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.512511520733456,
					2.277342634321704
				],
				[
					-1.46676305261398,
					7.179419152268396
				],
				[
					-3.7827047146360306,
					5.635458044253674
				],
				[
					-0.1929951385018488,
					0.42458930470404366
				]
			],
			"lastCommittedPoint": [
				-0.6513177413146991,
				1.4328990308922585
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "ellipse",
			"version": 628,
			"versionNonce": 1584909487,
			"isDeleted": false,
			"id": "yn65mxnO6RHb2FwaYk6jK",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.6903574900527545,
			"x": -483.7806168319877,
			"y": -491.37614081871436,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 16.00044593405216,
			"height": 5.338478908165533,
			"seed": 1145455087,
			"groupIds": [
				"zKu-zIKOLoWDjK2WhUJl8"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1322,
			"versionNonce": 1060886977,
			"isDeleted": false,
			"id": "Azi0C4SIuMPzRXmTAsfev",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -478.2585704534125,
			"y": -487.80092574775057,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 12.468624216286736,
			"height": 11.112636133085175,
			"seed": 1831218191,
			"groupIds": [
				"zKu-zIKOLoWDjK2WhUJl8"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.097431219190307,
					-2.659191175319716
				],
				[
					-4.48002536011508,
					-11.112636133085175
				],
				[
					-6.185753872129894,
					-9.949573119265448
				],
				[
					-6.662679182253108,
					-9.569335419349544
				],
				[
					-8.37119299709643,
					-8.142240424537775
				],
				[
					-0.411413597440176,
					-0.04579309097508428
				]
			]
		},
		{
			"type": "ellipse",
			"version": 466,
			"versionNonce": 1180196559,
			"isDeleted": false,
			"id": "SXlepHnG2R-KeIOXoDHwH",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.561395303850545,
			"x": -491.8596973653465,
			"y": -501.07698057405986,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 12.655072356702341,
			"height": 5.338478908165533,
			"seed": 1657000495,
			"groupIds": [
				"zKu-zIKOLoWDjK2WhUJl8"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 397,
			"versionNonce": 821885345,
			"isDeleted": false,
			"id": "ssaAwD1dLM-REgRusAOa8",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -471.9804120523898,
			"y": -484.1984179367868,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 5.426575653525369,
			"height": 5.346773070385275,
			"seed": 1040692303,
			"groupIds": [
				"zKu-zIKOLoWDjK2WhUJl8"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 424,
			"versionNonce": 614575343,
			"isDeleted": false,
			"id": "xSafb5qAQ9aHxUMz8hDTP",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -471.85488385289864,
			"y": -487.97313236552986,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 7.588701067936846,
			"height": 7.468245495429926,
			"seed": 1724535407,
			"groupIds": [
				"zKu-zIKOLoWDjK2WhUJl8"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.6538190327103326,
					2.368959592636383
				],
				[
					1.525770585087841,
					7.468245495429926
				],
				[
					3.9348820352265133,
					5.862171195337454
				],
				[
					0.2007592875115677,
					0.44167043252542443
				]
			]
		},
		{
			"id": "SIBzqbvLbSLv65CW8mY2C",
			"type": "line",
			"x": -211.19194803544758,
			"y": -281.8583348712043,
			"width": 148.57008973793097,
			"height": 176.37267963040932,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1902706479,
			"version": 337,
			"versionNonce": 827268481,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-15.638956814518998,
					130.32464012099211
				],
				[
					33.01557549731798,
					130.32464012099211
				],
				[
					-36.49089923387784,
					176.37267963040932
				],
				[
					-115.55451424061299,
					128.58697825271224
				],
				[
					-60.81816538979626,
					128.58697825271224
				],
				[
					-86.01426247985478,
					0
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				1.737661868279929,
				0.8688309341399645
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "whO7Gmoq",
			"type": "text",
			"x": -454.79824081459446,
			"y": -99.78800683190815,
			"width": 420.0594482421875,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1268322959,
			"version": 181,
			"versionNonce": 618411791,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"text": "Can we make use of patterns in the data\nin order to represent it in such a way\nthat helps us get over the hurdle\nof not having labels?",
			"rawText": "Can we make use of patterns in the data\nin order to represent it in such a way\nthat helps us get over the hurdle\nof not having labels?",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "Can we make use of patterns in the data\nin order to represent it in such a way\nthat helps us get over the hurdle\nof not having labels?",
			"lineHeight": 1.25
		},
		{
			"id": "uIbttZDj",
			"type": "text",
			"x": -526.1956487161912,
			"y": 189.0430440592162,
			"width": 570.2193603515625,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1135809135,
			"version": 101,
			"versionNonce": 1332856161,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "jtEgIuQjD3xYvk-WnsAMU",
					"type": "arrow"
				},
				{
					"id": "rLA3v9qUSzKVYu8LlXtPx",
					"type": "arrow"
				},
				{
					"id": "EOxAspbu2zaNAytM9iqmA",
					"type": "arrow"
				}
			],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"text": "Learn semantic representations of data from patterns in\nobservation space and encode it into latent space",
			"rawText": "Learn semantic representations of data from patterns in\nobservation space and encode it into latent space",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "Learn semantic representations of data from patterns in\nobservation space and encode it into latent space",
			"lineHeight": 1.25
		},
		{
			"id": "jtEgIuQjD3xYvk-WnsAMU",
			"type": "arrow",
			"x": -339.9208403305844,
			"y": 251.2728319849653,
			"width": 89.85878408383621,
			"height": 74.48423802448542,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1857867041,
			"version": 238,
			"versionNonce": 1837137199,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.7462889188868758,
					73.2343711703187
				],
				[
					-89.85878408383621,
					74.48423802448542
				]
			],
			"lastCommittedPoint": [
				-105.274408557333,
				120.83671243102577
			],
			"startBinding": {
				"elementId": "uIbttZDj",
				"focus": 0.3406387529605467,
				"gap": 12.229787925749122
			},
			"endBinding": {
				"elementId": "e1zWpLd0",
				"focus": -0.24036164361894874,
				"gap": 10.24628891888699
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "e1zWpLd0",
			"type": "text",
			"x": -902.5868264192451,
			"y": 307.23088480282615,
			"width": 462.5609130859375,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1041578081,
			"version": 350,
			"versionNonce": 112488769,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "jtEgIuQjD3xYvk-WnsAMU",
					"type": "arrow"
				}
			],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"text": "Since we have a large amount of unlabeled data\nwe can use this in order to greatly improve and generalize\nour feature extractor to be actually meaningful",
			"rawText": "Since we have a large amount of unlabeled data\nwe can use this in order to greatly improve and generalize\nour feature extractor to be actually meaningful",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "Since we have a large amount of unlabeled data\nwe can use this in order to greatly improve and generalize\nour feature extractor to be actually meaningful",
			"lineHeight": 1.25
		},
		{
			"id": "NQ-w02Eq_nO-iz8romiD8",
			"type": "arrow",
			"x": -149.40661811016048,
			"y": 256.50027166913105,
			"width": 111.08409535507428,
			"height": 72.1571901451764,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1763102369,
			"version": 81,
			"versionNonce": 1106706255,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					6.646056987055772,
					72.1571901451764
				],
				[
					111.08409535507428,
					70.25831672030336
				]
			],
			"lastCommittedPoint": [
				111.08409535507428,
				70.25831672030336
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "m1HQPOF2",
				"focus": 0.25977623393243415,
				"gap": 13.796722637833682
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "m1HQPOF2",
			"type": "text",
			"x": -24.525800117252516,
			"y": 294.4777401665923,
			"width": 359.7767333984375,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 670659055,
			"version": 239,
			"versionNonce": 1014407457,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "NQ-w02Eq_nO-iz8romiD8",
					"type": "arrow"
				}
			],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"text": "By mapping the data to latent space we can\ncluster the data according to \"distances\" in \nlatent space in order to measure similarity\nand dissimilarity ",
			"rawText": "By mapping the data to latent space we can\ncluster the data according to \"distances\" in \nlatent space in order to measure similarity\nand dissimilarity ",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "By mapping the data to latent space we can\ncluster the data according to \"distances\" in \nlatent space in order to measure similarity\nand dissimilarity ",
			"lineHeight": 1.25
		},
		{
			"id": "rLA3v9qUSzKVYu8LlXtPx",
			"type": "arrow",
			"x": -289.1532131688009,
			"y": 254.84177721762234,
			"width": 91.34152404403835,
			"height": 152.57481744322678,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 946448065,
			"version": 159,
			"versionNonce": 1687698799,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-6.447570476130977,
					105.03096915126491
				],
				[
					-91.34152404403835,
					152.57481744322678
				]
			],
			"lastCommittedPoint": [
				-32.02163693636135,
				175.47857041125962
			],
			"startBinding": {
				"elementId": "uIbttZDj",
				"focus": 0.15895208581945242,
				"gap": 15.79873315840615
			},
			"endBinding": {
				"elementId": "x44rMRro",
				"focus": -0.2032106921016776,
				"gap": 15.079215150364263
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "x44rMRro",
			"type": "text",
			"x": -640.9239092454601,
			"y": 422.4958098112133,
			"width": 371.8407287597656,
			"height": 120,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 390613921,
			"version": 446,
			"versionNonce": 2116539649,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "rLA3v9qUSzKVYu8LlXtPx",
					"type": "arrow"
				}
			],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"text": "By mapping data into latent space\nWe have a general purpose space that\nrepresents different types of modalities\n(Text, Image...) which we can use to corrolate\nthem together (Obviously the way we map each\nmodality to the latent space will be different)",
			"rawText": "By mapping data into latent space\nWe have a general purpose space that\nrepresents different types of modalities\n(Text, Image...) which we can use to corrolate\nthem together (Obviously the way we map each\nmodality to the latent space will be different)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "By mapping data into latent space\nWe have a general purpose space that\nrepresents different types of modalities\n(Text, Image...) which we can use to corrolate\nthem together (Obviously the way we map each\nmodality to the latent space will be different)",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 150,
			"versionNonce": 950843279,
			"isDeleted": false,
			"id": "EOxAspbu2zaNAytM9iqmA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -210.26659295672846,
			"y": 252.8837637347683,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 61.22589227427801,
			"height": 159.28260002248567,
			"seed": 286209775,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "uIbttZDj",
				"focus": -0.09919974452224603,
				"gap": 13.840719675552123
			},
			"endBinding": {
				"elementId": "X4GrHQxl",
				"focus": -0.38595687512657745,
				"gap": 11.907635050570207
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
					6.44757047613098,
					105.03096915126496
				],
				[
					61.22589227427801,
					159.28260002248567
				]
			]
		},
		{
			"id": "X4GrHQxl",
			"type": "text",
			"x": -211.09932098148772,
			"y": 424.0739988078242,
			"width": 378.0328063964844,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1419779105,
			"version": 230,
			"versionNonce": 2135395553,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "EOxAspbu2zaNAytM9iqmA",
					"type": "arrow"
				}
			],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"text": "By mapping our data into latent space\nwe can Use this space to search for semantics\n/ features and get the K-closest results",
			"rawText": "By mapping our data into latent space\nwe can Use this space to search for semantics\n/ features and get the K-closest results",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "By mapping our data into latent space\nwe can Use this space to search for semantics\n/ features and get the K-closest results",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 1783,
			"versionNonce": 611118511,
			"isDeleted": false,
			"id": "IZ9_65hhANwjS3Y9oJA-a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1041.405958443445,
			"y": 653.1337950909938,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 330.3676241451107,
			"height": 423.04414772437354,
			"seed": 119185007,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1776,
			"versionNonce": 1466255553,
			"isDeleted": false,
			"id": "uAKgo9gDBw7PLgW7DEw3f",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1051.1353447215265,
			"y": 657.7250551979623,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d2bab0",
			"width": 330.3676241451107,
			"height": 423.04414772437354,
			"seed": 2117793935,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1437,
			"versionNonce": 855728079,
			"isDeleted": false,
			"id": "8rPoPbpl0pEznsyCROVqQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1024.7877667592752,
			"y": 992.4155677503743,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 9113263,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1491,
			"versionNonce": 2132129,
			"isDeleted": false,
			"id": "mB7luOalAT3NO1D6xngdS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1084.7906676232146,
			"y": 986.3697958071634,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 145973455,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1447,
			"versionNonce": 1988267503,
			"isDeleted": false,
			"id": "fpyIXFSonsE18JEgudXdO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1022.2331574883215,
			"y": 937.6333911621152,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 676097775,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1463,
			"versionNonce": 321440897,
			"isDeleted": false,
			"id": "y9eedt44ao0nItjyLwcDA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1021.0977755901181,
			"y": 878.5935324555996,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 702462223,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1470,
			"versionNonce": 704182287,
			"isDeleted": false,
			"id": "zo3xb9QRPraSN14pW_Yzh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1023.3685393865226,
			"y": 821.2567465963871,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 1927462703,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1469,
			"versionNonce": 1211995233,
			"isDeleted": false,
			"id": "zT--5Sr6MfQ3Nu-uE9-el",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1020.5300846410173,
			"y": 762.7845788389725,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 633405775,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1462,
			"versionNonce": 324869679,
			"isDeleted": false,
			"id": "84bo-R7JHYCEopd-eDIZQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1021.6654665392193,
			"y": 704.8801020306585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 17.59841942213491,
			"height": 17.59841942213522,
			"seed": 64094063,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1482,
			"versionNonce": 858677313,
			"isDeleted": false,
			"id": "ygCZiHrtfWbHocF6ACwtF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1085.432795965262,
			"y": 698.0541702277651,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 257833359,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1479,
			"versionNonce": 630685775,
			"isDeleted": false,
			"id": "vja6jqEl1YLeocEIIvDOF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1084.1485392811655,
			"y": 757.1299776961503,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 1839083439,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1498,
			"versionNonce": 1104850977,
			"isDeleted": false,
			"id": "6bnVPXnQuNPXuhHx49fRH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1086.07492430731,
			"y": 813.6372717963438,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 146432463,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1492,
			"versionNonce": 1652596335,
			"isDeleted": false,
			"id": "_-aqYNXM5OkbUgW7RW_uU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1085.432795965262,
			"y": 873.3552076067765,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 1909149679,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1486,
			"versionNonce": 2050098177,
			"isDeleted": false,
			"id": "48PK1Nt3ljOQBntBJjMCq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1084.7906676232146,
			"y": 931.1467583910653,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 71.27624596729014,
			"height": 30.18003207623995,
			"seed": 47806991,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1654,
			"versionNonce": 2095118479,
			"isDeleted": false,
			"id": "wg04LwkJ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -959.5055740068015,
			"y": 673.4803529780495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 192.58482360839844,
			"height": 35,
			"seed": 1088249903,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Pretext Task",
			"rawText": "Pretext Task",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Pretext Task",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"id": "M2a3KLlx",
			"type": "text",
			"x": -998.5474815297412,
			"y": 759.5761715192303,
			"width": 271.6396789550781,
			"height": 225,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"FuFGamfT9oo6S4ns3QvEH"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1489898017,
			"version": 1542,
			"versionNonce": 2016664545,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"text": "Pretext tasks are tasks\nthat use unlabeled data\nalongside an objective goal\nin order to define right and\nwrong solutions.\nThese objectives are\nperformed on a property\nthat is inherent in\nthe dataset itself.",
			"rawText": "Pretext tasks are tasks\nthat use unlabeled data\nalongside an objective goal\nin order to define right and\nwrong solutions.\nThese objectives are\nperformed on a property\nthat is inherent in\nthe dataset itself.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 218,
			"containerId": null,
			"originalText": "Pretext tasks are tasks\nthat use unlabeled data\nalongside an objective goal\nin order to define right and\nwrong solutions.\nThese objectives are\nperformed on a property\nthat is inherent in\nthe dataset itself.",
			"lineHeight": 1.25
		},
		{
			"id": "TI-MyDS40TC9jeMNblpYc",
			"type": "image",
			"x": -704.9812553813238,
			"y": 679.1895099125096,
			"width": 117.67253252114526,
			"height": 116.91335489197657,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 976197153,
			"version": 805,
			"versionNonce": 980487855,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "97r9QitOfDYUe3gu4DwPS",
					"type": "arrow"
				}
			],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3187e5f535cff0aaa01c3b6765c034797449d321",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "97r9QitOfDYUe3gu4DwPS",
			"type": "arrow",
			"x": -583.9385021106857,
			"y": 767.2468292546625,
			"width": 73.00928038352504,
			"height": 1.1681484861364289,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 334466881,
			"version": 2489,
			"versionNonce": 737130433,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					73.00928038352504,
					1.1681484861364289
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "ywminjdp",
				"focus": 2.6377814275470786,
				"gap": 13.255990918939403
			},
			"endBinding": {
				"elementId": "nXTmUsBIWDyJpBr8cjY_3",
				"focus": 1.383209065466997,
				"gap": 23.60015608491176
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "RA9w4LXt6W8LNNV48VP1b",
			"type": "image",
			"x": -506.21314263557974,
			"y": 679.9213941132139,
			"width": 114.63582200447053,
			"height": 119.95006540865128,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 508112079,
			"version": 782,
			"versionNonce": 366567631,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "97r9QitOfDYUe3gu4DwPS",
					"type": "arrow"
				}
			],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7af7db0fe8f12cb0229995fc05f3cc483f14c204",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "YY06m12MZCwXS15EonllD",
			"type": "image",
			"x": -700.8253051149202,
			"y": 794.3265194944433,
			"width": 112.11813563992123,
			"height": 111.11708085742194,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1167991809,
			"version": 850,
			"versionNonce": 1468340129,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ZAZ21keT5KM7oW1i9nQww",
					"type": "arrow"
				}
			],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5067d7a646624a43e96765ac79fae9d9002bb47f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 3049,
			"versionNonce": 548564719,
			"isDeleted": false,
			"id": "ZAZ21keT5KM7oW1i9nQww",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -585.7673144109981,
			"y": 879.7205013052114,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 76.72187369171908,
			"height": 0.21200160933985635,
			"seed": 2013191713,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322180,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "80zRGUwH",
				"focus": 1.5447400898539396,
				"gap": 9.855300448552725
			},
			"endBinding": {
				"elementId": "nXTmUsBIWDyJpBr8cjY_3",
				"focus": -0.5779475305641433,
				"gap": 4.60805428386152
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
					76.72187369171908,
					0.21200160933985635
				]
			]
		},
		{
			"id": "ywminjdp",
			"type": "text",
			"x": -582.2626905479865,
			"y": 738.8072857523496,
			"width": 64.8082275390625,
			"height": 15.183552583373581,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2083222031,
			"version": 783,
			"versionNonce": 1294171009,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "97r9QitOfDYUe3gu4DwPS",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Re-arrange",
			"rawText": "Re-arrange",
			"fontSize": 12.146842066698865,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 10,
			"containerId": null,
			"originalText": "Re-arrange",
			"lineHeight": 1.25
		},
		{
			"id": "80zRGUwH",
			"type": "text",
			"x": -575.9120139624454,
			"y": 841.0684920119706,
			"width": 54.538330078125,
			"height": 30.367105166747162,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1981974689,
			"version": 776,
			"versionNonce": 629455119,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ZAZ21keT5KM7oW1i9nQww",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Fill in\nthe blank",
			"rawText": "Fill in\nthe blank",
			"fontSize": 12.146842066698865,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Fill in\nthe blank",
			"lineHeight": 1.25
		},
		{
			"id": "nXTmUsBIWDyJpBr8cjY_3",
			"type": "image",
			"x": -504.43738643541747,
			"y": 792.0151338257107,
			"width": 111.5311331830442,
			"height": 111.5311331830442,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1310340993,
			"version": 879,
			"versionNonce": 1829397345,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ZAZ21keT5KM7oW1i9nQww",
					"type": "arrow"
				},
				{
					"id": "97r9QitOfDYUe3gu4DwPS",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e8e22ff39be5ff6b28c879752b38a3faf43251e3",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "lgK3aRER1CRItK3nwQqXa",
			"type": "image",
			"x": -691.9742955488243,
			"y": 908.6347738934467,
			"width": 98.07857346088059,
			"height": 124.45832770208297,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 95445807,
			"version": 781,
			"versionNonce": 164151087,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "1QbgVuNDXYnfcm0uaLAdx",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6a758ac29208db3d41d8f7912f72596729642bf0",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "1QbgVuNDXYnfcm0uaLAdx",
			"type": "arrow",
			"x": -585.7877424420176,
			"y": 988.2774087023963,
			"width": 80.50428287600083,
			"height": 0.4173184167752903,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 362557825,
			"version": 2577,
			"versionNonce": 1669943105,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					80.50428287600083,
					0.4173184167752903
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "lgK3aRER1CRItK3nwQqXa",
				"focus": 0.27394856690624264,
				"gap": 8.107979645926207
			},
			"endBinding": {
				"elementId": "ZMYmFzRUfCfeIkRzG8ORp",
				"focus": -0.27489051203034376,
				"gap": 4.770151108817117
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "DEy6N4TM",
			"type": "text",
			"x": -566.7803425789755,
			"y": 966.0910496015567,
			"width": 29.645660400390625,
			"height": 15.183552583373581,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1049209487,
			"version": 751,
			"versionNonce": 1877410127,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Color",
			"rawText": "Color",
			"fontSize": 12.146842066698865,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 10,
			"containerId": null,
			"originalText": "Color",
			"lineHeight": 1.25
		},
		{
			"id": "ZMYmFzRUfCfeIkRzG8ORp",
			"type": "image",
			"x": -500.5133084571996,
			"y": 912.7921890248322,
			"width": 93.71325645449758,
			"height": 119.38812123655171,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2084881071,
			"version": 819,
			"versionNonce": 654294817,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "1QbgVuNDXYnfcm0uaLAdx",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "628ef8b824a61ee3577f37ac993257563acb977c",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "YpM8CwhjXdgeTZFxlPln0",
			"type": "line",
			"x": -364.97113794795996,
			"y": 786.5542359482661,
			"width": 233.61024703641078,
			"height": 179.949589238707,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1763601889,
			"version": 727,
			"versionNonce": 423100271,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					163.19579045021328,
					35.212667680232926
				],
				[
					167.56924648968334,
					-32.0749996714474
				],
				[
					233.61024703641078,
					74.5220002673461
				],
				[
					155.66562969231632,
					147.87458956725962
				],
				[
					160.60012103869735,
					85.26456608530967
				],
				[
					6.056561960203169,
					103.08876703649548
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				6.2101666889452645,
				6.210166688945492
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "QsQPcv8s",
			"type": "text",
			"x": 86.90958383945963,
			"y": 598.0558024911223,
			"width": 329.2533874511719,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2140580527,
			"version": 359,
			"versionNonce": 903688961,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Self-Supervised Learning",
			"rawText": "Self-Supervised Learning",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Self-Supervised Learning",
			"lineHeight": 1.25
		},
		{
			"id": "tyCIcf92",
			"type": "text",
			"x": -123.65722049132773,
			"y": 636.4826853833872,
			"width": 738.2991943359375,
			"height": 450,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1216012449,
			"version": 1435,
			"versionNonce": 134494607,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Usually in supervised learning we have labeled data and we learn\nby telling our model to adjust its parameters such that it outputs\nas close as possible to our label.\nsupervised learning usually learns both the features and\nthe given task together.\n\nSelf supervised learning requires pretext tasks (so unlabeled data)\nlearns by fine tuning its feature extractor.\nOur feature extractor's job is to represent all the meaningful semantic\ndetails of the data in feature/latent space such that the latent space\naccurately describes similarity and difference.\n\nWe then use This latent space in order to preform another (downstream)\ntask according to our description of the data.\nSelf-supervised learning separates the task of learning features from the\nactual downstream task.\nHence the name \"self-supervised\" I.e we developed an understanding of the\ndata and \"labeled\" it accordingly to be able to use it for something else.",
			"rawText": "Usually in supervised learning we have labeled data and we learn\nby telling our model to adjust its parameters such that it outputs\nas close as possible to our label.\nsupervised learning usually learns both the features and\nthe given task together.\n\nSelf supervised learning requires pretext tasks (so unlabeled data)\nlearns by fine tuning its feature extractor.\nOur feature extractor's job is to represent all the meaningful semantic\ndetails of the data in feature/latent space such that the latent space\naccurately describes similarity and difference.\n\nWe then use This latent space in order to preform another (downstream)\ntask according to our description of the data.\nSelf-supervised learning separates the task of learning features from the\nactual downstream task.\nHence the name \"self-supervised\" I.e we developed an understanding of the\ndata and \"labeled\" it accordingly to be able to use it for something else.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 443,
			"containerId": null,
			"originalText": "Usually in supervised learning we have labeled data and we learn\nby telling our model to adjust its parameters such that it outputs\nas close as possible to our label.\nsupervised learning usually learns both the features and\nthe given task together.\n\nSelf supervised learning requires pretext tasks (so unlabeled data)\nlearns by fine tuning its feature extractor.\nOur feature extractor's job is to represent all the meaningful semantic\ndetails of the data in feature/latent space such that the latent space\naccurately describes similarity and difference.\n\nWe then use This latent space in order to preform another (downstream)\ntask according to our description of the data.\nSelf-supervised learning separates the task of learning features from the\nactual downstream task.\nHence the name \"self-supervised\" I.e we developed an understanding of the\ndata and \"labeled\" it accordingly to be able to use it for something else.",
			"lineHeight": 1.25
		},
		{
			"id": "EjFXPTdK_h9oQF7PNarce",
			"type": "image",
			"x": -139.99748308299195,
			"y": 1095.3661390010402,
			"width": 120.00000000000001,
			"height": 197,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 590238287,
			"version": 230,
			"versionNonce": 346106593,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8a14068ec4715e1db9baf1da3152a60c1b0ebd81",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 887,
			"versionNonce": 1636052911,
			"isDeleted": false,
			"id": "Rat-HWjblaGO-i4PEFEEt",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -28.015031390928016,
			"y": 1143.320124745391,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 75.83783122287446,
			"height": 34.76024953299869,
			"seed": 39629935,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					52.97890383429052,
					6.801911137812006
				],
				[
					54.398676405012985,
					-6.195818490429438
				],
				[
					75.83783122287446,
					14.39516108900321
				],
				[
					50.534357553110084,
					28.564431042569254
				],
				[
					52.1362612651474,
					16.470265956076485
				],
				[
					1.9661659946670937,
					19.913306173121118
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "w55ZdB2pnC4p0TwZKYK8p",
			"type": "rectangle",
			"x": 273.823436720892,
			"y": 1109.3963987848283,
			"width": 197.96412984016814,
			"height": 93.30675016170903,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1994567649,
			"version": 416,
			"versionNonce": 198911681,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "lqsiSjic"
				},
				{
					"id": "-lAJnh1KAdtV9goZ-ERYj",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"id": "lqsiSjic",
			"type": "text",
			"x": 286.94560021275345,
			"y": 1131.0497738656827,
			"width": 171.7198028564453,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1031852033,
			"version": 421,
			"versionNonce": 266363343,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Encode data into\nlatent space",
			"rawText": "Encode data into\nlatent space",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 43,
			"containerId": "w55ZdB2pnC4p0TwZKYK8p",
			"originalText": "Encode data into\nlatent space",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 498,
			"versionNonce": 640329377,
			"isDeleted": false,
			"id": "lZzWA_PFWpmsQIQmldhLJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 55.89421341874004,
			"y": 1108.894862551827,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 118.5967571601629,
			"height": 93.30675016170903,
			"seed": 256924545,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "BGWQeaxI"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 615,
			"versionNonce": 607211503,
			"isDeleted": false,
			"id": "BGWQeaxI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 66.97264418388008,
			"y": 1130.5482376326813,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 96.43989562988281,
			"height": 50,
			"seed": 379274081,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Feature\nextractor",
			"rawText": "Feature extractor",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "lZzWA_PFWpmsQIQmldhLJ",
			"originalText": "Feature extractor",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 914,
			"versionNonce": 1849633409,
			"isDeleted": false,
			"id": "DgpkCj1yyydXsZ75NBMLj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 183.53991786229767,
			"y": 1146.0606774768428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 75.83783122287446,
			"height": 34.76024953299869,
			"seed": 1372768801,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					52.97890383429052,
					6.801911137812006
				],
				[
					54.398676405012985,
					-6.195818490429438
				],
				[
					75.83783122287446,
					14.39516108900321
				],
				[
					50.534357553110084,
					28.564431042569254
				],
				[
					52.1362612651474,
					16.470265956076485
				],
				[
					1.9661659946670937,
					19.913306173121118
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "vph8I9lBsg1brIeNb56-n",
			"type": "image",
			"x": 28.12415824320442,
			"y": 1245.7403973597388,
			"width": 128.02405633398166,
			"height": 104.4218560042532,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 478951585,
			"version": 315,
			"versionNonce": 2021620239,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d0a9d19100ef3cd08b1be324b71b3b9d2c00e3cc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 991,
			"versionNonce": 1826108001,
			"isDeleted": false,
			"id": "fB-Huf41t9OoMkB__6Mkv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 169.24127359661816,
			"y": 1300.4718204664905,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 75.83783122287446,
			"height": 34.76024953299869,
			"seed": 2134009409,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					52.97890383429052,
					6.801911137812006
				],
				[
					54.398676405012985,
					-6.195818490429438
				],
				[
					75.83783122287446,
					14.39516108900321
				],
				[
					50.534357553110084,
					28.564431042569254
				],
				[
					52.1362612651474,
					16.470265956076485
				],
				[
					1.9661659946670937,
					19.913306173121118
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "eRnHkXjXmxfrL32Ra07CE",
			"type": "rectangle",
			"x": 255.34797882727025,
			"y": 1269.469138881028,
			"width": 212.69273046855938,
			"height": 91.40514036665365,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1342019343,
			"version": 308,
			"versionNonce": 298016815,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "5s0Y3vqW"
				},
				{
					"id": "701a52jhNo3YkQYPtQ2eW",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"id": "5s0Y3vqW",
			"type": "text",
			"x": 296.54441882961635,
			"y": 1302.6717090643547,
			"width": 130.2998504638672,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 705142543,
			"version": 261,
			"versionNonce": 1724202561,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Target Task",
			"rawText": "Target Task",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "eRnHkXjXmxfrL32Ra07CE",
			"originalText": "Target Task",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 1162,
			"versionNonce": 1105560143,
			"isDeleted": false,
			"id": "1TEJFu6eavvoRUdnA2ER0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.5308176396716062,
			"x": 339.97282439306764,
			"y": 1223.25551863789,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 52.23199514145109,
			"height": 36.30586975261536,
			"seed": 2090538607,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					-1.502716851661381
				],
				[
					36.48830409640481,
					5.601642384995762
				],
				[
					37.46614790892108,
					-7.974033431561996
				],
				[
					52.23199514145109,
					13.53252744568245
				],
				[
					34.804665107488724,
					28.33183632105336
				],
				[
					35.90794859483308,
					15.6999021923873
				],
				[
					1.3541628370005687,
					19.296037759664266
				],
				[
					0,
					-1.502716851661381
				]
			]
		},
		{
			"type": "line",
			"version": 1005,
			"versionNonce": 1525009953,
			"isDeleted": false,
			"id": "H5qpGzHog46A4VMyYTozk",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 476.89753331277916,
			"y": 1302.091755026278,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 75.83783122287446,
			"height": 34.76024953299869,
			"seed": 1705071887,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					52.97890383429052,
					6.801911137812006
				],
				[
					54.398676405012985,
					-6.195818490429438
				],
				[
					75.83783122287446,
					14.39516108900321
				],
				[
					50.534357553110084,
					28.564431042569254
				],
				[
					52.1362612651474,
					16.470265956076485
				],
				[
					1.9661659946670937,
					19.913306173121118
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "YuoG523xzBlW-IUWTJcD4",
			"type": "ellipse",
			"x": 561.2856830376099,
			"y": 1273.3125199648289,
			"width": 116.1730852834855,
			"height": 80.35307658866054,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1859515489,
			"version": 309,
			"versionNonce": 163471471,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "w6mOEkrh"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"id": "w6mOEkrh",
			"type": "text",
			"x": 586.1688783752495,
			"y": 1301.0799555866372,
			"width": 66.25991821289062,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 935318465,
			"version": 326,
			"versionNonce": 1076453889,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "output",
			"rawText": "output",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 18,
			"containerId": "YuoG523xzBlW-IUWTJcD4",
			"originalText": "output",
			"lineHeight": 1.25
		},
		{
			"id": "-lAJnh1KAdtV9goZ-ERYj",
			"type": "arrow",
			"x": 480.51863537674717,
			"y": 1143.3035770485217,
			"width": 133.96928518605682,
			"height": 14.028197401681396,
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
			"roundness": {
				"type": 2
			},
			"seed": 1639198433,
			"version": 709,
			"versionNonce": 805904673,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713306268600,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					44.18882181529625,
					-14.028197401681396
				],
				[
					133.96928518605682,
					-2.8056394803363247
				]
			],
			"lastCommittedPoint": [
				133.96928518605682,
				-2.8056394803363105
			],
			"startBinding": {
				"elementId": "w55ZdB2pnC4p0TwZKYK8p",
				"gap": 8.731068815686996,
				"focus": 0.2747115548571131
			},
			"endBinding": {
				"elementId": "FySJECv8",
				"focus": -0.02859720308591467,
				"gap": 9.263261127234273
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "FySJECv8",
			"type": "text",
			"x": 623.7511816900383,
			"y": 1075.6682437647162,
			"width": 268.4805908203125,
			"height": 160,
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
			"seed": 1163481775,
			"version": 674,
			"versionNonce": 965882767,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "-lAJnh1KAdtV9goZ-ERYj",
					"type": "arrow"
				},
				{
					"id": "OZboZEROcVCCfa2iBFecJ",
					"type": "arrow"
				},
				{
					"id": "PUCHpTfPumwcs-lcBw2y4",
					"type": "arrow"
				},
				{
					"id": "icq_X_51me9I3BT8mxpTF",
					"type": "arrow"
				}
			],
			"updated": 1713301657151,
			"link": null,
			"locked": false,
			"text": "The first part teaches the model\nlots of semantic information\nabout the general purpose data\n(for example animals)\nThis part does not change its\nparameters after we are done\nlearning and have moved on to\nthe next part",
			"rawText": "The first part teaches the model\nlots of semantic information\nabout the general purpose data\n(for example animals)\nThis part does not change its\nparameters after we are done\nlearning and have moved on to\nthe next part",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 154,
			"containerId": null,
			"originalText": "The first part teaches the model\nlots of semantic information\nabout the general purpose data\n(for example animals)\nThis part does not change its\nparameters after we are done\nlearning and have moved on to\nthe next part",
			"lineHeight": 1.25
		},
		{
			"id": "701a52jhNo3YkQYPtQ2eW",
			"type": "arrow",
			"x": 325.51852031082717,
			"y": 1372.0682256476152,
			"width": 91.00653028708689,
			"height": 44.27344716669103,
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
			"roundness": {
				"type": 2
			},
			"seed": 1884496687,
			"version": 511,
			"versionNonce": 1533695233,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713306268602,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.6397573024698886,
					36.074660654340846
				],
				[
					-91.00653028708689,
					44.27344716669103
				]
			],
			"lastCommittedPoint": [
				-92.646287589557,
				54.93186963274627
			],
			"startBinding": {
				"elementId": "eRnHkXjXmxfrL32Ra07CE",
				"gap": 11.193946399933793,
				"focus": 0.30979943940458976
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "YBwC2LUC",
			"type": "text",
			"x": -64.65879577667806,
			"y": 1387.9907177255532,
			"width": 320.720703125,
			"height": 120,
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
			"seed": 1584752271,
			"version": 527,
			"versionNonce": 1176999361,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "The second part (Linear Probing)\n uses all that learnt features\nand semantics about animals in order to\nto vastly reduce the amount of labeled\ndata on the current task (Classifying\nthe name of an animal)",
			"rawText": "The second part (Linear Probing)\n uses all that learnt features\nand semantics about animals in order to\nto vastly reduce the amount of labeled\ndata on the current task (Classifying\nthe name of an animal)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "The second part (Linear Probing)\n uses all that learnt features\nand semantics about animals in order to\nto vastly reduce the amount of labeled\ndata on the current task (Classifying\nthe name of an animal)",
			"lineHeight": 1.25
		},
		{
			"id": "bWgorpsM",
			"type": "text",
			"x": 1523.4440750974732,
			"y": 970.3209875236103,
			"width": 256.7890319824219,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 792741839,
			"version": 497,
			"versionNonce": 1108763343,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "In-painting/Masking",
			"rawText": "In-painting/Masking",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "In-painting/Masking",
			"lineHeight": 1.25
		},
		{
			"id": "2XsFKIOj",
			"type": "text",
			"x": 1412.8777358217012,
			"y": 1014.9471575557641,
			"width": 488.3193664550781,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 529370735,
			"version": 586,
			"versionNonce": 1527854497,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Occlude a random part of the image with a mask\nThe model has to predict the missing content",
			"rawText": "Occlude a random part of the image with a mask\nThe model has to predict the missing content",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "Occlude a random part of the image with a mask\nThe model has to predict the missing content",
			"lineHeight": 1.25
		},
		{
			"id": "ELIWcVjOP4ty3GKHDnkwh",
			"type": "image",
			"x": 1455.107555611879,
			"y": 1075.1178461099985,
			"width": 423.2161244510707,
			"height": 240.1737639414333,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1965818209,
			"version": 539,
			"versionNonce": 33501423,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9a0582fead62dcfdc21de0dfd0dfcb9c3e4c105f",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "QD7y5RbU",
			"type": "text",
			"x": 1668.1378624189215,
			"y": 1308.721971748955,
			"width": 128.73629760742188,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1504731457,
			"version": 684,
			"versionNonce": 92002689,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Fill in the blanks",
			"rawText": "Fill in the blanks",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Fill in the blanks",
			"lineHeight": 1.25
		},
		{
			"id": "BQpokJpj",
			"type": "text",
			"x": 1452.6364409854014,
			"y": 1333.416323113738,
			"width": 476.22503662109375,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 634702241,
			"version": 524,
			"versionNonce": 65616655,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "s7YskMfDB_89uPwNr81J5",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "This works really well in vision, especially with a high masking\nratio (75%)",
			"rawText": "This works really well in vision, especially with a high masking\nratio (75%)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "This works really well in vision, especially with a high masking\nratio (75%)",
			"lineHeight": 1.25
		},
		{
			"id": "s7YskMfDB_89uPwNr81J5",
			"type": "arrow",
			"x": 1693.595121540311,
			"y": 1381.7048705643697,
			"width": 1.5800823834242692,
			"height": 45.822568584518194,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 707958895,
			"version": 1475,
			"versionNonce": 1990656353,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.5800823834242692,
					45.822568584518194
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "BQpokJpj",
				"focus": -0.00783367632383164,
				"gap": 8.288547450631768
			},
			"endBinding": {
				"elementId": "ZSXvoddN",
				"focus": -0.00874515036151485,
				"gap": 10.415026319818708
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "ZSXvoddN",
			"type": "text",
			"x": 1446.5273565951934,
			"y": 1437.9424654687066,
			"width": 505.0394287109375,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1910612687,
			"version": 552,
			"versionNonce": 1816985903,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "s7YskMfDB_89uPwNr81J5",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "This masking Technique can also be done with text\nwhich s used to train language models in NLP.\n",
			"rawText": "This masking Technique can also be done with text\nwhich s used to train language models in NLP.\n",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "This masking Technique can also be done with text\nwhich s used to train language models in NLP.\n",
			"lineHeight": 1.25
		},
		{
			"id": "nVKbNrTV",
			"type": "text",
			"x": 1941.7013265808846,
			"y": 1151.439283937804,
			"width": 224.9764862060547,
			"height": 100,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1167425935,
			"version": 681,
			"versionNonce": 199372097,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "zxpY2-h8AWPw_zqgASfmp",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "it is necessary to learn\nsemantic properties of an\nimage in order to be able to\nunderstand whats missing\nand fill it out correctly",
			"rawText": "it is necessary to learn\nsemantic properties of an\nimage in order to be able to\nunderstand whats missing\nand fill it out correctly",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 94,
			"containerId": null,
			"originalText": "it is necessary to learn\nsemantic properties of an\nimage in order to be able to\nunderstand whats missing\nand fill it out correctly",
			"lineHeight": 1.25
		},
		{
			"id": "zxpY2-h8AWPw_zqgASfmp",
			"type": "arrow",
			"x": 1876.186815623802,
			"y": 1196.9638419026155,
			"width": 58.959902764389426,
			"height": 0.22571062397855712,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 506960271,
			"version": 981,
			"versionNonce": 1016267599,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					58.959902764389426,
					0.22571062397855712
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "nVKbNrTV",
				"focus": 0.07523227561107738,
				"gap": 6.554608192693195
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "5YPNRqh3CG7AzEyfN9P-B",
			"type": "image",
			"x": 1488.1010934740693,
			"y": 1486.698818423314,
			"width": 415.15368108905614,
			"height": 78.0865619439718,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2132722433,
			"version": 720,
			"versionNonce": 1284300065,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0220811c694bbc4649363c0ba08f62fdf9a5818f",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "WCTdpIBH",
			"type": "text",
			"x": 1449.2672613297245,
			"y": 1572.0127615299884,
			"width": 501.9210205078125,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 205954735,
			"version": 511,
			"versionNonce": 890487151,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "words/tokens are already separate semantic entities which\nmakes the task generally better suited for masked predictions.",
			"rawText": "words/tokens are already separate semantic entities which\nmakes the task generally better suited for masked predictions.",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "words/tokens are already separate semantic entities which\nmakes the task generally better suited for masked predictions.",
			"lineHeight": 1.25
		},
		{
			"id": "OZboZEROcVCCfa2iBFecJ",
			"type": "arrow",
			"x": 915.7784502500144,
			"y": 1140.0362893951433,
			"width": 459.7460850614816,
			"height": 4.1048757594775225,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1893525281,
			"version": 418,
			"versionNonce": 672567553,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					459.7460850614816,
					4.1048757594775225
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "FySJECv8",
				"focus": -0.20986534339819865,
				"gap": 23.546677739663664
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "PUCHpTfPumwcs-lcBw2y4",
			"type": "arrow",
			"x": 915.7784502500144,
			"y": 1140.0362893951433,
			"width": 185.47926252886327,
			"height": 390.20230696408447,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1043109601,
			"version": 898,
			"versionNonce": 1998044047,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					173.77307381788114,
					39.680465674949346
				],
				[
					185.47926252886327,
					390.20230696408447
				]
			],
			"lastCommittedPoint": [
				186.08770109631405,
				337.968104196982
			],
			"startBinding": {
				"elementId": "FySJECv8",
				"focus": -0.46688216763943347,
				"gap": 23.546677739663664
			},
			"endBinding": {
				"elementId": "Li73Gg6F",
				"focus": 0.0021400598036569584,
				"gap": 12.115858899805971
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "Li73Gg6F",
			"type": "text",
			"x": 960.2477119452651,
			"y": 1542.3544552590338,
			"width": 283.38916015625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 992879055,
			"version": 277,
			"versionNonce": 1946077409,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "PUCHpTfPumwcs-lcBw2y4",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Contrastive Learning",
			"rawText": "Contrastive Learning",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Contrastive Learning",
			"lineHeight": 1.25
		},
		{
			"id": "UA1hW2Gj",
			"type": "text",
			"x": 815.8800618799692,
			"y": 1584.161836160747,
			"width": 567.619384765625,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1547630511,
			"version": 521,
			"versionNonce": 1725395375,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "When learning semantics, instead of only correlating\nand changing your result according to one pretext task\nwe can try to use multiple objectives to learn about the\nsemantics in different ways",
			"rawText": "When learning semantics, instead of only correlating\nand changing your result according to one pretext task\nwe can try to use multiple objectives to learn about the\nsemantics in different ways",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "When learning semantics, instead of only correlating\nand changing your result according to one pretext task\nwe can try to use multiple objectives to learn about the\nsemantics in different ways",
			"lineHeight": 1.25
		},
		{
			"id": "bp6vTAFkojIoQdueLTi56",
			"type": "image",
			"x": 741.030994118169,
			"y": 1768.9863049980536,
			"width": 136,
			"height": 111,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2031090465,
			"version": 373,
			"versionNonce": 701826241,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "nFxF57BF_Y63f8jHdPCnN",
					"type": "arrow"
				},
				{
					"id": "AjGA7rWdCxQewlxJSYHTG",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9444c80b3a42b4f0aa8c0fd6c19faf384cd6adf5",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "nFxF57BF_Y63f8jHdPCnN",
			"type": "arrow",
			"x": 883.4694473360341,
			"y": 1825.1533167100192,
			"width": 105.51679488969269,
			"height": 67.10048607062994,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2105592193,
			"version": 782,
			"versionNonce": 1299932111,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					57.88057195405468,
					-8.707696665654316
				],
				[
					55.83170215037121,
					-61.97831156142153
				],
				[
					105.51679488969269,
					-67.10048607062994
				]
			],
			"lastCommittedPoint": [
				141.98445706370467,
				-90.2910867735211
			],
			"startBinding": {
				"elementId": "bp6vTAFkojIoQdueLTi56",
				"focus": 0.18052184828755802,
				"gap": 6.438453217865117
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"type": "arrow",
			"version": 836,
			"versionNonce": 1698219169,
			"isDeleted": false,
			"id": "AjGA7rWdCxQewlxJSYHTG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 883.4694473360341,
			"y": 1825.0246559444422,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 105.51679488969303,
			"height": 67.10048607063015,
			"seed": 1758809697,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "bp6vTAFkojIoQdueLTi56",
				"focus": -0.16218378293662764,
				"gap": 6.438453217865117
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					57.88057195405486,
					8.707696665654344
				],
				[
					55.83170215037138,
					61.97831156142172
				],
				[
					105.51679488969303,
					67.10048607063015
				]
			]
		},
		{
			"id": "lx5fMqgOVIfjMxZzLODqb",
			"type": "arrow",
			"x": 1093.1831546504754,
			"y": 1762.4447095516543,
			"width": 64.99842550740323,
			"height": 0.30166284189999715,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1785668993,
			"version": 594,
			"versionNonce": 272239841,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713306268602,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					64.99842550740323,
					0.30166284189999715
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "eFNaibke2puMDLLh4bhy9",
				"gap": 3.2499212753700704,
				"focus": -0.027651548174360125
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"type": "arrow",
			"version": 574,
			"versionNonce": 2066435201,
			"isDeleted": false,
			"id": "55jXHg7JuV8oVEvInioF3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1099.276757041795,
			"y": 1889.1916392910894,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 60.93602391319018,
			"height": 0,
			"seed": 315791617,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713306268603,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "_UNtNszdn5p-Q4qdF8KR6",
				"gap": 3.656161434791102,
				"focus": 0.03823436794553024
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
					60.93602391319018,
					0
				]
			]
		},
		{
			"id": "eFNaibke2puMDLLh4bhy9",
			"type": "rectangle",
			"x": 1161.4315014332487,
			"y": 1719.383252653,
			"width": 131.62181165249012,
			"height": 85,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 126938863,
			"version": 338,
			"versionNonce": 683801615,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "lx5fMqgOVIfjMxZzLODqb",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "hqjYCgdl"
				},
				{
					"id": "AdHa7XOUsOBmZINMgVRdm",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"id": "hqjYCgdl",
			"type": "text",
			"x": 1177.4224685998258,
			"y": 1724.383252653,
			"width": 99.63987731933594,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2113892833,
			"version": 288,
			"versionNonce": 964087905,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Self-\nsupervised\nlearning",
			"rawText": "Self-supervised learning",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 68,
			"containerId": "eFNaibke2puMDLLh4bhy9",
			"originalText": "Self-supervised learning",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 345,
			"versionNonce": 1516610095,
			"isDeleted": false,
			"id": "_UNtNszdn5p-Q4qdF8KR6",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1163.8689423897763,
			"y": 1848.3165999287744,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 131.62181165249012,
			"height": 85,
			"seed": 598886465,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "eVNPh5KX"
				},
				{
					"id": "55jXHg7JuV8oVEvInioF3",
					"type": "arrow"
				},
				{
					"id": "t3VE5nzHO7xRHVsIaISsc",
					"type": "arrow"
				},
				{
					"id": "z6-lHZUi_iAOgebaxfqLD",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 293,
			"versionNonce": 568335425,
			"isDeleted": false,
			"id": "eVNPh5KX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1179.8599095563534,
			"y": 1853.3165999287744,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 99.63987731933594,
			"height": 75,
			"seed": 1235327009,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Self-\nsupervised\nlearning",
			"rawText": "Self-supervised learning",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "_UNtNszdn5p-Q4qdF8KR6",
			"originalText": "Self-supervised learning",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"id": "AdHa7XOUsOBmZINMgVRdm",
			"type": "arrow",
			"x": 1294.583904408286,
			"y": 1754.6895387401419,
			"width": 72.12439290517614,
			"height": 0.7554591933528627,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 243671119,
			"version": 989,
			"versionNonce": 1450379425,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713306268603,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					72.12439290517614,
					0.7554591933528627
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "eFNaibke2puMDLLh4bhy9",
				"gap": 1.530591322547025,
				"focus": -0.18289413880656588
			},
			"endBinding": {
				"elementId": "SquRHiZqe4PFbnbTCr1Cb",
				"gap": 7.049078884327969,
				"focus": -0.450266791661801
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"type": "arrow",
			"version": 839,
			"versionNonce": 1552998465,
			"isDeleted": false,
			"id": "t3VE5nzHO7xRHVsIaISsc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1296.7721102498185,
			"y": 1887.4387320524295,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 71.0796269100124,
			"height": 0.9899996833978548,
			"seed": 231619073,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713306268603,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "_UNtNszdn5p-Q4qdF8KR6",
				"gap": 1.2813562075521077,
				"focus": -0.05627809217917144
			},
			"endBinding": {
				"elementId": "GTB7f5-QMtz0fG1Km33Yl",
				"gap": 9.849547392863315,
				"focus": 1.5266844113693219
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
					71.0796269100124,
					-0.9899996833978548
				]
			]
		},
		{
			"id": "fd8hZW6y-TZpydYe6jGox",
			"type": "rectangle",
			"x": 1373.1492709430313,
			"y": 1676.4568465383184,
			"width": 19.645346969379062,
			"height": 136.8625838866749,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"hC_OdjzpGFt24rWoSHBjQ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 2112562671,
			"version": 379,
			"versionNonce": 473440879,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "AdHa7XOUsOBmZINMgVRdm",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"id": "Lw0aHMs0OHkhCjr26Sv_M",
			"type": "rectangle",
			"x": 1373.1325323007136,
			"y": 1694.6455728758192,
			"width": 19.370160809376316,
			"height": 103.41166496618631,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"hC_OdjzpGFt24rWoSHBjQ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1112518465,
			"version": 445,
			"versionNonce": 2091171841,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"id": "JHIMVVbPs_p05TF6bnzen",
			"type": "rectangle",
			"x": 1373.444954249252,
			"y": 1713.7033117366573,
			"width": 19.057738860837766,
			"height": 67.79556283281701,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"hC_OdjzpGFt24rWoSHBjQ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 662317711,
			"version": 458,
			"versionNonce": 487062671,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"id": "SquRHiZqe4PFbnbTCr1Cb",
			"type": "rectangle",
			"x": 1373.75737619779,
			"y": 1728.3871433179588,
			"width": 18.76347509702123,
			"height": 37.49063382459922,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"hC_OdjzpGFt24rWoSHBjQ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 435695361,
			"version": 424,
			"versionNonce": 351213537,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "AdHa7XOUsOBmZINMgVRdm",
					"type": "arrow"
				},
				{
					"id": "rRpVzu4SgIZPNIlr1j5nu",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"id": "UPCJ3zX0ezRTn9LyusGjm",
			"type": "line",
			"x": 1374.0716275831287,
			"y": 1747.1493505849603,
			"width": 18.03677286181269,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"hC_OdjzpGFt24rWoSHBjQ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 2108244399,
			"version": 376,
			"versionNonce": 1192727215,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					18.03677286181269,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "rectangle",
			"version": 386,
			"versionNonce": 98792385,
			"isDeleted": false,
			"id": "RBy8QkqejN3XN5bTpF0eH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1372.1848468234311,
			"y": 1844.3913017932773,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 19.645346969379062,
			"height": 136.8625838866749,
			"seed": 647248065,
			"groupIds": [
				"o-Tl5kKgigFNOWX9pu8zk"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "t3VE5nzHO7xRHVsIaISsc",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 451,
			"versionNonce": 1393517775,
			"isDeleted": false,
			"id": "siMFk3tj0Y7GVB4mO7aZT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1372.168108181114,
			"y": 1862.5800281307784,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 19.370160809376316,
			"height": 103.41166496618631,
			"seed": 1810987169,
			"groupIds": [
				"o-Tl5kKgigFNOWX9pu8zk"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 464,
			"versionNonce": 866210721,
			"isDeleted": false,
			"id": "8JdfqV_Hk38O0EVtMQQ29",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1372.480530129652,
			"y": 1881.6377669916164,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 19.057738860837766,
			"height": 67.79556283281701,
			"seed": 928758913,
			"groupIds": [
				"o-Tl5kKgigFNOWX9pu8zk"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 430,
			"versionNonce": 1351086831,
			"isDeleted": false,
			"id": "GTB7f5-QMtz0fG1Km33Yl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1372.79295207819,
			"y": 1896.3215985729175,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 18.76347509702123,
			"height": 37.49063382459922,
			"seed": 1217561697,
			"groupIds": [
				"o-Tl5kKgigFNOWX9pu8zk"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "aWmsfXN0Byxvvt7wk__al",
					"type": "arrow"
				},
				{
					"id": "t3VE5nzHO7xRHVsIaISsc",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 382,
			"versionNonce": 1381513089,
			"isDeleted": false,
			"id": "ene__Fop_41VXeC0mNouj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1373.107203463528,
			"y": 1915.0838058399195,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 18.03677286181269,
			"height": 0,
			"seed": 996495425,
			"groupIds": [
				"o-Tl5kKgigFNOWX9pu8zk"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					18.03677286181269,
					0
				]
			]
		},
		{
			"id": "rRpVzu4SgIZPNIlr1j5nu",
			"type": "arrow",
			"x": 1396.4444791627843,
			"y": 1749.7168018426787,
			"width": 75.42797033772877,
			"height": 71.9679716983834,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 559285537,
			"version": 661,
			"versionNonce": 1208597775,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					75.42797033772877,
					71.9679716983834
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "SquRHiZqe4PFbnbTCr1Cb",
				"focus": -0.36505020863306714,
				"gap": 3.923627867973096
			},
			"endBinding": {
				"elementId": "56e9Sc54",
				"focus": -0.6402414045827779,
				"gap": 7.63204037847845
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"type": "arrow",
			"version": 709,
			"versionNonce": 1682415457,
			"isDeleted": false,
			"id": "aWmsfXN0Byxvvt7wk__al",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1398.866478210326,
			"y": 1910.9527384361722,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 75.42797033772888,
			"height": 71.96797169838351,
			"seed": 1620618049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GTB7f5-QMtz0fG1Km33Yl",
				"focus": 0.42647439444916224,
				"gap": 7.310051035114952
			},
			"endBinding": {
				"elementId": "56e9Sc54",
				"focus": 0.6208739350865745,
				"gap": 5.210041330936747
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
					75.42797033772888,
					-71.96797169838351
				]
			]
		},
		{
			"id": "56e9Sc54",
			"type": "text",
			"x": 1479.5044898789915,
			"y": 1805.7687798000734,
			"width": 103.75987243652344,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1173726607,
			"version": 248,
			"versionNonce": 487408431,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "rRpVzu4SgIZPNIlr1j5nu",
					"type": "arrow"
				},
				{
					"id": "aWmsfXN0Byxvvt7wk__al",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "How similar\nare they?",
			"rawText": "How similar\nare they?",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "How similar\nare they?",
			"lineHeight": 1.25
		},
		{
			"id": "ftt3iT3N",
			"type": "text",
			"x": 741.1643835030377,
			"y": 1987.7647082296394,
			"width": 713.959228515625,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1781963297,
			"version": 437,
			"versionNonce": 2009008961,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "By training the model on two different augmentations of the data\nand telling it that theyre the same object thus their encoding needs to\nbe really close to each other, we can teach the model the semantics\nof said object.",
			"rawText": "By training the model on two different augmentations of the data\nand telling it that theyre the same object thus their encoding needs to\nbe really close to each other, we can teach the model the semantics\nof said object.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "By training the model on two different augmentations of the data\nand telling it that theyre the same object thus their encoding needs to\nbe really close to each other, we can teach the model the semantics\nof said object.",
			"lineHeight": 1.25
		},
		{
			"id": "UO9Zqeqe",
			"type": "text",
			"x": 734.7712046540646,
			"y": 2122.610209477617,
			"width": 741.8192138671875,
			"height": 100,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 587121633,
			"version": 509,
			"versionNonce": 804980047,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Problem: Representation collapse!\nThe optimal result for this model is to always encode into a constant\nnumber, by encoding a constant number, both encodings are always as close\nas possible to each other",
			"rawText": "Problem: Representation collapse!\nThe optimal result for this model is to always encode into a constant\nnumber, by encoding a constant number, both encodings are always as close\nas possible to each other",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "Problem: Representation collapse!\nThe optimal result for this model is to always encode into a constant\nnumber, by encoding a constant number, both encodings are always as close\nas possible to each other",
			"lineHeight": 1.25
		},
		{
			"id": "lDECn21z",
			"type": "text",
			"x": 618.9343465548955,
			"y": 2225.9076128710262,
			"width": 970.8189086914062,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 189346191,
			"version": 386,
			"versionNonce": 503489121,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "m2ZbC_CkWk8ro643Jn09P",
					"type": "arrow"
				}
			],
			"updated": 1713303392409,
			"link": null,
			"locked": false,
			"text": "Contrastive learning solves this issue by not only making sure that both augmentations\nof the same object are as close as possible to each other in latent space, but also that\nevery two different objects representations in latent space is as far as possible from eachother\n\nthis will turn our latent space into clusters of similar objects",
			"rawText": "Contrastive learning solves this issue by not only making sure that both augmentations\nof the same object are as close as possible to each other in latent space, but also that\nevery two different objects representations in latent space is as far as possible from eachother\n\nthis will turn our latent space into clusters of similar objects",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 118,
			"containerId": null,
			"originalText": "Contrastive learning solves this issue by not only making sure that both augmentations\nof the same object are as close as possible to each other in latent space, but also that\nevery two different objects representations in latent space is as far as possible from eachother\n\nthis will turn our latent space into clusters of similar objects",
			"lineHeight": 1.25
		},
		{
			"id": "1A4nsjbDhykbBYGMsV_2n",
			"type": "arrow",
			"x": 800.5654016836213,
			"y": 2604.8742996586147,
			"width": 629.8295711426499,
			"height": 0,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 556496879,
			"version": 71,
			"versionNonce": 1076593519,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					629.8295711426499,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "zJmlMmMC",
				"focus": 2.2596591422853085,
				"gap": 15.745739278566361
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "3Bfg_1Rznhm2c4pvFLwLV",
			"type": "arrow",
			"x": 1115.4801872549465,
			"y": 2816.916921943307,
			"width": 0,
			"height": 433.53268813652403,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 763454561,
			"version": 91,
			"versionNonce": 1288957697,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-433.53268813652403
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "gybi8t3w",
				"focus": 0.04727390802489775,
				"gap": 1
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "zJmlMmMC",
			"type": "text",
			"x": 1379.6867268584974,
			"y": 2620.620038937181,
			"width": 88.81990051269531,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 460961295,
			"version": 74,
			"versionNonce": 233258383,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "1A4nsjbDhykbBYGMsV_2n",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Features",
			"rawText": "Features",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Features",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 93,
			"versionNonce": 358639329,
			"isDeleted": false,
			"id": "gybi8t3w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1073.1696689024077,
			"y": 2358.28764238393,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 88.81990051269531,
			"height": 25,
			"seed": 406140335,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "3Bfg_1Rznhm2c4pvFLwLV",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Features",
			"rawText": "Features",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Features",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 417,
			"versionNonce": 1013363631,
			"isDeleted": false,
			"id": "337Spl11ZasRcvPWLH5Mf",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 880.156107595365,
			"y": 2429.2821632861987,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 57.63602461411599,
			"height": 42.56778288493534,
			"seed": 193615361,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "da4dc7fe07f90efe656d5a0b241750dcefc623ff",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 365,
			"versionNonce": 693297857,
			"isDeleted": false,
			"id": "aB9CVqyIH-QE4uad_ifdp",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 935.5715623639527,
			"y": 2389.1210627402493,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 49.70116570508217,
			"height": 39.96242377638364,
			"seed": 714544943,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "00ce334e0731ae23b97d07760b1513042e4daa00",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "my2ItBTQEHoXZpK9iSgAb",
			"type": "image",
			"x": 1167.498657916337,
			"y": 2718.6805960617494,
			"width": 69.16619074144819,
			"height": 55.761890210159784,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 946298735,
			"version": 147,
			"versionNonce": 1943168463,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cbe5fdb02d4582f3742a71d80e984064768eade4",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Aqz7gcO5J1uvwXB9HQd0v",
			"type": "image",
			"x": 1226.7330352710794,
			"y": 2656.6967469933434,
			"width": 58.545252930622524,
			"height": 46.46448645287502,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1233564463,
			"version": 74,
			"versionNonce": 894100129,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "90e063de1f2f13e275058785dd97657c52f8346d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "TOlG3Nc44msCgMRUVkuwY",
			"type": "image",
			"x": 957.6051834873579,
			"y": 2544.4318550148205,
			"width": 56.47016741478663,
			"height": 48.710907770006784,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1402498479,
			"version": 87,
			"versionNonce": 1128453103,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "aa8e3cef428f5c97511a8dc3a406255c9f746fbf",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "cCui0ML5N-Sh5BfmLlWak",
			"type": "image",
			"x": 998.667645511183,
			"y": 2502.2815324301923,
			"width": 40.4692259460885,
			"height": 36.83737233554209,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 295141505,
			"version": 80,
			"versionNonce": 637003393,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f1e3004e06538d525acd816a7daad177b4b3b018",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ZpiIpQqC8-hkZD5R71rkh",
			"type": "image",
			"x": 830.9747421349284,
			"y": 2528.9270775466366,
			"width": 47.694283341803626,
			"height": 54.94875362356664,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1111710017,
			"version": 129,
			"versionNonce": 1119911439,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f7515745eac029dbd3121589d1c37608aa75ff80",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "HKvmXihRYg2hJeqaqYMwH",
			"type": "ellipse",
			"x": 797.7749363355122,
			"y": 2357.3482104148516,
			"width": 307.68693825985974,
			"height": 279.3642912233877,
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
			"roundness": null,
			"seed": 939857647,
			"version": 73,
			"versionNonce": 639200865,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"id": "pz955cP0",
			"type": "text",
			"x": 748.1433276001769,
			"y": 2471.776619419405,
			"width": 46.4801025390625,
			"height": 40,
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
			"roundness": null,
			"seed": 1397172751,
			"version": 95,
			"versionNonce": 1967383599,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Animal\nspace",
			"rawText": "Animal\nspace",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Animal\nspace",
			"lineHeight": 1.25
		},
		{
			"id": "zDfYjEYRKu2MUGLObWIvU",
			"type": "ellipse",
			"x": 1098.5152248446643,
			"y": 2643.733537794951,
			"width": 405.42344585716614,
			"height": 172.22875707466073,
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
			"seed": 1428593711,
			"version": 135,
			"versionNonce": 1551825473,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"id": "CF2oy3PA",
			"type": "text",
			"x": 1269.3311678205537,
			"y": 2822.8209621867436,
			"width": 69.88815307617188,
			"height": 40,
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
			"seed": 1750025871,
			"version": 44,
			"versionNonce": 1790281295,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Furniture\nspace",
			"rawText": "Furniture\nspace",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Furniture\nspace",
			"lineHeight": 1.25
		},
		{
			"id": "Jy5YD5s9XhwHMJ5ZDhlSi",
			"type": "ellipse",
			"x": 864.5524512229273,
			"y": 2374.7725284891526,
			"width": 142.19332805259967,
			"height": 116.48309530508186,
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
			"seed": 831990561,
			"version": 71,
			"versionNonce": 1778911777,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false
		},
		{
			"id": "EfmMhD6w",
			"type": "text",
			"x": 827.3201464087175,
			"y": 2423.5695008466873,
			"width": 35.90528869628906,
			"height": 32.65421921499455,
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
			"seed": 1886023905,
			"version": 29,
			"versionNonce": 569238639,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "Dog\nspace",
			"rawText": "Dog\nspace",
			"fontSize": 13.06168768599782,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 27,
			"containerId": null,
			"originalText": "Dog\nspace",
			"lineHeight": 1.25
		},
		{
			"id": "15KVaHxv-F6U2OkPMrzBj",
			"type": "arrow",
			"x": 980.4023581101176,
			"y": 1723.4819607121426,
			"width": 170.53386382609074,
			"height": 18.43609338660417,
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
			"seed": 279497473,
			"version": 58,
			"versionNonce": 665067009,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-103.24212296498467,
					-18.43609338660417
				],
				[
					-170.53386382609074,
					-10.139851362632271
				]
			],
			"lastCommittedPoint": [
				-170.53386382609074,
				-10.139851362632271
			],
			"startBinding": {
				"elementId": "x8vpe8GwBYZWxoHEFBs2s",
				"focus": 0.58023597338673,
				"gap": 4.39228302414881
			},
			"endBinding": {
				"elementId": "Jk8S579e",
				"focus": 0.22110549167672955,
				"gap": 5.364814169900114
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "Jk8S579e",
			"type": "text",
			"x": 714.8234890740877,
			"y": 1693.8873236928005,
			"width": 89.68019104003906,
			"height": 40,
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
			"seed": 1942792463,
			"version": 43,
			"versionNonce": 716537487,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "15KVaHxv-F6U2OkPMrzBj",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "referred to\nas views",
			"rawText": "referred to\nas views",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "referred to\nas views",
			"lineHeight": 1.25
		},
		{
			"id": "vhul05uO9CRtw6P8N31pQ",
			"type": "image",
			"x": -409.7033161142051,
			"y": 1973.6413862811337,
			"width": 717,
			"height": 106,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 564680399,
			"version": 182,
			"versionNonce": 609400289,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "edc4764348121c501d935d68654f965c54a9ce9d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "z5X_7gSxjSJOdZNvSlpwr",
			"type": "line",
			"x": -151.39520983684133,
			"y": 2046.5350180562264,
			"width": 189.8586028456715,
			"height": 29.047103317852383,
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
			"seed": 711652961,
			"version": 509,
			"versionNonce": 130340015,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					6.735560189647008,
					10.945285308176615
				],
				[
					71.56532701499809,
					12.629175355588368
				],
				[
					81.24769478761556,
					25.679323223029332
				],
				[
					97.6656227498798,
					11.366257820029666
				],
				[
					183.54401516787755,
					11.366257820029212
				],
				[
					189.8586028456715,
					-3.367780094823049
				]
			],
			"lastCommittedPoint": [
				189.85860284567138,
				3.367780094823047
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "96RQ3iZw",
			"type": "text",
			"x": -148.111628561599,
			"y": 2078.4625310326865,
			"width": 180.784423828125,
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
			"seed": 179844129,
			"version": 262,
			"versionNonce": 1663259073,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ymYLh-JEM63KN30XjqkWc",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"text": "How similar the first is\nto the second",
			"rawText": "How similar the first is\nto the second",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "How similar the first is\nto the second",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 561,
			"versionNonce": 1355048655,
			"isDeleted": false,
			"id": "mfqNUcwXka7wdAxTVoTLG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 79.06180908859483,
			"y": 2047.0266568962775,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 189.8586028456715,
			"height": 29.04710331785238,
			"seed": 77514255,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.735560189647008,
					10.945285308176615
				],
				[
					71.56532701499809,
					12.629175355588368
				],
				[
					81.24769478761556,
					25.679323223029332
				],
				[
					97.6656227498798,
					11.366257820029666
				],
				[
					183.54401516787755,
					11.366257820029212
				],
				[
					189.8586028456715,
					-3.367780094823049
				]
			]
		},
		{
			"type": "text",
			"version": 320,
			"versionNonce": 1496674721,
			"isDeleted": false,
			"id": "bWZB0n4y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 69.14540471741907,
			"y": 2077.9199908529527,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 195.8084259033203,
			"height": 40,
			"seed": 1947806767,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "sbIl26bBCOvU5N1tavOv-",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "How similar the second is\nto the first",
			"rawText": "How similar the second is\nto the first",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How similar the second is\nto the first",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"id": "sbIl26bBCOvU5N1tavOv-",
			"type": "arrow",
			"x": 155.11883733622085,
			"y": 2127.0088564243665,
			"width": 77.72529322065563,
			"height": 127.06395761289751,
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
			"seed": 414214369,
			"version": 612,
			"versionNonce": 340571375,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.027616344886816,
					54.7456413119399
				],
				[
					-67.58721149622197,
					63.531978806448755
				],
				[
					-75.69767687576882,
					127.06395761289751
				]
			],
			"lastCommittedPoint": [
				-83.33116211103925,
				139.87730782924427
			],
			"startBinding": {
				"elementId": "bWZB0n4y",
				"focus": 0.13186833423790612,
				"gap": 9.088865571413862
			},
			"endBinding": {
				"elementId": "BMs2t3eLE2Bq42C5Tsbxe",
				"focus": -0.03987810699871459,
				"gap": 11.136068175512719
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "ymYLh-JEM63KN30XjqkWc",
			"type": "arrow",
			"x": -38.18058754297431,
			"y": 2129.7123448842153,
			"width": 118.27762011838885,
			"height": 123.00872492312428,
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
			"seed": 1222096577,
			"version": 630,
			"versionNonce": 733517185,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.703488459849019,
					62.180234576524334
				],
				[
					104.08430570418197,
					66.23546726629756
				],
				[
					118.27762011838885,
					123.00872492312428
				]
			],
			"lastCommittedPoint": [
				130.2049407984989,
				135.41313843043872
			],
			"startBinding": {
				"elementId": "96RQ3iZw",
				"focus": -0.1992087171348114,
				"gap": 11.24981385152887
			},
			"endBinding": {
				"elementId": "BMs2t3eLE2Bq42C5Tsbxe",
				"focus": 0.056754412621022,
				"gap": 12.487812405437126
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "BMs2t3eLE2Bq42C5Tsbxe",
			"type": "image",
			"x": -165.8994449586512,
			"y": 2265.2088822127766,
			"width": 494.7467923513841,
			"height": 104.27398762562804,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1878731439,
			"version": 223,
			"versionNonce": 2045132559,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "sbIl26bBCOvU5N1tavOv-",
					"type": "arrow"
				},
				{
					"id": "ymYLh-JEM63KN30XjqkWc",
					"type": "arrow"
				}
			],
			"updated": 1713301322181,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "17c893838b9b90d50ccd9dd6c8cd3b460beba4c4",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "H-hE5utVUbd2Z9jRA8zXa",
			"type": "arrow",
			"x": 208.1682710735896,
			"y": 2275.042409485785,
			"width": 88.82308250294318,
			"height": 81.46503823361445,
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
			"seed": 811313487,
			"version": 452,
			"versionNonce": 1008750447,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713303072179,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					23.41856610771265,
					-50.24424482024233
				],
				[
					88.82308250294318,
					-81.46503823361445
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "okFul1fL",
				"focus": 0.5764573659506534,
				"gap": 3.9365522719600676
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "okFul1fL",
			"type": "text",
			"x": 300.92790584849286,
			"y": 2163.072670404976,
			"width": 199.37643432617188,
			"height": 40,
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
			"seed": 1011340065,
			"version": 311,
			"versionNonce": 1449888673,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "H-hE5utVUbd2Z9jRA8zXa",
					"type": "arrow"
				}
			],
			"updated": 1713303070826,
			"link": null,
			"locked": false,
			"text": "Similarity function usually\ncosine similarity",
			"rawText": "Similarity function usually\ncosine similarity",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Similarity function usually\ncosine similarity",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 607,
			"versionNonce": 522185025,
			"isDeleted": false,
			"id": "RRckYrfU_naIttAbezz4J",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -13.223873595918121,
			"y": 2341.823518522445,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 315.0553897693904,
			"height": 29.047103317852383,
			"seed": 1070305167,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1713301322182,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					11.177131344368824,
					10.945285308176615
				],
				[
					118.75702053391649,
					12.629175355588368
				],
				[
					134.8241468414465,
					25.679323223029332
				],
				[
					162.06840449334496,
					11.366257820029666
				],
				[
					304.57682913404483,
					11.366257820029212
				],
				[
					315.0553897693904,
					-3.367780094823049
				]
			]
		},
		{
			"id": "DmsqZLpJ",
			"type": "text",
			"x": -57.830914320388274,
			"y": 2381.0112831633974,
			"width": 365.9207763671875,
			"height": 40,
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
			"seed": 462773601,
			"version": 315,
			"versionNonce": 1377765199,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322182,
			"link": null,
			"locked": false,
			"text": "Similarity result normalized using softmax\nto reflect a ratio according to other samples",
			"rawText": "Similarity result normalized using softmax\nto reflect a ratio according to other samples",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Similarity result normalized using softmax\nto reflect a ratio according to other samples",
			"lineHeight": 1.25
		},
		{
			"id": "yo1bICqi2pFJr9cNF70Zt",
			"type": "arrow",
			"x": -50.5737553958038,
			"y": 2322.8993201789,
			"width": 171.25653895991854,
			"height": 43.54860990206316,
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
			"seed": 1382774287,
			"version": 478,
			"versionNonce": 682826017,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322182,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-39.65286886001013,
					34.867177790698406
				],
				[
					-171.25653895991854,
					43.54860990206316
				]
			],
			"lastCommittedPoint": [
				-170.23386803693916,
				43.0712196238037
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "hc7fmOAj",
				"focus": 0.06256389982229853,
				"gap": 9.00615492797624
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "hc7fmOAj",
			"type": "text",
			"x": -521.0931021157298,
			"y": 2333.5141225811994,
			"width": 290.25665283203125,
			"height": 80,
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
			"seed": 1979083969,
			"version": 319,
			"versionNonce": 1115637103,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "yo1bICqi2pFJr9cNF70Zt",
					"type": "arrow"
				}
			],
			"updated": 1713301322182,
			"link": null,
			"locked": false,
			"text": "Log keeps the same ratios\nbut turns the probability distribution\nto a concave one to navigate easily\n(I think)",
			"rawText": "Log keeps the same ratios\nbut turns the probability distribution\nto a concave one to navigate easily\n(I think)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "Log keeps the same ratios\nbut turns the probability distribution\nto a concave one to navigate easily\n(I think)",
			"lineHeight": 1.25
		},
		{
			"id": "xT7T8Cb5mFwLF39Nau-ZV",
			"type": "arrow",
			"x": -75.33121053492687,
			"y": 2285.8228680916504,
			"width": 145.95157077081512,
			"height": 65.58957228971849,
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
			"seed": 1205411073,
			"version": 378,
			"versionNonce": 471158017,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713301322182,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-14.181529143722855,
					-62.63508705144295
				],
				[
					-145.95157077081512,
					-65.58957228971849
				]
			],
			"lastCommittedPoint": [
				-145.95157077081512,
				-65.58957228971849
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "0X1HZZMe",
				"focus": -0.228102278935671,
				"gap": 6.604779602038093
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "0X1HZZMe",
			"type": "text",
			"x": -534.9442015327801,
			"y": 2186.55216408559,
			"width": 307.056640625,
			"height": 80,
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
			"seed": 1944625199,
			"version": 389,
			"versionNonce": 1416806287,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "xT7T8Cb5mFwLF39Nau-ZV",
					"type": "arrow"
				}
			],
			"updated": 1713301322182,
			"link": null,
			"locked": false,
			"text": "High similarity will result in high\nratio, thus high log, and we want high\nsimilarity to not affect our loss unlike\nlow similarity thus we negate it",
			"rawText": "High similarity will result in high\nratio, thus high log, and we want high\nsimilarity to not affect our loss unlike\nlow similarity thus we negate it",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "High similarity will result in high\nratio, thus high log, and we want high\nsimilarity to not affect our loss unlike\nlow similarity thus we negate it",
			"lineHeight": 1.25
		},
		{
			"id": "8GqlBXmAyHzYnVaUEQdtj",
			"type": "image",
			"x": 321.0011707068643,
			"y": 2209.2232304589074,
			"width": 163.57862179388113,
			"height": 34.40791699802327,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1228647233,
			"version": 262,
			"versionNonce": 1585069199,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713303067688,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "25dc7135aa9762b3f29c542557c6e5065d66e21d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "-3UM_XRMqS5N4Gky0v-80",
			"type": "arrow",
			"x": 678.7170165385752,
			"y": 2025.8380438476524,
			"width": 241.22144709261056,
			"height": 1.4358419469797354,
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
			"seed": 1797535393,
			"version": 69,
			"versionNonce": 1781659055,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322182,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-241.22144709261056,
					1.4358419469797354
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "z6-lHZUi_iAOgebaxfqLD",
			"type": "arrow",
			"x": 1243.9658869417049,
			"y": 1945.701790207813,
			"width": 586.9741165365372,
			"height": 45.95130136773537,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 685987823,
			"version": 513,
			"versionNonce": 451751969,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713306268603,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					50.254468144293696,
					37.331890621475395
				],
				[
					586.9741165365372,
					45.95130136773537
				]
			],
			"lastCommittedPoint": [
				608.7969855194456,
				24.409313098656867
			],
			"startBinding": {
				"elementId": "_UNtNszdn5p-Q4qdF8KR6",
				"gap": 12.385190279038625,
				"focus": 0.48444713979112636
			},
			"endBinding": {
				"elementId": "WFcHREc8",
				"focus": 0.37182232622303596,
				"gap": 7.353753577844145
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "WFcHREc8",
			"type": "text",
			"x": 1838.2937570560862,
			"y": 1935.9084999049442,
			"width": 631.3992919921875,
			"height": 200,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 307509871,
			"version": 554,
			"versionNonce": 1690648417,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "z6-lHZUi_iAOgebaxfqLD",
					"type": "arrow"
				}
			],
			"updated": 1713301617182,
			"link": null,
			"locked": false,
			"text": "The representations (Not the encoding) will be saved\nafter pretraining in order to be transferred into assisting\nin the downstream task (Transfer Learning)\n\nIn cases where we have a very large amount of labeled data\nthe transfer learning in self-supervised models is slightly better\nthan supervised, whereas in models where data is scarce\nthe difference is drastically in favour of self-supervised",
			"rawText": "The representations (Not the encoding) will be saved\nafter pretraining in order to be transferred into assisting\nin the downstream task (Transfer Learning)\n\nIn cases where we have a very large amount of labeled data\nthe transfer learning in self-supervised models is slightly better\nthan supervised, whereas in models where data is scarce\nthe difference is drastically in favour of self-supervised",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 193,
			"containerId": null,
			"originalText": "The representations (Not the encoding) will be saved\nafter pretraining in order to be transferred into assisting\nin the downstream task (Transfer Learning)\n\nIn cases where we have a very large amount of labeled data\nthe transfer learning in self-supervised models is slightly better\nthan supervised, whereas in models where data is scarce\nthe difference is drastically in favour of self-supervised",
			"lineHeight": 1.25
		},
		{
			"id": "6MilhXLt_wReH_-CGOkPe",
			"type": "arrow",
			"x": 1542.6210119135078,
			"y": 2603.317401924573,
			"width": 175.17271753153864,
			"height": 4.547473508864641e-13,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1411706127,
			"version": 377,
			"versionNonce": 912864961,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713304337165,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					175.17271753153864,
					4.547473508864641e-13
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "U6GXoC0n",
				"focus": 0.14427836695462543,
				"gap": 2.583864364021565
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "U6GXoC0n",
			"type": "text",
			"x": 1720.377593809068,
			"y": 2517.745238620037,
			"width": 716.499267578125,
			"height": 200,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1301212833,
			"version": 454,
			"versionNonce": 1953937057,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "6MilhXLt_wReH_-CGOkPe",
					"type": "arrow"
				}
			],
			"updated": 1713304337165,
			"link": null,
			"locked": false,
			"text": "needs a lot of negatives samples in one batch to learn good\nrepresentation, because the larger the batch the more the model learns\nwhere not to put the representation we have gotten\ntherefore, training with multiple GPUs or TPUs is necessary\n\nTHe alternative would be storing representations in a\nmemory bank and use them as negatives\nin future iterations",
			"rawText": "needs a lot of negatives samples in one batch to learn good\nrepresentation, because the larger the batch the more the model learns\nwhere not to put the representation we have gotten\ntherefore, training with multiple GPUs or TPUs is necessary\n\nTHe alternative would be storing representations in a\nmemory bank and use them as negatives\nin future iterations",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 193,
			"containerId": null,
			"originalText": "needs a lot of negatives samples in one batch to learn good\nrepresentation, because the larger the batch the more the model learns\nwhere not to put the representation we have gotten\ntherefore, training with multiple GPUs or TPUs is necessary\n\nTHe alternative would be storing representations in a\nmemory bank and use them as negatives\nin future iterations",
			"lineHeight": 1.25
		},
		{
			"id": "OWIj0PQP9gAG8PoEAxM0o",
			"type": "arrow",
			"x": 687.2520601047073,
			"y": 1714.872062654882,
			"width": 207.6480152562699,
			"height": 1.3396646145565683,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 51749473,
			"version": 40,
			"versionNonce": 1922712705,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322182,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-207.6480152562699,
					-1.3396646145565683
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "ntXJ0Ukw",
			"type": "text",
			"x": -200.92911964969414,
			"y": 1594.3299867023234,
			"width": 597.0193481445312,
			"height": 250,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 821367311,
			"version": 376,
			"versionNonce": 1316683791,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322182,
			"link": null,
			"locked": false,
			"text": "Augmentation of views\nwhich ones do we pick?\n\nThis is very task data and domain specific and you\nmight have to test and handcraft your own.\n\nfor example SimCLR optimized its augmentation on ImageNet\nperformance which lead to\nrandom cropping followed by resize back to the original size,\nrandom color distortions, and random Gaussian blur",
			"rawText": "Augmentation of views\nwhich ones do we pick?\n\nThis is very task data and domain specific and you\nmight have to test and handcraft your own.\n\nfor example SimCLR optimized its augmentation on ImageNet\nperformance which lead to\nrandom cropping followed by resize back to the original size,\nrandom color distortions, and random Gaussian blur",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 243,
			"containerId": null,
			"originalText": "Augmentation of views\nwhich ones do we pick?\n\nThis is very task data and domain specific and you\nmight have to test and handcraft your own.\n\nfor example SimCLR optimized its augmentation on ImageNet\nperformance which lead to\nrandom cropping followed by resize back to the original size,\nrandom color distortions, and random Gaussian blur",
			"lineHeight": 1.25
		},
		{
			"id": "RnLvF4Bs2S5gNMQD41lSL",
			"type": "image",
			"x": -745.0600314098078,
			"y": 1577.0834887262552,
			"width": 498.5966346359552,
			"height": 292.1776278966697,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 933398895,
			"version": 93,
			"versionNonce": 565316385,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "jn02jzx9yuD6StFJHHwPV",
					"type": "arrow"
				}
			],
			"updated": 1713304428023,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "da8efcd14d7a38006291a91bf23878536a82b4fb",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "oHiOoCON",
			"type": "text",
			"x": -301.9148677197138,
			"y": 1700.2539171737878,
			"width": 118.47987365722656,
			"height": 25,
			"angle": 1.5736580600013008,
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
			"seed": 1542065935,
			"version": 188,
			"versionNonce": 1784555055,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301322182,
			"link": null,
			"locked": false,
			"text": "Performance",
			"rawText": "Performance",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Performance",
			"lineHeight": 1.25
		},
		{
			"id": "rN4n2ez5",
			"type": "text",
			"x": -605.8649690009327,
			"y": 1558.3743414984283,
			"width": 235.35972595214844,
			"height": 25,
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
			"seed": 851205871,
			"version": 45,
			"versionNonce": 1408336399,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301323394,
			"link": null,
			"locked": false,
			"text": "Based off of ImageNet",
			"rawText": "Based off of ImageNet",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Based off of ImageNet",
			"lineHeight": 1.25
		},
		{
			"id": "icq_X_51me9I3BT8mxpTF",
			"type": "arrow",
			"x": 917.9991074325012,
			"y": 1141.240783610021,
			"width": 774.9182528008948,
			"height": 867.0651914792625,
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
			"roundness": {
				"type": 2
			},
			"seed": 437126881,
			"version": 530,
			"versionNonce": 411328065,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713303918808,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					166.81552075386662,
					-89.09465312990596
				],
				[
					140.27668790666053,
					-786.6868308278939
				],
				[
					774.9182528008948,
					-867.0651914792625
				]
			],
			"lastCommittedPoint": [
				519.4028714381757,
				-845.4513892752788
			],
			"startBinding": {
				"elementId": "FySJECv8",
				"focus": 0.46824515110625387,
				"gap": 25.76733492215044
			},
			"endBinding": {
				"elementId": "IqqC5UHX",
				"focus": 0.9412453368204572,
				"gap": 18.295013525679337
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "S1Uxa7AK",
			"type": "text",
			"x": 2011.2911596909805,
			"y": 208.11914387104287,
			"width": 266.67315673828125,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 326646671,
			"version": 66,
			"versionNonce": 2023777665,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713302204396,
			"link": null,
			"locked": false,
			"text": "Image-Text Models",
			"rawText": "Image-Text Models",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Image-Text Models",
			"lineHeight": 1.25
		},
		{
			"id": "IqqC5UHX",
			"type": "text",
			"x": 1711.2123737590755,
			"y": 264.32020172410375,
			"width": 841.69921875,
			"height": 150,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 957817569,
			"version": 651,
			"versionNonce": 804999777,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "icq_X_51me9I3BT8mxpTF",
					"type": "arrow"
				},
				{
					"id": "KD4OeXqtTwlOcP7ODGhK1",
					"type": "arrow"
				}
			],
			"updated": 1713303918807,
			"link": null,
			"locked": false,
			"text": "As we have mentioned before, self-supervised representation of\nthe data allows us to mix and match different modalities of data\nwith each other, a good example of this is matching an image to a caption/word\nObviously we have different encoders for different modalities\nThis is great as it allows to attach naunced text to an image to get a better\n    understanding of the entire image not just one object in it (and thus generalize)",
			"rawText": "As we have mentioned before, self-supervised representation of\nthe data allows us to mix and match different modalities of data\nwith each other, a good example of this is matching an image to a caption/word\nObviously we have different encoders for different modalities\nThis is great as it allows to attach naunced text to an image to get a better\n    understanding of the entire image not just one object in it (and thus generalize)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 143,
			"containerId": null,
			"originalText": "As we have mentioned before, self-supervised representation of\nthe data allows us to mix and match different modalities of data\nwith each other, a good example of this is matching an image to a caption/word\nObviously we have different encoders for different modalities\nThis is great as it allows to attach naunced text to an image to get a better\n    understanding of the entire image not just one object in it (and thus generalize)",
			"lineHeight": 1.25
		},
		{
			"id": "Lm50ndJjlWdUVGOpM_Nku",
			"type": "image",
			"x": 1352.4200363947405,
			"y": 475.1392968259271,
			"width": 689.162272892343,
			"height": 402.2280435497448,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 7730561,
			"version": 158,
			"versionNonce": 496853057,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301891433,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b6dc79d7ad78e828f2bb3ba46192eef566916c7e",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "DJN1WoW3",
			"type": "text",
			"x": 1976.974760040705,
			"y": 420.2415289119345,
			"width": 318.5606689453125,
			"height": 20,
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
			"seed": 1763458817,
			"version": 347,
			"versionNonce": 13316257,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713303907611,
			"link": null,
			"locked": false,
			"text": "(Both encoded into the same dimensions)",
			"rawText": "(Both encoded into the same dimensions)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "(Both encoded into the same dimensions)",
			"lineHeight": 1.25
		},
		{
			"id": "opi2FBPRMfq3VWOmfTOpu",
			"type": "arrow",
			"x": 2013.1227226447156,
			"y": 718.6635511267583,
			"width": 162.34877022257865,
			"height": 2.549980684124307,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1764429583,
			"version": 77,
			"versionNonce": 1869698081,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713302159331,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					162.34877022257865,
					2.549980684124307
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "h7q5AWdZkJ6Mh8UkdeSeW",
				"focus": 0.06676499480472842,
				"gap": 8.059096951742958
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "sbXkmyVy",
			"type": "text",
			"x": 1514.365525995417,
			"y": 453.5155406619586,
			"width": 303.9196472167969,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1854653615,
			"version": 68,
			"versionNonce": 2055085441,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713301890034,
			"link": null,
			"locked": false,
			"text": "Contrastive Pre-training Stage",
			"rawText": "Contrastive Pre-training Stage",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Contrastive Pre-training Stage",
			"lineHeight": 1.25
		},
		{
			"id": "h7q5AWdZkJ6Mh8UkdeSeW",
			"type": "image",
			"x": 2183.5305898190372,
			"y": 520.9067911280654,
			"width": 638,
			"height": 441,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"MQfnzV1jKqNBBZ9ISUfrT"
			],
			"frameId": null,
			"roundness": null,
			"seed": 631493615,
			"version": 46,
			"versionNonce": 1255981039,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "opi2FBPRMfq3VWOmfTOpu",
					"type": "arrow"
				},
				{
					"id": "G9YdpB8uXjvNk-VOfmEom",
					"type": "arrow"
				}
			],
			"updated": 1713302623991,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0a1200e495bea4dc2b2829782f47b103247b4a02",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "KypEZk4f3HlzHRweO_-QA",
			"type": "rectangle",
			"x": 2199.3655246745566,
			"y": 722.2882735063414,
			"width": 285.4121559243081,
			"height": 40.968252046551356,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"MQfnzV1jKqNBBZ9ISUfrT"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 551803745,
			"version": 101,
			"versionNonce": 141146671,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713302158968,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 155,
			"versionNonce": 1092993153,
			"isDeleted": false,
			"id": "HH6mysEN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2279.114617935215,
			"y": 470.13375132726543,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 420.6395263671875,
			"height": 25,
			"seed": 2121288897,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713302552723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Create dataset classifier from label text",
			"rawText": "Create dataset classifier from label text",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Create dataset classifier from label text",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"id": "YoBtOjfs",
			"type": "text",
			"x": 2591.385527092141,
			"y": 963.5880941850728,
			"width": 236.21971130371094,
			"height": 25,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 922171521,
			"version": 91,
			"versionNonce": 718852399,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ocUgSQIM6uawh9vMTwXNC",
					"type": "arrow"
				}
			],
			"updated": 1713302929664,
			"link": null,
			"locked": false,
			"text": "Zero-shot classification",
			"rawText": "Zero-shot classification",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Zero-shot classification",
			"lineHeight": 1.25
		},
		{
			"id": "G9YdpB8uXjvNk-VOfmEom",
			"type": "arrow",
			"x": 2852.389033396358,
			"y": 977.9365885156923,
			"width": 131.93541197877903,
			"height": 1.0726456258437338,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1322500207,
			"version": 84,
			"versionNonce": 54120911,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713302623991,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					131.93541197877903,
					-1.0726456258437338
				]
			],
			"lastCommittedPoint": [
				131.93541197877903,
				-1.0726456258437338
			],
			"startBinding": {
				"elementId": "h7q5AWdZkJ6Mh8UkdeSeW",
				"focus": 1.0729769327182603,
				"gap": 30.85844357732094
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "3YSc8HGj",
			"type": "text",
			"x": 2917.3804002306642,
			"y": 924.3043072235057,
			"width": 511.4593505859375,
			"height": 225,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 944951343,
			"version": 427,
			"versionNonce": 148839265,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "IoAABl5xoSkIRnY5ihl6K",
					"type": "arrow"
				}
			],
			"updated": 1713302921947,
			"link": null,
			"locked": false,
			"text": "Zero-shot classification term comes\nfrom N-shot classification.\n\nN-shot classification means that you need\nN training examples in order for your model\nto perform on a particular new domain\nThe smaller the number N, the more robust a model\nis because it requires little to no extra supervised\ndataset in order to perform the downstream task",
			"rawText": "Zero-shot classification term comes\nfrom N-shot classification.\n\nN-shot classification means that you need\nN training examples in order for your model\nto perform on a particular new domain\nThe smaller the number N, the more robust a model\nis because it requires little to no extra supervised\ndataset in order to perform the downstream task",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 218,
			"containerId": null,
			"originalText": "Zero-shot classification term comes\nfrom N-shot classification.\n\nN-shot classification means that you need\nN training examples in order for your model\nto perform on a particular new domain\nThe smaller the number N, the more robust a model\nis because it requires little to no extra supervised\ndataset in order to perform the downstream task",
			"lineHeight": 1.25
		},
		{
			"id": "KD4OeXqtTwlOcP7ODGhK1",
			"type": "arrow",
			"x": 2583.734174547936,
			"y": 317.72347106312344,
			"width": 67.25994873046875,
			"height": 0.812732313831134,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1498644129,
			"version": 64,
			"versionNonce": 1203826209,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713303918809,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					67.25994873046875,
					0.812732313831134
				]
			],
			"lastCommittedPoint": [
				84,
				1
			],
			"startBinding": {
				"elementId": "IqqC5UHX",
				"focus": -0.3378208517739191,
				"gap": 30.822582038860673
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "WozFX0VN",
			"type": "text",
			"x": 2626.769857226159,
			"y": 289.5362033769546,
			"width": 234.4485321044922,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1933174543,
			"version": 111,
			"versionNonce": 577098561,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713302912822,
			"link": null,
			"locked": false,
			"text": "This allows things like\nimage Search\nimage generation\nzero-shot image classification",
			"rawText": "This allows things like\nimage Search\nimage generation\nzero-shot image classification",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "This allows things like\nimage Search\nimage generation\nzero-shot image classification",
			"lineHeight": 1.25
		},
		{
			"id": "IoAABl5xoSkIRnY5ihl6K",
			"type": "arrow",
			"x": 3167.994123278405,
			"y": 1157.5362033769543,
			"width": 268,
			"height": 51,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1055061391,
			"version": 172,
			"versionNonce": 1712309601,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713302984059,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-23,
					49
				],
				[
					-268,
					51
				]
			],
			"lastCommittedPoint": [
				-337,
				84
			],
			"startBinding": {
				"elementId": "3YSc8HGj",
				"focus": -0.16709283602342462,
				"gap": 8.231896153448588
			},
			"endBinding": {
				"elementId": "xltrGmLX",
				"focus": 0.05271020211472899,
				"gap": 8.95159912109375
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "ocUgSQIM6uawh9vMTwXNC",
			"type": "arrow",
			"x": 2695.994123278405,
			"y": 1003.5362033769544,
			"width": 0,
			"height": 112.99999999999989,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1158689249,
			"version": 74,
			"versionNonce": 885125121,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713302931336,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					112.99999999999989
				]
			],
			"lastCommittedPoint": [
				7,
				128.9999999999999
			],
			"startBinding": {
				"elementId": "YoBtOjfs",
				"focus": 0.11431103180235977,
				"gap": 14.9481091918816
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "xltrGmLX",
			"type": "text",
			"x": 2486.9457223994987,
			"y": 1157.5362033769543,
			"width": 404.0968017578125,
			"height": 100,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 837175265,
			"version": 265,
			"versionNonce": 2123379087,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "IoAABl5xoSkIRnY5ihl6K",
					"type": "arrow"
				}
			],
			"updated": 1713302981544,
			"link": null,
			"locked": false,
			"text": "Because our model already learnt the semantics\nof a picture of a dog AND the semantics of the\nword dog, it does not need an extra labelled data\nof dogs in order to be able to associate the\nword dog to the image of a dog",
			"rawText": "Because our model already learnt the semantics\nof a picture of a dog AND the semantics of the\nword dog, it does not need an extra labelled data\nof dogs in order to be able to associate the\nword dog to the image of a dog",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 94,
			"containerId": null,
			"originalText": "Because our model already learnt the semantics\nof a picture of a dog AND the semantics of the\nword dog, it does not need an extra labelled data\nof dogs in order to be able to associate the\nword dog to the image of a dog",
			"lineHeight": 1.25
		},
		{
			"id": "XKAfjjF11bnj-C_Rmt-_f",
			"type": "line",
			"x": 1038.4730218308325,
			"y": 2882.3009304799175,
			"width": 212.72727272727275,
			"height": 346.8686868686873,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1904596225,
			"version": 472,
			"versionNonce": 789412065,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713303083081,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					154.54545454545428,
					3.6363636363644076
				],
				[
					112.72727272727262,
					281.81818181818255
				],
				[
					185.45454545454527,
					281.81818181818244
				],
				[
					81.81818181818176,
					346.8686868686873
				],
				[
					-27.27272727272748,
					283.6363636363635
				],
				[
					45.454545454545595,
					276.36363636363694
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				1.8181818181817562,
				5.454545454545496
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "S55F5emS",
			"type": "text",
			"x": 841.9661455917158,
			"y": 3237.413855566527,
			"width": 557.6393432617188,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 213672431,
			"version": 167,
			"versionNonce": 1117874511,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713303119114,
			"link": null,
			"locked": false,
			"text": "This is not the only solution to Representation Collapse",
			"rawText": "This is not the only solution to Representation Collapse",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "This is not the only solution to Representation Collapse",
			"lineHeight": 1.25
		},
		{
			"id": "MZ2RBCh7",
			"type": "text",
			"x": 952.2746918699272,
			"y": 3271.580522233194,
			"width": 328.13336181640625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1833214351,
			"version": 39,
			"versionNonce": 929641985,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713303150598,
			"link": null,
			"locked": false,
			"text": "Non-contrastive learning",
			"rawText": "Non-contrastive learning",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Non-contrastive learning",
			"lineHeight": 1.25
		},
		{
			"id": "N5sdQr4mGOR86AUU7gFnW",
			"type": "image",
			"x": 790.4686319161683,
			"y": 3313.883746523624,
			"width": 654.6666666666665,
			"height": 231.4405286343612,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1719822785,
			"version": 86,
			"versionNonce": 1009246593,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713303227028,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "770d0d99622d8b3f35d5d8d1f9e74b1f064c4183",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ubHmK3nt",
			"type": "text",
			"x": 743.6286627586294,
			"y": 3538.4782053157205,
			"width": 773.619140625,
			"height": 175,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1149147393,
			"version": 483,
			"versionNonce": 254447183,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "16ZFAe6T2ZOUvqYFxyg_i",
					"type": "arrow"
				}
			],
			"updated": 1713305672240,
			"link": null,
			"locked": false,
			"text": "Bootstrap your own latent (BYOL) uses the idea of predicting the\nrepresentations of a random initialized model to improve the\nrepresentations.\nThis on its own is not good, but we build upon this idea moving forward.\nBoth networks have the exact same architecture but different weights\nand the weight of the target network after each iteration is the exponential\nmoving average of the online network.",
			"rawText": "Bootstrap your own latent (BYOL) uses the idea of predicting the\nrepresentations of a random initialized model to improve the\nrepresentations.\nThis on its own is not good, but we build upon this idea moving forward.\nBoth networks have the exact same architecture but different weights\nand the weight of the target network after each iteration is the exponential\nmoving average of the online network.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 168,
			"containerId": null,
			"originalText": "Bootstrap your own latent (BYOL) uses the idea of predicting the\nrepresentations of a random initialized model to improve the\nrepresentations.\nThis on its own is not good, but we build upon this idea moving forward.\nBoth networks have the exact same architecture but different weights\nand the weight of the target network after each iteration is the exponential\nmoving average of the online network.",
			"lineHeight": 1.25
		},
		{
			"id": "m2ZbC_CkWk8ro643Jn09P",
			"type": "arrow",
			"x": 1608.406021475142,
			"y": 2254.296734911496,
			"width": 118.8360008212303,
			"height": 0,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1445465679,
			"version": 34,
			"versionNonce": 642236655,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713303394112,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					118.8360008212303,
					0
				]
			],
			"lastCommittedPoint": [
				118.8360008212303,
				0
			],
			"startBinding": {
				"elementId": "lDECn21z",
				"focus": -0.5457740473524831,
				"gap": 18.65276622884039
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "20vANlVm",
			"type": "text",
			"x": 1700.568259710267,
			"y": 2240.255317640807,
			"width": 352.99957275390625,
			"height": 75,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1672581423,
			"version": 145,
			"versionNonce": 300667970,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713303430201,
			"link": "[[Regularization]]",
			"locked": false,
			"text": "This idea is very similar to\nthe auxiliary domain critic described\nhere",
			"rawText": "This idea is very similar to\nthe auxiliary domain critic described\nhere",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "This idea is very similar to\nthe auxiliary domain critic described\nhere",
			"lineHeight": 1.25
		},
		{
			"id": "jn02jzx9yuD6StFJHHwPV",
			"type": "arrow",
			"x": -749.3312187572915,
			"y": 1683.397793974515,
			"width": 158.33109716981448,
			"height": 1.6100523606457955,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1537108495,
			"version": 1579,
			"versionNonce": 54241359,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713304690016,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-158.33109716981448,
					1.6100523606457955
				]
			],
			"lastCommittedPoint": [
				-141.80036842259017,
				-2.41705173447599
			],
			"startBinding": {
				"elementId": "RnLvF4Bs2S5gNMQD41lSL",
				"focus": 0.2849678265922376,
				"gap": 4.271187347483647
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "gDGlQmRA",
			"type": "text",
			"x": -1503.4827448157862,
			"y": 1669.2984624903033,
			"width": 702.619140625,
			"height": 525,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1229847375,
			"version": 798,
			"versionNonce": 239181921,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713304826170,
			"link": null,
			"locked": false,
			"text": "Why are crops and color distortions important?\n\nFor starters, Cropping images is intuitively very good\nin making the model to associate different parts of an object\nto belong to the same object because it associates different\nfeatures of objects to be subparts\n\n\n\n\n\n\n\n\n\nColoration is important with cropping images because if you take two\ncropped versions of the same dog, the RGB values in each pixel will be\nsomewhat similar or have a similar curve.\nNeural nets may exploit this shortcut to solve the predictive task.\nTherefore, it is critical to compose cropping with color distortion\nin order to learn generalizable features.",
			"rawText": "Why are crops and color distortions important?\n\nFor starters, Cropping images is intuitively very good\nin making the model to associate different parts of an object\nto belong to the same object because it associates different\nfeatures of objects to be subparts\n\n\n\n\n\n\n\n\n\nColoration is important with cropping images because if you take two\ncropped versions of the same dog, the RGB values in each pixel will be\nsomewhat similar or have a similar curve.\nNeural nets may exploit this shortcut to solve the predictive task.\nTherefore, it is critical to compose cropping with color distortion\nin order to learn generalizable features.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 518,
			"containerId": null,
			"originalText": "Why are crops and color distortions important?\n\nFor starters, Cropping images is intuitively very good\nin making the model to associate different parts of an object\nto belong to the same object because it associates different\nfeatures of objects to be subparts\n\n\n\n\n\n\n\n\n\nColoration is important with cropping images because if you take two\ncropped versions of the same dog, the RGB values in each pixel will be\nsomewhat similar or have a similar curve.\nNeural nets may exploit this shortcut to solve the predictive task.\nTherefore, it is critical to compose cropping with color distortion\nin order to learn generalizable features.",
			"lineHeight": 1.25
		},
		{
			"id": "IWyiX7DXZ3hjGK5cFL2Wc",
			"type": "image",
			"x": -1315.2822319194145,
			"y": 1841.5343659022158,
			"width": 352,
			"height": 176,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2119057423,
			"version": 103,
			"versionNonce": 1964284335,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713304691794,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f0878ffe6dabcb5f51513bca659d37c805f26f90",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "1g4uMZe8e-6p_jhJKiwi-",
			"type": "image",
			"x": -1345.8453353180046,
			"y": 2211.2880569558274,
			"width": 403,
			"height": 202,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2129453185,
			"version": 43,
			"versionNonce": 2126197071,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713304717648,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c60de26b76fe746163a5031ea329698fce3eb6fd",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "XEn__Lfwi7peidcWLkeqO",
			"type": "arrow",
			"x": 2089.1043784986778,
			"y": 2751.751388369031,
			"width": 647.5,
			"height": 523.75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 122403873,
			"version": 234,
			"versionNonce": 1958201871,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713305092222,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-86.25000000000023,
					422.5
				],
				[
					-647.5,
					523.75
				]
			],
			"lastCommittedPoint": [
				-647.5,
				523.75
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "APXEePKH",
			"type": "text",
			"x": 2103.1646201978965,
			"y": 2843.001388369031,
			"width": 364.3795166015625,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 41005103,
			"version": 255,
			"versionNonce": 1997140559,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713305138549,
			"link": null,
			"locked": false,
			"text": "This is quite a bit requirement as it\nnot everyone has a lot of resources\nto run such large batches, perhaps\nthere are better ways?",
			"rawText": "This is quite a bit requirement as it\nnot everyone has a lot of resources\nto run such large batches, perhaps\nthere are better ways?",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "This is quite a bit requirement as it\nnot everyone has a lot of resources\nto run such large batches, perhaps\nthere are better ways?",
			"lineHeight": 1.25
		},
		{
			"id": "aSi4GIqx39Vnm1Tf_46tu",
			"type": "arrow",
			"x": 913.016820095763,
			"y": 3348.7288523491893,
			"width": 176.10417930464791,
			"height": 40.95446030340645,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1709107855,
			"version": 100,
			"versionNonce": 1426233007,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713305234075,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-111.39613202526562,
					-40.95446030340645
				],
				[
					-176.10417930464791,
					-25.347960074703224
				]
			],
			"lastCommittedPoint": [
				-189.20960660173796,
				-22.115408563839537
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "I16agvne",
				"focus": 0.3080639855489701,
				"gap": 14.410668882369237
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "I16agvne",
			"type": "text",
			"x": 626.8217503511287,
			"y": 3308.6789460154423,
			"width": 95.68022155761719,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 524254145,
			"version": 71,
			"versionNonce": 755204239,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "aSi4GIqx39Vnm1Tf_46tu",
					"type": "arrow"
				}
			],
			"updated": 1713305234075,
			"link": null,
			"locked": false,
			"text": "Only train\nthis network",
			"rawText": "Only train\nthis network",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Only train\nthis network",
			"lineHeight": 1.25
		},
		{
			"id": "16ZFAe6T2ZOUvqYFxyg_i",
			"type": "arrow",
			"x": 1037.9814578159978,
			"y": 3525.5019683823657,
			"width": 299.3843212426184,
			"height": 35.13110775169844,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1518466799,
			"version": 550,
			"versionNonce": 42069103,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1713305672242,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-178.77702463736773,
					-3.812607951786049
				],
				[
					-299.3843212426184,
					-35.13110775169844
				]
			],
			"lastCommittedPoint": [
				-181.7840998466072,
				-25.319928192920088
			],
			"startBinding": {
				"elementId": "ubHmK3nt",
				"focus": 1.0287770620633763,
				"gap": 12.976236933354812
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "uTC3cDoz",
			"type": "text",
			"x": 530.3830615412783,
			"y": 3430.1819477194654,
			"width": 214.28848266601562,
			"height": 100,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1582241441,
			"version": 153,
			"versionNonce": 1568013153,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713305620036,
			"link": null,
			"locked": false,
			"text": "Randomly initialize\nthis network and freeze\nits weights which will result\nin a random projection\nof the input image",
			"rawText": "Randomly initialize\nthis network and freeze\nits weights which will result\nin a random projection\nof the input image",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 94,
			"containerId": null,
			"originalText": "Randomly initialize\nthis network and freeze\nits weights which will result\nin a random projection\nof the input image",
			"lineHeight": 1.25
		},
		{
			"id": "EQsViY4mqcWbu_qTBxnf0",
			"type": "image",
			"x": 1528.5614001294325,
			"y": 3329.7840545819554,
			"width": 830,
			"height": 350,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1410608609,
			"version": 72,
			"versionNonce": 922996623,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713305840159,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d14b71bafd79ec96f2c400d3e55432a299246434",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Q3I5gFZS",
			"type": "text",
			"x": 730.1731907664303,
			"y": 3722.938381340294,
			"width": 793.6975708007812,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 188408705,
			"version": 246,
			"versionNonce": 628019361,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713306029582,
			"link": null,
			"locked": false,
			"text": "This model does not guarantee non-collapse but instead making it extremely implausible\nand removed the need for negative samples and \"important\" combinations of different augmentations",
			"rawText": "This model does not guarantee non-collapse but instead making it extremely implausible\nand removed the need for negative samples and \"important\" combinations of different augmentations",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "This model does not guarantee non-collapse but instead making it extremely implausible\nand removed the need for negative samples and \"important\" combinations of different augmentations",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 756,
			"versionNonce": 2055196143,
			"isDeleted": false,
			"id": "IQTldlL2XX28KHaiU7VBw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 481.82577515512185,
			"y": 3500.37771973297,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 233.61024703641078,
			"height": 179.94958923870695,
			"seed": 1237645345,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1713306086241,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-163.1957904502133,
					-35.212667680232904
				],
				[
					-167.56924648968334,
					32.07499967144739
				],
				[
					-233.61024703641078,
					-74.5220002673461
				],
				[
					-155.66562969231632,
					-147.87458956725956
				],
				[
					-160.60012103869738,
					-85.26456608530962
				],
				[
					-6.056561960203162,
					-103.08876703649545
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "GLa3SnDQ",
			"type": "text",
			"x": -306.60845586244113,
			"y": 3280.429183525321,
			"width": 235.98495483398438,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 551310433,
			"version": 114,
			"versionNonce": 1642638433,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713306259371,
			"link": null,
			"locked": false,
			"text": "DinoV2 and iBOT",
			"rawText": "DinoV2 and iBOT",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "DinoV2 and iBOT",
			"lineHeight": 1.25
		},
		{
			"id": "g7HL6bSM",
			"type": "text",
			"x": -515.1724755466682,
			"y": 3328.1428207743766,
			"width": 692.2392578125,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1634205583,
			"version": 176,
			"versionNonce": 214477345,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713306130828,
			"link": null,
			"locked": false,
			"text": "Dinov2 takes the idea of BYOL and builds upon it using transformers\nwhich results in something great that i wont get into now :]",
			"rawText": "Dinov2 takes the idea of BYOL and builds upon it using transformers\nwhich results in something great that i wont get into now :]",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "Dinov2 takes the idea of BYOL and builds upon it using transformers\nwhich results in something great that i wont get into now :]",
			"lineHeight": 1.25
		},
		{
			"id": "AseJTGQ4rhE4bmRZrIHTh",
			"type": "image",
			"x": -502.03314406306936,
			"y": 3408.005909834697,
			"width": 652.2664025817817,
			"height": 207.05938858936054,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 228575265,
			"version": 161,
			"versionNonce": 1908520719,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1713306267878,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "56c1246d3a64f87f221b7480740f9e27e43e7f39",
			"scale": [
				1,
				1
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#868e96",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "triangle",
		"scrollX": 2391.4251895677944,
		"scrollY": 1575.902280509204,
		"zoom": {
			"value": 0.2111655996423102
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