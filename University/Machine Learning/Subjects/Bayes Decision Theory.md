---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Bayes Decision Theory ^yyuc5zB4

What is bayes decision theory? ^KcWuzgqt

Bayes decision theory is a theoretical framework
for building a model under certain favorable assumptions
yielding an optimal classifier and helps us understand
certain features about our data ^O9Qk4AV6

What do we learn about our data? ^OsJX5csy

Properties of out Gaussian Distribution
prior probabilities of classes
maximum classification accuracy ^i0U0LoDK

%%***>>>text element-link:[[Gaussian Distribution]]<<<***%%Whats a Gaussian distribution? ^QjVaXDs3

Notations ^F8YCTnSi

w1 , w2 ... wn   ^0b5bMg6A

   Classes of our data ^hlV1d5Q1

X €R ^2o8CSe5K

d ^FlYxV4QP

Vector of features ^O4zv0ZCo

P(wj) ^0MKEu11k

Probability of being class j ^GOjZTo4m

p(x | wj) ^iIDBHL2a

density function of measurements for each class ^eldX1Pts

- Prior ^515i6fFY

p(x) ^MJgGYaTE

density function of measurements (marginalized) ^fxdN2evu

P(wj | x) ^Up3FRUwt

Probability of being of a certain class after observing x ^WwwkbpSX

- Posterior ^ifw9KMgi

%%***>>>text element-link:[[Probability density]]<<<***%%What is a density function? ^xShJ0dfq

Using Bayes theorem ^I1QXr8EX

We can get to our objective (The posterior) using information
that we know! ^iNrwduVf

Logically Since P is the probability of predicting a certain class given information
we have read, then optimizing our objective to predict the class with the highest
probability will give us the most "probable" class and thus an optimal decision! ^3OXJuDOm

Want more detail about
bayes theorem? ^Ibzlhyqt

doesnt depend on j
and thus can be eliminated
to maximize the value ^afEhWAW1

Applying the log to both 
sides will keep the same argmax
Convex function ^ku62Iwqo

Log rules ^DbdHD5mA

Now lets apply this to a multivariate Gaussian distribution ^NaaxVKmm

Notice that this is just the normal gaussian
distribution applied to d dimensions
such that the covariance matrix is just
the matrix of the variances in each direction ^xD6AflA9

Using our knowledge from Linear algebra and computer graphics
 we know that the
diagonal scales our distribution in each dimension
and that the other values shear our distribution ^bTcM1qPZ

+ ^cxoA6trN

-1 ^JNA3o3Hd

-1 ^zXA1o5zf

Assuming that the covariance is the same between both classes
i.e does not depend on the class! ^TUgPas3u

This leads us to a linear decision boundary that seperates both classes
The orientation is decided by their mean and covariance and
it shifts close to one of the two classes depending on the prior probabilities!
This is because Bayes theorem insists on us using our current information
and the PRIOR information to update our decision boundary ^C2SUaJGN

w 1 ^FoQI3LJY

w 2 ^zjJFvD50

w 1 ^h9qNt2Z0

w 2 ^RBpaZvFo

If w2 is more common in the wild than w1
aka its prior probability is higher! ^JR6Z3zaI

What if we relax our assumption that they have the same
shape aka the same covariance? ^hnfxWQlX

Well then the classifier wont be linear anymore and instead
it will be a degenerate form of higher order (quadratic, hyperbolic etc...) ^fnZC7kqu

What if our data is non-numerical? ^7JuhJCdl

Lets take an example of Spam email ^IWIa5hi9

We can store all suspicious words that are marked as spam somewhere.
Our input X will be encoding whether each word we have stores at index i
has occurred or not (1 or 0)

Qij represents the probability of the word in occurring in class j ^J2cQsfTt

Compositing this from a Bernoulli distribution over all words ^XCKSEeVZ

xi times
its probability
in class j ^z8PvYBSb

the exact
opposite ^xTYsOdme

samples are
i.i.d ^m1mLs5oK

This is rewritten in this way to
allow us to simplify
it yeilds the same value but
is easier to simplify than log
of sum ^abJPqkk0

* ^Kh3hlY3o

Logarithm rules ^dTsI3WRF

Linear classifier! ^n4PyBofU

What about cases where we want
to evaluate the minimum cost
for our action, not necessarily
the "correct" action? ^nuocvixd

Let ak be an action with a specified cost
lambda is a function that evaluates cost, the expected cost of action ak 
given our information is:
 ^PUtKPQeU

cost of this action
given the truth is
of class wj ^f6kTDLn3

probability of class
wj occurring given
our evidence x ^jFTY7Kcy

cost of our action ak
given our evidence x ^SznVQfLW

Therefore the action ak that we should take is the action with the
lowest value given by lambda and our evidence x! ^NqbnpQgU

it is also important to determine what is the
expected error of the classifier
(e.g. to determine whether the classifier
is good enough for practical use) ^DruDDMSS

Bayes Error rate ^KGG7is4k

Our classifier's error over predicting datapoint x is usually evaluated as  ^8KXqtZZm

which if you recall we only decide w2 if it has a bigger posterior than w1 and vice verse
meaning ^4MiwYKGJ

To evaluate the total error over all values of x we need to use our
pdf of x that measures the probability distribution at each point in x!
as we know from pdfs this is not a SUM since its continuous values, it is
instead an integral.
and obviously we multiply each probability of x with its own error ^rcFxcZhg

due to the minimum inside the integral this is hard to solve analytically
instead we can:
 ^OcUzYnfr

Upper bound it          or      evaluate it Empirically  ^yXCv3yuv

a very basic bound dictating that only works in binary classification
relying on the assumption that the probability of another class
is 1 -  the first, and the minimum of both cant be above 0.5 ^J2YZO4UR

This doesnt help much as it says that the classifier is correct at
least 50% of the time, which is shit... and it also doesnt depend on our
distributions.. so its very general ^IKlyPMFB

This is because ^ItspGkj9

According to bayes theorem ^6uKhU7bF

This tells us that the classifier is accurate when one class
is highly dominant over the other! ^uRJ0p5DM

Whys it hard?
 ^MzcWvPcD

Why is the sky blue? 
why do you ask so many questions?
why are you adopted?
the world will never know!

JK the last one is obvious

anyway a pdf from its definition is infinitely
continuous meaning you can go to very very small values
infinitely between each 2 values which is the mean reason we
use areas instead of sums.

a minimum function on the other hand has discontinuities and is
not not something you can calculate on continuous values with
infinitely small differences ^pfKQwX8d

We can also upper bound our error with the harmonic mean of the class posteriors! ^cQG28fLK

The harmonic mean is the lowest of the three pythagorean means followed up
by the geometric and the arithmetic, it represents an average rate of sorts
and is calculated by the inverse of numbers divided by their count ^3rfFB1pg

This can be easily proven given two cases of which the first posterior
is minimal and then the other case of the other posterior is minimal
the harmonic mean can be expressed as the posterior itself plus a bigger
value incoming from the bigger posterior in each case and thus it upper bounds it! ^QwKhRXpm


