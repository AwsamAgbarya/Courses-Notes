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

%%***>>>text element-link:[[Bayes Theorem]]<<<***%%Want more detail about
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

Qij represents the probability of the word occurring in class j ^J2cQsfTt

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
is highly dominant over the other!
(While the result we got is in binary classification, it does apply
to more classes) ^uRJ0p5DM

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
by the geometric and the arithmetic, it represents an average rate or average density
and is calculated by the inverse of sum of inverse numbers divided by their count ^3rfFB1pg

This can be easily proven given two cases of which the first posterior
is minimal and then the other case of the other posterior is minimal
the harmonic mean can be expressed as the posterior itself plus a bigger
value incoming from the bigger posterior in each case and thus it upper bounds it! ^QwKhRXpm

Case 1: Posterior of class 1 is smaller than Posterior of class 2 ^AAwgWkki

Case 2: Posterior of class 2 is smaller than Posterior of class 1 ^kH9I8Elm

For example:
A car is heading from city A to city B
The car travels half the distance going 30KM/h
and the other half going 50KM/h, what is the
average speed that this car is travelling at?

The answer here is 37.5 not 40, because its travelling
half the DISTANCE not half the TIME at that speed
and in this case we want the average of two rates
which the harmonic mean helps us with. ^D4XTGR0H

- likelihood ^voLsalew

- evidence ^jj7irAWb

Integrate Numerically  ^6MHInLsD

Discretize The entire distribution and numerically
integrate over the entire space ^YSo5zePC

Problem:
if input is high dimensional this is
very hard to compute ^xdfSgO8W

Sampling ^GaEWzQYe

Sample points and approximate the error
The integral is replaced by an expectation
over x of P(Err|x)
(Monte carlo) ^Hx3bkiDU

In Some cases it is sometimes irrelevant to rely on the data generating distributions (The likelihood)
because it doesn't contribute much to the accuracy of the classifier, and instead we only want to take the
information provided by The prior distribution
Lets take an example ^J3iAoIFr

If we were to rely solely on the prior, for the prediction, one class is going to be clearly superior
to the other and will be picked all the time ^lunPVeD4

Lets find out for which values this situation is the optimal solution ^coYqP2SM

Lets determine when is it optimal to predict only the first class ^IA7gUC0l

Case 1:          (Mu is positive, which means x is negative) ^hPh9HnEr

Case 2:          (Mu is positive, which means x is positive) ^FdYPvx7O

Case 3:          (Mu is positive, which means x can be positive or negative) ^OLbg6ZZq

2x ^2bnUTnDG

When this condition applies
There is no point in counting
on the Likelihood of the data
we can just predict based off
of the prior (which says just predict
the first class at all times) ^9Whca9sh