# Embedded files
97b7886e0bd346aad2034adde5a733a8e81ebfd9: $$\arg\max_j{\frac{P(x|w_j) * P(w_j)}{p(x)}}$$
d512defb5e8df29f36af3718c66035b8b4d88b03: $$\arg\max_j{P(x|w_j) * P(w_j)}$$
51161663f2ea2e8de51aed4a4d82aa7ecc9480cc: $$\arg\max_j{\log({P(x|w_j) * P(w_j)})}$$
2e564e9e7c093cfa1ba06fdae290d4a14b6382ea: $$\arg\max_j{\log(P(x|w_j)) + \log(P(w_j))}$$
ed2e6505952b97c93f376535861ad1d9cf2c80f5: $$\begin{bmatrix}
\sigma_1\sigma_1 & \sigma_1\sigma_2 \\
\sigma_2\sigma_1 & \sigma_2\sigma_2 \\
\end{bmatrix}$$
d29451bfb99410bf5cdb56f615ce684b53c084cc: $$\log p(x|w_j) = \log$$
83d5835f35bd524c66e47a21b22234c9f3f1d23e: $$\arg\max_j [ $$
c9ade5da33ab114cb901ccf07ca771d0ff08afb7: $$+ \log P(w_j) ]$$
e4b1ee0f1f45122828a5c47d221c14af0fa42629: $$\arg\max_j [ x^T\sum mu_j - \frac{1}{2}\mu_j^T\sum \mu_j + logP(w_j) ]$$
eb12c15e924b4dfc299b706190ab2c0f6066f3cd: $$log P(x|w_j) = \sum_i log( q_{ij}^{x_i}*(1-q_{ij}^{(1-x_i)} ) )$$
d68824fc30e11a2cd7902de328c9cff1e7c2bfd6: $$\arg\max_j [ $$
9a3090f3bcd241da7b11eab2f5360d594ef7ad3e: $$+ log P(w_j) ]$$
f7e637fcffa09990960ab8289fd773de2a64ebdb: $$log(q_{ij}) = aij$$
b597c9e83331f58a52f75c4f92d14f04871dcea5: $$log(q_{ij}) = b_{ij}$$
e2265d7dc62e53ad037885dbd1bf99c09b1b8646: $$\arg\max_j [ x^T * a_j + (1-x)^T * b_j + log P(w_j) ]$$
28dc934e8541dc18af31941fcf630225ce9fd5e8: $$\arg\max_j [ x^T *(a_j - b_j) + 1^Tb_j + logP(w_j) ]$$
6d2e5224ab733dd6ae0f83bddd2d1f0d62c41693: [[Pasted Image 20231224190510_388.png]]
a899c87076f2811ac66f4c69f100b405e84f49bb: [[Pasted Image 20231224190844_412.png]]
1d7efc8a7e930513224f674f97146fa718e3e725: [[Pasted Image 20231225134035_459.png]]
a98459a5bd580d1d66615ec2bac038a2798b941b: [[Pasted Image 20231225135308_567.png]]
412108155d49eb014bac935f127ea9f430731c2a: [[Pasted Image 20231225135511_589.png]]
6a991878374532f72a779fb263d88d8ac0ed8217: [[Pasted Image 20231225135542_602.png]]
d8def8f2fc22b8ce4a33923948827a606c1fb95a: [[Pasted Image 20231225141832_762.png]]
8fd194e8a469ce626b346968217d411f496ef747: [[Pasted Image 20231225141937_779.png]]
e331ef28ed43e9c7d6f7b8e329f30f951d99b07d: [[Pasted Image 20231225143709_941.png]]
9cfd461052234b906c78e9d854e5869780b47a68: [[Pasted Image 20231225144710_016.png]]
512d9c0586df25cd1c43616fc6d0ad5d63ea18b3: [[Pasted Image 20231225145509_077.png]]
c85c6b1d40640bac98367b568fdb7221078673e9: [[Pasted Image 20231225145624_087.png]]
2c12da7a8d363ac86ece2272ae41c8523b090203: [[Pasted Image 20231225150039_171.png]]
9381915d791628f8c297907945fcd2f5a516f4e4: [[Pasted Image 20231225150054_174.png]]
11fa70d59a27a2af07cbaa55cd5e9b9e4a1b9347: [[Pasted Image 20231225150311_201.png]]
dd3826e0353b3edaa9d86094153720d823fe2d75: [[Pasted Image 20231225150626_227.png]]
d73d9f78a29a11c8442037f608ca38723f12d5e7: [[Pasted Image 20231225150641_236.png]]
7680b80df86f0a0ebc914350bc8c4804fdc43a58: [[Pasted Image 20231225150657_239.png]]
eb6c7d68cb703d2c09c29940477870e951458d2a: [[Pasted Image 20231225150742_250.png]]
b5adbee82d429a32d9810a2f43e8f29d11d6ce15: [[Pasted Image 20231225151954_490.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.3",
	"elements": [
		{
			"type": "ellipse",
			"version": 91,
			"versionNonce": 839021168,
			"isDeleted": false,
			"id": "6WAWhM8JNyXL8YlP1VF-H",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -211.9761269115603,
			"y": -433.1861932346808,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 383,
			"height": 155,
			"seed": 44271229,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "yyuc5zB4"
				}
			],
			"updated": 1703512433117,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 70,
			"versionNonce": 996682896,
			"isDeleted": false,
			"id": "yyuc5zB4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -122.36348542089354,
			"y": -390.4869687766382,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 203.95281982421875,
			"height": 70,
			"seed": 92455965,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Bayes Decision\nTheory",
			"rawText": "Bayes Decision Theory",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "6WAWhM8JNyXL8YlP1VF-H",
			"originalText": "Bayes Decision Theory",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 78,
			"versionNonce": 803906672,
			"isDeleted": false,
			"id": "KcWuzgqt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -153,
			"y": -211.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 302.2596435546875,
			"height": 25,
			"seed": 149210781,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "What is bayes decision theory?",
			"rawText": "What is bayes decision theory?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is bayes decision theory?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 294,
			"versionNonce": 349444752,
			"isDeleted": false,
			"id": "O9Qk4AV6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -222.5646716934085,
			"y": -184.69821369474877,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 446.96099853515625,
			"height": 80,
			"seed": 154416595,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VlYRdt55i7b_EXo3JyFZa",
					"type": "arrow"
				}
			],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Bayes decision theory is a theoretical framework\nfor building a model under certain favorable assumptions\nyielding an optimal classifier and helps us understand\ncertain features about our data",
			"rawText": "Bayes decision theory is a theoretical framework\nfor building a model under certain favorable assumptions\nyielding an optimal classifier and helps us understand\ncertain features about our data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bayes decision theory is a theoretical framework\nfor building a model under certain favorable assumptions\nyielding an optimal classifier and helps us understand\ncertain features about our data",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "line",
			"version": 327,
			"versionNonce": 1711052400,
			"isDeleted": false,
			"id": "A_ecHOzfetHfkxhZhD2ig",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 192.96685009863177,
			"y": -111.88646852286922,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 206.49692398663535,
			"height": 103.38086041978801,
			"seed": 1001431421,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					66.69480377744094,
					-7.407839347352109
				],
				[
					141.87774997033125,
					-103.38086041978801
				],
				[
					206.49692398663535,
					-76.1123620687593
				]
			]
		},
		{
			"type": "text",
			"version": 154,
			"versionNonce": 1989298320,
			"isDeleted": false,
			"id": "OsJX5csy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 352.18595673466876,
			"y": -179.4663330777889,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 248.99087524414062,
			"height": 17.830356652556997,
			"seed": 1954939901,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 14.264285322045598,
			"fontFamily": 1,
			"text": "What do we learn about our data?",
			"rawText": "What do we learn about our data?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What do we learn about our data?",
			"lineHeight": 1.25,
			"baseline": 12
		},
		{
			"type": "text",
			"version": 183,
			"versionNonce": 687884400,
			"isDeleted": false,
			"id": "i0U0LoDK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 363.1825586462988,
			"y": -159.33466990063727,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 221.07359313964844,
			"height": 41.88524523458172,
			"seed": 583137043,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 11.169398729221792,
			"fontFamily": 1,
			"text": "Properties of out Gaussian Distribution\nprior probabilities of classes\nmaximum classification accuracy",
			"rawText": "Properties of out Gaussian Distribution\nprior probabilities of classes\nmaximum classification accuracy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Properties of out Gaussian Distribution\nprior probabilities of classes\nmaximum classification accuracy",
			"lineHeight": 1.25,
			"baseline": 37
		},
		{
			"type": "line",
			"version": 158,
			"versionNonce": 475707024,
			"isDeleted": false,
			"id": "TpiJDq1pw_2wFw0gkj8LD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 599.1811653566615,
			"y": -153.11836612195057,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 107.57069983980682,
			"height": 23.859666505821764,
			"seed": 1591950429,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					55.80735555599006,
					2.0220056360865613
				],
				[
					107.57069983980682,
					-21.837660869735203
				]
			]
		},
		{
			"type": "text",
			"version": 194,
			"versionNonce": 1958591088,
			"isDeleted": false,
			"id": "QjVaXDs3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.34834345212427653,
			"x": 641.4981498629702,
			"y": -186.41828054059417,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 158.77041625976562,
			"height": 12.777173193819383,
			"seed": 966312605,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": "[[Gaussian Distribution]]",
			"locked": false,
			"fontSize": 10.221738555055506,
			"fontFamily": 1,
			"text": "Whats a Gaussian distribution?",
			"rawText": "Whats a Gaussian distribution?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Whats a Gaussian distribution?",
			"lineHeight": 1.25,
			"baseline": 8
		},
		{
			"type": "line",
			"version": 259,
			"versionNonce": 182805648,
			"isDeleted": false,
			"id": "DqN0IaRPGcK_XoomFuBA3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -234.2654088467142,
			"y": -136.78671972945432,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 517.6324519358974,
			"height": 146.8878974706313,
			"seed": 1064382621,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-107.06655451570157,
					-4.014995794338802
				],
				[
					-307.80265684745814,
					-146.8878974706313
				],
				[
					-517.6324519358974,
					-136.08969843124743
				]
			]
		},
		{
			"type": "text",
			"version": 192,
			"versionNonce": 201124976,
			"isDeleted": false,
			"id": "F8YCTnSi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -883.8613981284201,
			"y": -266.52731949840984,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 95.55989074707031,
			"height": 25,
			"seed": 1804501949,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Notations",
			"rawText": "Notations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Notations",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 184,
			"versionNonce": 1877627536,
			"isDeleted": false,
			"id": "0b5bMg6A",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -978.2453986219631,
			"y": -225.8372431030392,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 117.69622802734375,
			"height": 20,
			"seed": 123391677,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EK2d7lrnkut8qXanJwKFB",
					"type": "arrow"
				}
			],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "w1 , w2 ... wn  ",
			"rawText": "w1 , w2 ... wn  ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "w1 , w2 ... wn  ",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 170,
			"versionNonce": 411426416,
			"isDeleted": false,
			"id": "hlV1d5Q1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -823.0823011495095,
			"y": -225.66404750677148,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 188.96038818359375,
			"height": 20,
			"seed": 87893757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EK2d7lrnkut8qXanJwKFB",
					"type": "arrow"
				}
			],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "   Classes of our data",
			"rawText": "   Classes of our data",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "   Classes of our data",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 344,
			"versionNonce": 35750032,
			"isDeleted": false,
			"id": "EK2d7lrnkut8qXanJwKFB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -853.2439446851135,
			"y": -216.77567921210104,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 30.02479417632378,
			"height": 1.07336138994188,
			"seed": 889768125,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "0b5bMg6A",
				"focus": 0.3513851813321229,
				"gap": 7.305225909505793
			},
			"endBinding": {
				"elementId": "hlV1d5Q1",
				"focus": 0.2501255145811224,
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
					10.054373682797063,
					-0.984386620492046
				],
				[
					30.02479417632378,
					-1.07336138994188
				]
			]
		},
		{
			"type": "text",
			"version": 200,
			"versionNonce": 1260425328,
			"isDeleted": false,
			"id": "2o8CSe5K",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -949.9838555892039,
			"y": -193.70028488085197,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 40.03208923339844,
			"height": 20,
			"seed": 574249853,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "X €R",
			"rawText": "X €R",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "X €R",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 162,
			"versionNonce": 1631776400,
			"isDeleted": false,
			"id": "FlYxV4QP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -908.3074857615238,
			"y": -198.1143735994474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 4.694244384765625,
			"height": 10.327718436363313,
			"seed": 1604062579,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 8.26217474909065,
			"fontFamily": 1,
			"text": "d",
			"rawText": "d",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "d",
			"lineHeight": 1.25,
			"baseline": 7
		},
		{
			"type": "arrow",
			"version": 268,
			"versionNonce": 2073363056,
			"isDeleted": false,
			"id": "RWDhS5QeFZMIrb2qiFP-n",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -853.7668339988727,
			"y": -184.4708022431873,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 30.02479417632378,
			"height": 1.07336138994188,
			"seed": 771247197,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433117,
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
					10.054373682797063,
					-0.984386620492046
				],
				[
					30.02479417632378,
					-1.07336138994188
				]
			]
		},
		{
			"type": "text",
			"version": 247,
			"versionNonce": 1980144784,
			"isDeleted": false,
			"id": "O4zv0ZCo",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -796.4492937803387,
			"y": -196.5023266721746,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 152.12831115722656,
			"height": 20,
			"seed": 516972381,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vector of features",
			"rawText": "Vector of features",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vector of features",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 1219179632,
			"isDeleted": false,
			"id": "0MKEu11k",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -947.6650916349039,
			"y": -160.01664976213306,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 37.61607360839844,
			"height": 20,
			"seed": 1128309725,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "P(wj)",
			"rawText": "P(wj)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "P(wj)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 275,
			"versionNonce": 1378126480,
			"isDeleted": false,
			"id": "eUpOuKxtPo_jxvPPMtf5E",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -852.9574855063788,
			"y": -149.3978569316008,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 30.02479417632378,
			"height": 1.07336138994188,
			"seed": 1806427315,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433117,
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
					10.054373682797063,
					-0.984386620492046
				],
				[
					30.02479417632378,
					-1.07336138994188
				]
			]
		},
		{
			"type": "text",
			"version": 191,
			"versionNonce": 942351984,
			"isDeleted": false,
			"id": "GOjZTo4m",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -800.4653012786611,
			"y": -160.01664976213306,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 211.0564727783203,
			"height": 20,
			"seed": 196519677,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Probability of being class j",
			"rawText": "Probability of being class j",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Probability of being class j",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 107,
			"versionNonce": 273987728,
			"isDeleted": false,
			"id": "iIDBHL2a",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -959.6696881700566,
			"y": -124.14236559047782,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 62.608123779296875,
			"height": 20,
			"seed": 1809398515,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "p(x | wj)",
			"rawText": "p(x | wj)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p(x | wj)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 322,
			"versionNonce": 1457313904,
			"isDeleted": false,
			"id": "9LT79KMX70FMT8m_i5Nfe",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -854.2083037142422,
			"y": -112.64627265753661,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 30.02479417632378,
			"height": 1.07336138994188,
			"seed": 2032198141,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433117,
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
					10.054373682797063,
					-0.984386620492046
				],
				[
					30.02479417632378,
					-1.07336138994188
				]
			]
		},
		{
			"type": "text",
			"version": 274,
			"versionNonce": 877602448,
			"isDeleted": false,
			"id": "eldX1Pts",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -805.4574822580236,
			"y": -122.17665138929121,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 330.35052490234375,
			"height": 17.130076638835057,
			"seed": 748092499,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 13.704061311068045,
			"fontFamily": 1,
			"text": "density function of measurements for each class",
			"rawText": "density function of measurements for each class",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "density function of measurements for each class",
			"lineHeight": 1.25,
			"baseline": 12
		},
		{
			"type": "text",
			"version": 78,
			"versionNonce": 1485326960,
			"isDeleted": false,
			"id": "515i6fFY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -580.0215829193755,
			"y": -156.73490192602483,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 51.280120849609375,
			"height": 20,
			"seed": 631535677,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- Prior",
			"rawText": "- Prior",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- Prior",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 78,
			"versionNonce": 181130384,
			"isDeleted": false,
			"id": "MJgGYaTE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -946.1729007405158,
			"y": -84.17194984118632,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 28.928054809570312,
			"height": 20,
			"seed": 1792602461,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "p(x)",
			"rawText": "p(x)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p(x)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 342,
			"versionNonce": 938835056,
			"isDeleted": false,
			"id": "25CPj0NFmAtf_UxI5BTKr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -856.8214299590876,
			"y": -74.29648602254032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 30.02479417632378,
			"height": 1.07336138994188,
			"seed": 551474077,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433117,
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
					10.054373682797063,
					-0.984386620492046
				],
				[
					30.02479417632378,
					-1.07336138994188
				]
			]
		},
		{
			"type": "text",
			"version": 293,
			"versionNonce": 159564432,
			"isDeleted": false,
			"id": "fxdN2evu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -804.4612836506714,
			"y": -86.11591674449724,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 330.0479736328125,
			"height": 17.612032662174904,
			"seed": 476524531,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 14.089626129739925,
			"fontFamily": 1,
			"text": "density function of measurements (marginalized)",
			"rawText": "density function of measurements (marginalized)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "density function of measurements (marginalized)",
			"lineHeight": 1.25,
			"baseline": 12
		},
		{
			"type": "text",
			"version": 85,
			"versionNonce": 1458335344,
			"isDeleted": false,
			"id": "Up3FRUwt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -967.132889897575,
			"y": -43.45995522104718,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 65.29612731933594,
			"height": 20,
			"seed": 1882489181,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "P(wj | x)",
			"rawText": "P(wj | x)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "P(wj | x)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 362,
			"versionNonce": 791408784,
			"isDeleted": false,
			"id": "zcDyzks6NenEKNVMftGp4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -857.8305365077118,
			"y": -35.450102329483734,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 30.02479417632378,
			"height": 1.07336138994188,
			"seed": 753213651,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433117,
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
					10.054373682797063,
					-0.984386620492046
				],
				[
					30.02479417632378,
					-1.07336138994188
				]
			]
		},
		{
			"type": "text",
			"version": 163,
			"versionNonce": 506798192,
			"isDeleted": false,
			"id": "WwwkbpSX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -809.3496844924332,
			"y": -48.96724739805293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 365.52410888671875,
			"height": 16.328471881996165,
			"seed": 1291853971,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 13.062777505596932,
			"fontFamily": 1,
			"text": "Probability of being of a certain class after observing x",
			"rawText": "Probability of being of a certain class after observing x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Probability of being of a certain class after observing x",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 1669291664,
			"isDeleted": false,
			"id": "ifw9KMgi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -439.91805259244177,
			"y": -48.355326045052294,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 71.82002258300781,
			"height": 16.609235306143106,
			"seed": 1882955741,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"fontSize": 13.287388244914483,
			"fontFamily": 1,
			"text": "- Posterior",
			"rawText": "- Posterior",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- Posterior",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "line",
			"version": 150,
			"versionNonce": 496472688,
			"isDeleted": false,
			"id": "SfWxWXvBMqKG5BL3NqPLF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -983.6724947936652,
			"y": -108.76616711392194,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 159.36444168410708,
			"height": 39.00058066530892,
			"seed": 1626460275,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-90.104789812955,
					-39.00058066530892
				],
				[
					-159.36444168410708,
					-26.896952182971688
				]
			]
		},
		{
			"type": "text",
			"version": 84,
			"versionNonce": 1463094416,
			"isDeleted": false,
			"id": "xShJ0dfq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.38728695704960003,
			"x": -1289.2849012844208,
			"y": -137.0079669060422,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 217.18446350097656,
			"height": 20,
			"seed": 1885612701,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": "[[Probability density]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What is a density function?",
			"rawText": "What is a density function?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is a density function?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 53,
			"versionNonce": 735822960,
			"isDeleted": false,
			"id": "I1QXr8EX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -108.44893171734304,
			"y": -32.47404109276545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 203.3397674560547,
			"height": 25,
			"seed": 615424371,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VlYRdt55i7b_EXo3JyFZa",
					"type": "arrow"
				}
			],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Using Bayes theorem",
			"rawText": "Using Bayes theorem",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Using Bayes theorem",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 51,
			"versionNonce": 1678047888,
			"isDeleted": false,
			"id": "VlYRdt55i7b_EXo3JyFZa",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -13.63955920590817,
			"y": -90.47294906236593,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.3059497663312811,
			"height": 53.10862383080601,
			"seed": 883884115,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "O9Qk4AV6",
				"focus": 0.05890464573293874,
				"gap": 14.225264632382846
			},
			"endBinding": {
				"elementId": "I1QXr8EX",
				"focus": -0.08427458097289638,
				"gap": 4.89028413879447
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
					-1.3059497663312811,
					53.10862383080601
				]
			]
		},
		{
			"type": "image",
			"version": 110,
			"versionNonce": 113882736,
			"isDeleted": false,
			"id": "JKfYPL7gQfsdaSfNEqtol",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -204.61942791518788,
			"y": -5.869273551244035,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 378.30107545572673,
			"height": 110.61052206231456,
			"seed": 1291826557,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6d2e5224ab733dd6ae0f83bddd2d1f0d62c41693",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 115,
			"versionNonce": 1822894224,
			"isDeleted": false,
			"id": "iNrwduVf",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -324.71704352802146,
			"y": 99.41922731276162,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 609.9593505859375,
			"height": 50,
			"seed": 1276379005,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "cppW8ZJOInt_mGVv6tAhI",
					"type": "arrow"
				}
			],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can get to our objective (The posterior) using information\nthat we know!",
			"rawText": "We can get to our objective (The posterior) using information\nthat we know!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can get to our objective (The posterior) using information\nthat we know!",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 77,
			"versionNonce": 1932093552,
			"isDeleted": false,
			"id": "cppW8ZJOInt_mGVv6tAhI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.250742471973347,
			"x": -1.49280658008081,
			"y": 161.4448161574062,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.3947506169686221,
			"height": 86.52741582216674,
			"seed": 2025342579,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "iNrwduVf",
				"focus": -0.049335042435966356,
				"gap": 12.016007101895553
			},
			"endBinding": {
				"elementId": "3OXJuDOm",
				"focus": 0.044662666362837736,
				"gap": 9.936849173360145
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
					0.2710179439535523,
					18.492013173466376
				],
				[
					-1.1237326730150698,
					86.52741582216674
				]
			]
		},
		{
			"type": "text",
			"version": 306,
			"versionNonce": 1020499600,
			"isDeleted": false,
			"id": "3OXJuDOm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -419.99572754752705,
			"y": 257.8904174055913,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 802.819091796875,
			"height": 75,
			"seed": 265892637,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "cppW8ZJOInt_mGVv6tAhI",
					"type": "arrow"
				}
			],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Logically Since P is the probability of predicting a certain class given information\nwe have read, then optimizing our objective to predict the class with the highest\nprobability will give us the most \"probable\" class and thus an optimal decision!",
			"rawText": "Logically Since P is the probability of predicting a certain class given information\nwe have read, then optimizing our objective to predict the class with the highest\nprobability will give us the most \"probable\" class and thus an optimal decision!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Logically Since P is the probability of predicting a certain class given information\nwe have read, then optimizing our objective to predict the class with the highest\nprobability will give us the most \"probable\" class and thus an optimal decision!",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 119,
			"versionNonce": 1556273776,
			"isDeleted": false,
			"id": "KPRD-AYXyofqY0wKa1sXz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -277.8624126648267,
			"y": 337.85780683759737,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 528.6603279790265,
			"height": 57.50340409596429,
			"seed": 1643836851,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a899c87076f2811ac66f4c69f100b405e84f49bb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 78,
			"versionNonce": 1765950608,
			"isDeleted": false,
			"id": "mebBR3l5tXUA_jJoVe952",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 168.77259657180605,
			"y": -15.883699552410064,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 154.64516911603596,
			"height": 57.32536441370297,
			"seed": 2124333843,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					84.65489861093351,
					-19.99722014431501
				],
				[
					154.64516911603596,
					37.32814426938796
				]
			]
		},
		{
			"type": "text",
			"version": 72,
			"versionNonce": 1985875056,
			"isDeleted": false,
			"id": "Ibzlhyqt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 270.33715086109316,
			"y": 29.77731474103041,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 188.81640625,
			"height": 40,
			"seed": 568460947,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Want more detail about\nbayes theorem?",
			"rawText": "Want more detail about\nbayes theorem?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Want more detail about\nbayes theorem?",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 124,
			"versionNonce": 799748752,
			"isDeleted": false,
			"id": "uFplPRUg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -139.52552254651263,
			"y": 402.8484297771845,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 270.84384316593054,
			"height": 60.35107374893018,
			"seed": 52888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "97b7886e0bd346aad2034adde5a733a8e81ebfd9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 130,
			"versionNonce": 1505951344,
			"isDeleted": false,
			"id": "1ZqYVzQlDnO_bjGacPrgy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 73.04026079422204,
			"y": 456.0790768604224,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 145.5200745919547,
			"height": 25.543417348587866,
			"seed": 1818547344,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					82.04855269546391,
					18.577030798973
				],
				[
					145.5200745919547,
					-6.966386549614867
				]
			]
		},
		{
			"type": "text",
			"version": 109,
			"versionNonce": 1455841424,
			"isDeleted": false,
			"id": "afEhWAW1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 201.49504391836496,
			"y": 384.8671254643595,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 212.16046142578125,
			"height": 60,
			"seed": 968171632,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "doesnt depend on j\nand thus can be eliminated\nto maximize the value",
			"rawText": "doesnt depend on j\nand thus can be eliminated\nto maximize the value",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "doesnt depend on j\nand thus can be eliminated\nto maximize the value",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 136,
			"versionNonce": 666480752,
			"isDeleted": false,
			"id": "zfvxaIhi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -140.35520997815638,
			"y": 495.3539470512077,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 261.7754261582211,
			"height": 40.15873014927255,
			"seed": 53341,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d512defb5e8df29f36af3718c66035b8b4d88b03",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 350,
			"versionNonce": 239849104,
			"isDeleted": false,
			"id": "lW3P5d8R",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -141.9467710464036,
			"y": 560.4547745543302,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 300.5904767836726,
			"height": 38.4641842329818,
			"seed": 25999,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "51161663f2ea2e8de51aed4a4d82aa7ecc9480cc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 138,
			"versionNonce": 671752816,
			"isDeleted": false,
			"id": "dyPgzX9b",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -143.61623516816223,
			"y": 623.6956560239663,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 351.79822136324344,
			"height": 38.146795087580614,
			"seed": 92270,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2e564e9e7c093cfa1ba06fdae290d4a14b6382ea",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 98,
			"versionNonce": 1324579984,
			"isDeleted": false,
			"id": "17SZhmHyUWPxRHlnYD9-N",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -161.75987662753408,
			"y": 506.53721598522685,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 118.64751485872972,
			"height": 29.328599178562456,
			"seed": 1305464976,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-46.659135056803876,
					-29.328599178562456
				],
				[
					-118.64751485872972,
					-11.998063300321007
				]
			]
		},
		{
			"type": "text",
			"version": 182,
			"versionNonce": 1769755760,
			"isDeleted": false,
			"id": "ku62Iwqo",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -421.5119681751544,
			"y": 494.53915268490584,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 252.88055419921875,
			"height": 60,
			"seed": 859588240,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Applying the log to both \nsides will keep the same argmax\nConvex function",
			"rawText": "Applying the log to both \nsides will keep the same argmax\nConvex function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Applying the log to both \nsides will keep the same argmax\nConvex function",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 56,
			"versionNonce": 980773520,
			"isDeleted": false,
			"id": "8jvTeGa1W9oFcrE_dgKXX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 172.85277763697434,
			"y": 569.193768775792,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 114.64816042528946,
			"height": 39.326985262163134,
			"seed": 407902832,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					61.98999371832508,
					-39.326985262163134
				],
				[
					114.64816042528946,
					-19.33021309496155
				]
			]
		},
		{
			"type": "text",
			"version": 20,
			"versionNonce": 1641563760,
			"isDeleted": false,
			"id": "DbdHD5mA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 255.460222915626,
			"y": 549.8635556808305,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 72.08013916015625,
			"height": 20,
			"seed": 270159984,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Log rules",
			"rawText": "Log rules",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Log rules",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 102,
			"versionNonce": 2072615056,
			"isDeleted": false,
			"id": "ID3EqbFAvJJqsAVPyRM0e",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 195.44996029838308,
			"y": 672.0502738559322,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 654.3788251143242,
			"height": 527.4465859678546,
			"seed": 1602622576,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					356.14968071193925,
					-25.87938856384335
				],
				[
					470.758401494674,
					-464.59664231280647
				],
				[
					654.3788251143242,
					-527.4465859678546
				]
			]
		},
		{
			"type": "text",
			"version": 161,
			"versionNonce": 233175152,
			"isDeleted": false,
			"id": "NaaxVKmm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 865.6617826514837,
			"y": 62.88931017301522,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 589.4393310546875,
			"height": 25,
			"seed": 1571232880,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Now lets apply this to a multivariate Gaussian distribution",
			"rawText": "Now lets apply this to a multivariate Gaussian distribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Now lets apply this to a multivariate Gaussian distribution",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 174,
			"versionNonce": 635963024,
			"isDeleted": false,
			"id": "s6FPj0vwwgkuF6Uo7xT5m",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 853.3520032700317,
			"y": 133.75155016464174,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 637.4735747086868,
			"height": 82.4638781236528,
			"seed": 1772326032,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "00TNvfSdRIosN57NeuT35",
					"type": "arrow"
				}
			],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1d7efc8a7e930513224f674f97146fa718e3e725",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 78,
			"versionNonce": 292383344,
			"isDeleted": false,
			"id": "G-O5SlYjyxXxy8yEJVJSS",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1492.2405346512833,
			"y": 159.34234849737194,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 110.1960334078176,
			"height": 118.33551314816785,
			"seed": 399677584,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					110.1960334078176,
					-45.08019548501633
				],
				[
					107.06546427691364,
					-118.33551314816785
				]
			]
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 373863568,
			"isDeleted": false,
			"id": "xD6AflA9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1368.808990370482,
			"y": -65.43251510152885,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 447.2195129394531,
			"height": 100,
			"seed": 89890416,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Notice that this is just the normal gaussian\ndistribution applied to d dimensions\nsuch that the covariance matrix is just\nthe matrix of the variances in each direction",
			"rawText": "Notice that this is just the normal gaussian\ndistribution applied to d dimensions\nsuch that the covariance matrix is just\nthe matrix of the variances in each direction",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Notice that this is just the normal gaussian\ndistribution applied to d dimensions\nsuch that the covariance matrix is just\nthe matrix of the variances in each direction",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "line",
			"version": 52,
			"versionNonce": 1463196784,
			"isDeleted": false,
			"id": "D9n0ID9ODG0uuZCD4XRNG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1826.744416158371,
			"y": -66.70118503650338,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 184.46690329920807,
			"height": 64.90502153120286,
			"seed": 1526150768,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					133.22609682720577,
					0
				],
				[
					184.46690329920807,
					64.90502153120286
				]
			]
		},
		{
			"type": "image",
			"version": 70,
			"versionNonce": 1382261392,
			"isDeleted": false,
			"id": "jK6nnbco",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1894.6676133381095,
			"y": 10.932122434021693,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 216.00714341493838,
			"height": 85.54738353066867,
			"seed": 73625,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ed2e6505952b97c93f376535861ad1d9cf2c80f5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 287,
			"versionNonce": 822709872,
			"isDeleted": false,
			"id": "bTcM1qPZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1711.7594898624957,
			"y": 106.08920872850553,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 619.9793090820312,
			"height": 100,
			"seed": 869333104,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Using our knowledge from Linear algebra and computer graphics\n we know that the\ndiagonal scales our distribution in each dimension\nand that the other values shear our distribution",
			"rawText": "Using our knowledge from Linear algebra and computer graphics\n we know that the\ndiagonal scales our distribution in each dimension\nand that the other values shear our distribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Using our knowledge from Linear algebra and computer graphics\n we know that the\ndiagonal scales our distribution in each dimension\nand that the other values shear our distribution",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 166,
			"versionNonce": 1760612496,
			"isDeleted": false,
			"id": "c320SuiH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 859.8576952405901,
			"y": 335.8406928326277,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 189.6755228748206,
			"height": 26.64862718075992,
			"seed": 8321,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d29451bfb99410bf5cdb56f615ce684b53c084cc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 96,
			"versionNonce": 2007908464,
			"isDeleted": false,
			"id": "00TNvfSdRIosN57NeuT35",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1139.2202219593746,
			"y": 224.204666381429,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.1441393735021848,
			"height": 73.97280838582557,
			"seed": 762822256,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "s6FPj0vwwgkuF6Uo7xT5m",
				"focus": 0.10719552421789828,
				"gap": 7.989238093134446
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
					2.1441393735021848,
					73.97280838582557
				]
			]
		},
		{
			"type": "image",
			"version": 85,
			"versionNonce": 1369980560,
			"isDeleted": false,
			"id": "UZVjMtnWoREnhhAbjIRFE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1054.7602678498008,
			"y": 323.29574645727706,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 372.44235537525424,
			"height": 48.95334688768884,
			"seed": 479122064,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ydXvclu6mu_qTBXk2A-fD",
					"type": "arrow"
				}
			],
			"updated": 1703512433118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a98459a5bd580d1d66615ec2bac038a2798b941b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 41,
			"versionNonce": 720155248,
			"isDeleted": false,
			"id": "AX1KAMpgadeP3c1KUzRrL",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1182.001950395938,
			"y": 334.6791471948212,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 11.43889612003477,
			"height": 23.640385314738637,
			"seed": 194865808,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					11.43889612003477,
					23.640385314738637
				]
			]
		},
		{
			"type": "line",
			"version": 28,
			"versionNonce": 1296166032,
			"isDeleted": false,
			"id": "5h2oezH1moPFx6C9sL6kM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1180.2178890895655,
			"y": 316.25778235455044,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 16.71655691506703,
			"height": 0.309565868797506,
			"seed": 64736880,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.71655691506703,
					0.309565868797506
				]
			]
		},
		{
			"type": "line",
			"version": 24,
			"versionNonce": 294446192,
			"isDeleted": false,
			"id": "0oOfN3eTBD18hxSqFZojb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1188.2666016783014,
			"y": 309.7568991098022,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0.9286976063926886,
			"height": 16.097425177471848,
			"seed": 324912272,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.9286976063926886,
					16.097425177471848
				]
			]
		},
		{
			"type": "image",
			"version": 101,
			"versionNonce": 1165351568,
			"isDeleted": false,
			"id": "YqKAr1oX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 856.2726463404181,
			"y": 462.4840291106367,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 95.18826236490307,
			"height": 42.13250957135054,
			"seed": 94891,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "83d5835f35bd524c66e47a21b22234c9f3f1d23e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 48,
			"versionNonce": 1498863216,
			"isDeleted": false,
			"id": "ydXvclu6mu_qTBXk2A-fD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1136.80707620844,
			"y": 381.047852970447,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0,
			"height": 49.5351228983817,
			"seed": 1087324272,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "UZVjMtnWoREnhhAbjIRFE",
				"focus": 0.5594120422959256,
				"gap": 8.798759625481154
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
					49.5351228983817
				]
			]
		},
		{
			"type": "image",
			"version": 99,
			"versionNonce": 754714768,
			"isDeleted": false,
			"id": "M7GbcjC0xxnUOp8QXVGWa",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 954.1798970046596,
			"y": 452.7862883881466,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 144.31198484493754,
			"height": 47.17891812238343,
			"seed": 1578963088,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "412108155d49eb014bac935f127ea9f430731c2a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 26,
			"versionNonce": 923961456,
			"isDeleted": false,
			"id": "cxoA6trN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1101.7197666381417,
			"y": 460.23567825551106,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 12.499984741210938,
			"height": 25,
			"seed": 411156112,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "+",
			"rawText": "+",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "+",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 179,
			"versionNonce": 1603040912,
			"isDeleted": false,
			"id": "zUhGKr6HutkjVp7GcBAwJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1111.265099135906,
			"y": 452.5236372500815,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 196.6478709222474,
			"height": 38.72450381238102,
			"seed": 1521925264,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6a991878374532f72a779fb263d88d8ac0ed8217",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 129,
			"versionNonce": 109574768,
			"isDeleted": false,
			"id": "TOzzmXog",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1304.0380252268365,
			"y": 461.7421133630924,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 114.12519443256093,
			"height": 22.046912560835636,
			"seed": 98810,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c9ade5da33ab114cb901ccf07ca771d0ff08afb7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 61,
			"versionNonce": 31401104,
			"isDeleted": false,
			"id": "Jmhl9vn7zkSqhJU33gaWF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 961.8372826850707,
			"y": 453.0257074534728,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 135.21860152452086,
			"height": 46.50051455141897,
			"seed": 708309648,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					135.21860152452086,
					46.50051455141897
				]
			]
		},
		{
			"type": "freedraw",
			"version": 35,
			"versionNonce": 1786719344,
			"isDeleted": false,
			"id": "077C90R9MxS9EieUZfZZk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1160.3515970405538,
			"y": 360.6823925129444,
			"strokeColor": "#ffffff",
			"backgroundColor": "#a5d8ff",
			"width": 1.0826519401734913,
			"height": 6.186582515277223,
			"seed": 616574576,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.1546645628819192
				],
				[
					0.30932912576372473,
					-0.46399368864575763
				],
				[
					0.4639936886455871,
					-0.7733228144096529
				],
				[
					0.4639936886455871,
					-1.0826519401734913
				],
				[
					0.4639936886455871,
					-1.3919810659373297
				],
				[
					0.4639936886455871,
					-1.701310191701225
				],
				[
					0.4639936886455871,
					-1.8559747545831442
				],
				[
					0.4639936886455871,
					-1.3919810659373297
				],
				[
					0.4639936886455871,
					-0.9279873772915721
				],
				[
					0.4639936886455871,
					-0.1546645628819192
				],
				[
					0.4639936886455871,
					0.4639936886458145
				],
				[
					0.4639936886455871,
					0.927987377291629
				],
				[
					0.4639936886455871,
					1.3919810659374434
				],
				[
					0.4639936886455871,
					1.7013101917012818
				],
				[
					0.4639936886455871,
					1.855974754583201
				],
				[
					0.4639936886455871,
					2.0106393174651203
				],
				[
					0.4639936886455871,
					2.1653038803470963
				],
				[
					0.4639936886455871,
					2.3199684432290155
				],
				[
					0.30932912576372473,
					2.629297568992854
				],
				[
					0.15466456288186237,
					2.938626694756749
				],
				[
					0.15466456288186237,
					3.0932912576386684
				],
				[
					0,
					3.2479558205205876
				],
				[
					-0.15466456288208974,
					3.402620383402507
				],
				[
					-0.3093291257639521,
					3.711949509166402
				],
				[
					-0.6186582515279042,
					4.0212786349302405
				],
				[
					-0.6186582515279042,
					4.17594319781216
				],
				[
					-0.6186582515279042,
					4.330607760694079
				],
				[
					-0.6186582515279042,
					4.330607760694079
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 63,
			"versionNonce": 1638666896,
			"isDeleted": false,
			"id": "GmkvjRyw8hWE35CcJxTNO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1334.6585594084906,
			"y": 357.74376581818774,
			"strokeColor": "#ffffff",
			"backgroundColor": "#a5d8ff",
			"width": 4.330607760694193,
			"height": 7.887892706978505,
			"seed": 685132400,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.15466456288208974,
					0
				],
				[
					0.4639936886458145,
					-0.30932912576389526
				],
				[
					0.4639936886458145,
					-0.7733228144096529
				],
				[
					0.4639936886458145,
					-1.0826519401735482
				],
				[
					0.4639936886458145,
					-1.2373165030554674
				],
				[
					0.6186582515276768,
					-1.2373165030554674
				],
				[
					0.6186582515276768,
					-1.3919810659373866
				],
				[
					0.6186582515276768,
					-1.5466456288193058
				],
				[
					0.7733228144097666,
					-1.5466456288193058
				],
				[
					0.927987377291629,
					-2.0106393174651203
				],
				[
					0.927987377291629,
					-2.3199684432289587
				],
				[
					0.927987377291629,
					-2.629297568992854
				],
				[
					1.0826519401734913,
					-2.783962131874773
				],
				[
					1.0826519401734913,
					-3.2479558205205876
				],
				[
					1.0826519401734913,
					-3.402620383402507
				],
				[
					1.237316503055581,
					-3.557284946284426
				],
				[
					1.237316503055581,
					-3.711949509166402
				],
				[
					1.237316503055581,
					-3.8666140720483213
				],
				[
					1.3919810659374434,
					-4.0212786349302405
				],
				[
					1.5466456288193058,
					-4.0212786349302405
				],
				[
					1.7013101917011682,
					-4.17594319781216
				],
				[
					1.855974754583258,
					-4.17594319781216
				],
				[
					2.0106393174651203,
					-4.330607760694079
				],
				[
					2.16530388034721,
					-4.330607760694079
				],
				[
					2.3199684432290724,
					-4.330607760694079
				],
				[
					2.4746330061109347,
					-4.330607760694079
				],
				[
					2.629297568992797,
					-4.330607760694079
				],
				[
					2.783962131874887,
					-4.330607760694079
				],
				[
					2.938626694756749,
					-4.330607760694079
				],
				[
					3.0932912576386116,
					-4.330607760694079
				],
				[
					3.2479558205207013,
					-4.485272323576055
				],
				[
					3.4026203834025637,
					-4.485272323576055
				],
				[
					3.557284946284426,
					-4.639936886457974
				],
				[
					3.7119495091662884,
					-4.794601449339893
				],
				[
					3.866614072048378,
					-4.794601449339893
				],
				[
					4.0212786349302405,
					-4.949266012221813
				],
				[
					4.0212786349302405,
					-5.103930575103732
				],
				[
					4.175943197812103,
					-5.258595137985708
				],
				[
					4.175943197812103,
					-5.413259700867627
				],
				[
					4.330607760694193,
					-5.7225888266314655
				],
				[
					4.330607760694193,
					-5.877253389513385
				],
				[
					4.330607760694193,
					-6.031917952395361
				],
				[
					4.330607760694193,
					-6.18658251527728
				],
				[
					4.175943197812103,
					-6.18658251527728
				],
				[
					4.175943197812103,
					-6.341247078159199
				],
				[
					4.175943197812103,
					-6.495911641041118
				],
				[
					4.175943197812103,
					-6.650576203923038
				],
				[
					4.0212786349302405,
					-6.805240766805014
				],
				[
					4.0212786349302405,
					-6.959905329686933
				],
				[
					3.866614072048378,
					-6.959905329686933
				],
				[
					3.866614072048378,
					-7.114569892568852
				],
				[
					3.866614072048378,
					-7.269234455450771
				],
				[
					3.866614072048378,
					-7.4238990183326905
				],
				[
					3.866614072048378,
					-7.733228144096586
				],
				[
					3.866614072048378,
					-7.887892706978505
				],
				[
					3.866614072048378,
					-7.887892706978505
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 96,
			"versionNonce": 1824530032,
			"isDeleted": false,
			"id": "NcQT6Dww258XW0ZUlaAjb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1354.778802069358,
			"y": 194.01759830775674,
			"strokeColor": "#ffffff",
			"backgroundColor": "#a5d8ff",
			"width": 4.513663547322949,
			"height": 14.71119970979305,
			"seed": 1523080816,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.16717272397491456
				],
				[
					0.16717272397477245,
					-0.16717272397491456
				],
				[
					0.16717272397477245,
					-0.6686908958996867
				],
				[
					0.5015181719247721,
					-0.8358636198746012
				],
				[
					0.5015181719247721,
					-1.0030363438495158
				],
				[
					0.6686908958995446,
					-1.3373817917993733
				],
				[
					0.8358636198745444,
					-1.504554515774288
				],
				[
					1.0030363438495442,
					-1.504554515774288
				],
				[
					1.0030363438495442,
					-1.6717272397492025
				],
				[
					1.1702090678243167,
					-1.838899963724117
				],
				[
					1.1702090678243167,
					-2.00607268769906
				],
				[
					1.1702090678243167,
					-2.1732454116739746
				],
				[
					1.1702090678243167,
					-2.507590859623832
				],
				[
					1.1702090678243167,
					-2.6747635835987467
				],
				[
					1.1702090678243167,
					-3.1762817555234903
				],
				[
					1.3373817917993165,
					-3.3434544794984333
				],
				[
					1.3373817917993165,
					-3.6777999274482625
				],
				[
					1.3373817917993165,
					-4.012145375398092
				],
				[
					1.3373817917993165,
					-4.179318099373035
				],
				[
					1.3373817917993165,
					-4.513663547322864
				],
				[
					1.5045545157743163,
					-4.848008995272721
				],
				[
					1.5045545157743163,
					-5.18235444322255
				],
				[
					1.6717272397490888,
					-5.6838726151473224
				],
				[
					1.8388999637240886,
					-5.851045339122237
				],
				[
					1.8388999637240886,
					-6.352563511047009
				],
				[
					2.006072687698861,
					-6.519736235021924
				],
				[
					2.006072687698861,
					-6.854081682971781
				],
				[
					2.173245411673861,
					-7.355599854896525
				],
				[
					2.3404181356488607,
					-7.5227725788714395
				],
				[
					2.3404181356488607,
					-7.857118026821297
				],
				[
					2.3404181356488607,
					-8.191463474771155
				],
				[
					2.5075908596238605,
					-8.692981646695898
				],
				[
					2.5075908596238605,
					-8.860154370670813
				],
				[
					2.5075908596238605,
					-9.19449981862067
				],
				[
					2.674763583598633,
					-9.361672542595585
				],
				[
					2.674763583598633,
					-9.696017990545414
				],
				[
					2.674763583598633,
					-10.030363438495272
				],
				[
					2.841936307573633,
					-10.197536162470186
				],
				[
					2.841936307573633,
					-10.531881610420044
				],
				[
					3.0091090315484053,
					-10.699054334394958
				],
				[
					3.0091090315484053,
					-10.866227058369873
				],
				[
					3.176281755523405,
					-11.367745230294645
				],
				[
					3.176281755523405,
					-11.53491795426956
				],
				[
					3.176281755523405,
					-11.869263402219417
				],
				[
					3.343454479498405,
					-12.036436126194332
				],
				[
					3.343454479498405,
					-12.203608850169246
				],
				[
					3.343454479498405,
					-12.537954298119104
				],
				[
					3.5106272034734047,
					-12.705127022094018
				],
				[
					3.5106272034734047,
					-12.872299746068933
				],
				[
					3.5106272034734047,
					-13.039472470043847
				],
				[
					3.5106272034734047,
					-13.206645194018762
				],
				[
					3.5106272034734047,
					-13.373817917993705
				],
				[
					3.677799927448177,
					-13.708163365943534
				],
				[
					3.677799927448177,
					-13.875336089918477
				],
				[
					3.677799927448177,
					-14.042508813893392
				],
				[
					3.677799927448177,
					-14.209681537868306
				],
				[
					3.844972651423177,
					-14.37685426184322
				],
				[
					3.844972651423177,
					-14.544026985818135
				],
				[
					3.844972651423177,
					-14.042508813893392
				],
				[
					3.844972651423177,
					-13.373817917993705
				],
				[
					3.844972651423177,
					-12.705127022094018
				],
				[
					3.844972651423177,
					-12.203608850169246
				],
				[
					3.844972651423177,
					-11.53491795426956
				],
				[
					3.844972651423177,
					-11.033399782344787
				],
				[
					3.677799927448177,
					-10.197536162470186
				],
				[
					3.5106272034734047,
					-9.5288452665705
				],
				[
					3.343454479498405,
					-8.692981646695898
				],
				[
					3.0091090315484053,
					-8.191463474771155
				],
				[
					2.841936307573633,
					-7.6899453028463824
				],
				[
					2.674763583598633,
					-7.355599854896525
				],
				[
					2.5075908596238605,
					-7.18842713092161
				],
				[
					2.3404181356488607,
					-7.021254406946696
				],
				[
					2.173245411673861,
					-6.854081682971781
				],
				[
					2.006072687698861,
					-6.854081682971781
				],
				[
					1.8388999637240886,
					-6.686908958996838
				],
				[
					1.6717272397490888,
					-6.519736235021924
				],
				[
					1.3373817917993165,
					-6.352563511047009
				],
				[
					1.1702090678243167,
					-6.185390787072066
				],
				[
					0.8358636198745444,
					-6.018218063097152
				],
				[
					0.6686908958995446,
					-5.851045339122237
				],
				[
					0.5015181719247721,
					-5.516699891172408
				],
				[
					0.3343454479497723,
					-5.349527167197465
				],
				[
					0,
					-5.349527167197465
				],
				[
					-0.16717272397499983,
					-5.18235444322255
				],
				[
					-0.33434544794999965,
					-5.18235444322255
				],
				[
					-0.5015181719247721,
					-5.18235444322255
				],
				[
					-0.6686908958997719,
					-5.18235444322255
				],
				[
					-0.6686908958997719,
					-5.015181719247636
				],
				[
					-0.6686908958997719,
					-5.015181719247636
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 63,
			"versionNonce": 1437286544,
			"isDeleted": false,
			"id": "25RVrgh2vfie36CJ8y9Z2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1111.2081432378975,
			"y": 204.5494799181768,
			"strokeColor": "#ffffff",
			"backgroundColor": "#a5d8ff",
			"width": 5.851045339122038,
			"height": 12.203608850169246,
			"seed": 105831056,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.16717272397499983,
					-0.16717272397491456
				],
				[
					0.3343454479497723,
					-0.33434544794985754
				],
				[
					0.6686908958997719,
					-0.6686908958996867
				],
				[
					0.8358636198745444,
					-1.0030363438495158
				],
				[
					1.170209067824544,
					-1.3373817917993733
				],
				[
					1.5045545157743163,
					-1.504554515774288
				],
				[
					1.6717272397493161,
					-2.00607268769906
				],
				[
					1.8388999637240886,
					-2.00607268769906
				],
				[
					1.8388999637240886,
					-2.1732454116739746
				],
				[
					1.3373817917993165,
					-1.838899963724117
				],
				[
					1.0030363438495442,
					-1.6717272397492025
				],
				[
					0.3343454479497723,
					-1.0030363438495158
				],
				[
					-0.16717272397499983,
					-0.6686908958996867
				],
				[
					-0.8358636198745444,
					-0.16717272397491456
				],
				[
					-1.1702090678243167,
					0.16717272397491456
				],
				[
					-0.6686908958997719,
					0
				],
				[
					-0.16717272397499983,
					-0.33434544794985754
				],
				[
					0.16717272397499983,
					-0.6686908958996867
				],
				[
					0.5015181719247721,
					-1.0030363438495158
				],
				[
					0.8358636198745444,
					-1.3373817917993733
				],
				[
					1.0030363438495442,
					-1.6717272397492025
				],
				[
					1.170209067824544,
					-2.1732454116739746
				],
				[
					1.3373817917993165,
					-2.6747635835987467
				],
				[
					1.6717272397493161,
					-3.3434544794984333
				],
				[
					1.8388999637240886,
					-3.6777999274482625
				],
				[
					2.0060726876990884,
					-4.012145375398092
				],
				[
					2.1732454116740882,
					-4.513663547322864
				],
				[
					2.3404181356488607,
					-4.848008995272721
				],
				[
					2.3404181356488607,
					-5.015181719247636
				],
				[
					2.5075908596238605,
					-5.18235444322255
				],
				[
					2.5075908596238605,
					-5.516699891172408
				],
				[
					2.6747635835988604,
					-5.851045339122237
				],
				[
					2.6747635835988604,
					-6.1853907870720946
				],
				[
					2.841936307573633,
					-6.519736235021924
				],
				[
					3.0091090315486326,
					-7.021254406946696
				],
				[
					3.176281755523405,
					-7.355599854896525
				],
				[
					3.176281755523405,
					-7.5227725788714395
				],
				[
					3.343454479498405,
					-7.857118026821297
				],
				[
					3.5106272034734047,
					-8.191463474771155
				],
				[
					3.6777999274484046,
					-8.525808922720984
				],
				[
					3.6777999274484046,
					-8.692981646695898
				],
				[
					3.844972651423177,
					-8.860154370670813
				],
				[
					3.844972651423177,
					-9.027327094645756
				],
				[
					3.844972651423177,
					-9.19449981862067
				],
				[
					4.012145375398177,
					-9.528845266570528
				],
				[
					4.012145375398177,
					-9.863190714520357
				],
				[
					4.179318099372949,
					-10.197536162470186
				],
				[
					4.346490823347949,
					-10.364708886445129
				],
				[
					4.346490823347949,
					-10.866227058369873
				],
				[
					4.513663547322949,
					-11.033399782344787
				],
				[
					4.513663547322949,
					-11.367745230294645
				],
				[
					4.513663547322949,
					-11.53491795426956
				],
				[
					4.680836271297721,
					-11.53491795426956
				],
				[
					4.680836271297721,
					-11.869263402219417
				],
				[
					4.680836271297721,
					-12.036436126194332
				],
				[
					4.680836271297721,
					-12.036436126194332
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "image",
			"version": 184,
			"versionNonce": 504549488,
			"isDeleted": false,
			"id": "SA1PK4n7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 858.643894994006,
			"y": 528.6157789031577,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 487.3172453863656,
			"height": 54.47352894046987,
			"seed": 55569,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e4b1ee0f1f45122828a5c47d221c14af0fa42629",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 44,
			"versionNonce": 496283280,
			"isDeleted": false,
			"id": "JNA3o3Hd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1015.2303683921518,
			"y": 521.8380590693494,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 13.639984130859375,
			"height": 25,
			"seed": 1621434992,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "-1",
			"rawText": "-1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "-1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 67,
			"versionNonce": 910115440,
			"isDeleted": false,
			"id": "zXA1o5zf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1183.4109761515888,
			"y": 520.5035765969467,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 13.639984130859375,
			"height": 25,
			"seed": 1263039600,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "-1",
			"rawText": "-1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "-1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "freedraw",
			"version": 64,
			"versionNonce": 1109417104,
			"isDeleted": false,
			"id": "Jo8arABemUNujH_nXj_rb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 977.9352633467264,
			"y": 583.040459672879,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 90.23152747851998,
			"height": 18.668591892107543,
			"seed": 83523728,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.3457146646686624
				],
				[
					0,
					1.3828586586746496
				],
				[
					1.0371439940059872,
					3.111431982017848
				],
				[
					2.420002652680637,
					4.84000530536116
				],
				[
					4.494290640692611,
					6.9142932933731345
				],
				[
					6.9142932933731345,
					9.334295946053771
				],
				[
					8.642866616716447,
					10.371439940059759
				],
				[
					12.10001326340307,
					12.445727928071733
				],
				[
					14.86573058075237,
					13.828586586746383
				],
				[
					18.32287722743888,
					14.86573058075237
				],
				[
					20.742879880119517,
					15.557159910089695
				],
				[
					23.85431186213748,
					16.24858923942702
				],
				[
					28.34860250283009,
					16.940018568764344
				],
				[
					33.880037137528575,
					17.631447898101555
				],
				[
					36.645754454877874,
					17.631447898101555
				],
				[
					39.41147177222717,
					17.631447898101555
				],
				[
					42.17718908957647,
					17.631447898101555
				],
				[
					44.597191742256996,
					17.631447898101555
				],
				[
					47.017194394937746,
					17.631447898101555
				],
				[
					48.745767718280945,
					17.631447898101555
				],
				[
					51.165770370961695,
					17.631447898101555
				],
				[
					53.58577302364222,
					17.631447898101555
				],
				[
					55.66006101165419,
					17.631447898101555
				],
				[
					57.73434899966617,
					17.631447898101555
				],
				[
					59.462922323009366,
					17.631447898101555
				],
				[
					61.19149564635279,
					17.631447898101555
				],
				[
					62.92006896969599,
					17.631447898101555
				],
				[
					64.99435695770796,
					17.631447898101555
				],
				[
					66.03150095171384,
					17.285733233432893
				],
				[
					67.41435961038849,
					17.285733233432893
				],
				[
					69.14293293373191,
					16.594303904095568
				],
				[
					70.18007692773779,
					16.24858923942702
				],
				[
					71.90865025108121,
					15.902874574758243
				],
				[
					73.29150890975586,
					15.211445245420919
				],
				[
					75.02008223309906,
					14.520015916083594
				],
				[
					76.05722622710493,
					13.828586586746383
				],
				[
					76.40294089177371,
					13.48287192207772
				],
				[
					77.78579955044836,
					12.791442592740395
				],
				[
					78.82294354445423,
					12.10001326340307
				],
				[
					79.86008753846033,
					11.062869269397083
				],
				[
					81.24294619713498,
					10.025725275391096
				],
				[
					81.93437552647231,
					9.334295946053771
				],
				[
					83.6629488498155,
					7.951437287379122
				],
				[
					84.35437817915283,
					7.260007958041797
				],
				[
					85.39152217315893,
					6.22286396403581
				],
				[
					86.4286661671648,
					5.185719970029822
				],
				[
					86.77438083183335,
					4.494290640692498
				],
				[
					87.46581016117091,
					3.802861311355173
				],
				[
					87.81152482583946,
					3.111431982017848
				],
				[
					88.157239490508,
					2.420002652680523
				],
				[
					88.84866881984556,
					1.3828586586746496
				],
				[
					89.1943834845141,
					1.0371439940059872
				],
				[
					89.88581281385143,
					0
				],
				[
					90.23152747851998,
					-0.3457146646686624
				],
				[
					90.23152747851998,
					-0.6914293293373248
				],
				[
					90.23152747851998,
					-1.0371439940059872
				],
				[
					90.23152747851998,
					-1.0371439940059872
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 90,
			"versionNonce": 873297008,
			"isDeleted": false,
			"id": "J3jhkC6xds-ol7AjumR8e",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1025.2981724063327,
			"y": 627.2919367504674,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 35.608610460872,
			"height": 20.74287988011963,
			"seed": 1101763216,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.3457146646686624
				],
				[
					0,
					-0.6914293293373248
				],
				[
					0,
					-2.0742879880119744
				],
				[
					-0.3457146646685487,
					-3.457146646686624
				],
				[
					-0.6914293293373248,
					-4.148575976023949
				],
				[
					-1.0371439940058735,
					-4.494290640692498
				],
				[
					-1.3828586586746496,
					-4.840005305361274
				],
				[
					-1.7285733233431984,
					-4.840005305361274
				],
				[
					-2.420002652680523,
					-4.494290640692498
				],
				[
					-3.802861311355173,
					-4.148575976023949
				],
				[
					-4.840005305361274,
					-4.148575976023949
				],
				[
					-5.531434634698485,
					-3.802861311355173
				],
				[
					-6.22286396403581,
					-3.457146646686624
				],
				[
					-7.260007958041797,
					-3.457146646686624
				],
				[
					-8.297151952047784,
					-3.457146646686624
				],
				[
					-8.988581281385109,
					-2.7657173173492993
				],
				[
					-10.025725275391096,
					-1.728573323343312
				],
				[
					-10.717154604728421,
					-0.6914293293373248
				],
				[
					-11.754298598734408,
					0.6914293293373248
				],
				[
					-12.10001326340307,
					2.420002652680637
				],
				[
					-12.791442592740395,
					3.457146646686624
				],
				[
					-12.791442592740395,
					4.494290640692611
				],
				[
					-13.137157257409058,
					6.222863964035923
				],
				[
					-13.137157257409058,
					7.260007958041911
				],
				[
					-13.137157257409058,
					8.297151952047898
				],
				[
					-12.791442592740395,
					9.680010610722547
				],
				[
					-12.10001326340307,
					11.062869269397083
				],
				[
					-11.754298598734408,
					12.445727928071733
				],
				[
					-10.025725275391096,
					13.828586586746383
				],
				[
					-9.334295946053771,
					14.520015916083707
				],
				[
					-8.642866616716447,
					14.86573058075237
				],
				[
					-7.951437287379122,
					15.557159910089695
				],
				[
					-6.568578628704472,
					15.902874574758357
				],
				[
					-4.840005305361274,
					15.902874574758357
				],
				[
					-3.457146646686624,
					15.902874574758357
				],
				[
					-2.7657173173492993,
					15.557159910089695
				],
				[
					-1.3828586586746496,
					14.520015916083707
				],
				[
					-0.3457146646685487,
					13.828586586746383
				],
				[
					0.3457146646687761,
					12.791442592740395
				],
				[
					1.3828586586746496,
					11.408583934065746
				],
				[
					2.0742879880119744,
					10.371439940059872
				],
				[
					2.4200026526807505,
					8.988581281385223
				],
				[
					2.7657173173492993,
					6.914293293373248
				],
				[
					2.7657173173492993,
					5.5314346346985985
				],
				[
					2.7657173173492993,
					4.148575976023949
				],
				[
					2.7657173173492993,
					3.1114319820179617
				],
				[
					2.7657173173492993,
					2.0742879880119744
				],
				[
					2.7657173173492993,
					1.0371439940059872
				],
				[
					2.4200026526807505,
					0.3457146646686624
				],
				[
					2.4200026526807505,
					0
				],
				[
					2.4200026526807505,
					-0.3457146646686624
				],
				[
					2.4200026526807505,
					-0.6914293293373248
				],
				[
					2.4200026526807505,
					-1.0371439940059872
				],
				[
					2.4200026526807505,
					-1.3828586586746496
				],
				[
					2.4200026526807505,
					-1.0371439940059872
				],
				[
					2.4200026526807505,
					0
				],
				[
					2.7657173173492993,
					1.0371439940059872
				],
				[
					3.111431982017848,
					2.7657173173492993
				],
				[
					3.457146646686624,
					4.148575976023949
				],
				[
					3.8028613113554,
					5.877149299367261
				],
				[
					4.148575976023949,
					7.605722622710573
				],
				[
					4.840005305361274,
					9.680010610722547
				],
				[
					5.5314346346985985,
					11.408583934065746
				],
				[
					6.222863964035923,
					12.445727928071733
				],
				[
					6.568578628704472,
					13.48287192207772
				],
				[
					7.260007958041797,
					13.828586586746383
				],
				[
					8.297151952047898,
					14.520015916083707
				],
				[
					10.025725275391096,
					15.211445245421032
				],
				[
					11.408583934065746,
					15.557159910089695
				],
				[
					13.137157257409172,
					15.902874574758357
				],
				[
					15.211445245420919,
					15.902874574758357
				],
				[
					16.940018568764344,
					15.902874574758357
				],
				[
					18.668591892107543,
					15.902874574758357
				],
				[
					20.051450550782192,
					15.902874574758357
				],
				[
					21.088594544788293,
					15.902874574758357
				],
				[
					22.125738538794167,
					15.557159910089695
				],
				[
					22.471453203462943,
					15.211445245421032
				],
				[
					22.471453203462943,
					14.86573058075237
				],
				[
					22.471453203462943,
					14.520015916083707
				],
				[
					22.471453203462943,
					14.174301251415045
				],
				[
					22.471453203462943,
					13.828586586746383
				],
				[
					22.471453203462943,
					13.48287192207772
				],
				[
					22.471453203462943,
					13.48287192207772
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 117,
			"versionNonce": 1963346576,
			"isDeleted": false,
			"id": "bYUy84WqyG4OS-nG0-_Cw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1336.0956559434574,
			"y": 573.3604490621565,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 240.2716919447182,
			"height": 26.62002917948689,
			"seed": 144712304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.3457146646685487,
					0
				],
				[
					-0.3457146646685487,
					0.6914293293373248
				],
				[
					-0.6914293293373248,
					0.6914293293373248
				],
				[
					-2.0742879880119744,
					2.0742879880119744
				],
				[
					-3.457146646686624,
					3.1114319820179617
				],
				[
					-4.840005305361274,
					3.8028613113552865
				],
				[
					-7.260007958041797,
					4.840005305361274
				],
				[
					-10.025725275391096,
					5.5314346346985985
				],
				[
					-11.754298598734295,
					6.222863964035923
				],
				[
					-13.828586586746269,
					7.951437287379235
				],
				[
					-15.557159910089695,
					8.64286661671656
				],
				[
					-17.977162562770218,
					10.371439940059872
				],
				[
					-19.01430655677609,
					11.408583934065746
				],
				[
					-21.78002387412539,
					12.10001326340307
				],
				[
					-24.20002652680614,
					12.791442592740395
				],
				[
					-26.96574384415544,
					13.48287192207772
				],
				[
					-30.07717582617329,
					14.520015916083707
				],
				[
					-32.49717847885381,
					14.86573058075237
				],
				[
					-36.30003979020921,
					15.902874574758357
				],
				[
					-41.140045095570486,
					15.902874574758357
				],
				[
					-43.905762412919785,
					15.902874574758357
				],
				[
					-47.70862372427496,
					16.940018568764344
				],
				[
					-51.16577037096158,
					17.63144789810167
				],
				[
					-55.3143463469853,
					18.668591892107656
				],
				[
					-59.1172076583407,
					19.705735886113644
				],
				[
					-62.920068969695876,
					20.39716521545097
				],
				[
					-66.03150095171395,
					20.74287988011963
				],
				[
					-68.79721826906302,
					21.780023874125618
				],
				[
					-73.29150890975575,
					22.817167868131605
				],
				[
					-77.4400848857797,
					23.50859719746893
				],
				[
					-82.28009019114074,
					24.545741191474917
				],
				[
					-86.77438083183347,
					25.58288518548079
				],
				[
					-91.26867147252597,
					25.928599850149567
				],
				[
					-96.10867677788724,
					26.62002917948689
				],
				[
					-99.91153808924241,
					26.62002917948689
				],
				[
					-104.40582872993514,
					26.62002917948689
				],
				[
					-108.90011937062764,
					26.62002917948689
				],
				[
					-113.74012467598891,
					26.62002917948689
				],
				[
					-117.88870065201286,
					26.62002917948689
				],
				[
					-123.42013528671123,
					26.62002917948689
				],
				[
					-128.95156992140983,
					25.58288518548079
				],
				[
					-133.44586056210233,
					25.237170520812242
				],
				[
					-137.59443653812627,
					25.237170520812242
				],
				[
					-142.43444184348755,
					24.545741191474917
				],
				[
					-145.89158849017417,
					24.20002652680614
				],
				[
					-151.077308460204,
					23.162882532800268
				],
				[
					-157.30017242423992,
					22.817167868131605
				],
				[
					-161.1030337355951,
					22.471453203462943
				],
				[
					-165.59732437628782,
					21.780023874125618
				],
				[
					-170.78304434631764,
					21.434309209456956
				],
				[
					-173.54876166366694,
					21.434309209456956
				],
				[
					-175.96876431634746,
					21.434309209456956
				],
				[
					-178.73448163369676,
					21.434309209456956
				],
				[
					-181.8459136157146,
					21.434309209456956
				],
				[
					-184.6116309330639,
					21.434309209456956
				],
				[
					-187.72306291508198,
					21.434309209456956
				],
				[
					-190.1430655677625,
					21.434309209456956
				],
				[
					-192.21735355577448,
					21.434309209456956
				],
				[
					-194.98307087312378,
					20.74287988011963
				],
				[
					-197.40307352580453,
					20.39716521545097
				],
				[
					-199.13164684914773,
					20.39716521545097
				],
				[
					-200.86022017249093,
					20.051450550782306
				],
				[
					-202.24307883116558,
					19.705735886113644
				],
				[
					-203.971652154509,
					19.36002122144498
				],
				[
					-205.00879614851488,
					19.36002122144498
				],
				[
					-206.39165480718952,
					19.01430655677632
				],
				[
					-207.77451346586417,
					18.322877227438994
				],
				[
					-208.81165745987005,
					17.97716256277033
				],
				[
					-210.1945161185447,
					17.63144789810167
				],
				[
					-211.57737477721935,
					17.285733233433007
				],
				[
					-212.61451877122545,
					16.940018568764344
				],
				[
					-213.65166276523132,
					16.594303904095682
				],
				[
					-214.68880675923742,
					16.24858923942702
				],
				[
					-216.07166541791207,
					15.902874574758357
				],
				[
					-217.80023874125527,
					15.557159910089695
				],
				[
					-219.52881206459847,
					15.211445245421032
				],
				[
					-220.91167072327312,
					15.211445245421032
				],
				[
					-221.60310005261067,
					15.211445245421032
				],
				[
					-222.64024404661654,
					14.86573058075237
				],
				[
					-223.33167337595387,
					14.86573058075237
				],
				[
					-224.0231027052912,
					14.520015916083707
				],
				[
					-224.36881736995974,
					14.520015916083707
				],
				[
					-225.7516760286344,
					14.174301251415045
				],
				[
					-226.44310535797172,
					14.174301251415045
				],
				[
					-227.13453468730904,
					14.174301251415045
				],
				[
					-227.48024935197782,
					14.174301251415045
				],
				[
					-228.17167868131514,
					14.174301251415045
				],
				[
					-228.5173933459837,
					14.174301251415045
				],
				[
					-229.20882267532102,
					13.828586586746496
				],
				[
					-229.90025200465834,
					13.828586586746496
				],
				[
					-230.2459666693269,
					13.48287192207772
				],
				[
					-230.93739599866444,
					13.137157257409172
				],
				[
					-231.283110663333,
					13.137157257409172
				],
				[
					-231.97453999267032,
					12.791442592740395
				],
				[
					-232.66596932200764,
					12.445727928071847
				],
				[
					-233.0116839866762,
					12.445727928071847
				],
				[
					-233.70311331601374,
					12.10001326340307
				],
				[
					-234.0488279806823,
					11.754298598734522
				],
				[
					-234.39454264535084,
					11.754298598734522
				],
				[
					-234.74025731001962,
					11.408583934065746
				],
				[
					-235.7774013040255,
					10.717154604728535
				],
				[
					-236.12311596869426,
					10.717154604728535
				],
				[
					-236.4688306333628,
					10.371439940059872
				],
				[
					-236.8145452980316,
					10.02572527539121
				],
				[
					-237.16025996270014,
					10.02572527539121
				],
				[
					-238.19740395670624,
					9.680010610722547
				],
				[
					-238.5431186213748,
					9.334295946053885
				],
				[
					-239.2345479507121,
					9.334295946053885
				],
				[
					-239.5802626153809,
					8.988581281385223
				],
				[
					-240.2716919447182,
					8.64286661671656
				],
				[
					-240.2716919447182,
					8.64286661671656
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 23,
			"versionNonce": 2101700208,
			"isDeleted": false,
			"id": "6l2Thh9cd0LhGrobs0au_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1213.712664650752,
			"y": 614.1547794930583,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.037143994006101,
			"height": 21.08859454478818,
			"seed": 1242182768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.3457146646686624
				],
				[
					0,
					1.0371439940059872
				],
				[
					0.3457146646685487,
					2.7657173173492993
				],
				[
					0.6914293293373248,
					3.8028613113552865
				],
				[
					1.037143994006101,
					5.5314346346985985
				],
				[
					1.037143994006101,
					7.605722622710573
				],
				[
					1.037143994006101,
					9.334295946053885
				],
				[
					1.037143994006101,
					11.408583934065746
				],
				[
					1.037143994006101,
					13.828586586746383
				],
				[
					0.6914293293373248,
					15.557159910089695
				],
				[
					0.6914293293373248,
					17.63144789810167
				],
				[
					0.6914293293373248,
					18.668591892107656
				],
				[
					0.6914293293373248,
					19.705735886113644
				],
				[
					0.6914293293373248,
					20.39716521545097
				],
				[
					0.6914293293373248,
					20.74287988011963
				],
				[
					0.6914293293373248,
					21.08859454478818
				],
				[
					0.6914293293373248,
					21.08859454478818
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 53,
			"versionNonce": 1895725200,
			"isDeleted": false,
			"id": "Bd3lGKCX_ghNo_qDLIQgn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1215.4412379740952,
			"y": 628.3290807444733,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 17.28573323343312,
			"height": 13.48287192207772,
			"seed": 489450096,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.3457146646686624
				],
				[
					0.3457146646687761,
					-0.3457146646686624
				],
				[
					0.3457146646687761,
					-0.6914293293373248
				],
				[
					1.7285733233434257,
					-2.420002652680637
				],
				[
					2.4200026526807505,
					-3.4571466466865104
				],
				[
					3.4571466466868515,
					-4.494290640692611
				],
				[
					4.148575976023949,
					-5.185719970029936
				],
				[
					4.494290640692725,
					-5.531434634698485
				],
				[
					5.18571997003005,
					-5.877149299367261
				],
				[
					5.877149299367375,
					-5.877149299367261
				],
				[
					6.568578628704699,
					-5.877149299367261
				],
				[
					7.605722622710573,
					-5.877149299367261
				],
				[
					8.642866616716674,
					-5.877149299367261
				],
				[
					10.371439940059872,
					-5.185719970029936
				],
				[
					11.408583934065973,
					-4.84000530536116
				],
				[
					12.445727928071847,
					-4.494290640692611
				],
				[
					13.828586586746496,
					-4.148575976023835
				],
				[
					14.86573058075237,
					-3.1114319820179617
				],
				[
					15.557159910089922,
					-2.420002652680637
				],
				[
					16.24858923942702,
					-2.0742879880119744
				],
				[
					16.594303904095796,
					-1.3828586586746496
				],
				[
					17.28573323343312,
					-0.3457146646686624
				],
				[
					17.28573323343312,
					0.6914293293373248
				],
				[
					17.28573323343312,
					1.3828586586746496
				],
				[
					17.28573323343312,
					2.0742879880119744
				],
				[
					16.940018568764344,
					2.420002652680637
				],
				[
					16.24858923942702,
					3.457146646686624
				],
				[
					15.211445245421146,
					4.494290640692611
				],
				[
					14.520015916083821,
					4.840005305361274
				],
				[
					13.48287192207772,
					5.877149299367261
				],
				[
					12.445727928071847,
					6.222863964035923
				],
				[
					11.754298598734522,
					6.568578628704586
				],
				[
					10.717154604728421,
					6.9142932933731345
				],
				[
					10.025725275391324,
					7.260007958041911
				],
				[
					8.988581281385223,
					7.260007958041911
				],
				[
					7.605722622710573,
					7.605722622710459
				],
				[
					6.914293293373248,
					7.605722622710459
				],
				[
					5.877149299367375,
					7.605722622710459
				],
				[
					4.840005305361274,
					7.605722622710459
				],
				[
					4.148575976023949,
					7.605722622710459
				],
				[
					3.4571466466868515,
					7.605722622710459
				],
				[
					2.7657173173492993,
					7.605722622710459
				],
				[
					2.4200026526807505,
					7.605722622710459
				],
				[
					2.074287988012202,
					7.605722622710459
				],
				[
					1.7285733233434257,
					7.605722622710459
				],
				[
					1.3828586586746496,
					7.605722622710459
				],
				[
					1.3828586586746496,
					7.605722622710459
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 207,
			"versionNonce": 2125404272,
			"isDeleted": false,
			"id": "TUgPas3u",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 895.1074177486037,
			"y": 91.68864802421615,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 510.1130676269531,
			"height": 40,
			"seed": 234522736,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Assuming that the covariance is the same between both classes\ni.e does not depend on the class!",
			"rawText": "Assuming that the covariance is the same between both classes\ni.e does not depend on the class!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assuming that the covariance is the same between both classes\ni.e does not depend on the class!",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 444,
			"versionNonce": 1505814160,
			"isDeleted": false,
			"id": "C2SUaJGN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 753.6132204373084,
			"y": 699.9243656628682,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 767.4991455078125,
			"height": 125,
			"seed": 2121962096,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "TkYxtzKdY6mAHX3E3WkgL",
					"type": "arrow"
				},
				{
					"id": "wZ4_X0R4RDC1-TjclHxKC",
					"type": "arrow"
				}
			],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This leads us to a linear decision boundary that seperates both classes\nThe orientation is decided by their mean and covariance and\nit shifts close to one of the two classes depending on the prior probabilities!\nThis is because Bayes theorem insists on us using our current information\nand the PRIOR information to update our decision boundary",
			"rawText": "This leads us to a linear decision boundary that seperates both classes\nThe orientation is decided by their mean and covariance and\nit shifts close to one of the two classes depending on the prior probabilities!\nThis is because Bayes theorem insists on us using our current information\nand the PRIOR information to update our decision boundary",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This leads us to a linear decision boundary that seperates both classes\nThe orientation is decided by their mean and covariance and\nit shifts close to one of the two classes depending on the prior probabilities!\nThis is because Bayes theorem insists on us using our current information\nand the PRIOR information to update our decision boundary",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "arrow",
			"version": 230,
			"versionNonce": 1276283504,
			"isDeleted": false,
			"id": "TkYxtzKdY6mAHX3E3WkgL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1118.1610556349158,
			"y": 647.3793846681448,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.4958350380761658,
			"height": 38.40347511259779,
			"seed": 57493648,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "C2SUaJGN",
				"focus": -0.03811829944933054,
				"gap": 14.14150588212567
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
					1.4958350380761658,
					38.40347511259779
				]
			]
		},
		{
			"type": "ellipse",
			"version": 390,
			"versionNonce": 470127760,
			"isDeleted": false,
			"id": "OL_RDVVwh-qsxDaWhOUmk",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.726422537062287,
			"x": 790.4472729006782,
			"y": 998.6997015130914,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 95.70606395381878,
			"height": 185.98199661947785,
			"seed": 1367214224,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 148,
			"versionNonce": 1077394544,
			"isDeleted": false,
			"id": "_EUp1RCXursyaoUMaLwk6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 802.665068299038,
			"y": 924.035396300892,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 221.2778499925173,
			"height": 260.64630183167685,
			"seed": 1170219120,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					221.2778499925173,
					260.64630183167685
				]
			]
		},
		{
			"type": "ellipse",
			"version": 427,
			"versionNonce": 1300529808,
			"isDeleted": false,
			"id": "YjvmpLL2sjqbgxrFwR7Uq",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.648158571789272,
			"x": 915.6796757338667,
			"y": 897.5635062711123,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 95.70606395381878,
			"height": 185.98199661947785,
			"seed": 1012376720,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 133,
			"versionNonce": 484879984,
			"isDeleted": false,
			"id": "FoQI3LJY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.2249498524676445,
			"x": 936.3842183648419,
			"y": 951.5036047986822,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 27.5999755859375,
			"height": 25,
			"seed": 492626544,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "w 1",
			"rawText": "w 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "w 1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 47,
			"versionNonce": 217428112,
			"isDeleted": false,
			"id": "zjJFvD50",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 800.5055840592729,
			"y": 1039.630933750815,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 36.41996765136719,
			"height": 25,
			"seed": 1699158672,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "w 2",
			"rawText": "w 2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "w 2",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 85,
			"versionNonce": 719806576,
			"isDeleted": false,
			"id": "WpjRjtdkaDcV9GZd3jpjJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1051.8035065920567,
			"y": 1003.4631546055207,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 224.65245331240408,
			"height": 2.1670654660360924,
			"seed": 238010480,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
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
					224.65245331240408,
					2.1670654660360924
				]
			]
		},
		{
			"type": "ellipse",
			"version": 450,
			"versionNonce": 1645289104,
			"isDeleted": false,
			"id": "8K-ekHOPItAdXnCANWd47",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.726422537062287,
			"x": 1321.2647914490015,
			"y": 941.0066351054883,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 95.70606395381878,
			"height": 185.98199661947785,
			"seed": 665816688,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 212,
			"versionNonce": 1510068848,
			"isDeleted": false,
			"id": "pHPDjVgsga3-DlF3L3vhi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1333.4825868473613,
			"y": 866.3423298932888,
			"strokeColor": "#ced4da",
			"backgroundColor": "transparent",
			"width": 221.2778499925173,
			"height": 260.64630183167685,
			"seed": 697581680,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					221.2778499925173,
					260.64630183167685
				]
			]
		},
		{
			"type": "ellipse",
			"version": 487,
			"versionNonce": 495897744,
			"isDeleted": false,
			"id": "EbMnVlnFadJV4deHxe6zC",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.648158571789272,
			"x": 1446.49719428219,
			"y": 839.8704398635092,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 95.70606395381878,
			"height": 185.98199661947785,
			"seed": 806531696,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 193,
			"versionNonce": 1627260016,
			"isDeleted": false,
			"id": "h9qNt2Z0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.2249498524676445,
			"x": 1467.2017369131652,
			"y": 893.8105383910791,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 27.5999755859375,
			"height": 25,
			"seed": 32695408,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "w 1",
			"rawText": "w 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "w 1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 107,
			"versionNonce": 958839440,
			"isDeleted": false,
			"id": "RBpaZvFo",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1331.3231026075962,
			"y": 981.9378673432119,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 36.41996765136719,
			"height": 25,
			"seed": 1291638384,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "w 2",
			"rawText": "w 2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "w 2",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 120,
			"versionNonce": 1571026544,
			"isDeleted": false,
			"id": "H1G0RZJtvwKYOiNgcBEz2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1521.1038919701716,
			"y": 1083.4190729172756,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 33.37137742002278,
			"height": 23.755895790524846,
			"seed": 1010036880,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
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
					33.37137742002278,
					-23.755895790524846
				]
			]
		},
		{
			"type": "line",
			"version": 274,
			"versionNonce": 932243600,
			"isDeleted": false,
			"id": "xFHIcKcIApyMaihILeBsC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1378.1130632446814,
			"y": 847.2199783364271,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 221.2778499925173,
			"height": 260.64630183167685,
			"seed": 1632664208,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					221.2778499925173,
					260.64630183167685
				]
			]
		},
		{
			"type": "text",
			"version": 134,
			"versionNonce": 1958455408,
			"isDeleted": false,
			"id": "JR6Z3zaI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1218.414507563702,
			"y": 1163.833770225103,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 402.9195556640625,
			"height": 50,
			"seed": 1805307536,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433119,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "If w2 is more common in the wild than w1\naka its prior probability is higher!",
			"rawText": "If w2 is more common in the wild than w1\naka its prior probability is higher!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If w2 is more common in the wild than w1\naka its prior probability is higher!",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 35,
			"versionNonce": 75847312,
			"isDeleted": false,
			"id": "wZ4_X0R4RDC1-TjclHxKC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1551.673227462462,
			"y": 722.0332949597667,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 342.11626379946347,
			"height": 1.2395516804327826,
			"seed": 1908245136,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "C2SUaJGN",
				"focus": -0.6086978288706919,
				"gap": 30.56086151734098
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
					342.11626379946347,
					-1.2395516804327826
				]
			]
		},
		{
			"type": "text",
			"version": 213,
			"versionNonce": 1913461360,
			"isDeleted": false,
			"id": "hnfxWQlX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1910.4482356662647,
			"y": 700.9609163924085,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 583.979248046875,
			"height": 50,
			"seed": 380638864,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "What if we relax our assumption that they have the same\nshape aka the same covariance?",
			"rawText": "What if we relax our assumption that they have the same\nshape aka the same covariance?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What if we relax our assumption that they have the same\nshape aka the same covariance?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 165,
			"versionNonce": 1421608080,
			"isDeleted": false,
			"id": "fnZC7kqu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1902.6981769471286,
			"y": 754.3034319292893,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 572.209228515625,
			"height": 40,
			"seed": 1371019376,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Well then the classifier wont be linear anymore and instead\nit will be a degenerate form of higher order (quadratic, hyperbolic etc...)",
			"rawText": "Well then the classifier wont be linear anymore and instead\nit will be a degenerate form of higher order (quadratic, hyperbolic etc...)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Well then the classifier wont be linear anymore and instead\nit will be a degenerate form of higher order (quadratic, hyperbolic etc...)",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 107,
			"versionNonce": 1751141488,
			"isDeleted": false,
			"id": "eOyeQ7uLBteEvWxgtNPdm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -148.58521695259878,
			"y": 677.0100325772542,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 507.78492850522025,
			"height": 136.2349808184738,
			"seed": 1939455632,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-189.1527006405255,
					113.7168021707921
				],
				[
					-507.78492850522025,
					-22.51817864768168
				]
			]
		},
		{
			"type": "text",
			"version": 131,
			"versionNonce": 99414672,
			"isDeleted": false,
			"id": "7JuhJCdl",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.436289409803317,
			"x": -605.3036503805372,
			"y": 693.8986665630152,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 273.92059326171875,
			"height": 20,
			"seed": 1487871120,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What if our data is non-numerical?",
			"rawText": "What if our data is non-numerical?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What if our data is non-numerical?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 332,
			"versionNonce": 1367162480,
			"isDeleted": false,
			"id": "IWIa5hi9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1139.8772546293883,
			"y": 559.1021028002364,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 362.7196044921875,
			"height": 25,
			"seed": 419356304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets take an example of Spam email",
			"rawText": "Lets take an example of Spam email",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets take an example of Spam email",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 459,
			"versionNonce": 2127569040,
			"isDeleted": false,
			"id": "J2cQsfTt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1259.1257722581322,
			"y": 595.4731818878191,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 580.9772338867188,
			"height": 100,
			"seed": 1032994448,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "GXxs65CxG6stNnxCSv46p",
					"type": "arrow"
				}
			],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can store all suspicious words that are marked as spam somewhere.\nOur input X will be encoding whether each word we have stores at index i\nhas occurred or not (1 or 0)\n\nQij represents the probability of the word in occurring in class j",
			"rawText": "We can store all suspicious words that are marked as spam somewhere.\nOur input X will be encoding whether each word we have stores at index i\nhas occurred or not (1 or 0)\n\nQij represents the probability of the word in occurring in class j",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can store all suspicious words that are marked as spam somewhere.\nOur input X will be encoding whether each word we have stores at index i\nhas occurred or not (1 or 0)\n\nQij represents the probability of the word in occurring in class j",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "image",
			"version": 203,
			"versionNonce": 774631536,
			"isDeleted": false,
			"id": "MVcVkyrextVLwkFafM6k9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1067.6436209835028,
			"y": 700.9354662967125,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 213.19248573467726,
			"height": 59.41429930310677,
			"seed": 50409616,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d8def8f2fc22b8ce4a33923948827a606c1fb95a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 219,
			"versionNonce": 253595280,
			"isDeleted": false,
			"id": "XCKSEeVZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1206.0330966543677,
			"y": 766.6128910344041,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 470.385009765625,
			"height": 20,
			"seed": 606213744,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Compositing this from a Bernoulli distribution over all words",
			"rawText": "Compositing this from a Bernoulli distribution over all words",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Compositing this from a Bernoulli distribution over all words",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 257,
			"versionNonce": 640967280,
			"isDeleted": false,
			"id": "ImvwVXHx24yrprR9eKcJC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1109.527433053877,
			"y": 790.837912254021,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 306.95568583211093,
			"height": 59.91627501227391,
			"seed": 580469360,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8fd194e8a469ce626b346968217d411f496ef747",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 168,
			"versionNonce": 1334656144,
			"isDeleted": false,
			"id": "pNtBypT29TRxAa9hTIww2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -967.1787236262326,
			"y": 832.3380760422168,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 25.907539051121375,
			"seed": 697233520,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					25.907539051121375
				]
			]
		},
		{
			"type": "text",
			"version": 266,
			"versionNonce": 677287024,
			"isDeleted": false,
			"id": "z8PvYBSb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1020.5500490048281,
			"y": 863.912889260771,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 107.55226135253906,
			"height": 60,
			"seed": 163852912,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "xi times\nits probability\nin class j",
			"rawText": "xi times\nits probability\nin class j",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "xi times\nits probability\nin class j",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 249,
			"versionNonce": 30878352,
			"isDeleted": false,
			"id": "MKyBzl-mZm2uwLu760zyr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -875.6927263519605,
			"y": 834.30183412256,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 25.907539051121375,
			"height": 25.907539051121375,
			"seed": 434136208,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					25.907539051121375,
					25.907539051121375
				]
			]
		},
		{
			"type": "text",
			"version": 352,
			"versionNonce": 175277680,
			"isDeleted": false,
			"id": "xTYsOdme",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -876.4235045672705,
			"y": 861.4237890667025,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 79.18417358398438,
			"height": 40,
			"seed": 1736790672,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "the exact\nopposite",
			"rawText": "the exact\nopposite",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the exact\nopposite",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 159,
			"versionNonce": 1890801808,
			"isDeleted": false,
			"id": "Cy1KrmkAxMJT7N16fo0ic",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1018.3523009478495,
			"y": 841.7352314820498,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 44.301698010423024,
			"height": 21.31811032080509,
			"seed": 1904698000,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-44.301698010423024,
					21.31811032080509
				]
			]
		},
		{
			"type": "text",
			"version": 168,
			"versionNonce": 691550320,
			"isDeleted": false,
			"id": "m1mLs5oK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1130.3031144522877,
			"y": 864.3857236979052,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 93.32820129394531,
			"height": 40,
			"seed": 838409328,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "samples are\ni.i.d",
			"rawText": "samples are\ni.i.d",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "samples are\ni.i.d",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 241,
			"versionNonce": 1339672208,
			"isDeleted": false,
			"id": "sCSq05MA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1124.3726407278282,
			"y": 945.4994095501454,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 355.0230923789427,
			"height": 46.253008514158026,
			"seed": 78648,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "eb12c15e924b4dfc299b706190ab2c0f6066f3cd",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 209,
			"versionNonce": 142060144,
			"isDeleted": false,
			"id": "0WyYS_-fPzmwwaKZiWN_-",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -766.744582318428,
			"y": 937.1039990256472,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 73.26592687511993,
			"height": 13.45700697706286,
			"seed": 1186815632,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					33.642517442657095,
					-13.45700697706286
				],
				[
					73.26592687511993,
					-2.242834496177238
				]
			]
		},
		{
			"type": "text",
			"version": 355,
			"versionNonce": 469922960,
			"isDeleted": false,
			"id": "abJPqkk0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -724.1718396961811,
			"y": 946.3633118459323,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 152.55657958984375,
			"height": 61.29203792002354,
			"seed": 983960208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 9.806726067203765,
			"fontFamily": 1,
			"text": "This is rewritten in this way to\nallow us to simplify\nit yeilds the same value but\nis easier to simplify than log\nof sum",
			"rawText": "This is rewritten in this way to\nallow us to simplify\nit yeilds the same value but\nis easier to simplify than log\nof sum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is rewritten in this way to\nallow us to simplify\nit yeilds the same value but\nis easier to simplify than log\nof sum",
			"lineHeight": 1.25,
			"baseline": 57
		},
		{
			"type": "image",
			"version": 73,
			"versionNonce": 1928911984,
			"isDeleted": false,
			"id": "ju6ZHeCa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1140.691074732484,
			"y": 1081.3045471376809,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 114.2836634858606,
			"height": 50.58457236259404,
			"seed": 43758,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d68824fc30e11a2cd7902de328c9cff1e7c2bfd6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 110,
			"versionNonce": 2061853328,
			"isDeleted": false,
			"id": "34Ji3k3YXDC9OhrRT6Zze",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1028.9962860363776,
			"y": 1072.3676180685543,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 184.85227453811476,
			"height": 50.92868788294999,
			"seed": 167030896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "RnDlfmrlY0SLJ3yBPFTwo",
					"type": "arrow"
				}
			],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e331ef28ed43e9c7d6f7b8e329f30f951d99b07d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 65,
			"versionNonce": 444845680,
			"isDeleted": false,
			"id": "UIkYIfuF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -838.6734079951891,
			"y": 1083.3922836815073,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 107.99031305523052,
			"height": 22.38823563340145,
			"seed": 29562,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9a3090f3bcd241da7b11eab2f5360d594ef7ad3e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 31,
			"versionNonce": 456822928,
			"isDeleted": false,
			"id": "RnDlfmrlY0SLJ3yBPFTwo",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -942.5570772488775,
			"y": 991.4662356912585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.5986928481556788,
			"height": 76.6326845639345,
			"seed": 896369264,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "34Ji3k3YXDC9OhrRT6Zze",
				"focus": -0.055664690236136107,
				"gap": 4.2686978133612
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
					0.5986928481556788,
					76.6326845639345
				]
			]
		},
		{
			"type": "line",
			"version": 50,
			"versionNonce": 937459824,
			"isDeleted": false,
			"id": "IQzJGMmbfckgOa-ZIoW5i",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1138.9036726630877,
			"y": 1070.6479227433329,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 111.5299610599784,
			"height": 42.66582402965628,
			"seed": 1557525616,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-74.8523228590459,
					-42.66582402965628
				],
				[
					-111.5299610599784,
					-12.724894886037873
				]
			]
		},
		{
			"type": "image",
			"version": 44,
			"versionNonce": 347733648,
			"isDeleted": false,
			"id": "bBNY3mX0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1360.0610616960744,
			"y": 1049.9785724410144,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 95,
			"height": 17,
			"seed": 32242,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f7e637fcffa09990960ab8289fd773de2a64ebdb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 74,
			"versionNonce": 718729840,
			"isDeleted": false,
			"id": "Kh3hlY3o",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1372.828309821803,
			"y": 1046.695179428438,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.256011962890625,
			"height": 20,
			"seed": 1181314704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "*",
			"rawText": "*",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "*",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 42,
			"versionNonce": 1209773200,
			"isDeleted": false,
			"id": "H4ia7uGX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1358.0610616960732,
			"y": 1074.6798389844996,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 91,
			"height": 17,
			"seed": 16413,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b597c9e83331f58a52f75c4f92d14f04871dcea5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 208,
			"versionNonce": 439297136,
			"isDeleted": false,
			"id": "PeklgbPJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1134.9417876090013,
			"y": 1133.4001920329129,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 496.93316998187026,
			"height": 47.93567556095211,
			"seed": 80552,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "leDdUkuZvDdZC0dJkHJKb",
					"type": "arrow"
				}
			],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e2265d7dc62e53ad037885dbd1bf99c09b1b8646",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 241,
			"versionNonce": 1058511504,
			"isDeleted": false,
			"id": "OwkmwvhL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1137.576610479853,
			"y": 1185.6270188879212,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 496.13478655239106,
			"height": 49.77941002197904,
			"seed": 16641,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "28dc934e8541dc18af31941fcf630225ce9fd5e8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 163,
			"versionNonce": 330372720,
			"isDeleted": false,
			"id": "leDdUkuZvDdZC0dJkHJKb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -681.6375546632271,
			"y": 1101.3178789761607,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 77.88046163493038,
			"height": 44.675613651045296,
			"seed": 2040619120,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "dTsI3WRF",
				"focus": 1.5088460942771982,
				"gap": 7.771327404703925
			},
			"endBinding": {
				"elementId": "PeklgbPJ",
				"focus": 0.6003142707998947,
				"gap": 8.895095229322123
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
					67.61714498536594,
					4.829796070383281
				],
				[
					77.88046163493038,
					38.63836856306625
				],
				[
					52.5240322654181,
					44.675613651045296
				]
			]
		},
		{
			"type": "text",
			"version": 31,
			"versionNonce": 207997072,
			"isDeleted": false,
			"id": "dTsI3WRF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -688.6139314949681,
			"y": 1073.5465515714568,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 120.20826721191406,
			"height": 20,
			"seed": 37059216,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "leDdUkuZvDdZC0dJkHJKb",
					"type": "arrow"
				}
			],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Logarithm rules",
			"rawText": "Logarithm rules",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Logarithm rules",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 29,
			"versionNonce": 740608112,
			"isDeleted": false,
			"id": "n4PyBofU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -967.750378058527,
			"y": 1237.7507536639723,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 130.30429077148438,
			"height": 20,
			"seed": 431057040,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Linear classifier!",
			"rawText": "Linear classifier!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Linear classifier!",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 272,
			"versionNonce": 525482608,
			"isDeleted": false,
			"id": "nuocvixd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -673.6031125329819,
			"y": 90.78728247643096,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 267.632568359375,
			"height": 80,
			"seed": 900404880,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What about cases where we want\nto evaluate the minimum cost\nfor our action, not necessarily\nthe \"correct\" action?",
			"rawText": "What about cases where we want\nto evaluate the minimum cost\nfor our action, not necessarily\nthe \"correct\" action?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What about cases where we want\nto evaluate the minimum cost\nfor our action, not necessarily\nthe \"correct\" action?",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 235,
			"versionNonce": 1641604240,
			"isDeleted": false,
			"id": "PUtKPQeU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1388.0242244168103,
			"y": 140.31139973502547,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 606.9771728515625,
			"height": 80,
			"seed": 614921328,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "m54yY_HJ8xsFNoAhiLdvN",
					"type": "arrow"
				}
			],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Let ak be an action with a specified cost\nlambda is a function that evaluates cost, the expected cost of action ak \ngiven our information is:\n",
			"rawText": "Let ak be an action with a specified cost\nlambda is a function that evaluates cost, the expected cost of action ak \ngiven our information is:\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Let ak be an action with a specified cost\nlambda is a function that evaluates cost, the expected cost of action ak \ngiven our information is:\n",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "image",
			"version": 143,
			"versionNonce": 1879141488,
			"isDeleted": false,
			"id": "uElotypVhqbvLb8bSfOlo",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1233.2370989998994,
			"y": 208.7288511548237,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 301.6825410329501,
			"height": 73.5351193767816,
			"seed": 70879344,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9cfd461052234b906c78e9d854e5869780b47a68",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 102,
			"versionNonce": 476959376,
			"isDeleted": false,
			"id": "SbE4ht2UnDXAT9dAwDO1D",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1051.662377838512,
			"y": 264.348579733003,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.3317308121618794,
			"height": 42.46154395671988,
			"seed": 336013424,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.3317308121618794,
					42.46154395671988
				]
			]
		},
		{
			"type": "text",
			"version": 123,
			"versionNonce": 133848688,
			"isDeleted": false,
			"id": "f6kTDLn3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1131.9670430084325,
			"y": 314.7716631816078,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 151.9843292236328,
			"height": 60,
			"seed": 1931245200,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "cost of this action\ngiven the truth is\nof class wj",
			"rawText": "cost of this action\ngiven the truth is\nof class wj",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "cost of this action\ngiven the truth is\nof class wj",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 78,
			"versionNonce": 1379205264,
			"isDeleted": false,
			"id": "AuycGHdpW4hJ7D8idgo3h",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -962.0950585548059,
			"y": 259.372617550575,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.73558400670919,
			"height": 36.158658525644114,
			"seed": 270008976,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433120,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					54.73558400670919,
					36.158658525644114
				]
			]
		},
		{
			"type": "text",
			"version": 139,
			"versionNonce": 1476726896,
			"isDeleted": false,
			"id": "jFTY7Kcy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -950.8057541643909,
			"y": 301.1706998829708,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 151.2483367919922,
			"height": 60,
			"seed": 1169031792,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433121,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "probability of class\nwj occurring given\nour evidence x",
			"rawText": "probability of class\nwj occurring given\nour evidence x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability of class\nwj occurring given\nour evidence x",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 127,
			"versionNonce": 1659268752,
			"isDeleted": false,
			"id": "ztwQHkhh5PHWYwvVZ_9RB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1192.0708768467362,
			"y": 266.39283450906566,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.937501674313097,
			"height": 44.45192882969104,
			"seed": 500193936,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433121,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.937501674313097,
					44.45192882969104
				]
			]
		},
		{
			"type": "text",
			"version": 131,
			"versionNonce": 2011791984,
			"isDeleted": false,
			"id": "SznVQfLW",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1323.5086219143357,
			"y": 315.43512480593165,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 174.1443634033203,
			"height": 40,
			"seed": 576868496,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433121,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "cost of our action ak\ngiven our evidence x",
			"rawText": "cost of our action ak\ngiven our evidence x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "cost of our action ak\ngiven our evidence x",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 200,
			"versionNonce": 2000297104,
			"isDeleted": false,
			"id": "NqbnpQgU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1350.4116332847454,
			"y": 379.67465726236617,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 545.7930908203125,
			"height": 40,
			"seed": 827575440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433121,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Therefore the action ak that we should take is the action with the\nlowest value given by lambda and our evidence x!",
			"rawText": "Therefore the action ak that we should take is the action with the\nlowest value given by lambda and our evidence x!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Therefore the action ak that we should take is the action with the\nlowest value given by lambda and our evidence x!",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 59,
			"versionNonce": 1181725808,
			"isDeleted": false,
			"id": "GXxs65CxG6stNnxCSv46p",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -612.4818245328469,
			"y": 678.074796287731,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 53.461449564530426,
			"height": 27.913500215108684,
			"seed": 543228048,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433121,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "J2cQsfTt",
				"focus": -0.7604244406528359,
				"gap": 12.205264274036153
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
					-53.461449564530426,
					-27.913500215108684
				]
			]
		},
		{
			"type": "arrow",
			"version": 64,
			"versionNonce": 137537168,
			"isDeleted": false,
			"id": "5Ihu4cISY-VnPE35Wa0NK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 811.1874923321161,
			"y": 147.86864846422662,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 49.37981901180899,
			"height": 4.957047468366909,
			"seed": 1319478928,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433121,
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
					49.37981901180899,
					-4.957047468366909
				]
			]
		},
		{
			"type": "arrow",
			"version": 278,
			"versionNonce": 1870265456,
			"isDeleted": false,
			"id": "m54yY_HJ8xsFNoAhiLdvN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -252.1480369910571,
			"y": 644.9873113042654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 636.1590039981604,
			"height": 558.9779483660307,
			"seed": 524218480,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433121,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "PUtKPQeU",
				"focus": 0.05625844948071162,
				"gap": 15.711508980725853
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
					-325.0959616020011,
					-90.04456490415146
				],
				[
					-344.97593047694363,
					-419.818166241433
				],
				[
					-516.8791907485054,
					-558.9779483660307
				],
				[
					-636.1590039981604,
					-520.3874205499658
				]
			]
		},
		{
			"type": "arrow",
			"version": 66,
			"versionNonce": 702606960,
			"isDeleted": false,
			"id": "ei5x94pSW7lRwYqop2vhQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 29.80640562855865,
			"y": 683.6994014581688,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 3.7830236331466267,
			"height": 306.4249142848795,
			"seed": 1853375120,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512433121,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "KGG7is4k",
				"focus": 0.002452810900074151,
				"gap": 6.686338624299879
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
					3.7830236331466267,
					306.4249142848795
				]
			]
		},
		{
			"type": "text",
			"version": 56,
			"versionNonce": 513384560,
			"isDeleted": false,
			"id": "DruDDMSS",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 36.96970095759946,
			"y": 756.5226063962419,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 360.1927490234375,
			"height": 80,
			"seed": 1911460464,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512433121,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "it is also important to determine what is the\nexpected error of the classifier\n(e.g. to determine whether the classifier\nis good enough for practical use)",
			"rawText": "it is also important to determine what is the\nexpected error of the classifier\n(e.g. to determine whether the classifier\nis good enough for practical use)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "it is also important to determine what is the\nexpected error of the classifier\n(e.g. to determine whether the classifier\nis good enough for practical use)",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 46,
			"versionNonce": 1772281488,
			"isDeleted": false,
			"id": "KGG7is4k",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -87.93108618018914,
			"y": 996.8106543673482,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 243.04103088378906,
			"height": 35,
			"seed": 1855484048,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ei5x94pSW7lRwYqop2vhQ",
					"type": "arrow"
				}
			],
			"updated": 1703512433121,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Bayes Error rate",
			"rawText": "Bayes Error rate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bayes Error rate",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 906142320,
			"isDeleted": false,
			"id": "8KXqtZZm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -331.30049215235067,
			"y": 1028.5718949775546,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 739.3191528320312,
			"height": 25,
			"seed": 1025524848,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512739740,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Our classifier's error over predicting datapoint x is usually evaluated as ",
			"rawText": "Our classifier's error over predicting datapoint x is usually evaluated as ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Our classifier's error over predicting datapoint x is usually evaluated as ",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 88,
			"versionNonce": 320102544,
			"isDeleted": false,
			"id": "fdszc8Ot6u1nuROFoxk5K",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -200.51815119372418,
			"y": 1055.500369215708,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 450.8096666842006,
			"height": 73.43505882638561,
			"seed": 1744952432,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512508440,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "512d9c0586df25cd1c43616fc6d0ad5d63ea18b3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 149,
			"versionNonce": 409970832,
			"isDeleted": false,
			"id": "4MiwYKGJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -403.64664804397944,
			"y": 1127.9830113710432,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 870.5390625,
			"height": 50,
			"seed": 460362864,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512575380,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "which if you recall we only decide w2 if it has a bigger posterior than w1 and vice verse\nmeaning",
			"rawText": "which if you recall we only decide w2 if it has a bigger posterior than w1 and vice verse\nmeaning",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "which if you recall we only decide w2 if it has a bigger posterior than w1 and vice verse\nmeaning",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 80,
			"versionNonce": 178465904,
			"isDeleted": false,
			"id": "olPjtwXsHpQt2c_XAFDMP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -151.54422659034083,
			"y": 1186.8473823616334,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 377.280546311395,
			"height": 52.54979037908717,
			"seed": 485147792,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512580482,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c85c6b1d40640bac98367b568fdb7221078673e9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 390,
			"versionNonce": 1115026032,
			"isDeleted": false,
			"id": "rcFxcZhg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -332.7827893412697,
			"y": 1243.6108367384413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 732.5392456054688,
			"height": 125,
			"seed": 772497520,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512823944,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "To evaluate the total error over all values of x we need to use our\npdf of x that measures the probability distribution at each point in x!\nas we know from pdfs this is not a SUM since its continuous values, it is\ninstead an integral.\nand obviously we multiply each probability of x with its own error",
			"rawText": "To evaluate the total error over all values of x we need to use our\npdf of x that measures the probability distribution at each point in x!\nas we know from pdfs this is not a SUM since its continuous values, it is\ninstead an integral.\nand obviously we multiply each probability of x with its own error",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "To evaluate the total error over all values of x we need to use our\npdf of x that measures the probability distribution at each point in x!\nas we know from pdfs this is not a SUM since its continuous values, it is\ninstead an integral.\nand obviously we multiply each probability of x with its own error",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 113,
			"versionNonce": 1608747664,
			"isDeleted": false,
			"id": "6pvj1u1isGefBKJk1n9Vj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -126.46320102445917,
			"y": 1376.6166289174794,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 494.62130826705294,
			"height": 94.3800376198617,
			"seed": 32950416,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512850233,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2c12da7a8d363ac86ece2272ae41c8523b090203",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 79,
			"versionNonce": 238270608,
			"isDeleted": false,
			"id": "AmqbvGNOEIdoh3QufOCOx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -228.60525954917296,
			"y": 1383.9151328926155,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 104.866708466513,
			"height": 77.7761421126638,
			"seed": 11669136,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703512850233,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9381915d791628f8c297907945fcd2f5a516f4e4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 185,
			"versionNonce": 1907011184,
			"isDeleted": false,
			"id": "OcUzYnfr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -339.65390841367696,
			"y": 1460.0485529053599,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 707.6593017578125,
			"height": 75,
			"seed": 1069662864,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "qs8Mbd3CPjZnKEp9IK23h",
					"type": "arrow"
				}
			],
			"updated": 1703513523623,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "due to the minimum inside the integral this is hard to solve analytically\ninstead we can:\n",
			"rawText": "due to the minimum inside the integral this is hard to solve analytically\ninstead we can:\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "due to the minimum inside the integral this is hard to solve analytically\ninstead we can:\n",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 209,
			"versionNonce": 28592272,
			"isDeleted": false,
			"id": "yXCv3yuv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -340.7355548695649,
			"y": 1524.5957069661233,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 772.0753173828125,
			"height": 35,
			"seed": 2001039504,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "CVXrBxYNeUMFRDpk-hq94",
					"type": "arrow"
				}
			],
			"updated": 1703512983800,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Upper bound it          or      evaluate it Empirically ",
			"rawText": "Upper bound it          or      evaluate it Empirically ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Upper bound it          or      evaluate it Empirically ",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "arrow",
			"version": 207,
			"versionNonce": 163319408,
			"isDeleted": false,
			"id": "CVXrBxYNeUMFRDpk-hq94",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -263.33505463835843,
			"y": 1573.305363330477,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.3124890836073746,
			"height": 259.8728385542688,
			"seed": 1306089104,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703512988835,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "yXCv3yuv",
				"focus": 0.798908905268433,
				"gap": 13.709656364353577
			},
			"endBinding": {
				"elementId": "DHStJkjMuRw5Y48vdROzT",
				"focus": 0.01685448515648679,
				"gap": 7.060960788645843
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
					-1.3124890836073746,
					259.8728385542688
				]
			]
		},
		{
			"type": "image",
			"version": 90,
			"versionNonce": 506711184,
			"isDeleted": false,
			"id": "DHStJkjMuRw5Y48vdROzT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -521.8984606989427,
			"y": 1840.2391626733915,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 504.66922612816387,
			"height": 244.43842789336918,
			"seed": 1962654320,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "CVXrBxYNeUMFRDpk-hq94",
					"type": "arrow"
				},
				{
					"id": "esp0sPuaaUp3_3alSU8as",
					"type": "arrow"
				}
			],
			"updated": 1703513165330,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "11fa70d59a27a2af07cbaa55cd5e9b9e4a1b9347",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 305,
			"versionNonce": 1866388881,
			"isDeleted": false,
			"id": "J2YZO4UR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -567.9103462163926,
			"y": 2084.9261496029403,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 670.8792724609375,
			"height": 75,
			"seed": 823876240,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703872172916,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "a very basic bound dictating that only works in binary classification\nrelying on the assumption that the probability of another class\nis 1 -  the first, and the minimum of both cant be above 0.5",
			"rawText": "a very basic bound dictating that only works in binary classification\nrelying on the assumption that the probability of another class\nis 1 -  the first, and the minimum of both cant be above 0.5",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a very basic bound dictating that only works in binary classification\nrelying on the assumption that the probability of another class\nis 1 -  the first, and the minimum of both cant be above 0.5",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 228,
			"versionNonce": 1522470544,
			"isDeleted": false,
			"id": "IKlyPMFB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -573.1327322150605,
			"y": 2163.384265604859,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 575.1051025390625,
			"height": 60,
			"seed": 1577752208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703513108403,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This doesnt help much as it says that the classifier is correct at\nleast 50% of the time, which is shit... and it also doesnt depend on our\ndistributions.. so its very general",
			"rawText": "This doesnt help much as it says that the classifier is correct at\nleast 50% of the time, which is shit... and it also doesnt depend on our\ndistributions.. so its very general",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This doesnt help much as it says that the classifier is correct at\nleast 50% of the time, which is shit... and it also doesnt depend on our\ndistributions.. so its very general",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 58,
			"versionNonce": 616296048,
			"isDeleted": false,
			"id": "esp0sPuaaUp3_3alSU8as",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4.706436907974307,
			"y": 1914.541701179413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 367.49694341007717,
			"height": 0,
			"seed": 268351600,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703513432830,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "DHStJkjMuRw5Y48vdROzT",
				"focus": -0.392055176050845,
				"gap": 12.522797662804493
			},
			"endBinding": {
				"elementId": "AhWepWY0zPo_Jkejs0KM5",
				"focus": 0.2205993058430142,
				"gap": 10.328146444503261
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
					367.49694341007717,
					0
				]
			]
		},
		{
			"type": "image",
			"version": 192,
			"versionNonce": 102015088,
			"isDeleted": false,
			"id": "AhWepWY0zPo_Jkejs0KM5",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 373.1186529466062,
			"y": 1875.1265905512885,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 475.2529255932117,
			"height": 101.14209782878508,
			"seed": 440239728,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "esp0sPuaaUp3_3alSU8as",
					"type": "arrow"
				}
			],
			"updated": 1703513432830,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dd3826e0353b3edaa9d86094153720d823fe2d75",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 218,
			"versionNonce": 1013109392,
			"isDeleted": false,
			"id": "436d4kbem6Q4P0ppS0M7c",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 445.8028682169012,
			"y": 1975.7559488847974,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 419.9673175300133,
			"height": 88.81029295437558,
			"seed": 343298704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703513432212,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d73d9f78a29a11c8442037f608ca38723f12d5e7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 281,
			"versionNonce": 730464400,
			"isDeleted": false,
			"id": "tlds3PMW84pJGhLnrgyVF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 448.619691957682,
			"y": 2070.4835035444157,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 333.4241152005483,
			"height": 68.47102365725544,
			"seed": 1532693104,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703513432212,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7680b80df86f0a0ebc914350bc8c4804fdc43a58",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 342,
			"versionNonce": 1569133168,
			"isDeleted": false,
			"id": "aPue6DVm7kbAA9Xk7GD7l",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 783.1166864728925,
			"y": 2002.410429099283,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 155.39608822435014,
			"height": 56.654823831794374,
			"seed": 1514723952,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703513432831,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "M4SxKv-KwCim0LZxsotLr",
				"focus": 0.990875643835255,
				"gap": 11.633702087304528
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
					126.25932168228451,
					-44.78428931465646
				],
				[
					155.39608822435014,
					-56.654823831794374
				]
			]
		},
		{
			"type": "text",
			"version": 187,
			"versionNonce": 1062149264,
			"isDeleted": false,
			"id": "ItspGkj9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 960.0955647284025,
			"y": 1924.712384987108,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 123.26426696777344,
			"height": 20,
			"seed": 1730648688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703513432212,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is because",
			"rawText": "This is because",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is because",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 264,
			"versionNonce": 1583155856,
			"isDeleted": false,
			"id": "M4SxKv-KwCim0LZxsotLr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 950.1464767845471,
			"y": 1940.6129252880576,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 152.09276482856438,
			"height": 26.376447954503284,
			"seed": 2072728208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "aPue6DVm7kbAA9Xk7GD7l",
					"type": "arrow"
				}
			],
			"updated": 1703513432212,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "eb6c7d68cb703d2c09c29940477870e951458d2a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 233,
			"versionNonce": 1818732176,
			"isDeleted": false,
			"id": "6uKhU7bF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 954.1602974698335,
			"y": 1962.0921908921594,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 150.44456481933594,
			"height": 13.91523964013011,
			"seed": 1680205936,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703513432212,
			"link": null,
			"locked": false,
			"fontSize": 11.132191712104088,
			"fontFamily": 1,
			"text": "According to bayes theorem",
			"rawText": "According to bayes theorem",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "According to bayes theorem",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 233,
			"versionNonce": 735335568,
			"isDeleted": false,
			"id": "uRJ0p5DM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 456.8646883250141,
			"y": 2137.7718615588897,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 481.2969970703125,
			"height": 40,
			"seed": 125358704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703513432212,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This tells us that the classifier is accurate when one class\nis highly dominant over the other!",
			"rawText": "This tells us that the classifier is accurate when one class\nis highly dominant over the other!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This tells us that the classifier is accurate when one class\nis highly dominant over the other!",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 545,
			"versionNonce": 1973159024,
			"isDeleted": false,
			"id": "qs8Mbd3CPjZnKEp9IK23h",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 381.6740111053871,
			"y": 1488.472805447128,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 248.92799091632787,
			"height": 176.96866309522716,
			"seed": 1596907664,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703513690261,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "OcUzYnfr",
				"focus": 0.9306340560814395,
				"gap": 13.66861776125154
			},
			"endBinding": {
				"elementId": "pfKQwX8d",
				"focus": 0.8319895573173417,
				"gap": 22.390160302412824
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
					148.48211568968395,
					-170.87227599209655
				],
				[
					248.92799091632787,
					-176.96866309522716
				]
			]
		},
		{
			"type": "text",
			"version": 140,
			"versionNonce": 752183440,
			"isDeleted": false,
			"id": "MzcWvPcD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.547095392652782,
			"x": 416.2586581822326,
			"y": 1314.9446851213984,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 133.23983764648438,
			"height": 50,
			"seed": 940231824,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703513599212,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Whys it hard?\n",
			"rawText": "Whys it hard?\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Whys it hard?\n",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 668,
			"versionNonce": 710922864,
			"isDeleted": false,
			"id": "pfKQwX8d",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 652.9921623241278,
			"y": 1282.3971374442272,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 499.45703125,
			"height": 300,
			"seed": 417364592,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "qs8Mbd3CPjZnKEp9IK23h",
					"type": "arrow"
				}
			],
			"updated": 1703513690260,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Why is the sky blue? \nwhy do you ask so many questions?\nwhy are you adopted?\nthe world will never know!\n\nJK the last one is obvious\n\nanyway a pdf from its definition is infinitely\ncontinuous meaning you can go to very very small values\ninfinitely between each 2 values which is the mean reason we\nuse areas instead of sums.\n\na minimum function on the other hand has discontinuities and is\nnot not something you can calculate on continuous values with\ninfinitely small differences",
			"rawText": "Why is the sky blue? \nwhy do you ask so many questions?\nwhy are you adopted?\nthe world will never know!\n\nJK the last one is obvious\n\nanyway a pdf from its definition is infinitely\ncontinuous meaning you can go to very very small values\ninfinitely between each 2 values which is the mean reason we\nuse areas instead of sums.\n\na minimum function on the other hand has discontinuities and is\nnot not something you can calculate on continuous values with\ninfinitely small differences",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Why is the sky blue? \nwhy do you ask so many questions?\nwhy are you adopted?\nthe world will never know!\n\nJK the last one is obvious\n\nanyway a pdf from its definition is infinitely\ncontinuous meaning you can go to very very small values\ninfinitely between each 2 values which is the mean reason we\nuse areas instead of sums.\n\na minimum function on the other hand has discontinuities and is\nnot not something you can calculate on continuous values with\ninfinitely small differences",
			"lineHeight": 1.25,
			"baseline": 294
		},
		{
			"type": "text",
			"version": 243,
			"versionNonce": 184010864,
			"isDeleted": false,
			"id": "cQG28fLK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1227.0933258399662,
			"y": 1881.8745174290798,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 824.1390991210938,
			"height": 25,
			"seed": 243469968,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703514326826,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can also upper bound our error with the harmonic mean of the class posteriors!",
			"rawText": "We can also upper bound our error with the harmonic mean of the class posteriors!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can also upper bound our error with the harmonic mean of the class posteriors!",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 321,
			"versionNonce": 1479770224,
			"isDeleted": false,
			"id": "3rfFB1pg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1938.6412683605013,
			"y": 1759.7547497690502,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 614.7212524414062,
			"height": 60,
			"seed": 1777432688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703514322478,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The harmonic mean is the lowest of the three pythagorean means followed up\nby the geometric and the arithmetic, it represents an average rate of sorts\nand is calculated by the inverse of numbers divided by their count",
			"rawText": "The harmonic mean is the lowest of the three pythagorean means followed up\nby the geometric and the arithmetic, it represents an average rate of sorts\nand is calculated by the inverse of numbers divided by their count",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The harmonic mean is the lowest of the three pythagorean means followed up\nby the geometric and the arithmetic, it represents an average rate of sorts\nand is calculated by the inverse of numbers divided by their count",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 280,
			"versionNonce": 1221194352,
			"isDeleted": false,
			"id": "llnXDBfGaVojCqLghTqeE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1725.3417581216736,
			"y": 1863.8955948871135,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 193.97543167557865,
			"height": 75.23921745278403,
			"seed": 1653794416,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703514322478,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					96.31002432605317,
					-62.16469834747613
				],
				[
					193.97543167557865,
					-75.23921745278403
				]
			]
		},
		{
			"type": "image",
			"version": 111,
			"versionNonce": 286749808,
			"isDeleted": false,
			"id": "_tnMUFUW9_ZjkAXtG48kJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1396.8981134440558,
			"y": 1925.6584698266183,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 411.0804210163957,
			"height": 78.53975523483983,
			"seed": 1791182448,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703514315682,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b5adbee82d429a32d9810a2f43e8f29d11d6ce15",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 405,
			"versionNonce": 688875120,
			"isDeleted": false,
			"id": "QwKhRXpm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1338.546791245246,
			"y": 2014.4986526780322,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 648.193359375,
			"height": 80,
			"seed": 1921850512,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1703514315682,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This can be easily proven given two cases of which the first posterior\nis minimal and then the other case of the other posterior is minimal\nthe harmonic mean can be expressed as the posterior itself plus a bigger\nvalue incoming from the bigger posterior in each case and thus it upper bounds it!",
			"rawText": "This can be easily proven given two cases of which the first posterior\nis minimal and then the other case of the other posterior is minimal\nthe harmonic mean can be expressed as the posterior itself plus a bigger\nvalue incoming from the bigger posterior in each case and thus it upper bounds it!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This can be easily proven given two cases of which the first posterior\nis minimal and then the other case of the other posterior is minimal\nthe harmonic mean can be expressed as the posterior itself plus a bigger\nvalue incoming from the bigger posterior in each case and thus it upper bounds it!",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 54,
			"versionNonce": 514832496,
			"isDeleted": false,
			"id": "7Zj6F2SzprEH6nQsm-1AP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 931.6085740085115,
			"y": 2055.5163061927033,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 333.22774170707623,
			"height": 0,
			"seed": 1242948752,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1703514330925,
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
					333.22774170707623,
					0
				]
			]
		},
		{
			"id": "LpP6R7Ws3rWAOIiPWmvMh",
			"type": "arrow",
			"x": -749.9718658255968,
			"y": 1798.6463026703398,
			"width": 133.34380946939086,
			"height": 307.4315607210956,
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
			"seed": 361974463,
			"version": 23,
			"versionNonce": 983970833,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1703872167472,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					133.34380946939086,
					-307.4315607210956
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "z8FyfHNAahW1DOLzPZLHW",
			"type": "arrow",
			"x": -659.8413279435085,
			"y": 1662.8331633959601,
			"width": 246.93298049887204,
			"height": 285.2075924761971,
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
			"seed": 684165617,
			"version": 113,
			"versionNonce": 1622691967,
			"isDeleted": true,
			"boundElements": [],
			"updated": 1703872178514,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					151.86378300680627,
					-53.090590807257286
				],
				[
					-93.83453258957138,
					232.1170016689398
				],
				[
					153.09844790930066,
					117.29316573696428
				],
				[
					40.74394178231387,
					141.98646378685135
				]
			],
			"lastCommittedPoint": [
				40.74394178231387,
				141.98646378685135
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "7PDGWZYz",
			"type": "text",
			"x": -757.6758681624744,
			"y": 1884.9501650649,
			"width": 8.000015258789062,
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
			"seed": 1681298481,
			"version": 2,
			"versionNonce": 1102474175,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1703872172843,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "z8FyfHNAahW1DOLzPZLHW",
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 730.8345598369342,
		"scrollY": -238.029865917469,
		"zoom": {
			"value": 0.8099363624735159
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