This process can be repeated for a
gaussian distribution generating function
and the condition will be as follows ^MX5AQC69


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
b597c9e83331f58a52f75c4f92d14f04871dcea5: $$log(1 - q_{ij}) = b_{ij}$$
e2265d7dc62e53ad037885dbd1bf99c09b1b8646: $$\arg\max_j [ x^T * a_j + (1-x)^T * b_j + log P(w_j) ]$$
28dc934e8541dc18af31941fcf630225ce9fd5e8: $$\arg\max_j [ x^T *(a_j - b_j) + 1^Tb_j + logP(w_j) ]$$
0bdc3abd982dd81d14ea48ddc021fb95d6e2609a: $$P(Err) = \int_x P(Err|x) p(x) dx = \int_x min \{ P(w_1|x) , P(w_2,x) \} p(x) dx $$
f75eaed08d20f245476983ea9425da048f819012: $$P(Err) = \int_x P(w_1|x) p(x) dx = \int_x \frac{2}{\frac{2}{P(w_1|x)}} p(x) dx  \leq \int_x \frac{2}{\frac{1}{P(w_1|x)} + \frac{1}{P(w_2|x)}} p(x) dx $$
20af2050539e0e20c222144b7c6541f8600b08ac: $$P(Err) = \int_x P(w_2|x) p(x) dx = \int_x \frac{2}{\frac{2}{P(w_2|x)}} p(x) dx  \leq \int_x \frac{2}{\frac{1}{P(w_1|x)} + \frac{1}{P(w_2|x)}} p(x) dx $$
adeb68f9a1d709262cae779cb3de8000f1717065: $$\arg\max_j{\log(P(x|w_j)) + \log(P(w_j))}$$
c08c02d01647a7c9c2428206b200cc3f616c83d8: $$log ( p(w_j | x) ) = log( p(x | w_j ) ) + log ( P(W_j))$$
08504741981d5f37449f17deb7f0009797e9e841: $$log ( p(w_1 |x))= log  \left[ \frac{1}{2\sigma}exp \left( - \frac{ | x - \mu |}{\sigma} \right) \right] + log(P(w_1 ))$$
2d8be629d1312867a5fae084b5e049f5cba1da33: $$log ( p(w_2 |x))= log  \left[ \frac{1}{2\sigma}exp \left( - \frac{ | x + \mu |}{\sigma} \right) \right] + log(P(w_2 ))$$
fd14bae1f6b5e21cd06720b3ec8fc60213754f31: $$P(Err|x) = min[ P(w_1 |x) , P(w_2 | x) ] = P(w_2 | x)$$
c0d2b9b8d323b61a51920c47775f61cabbf6cd3e: $$log[p(w_1 | x)] > log[p(w_2 | x)]$$
3351dc8934ead97a89dfcc805115a7f069ee7d2d: $$log  \left[ \frac{1}{2\sigma}exp \left( - \frac{ | x - \mu |}{\sigma} \right) \right] + log(P(w_1 )) > log  \left[ \frac{1}{2\sigma}exp \left( - \frac{ | x + \mu |}{\sigma} \right) \right] + log(P(w_2 ))$$
8d3f49ca811440b9abdad830a8eb03f9054ffb70: $$ - \frac{ | x - \mu |}{\sigma}+ log(P(w_1 )) > - \frac{ | x + \mu |}{\sigma} + log(P(w_2 ))$$
0cc29adc172637425c1ed66f346e9ff85bfaeeae: $$\color{red} x \leq -\mu$$
b2af080f2ed30c3195601f1e586ce3199310ceb4: $$ - \frac{ \mu - x}{\sigma}+ log(P(w_1 )) > - \frac{ -x -\mu}{\sigma} + log(P(w_2 ))$$
7d0e4d7f75206dfa20144b52d551b444ae1e9ac8: $$2\mu< \sigma log\left[\frac{P(w_1)}{P(w_2)} \right]$$
c274eb79b7fa8ba0b4113aaf4e8e5bd595ff18ff: $$\color{red} x \geq \mu$$
f14869448a74e9f1521539120ad3a376dc8f6a35: $$ - \frac{ x - \mu }{\sigma}+ log(P(w_1 )) > - \frac{ x +\mu}{\sigma} + log(P(w_2 ))$$
c29317a9601381e8711267fb4076bf774ceeb34b: $$- 2\mu < \sigma log\left[\frac{P(w_1)}{P(w_2)} \right]$$
70c16634fd207f3abc9774454fb167388d5685b8: $$\color{red} - \mu < x < \mu$$
7c163eba48a876b7b8c2b82c68093a9ef28c49b5: $$ - \frac{  \mu -x }{\sigma}+ log(P(w_1 )) > - \frac{ x +\mu}{\sigma} + log(P(w_2 ))$$
ac48a6a8b9feb49b0512700c92c5c0a626a52df9: $$2x< \sigma log\left[\frac{P(w_1)}{P(w_2)} \right]$$
72304a5565ea3b64183c13716c703484b3e9a449: $$\color{red} - \mu < x < \mu$$
5d55109809275302dfd8ad5906f394b3d0204f7c: $$2 \mu$$
3e6b910f2f2c886e827a770350fa31f51149eda4: $$- 2 \mu$$
7352f13eb067e4fa25b3fb09c94edfa5078caef9: $$\frac{2\mu}{\sigma} <  log\left[\frac{P(w_1)}{P(w_2)} \right]$$
65a66788291094f7459915e01b051e637ba43eb4: $$\frac{-2x\mu}{\sigma^2} <  log\left[\frac{P(w_1)}{P(w_2)} \right]$$
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
4ec8994b9c46da2d5fd1c835887ebb7ad5937220: [[Pasted Image 20240222203711_269.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.22",
	"elements": [
		{
			"type": "ellipse",
			"version": 95,
			"versionNonce": 1635998540,
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
			"updated": 1708633450402,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 74,
			"versionNonce": 1869336436,
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
			"updated": 1708633450402,
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
			"version": 82,
			"versionNonce": 1771180492,
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
			"updated": 1708633450402,
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
			"version": 298,
			"versionNonce": 1034535156,
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
			"updated": 1708633450402,
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
			"version": 331,
			"versionNonce": 461764684,
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
			"updated": 1708633450402,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 158,
			"versionNonce": 1110278772,
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
			"updated": 1708633450402,
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
			"version": 187,
			"versionNonce": 1664683724,
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
			"updated": 1708633450402,
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
			"version": 162,
			"versionNonce": 1404900340,
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
			"updated": 1708633450402,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 198,
			"versionNonce": 558191948,
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
			"updated": 1708633450402,
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
			"version": 263,
			"versionNonce": 6190452,
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
			"updated": 1708633450403,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 196,
			"versionNonce": 319081420,
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
			"updated": 1708633450403,
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
			"version": 188,
			"versionNonce": 626501364,
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
			"updated": 1708633450403,
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
			"version": 174,
			"versionNonce": 982610508,
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
			"updated": 1708633450403,
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
			"version": 348,
			"versionNonce": 120498292,
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
			"updated": 1708633450403,
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
			"version": 204,
			"versionNonce": 1187334348,
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
			"updated": 1708633450403,
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
			"version": 166,
			"versionNonce": 1772714484,
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
			"updated": 1708633450403,
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
			"version": 272,
			"versionNonce": 2067418956,
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
			"updated": 1708633450403,
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
			"version": 251,
			"versionNonce": 667818868,
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
			"updated": 1708633450403,
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
			"version": 92,
			"versionNonce": 407537100,
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
			"updated": 1708633450403,
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
			"version": 279,
			"versionNonce": 1273138420,
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
			"updated": 1708633450403,
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
			"version": 195,
			"versionNonce": 1125117004,
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
			"updated": 1708633450403,
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
			"version": 111,
			"versionNonce": 661442164,
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
			"updated": 1708633450403,
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
			"version": 326,
			"versionNonce": 1835303628,
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
			"updated": 1708633450403,
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
			"version": 278,
			"versionNonce": 1798496244,
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
			"updated": 1708633450403,
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
			"version": 82,
			"versionNonce": 1038240076,
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
			"updated": 1708633450403,
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
			"version": 82,
			"versionNonce": 1060815220,
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
			"updated": 1708633450403,
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
			"version": 346,
			"versionNonce": 2011381708,
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
			"updated": 1708633450403,
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
			"version": 297,
			"versionNonce": 1523217140,
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
			"updated": 1708633450403,
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
			"version": 89,
			"versionNonce": 1669424716,
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
			"updated": 1708633450403,
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
			"version": 366,
			"versionNonce": 476574836,
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
			"updated": 1708633450403,
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
			"version": 167,
			"versionNonce": 899071180,
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
			"updated": 1708633450403,
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
			"version": 103,
			"versionNonce": 567887348,
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
			"updated": 1708633450403,
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
			"version": 154,
			"versionNonce": 2008892236,
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
			"updated": 1708633450403,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 88,
			"versionNonce": 1612998516,
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
			"updated": 1708633450403,
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
			"version": 57,
			"versionNonce": 1884223948,
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
			"updated": 1708633450403,
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
			"version": 55,
			"versionNonce": 999250164,
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
			"updated": 1708633450403,
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
			"version": 114,
			"versionNonce": 174448716,
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
			"updated": 1708633450403,
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
			"version": 119,
			"versionNonce": 530586228,
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
			"updated": 1708633450404,
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
			"version": 81,
			"versionNonce": 1037825740,
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
			"updated": 1708633450404,
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
			"version": 310,
			"versionNonce": 387754996,
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
			"updated": 1708633450404,
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
			"version": 123,
			"versionNonce": 2001419596,
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
			"updated": 1708633450404,
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
			"version": 82,
			"versionNonce": 1678445940,
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
			"updated": 1708633450404,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 77,
			"versionNonce": 897996,
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
			"updated": 1708633450404,
			"link": "[[Bayes Theorem]]",
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
			"version": 128,
			"versionNonce": 397491956,
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
			"updated": 1708633450404,
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
			"version": 134,
			"versionNonce": 1715296844,
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
			"updated": 1708633450404,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 113,
			"versionNonce": 714424436,
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
			"updated": 1708633450404,
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
			"version": 140,
			"versionNonce": 1689530572,
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
			"updated": 1708633450404,
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
			"version": 354,
			"versionNonce": 343740916,
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
			"updated": 1708633450404,
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
			"version": 142,
			"versionNonce": 1259091788,
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
			"updated": 1708633450404,
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
			"version": 102,
			"versionNonce": 1684976500,
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
			"updated": 1708633450404,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 186,
			"versionNonce": 1704947148,
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
			"updated": 1708633450404,
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
			"version": 60,
			"versionNonce": 1487938804,
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
			"updated": 1708633450404,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 24,
			"versionNonce": 1703400524,
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
			"updated": 1708633450404,
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
			"version": 106,
			"versionNonce": 1992779380,
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
			"updated": 1708633450404,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 165,
			"versionNonce": 1218407116,
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
			"updated": 1708633450404,
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
			"version": 178,
			"versionNonce": 595228660,
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
			"updated": 1708633450404,
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
			"version": 82,
			"versionNonce": 1098920268,
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
			"updated": 1708633450404,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 241,
			"versionNonce": 986667380,
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
			"updated": 1708633450404,
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
			"version": 56,
			"versionNonce": 528754636,
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
			"updated": 1708633450404,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 74,
			"versionNonce": 671877876,
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
			"updated": 1708633450404,
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
			"version": 291,
			"versionNonce": 918900300,
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
			"updated": 1708633450404,
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
			"version": 170,
			"versionNonce": 2109115508,
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
			"updated": 1708633450404,
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
			"version": 100,
			"versionNonce": 1209902284,
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
			"updated": 1708633450404,
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
			"version": 89,
			"versionNonce": 227859956,
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
			"updated": 1708633450404,
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
			"version": 45,
			"versionNonce": 1764174668,
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
			"updated": 1708633450404,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 32,
			"versionNonce": 11337588,
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
			"updated": 1708633450404,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 28,
			"versionNonce": 1815863756,
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
			"updated": 1708633450404,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 105,
			"versionNonce": 1866789108,
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
			"updated": 1708633450404,
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
			"version": 52,
			"versionNonce": 1215678540,
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
			"updated": 1708633450404,
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
			"version": 103,
			"versionNonce": 2028122740,
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
			"updated": 1708633450404,
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
			"version": 30,
			"versionNonce": 28237516,
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
			"updated": 1708633450404,
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
			"version": 183,
			"versionNonce": 1548502004,
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
			"updated": 1708633450405,
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
			"version": 133,
			"versionNonce": 276899148,
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
			"updated": 1708633450405,
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
			"version": 65,
			"versionNonce": 260547956,
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
			"updated": 1708633450405,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 39,
			"versionNonce": 1246141388,
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
			"updated": 1708633450405,
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
			"version": 67,
			"versionNonce": 1473959668,
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
			"updated": 1708633450405,
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
			"version": 100,
			"versionNonce": 1226392140,
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
			"updated": 1708633450405,
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
			"version": 67,
			"versionNonce": 1640749172,
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
			"updated": 1708633450405,
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
			"version": 188,
			"versionNonce": 1406343372,
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
			"updated": 1708633450405,
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
			"version": 48,
			"versionNonce": 1495312884,
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
			"updated": 1708633450405,
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
			"version": 71,
			"versionNonce": 1175330636,
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
			"updated": 1708633450405,
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
			"version": 68,
			"versionNonce": 14633844,
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
			"updated": 1708633450405,
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
			"version": 94,
			"versionNonce": 2015647180,
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
			"updated": 1708633450405,
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
			"version": 121,
			"versionNonce": 1263385844,
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
			"updated": 1708633450405,
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
			"version": 27,
			"versionNonce": 657439820,
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
			"updated": 1708633450405,
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
			"version": 57,
			"versionNonce": 1911684724,
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
			"updated": 1708633450405,
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
			"version": 211,
			"versionNonce": 1560957644,
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
			"updated": 1708633450405,
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
			"version": 448,
			"versionNonce": 227676148,
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
			"updated": 1708633450405,
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
			"version": 234,
			"versionNonce": 1481513292,
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
			"updated": 1708633450405,
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
			"version": 394,
			"versionNonce": 775156084,
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
			"updated": 1708633450405,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 152,
			"versionNonce": 1951731660,
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
			"updated": 1708633450405,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 431,
			"versionNonce": 1931322100,
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
			"updated": 1708633450405,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 288962124,
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
			"updated": 1708633450405,
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
			"version": 51,
			"versionNonce": 584393844,
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
			"updated": 1708633450405,
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
			"version": 89,
			"versionNonce": 2077527244,
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
			"updated": 1708633450405,
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
			"version": 454,
			"versionNonce": 1126200820,
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
			"updated": 1708633450405,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 216,
			"versionNonce": 1438716748,
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
			"updated": 1708633450405,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 491,
			"versionNonce": 822450036,
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
			"updated": 1708633450405,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 197,
			"versionNonce": 2102970828,
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
			"updated": 1708633450405,
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
			"version": 111,
			"versionNonce": 952797428,
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
			"updated": 1708633450405,
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
			"version": 124,
			"versionNonce": 1974841420,
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
			"updated": 1708633450405,
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
			"version": 278,
			"versionNonce": 771050100,
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
			"updated": 1708633450405,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 138,
			"versionNonce": 1320273612,
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
			"updated": 1708633450405,
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
			"version": 39,
			"versionNonce": 55303156,
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
			"updated": 1708633450405,
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
			"version": 217,
			"versionNonce": 216468812,
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
			"updated": 1708633450405,
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
			"version": 169,
			"versionNonce": 1658076532,
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
			"updated": 1708633450406,
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
			"version": 111,
			"versionNonce": 296715212,
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
			"updated": 1708633450406,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 135,
			"versionNonce": 1171549940,
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
			"updated": 1708633450406,
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
			"version": 336,
			"versionNonce": 52767308,
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
			"updated": 1708633450406,
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
			"version": 466,
			"versionNonce": 215117940,
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
			"updated": 1708633450406,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can store all suspicious words that are marked as spam somewhere.\nOur input X will be encoding whether each word we have stores at index i\nhas occurred or not (1 or 0)\n\nQij represents the probability of the word occurring in class j",
			"rawText": "We can store all suspicious words that are marked as spam somewhere.\nOur input X will be encoding whether each word we have stores at index i\nhas occurred or not (1 or 0)\n\nQij represents the probability of the word occurring in class j",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can store all suspicious words that are marked as spam somewhere.\nOur input X will be encoding whether each word we have stores at index i\nhas occurred or not (1 or 0)\n\nQij represents the probability of the word occurring in class j",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "image",
			"version": 207,
			"versionNonce": 874643660,
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
			"updated": 1708633450406,
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
			"version": 223,
			"versionNonce": 395592180,
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
			"updated": 1708633450406,
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
			"version": 261,
			"versionNonce": 205522764,
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
			"updated": 1708633450406,
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
			"version": 172,
			"versionNonce": 1562370932,
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
			"updated": 1708633450406,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 270,
			"versionNonce": 1876508108,
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
			"updated": 1708633450406,
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
			"version": 253,
			"versionNonce": 62608628,
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
			"updated": 1708633450406,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 356,
			"versionNonce": 671589452,
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
			"updated": 1708633450406,
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
			"version": 163,
			"versionNonce": 2028770932,
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
			"updated": 1708633450406,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 172,
			"versionNonce": 1252342476,
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
			"updated": 1708633450406,
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
			"version": 245,
			"versionNonce": 158967796,
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
			"updated": 1708633450406,
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
			"version": 213,
			"versionNonce": 575406412,
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
			"updated": 1708633450406,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 359,
			"versionNonce": 2036894068,
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
			"updated": 1708633450406,
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
			"version": 77,
			"versionNonce": 374732748,
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
			"updated": 1708633450406,
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
			"version": 114,
			"versionNonce": 469711604,
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
			"updated": 1708633450406,
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
			"version": 69,
			"versionNonce": 316481100,
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
			"updated": 1708633450406,
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
			"version": 35,
			"versionNonce": 1807989876,
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
			"updated": 1708633450406,
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
			"version": 54,
			"versionNonce": 1891333324,
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
			"updated": 1708633450406,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 48,
			"versionNonce": 578555380,
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
			"updated": 1708633450406,
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
			"version": 78,
			"versionNonce": 1569389388,
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
			"updated": 1708633450406,
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
			"version": 46,
			"versionNonce": 1361981300,
			"isDeleted": false,
			"id": "H4ia7uGX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1364.8104636065257,
			"y": 1075.777840380519,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 104.49880382090505,
			"height": 14.80399720796155,
			"seed": 16413,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450406,
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
			"version": 212,
			"versionNonce": 1134932428,
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
			"updated": 1708633450406,
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
			"version": 245,
			"versionNonce": 2015371508,
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
			"updated": 1708633450406,
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
			"version": 167,
			"versionNonce": 841324620,
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
			"updated": 1708633450406,
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
			"version": 35,
			"versionNonce": 517464692,
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
			"updated": 1708633450406,
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
			"version": 33,
			"versionNonce": 1155837644,
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
			"updated": 1708633450406,
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
			"version": 276,
			"versionNonce": 1813738484,
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
			"updated": 1708633450406,
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
			"version": 239,
			"versionNonce": 209515852,
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
			"updated": 1708633450406,
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
			"version": 147,
			"versionNonce": 1039193460,
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
			"updated": 1708633450406,
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
			"version": 106,
			"versionNonce": 1984457676,
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
			"updated": 1708633450406,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 127,
			"versionNonce": 1100875508,
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
			"updated": 1708633450407,
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
			"version": 82,
			"versionNonce": 878776908,
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
			"updated": 1708633450407,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 143,
			"versionNonce": 195627124,
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
			"updated": 1708633450407,
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
			"version": 131,
			"versionNonce": 631302348,
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
			"updated": 1708633450407,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 135,
			"versionNonce": 802675188,
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
			"updated": 1708633450407,
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
			"version": 204,
			"versionNonce": 1034022732,
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
			"updated": 1708633450407,
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
			"version": 66,
			"versionNonce": 1496349556,
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
			"height": 27.91350021510857,
			"seed": 543228048,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708633450407,
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
					-27.91350021510857
				]
			]
		},
		{
			"type": "arrow",
			"version": 68,
			"versionNonce": 1824400844,
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
			"updated": 1708633450407,
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
			"version": 282,
			"versionNonce": 1643703540,
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
			"updated": 1708633450407,
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
			"version": 70,
			"versionNonce": 135236684,
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
			"updated": 1708633450407,
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
			"version": 60,
			"versionNonce": 1807167092,
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
			"updated": 1708633450407,
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
			"version": 50,
			"versionNonce": 829432524,
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
			"updated": 1708633450407,
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
			"version": 141,
			"versionNonce": 1999716340,
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
			"updated": 1708633450407,
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
			"version": 92,
			"versionNonce": 1064954188,
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
			"updated": 1708633450407,
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
			"version": 153,
			"versionNonce": 2087526772,
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
			"updated": 1708633450407,
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
			"version": 84,
			"versionNonce": 629596108,
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
			"updated": 1708633450407,
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
			"version": 394,
			"versionNonce": 45142772,
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
			"updated": 1708633450407,
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
			"version": 117,
			"versionNonce": 1538328140,
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
			"updated": 1708633450407,
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
			"version": 83,
			"versionNonce": 948065396,
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
			"updated": 1708633450407,
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
			"version": 189,
			"versionNonce": 1188191436,
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
			"updated": 1708633450407,
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
			"version": 213,
			"versionNonce": 195536372,
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
			"updated": 1708633450407,
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
			"version": 211,
			"versionNonce": 545579852,
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
			"updated": 1708633450407,
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
			"version": 94,
			"versionNonce": 1093060468,
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
			"updated": 1708633450407,
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
			"version": 309,
			"versionNonce": 1596103116,
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
			"updated": 1708633450407,
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
			"version": 232,
			"versionNonce": 222673140,
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
			"updated": 1708633450407,
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
			"version": 62,
			"versionNonce": 499482700,
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
			"updated": 1708633450407,
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
			"version": 196,
			"versionNonce": 730495604,
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
			"updated": 1708633450407,
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
			"version": 222,
			"versionNonce": 71800524,
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
			"updated": 1708633450407,
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
			"version": 285,
			"versionNonce": 1991969780,
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
			"updated": 1708633450407,
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
			"version": 346,
			"versionNonce": 792911180,
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
			"updated": 1708633450407,
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
			"version": 191,
			"versionNonce": 14511476,
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
			"updated": 1708633450407,
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
			"version": 268,
			"versionNonce": 403788748,
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
			"updated": 1708633450407,
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
			"version": 237,
			"versionNonce": 725065460,
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
			"updated": 1708633450407,
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
			"version": 372,
			"versionNonce": 2093808204,
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
			"width": 507.921142578125,
			"height": 80,
			"seed": 125358704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450407,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This tells us that the classifier is accurate when one class\nis highly dominant over the other!\n(While the result we got is in binary classification, it does apply\nto more classes)",
			"rawText": "This tells us that the classifier is accurate when one class\nis highly dominant over the other!\n(While the result we got is in binary classification, it does apply\nto more classes)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This tells us that the classifier is accurate when one class\nis highly dominant over the other!\n(While the result we got is in binary classification, it does apply\nto more classes)",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 549,
			"versionNonce": 1045405812,
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
			"updated": 1708633450407,
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
			"version": 144,
			"versionNonce": 1213190348,
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
			"updated": 1708633450407,
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
			"version": 673,
			"versionNonce": 32207348,
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
				},
				{
					"id": "704NjtUB1kDjDzWbzfCs0",
					"type": "arrow"
				}
			],
			"updated": 1708633450408,
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
			"version": 247,
			"versionNonce": 2050217804,
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
			"updated": 1708633450408,
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
			"version": 368,
			"versionNonce": 1427182452,
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
			"width": 693.6654052734375,
			"height": 60,
			"seed": 1777432688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "4PkSg1mKqeMV_HPsLrJ_F",
					"type": "arrow"
				}
			],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The harmonic mean is the lowest of the three pythagorean means followed up\nby the geometric and the arithmetic, it represents an average rate or average density\nand is calculated by the inverse of sum of inverse numbers divided by their count",
			"rawText": "The harmonic mean is the lowest of the three pythagorean means followed up\nby the geometric and the arithmetic, it represents an average rate or average density\nand is calculated by the inverse of sum of inverse numbers divided by their count",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The harmonic mean is the lowest of the three pythagorean means followed up\nby the geometric and the arithmetic, it represents an average rate or average density\nand is calculated by the inverse of sum of inverse numbers divided by their count",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 284,
			"versionNonce": 248712652,
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
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 115,
			"versionNonce": 1174832372,
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
			"updated": 1708633450408,
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
			"version": 409,
			"versionNonce": 1732736076,
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
			"updated": 1708633450408,
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
			"version": 58,
			"versionNonce": 710002292,
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
			"updated": 1708633450408,
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
			"type": "rectangle",
			"version": 65,
			"versionNonce": 829098700,
			"isDeleted": false,
			"id": "VQZqluJAFukYnGu4WpsKr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1395.1897017406363,
			"y": 1922.3238317727714,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 416.6694897847342,
			"height": 79.84086031803281,
			"seed": 13726282,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 196,
			"versionNonce": 918083572,
			"isDeleted": false,
			"id": "AAwgWkki",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1339.4674346436786,
			"y": 2168.4998177533716,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 517.1210327148438,
			"height": 20,
			"seed": 292412758,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Case 1: Posterior of class 1 is smaller than Posterior of class 2",
			"rawText": "Case 1: Posterior of class 1 is smaller than Posterior of class 2",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Case 1: Posterior of class 1 is smaller than Posterior of class 2",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 157,
			"versionNonce": 1339543884,
			"isDeleted": false,
			"id": "rNyYNRbN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1341.0876257817056,
			"y": 2097.0646837893137,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 697.2274725700702,
			"height": 55.54432695526764,
			"seed": 17662,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0bdc3abd982dd81d14ea48ddc021fb95d6e2609a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 144,
			"versionNonce": 390183284,
			"isDeleted": false,
			"id": "Cr9vMj9-gguTTyRq0FF3a",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1335.3419417038085,
			"y": 2190.6804444450236,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 698.5417573793986,
			"height": 55.43982201423799,
			"seed": 83859786,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f75eaed08d20f245476983ea9425da048f819012",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 328,
			"versionNonce": 1105709004,
			"isDeleted": false,
			"id": "kH9I8Elm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1337.8040833870537,
			"y": 2253.60926201904,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 524.177001953125,
			"height": 20,
			"seed": 159847958,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Case 2: Posterior of class 2 is smaller than Posterior of class 1",
			"rawText": "Case 2: Posterior of class 2 is smaller than Posterior of class 1",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Case 2: Posterior of class 2 is smaller than Posterior of class 1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 276,
			"versionNonce": 120744692,
			"isDeleted": false,
			"id": "iwrRluxZd1NmCFFUDv9sE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1332.8469148188708,
			"y": 2276.6215643390046,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 698.5417573793986,
			"height": 55.43982201423799,
			"seed": 598205270,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "20af2050539e0e20c222144b7c6541f8600b08ac",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 199,
			"versionNonce": 196406860,
			"isDeleted": false,
			"id": "4PkSg1mKqeMV_HPsLrJ_F",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2642.113496574894,
			"y": 1781.3818865477956,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 279.07612546372275,
			"height": 43.8996152414843,
			"seed": 316240074,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "3rfFB1pg",
				"focus": 0.20571343723321814,
				"gap": 9.806822940955044
			},
			"endBinding": {
				"elementId": "D4XTGR0H",
				"focus": 0.4598083250599929,
				"gap": 7.348135655526221
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
					199.9000336889021,
					-10.19098210963034
				],
				[
					279.07612546372275,
					33.70863313185396
				]
			]
		},
		{
			"type": "text",
			"version": 549,
			"versionNonce": 1762716788,
			"isDeleted": false,
			"id": "D4XTGR0H",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2710.8982788096323,
			"y": 1822.4386553351758,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 439.74493408203125,
			"height": 200,
			"seed": 142397322,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "4PkSg1mKqeMV_HPsLrJ_F",
					"type": "arrow"
				}
			],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "For example:\nA car is heading from city A to city B\nThe car travels half the distance going 30KM/h\nand the other half going 50KM/h, what is the\naverage speed that this car is travelling at?\n\nThe answer here is 37.5 not 40, because its travelling\nhalf the DISTANCE not half the TIME at that speed\nand in this case we want the average of two rates\nwhich the harmonic mean helps us with.",
			"rawText": "For example:\nA car is heading from city A to city B\nThe car travels half the distance going 30KM/h\nand the other half going 50KM/h, what is the\naverage speed that this car is travelling at?\n\nThe answer here is 37.5 not 40, because its travelling\nhalf the DISTANCE not half the TIME at that speed\nand in this case we want the average of two rates\nwhich the harmonic mean helps us with.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "For example:\nA car is heading from city A to city B\nThe car travels half the distance going 30KM/h\nand the other half going 50KM/h, what is the\naverage speed that this car is travelling at?\n\nThe answer here is 37.5 not 40, because its travelling\nhalf the DISTANCE not half the TIME at that speed\nand in this case we want the average of two rates\nwhich the harmonic mean helps us with.",
			"lineHeight": 1.25,
			"baseline": 194
		},
		{
			"type": "text",
			"version": 56,
			"versionNonce": 504972492,
			"isDeleted": false,
			"id": "voLsalew",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -470.19567537316243,
			"y": -121.1332026161528,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 81.28018188476562,
			"height": 20,
			"seed": 129674262,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- likelihood",
			"rawText": "- likelihood",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- likelihood",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 70,
			"versionNonce": 1587756532,
			"isDeleted": false,
			"id": "jj7irAWb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -469.51161593713505,
			"y": -85.38438559933758,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 77.31214904785156,
			"height": 20,
			"seed": 586956630,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- evidence",
			"rawText": "- evidence",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- evidence",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 183,
			"versionNonce": 1051642700,
			"isDeleted": false,
			"id": "hC8OYgz7JeAlNJmHRKSwI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 233.09543477711566,
			"y": 1589.8537455958271,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 255.53325054678305,
			"height": 146.18302832105655,
			"seed": 1799126516,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "YSo5zePC",
				"focus": -1.3343296053014626,
				"gap": 10.960802306476126
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
					26.023674648345832,
					129.11746267833087
				],
				[
					255.53325054678305,
					146.18302832105655
				]
			]
		},
		{
			"type": "arrow",
			"version": 76,
			"versionNonce": 1626300276,
			"isDeleted": false,
			"id": "704NjtUB1kDjDzWbzfCs0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 691.4629272389483,
			"y": 1589.6038557615702,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 61.05554436727266,
			"seed": 259081292,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "pfKQwX8d",
				"focus": 0.8459496512901656,
				"gap": 7.206718317343075
			},
			"endBinding": {
				"elementId": "6MHInLsD",
				"focus": 0.00771323535286351,
				"gap": 6.158133106402829
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
					61.05554436727266
				]
			]
		},
		{
			"type": "text",
			"version": 72,
			"versionNonce": 1875870156,
			"isDeleted": false,
			"id": "6MHInLsD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 580.2215868152746,
			"y": 1656.8175332352457,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 220.77975463867188,
			"height": 25,
			"seed": 1545644748,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "704NjtUB1kDjDzWbzfCs0",
					"type": "arrow"
				}
			],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Integrate Numerically ",
			"rawText": "Integrate Numerically ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Integrate Numerically ",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 1480282356,
			"isDeleted": false,
			"id": "YSo5zePC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 495.8751684712905,
			"y": 1685.0759716104076,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 387.21685791015625,
			"height": 40,
			"seed": 246222028,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "hC8OYgz7JeAlNJmHRKSwI",
					"type": "arrow"
				},
				{
					"id": "f9KOHrC-A9KeZlD39lDEu",
					"type": "arrow"
				}
			],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Discretize The entire distribution and numerically\nintegrate over the entire space",
			"rawText": "Discretize The entire distribution and numerically\nintegrate over the entire space",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Discretize The entire distribution and numerically\nintegrate over the entire space",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 109,
			"versionNonce": 1486186572,
			"isDeleted": false,
			"id": "xdfSgO8W",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 552.5829423200839,
			"y": 1729.4176130944427,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 259.48858642578125,
			"height": 60,
			"seed": 213325556,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "f9KOHrC-A9KeZlD39lDEu",
					"type": "arrow"
				}
			],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Problem:\nif input is high dimensional this is\nvery hard to compute",
			"rawText": "Problem:\nif input is high dimensional this is\nvery hard to compute",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem:\nif input is high dimensional this is\nvery hard to compute",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 157,
			"versionNonce": 873271924,
			"isDeleted": false,
			"id": "f9KOHrC-A9KeZlD39lDEu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 823.1984623949497,
			"y": 1769.4318278402093,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 185.29721852772911,
			"height": 64.31804279474886,
			"seed": 2066573172,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xdfSgO8W",
				"focus": 0.463071670597617,
				"gap": 11.126933649084549
			},
			"endBinding": {
				"elementId": "Hx3bkiDU",
				"focus": 0.4077067904858118,
				"gap": 15.101468880644575
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
					95.71137320647165,
					-4.594145913910552
				],
				[
					113.32226587646244,
					-62.02096983779347
				],
				[
					185.29721852772911,
					-64.31804279474886
				]
			]
		},
		{
			"type": "text",
			"version": 44,
			"versionNonce": 752516812,
			"isDeleted": false,
			"id": "GaEWzQYe",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1152.4491937649116,
			"y": 1644.3175328776574,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 77.01991271972656,
			"height": 25,
			"seed": 31716684,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Sampling",
			"rawText": "Sampling",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sampling",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 140,
			"versionNonce": 53126132,
			"isDeleted": false,
			"id": "Hx3bkiDU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1023.5971498033234,
			"y": 1677.7518366050413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 337.3287353515625,
			"height": 80,
			"seed": 1045900492,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "f9KOHrC-A9KeZlD39lDEu",
					"type": "arrow"
				}
			],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Sample points and approximate the error\nThe integral is replaced by an expectation\nover x of P(Err|x)\n(Monte carlo)",
			"rawText": "Sample points and approximate the error\nThe integral is replaced by an expectation\nover x of P(Err|x)\n(Monte carlo)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sample points and approximate the error\nThe integral is replaced by an expectation\nover x of P(Err|x)\n(Monte carlo)",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 65,
			"versionNonce": 356042060,
			"isDeleted": false,
			"id": "xf82U2ODz2yP3vYV-DU37",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1625.5211097976905,
			"y": 2385.8068431283345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.3333333333332575,
			"height": 188,
			"seed": 307045364,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708633450408,
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
					-1.3333333333332575,
					188
				]
			]
		},
		{
			"type": "text",
			"version": 357,
			"versionNonce": 194643316,
			"isDeleted": false,
			"id": "J3iAoIFr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1076.0283526362323,
			"y": 2597.390176461668,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1082.81884765625,
			"height": 100,
			"seed": 1313095540,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "In Some cases it is sometimes irrelevant to rely on the data generating distributions (The likelihood)\nbecause it doesn't contribute much to the accuracy of the classifier, and instead we only want to take the\ninformation provided by The prior distribution\nLets take an example",
			"rawText": "In Some cases it is sometimes irrelevant to rely on the data generating distributions (The likelihood)\nbecause it doesn't contribute much to the accuracy of the classifier, and instead we only want to take the\ninformation provided by The prior distribution\nLets take an example",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In Some cases it is sometimes irrelevant to rely on the data generating distributions (The likelihood)\nbecause it doesn't contribute much to the accuracy of the classifier, and instead we only want to take the\ninformation provided by The prior distribution\nLets take an example",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 71,
			"versionNonce": 386546636,
			"isDeleted": false,
			"id": "g-fAUKlx-avT2va5ywUhk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1284.029021131024,
			"y": 2697.3901758426196,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 685.2575757575761,
			"height": 71.00000000000004,
			"seed": 1952704076,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4ec8994b9c46da2d5fd1c835887ebb7ad5937220",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 276,
			"versionNonce": 1654732532,
			"isDeleted": false,
			"id": "lunPVeD4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1142.8183315919614,
			"y": 2755.02112884262,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 967.678955078125,
			"height": 50,
			"seed": 390262132,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "If we were to rely solely on the prior, for the prediction, one class is going to be clearly superior\nto the other and will be picked all the time",
			"rawText": "If we were to rely solely on the prior, for the prediction, one class is going to be clearly superior\nto the other and will be picked all the time",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If we were to rely solely on the prior, for the prediction, one class is going to be clearly superior\nto the other and will be picked all the time",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 188,
			"versionNonce": 2087248460,
			"isDeleted": false,
			"id": "gf2ZPKhenRHU_OdiVn4g8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1462.4553324494022,
			"y": 2813.9477312988297,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 351.79822136324344,
			"height": 38.146795087580614,
			"seed": 859418572,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "adeb68f9a1d709262cae779cb3de8000f1717065",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 50,
			"versionNonce": 80099444,
			"isDeleted": false,
			"id": "Ab-rqiQvq5eyBiWu0SAe6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1577.3550156024983,
			"y": 2813.150637055481,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 107.43066612177358,
			"height": 19.68624771864961,
			"seed": 1256782708,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5624642205327746,
					0
				],
				[
					2.8123211026641,
					0
				],
				[
					5.624642205328428,
					0.5624642205330019
				],
				[
					7.312034866926979,
					1.1249284410655491
				],
				[
					10.124355969591079,
					2.249856882131553
				],
				[
					12.936677072255407,
					2.8123211026641
				],
				[
					16.873926615985283,
					3.937249543730104
				],
				[
					19.68624771864961,
					4.499713764262651
				],
				[
					24.748425703445264,
					4.499713764262651
				],
				[
					28.68567524717514,
					5.062177984795653
				],
				[
					34.31031745250357,
					6.187106425861202
				],
				[
					40.497423878365,
					6.187106425861202
				],
				[
					47.246994524758975,
					7.874499087459753
				],
				[
					51.74670828902185,
					7.874499087459753
				],
				[
					56.246422053284505,
					9.561891749058304
				],
				[
					59.05874315594883,
					9.561891749058304
				],
				[
					61.87106425861316,
					10.124355969591306
				],
				[
					65.80831380234304,
					10.124355969591306
				],
				[
					68.62063490500736,
					10.686820190123854
				],
				[
					70.30802756660569,
					11.249284410656855
				],
				[
					73.68281288980279,
					11.811748631189857
				],
				[
					76.49513399246712,
					12.37421285172286
				],
				[
					78.74499087459844,
					12.936677072255407
				],
				[
					80.99484775672977,
					14.061605513320956
				],
				[
					83.8071688593941,
					14.061605513320956
				],
				[
					85.49456152099265,
					14.061605513320956
				],
				[
					87.74441840312397,
					14.624069733853958
				],
				[
					89.99427528525553,
					15.18653395438696
				],
				[
					91.11920372632108,
					15.748998174919507
				],
				[
					93.93152482898518,
					16.31146239545251
				],
				[
					95.61891749058373,
					16.87392661598551
				],
				[
					97.30631015218228,
					17.436390836518058
				],
				[
					97.86877437271528,
					17.436390836518058
				],
				[
					99.55616703431383,
					17.436390836518058
				],
				[
					101.24355969591238,
					17.99885505705106
				],
				[
					102.36848813697793,
					17.99885505705106
				],
				[
					103.4934165780437,
					18.56131927758406
				],
				[
					104.05588079857648,
					18.56131927758406
				],
				[
					104.61834501910948,
					18.56131927758406
				],
				[
					105.74327346017503,
					19.12378349811661
				],
				[
					106.30573768070803,
					19.12378349811661
				],
				[
					106.86820190124081,
					19.68624771864961
				],
				[
					107.43066612177358,
					19.68624771864961
				],
				[
					106.86820190124081,
					19.68624771864961
				],
				[
					106.86820190124081,
					19.68624771864961
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 66,
			"versionNonce": 1009694924,
			"isDeleted": false,
			"id": "RpGsfnx7a09Df6mmyAeo7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1680.848432180542,
			"y": 2815.4004939376127,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 107.43066612177358,
			"height": 23.62349726237926,
			"seed": 256582132,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.2498568821313256,
					0
				],
				[
					-6.18710642586143,
					0
				],
				[
					-11.249284410657083,
					0
				],
				[
					-15.186533954386732,
					0
				],
				[
					-17.99885505705106,
					0.5624642205325472
				],
				[
					-20.811176159715387,
					1.687392661598551
				],
				[
					-23.061033041846713,
					2.8123211026641
				],
				[
					-25.87335414451104,
					3.9372495437296493
				],
				[
					-29.810603688240917,
					4.499713764262651
				],
				[
					-31.497996349839468,
					4.499713764262651
				],
				[
					-33.18538901143802,
					5.062177984795198
				],
				[
					-34.31031745250357,
					5.062177984795198
				],
				[
					-35.99771011410212,
					5.6246422053282
				],
				[
					-37.68510277570067,
					6.187106425861202
				],
				[
					-39.37249543729922,
					6.187106425861202
				],
				[
					-42.18481653996355,
					7.312034866926751
				],
				[
					-43.8722092015621,
					7.874499087459753
				],
				[
					-45.55960186316065,
					8.4369633079923
				],
				[
					-47.80945874529198,
					8.999427528525302
				],
				[
					-48.93438718635775,
					9.561891749058304
				],
				[
					-50.621779847956304,
					9.561891749058304
				],
				[
					-51.74670828902185,
					10.124355969591306
				],
				[
					-53.434100950620405,
					10.686820190123854
				],
				[
					-55.68395783275173,
					11.249284410656855
				],
				[
					-57.37135049435028,
					11.249284410656855
				],
				[
					-59.05874315594883,
					11.811748631189403
				],
				[
					-60.18367159701461,
					11.811748631189403
				],
				[
					-62.433528479145934,
					11.811748631189403
				],
				[
					-64.68338536127726,
					12.374212851722405
				],
				[
					-66.93324224340881,
					12.936677072255407
				],
				[
					-68.05817068447436,
					13.499141292787954
				],
				[
					-69.18309912554014,
					13.499141292787954
				],
				[
					-70.87049178713869,
					14.061605513320956
				],
				[
					-72.55788444873724,
					15.186533954386505
				],
				[
					-73.68281288980302,
					15.748998174919507
				],
				[
					-74.80774133086857,
					16.31146239545251
				],
				[
					-76.49513399246712,
					16.873926615985056
				],
				[
					-77.6200624335329,
					16.873926615985056
				],
				[
					-78.18252665406567,
					17.436390836518058
				],
				[
					-79.30745509513144,
					17.99885505705106
				],
				[
					-80.99484775672977,
					18.561319277583607
				],
				[
					-82.68224041832832,
					18.561319277583607
				],
				[
					-84.93209730045987,
					19.12378349811661
				],
				[
					-86.05702574152542,
					19.12378349811661
				],
				[
					-87.1819541825912,
					19.12378349811661
				],
				[
					-88.30688262365697,
					19.12378349811661
				],
				[
					-89.99427528525553,
					19.12378349811661
				],
				[
					-91.68166794685408,
					19.68624771864961
				],
				[
					-93.9315248289854,
					20.248711939182158
				],
				[
					-95.61891749058395,
					20.248711939182158
				],
				[
					-97.3063101521825,
					20.81117615971516
				],
				[
					-98.43123859324828,
					20.81117615971516
				],
				[
					-100.1186312548466,
					21.373640380248162
				],
				[
					-101.80602391644516,
					21.93610460078071
				],
				[
					-102.93095235751093,
					21.93610460078071
				],
				[
					-104.61834501910948,
					22.49856882131371
				],
				[
					-105.18080923964226,
					22.49856882131371
				],
				[
					-105.74327346017503,
					23.061033041846713
				],
				[
					-106.86820190124081,
					23.62349726237926
				],
				[
					-107.43066612177358,
					23.62349726237926
				],
				[
					-107.43066612177358,
					23.62349726237926
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 109,
			"versionNonce": 1842285044,
			"isDeleted": false,
			"id": "coYqP2SM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1296.386885050989,
			"y": 2851.1196635743727,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 675.2791748046875,
			"height": 25,
			"seed": 1428140148,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets find out for which values this situation is the optimal solution",
			"rawText": "Lets find out for which values this situation is the optimal solution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets find out for which values this situation is the optimal solution",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 148,
			"versionNonce": 1643495244,
			"isDeleted": false,
			"id": "t3TBtEBj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1417.2275648495686,
			"y": 2879.8394465479187,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 430.0345553804562,
			"height": 24.532172622375022,
			"seed": 1041,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c08c02d01647a7c9c2428206b200cc3f616c83d8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 439,
			"versionNonce": 817998708,
			"isDeleted": false,
			"id": "bt7NotqT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1417.2275652466383,
			"y": 2908.091402438782,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 558.7386061732792,
			"height": 56.15463378625922,
			"seed": 34868,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "08504741981d5f37449f17deb7f0009797e9e841",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 506,
			"versionNonce": 1981281740,
			"isDeleted": false,
			"id": "Gg71XbrowuRgCbu6u8raa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1417.2275645225882,
			"y": 2968.4471580802733,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 558.7386061732792,
			"height": 56.15463378625922,
			"seed": 1981190260,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2d8be629d1312867a5fae084b5e049f5cba1da33",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ZAPvSMSrjPMFRrwwPchN3",
			"type": "freedraw",
			"x": 1979.423485712511,
			"y": 2913.3883192068133,
			"width": 32.74780235720823,
			"height": 102.25334205413947,
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
			"seed": 829811148,
			"version": 95,
			"versionNonce": 266607860,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.6683224970856827
				],
				[
					3.3416124854295504,
					1.3366449941718201
				],
				[
					5.346579976687053,
					2.6732899883436403
				],
				[
					8.019869965030693,
					4.678257479601143
				],
				[
					11.361482450460016,
					7.351547467944783
				],
				[
					14.70309493588934,
					10.024837456288424
				],
				[
					16.70806242714707,
					13.366449941717747
				],
				[
					18.7130299184048,
					16.70806242714707
				],
				[
					19.381352415490483,
					19.38135241549071
				],
				[
					19.381352415490483,
					20.71799740966253
				],
				[
					19.381352415490483,
					22.054642403833896
				],
				[
					19.381352415490483,
					24.059609895091853
				],
				[
					19.381352415490483,
					26.064577386349356
				],
				[
					19.381352415490483,
					27.401222380521176
				],
				[
					18.044707421318662,
					29.40618987177868
				],
				[
					17.37638492423298,
					30.7428348659505
				],
				[
					17.37638492423298,
					31.411157363036182
				],
				[
					16.70806242714707,
					32.747802357208
				],
				[
					16.70806242714707,
					33.41612485429414
				],
				[
					16.70806242714707,
					34.08444735137982
				],
				[
					15.37141743297525,
					35.42109234555164
				],
				[
					14.70309493588934,
					37.426059836809145
				],
				[
					14.70309493588934,
					38.762704830980965
				],
				[
					14.70309493588934,
					40.099349825152785
				],
				[
					14.70309493588934,
					42.772639813496426
				],
				[
					14.70309493588934,
					43.44096231058211
				],
				[
					15.37141743297525,
					44.77760730475393
				],
				[
					15.37141743297525,
					46.11425229892575
				],
				[
					16.03973993006116,
					47.45089729309757
				],
				[
					16.70806242714707,
					49.45586478435507
				],
				[
					16.70806242714707,
					50.12418728144121
				],
				[
					17.37638492423298,
					50.79250977852689
				],
				[
					18.044707421318662,
					50.79250977852689
				],
				[
					23.391287398005943,
					51.46083227561303
				],
				[
					24.727932392177763,
					51.46083227561303
				],
				[
					27.401222380521176,
					52.12915477269871
				],
				[
					28.73786737469277,
					52.12915477269871
				],
				[
					30.07451236886459,
					52.12915477269871
				],
				[
					31.41115736303641,
					52.12915477269871
				],
				[
					32.74780235720823,
					52.12915477269871
				],
				[
					31.41115736303641,
					52.12915477269871
				],
				[
					30.07451236886459,
					52.12915477269871
				],
				[
					28.73786737469277,
					52.12915477269871
				],
				[
					26.732899883435266,
					52.12915477269871
				],
				[
					25.396254889263446,
					52.12915477269871
				],
				[
					22.722964900920033,
					52.12915477269871
				],
				[
					20.717997409662303,
					53.46579976687053
				],
				[
					20.717997409662303,
					54.80244476104235
				],
				[
					20.04967491257662,
					56.13908975521417
				],
				[
					20.04967491257662,
					58.144057246471675
				],
				[
					20.04967491257662,
					59.480702240643495
				],
				[
					20.04967491257662,
					61.485669731901
				],
				[
					20.04967491257662,
					62.82231472607282
				],
				[
					20.717997409662303,
					64.15895972024464
				],
				[
					21.386319906748213,
					66.16392721150214
				],
				[
					22.054642403834123,
					68.16889470275964
				],
				[
					24.059609895091626,
					70.1738621940176
				],
				[
					25.396254889263446,
					72.84715218236124
				],
				[
					26.732899883435266,
					74.85211967361874
				],
				[
					28.069544877607086,
					76.18876466779056
				],
				[
					28.73786737469277,
					77.52540966196193
				],
				[
					30.07451236886459,
					79.53037715321989
				],
				[
					30.7428348659505,
					80.86702214739171
				],
				[
					30.7428348659505,
					82.20366714156353
				],
				[
					30.7428348659505,
					84.20863463282103
				],
				[
					30.07451236886459,
					86.21360212407853
				],
				[
					28.069544877607086,
					89.55521460950786
				],
				[
					26.732899883435266,
					92.2285045978515
				],
				[
					25.396254889263446,
					94.233472089109
				],
				[
					24.727932392177763,
					95.57011708328082
				],
				[
					23.391287398005943,
					96.90676207745264
				],
				[
					22.722964900920033,
					97.57508457453878
				],
				[
					22.054642403834123,
					98.24340707162446
				],
				[
					20.717997409662303,
					98.91172956871014
				],
				[
					19.381352415490483,
					99.58005206579628
				],
				[
					18.7130299184048,
					100.24837456288196
				],
				[
					17.37638492423298,
					100.9166970599681
				],
				[
					16.70806242714707,
					101.58501955705378
				],
				[
					15.37141743297525,
					101.58501955705378
				],
				[
					14.70309493588934,
					101.58501955705378
				],
				[
					13.36644994171752,
					101.58501955705378
				],
				[
					12.698127444631837,
					101.58501955705378
				],
				[
					12.029804947545927,
					101.58501955705378
				],
				[
					10.693159953374106,
					101.58501955705378
				],
				[
					10.024837456288196,
					101.58501955705378
				],
				[
					9.356514959202514,
					101.58501955705378
				],
				[
					8.019869965030693,
					101.58501955705378
				],
				[
					7.351547467944783,
					101.58501955705378
				],
				[
					6.683224970858873,
					101.58501955705378
				],
				[
					6.683224970858873,
					101.58501955705378
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				6.683224970858873,
				101.58501955705378
			]
		},
		{
			"id": "IA7gUC0l",
			"type": "text",
			"x": 2032.6096342483443,
			"y": 2943.9226000090694,
			"width": 637.979248046875,
			"height": 25,
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
			"seed": 1415028684,
			"version": 116,
			"versionNonce": 1705991244,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"text": "Lets determine when is it optimal to predict only the first class",
			"rawText": "Lets determine when is it optimal to predict only the first class",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Lets determine when is it optimal to predict only the first class",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 59,
			"versionNonce": 347889268,
			"isDeleted": false,
			"id": "5YoBeBfB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2101.2679163946214,
			"y": 2971.2716588831377,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 471.48679582453724,
			"height": 23.997830925200997,
			"seed": 13645,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fd14bae1f6b5e21cd06720b3ec8fc60213754f31",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 180,
			"versionNonce": 1788211916,
			"isDeleted": false,
			"id": "NHfZbZl5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2101.2679156460404,
			"y": 3004.1094190698104,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 330.2325231608247,
			"height": 29.23933798819802,
			"seed": 66970,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c0d2b9b8d323b61a51920c47775f61cabbf6cd3e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 455,
			"versionNonce": 672165876,
			"isDeleted": false,
			"id": "4LV9IVMY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2102.026892530395,
			"y": 3045.2313043803506,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 720.5207032913426,
			"height": 48.276094022870524,
			"seed": 91357,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450408,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3351dc8934ead97a89dfcc805115a7f069ee7d2d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "0hC0hPJeEOySAIVui1Y27",
			"type": "freedraw",
			"x": 2140.3710770420944,
			"y": 3041.8397656586976,
			"width": 30.359072168951116,
			"height": 45.5386082534269,
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
			"roundness": null,
			"seed": 213968588,
			"version": 26,
			"versionNonce": 1936046412,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.517953608447442,
					0
				],
				[
					6.071814433790223,
					3.035907216895339
				],
				[
					9.107721650685107,
					5.312837629566275
				],
				[
					12.143628867580446,
					8.348744846461614
				],
				[
					13.661582476027888,
					12.143628867580446
				],
				[
					15.17953608447533,
					15.179536084475785
				],
				[
					18.974420105594163,
					17.45646649714672
				],
				[
					21.251350518265554,
					22.010327322489502
				],
				[
					24.287257735160892,
					25.805211343608335
				],
				[
					26.56418814783183,
					31.118048973175064
				],
				[
					29.600095364727167,
					34.9129329942939
				],
				[
					30.359072168951116,
					36.43088660274134
				],
				[
					30.359072168951116,
					37.18986340696529
				],
				[
					30.359072168951116,
					37.94884021118878
				],
				[
					30.359072168951116,
					39.46679381963668
				],
				[
					30.359072168951116,
					40.98474742808412
				],
				[
					30.359072168951116,
					42.50270103653156
				],
				[
					30.359072168951116,
					43.26167784075551
				],
				[
					30.359072168951116,
					44.020654644979004
				],
				[
					29.600095364727167,
					45.5386082534269
				],
				[
					29.600095364727167,
					45.5386082534269
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				29.600095364727167,
				45.5386082534269
			]
		},
		{
			"id": "aUARZ7H5nMbWYTU_rHa7K",
			"type": "freedraw",
			"x": 2548.700597714487,
			"y": 3045.6346496798164,
			"width": 34.15395619006995,
			"height": 49.33349227454573,
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
			"roundness": null,
			"seed": 170044492,
			"version": 32,
			"versionNonce": 702959988,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.7589768042239484,
					0
				],
				[
					-1.517953608447442,
					0
				],
				[
					-3.035907216895339,
					0
				],
				[
					-5.3128376295667294,
					1.517953608447442
				],
				[
					-6.071814433790223,
					2.2769304126713905
				],
				[
					-6.8307912380141715,
					3.035907216895339
				],
				[
					-8.348744846461614,
					5.3128376295667294
				],
				[
					-10.625675259133004,
					7.58976804223812
				],
				[
					-12.143628867580446,
					10.625675259133004
				],
				[
					-13.661582476027888,
					14.420559280251837
				],
				[
					-15.179536084475785,
					16.697489692923227
				],
				[
					-17.456466497147176,
					21.25135051826601
				],
				[
					-22.76930412671345,
					27.32316495205623
				],
				[
					-23.528280930936944,
					30.359072168951116
				],
				[
					-25.04623453938484,
					33.394979385846455
				],
				[
					-26.564188147832283,
					36.43088660274134
				],
				[
					-28.082141756279725,
					38.70781701541273
				],
				[
					-29.600095364727622,
					41.74372423230807
				],
				[
					-30.359072168951116,
					43.26167784075551
				],
				[
					-31.118048973175064,
					44.02065464497946
				],
				[
					-31.877025777399012,
					44.77963144920295
				],
				[
					-32.636002581622506,
					45.5386082534269
				],
				[
					-33.394979385846455,
					46.297585057650394
				],
				[
					-33.394979385846455,
					47.05656186187434
				],
				[
					-34.15395619006995,
					48.574515470321785
				],
				[
					-34.15395619006995,
					49.33349227454573
				],
				[
					-34.15395619006995,
					49.33349227454573
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-34.15395619006995,
				49.33349227454573
			]
		},
		{
			"type": "image",
			"version": 101,
			"versionNonce": 192458700,
			"isDeleted": false,
			"id": "7UMYPyrZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2101.267915976605,
			"y": 3111.237210241034,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 502.2055928025181,
			"height": 50.50112106394036,
			"seed": 86469,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8d3f49ca811440b9abdad830a8eb03f9054ffb70",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "hPh9HnEr",
			"type": "text",
			"x": 2102.026892787825,
			"y": 3185.5971673080558,
			"width": 584.359375,
			"height": 25,
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
			"roundness": null,
			"seed": 742063988,
			"version": 113,
			"versionNonce": 159646452,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"text": "Case 1:          (Mu is positive, which means x is negative)",
			"rawText": "Case 1:          (Mu is positive, which means x is negative)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Case 1:          (Mu is positive, which means x is negative)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 74,
			"versionNonce": 1122555468,
			"isDeleted": false,
			"id": "AGtq01Rn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2176.630585476602,
			"y": 3190.6012500971415,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 70.17757594022366,
			"height": 17.863382966602387,
			"seed": 7839,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0cc29adc172637425c1ed66f346e9ff85bfaeeae",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 66,
			"versionNonce": 1567589492,
			"isDeleted": false,
			"id": "xYmZFmtU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2103.768084164696,
			"y": 3218.337542183123,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 353,
			"height": 32,
			"seed": 25769,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b2af080f2ed30c3195601f1e586ce3199310ceb4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 241,
			"versionNonce": 378547404,
			"isDeleted": false,
			"id": "47L6v-oMyPiDqbktNL0Vb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2109.0445501420672,
			"y": 3254.290586562723,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 167.9290437207137,
			"height": 46.97315908271712,
			"seed": 2034643020,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7d0e4d7f75206dfa20144b52d551b444ae1e9ac8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 224,
			"versionNonce": 2070861300,
			"isDeleted": false,
			"id": "FdYPvx7O",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2109.044549622981,
			"y": 3301.263745871728,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 585.7192993164062,
			"height": 25,
			"seed": 1959249780,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Case 2:          (Mu is positive, which means x is positive)",
			"rawText": "Case 2:          (Mu is positive, which means x is positive)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Case 2:          (Mu is positive, which means x is positive)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 173,
			"versionNonce": 1476965196,
			"isDeleted": false,
			"id": "n9rwQcva0620XEPdIL9NI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2183.6482423117573,
			"y": 3306.2678286608134,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 70.17757594022366,
			"height": 17.863382966602387,
			"seed": 617003252,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c274eb79b7fa8ba0b4113aaf4e8e5bd595ff18ff",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 165,
			"versionNonce": 277346164,
			"isDeleted": false,
			"id": "eXSTEVxA9db339fIL6hSr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2110.785740999851,
			"y": 3334.004120746795,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 353,
			"height": 32,
			"seed": 720075380,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f14869448a74e9f1521539120ad3a376dc8f6a35",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 340,
			"versionNonce": 363620812,
			"isDeleted": false,
			"id": "8w11qzc0G-e46MUMCTXhL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2116.062206977222,
			"y": 3369.957165126395,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 167.9290437207137,
			"height": 46.97315908271712,
			"seed": 1643908084,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c29317a9601381e8711267fb4076bf774ceeb34b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 372,
			"versionNonce": 956360948,
			"isDeleted": false,
			"id": "OLbg6ZZq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2109.044549819833,
			"y": 3427.2717339867995,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 754.0791625976562,
			"height": 25,
			"seed": 1738363852,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Case 3:          (Mu is positive, which means x can be positive or negative)",
			"rawText": "Case 3:          (Mu is positive, which means x can be positive or negative)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Case 3:          (Mu is positive, which means x can be positive or negative)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 319,
			"versionNonce": 43339852,
			"isDeleted": false,
			"id": "K-IW59Rw3wgWUeTRWYNPm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2190.872331554416,
			"y": 3434.10592093346,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 88.26258533403089,
			"height": 14.203174651453248,
			"seed": 2061040204,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "70c16634fd207f3abc9774454fb167388d5685b8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 264,
			"versionNonce": 408922740,
			"isDeleted": false,
			"id": "GhlFkiTIt0aRfkIsL687t",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2114.0662272844415,
			"y": 3459.709095787771,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 346.4390278245221,
			"height": 32.60602614819032,
			"seed": 618385612,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7c163eba48a876b7b8c2b82c68093a9ef28c49b5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 439,
			"versionNonce": 1587373772,
			"isDeleted": false,
			"id": "xp4hsXl7P6T4MXLEdhfJb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2112.3286461410794,
			"y": 3496.965044861453,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 175.39616578670243,
			"height": 44.97337584274422,
			"seed": 1698682700,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ac48a6a8b9feb49b0512700c92c5c0a626a52df9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 345,
			"versionNonce": 1902787572,
			"isDeleted": false,
			"id": "1igaTLqCb7erHCgcrimIi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2286.3059523828356,
			"y": 3513.188969111043,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 91.59441349182954,
			"height": 13.68652155625039,
			"seed": 1373841012,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "72304a5565ea3b64183c13716c703484b3e9a449",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "GLpO8wszGDHXGBwZ_wi7I",
			"type": "freedraw",
			"x": 2089.207229992159,
			"y": 3183.862846914599,
			"width": 74.22424499291992,
			"height": 377.2338098463697,
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
			"seed": 610083660,
			"version": 107,
			"versionNonce": 1583263052,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.6196792350442593,
					1.746452823362688
				],
				[
					-6.985811293451206,
					7.859037705132778
				],
				[
					-12.225169763539725,
					13.098396175221296
				],
				[
					-15.7180754102651,
					19.21098105699093
				],
				[
					-19.21098105699093,
					25.32356593876102
				],
				[
					-20.084207468672503,
					27.94324517380528
				],
				[
					-20.084207468672503,
					30.56292440884954
				],
				[
					-20.084207468672503,
					33.1826036438938
				],
				[
					-20.084207468672503,
					35.80228287893806
				],
				[
					-21.83066029203519,
					40.168414937345005
				],
				[
					-22.703886703716762,
					44.53454699575195
				],
				[
					-22.703886703716762,
					49.77390546584047
				],
				[
					-23.577113115398333,
					55.88649034761056
				],
				[
					-24.45033952707945,
					62.87230164106177
				],
				[
					-24.45033952707945,
					67.23843369946871
				],
				[
					-24.45033952707945,
					73.35101858123835
				],
				[
					-24.45033952707945,
					77.71715063964575
				],
				[
					-22.703886703716762,
					83.82973552141539
				],
				[
					-22.703886703716762,
					87.32264116814122
				],
				[
					-21.83066029203519,
					92.56199963822974
				],
				[
					-20.95743388035362,
					96.92813169663668
				],
				[
					-19.21098105699093,
					103.04071657840677
				],
				[
					-18.337754645309815,
					107.40684863681372
				],
				[
					-17.464528233628243,
					112.64620710690224
				],
				[
					-15.7180754102651,
					117.01233916530919
				],
				[
					-15.7180754102651,
					122.2516976353977
				],
				[
					-13.098396175221296,
					128.36428251716734
				],
				[
					-13.098396175221296,
					130.11073534053048
				],
				[
					-12.225169763539725,
					132.73041457557474
				],
				[
					-12.225169763539725,
					136.22332022230012
				],
				[
					-11.351943351858154,
					149.3217163975214
				],
				[
					-10.478716940177037,
					155.4343012792915
				],
				[
					-10.478716940177037,
					159.80043333769845
				],
				[
					-10.478716940177037,
					163.29333898442383
				],
				[
					-10.478716940177037,
					165.03979180778697
				],
				[
					-12.225169763539725,
					168.53269745451234
				],
				[
					-13.098396175221296,
					170.2791502778755
				],
				[
					-15.7180754102651,
					173.77205592460086
				],
				[
					-17.464528233628243,
					176.39173515964512
				],
				[
					-20.084207468672503,
					177.2649615713267
				],
				[
					-22.703886703716762,
					179.88464080637095
				],
				[
					-24.45033952707945,
					180.75786721805207
				],
				[
					-26.196792350442138,
					181.63109362973364
				],
				[
					-27.07001876212371,
					182.5043200414152
				],
				[
					-27.94324517380528,
					183.37754645309633
				],
				[
					-29.68969799716797,
					185.9972256881406
				],
				[
					-31.436150820530656,
					186.87045209982216
				],
				[
					-31.436150820530656,
					187.74367851150373
				],
				[
					-33.1826036438938,
					189.49013133486642
				],
				[
					-34.92905646725649,
					190.363357746548
				],
				[
					-34.92905646725649,
					191.2365841582291
				],
				[
					-31.436150820530656,
					192.9830369815918
				],
				[
					-29.68969799716797,
					192.9830369815918
				],
				[
					-27.07001876212371,
					193.85626339327337
				],
				[
					-26.196792350442138,
					193.85626339327337
				],
				[
					-23.577113115398333,
					196.47594262831763
				],
				[
					-22.703886703716762,
					197.3491690399992
				],
				[
					-21.83066029203519,
					198.2223954516803
				],
				[
					-20.084207468672503,
					200.84207468672457
				],
				[
					-18.337754645309815,
					204.3349803334504
				],
				[
					-15.7180754102651,
					208.70111239185735
				],
				[
					-11.351943351858154,
					213.94047086194587
				],
				[
					-6.985811293451206,
					222.67273497875976
				],
				[
					-5.2393584700885185,
					226.1656406254856
				],
				[
					-5.2393584700885185,
					230.531772683893
				],
				[
					-5.2393584700885185,
					233.1514519189368
				],
				[
					-5.2393584700885185,
					237.51758397734375
				],
				[
					-5.2393584700885185,
					241.88371603575115
				],
				[
					-6.112584881769635,
					244.5033952707954
				],
				[
					-7.859037705132778,
					247.99630091752078
				],
				[
					-9.605490528495466,
					252.36243297592773
				],
				[
					-10.478716940177037,
					254.98211221097245
				],
				[
					-13.098396175221296,
					258.4750178576978
				],
				[
					-14.844848998583984,
					261.96792350442365
				],
				[
					-15.7180754102651,
					266.3340555628306
				],
				[
					-16.591301821946672,
					270.70018762123755
				],
				[
					-16.591301821946672,
					275.93954609132606
				],
				[
					-16.591301821946672,
					282.05213097309615
				],
				[
					-16.591301821946672,
					287.2914894431842
				],
				[
					-16.591301821946672,
					294.2773007366359
				],
				[
					-16.591301821946672,
					298.6434327950428
				],
				[
					-15.7180754102651,
					303.0095648534498
				],
				[
					-13.098396175221296,
					309.12214973521986
				],
				[
					-12.225169763539725,
					314.3615082053084
				],
				[
					-10.478716940177037,
					320.474093087078
				],
				[
					-6.985811293451206,
					328.3331307922108
				],
				[
					-3.4929056467258306,
					334.4457156739809
				],
				[
					0.8732264116815713,
					340.5583005557505
				],
				[
					4.366132058407402,
					345.79765902583904
				],
				[
					7.859037705132778,
					351.03701749592756
				],
				[
					10.478716940177037,
					357.1496023776972
				],
				[
					13.971622586902868,
					361.5157344361046
				],
				[
					16.591301821946672,
					365.88186649451154
				],
				[
					19.210981056991386,
					369.3747721412374
				],
				[
					22.703886703716762,
					373.7409041996443
				],
				[
					25.32356593876102,
					375.487357023007
				],
				[
					29.68969799716797,
					377.2338098463697
				],
				[
					33.1826036438938,
					377.2338098463697
				],
				[
					37.548735702300746,
					377.2338098463697
				],
				[
					38.42196211398232,
					377.2338098463697
				],
				[
					39.295188525663434,
					377.2338098463697
				],
				[
					39.295188525663434,
					377.2338098463697
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				39.295188525663434,
				377.2338098463697
			]
		},
		{
			"id": "Mr576qG4AcDJJfr6UIoc2",
			"type": "arrow",
			"x": 1662.1995146799486,
			"y": 3377.719110307872,
			"width": 372.86767778796275,
			"height": 2.6196792350442593,
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
			"roundness": {
				"type": 2
			},
			"seed": 891782988,
			"version": 44,
			"versionNonce": 1042718068,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					372.86767778796275,
					2.6196792350442593
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "vITvxGCvYml_RfUO51HGY",
			"type": "line",
			"x": 1914.441459022627,
			"y": 3371.299177862198,
			"width": 0.6253015005263478,
			"height": 19.384346516319056,
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
			"seed": 721146100,
			"version": 36,
			"versionNonce": 322118604,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6253015005263478,
					19.384346516319056
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
			"version": 60,
			"versionNonce": 1205522164,
			"isDeleted": false,
			"id": "oCGSrL6Y",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1906.2230853988115,
			"y": 3393.4437454389936,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 18,
			"height": 15,
			"seed": 48405,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5d55109809275302dfd8ad5906f394b3d0204f7c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 43,
			"versionNonce": 1395968588,
			"isDeleted": false,
			"id": "J2Tks71Zq2yFmAUMe5dMi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1733.4496688128802,
			"y": 3369.416192572956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6253015005263478,
			"height": 19.384346516319056,
			"seed": 1629521612,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6253015005263478,
					19.384346516319056
				]
			]
		},
		{
			"type": "image",
			"version": 75,
			"versionNonce": 1057804404,
			"isDeleted": false,
			"id": "JM4UtzRiMXc-XeucHVOYk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1718.0858295563146,
			"y": 3394.3210436750896,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 27.37383262519397,
			"height": 13.245402883158373,
			"seed": 47190988,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3e6b910f2f2c886e827a770350fa31f51149eda4",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "nMFYNFfymsrd0hH5q6B7_",
			"type": "line",
			"x": 1821.8570734126033,
			"y": 3368.755642938811,
			"width": 0.78194754930405,
			"height": 20.330636281906663,
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
			"seed": 759955060,
			"version": 41,
			"versionNonce": 557686988,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.78194754930405,
					20.330636281906663
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "2bnUTnDG",
			"type": "text",
			"x": 1813.2556503702583,
			"y": 3396.5147809391065,
			"width": 18.691879272460938,
			"height": 18.353445830915003,
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
			"seed": 1338736716,
			"version": 42,
			"versionNonce": 1401070068,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"text": "2x",
			"rawText": "2x",
			"fontSize": 14.682756664732002,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 13,
			"containerId": null,
			"originalText": "2x",
			"lineHeight": 1.25
		},
		{
			"id": "K-1m0xTg_ERfEFKmiOfep",
			"type": "arrow",
			"x": 1919.3742621137778,
			"y": 3346.9222642091113,
			"width": 122.32156838439232,
			"height": 0.008455827661236981,
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
			"seed": 1878531188,
			"version": 170,
			"versionNonce": 350725964,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					122.32156838439232,
					0.008455827661236981
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "9HoKJkDU63uuKm0_aQnmE",
				"focus": -0.09337636273800871,
				"gap": 1
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "ojyXd3hkwChSK-uicukva",
			"type": "arrow",
			"x": 1824.845738589296,
			"y": 3315.6956237054123,
			"width": 212.63321041286918,
			"height": 3.847882994172778,
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
			"seed": 2115323724,
			"version": 81,
			"versionNonce": 1279411060,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					212.63321041286918,
					3.847882994172778
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "9E4U8qtu4Kj0f-eEMrCxI",
			"type": "arrow",
			"x": 1734.4621634292569,
			"y": 3290.142817019584,
			"width": 309.18144631226323,
			"height": 4.2678420503225425,
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
			"seed": 2057736652,
			"version": 105,
			"versionNonce": 1116528076,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708633450409,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					309.18144631226323,
					4.2678420503225425
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "9HoKJkDU63uuKm0_aQnmE",
			"type": "ellipse",
			"x": 1910.1217343820151,
			"y": 3343.3370549409833,
			"width": 8.81279747451481,
			"height": 7.90818619630727,
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
			"roundness": {
				"type": 2
			},
			"seed": 1957459404,
			"version": 122,
			"versionNonce": 529642740,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "K-1m0xTg_ERfEFKmiOfep",
					"type": "arrow"
				}
			],
			"updated": 1708633450409,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 155,
			"versionNonce": 591873100,
			"isDeleted": false,
			"id": "dGfLr7kfeOtdZyzttPigc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1818.8466382124063,
			"y": 3312.9631758994265,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.81279747451481,
			"height": 7.90818619630727,
			"seed": 1919341900,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708633450409,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 277,
			"versionNonce": 1412532212,
			"isDeleted": false,
			"id": "SeggxKv7EzMEYNhTsjg4a",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1781.6506700836292,
			"y": 3210.2657478801543,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 166.75057973119104,
			"height": 47.30512900175631,
			"seed": 574199756,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "cY9ztF6DKuLZP3fJhnOsy",
					"type": "arrow"
				}
			],
			"updated": 1708633595217,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7352f13eb067e4fa25b3fb09c94edfa5078caef9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 167,
			"versionNonce": 582770252,
			"isDeleted": false,
			"id": "UBHYERNB22sDJej2elunc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1727.5332270123915,
			"y": 3287.4026744498033,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.81279747451481,
			"height": 7.90818619630727,
			"seed": 450635380,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708633460226,
			"link": null,
			"locked": false
		},
		{
			"id": "cY9ztF6DKuLZP3fJhnOsy",
			"type": "arrow",
			"x": 1922.9428827288998,
			"y": 3195.6814265006715,
			"width": 206.9890668693563,
			"height": 54.489398632330904,
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
			"seed": 60939084,
			"version": 301,
			"versionNonce": 1668422388,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708633781647,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.7137273771863875,
					-49.96091640304712
				],
				[
					-206.2753394921699,
					-54.489398632330904
				]
			],
			"lastCommittedPoint": [
				-258.3693105414702,
				-50.67464378023351
			],
			"startBinding": {
				"elementId": "SeggxKv7EzMEYNhTsjg4a",
				"focus": 0.6853243307131321,
				"gap": 14.584321379483072
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "9Whca9sh",
			"type": "text",
			"x": 1409.0591711547052,
			"y": 3087.9085925455274,
			"width": 361.11956787109375,
			"height": 150,
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
			"seed": 264771532,
			"version": 323,
			"versionNonce": 1840736628,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708633781646,
			"link": null,
			"locked": false,
			"text": "When this condition applies\nThere is no point in counting\non the Likelihood of the data\nwe can just predict based off\nof the prior (which says just predict\nthe first class at all times)",
			"rawText": "When this condition applies\nThere is no point in counting\non the Likelihood of the data\nwe can just predict based off\nof the prior (which says just predict\nthe first class at all times)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 143,
			"containerId": null,
			"originalText": "When this condition applies\nThere is no point in counting\non the Likelihood of the data\nwe can just predict based off\nof the prior (which says just predict\nthe first class at all times)",
			"lineHeight": 1.25
		},
		{
			"id": "wg_pWKHDGE751O3vQ4HGF",
			"type": "arrow",
			"x": 1375.0840953289662,
			"y": 3160.678724897909,
			"width": 190.23745853076502,
			"height": 100.75710277406552,
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
			"seed": 335713484,
			"version": 90,
			"versionNonce": 1355187020,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708633943435,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-171.81737525682752,
					7.4242075728261625
				],
				[
					-190.23745853076502,
					100.75710277406552
				]
			],
			"lastCommittedPoint": [
				-191.96879581164058,
				100.75710277406506
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "MX5AQC69",
				"focus": -0.04733741968640276,
				"gap": 9.545409736490456
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "MX5AQC69",
			"type": "text",
			"x": 986.904099378356,
			"y": 3270.9812374084645,
			"width": 396.799560546875,
			"height": 75,
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
			"seed": 765297140,
			"version": 174,
			"versionNonce": 1187511500,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "wg_pWKHDGE751O3vQ4HGF",
					"type": "arrow"
				}
			],
			"updated": 1708633943433,
			"link": null,
			"locked": false,
			"text": "This process can be repeated for a\ngaussian distribution generating function\nand the condition will be as follows",
			"rawText": "This process can be repeated for a\ngaussian distribution generating function\nand the condition will be as follows",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "This process can be repeated for a\ngaussian distribution generating function\nand the condition will be as follows",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 361,
			"versionNonce": 587211852,
			"isDeleted": false,
			"id": "EA7sfHtM8fTh23hzCvoJA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1079.473094035836,
			"y": 3349.4466521144295,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 179.2881551235446,
			"height": 43.99709328185144,
			"seed": 624913396,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708634080468,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "65a66788291094f7459915e01b051e637ba43eb4",
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
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 228.7617443905648,
		"scrollY": -1931.5878046448695,
		"zoom": {
			"value": 0.5268856921170714
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