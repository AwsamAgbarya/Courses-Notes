---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Structured Prediction and EBMs ^yCpBWxEM

Motivation ^hOaqEBcX

So far we have trained neural networks to output something quite
uniform and simple i.e Class index/probability, Number prediction

In other cases we want to output a structure that is much more complex
or even a sequence of complex structures (e.g machine translation does not have a fixed
length uniform output, Question/answer etc...)
Those outputs are not random, theyre structured and follow certain constraints, rules or
underlying dynamics such as energy functions ^GVkCGxZL

Forward v.s Inverse ^fCpDv9uO

Consider the following situation where we are trying to predict a possible value
and there are multiple plausible outputs that can be the outcome of such
prediction (this is quite often the case when dealing with inverse problems) ^iENRjiog

Solution 1 ^nOWBrkfv

Solution 2 ^MSKDdkuK

What we get
from NN ^oyVdMWC4

averaged over
both solutions ^xj4FtRsr

f(x) + noise ^N9B5MDMl

f is not invertible ^xFn3xWm4

We need to change our view of the task
such that it is now 
learning the conditional probability model
p(t | x)

such that we need to minimize the divergence between
the true probability and the learned probability model ^d4r5sUnr

Mixture density networks ^ShSOvj4S

Networks that are based off of a bunch of distributions that represent the outputs
such that we want to learn more about those distributions and the likelihood
of our point belonging to it ^jZrpKEuC

%%***>>>text element-link:[[Expectation Maximization]]<<<***%%Think GMM in
Expectation Maximization ^q3BX2cRo

Vector x ^ldQLf7N6

NN ^4I0cI0eU

Parameter
vector ^NqL7sPZh

Mixture model ^SGOpfTXn

Conditional
probability
density ^hTt9iiAI

Prior of
distribution ^9yptzKys

Optimize the Likelihood
of this model ^7qY3W80C

These parameters are subject
to certain constraints which can be
modeled in the output layer ^k3mwOHSn

The problem with GMMs ^lFPIGqLQ

Gaussian mixture models capture localized
high density spots in our space and identify them
as a distribution, but this gets rather out of
hand with global effects and spaces where
our data is distributed across every possible
corner of our space IN HIGH DIMENSIONAL space
for example when using pictures ^kz26hJV9

Thus it is better to use Boltzmann machines
BMs or rather RBMs are quite good at understanding
global effects by drawing conclusions between inputs and outputs
without learning features specific to that input... only the transitions that
lead to the output aka Global effects ^2rJtXctP

Conditional Restricted Boltzmann Machines
(CRBM) ^EfWErfAq

Can be interpreted as a two-layer neural network.
The lower the free energy the more likely the joint configuration
(x,y) is to occur in the wild!

Thus we perform coordinate gradient descent where we set x to a certain
value and minimize according to y then set y to a certain value and minimize
according to x ^NsnRldnX

We would like to proceed with a stochastic gradient descent procedure
We update the weights and both biases via the LR and gradient,
the gradient of our objective is given by ^97FLdIse

Standard CRBM ^hMX9RftN

Higher order CRBM ^IDNhkZTU

Additive ^T6yNUCsn

Multiplicative ^IsGKaqfi

We notice that we can represent the
conditional distributions in a much
easier way than the joint distribution
of the latent and in the input.

Remember that that their distributions are Bernoulli so the process
of sampling from the conditional goes as follows:

We sample from a uniform distribution a value between 0 and 1

we compute the probability that our jth hidden value is 1 given our input x

if this value is greater than the uniform we set the jth unit to 1 else we set it to 0


which leads our jth unit to be equal to 1 with a probability of p(hj==1 | xi) ^4urkPr8F

the hidden units are
conditionally independent
given x due to a local markov
property (the restriction) ^d3sokiXG

Since h and x are given via bernoulli distributions, we can
derive the following ^9ezLqFic

note that the conditional relation is symmetric between
the latent and the input ^sRuClUB7

softplus which is a smooth version
of relu ^gOtDtMCU

CRBMS are a special kind of RBM that specializes in working with structured output
something that the RBMs have never been able to tackle.

The difficulty in structured output prediction is that the output space typically has an exponential
number of possible configuration, exact gradients are intractable,
instead approximations like Contrastive divergence will be used (or even better algorithms). ^FdUuSBtW

examples of structured output ^iHhKxa2c

the output space has arbitrary
structure but the set of likely
output configurations is relatively
small, such as in multi-label classification ^w6Mi0Owz

house ^sGQrDM1K

horse ^gg4NzXGN

tree ^7BuvOvkG

human ^3aXNlPpX

grass ^o17ca1S4

1    0   1    0    1 ^KPOBPgeg

the output space is arbitrarily
structured but where the variability 
in it is much greater than multi-label
classification, such as in image
denoising or pixel labeling. ^Ck577QYZ

Before moving forward to CRBMs, lets get a very very quick overview of RBM and training such models ^YQGjGDnX

Restricted Boltzmann machines ^w0qbNunr

A Restricted Boltzmann Machine is an undirected graphical model for unsupervised learning.
that is used to discover hidden structures in data
The task of an RBM is to define a probability distribution over a vector of observed
binary variables v and a vector of binary hidden variables h.
i.e we want a model that after looking at a dataset would generate
similarly looking data through the probability of them being "plausible" scenarios ^M9eN74rn

Normalization Term
which is the sum of all possible
configurations over all values of h and v
This is generally intractable in this form
because it needs to find all combinations
of a variable that is high dimensional ^0ZtqANsM

Energy functions are functions
that get as an input the current
scenario of v and h and through the current
state of the system (weights, biases etc..)
output its energy.
Just view it as a score function that can
be positive or negative to signify two things
attracting or repelling each other.... ^l4Xhxq1T

a matrix containing
pairwise weights
linking elements in v
and elements in h ^prIROqGj

bias of visible
variable/layer ^rT90OzG5

bias of hidden
variable/layer ^k1JscRnn

W ^kxcxdAuL

V ^VQrbc0gL

h ^tgLp4uBX

Binary values
plus bias for each
element ^dovmNECD

No two elements from V, h are connected to
each other which is where the "restricted" comes into play
otherwise fully connected between every component of v and h ^ngaOV11U

The energy in our case correlates to probability.
Our energy function uses dot products,
which are a measure of similarities of two vectors
W's values signify positively or negatively if we want our v and h to be similar.
Low energy in our context symbolizes high probability and vice versa.

This concludes that given a real input from the dataset,
how similar is it to the features saved in h that are learned from our
distribution of inputs (which means how plausible that this sample x was drawn from our dist) ^jeAMoDX1

For the sake of understanding lets defined a very simple example and walk through it
while explaining ^M4WEME0i

V is this example is a datapoint from our dataset that describes
whether a student attended a ML lecture or not, each element i
gives 1 if the i-th student attends and 0 if it does not.
The bias for v can be thought of as prior knowledge that
i-th student is more likely to attend classes in general or not.
if it was negative then the student is less likely to attend in general
and vice vera
but the bias does not mean anything at the start of training. ^IEEYFIqV

The hidden layer in this example are factors
or features of the data
that contribute to a student attending
for example if j-th unit of h can be 1 if hes in korea
bragging about his work or 0 if hes not.
another unit can describe whether there is a train strike or not
note that these states are not something we know in each datapoint
which is why theyre hidden, theyre not available in the dataset. ^wugb9a97

what this means for our example is that no two events in v or two events in h affect
each other, i.e students dont attend classes because their friend does. Only factors
in h affect factors in v, and the weights connecting them are the strength of the effect ^waiju7ZB

Our goal in this example is to learn what are the most plausible scenarios that happen
i.e learn the probability distribution over h and v that describes what is happening and the patterns
that occur in the data often. ^OJivyeYg

We define an energy function to give us a measure of score
note that energy = -score in this context and score = likelyness of a scenario ^QVXVLhwc

Now since we can measure scores, we can "easily" build a probability distribution
using the softmax function which maps values to the range 0..1 such that their sum is 1 ^9WEm90O5

Lets take for simplified example scenario:

Sanad=1 , Awsam=1, Philipp=0



Professor=1 , strike=1
is absent             ^roXTpIND

Classic philipp
doesnt bother
showing up ^yLz8cUo6

2 ^FV5apLXh

0 ^cNQYVdA4

1 ^GJgLzdqy

1 ^DZqFW4HP

0 ^BFsRcpOr

0.5 ^9m0Zq2fe

Concludes in the score of 2.5
if we calculate every single possible scenario's
score then divide by their sum we will get a probability
of each one ^x6l9Qnei

Note that the reason we are using Exp
is because we dont want to map high scores to high
numbers and low scores to low numbers without making
them sum to 0 (as in no negative numbers) in order
to not divide by 0
 ^70PZ3G1v

Problem:
We cant compute an exponential number of combinations
We need to develop an algorithm that does not require the denominator
in order to learn the probability distribution ^b6MRqJRb

Lets explain briefly, the process of contrastive divergence
Given a dataset with our data v, what we are trying to do here
to build p(v,h) is the following:

for every point vi that occurs in data
increase P(vi | h) over all possible values of h
and decrease all probabilities
after a sufficient number of datapoints we will achieve a data
distribution such that it mimics the probability distribution of our dataset
The end goal is to update the weights and biases such that:


Which translates to the log likelihood of the data ^LpKHFnlf

visual explanation ^hnLR68lN

probability ^NqUjnsbC

scenario ^q6aNAWL3

lets take a scenario of all
possible combinations of
the letters A, B, C

lets also assume we
have a dataset over occurances
of A and B, and C is our hidden
layer ^Y4mDn0Zq

A ^SW3dhAOW

B ^gOuK40GM

C ^i2ogkj5Q

AB ^LLwB7AoI

AC ^RYVAiBw1

BC ^BXl1xLRa

ABC ^PBAg8WDP

First datapoint samples AB
so we increase probability
of all scenarios that include
AB in them over all values of
h
and decrease everything (including
those we increased) ^Z5FhW3jM

probability ^hNbp7I2t

scenario ^CbYxbqSk

A ^9cj6QbUM

B ^TrWFrgqG

C ^X2k7lvaA

AB ^90CDNutQ

AC ^J2d0PyqR

BC ^eq2h9lR7

ABC ^ro9pgnhH

lets say we samples A
now so we repeat the
process ^YFwi8mmr

probability ^050ipAlq

scenario ^wPIE5DBV

A ^MsdctTfo

B ^6vJrLluM

C ^OZ4ILVrW

AB ^XmqiRVGI

AC ^nePxwTyT

BC ^kdL13VA4

ABC ^XcZj3Qg9

Overtime, points that never occur
will result in very low probability
and things that did occur (or variations of them
given values of the hidden layer) will be
with high probability exactly how the distribution
of the original dataset is ^XPQzNvIT

probability ^0DdmHCrR

scenario ^CwuTskK2

A ^ZAu7nL1s

B ^fLl5Cd9k

C ^kkHNetD2

AB ^zEBwwEeP

AC ^NDKN0AMq

BC ^J6PEN3ys

ABC ^60IqkPLs

A popular use case for RBMs is recommendation systems
lets say you click on a yt video, which is the input x
the hidden layer will be (trained) to contain the structure
of videos like "what style is this video?" "whats the topic?"
etc...
after enough training, we will understand the patterns
that activate the hidden nodes i.e learning the probability distribution
of the dataset
by adjusting the weights and biases, this model can figure out
how likely is someone who regularly watches cat videos on youtube
to also watch animal documentaries.
and this applies to any example where you want to learn more about ur data ^gAqZ2LFv

Task:
Show to the RBM, samples form a database of visible unit combinations (possible inputs)
and adjust the parameters (W and the biases) such that the probability distribution
defined by the energy function of our RBM p(v,h) encodes the observed probability
distribution p(h)
 ^TJVZWu2C

Fancy words for
if we take our p(v,h) and theoretically
marginalize over all possible values of h
then we get something close to p(v) ^Aptb9c6w

But that is not something we can do
but it turns out its something
we can derive ^LyxgUr5T

Free energy function ^fnlambpY

The probability function correlates to its corresponding Energy function
meaning if we can derive the energy function then we can derive the distribution
that it builds and thus avoid having to marginalize p(v,h) to p(v)  ^1SWBHol3

marginalization of p(x,h) over all
values of h ^R9rTUWYn

We are using x instead of v
here because the derivation I stole
does... deal with it..  ^0wXWfmmQ

unrelated to 
different values
of h ^dHqM1Fbb

Exponential of a sum 
=
product of all the eponentiated
sums ^4m8aoMLr

We evaluate the two cases
when hj=1 and when hj=0 ^xjJifAaL

This final result is also called the free energy functions (also called Softplus) ^2PgBtZQF

such that ^I1seJjCP

Now that we have our probability distribution
we can learn from it how to tune our parameters
such that the likelihood of our data increases
to a point where it matches our dataset ^SnR4mSyv

its like a smooth Relu ^Q0rscUAw

if elements of x are 1 when c
is positive and 0 when c is negative
i.e
if it has features that we know have
a higher prior to occur and 0 otherwise
the probability increases ^5KMNZXwO

for this to be big
we want the input vector to be
well aligned with W's jth row, so for
a given hidden unit j, if x is positive
for positive values of wj and 0 for negative
values of wj, then this means the features
detected in x via the dot product match
what we learned (and is stored) in h
the bias of the hidden unit bj is the threshold
of "how present must this feature be in order
for us to consider it a meaningful feature
 andlet it significantly affect the prob" ^QCDEX3N4

We can make a loss function out of this objective ^27OfqHbt

We can get the probability of A
by enumerating over all possible scenarios
of A and the hidden unit
as in A and AC ^ESllB8Zt

positive phase ^KP1ajpwN

negative phase ^pgWxSaM2

given our data point xi this is
an expectation over the
conditional distribution
p(h | xi) ^DfO7PAS6

this is derived from Z ^9Gm9Pn2x

this is derived from sum
over energies (numerator) ^WbflxJBJ

Summation over hidden vectors
given a visible vector xi multiplied
by their energy function ^fBNBLyxX

The positive phase tells us that for all parameters that affected
the expectation xi, should be increased in order to increase the probability
of having a combination of variables that includes xi and all possible values
of h ^Xb6H4eca

Recall the visual example above:
 ^u8TDvCpP

First datapoint samples AB
so we increase probability
of all scenarios that include
AB in them over all values of
h
and decrease everything (including
those we increased) ^Ei2p16Ws

Go over all possible values
of x and h (intractable)
in the probability distribution
built by our model
and which parameters actually
affected them and reduce it ^gsw2c8NG

What this really is doing is the push pull approach ^zpG0xTnN

Since we want to associate low energy with high probability and we want
to increase the probability of observing xi given our parameters
and decrease the chance of finding random unrelated points samples from
our model x,y given our parameters.
We traverse the loss function by reducing probabilities of all points in our space
and only increasing the ones we just observed ^VaAfIWih

(soft on/off value
indicating how well
present the feature
in W is in x) ^xHTt2pUZ

Expectation
over the observations ^JyZSWrwT

expectation over
the probability distribution
built by the model ^UlTIu2pw

p(hj | x) ^0XL5bDoO

Another and final way to look at this is
given enough datapoints xi, the left term
is calculating the expected value of xi, h
over the DATASET distribution, and the right
term is calculating the expected value over the
distribution inferred and built by the model itself
and this leads us to a a good solution at the
minima when the gradient is 0
(as in the left and right term are equal)
BECAUSE the distribution built by the model will be
closer and closer to the dataset distribution ^hQqsSDDb

Okay cool, I get it (Kinda...) But
you just said the right side is
intractable, how do we even do this? ^9sUUi4Vf

Gibbs Sampling ^K0S5FDT7

Training ^KpYlSGDE

Persistent Contrastive Divergence ^SgSwTgfO

Instead of decreasing all points (over all values of h and x)
lets just obtain one random point and decrease it and be satisfied with that
over an infinite amount of points this will converge to the normal CD
it just will be an approximation and is a lot slower. ^FmCVwL49

Analogy ^uUuMKpl6

Say you have a jar of Blue and red balls, and you have an external
supply of blue balls... you want to get rid of all the red balls and only
fill the jar with blue balls.
one way to do this is to take all red balls out and put all blue balls in
(which is what the normal CD algorithm tries)

The enhanced method goes as follows:
Take exactly one ball out of the jar and throw it away
and instead insert a blue ball from your supply...
if the ball you took out was red, we are closer to our solution of all blue balls
if the ball you took out was blue, we are exactly where we were on the last step

with every iteration we will always move forwards towards a solution or stand still
and over an infinite amount of steps we will converge ^KLPxNRVy

Supply ^4MKn0Jeo

Jar ^KjEaRE94

How do we obtain a random
sample without iterating over
a lot of values? ^Xu4HpERR

Sampling from a joint probability distribution is hard!
we instead try to sample from conditional distribution some T amount of times
and we will produce something random form the joint  ^vPjLzrHa

For example:
(stupid example)

If we want to sample from a joint probability distribution of all
possible values of english letters and digits


1. Start at an english letter (lets say A)

2. Sample a number according to the conditional probability distribution
p( digit | A )

3. We call that digit N, now we sample a letter according to the conditional
distribution of N p( Letter | N )

4. Repeat steps 2-3, T times until you get something completely random ^2zqTdXa3

Formulated to our 
Issue ^ZmSqi9n7

1. Start at the current Point observed xi

2. Sample an h according to the conditional distribution
p(hi|xi)

3. get that value of h and sample an x according to its conditional
p(xj | hi)

4. Repeat this process T times

5. sample one random h value given xi and one random value
h given xj

6. Increase the probability of xi,h in your models distribution
and decrease the probability of xj,h (after the T iterations)
in your distribution ^FBM4WSE3

Which turns our previous example
about the visible layers A,B 
and latent C into ^eIMqYlS6

probability ^Q8DMkDxu

scenario ^MY4nqgZd

A ^Pdcl17Yd

B ^pa7y40WS

C ^IynFiyxs

AB ^0SwEujEw

AC ^8uFBtSR4

BC ^kN1X1QQo

ABC ^W1Lx9vqJ

after observing AB ^DcetZArb

Previously ^TLepbfFT

Now ^ipJsC98w

probability ^4dxuK7pa

scenario ^BMzzBwe7

A ^K6NIldma

B ^gqpKK7uK

C ^g44lMf7B

AB ^vpzvY4Zx

AC ^oov1Jt5B

BC ^NIEkdIFh

ABC ^3eM2uBCx

probability ^xBLwGkxc

scenario ^LgXxQYYq

A ^g27P9Mue

B ^lkTmUWMD

C ^5ooY1U2r

AB ^rEBjDczl

AC ^Vw6Autku

BC ^LljYdUpO

ABC ^u42TsBOv

choose only one randomly between
h that correlate to AB
to increase ^AwFTcixQ

choose randomly another x by using Gibbs
then choose randomly a variation one h of it
to decrease ^RtXoOckV

Derivation ^cmqMaVqB

Oh sorry that took longer than expected, anyway where were we? ^32zhlyHu

THIS WILL BE A REPLACEMENT FUNCTION FOR THE STANDARD ENERGY FUNCTION
(Read the training part first) ^ys83Zgbs

The log-likelihood of the data turns into



Deriving our gradient we  arrive at ^VlpMmdHL

positive phase
corresponds to the expected gradient of
the energy This simplification occurs because
the gradient of F w.r.t. p(h|v)
is zero, so the effect of changing the parameters on
p(h|v) can be ignored ^4RbcuHhQ

negative phase, is an expectation over the model
distribution, p(v), and is intractable to compute exactly
for all but the smallest model
Gibbs sampling is still possible ofc
We can then ignore the sampled h and only keep the
sampled v ^GCzeHR4j

Unlike RBMS, CRBMS model the distribution of two inputs u and v
p(v|u) by using an RBM to model v and using u to dynamically
determine the biases or weights of that RBM



Associated with the distribution ^O3nofUTz

The energy function is defined like RBM but with an additional layer u and weights associated with it
We can turn this energy function the same way we did with RBMs into a free energy function
marginalized over h values ^QLZ69Vla

V ^2uYGMk97

u ^0XQ6ILkB

This free energy function defined the following distribution ^gFuD3017

sometimes seen in a simpler
form where the biases are 0
and v and u are not connected
(x and y here) ^vg0gDQA7


# Embedded files
0edd9c2d94201837a21fb4a0d69930b86e0f8193: $$p(h|x) = \Pi_j p(h_j|x)$$
d68fab0532591d3932daafad444bb1016db263c2: $$p(h_j ==1 | x) = \text{ sigmoid}(b_j + W_{j:}x)$$
ebf34d15c595014e0cea4549b73b2b759ff83303: $$p(x_k == 1 | h) = \text{ sigmoid}(c_k + h^TW_{:k})$$
0a58a98342599296079bb17f9da791a5f258597d: $$b_i^v$$
9cf2e388325851a7e449c3be8d3b86ea1d195fd5: $$b_j^h$$
2682318a6f25a146b3e241f0f699ca0cc7ac86ba: $$E(v,h) = - v^TWh- v^Tb^v - h^Tb^h$$
7e3a11868a4e04a39502f3d611789ffe3abd85a2: $$p(v,h) = \frac{exp ( -E(v,h)) }{\sum_{h \in \{0,1\}^d} exp(-E(v,h))}$$
9270c865a6e134f8fe7cb6d1ef11d7d13c584a58: $$\arg\max \Pi_{v \in V} P(v)$$
bddb6e9e5ba1ba8392c44c9f81fed1f410e5e101: $$\arg\max E[log(P(v))]$$
2813ad29ca21e8d35c18edb984a5d42b7b056096: $$p(x)$$
5207afc8cbaf940ad1ee7e5a5e3fb97983c8d559: $$p(x) = \frac{exp(-F(x))}{Z}$$
68f6888780542236d2df59319879564b2a1c94a8: $$F(x) = -c^Tx - \sum_{j=1}^H log(1+ exp(b_j +W_j x))$$
38d677b40f9a99e8245fed7311551c22e111d810: $$\frac{exp(c^Tx + \sum_{j=1}^H log(1+ exp(b_j +W_j x)))}{Z}$$
76d4d8d8fa1f3003df60bc193aeb940bd369e8a1: $$l(x) = \frac{1}{N} \sum_{i=1}^N -log(p(x_i))$$
c0a499b0dc933d7f5542f4266a5e6a88169f7213: $$\frac{\partial - logp(x_i)}{\partial \theta} = E_h \left[ \frac{\partial E(x_i,h)}{\partial \theta} | x_i \right] - E_{x,h} \left[ \frac{\partial E(X,h)}{\partial \theta}\right]$$
1e903a011823ca88927345ec93829c49300d480c: $$I\{ p(h_j==1 | x_i) > U[0..1] \}$$
2f1183fa1f8aa17584d1e81bdf626d196593895e: $$E (v, h, u) = − v^TW^{vh}h − v^Tb_v − u^TW^{uv}v − u^TW^{uh}h − h^Tb_h $$
9b64c0af91848b6f3c0b2a7186db887d8cf2aa0b: $$F(u,v) = − \sum_j log(1 + exp(b_j^h + v^TW^{vh}_{·j} + u^T W^{uh}_{·j})) − v^T b_v − u^TW^{uv} v$$
9334036148bc15cfb8b2a244e14f2e86159cf47a: $$p(v | u) = \frac{exp(-F(v,u)}{\sum_{v'}exp(-F(v,u))}$$
31ee164613b395561a3aa7005888276f3ec2d4b8: $$p(v,h,u) = Z^{-1} exp(-E(v,h,u))$$
3e3265aacc4691dfd3d08c74a861d55d6aa4a0a1: [[Pasted Image 20240127190909_702.png]]
a5b0374752dfb54041fdf8d5c93d765cb549e4a3: [[Pasted Image 20240127191951_013.png]]
a124003092c327e18715bd3c4334e4d1e470bcfb: [[Pasted Image 20240127192041_658.png]]
9e9a0b97f4802026311d1788a9a338107a233460: [[Pasted Image 20240127192144_068.png]]
a222ab9a8e5d7bd8c568f9f71ddb8bef5ec0da2b: [[Pasted Image 20240127192229_080.png]]
1aed2ca66ab831139587a32ac46cfbc96a0ace5d: [[Pasted Image 20240127192555_100.png]]
0732dc9282a0e9f4feaef8974b644bb34c458fa9: [[Pasted Image 20240127192642_116.png]]
f0b64e743b0df6337ecd066100b51279963b67c8: [[Pasted Image 20240127192845_127.png]]
63e2c0de5a6dd97eadbd7e56eca4a80e06666d03: [[Pasted Image 20240127192957_160.png]]
3f0c6a98da54be803ba992476fda0eca5f7393b5: [[Pasted Image 20240127193013_174.png]]
d0d1d36cc01a3c23754ae18d7782b8b99eb0a196: [[Pasted Image 20240127193507_205.png]]
0cc2d4da6a9879d99c6f2320990680238d585b86: [[Pasted Image 20240127195937_384.png]]
e0dea364c7011de73d9677b23a6e3b6be647868d: [[Pasted Image 20240127200037_389.png]]
bbb32d99227583705b743363c020f83d9727deab: [[Pasted Image 20240127200836_494.png]]
a0ee93c7c23aa945852fa7391fb107d5e49eb93c: [[Pasted Image 20240127200906_496.png]]
50c36a584ee9647a13762db7081bdb75ade49b1b: [[Pasted Image 20240127201130_542.png]]
6fa4af893c110fe256a85c5e2c3b5f9e4b29fcf1: [[Pasted Image 20240127201442_585.png]]
5399d3937af064035d71662a3745b46f3012d035: [[Pasted Image 20240127203437_789.png]]
e0afc5abe8fa25061d8fd314a8a40f61b3f3ea83: [[Pasted Image 20240127203501_810.png]]
cd4eb941ea5c5764e065c0b5c14bfd4c65721171: [[Pasted Image 20240127203516_811.png]]
8a49189668af2e76c9370ae00b59946c8340461f: [[Pasted Image 20240127203531_813.png]]
0fb9e45d1795c97223225c72c522896dd707a6e2: [[Pasted Image 20240127203546_814.png]]
1a0b42c9e99c729659c286778394c8840c120f8e: [[Pasted Image 20240131181242_851.png]]
78ae3aa134d670b3b52c56eb791c9264798564c2: [[Pasted Image 20240217185424_932.png]]
9d0b0bfbcbd7fbf841215fb6c3303b2a15727338: [[cropped_Pasted Image 20240217230457_289]]
d7e7a54e673a3f3a9b8fbb07703258013bbcb761: [[Pasted Image 20240127201357_571.png]]
fe2b3efcf3c0208afe36ddc82f95c97868a12728: [[Pasted Image 20240127201800_635.png]]
a4a79f31e10847e1c8579539cd7add01b338f6dc: [[Pasted Image 20240218014435_004.png]]
ab6d835db2b83ed0b87761035db276ae3569e3a1: [[Pasted Image 20240218014535_024.png]]
0dc9ce934cb083f3e671aaeda8271cd54f2b2665: [[Pasted Image 20240218020846_221.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.20",
	"elements": [
		{
			"type": "image",
			"version": 694,
			"versionNonce": 474293430,
			"isDeleted": false,
			"id": "kLHxcnE0I3gvyr4yvZK52",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 190.63875337727143,
			"y": 1632.2575830503445,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 352.85834247275113,
			"height": 233.3302629738679,
			"seed": 419488272,
			"groupIds": [
				"-CJMpiwBzbM0aTQnvqGCQ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708217717542,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0dea364c7011de73d9677b23a6e3b6be647868d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "8poG6eKbeREZDgXG2GbXv",
			"type": "freedraw",
			"x": 291.63967206587915,
			"y": 1860.9071055705556,
			"width": 10.075242131062396,
			"height": 7.916261674406087,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"-CJMpiwBzbM0aTQnvqGCQ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 973544938,
			"version": 261,
			"versionNonce": 1558912502,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217717542,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.7196601522186938,
					0
				],
				[
					-2.158980456656195,
					0
				],
				[
					-2.8786406088750027,
					-0.7196601522186938
				],
				[
					-3.5983007610936966,
					-0.7196601522186938
				],
				[
					-2.8786406088750027,
					-0.7196601522186938
				],
				[
					-1.4393203044375014,
					-0.7196601522186938
				],
				[
					0,
					-0.7196601522186938
				],
				[
					1.4393203044375014,
					-0.7196601522186938
				],
				[
					2.8786406088750027,
					-0.7196601522186938
				],
				[
					4.317960913312504,
					-0.7196601522186938
				],
				[
					5.037621065531198,
					-1.4393203044373877
				],
				[
					6.476941369968699,
					-2.158980456656309
				],
				[
					6.476941369968699,
					-2.8786406088750027
				],
				[
					6.476941369968699,
					-3.5983007610936966
				],
				[
					6.476941369968699,
					-5.037621065531312
				],
				[
					6.476941369968699,
					-6.476941369968699
				],
				[
					6.476941369968699,
					-7.196601522187393
				],
				[
					5.037621065531198,
					-7.196601522187393
				],
				[
					4.317960913312504,
					-7.196601522187393
				],
				[
					3.5983007610936966,
					-7.196601522187393
				],
				[
					2.8786406088750027,
					-7.916261674406087
				],
				[
					1.4393203044375014,
					-7.916261674406087
				],
				[
					0,
					-7.916261674406087
				],
				[
					0,
					-7.916261674406087
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0,
				-7.916261674406087
			]
		},
		{
			"id": "bOMsD1LmaAZBYIXrKm8Wk",
			"type": "freedraw",
			"x": 478.03165149053336,
			"y": 1861.6267657227743,
			"width": 12.953882739937399,
			"height": 10.79490228328109,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"-CJMpiwBzbM0aTQnvqGCQ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 547196266,
			"version": 264,
			"versionNonce": 553643830,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217717542,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.4393203044373877,
					-1.4393203044373877
				],
				[
					-1.4393203044373877,
					-2.1589804566560815
				],
				[
					-2.158980456656195,
					-2.8786406088750027
				],
				[
					-2.878640608874889,
					-3.5983007610936966
				],
				[
					-4.31796091331239,
					-4.31796091331239
				],
				[
					-5.037621065531198,
					-4.31796091331239
				],
				[
					-5.757281217749892,
					-5.037621065531312
				],
				[
					-5.757281217749892,
					-5.7572812177500055
				],
				[
					-5.037621065531198,
					-6.476941369968699
				],
				[
					-4.31796091331239,
					-7.916261674406087
				],
				[
					-3.5983007610936966,
					-8.63592182662478
				],
				[
					-2.158980456656195,
					-10.075242131062396
				],
				[
					-1.4393203044373877,
					-10.79490228328109
				],
				[
					-0.7196601522186938,
					-10.79490228328109
				],
				[
					0,
					-10.79490228328109
				],
				[
					0.7196601522188075,
					-10.79490228328109
				],
				[
					1.4393203044375014,
					-10.79490228328109
				],
				[
					2.158980456656309,
					-10.79490228328109
				],
				[
					3.5983007610938103,
					-10.79490228328109
				],
				[
					4.317960913312504,
					-10.79490228328109
				],
				[
					5.037621065531198,
					-10.79490228328109
				],
				[
					5.7572812177500055,
					-10.79490228328109
				],
				[
					5.7572812177500055,
					-10.075242131062396
				],
				[
					5.7572812177500055,
					-9.355581978843702
				],
				[
					6.476941369968699,
					-9.355581978843702
				],
				[
					7.196601522187507,
					-9.355581978843702
				],
				[
					7.196601522187507,
					-9.355581978843702
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				7.196601522187507,
				-9.355581978843702
			]
		},
		{
			"id": "72gXm3bbHwirk9bmhKc5S",
			"type": "freedraw",
			"x": 308.19185556691025,
			"y": 1735.6862390844944,
			"width": 30.94538654540588,
			"height": 15.11286319659348,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"-CJMpiwBzbM0aTQnvqGCQ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1628179754,
			"version": 283,
			"versionNonce": 1156094070,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217717542,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.7196601522186938,
					0
				],
				[
					-1.4393203044375014,
					0
				],
				[
					-2.8786406088750027,
					0.7196601522186938
				],
				[
					-3.5983007610936966,
					1.4393203044373877
				],
				[
					-5.757281217749892,
					2.1589804566560815
				],
				[
					-7.196601522187393,
					3.5983007610936966
				],
				[
					-8.635921826624894,
					5.037621065531084
				],
				[
					-10.075242131062396,
					6.476941369968699
				],
				[
					-11.514562435499897,
					7.916261674406087
				],
				[
					-12.953882739937399,
					9.355581978843702
				],
				[
					-15.832523348812288,
					10.075242131062396
				],
				[
					-17.27184365324979,
					10.79490228328109
				],
				[
					-18.71116395768729,
					11.514562435499784
				],
				[
					-20.15048426212479,
					12.234222587718477
				],
				[
					-21.589804566562293,
					12.953882739937399
				],
				[
					-24.468445175437296,
					13.673542892156092
				],
				[
					-26.62742563209349,
					14.393203044374786
				],
				[
					-28.066745936530992,
					14.393203044374786
				],
				[
					-28.786406088749686,
					14.393203044374786
				],
				[
					-30.225726393187188,
					15.11286319659348
				],
				[
					-30.94538654540588,
					15.11286319659348
				],
				[
					-30.225726393187188,
					14.393203044374786
				],
				[
					-28.786406088749686,
					12.953882739937399
				],
				[
					-26.62742563209349,
					10.79490228328109
				],
				[
					-24.468445175437296,
					7.916261674406087
				],
				[
					-22.309464718780987,
					6.476941369968699
				],
				[
					-20.15048426212479,
					5.037621065531084
				],
				[
					-17.991503805468597,
					3.5983007610936966
				],
				[
					-16.552183501031095,
					2.1589804566560815
				],
				[
					-15.112863196593594,
					2.1589804566560815
				],
				[
					-13.673542892156092,
					2.1589804566560815
				],
				[
					-12.953882739937399,
					2.1589804566560815
				],
				[
					-11.514562435499897,
					3.5983007610936966
				],
				[
					-10.075242131062396,
					5.037621065531084
				],
				[
					-8.635921826624894,
					7.196601522187393
				],
				[
					-8.635921826624894,
					7.916261674406087
				],
				[
					-7.916261674406201,
					8.63592182662478
				],
				[
					-7.916261674406201,
					10.075242131062396
				],
				[
					-7.196601522187393,
					10.075242131062396
				],
				[
					-6.476941369968699,
					10.075242131062396
				],
				[
					-6.476941369968699,
					10.79490228328109
				],
				[
					-6.476941369968699,
					11.514562435499784
				],
				[
					-6.476941369968699,
					12.953882739937399
				],
				[
					-6.476941369968699,
					13.673542892156092
				],
				[
					-6.476941369968699,
					14.393203044374786
				],
				[
					-6.476941369968699,
					14.393203044374786
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-6.476941369968699,
				14.393203044374786
			]
		},
		{
			"id": "6EQ9YfYERJnpVsFKBn_nI",
			"type": "freedraw",
			"x": 488.82655377381457,
			"y": 1728.489637562307,
			"width": 15.112863196593594,
			"height": 24.46844517543741,
			"angle": 0,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"-CJMpiwBzbM0aTQnvqGCQ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 671502634,
			"version": 283,
			"versionNonce": 1349130678,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217717542,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.4393203044375014,
					-0.7196601522189212
				],
				[
					-2.158980456656195,
					-0.7196601522189212
				],
				[
					-3.5983007610936966,
					-0.7196601522189212
				],
				[
					-6.476941369968699,
					-0.7196601522189212
				],
				[
					-8.635921826624894,
					0
				],
				[
					-10.794902283281203,
					0.7196601522186938
				],
				[
					-12.953882739937399,
					2.1589804566560815
				],
				[
					-14.3932030443749,
					3.5983007610936966
				],
				[
					-15.112863196593594,
					5.037621065531084
				],
				[
					-15.112863196593594,
					6.476941369968699
				],
				[
					-15.112863196593594,
					7.916261674406087
				],
				[
					-15.112863196593594,
					9.355581978843475
				],
				[
					-15.112863196593594,
					10.79490228328109
				],
				[
					-15.112863196593594,
					12.953882739937171
				],
				[
					-15.112863196593594,
					14.393203044374786
				],
				[
					-14.3932030443749,
					15.832523348812174
				],
				[
					-12.953882739937399,
					17.27184365324979
				],
				[
					-12.234222587718591,
					17.991503805468483
				],
				[
					-11.514562435499897,
					18.711163957687177
				],
				[
					-10.794902283281203,
					19.43082410990587
				],
				[
					-9.355581978843702,
					20.15048426212479
				],
				[
					-8.635921826624894,
					20.15048426212479
				],
				[
					-7.916261674406201,
					20.870144414343486
				],
				[
					-7.196601522187393,
					20.870144414343486
				],
				[
					-6.476941369968699,
					21.58980456656218
				],
				[
					-5.7572812177500055,
					22.309464718780873
				],
				[
					-5.037621065531198,
					23.029124870999794
				],
				[
					-4.317960913312504,
					23.029124870999794
				],
				[
					-4.317960913312504,
					23.74878502321849
				],
				[
					-5.7572812177500055,
					23.74878502321849
				],
				[
					-7.916261674406201,
					23.029124870999794
				],
				[
					-9.355581978843702,
					22.309464718780873
				],
				[
					-10.075242131062396,
					21.58980456656218
				],
				[
					-10.075242131062396,
					20.15048426212479
				],
				[
					-10.794902283281203,
					19.43082410990587
				],
				[
					-10.794902283281203,
					18.711163957687177
				],
				[
					-11.514562435499897,
					17.991503805468483
				],
				[
					-12.234222587718591,
					17.991503805468483
				],
				[
					-11.514562435499897,
					17.27184365324979
				],
				[
					-10.794902283281203,
					16.552183501031095
				],
				[
					-10.075242131062396,
					15.832523348812174
				],
				[
					-9.355581978843702,
					14.393203044374786
				],
				[
					-8.635921826624894,
					13.673542892156092
				],
				[
					-7.916261674406201,
					13.673542892156092
				],
				[
					-7.196601522187393,
					13.673542892156092
				],
				[
					-7.196601522187393,
					13.673542892156092
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-7.196601522187393,
				13.673542892156092
			]
		},
		{
			"id": "2uYGMk97",
			"type": "text",
			"x": 287.90899420137134,
			"y": 1842.9156017650869,
			"width": 10.339996337890625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"-CJMpiwBzbM0aTQnvqGCQ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 32019754,
			"version": 271,
			"versionNonce": 178877174,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217717542,
			"link": null,
			"locked": false,
			"text": "V",
			"rawText": "V",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "V",
			"lineHeight": 1.25
		},
		{
			"id": "0XQ6ILkB",
			"type": "text",
			"x": 483.866221250252,
			"y": 1839.3173010039932,
			"width": 11.3599853515625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"-CJMpiwBzbM0aTQnvqGCQ"
			],
			"frameId": null,
			"roundness": null,
			"seed": 752925622,
			"version": 245,
			"versionNonce": 237741110,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217717542,
			"link": null,
			"locked": false,
			"text": "u",
			"rawText": "u",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "u",
			"lineHeight": 1.25
		},
		{
			"id": "2Sv8pHBI0iHfP653EZy4Z",
			"type": "image",
			"x": -1706.9907461414805,
			"y": 4585.958263977676,
			"width": 568,
			"height": 83,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 446658038,
			"version": 71,
			"versionNonce": 1990174646,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217112005,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a4a79f31e10847e1c8579539cd7add01b338f6dc",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "jvPW3GigvXnlbQKMRUUnT",
			"type": "rectangle",
			"x": -2972.240770061753,
			"y": 3871.4223714548943,
			"width": 289.5721595498412,
			"height": 121.59523582828842,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
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
			"seed": 370789546,
			"version": 270,
			"versionNonce": 2046729078,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1797,
			"versionNonce": 432520374,
			"isDeleted": false,
			"id": "i8zFpDLRNK68fro2ehuoG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1732.9716189855264,
			"y": 1694.1445280485718,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#eaddd7",
			"width": 202.9964150225261,
			"height": 44.53197708471382,
			"seed": 1591688106,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1704,
			"versionNonce": 1046132214,
			"isDeleted": false,
			"id": "MGTE6Xme2kOsJPrW5NbIc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1570.4665547513096,
			"y": 1704.861368729707,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 142820150,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1717,
			"versionNonce": 1622968118,
			"isDeleted": false,
			"id": "iqamdZtqwRg777DM2WPAG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1606.8979495921792,
			"y": 1703.844624336443,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 1977077686,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1708,
			"versionNonce": 290599030,
			"isDeleted": false,
			"id": "4j_QwJKmJwWA6krCb8KiV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1641.6002693399646,
			"y": 1704.2808181597222,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 1676001462,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1704,
			"versionNonce": 199274934,
			"isDeleted": false,
			"id": "SIAxWeFhj5Qw5Oe7CGo6j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1679.1918826737233,
			"y": 1704.1268345793833,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 195173686,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1712,
			"versionNonce": 1267534582,
			"isDeleted": false,
			"id": "RVjt45pmwBx_I1phEOwE6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1719.6727895934587,
			"y": 1703.382673595421,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 205917034,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1758,
			"versionNonce": 517749814,
			"isDeleted": false,
			"id": "ZHPvhCD7FNz77g_TSw_QP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1806.0915015103747,
			"y": 1895.2034623623267,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#eaddd7",
			"width": 353.27289677798086,
			"height": 44.53197708471382,
			"seed": 196391978,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1595,
			"versionNonce": 1001604470,
			"isDeleted": false,
			"id": "oItOS-ZtQvA013PdpntA9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1493.3105858862364,
			"y": 1906.2280833502577,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 1679859434,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1615,
			"versionNonce": 1398220470,
			"isDeleted": false,
			"id": "mYXkdgPq4VeLiF0Trh2wm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1529.7411062460465,
			"y": 1904.4560887901935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 88158634,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1602,
			"versionNonce": 644669430,
			"isDeleted": false,
			"id": "DVEMJ3F-tfRuIUWhCi4NM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1564.4434259938312,
			"y": 1904.8922826134713,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 1111583850,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1599,
			"versionNonce": 419000630,
			"isDeleted": false,
			"id": "wEPKU-fJSVzOTgqUeVgYF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1602.0350393275921,
			"y": 1904.7382990331344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 1357664042,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1608,
			"versionNonce": 1180818038,
			"isDeleted": false,
			"id": "EVz-YTXhaapQTIjcs7Zbn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1642.5159462473252,
			"y": 1903.9941380491741,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 1974262250,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1597,
			"versionNonce": 359340982,
			"isDeleted": false,
			"id": "0UdaNZyX1xn5iRV8otjc6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1678.4658126781617,
			"y": 1905.569129239112,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 198722678,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1606,
			"versionNonce": 1278883062,
			"isDeleted": false,
			"id": "lhMgXhR1-RYrr9yRiI6bo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1716.982696704032,
			"y": 1904.7692805382808,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 1210183094,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1599,
			"versionNonce": 609494582,
			"isDeleted": false,
			"id": "iqOwy9mlZn_bk2IhPrVpj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1755.5022041730824,
			"y": 1906.2351823378576,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 1601393526,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1607,
			"versionNonce": 1587408758,
			"isDeleted": false,
			"id": "gn4XhKS0rex7gou6Yf5l-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 3.1456888523284263,
			"x": -1792.5085878653495,
			"y": 1905.4370825991473,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 27.760193507354018,
			"height": 27.181856142617562,
			"seed": 860721270,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1152,
			"versionNonce": 1465684150,
			"isDeleted": false,
			"id": "V4nm6gChCWjwUnXoktDQG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5719541956800063,
			"x": -1642.391197580621,
			"y": 1889.5097152950411,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 178.80343989557775,
			"height": 144.3157693769765,
			"seed": 1836833066,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					178.80343989557775,
					-144.3157693769765
				]
			]
		},
		{
			"type": "line",
			"version": 1144,
			"versionNonce": 439683574,
			"isDeleted": false,
			"id": "40fGSNavkTpVWtm0mblFW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5719541956800063,
			"x": -1659.6930066084844,
			"y": 1871.7205592751889,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 176.92856116715006,
			"height": 107.25719096266744,
			"seed": 10485238,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					176.92856116715006,
					-107.25719096266744
				]
			]
		},
		{
			"type": "line",
			"version": 1096,
			"versionNonce": 1982618422,
			"isDeleted": false,
			"id": "dq5pKFdiSolnFuNxpBgMb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5719541956800063,
			"x": -1712.087249352645,
			"y": 1818.283332033785,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 173.28475796469627,
			"height": 4.606574841295696,
			"seed": 1528961194,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					173.28475796469627,
					-4.606574841295696
				]
			]
		},
		{
			"type": "line",
			"version": 1106,
			"versionNonce": 296191094,
			"isDeleted": false,
			"id": "Jd3R0yG2qX8SCQtUuAslx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5719541956800063,
			"x": -1774.6954541852972,
			"y": 1762.0900380354446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 179.36125093141038,
			"height": 115.44905278091392,
			"seed": 439609078,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					179.36125093141038,
					115.44905278091392
				]
			]
		},
		{
			"type": "line",
			"version": 1080,
			"versionNonce": 2120975798,
			"isDeleted": false,
			"id": "2dl5ioznZb5uBYbzdT8xk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5719541956800063,
			"x": -1793.4465420214658,
			"y": 1741.6331452472432,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 175.95580689237158,
			"height": 152.80353791247285,
			"seed": 1020804138,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					175.95580689237158,
					152.80353791247285
				]
			]
		},
		{
			"type": "line",
			"version": 365,
			"versionNonce": 1302159094,
			"isDeleted": false,
			"id": "sWq9liCem5RgWbiuLJixm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1625.107567589821,
			"y": 1728.0629451616728,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 74.7917224025681,
			"height": 180.29800430971432,
			"seed": 1346351146,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					74.7917224025681,
					180.29800430971432
				]
			]
		},
		{
			"type": "line",
			"version": 359,
			"versionNonce": 599920694,
			"isDeleted": false,
			"id": "RYOlPtjpWfWr2ENEohoqT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1626.5635463914655,
			"y": 1729.228195793747,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fff9db",
			"width": 38.764556530974346,
			"height": 174.54078829393484,
			"seed": 1749244586,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					38.764556530974346,
					174.54078829393484
				]
			]
		},
		{
			"type": "line",
			"version": 315,
			"versionNonce": 1287559542,
			"isDeleted": false,
			"id": "V6ll8cbVBn_NEEZO25Xop",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1627.8901874727117,
			"y": 1730.6534094180388,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fff9db",
			"width": 73.3005286760739,
			"height": 173.13044801500337,
			"seed": 294521142,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-73.3005286760739,
					173.13044801500337
				]
			]
		},
		{
			"type": "line",
			"version": 251,
			"versionNonce": 1339554486,
			"isDeleted": false,
			"id": "Gf9ZWZNM8d5eS8CC6HRRq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1663.6757089385524,
			"y": 1905.0206081310753,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fff9db",
			"width": 36.69846770774052,
			"height": 173.00706205077722,
			"seed": 1924992758,
			"groupIds": [
				"rP-uDpq526ITz0Smhh4zz"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					36.69846770774052,
					-173.00706205077722
				]
			]
		},
		{
			"type": "image",
			"version": 375,
			"versionNonce": 1340347690,
			"isDeleted": false,
			"id": "MJc9csI5-Cawplqq2EcM8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 978.7409578088791,
			"y": 158.97763789270834,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 139,
			"height": 154,
			"seed": 891767024,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9e9a0b97f4802026311d1788a9a338107a233460",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 185,
			"versionNonce": 535997046,
			"isDeleted": false,
			"id": "pLpmxmawcv6MJb2WwSdZE",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1087.4144950795617,
			"y": 552.181663717298,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 307.9423180575037,
			"height": 53.62179667667975,
			"seed": 176024080,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3e3265aacc4691dfd3d08c74a861d55d6aa4a0a1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 66,
			"versionNonce": 230416362,
			"isDeleted": false,
			"id": "afUXP3smGWzx7gKHB0aMm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -185.75,
			"y": -416.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 361,
			"height": 133,
			"seed": 1419555856,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "yCpBWxEM"
				}
			],
			"updated": 1708212522956,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 64,
			"versionNonce": 610397110,
			"isDeleted": false,
			"id": "yCpBWxEM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -111.23265803737496,
			"y": -374.7804134489054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 211.69976806640625,
			"height": 50,
			"seed": 1049304592,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Structured Prediction\nand EBMs",
			"rawText": "Structured Prediction and EBMs",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "afUXP3smGWzx7gKHB0aMm",
			"originalText": "Structured Prediction and EBMs",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 67,
			"versionNonce": 1003246250,
			"isDeleted": false,
			"id": "hOaqEBcX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -78.14634704589844,
			"y": -245.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 142.7725830078125,
			"height": 35,
			"seed": 2093223952,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Motivation",
			"rawText": "Motivation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Motivation",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 662,
			"versionNonce": 1943471350,
			"isDeleted": false,
			"id": "GVkCGxZL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -464.6195373535156,
			"y": -213.1068455063164,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 897.7390747070312,
			"height": 200,
			"seed": 2119433744,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mFNLB_miad-yx4tlk69Hz",
					"type": "arrow"
				},
				{
					"id": "aIjQqKtfT31UjZtlQbJ8P",
					"type": "arrow"
				}
			],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "So far we have trained neural networks to output something quite\nuniform and simple i.e Class index/probability, Number prediction\n\nIn other cases we want to output a structure that is much more complex\nor even a sequence of complex structures (e.g machine translation does not have a fixed\nlength uniform output, Question/answer etc...)\nThose outputs are not random, theyre structured and follow certain constraints, rules or\nunderlying dynamics such as energy functions",
			"rawText": "So far we have trained neural networks to output something quite\nuniform and simple i.e Class index/probability, Number prediction\n\nIn other cases we want to output a structure that is much more complex\nor even a sequence of complex structures (e.g machine translation does not have a fixed\nlength uniform output, Question/answer etc...)\nThose outputs are not random, theyre structured and follow certain constraints, rules or\nunderlying dynamics such as energy functions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "So far we have trained neural networks to output something quite\nuniform and simple i.e Class index/probability, Number prediction\n\nIn other cases we want to output a structure that is much more complex\nor even a sequence of complex structures (e.g machine translation does not have a fixed\nlength uniform output, Question/answer etc...)\nThose outputs are not random, theyre structured and follow certain constraints, rules or\nunderlying dynamics such as energy functions",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "arrow",
			"version": 290,
			"versionNonce": 482372970,
			"isDeleted": false,
			"id": "mFNLB_miad-yx4tlk69Hz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -482.61902783050743,
			"y": -128.41928803810703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 463.9001966303174,
			"height": 122.10639906327151,
			"seed": 327094800,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"customData": {},
			"startBinding": {
				"elementId": "GVkCGxZL",
				"focus": 0.09169289759716182,
				"gap": 17.99949047699181
			},
			"endBinding": {
				"elementId": "fCpDv9uO",
				"focus": -0.2647624156764151,
				"gap": 15.508894092035575
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
					-401.6420664500141,
					-4.856725562604595
				],
				[
					-463.9001966303174,
					117.24967350066692
				]
			]
		},
		{
			"type": "text",
			"version": 153,
			"versionNonce": 1607923254,
			"isDeleted": false,
			"id": "fCpDv9uO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1061.6047009781232,
			"y": 4.339279554595464,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 273.701171875,
			"height": 35,
			"seed": 729315344,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "mFNLB_miad-yx4tlk69Hz",
					"type": "arrow"
				}
			],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Forward v.s Inverse",
			"rawText": "Forward v.s Inverse",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Forward v.s Inverse",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 534,
			"versionNonce": 1709387818,
			"isDeleted": false,
			"id": "iENRjiog",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1320.721230368766,
			"y": 48.81296302433992,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 785.7791748046875,
			"height": 75,
			"seed": 799011344,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8tzjjTI9e2LuWREJEm_I3",
					"type": "arrow"
				},
				{
					"id": "riZkc_MTqS68J_FZUu8dJ",
					"type": "arrow"
				}
			],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Consider the following situation where we are trying to predict a possible value\nand there are multiple plausible outputs that can be the outcome of such\nprediction (this is quite often the case when dealing with inverse problems)",
			"rawText": "Consider the following situation where we are trying to predict a possible value\nand there are multiple plausible outputs that can be the outcome of such\nprediction (this is quite often the case when dealing with inverse problems)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Consider the following situation where we are trying to predict a possible value\nand there are multiple plausible outputs that can be the outcome of such\nprediction (this is quite often the case when dealing with inverse problems)",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 262,
			"versionNonce": 1095155574,
			"isDeleted": false,
			"id": "wxsgsFVEogIEN0tj_-y3p",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1331.8163885167203,
			"y": 309.80698843013835,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 201.0278782869441,
			"height": 0.6490248859049643,
			"seed": 616934640,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522956,
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
					201.0278782869441,
					0.6490248859049643
				]
			]
		},
		{
			"type": "arrow",
			"version": 310,
			"versionNonce": 1797233386,
			"isDeleted": false,
			"id": "riZkc_MTqS68J_FZUu8dJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1332.6719805045277,
			"y": 313.2293563813677,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 0.8555919878073155,
			"height": 175.39635750050553,
			"seed": 1545058320,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "iENRjiog",
				"focus": 1.0271220034080628,
				"gap": 14.02003585652227
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
					0.8555919878073155,
					-175.39635750050553
				]
			]
		},
		{
			"type": "text",
			"version": 196,
			"versionNonce": 208363702,
			"isDeleted": false,
			"id": "nOWBrkfv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1281.3444246604213,
			"y": 322.3046378540729,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 73.10415649414062,
			"height": 20,
			"seed": 1849479696,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Solution 1",
			"rawText": "Solution 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Solution 1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "freedraw",
			"version": 147,
			"versionNonce": 1258335658,
			"isDeleted": false,
			"id": "kKy2CQuSO27KxhuiLM12x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1324.008997379386,
			"y": 299.1555286667688,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 374619664,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 147,
			"versionNonce": 1693047286,
			"isDeleted": false,
			"id": "Jr9dBLxkR3NVxd9VhG1zx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1307.7309602422747,
			"y": 301.3259336183836,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1054750736,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 147,
			"versionNonce": 447834218,
			"isDeleted": false,
			"id": "H5_QelyZXGhXJ3dPP-z4t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1312.3430707644563,
			"y": 277.99408038852425,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1613918736,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 147,
			"versionNonce": 835136310,
			"isDeleted": false,
			"id": "RbQuYbhypYU6FlgryTn0l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1296.6076348652489,
			"y": 296.44252247725024,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 460909584,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 148,
			"versionNonce": 301779754,
			"isDeleted": false,
			"id": "Y73X7RSL2oThHwaG3dfAt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1309.358763955986,
			"y": 287.2183014328873,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0,
			"seed": 1121560080,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.271300618951841,
					0
				],
				[
					-0.271300618951841,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 147,
			"versionNonce": 828920950,
			"isDeleted": false,
			"id": "VWi_ey5rImRSEeiHK5qoU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1278.9730946333784,
			"y": 289.38870638450214,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 252583440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 150,
			"versionNonce": 927847914,
			"isDeleted": false,
			"id": "PT7t6G9RpdGH-KGlUr7IU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1269.7488735890156,
			"y": 299.42682928572066,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.8139018568556367,
			"height": 1.3565030947592618,
			"seed": 1734613008,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.271300618951841
				],
				[
					0.5426012379037388,
					-1.3565030947592618
				],
				[
					0.8139018568556367,
					-1.3565030947592618
				],
				[
					0.8139018568556367,
					-1.3565030947592618
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 147,
			"versionNonce": 227694006,
			"isDeleted": false,
			"id": "UonZV0Ay0eonVCnROx88G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1293.0807268188748,
			"y": 273.6532704852947,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1578552336,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 149,
			"versionNonce": 196053162,
			"isDeleted": false,
			"id": "OT0q1-rRE7mFTM5S7rm7g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1286.0269107261265,
			"y": 299.42682928572066,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 1.0852024758074208,
			"height": 0.8139018568555798,
			"seed": 1338213904,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5426012379037388,
					-0.271300618951841
				],
				[
					1.0852024758074208,
					-0.8139018568555798
				],
				[
					1.0852024758074208,
					-0.8139018568555798
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 151,
			"versionNonce": 1869229814,
			"isDeleted": false,
			"id": "NW6-5iHY2yEWlJYcipv9G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1251.3004315002895,
			"y": 302.1398354752392,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 1.085202475807364,
			"height": 0.542601237903682,
			"seed": 276675600,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					0.271300618951841
				],
				[
					0.542601237903682,
					0
				],
				[
					0.813901856855523,
					0
				],
				[
					1.085202475807364,
					-0.271300618951841
				],
				[
					1.085202475807364,
					-0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 147,
			"versionNonce": 919397226,
			"isDeleted": false,
			"id": "40P79xiRbg6GLnkk4-HRf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1273.0044810164377,
			"y": 274.19587172319837,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 278720016,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 148,
			"versionNonce": 326426678,
			"isDeleted": false,
			"id": "k3jXJYiciNuTqQahklK0F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1244.7892166454449,
			"y": 276.63757729376505,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0,
			"seed": 598009872,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					0
				],
				[
					0.271300618951841,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 150,
			"versionNonce": 854648362,
			"isDeleted": false,
			"id": "tBgHBF45ye0HrGwZFEb7Z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1249.4013271676265,
			"y": 286.1330989570799,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 1.8991043326630006,
			"height": 0.8139018568555798,
			"seed": 925392912,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					0
				],
				[
					0.8139018568555798,
					-0.5426012379037388
				],
				[
					1.8991043326630006,
					-0.8139018568555798
				],
				[
					1.8991043326630006,
					-0.8139018568555798
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 147,
			"versionNonce": 1570204022,
			"isDeleted": false,
			"id": "WuKnQScjECETe-acRotE3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1221.4573634155856,
			"y": 293.7295162877317,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1879381008,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 148,
			"versionNonce": 2030473450,
			"isDeleted": false,
			"id": "IxH9_WKqPobUzs_wUwXhU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1264.0515605910266,
			"y": 284.5052952433688,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0.271300618951841,
			"seed": 167169552,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					-0.271300618951841
				],
				[
					0.271300618951841,
					-0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 147,
			"versionNonce": 1830210230,
			"isDeleted": false,
			"id": "APzmsrnxs9poRllZB9fL5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1227.6972776514783,
			"y": 277.45147915062057,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1784104464,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 147,
			"versionNonce": 748217258,
			"isDeleted": false,
			"id": "B-_t1AAAL6H5XmwljxUIL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1239.9058055043117,
			"y": 255.2048283965687,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1918779408,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 147,
			"versionNonce": 815268854,
			"isDeleted": false,
			"id": "Bh9h9fy9Y9RroN_uqO3L-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1204.365424421619,
			"y": 263.07254634617243,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1750039056,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 148,
			"versionNonce": 1205001834,
			"isDeleted": false,
			"id": "lEbrKG67Pf-OgQvf8_7-R",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1218.4730566071153,
			"y": 245.7093067332538,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0,
			"height": 0.5426012379037388,
			"seed": 22213648,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.5426012379037388
				],
				[
					0,
					0.5426012379037388
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 147,
			"versionNonce": 2048922934,
			"isDeleted": false,
			"id": "gGfJHpMmeoIC0S3TRT46X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1203.8228231837152,
			"y": 292.3730131929725,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 930114576,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 149,
			"versionNonce": 1199538474,
			"isDeleted": false,
			"id": "WMi5dekR8bL67ZLzE71eq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1217.9304553692116,
			"y": 268.4985587252095,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 1.0852024758074208,
			"height": 0.8139018568555798,
			"seed": 2013341200,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.542601237903682,
					-0.5426012379037388
				],
				[
					1.0852024758074208,
					-0.8139018568555798
				],
				[
					1.0852024758074208,
					-0.8139018568555798
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 147,
			"versionNonce": 320077430,
			"isDeleted": false,
			"id": "joB5toDrIKm0iv8MEPSBp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1201.6524182321004,
			"y": 251.13531911229086,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1043815440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 148,
			"versionNonce": 1460259818,
			"isDeleted": false,
			"id": "XeW11n9Qce1L3xVkeLUun",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1233.665891268419,
			"y": 232.95817764251672,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0.542601237903682,
			"seed": 921572880,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					-0.542601237903682
				],
				[
					0.271300618951841,
					-0.542601237903682
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 147,
			"versionNonce": 1345896374,
			"isDeleted": false,
			"id": "MYOSTHLMbYPmp7lZx3Jw8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1210.3340380385598,
			"y": 227.26086464452783,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1567264272,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 147,
			"versionNonce": 2088550058,
			"isDeleted": false,
			"id": "ZYftmE91_yZRU64etDbqt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1231.495486316804,
			"y": 213.42453307798337,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 64391184,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 148,
			"versionNonce": 632510710,
			"isDeleted": false,
			"id": "RWSSbAo5txk9l5Bw24IWz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1217.387854131308,
			"y": 206.64201760418706,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0,
			"height": 0.271300618951841,
			"seed": 374129168,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.271300618951841
				],
				[
					0,
					0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 145,
			"versionNonce": 1149458794,
			"isDeleted": false,
			"id": "PGHm8NDqjZXUZId-q701J",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1197.8542095667744,
			"y": 233.2294782614686,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 998608624,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 146,
			"versionNonce": 990431798,
			"isDeleted": false,
			"id": "4oAE8dqLgE3yI8ueq8t9q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1194.3273015204004,
			"y": 216.95144112435742,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0.271300618951841,
			"seed": 1070773488,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.271300618951841,
					-0.271300618951841
				],
				[
					-0.271300618951841,
					-0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 146,
			"versionNonce": 1852349482,
			"isDeleted": false,
			"id": "wFgBKW1ixMlLmb1Myw5Td",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1240.7197073611671,
			"y": 194.1621891324018,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.813901856855523,
			"height": 0.271300618951841,
			"seed": 689487088,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.813901856855523,
					-0.271300618951841
				],
				[
					0.813901856855523,
					-0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 145,
			"versionNonce": 2132677494,
			"isDeleted": false,
			"id": "UtdaVr0_UdYkNJxc7xR6a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1217.6591547502599,
			"y": 195.51869222716107,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1528481008,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 145,
			"versionNonce": 404195050,
			"isDeleted": false,
			"id": "WJE2opXveMbbV0gC8Nkpg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1202.7376207079078,
			"y": 189.82137922917218,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 581675760,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 146,
			"versionNonce": 1010316470,
			"isDeleted": false,
			"id": "r5Oe9amDtwbeRFmlpDpp0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1227.4259770325264,
			"y": 177.07025013843509,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0.271300618951841,
			"seed": 1893617904,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.271300618951841,
					-0.271300618951841
				],
				[
					0.271300618951841,
					-0.271300618951841
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 145,
			"versionNonce": 1780160938,
			"isDeleted": false,
			"id": "5AzQgH4PonUH73xe6UJUu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1204.365424421619,
			"y": 172.18683899730178,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1500928240,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 149,
			"versionNonce": 737947126,
			"isDeleted": false,
			"id": "oIR7tpgi9J5-dJzalD_bu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1190.8003934740264,
			"y": 199.04560027353517,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.542601237903682,
			"height": 1.6278037137111028,
			"seed": 4177648,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.5426012379037388
				],
				[
					0,
					-0.8139018568555798
				],
				[
					0.271300618951841,
					-1.0852024758074208
				],
				[
					0.542601237903682,
					-1.6278037137111028
				],
				[
					0.542601237903682,
					-1.6278037137111028
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 145,
			"versionNonce": 1134449770,
			"isDeleted": false,
			"id": "afHzz1Vp52-qIkaBU9cn2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1187.0021848087003,
			"y": 181.41106004166477,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 505998576,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 145,
			"versionNonce": 191823670,
			"isDeleted": false,
			"id": "QcpfDBQMKyHyB4wQ38FrD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1217.387854131308,
			"y": 157.80790619285358,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 260756208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
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
			"version": 146,
			"versionNonce": 1718368042,
			"isDeleted": false,
			"id": "QGDio6qpUEYTQehGztezJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1201.1098169941968,
			"y": 154.00969752752763,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.27130061895189783,
			"height": 0,
			"seed": 758020336,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.27130061895189783,
					0
				],
				[
					-0.27130061895189783,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 146,
			"versionNonce": 787851382,
			"isDeleted": false,
			"id": "lbl-lZfMkhv7FweVaWFZf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1224.1703696051043,
			"y": 151.56799195696095,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 1.3565030947592618,
			"height": 0,
			"seed": 2020770032,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.3565030947592618,
					0
				],
				[
					1.3565030947592618,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 146,
			"versionNonce": 586138090,
			"isDeleted": false,
			"id": "4HIf6TVK1LmYiZRTsDAH_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1205.7219275163782,
			"y": 144.5141758642128,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.271300618951841,
			"height": 0,
			"seed": 494045424,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522956,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.271300618951841,
					0
				],
				[
					-0.271300618951841,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 145,
			"versionNonce": 374679990,
			"isDeleted": false,
			"id": "qjxYzJN5VVXUJdsToaprO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1228.511179508334,
			"y": 159.97831114446836,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1580110064,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 145,
			"versionNonce": 70513834,
			"isDeleted": false,
			"id": "BDPH3LgtToFIaqSt6xGcZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1176.1501600506263,
			"y": 165.13302290455357,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 541259504,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 145,
			"versionNonce": 11698934,
			"isDeleted": false,
			"id": "Tsy0MGVHtF4whuRZgHNhl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1188.3586879034597,
			"y": 164.86172228560173,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2108234992,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"type": "arrow",
			"version": 305,
			"versionNonce": 2078527338,
			"isDeleted": false,
			"id": "VtRfCRuZHefalqUjg_hEK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -714.6513855069493,
			"y": 309.1543921871067,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 192.32561990988972,
			"height": 2.0262134057894627,
			"seed": 1368324336,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522957,
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
					192.32561990988972,
					2.0262134057894627
				]
			]
		},
		{
			"type": "arrow",
			"version": 326,
			"versionNonce": 9614390,
			"isDeleted": false,
			"id": "8tzjjTI9e2LuWREJEm_I3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -714.8089002220368,
			"y": 313.274837411056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 0.8555919878073155,
			"height": 175.39635750050553,
			"seed": 1763859184,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "iENRjiog",
				"focus": -0.5447592138502519,
				"gap": 14.06551688621056
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
					0.8555919878073155,
					-175.39635750050553
				]
			]
		},
		{
			"type": "text",
			"version": 225,
			"versionNonce": 239751722,
			"isDeleted": false,
			"id": "MSKDdkuK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -666.3112746125345,
			"y": 318.16165524744173,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 80.16017150878906,
			"height": 20,
			"seed": 1006206192,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Solution 2",
			"rawText": "Solution 2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Solution 2",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "freedraw",
			"version": 159,
			"versionNonce": 265993590,
			"isDeleted": false,
			"id": "E7VHvYRHKOC9BUg6ofVhY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -702.6770274225223,
			"y": 293.6726594521053,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1052496624,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 2119335146,
			"isDeleted": false,
			"id": "iG8vEvQ_WiHio8FQxZQ-a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -691.0193354303889,
			"y": 294.9679585623423,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2113894640,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 600809142,
			"isDeleted": false,
			"id": "OVOdvTJD355LsncYTzV_F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -682.2760664362888,
			"y": 298.85385589305344,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 937221872,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 2038910890,
			"isDeleted": false,
			"id": "4Ld8L5XrBnxzRD7QPW2Ja",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -699.7626044244889,
			"y": 275.53847190878656,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1437336816,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 1091983350,
			"isDeleted": false,
			"id": "66Ti5CnID1gsbgFg21mpy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -663.4942293378515,
			"y": 274.2431727985495,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 532998896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 160,
			"versionNonce": 1142147690,
			"isDeleted": false,
			"id": "zTF3NB6sojyjr5gzi_Sl6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -682.9237159914073,
			"y": 270.6811002453976,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0,
			"height": 0.32382477755925265,
			"seed": 494899440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.32382477755925265
				],
				[
					0,
					-0.32382477755925265
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 164,
			"versionNonce": 263448886,
			"isDeleted": false,
			"id": "xk1KzHqSQo9oSePEwD6ob",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -691.0193354303889,
			"y": 244.7751180406566,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 2.590598220474078,
			"height": 0,
			"seed": 192387312,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6476495551185053,
					0
				],
				[
					-0.971474332677758,
					0
				],
				[
					-1.2952991102370106,
					0
				],
				[
					-1.9429486653555728,
					0
				],
				[
					-2.590598220474078,
					0
				],
				[
					-2.590598220474078,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 159,
			"versionNonce": 1690496298,
			"isDeleted": false,
			"id": "VFB7qFvK688nVKF7evO4S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -690.0478610977111,
			"y": 255.13751092255296,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1218160880,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 160,
			"versionNonce": 1863144054,
			"isDeleted": false,
			"id": "lzzUL0tZ8wCNkGGNLzi2w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -700.0864292020483,
			"y": 257.0804595879086,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.3238247775593095,
			"height": 0.9714743326778148,
			"seed": 329715440,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3238247775593095,
					-0.9714743326778148
				],
				[
					0.3238247775593095,
					-0.9714743326778148
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 159,
			"versionNonce": 1358936042,
			"isDeleted": false,
			"id": "Zx-9mgmqX3PKBgYxW27ZS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -658.9606824520218,
			"y": 243.15599415286027,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1257248496,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 162,
			"versionNonce": 166171574,
			"isDeleted": false,
			"id": "-4DYdmCazWJK79WHXJ0H6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -695.8767070937778,
			"y": 227.28858005245638,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 2.2667734429148254,
			"height": 0.6476495551185621,
			"seed": 1038761200,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.32382477755925265,
					0
				],
				[
					1.9429486653555728,
					0.6476495551185621
				],
				[
					2.2667734429148254,
					0.6476495551185621
				],
				[
					2.2667734429148254,
					0.6476495551185621
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 159,
			"versionNonce": 416623274,
			"isDeleted": false,
			"id": "VFjAOccPyeVh5auBUnrRQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -668.6754257787998,
			"y": 253.84221181231595,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2142488816,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 160,
			"versionNonce": 1785179382,
			"isDeleted": false,
			"id": "GOYMnJyC3T1PcWCypDjjG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -672.8851478870702,
			"y": 228.58387916269345,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.32382477755925265,
			"height": 0.6476495551185053,
			"seed": 338898672,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.32382477755925265,
					0.6476495551185053
				],
				[
					-0.32382477755925265,
					0.6476495551185053
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 159,
			"versionNonce": 317605226,
			"isDeleted": false,
			"id": "v-HsqWf3Ykj0ihtNvQPu4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -705.2676256429964,
			"y": 239.59392159970838,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 342636272,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 160,
			"versionNonce": 236101174,
			"isDeleted": false,
			"id": "yy9nvwiOshBLSdVL3nsxO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -668.9992505563589,
			"y": 208.18291817645985,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.6476495551185053,
			"height": 0.3238247775593095,
			"seed": 995777776,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6476495551185053,
					0.3238247775593095
				],
				[
					0.6476495551185053,
					0.3238247775593095
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 160,
			"versionNonce": 144050218,
			"isDeleted": false,
			"id": "hIJRFa8AxE6BtOlcFg2CO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -657.9892081193441,
			"y": 229.23152871781195,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0,
			"height": 0.32382477755925265,
			"seed": 1871471856,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.32382477755925265
				],
				[
					0,
					-0.32382477755925265
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 159,
			"versionNonce": 2043504502,
			"isDeleted": false,
			"id": "RqDXscrTfxeCLkbcRlyNs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -686.4857885445592,
			"y": 210.12586684181548,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 377122032,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 1639412458,
			"isDeleted": false,
			"id": "odPuxZjN0Es3jEF5Rv5Ub",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -633.7023498023993,
			"y": 200.0872987374783,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 122442480,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 1306331318,
			"isDeleted": false,
			"id": "V9Z8dW1iPmgCteQqnRDM3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -634.9976489126364,
			"y": 221.1359092788304,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 442497264,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 163,
			"versionNonce": 1356694954,
			"isDeleted": false,
			"id": "La5FOv4UQsa9dPHpjunWp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -644.388567461855,
			"y": 214.01176417252663,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.6476495551185053,
			"height": 1.9429486653555728,
			"seed": 2047696624,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.32382477755925265,
					0
				],
				[
					-0.6476495551185053,
					0.6476495551185053
				],
				[
					-0.6476495551185053,
					1.61912388779632
				],
				[
					-0.6476495551185053,
					1.9429486653555728
				],
				[
					-0.6476495551185053,
					1.9429486653555728
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 159,
			"versionNonce": 1508278774,
			"isDeleted": false,
			"id": "8OYoX7irL2aojDpwHEgPD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -637.9120719106697,
			"y": 239.59392159970838,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1435143408,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 2134065258,
			"isDeleted": false,
			"id": "R_5OflIH-FKPd_L0f0zuI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -623.3399569205029,
			"y": 214.98323850520438,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1926263536,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 820958006,
			"isDeleted": false,
			"id": "gdUy3GBKYf3Yuxo-BACe1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -605.8534189323027,
			"y": 236.35567382411574,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 383260912,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 948151082,
			"isDeleted": false,
			"id": "7WreC7VCk3aY1E92LL1Kr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -607.4725428200991,
			"y": 218.86913583591553,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1006206704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 1029373046,
			"isDeleted": false,
			"id": "ddCrIUa2W_BqZHjJ8AQOy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -608.4440171527768,
			"y": 204.2970208457487,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1535943920,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 389656042,
			"isDeleted": false,
			"id": "aTSbR3yZNHxrRJjtqfp8g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -617.5111109244363,
			"y": 233.44125082608235,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1307151088,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 1425014198,
			"isDeleted": false,
			"id": "aU4zZGgcXZYUbA7QbLK0q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -577.3568385070876,
			"y": 213.04028983984887,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 711471344,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 160,
			"versionNonce": 811622570,
			"isDeleted": false,
			"id": "CrQ9cJ3F8uXhWfTxW90K2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -593.2242526074915,
			"y": 208.18291817645985,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.32382477755925265,
			"height": 1.2952991102371243,
			"seed": 660641520,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.32382477755925265,
					1.2952991102371243
				],
				[
					0.32382477755925265,
					1.2952991102371243
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 159,
			"versionNonce": 1288886006,
			"isDeleted": false,
			"id": "KqmWn2d0AlZl8NHxgIbYv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -575.413889841732,
			"y": 246.71806670601217,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 296066800,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 160,
			"versionNonce": 1067629418,
			"isDeleted": false,
			"id": "tauHNbz08WR4E5bq_f5ZO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -557.6035270759726,
			"y": 213.36411461740812,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.32382477755925265,
			"height": 0.32382477755925265,
			"seed": 321701104,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.32382477755925265,
					0.32382477755925265
				],
				[
					-0.32382477755925265,
					0.32382477755925265
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 159,
			"versionNonce": 227051574,
			"isDeleted": false,
			"id": "cG8maxXJH_SQahbCOb6v8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -588.6907057216617,
			"y": 230.85065260560827,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 921357552,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 1397472810,
			"isDeleted": false,
			"id": "yHFZdRbaiEsrw_tK6qUK7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -566.6706208476319,
			"y": 228.2600543851342,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1964552944,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 162,
			"versionNonce": 653660534,
			"isDeleted": false,
			"id": "edVTgG4a0BDuE8P-kqzoS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -572.4994668436987,
			"y": 202.67789695795244,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0,
			"height": 0.9714743326778148,
			"seed": 50878704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.32382477755925265
				],
				[
					0,
					-0.6476495551185053
				],
				[
					0,
					-0.9714743326778148
				],
				[
					0,
					-0.9714743326778148
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 160,
			"versionNonce": 2017880298,
			"isDeleted": false,
			"id": "hmuoCWPFS3s6qT4Mlw24z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -556.6320527432948,
			"y": 237.6509729343528,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.3238247775593095,
			"height": 0,
			"seed": 1988945136,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3238247775593095,
					0
				],
				[
					0.3238247775593095,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 159,
			"versionNonce": 1684042422,
			"isDeleted": false,
			"id": "dDGtC5744duIkD6jv9a7R",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -544.9743607511614,
			"y": 214.01176417252663,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1497033968,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 1713224618,
			"isDeleted": false,
			"id": "oI7taBz4l-DZdzkSqIcbq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -539.7931643102131,
			"y": 228.58387916269345,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 199021296,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 1617734646,
			"isDeleted": false,
			"id": "bx9X8tziL-xIz7PAh14XX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -537.2025660897391,
			"y": 209.47821728669697,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1925216496,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 721204842,
			"isDeleted": false,
			"id": "_-jPJrNXmzy2U-zI61prK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -530.0784209834353,
			"y": 234.08890038120092,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2017320688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 421510454,
			"isDeleted": false,
			"id": "kU_byxG6aJFMfbQuBCf72",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -549.1840828594318,
			"y": 203.97319606818945,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 95225072,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 1471043882,
			"isDeleted": false,
			"id": "rh_TcUV-UR852HGFgHuWI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -541.4122881980095,
			"y": 248.01336581624918,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1667623664,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 64923254,
			"isDeleted": false,
			"id": "ZXTnUH3t5Q3HY1SRBMD1q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -655.7224346764292,
			"y": 200.41112351503756,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 415273200,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 159,
			"versionNonce": 731751402,
			"isDeleted": false,
			"id": "zTAXb_C40pZgJXB0hiC1k",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -599.3769233811174,
			"y": 191.6678545209375,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1276442352,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
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
			"version": 370,
			"versionNonce": 560883638,
			"isDeleted": false,
			"id": "Garo4KnQLzkHe3aN65_Hc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -695.3286598935833,
			"y": 299.73180957416145,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 161.53655927512813,
			"height": 79.8935329266879,
			"seed": 1573304848,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.538036189224727,
					-48.98581580906409
				],
				[
					32.65721053937608,
					-79.8935329266879
				],
				[
					74.35347042447233,
					-79.0187862158117
				],
				[
					132.08675334229792,
					-78.4356217418943
				],
				[
					161.53655927512813,
					-76.68612832014202
				]
			]
		},
		{
			"type": "line",
			"version": 341,
			"versionNonce": 1087739562,
			"isDeleted": false,
			"id": "yk24uY2KCXh1culhv5RKD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1319.1049529639147,
			"y": 289.4501147190446,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 110.72582127453643,
			"height": 132.51471833693813,
			"seed": 593146608,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					58.862181895324,
					0.9729286263689687
				],
				[
					90.23913009572397,
					-6.8105003845829515
				],
				[
					99.72518420282165,
					-36.48482348883721
				],
				[
					108.07832828784387,
					-69.45587962841716
				],
				[
					110.72582127453643,
					-131.54178971056916
				]
			]
		},
		{
			"type": "arrow",
			"version": 133,
			"versionNonce": 301203702,
			"isDeleted": false,
			"id": "KER7QJLChPqrkcthVh9Kp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1136.682366544363,
			"y": 223.15534037048212,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 68.51060077010538,
			"height": 0,
			"seed": 333315600,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522957,
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
					68.51060077010538,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 125,
			"versionNonce": 939602282,
			"isDeleted": false,
			"id": "i3qnYzbMqaNGHvAo9J1up",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -739.0762013607159,
			"y": 217.03832244457988,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 79.11343184166924,
			"height": 0.40780119506018764,
			"seed": 448533232,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522957,
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
					-79.11343184166924,
					0.40780119506018764
				]
			]
		},
		{
			"type": "arrow",
			"version": 130,
			"versionNonce": 687108662,
			"isDeleted": false,
			"id": "w0MnWrqDm5D0WAZGaEBxJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1031.8774594139043,
			"y": 308.79359133311385,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 196.1523748239327,
			"height": 2.0390059753007677,
			"seed": 191548944,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522957,
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
					196.1523748239327,
					2.0390059753007677
				]
			]
		},
		{
			"type": "arrow",
			"version": 160,
			"versionNonce": 1684763690,
			"isDeleted": false,
			"id": "4IrBmxsv9uHHjMY0HLSv3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1031.8774594139043,
			"y": 309.201392528174,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 4.893614340721854,
			"height": 164.75168280430097,
			"seed": 316412432,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522957,
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
					4.893614340721854,
					-164.75168280430097
				]
			]
		},
		{
			"type": "text",
			"version": 147,
			"versionNonce": 22330230,
			"isDeleted": false,
			"id": "oyVdMWC4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -992.5156093016708,
			"y": 316.92806789983297,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 99.85621643066406,
			"height": 40,
			"seed": 482830064,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What we get\nfrom NN",
			"rawText": "What we get\nfrom NN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What we get\nfrom NN",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 204,
			"versionNonce": 2013224682,
			"isDeleted": false,
			"id": "Op3JQp9x-aEUssJ5Y2QED",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1028.615049853423,
			"y": 305.53118177263264,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 148.439635001895,
			"height": 123.56376210322571,
			"seed": 1461518864,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					148.439635001895,
					-123.56376210322571
				]
			]
		},
		{
			"type": "text",
			"version": 150,
			"versionNonce": 291101878,
			"isDeleted": false,
			"id": "xj4FtRsr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -938.6623373783343,
			"y": 137.62347506712865,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 112.08023071289062,
			"height": 40,
			"seed": 1006959856,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "averaged over\nboth solutions",
			"rawText": "averaged over\nboth solutions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "averaged over\nboth solutions",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 163,
			"versionNonce": 793244074,
			"isDeleted": false,
			"id": "N9B5MDMl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -622.2893102008416,
			"y": 160.9188635460893,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 92.09617614746094,
			"height": 20,
			"seed": 675646704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "f(x) + noise",
			"rawText": "f(x) + noise",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f(x) + noise",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 126,
			"versionNonce": 1051252214,
			"isDeleted": false,
			"id": "xFn3xWm4",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1197.8017072915027,
			"y": 129.15942329165614,
			"strokeColor": "#1971c2",
			"backgroundColor": "#d0bfff",
			"width": 137.95230102539062,
			"height": 20,
			"seed": 2115783184,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "f is not invertible",
			"rawText": "f is not invertible",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f is not invertible",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 468,
			"versionNonce": 2104503402,
			"isDeleted": false,
			"id": "d4r5sUnr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1199.9486759717215,
			"y": 377.1816645148332,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 531.1994018554688,
			"height": 175,
			"seed": 1564124688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We need to change our view of the task\nsuch that it is now \nlearning the conditional probability model\np(t | x)\n\nsuch that we need to minimize the divergence between\nthe true probability and the learned probability model",
			"rawText": "We need to change our view of the task\nsuch that it is now \nlearning the conditional probability model\np(t | x)\n\nsuch that we need to minimize the divergence between\nthe true probability and the learned probability model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We need to change our view of the task\nsuch that it is now \nlearning the conditional probability model\np(t | x)\n\nsuch that we need to minimize the divergence between\nthe true probability and the learned probability model",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "arrow",
			"version": 283,
			"versionNonce": 1917232950,
			"isDeleted": false,
			"id": "aIjQqKtfT31UjZtlQbJ8P",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 461.1428194412597,
			"y": -113.40212531899596,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 409.7002731576472,
			"height": 135.52324674412267,
			"seed": 78329072,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GVkCGxZL",
				"focus": -0.12480778621995965,
				"gap": 28.023282087744064
			},
			"endBinding": {
				"elementId": "ShSOvj4S",
				"focus": -0.14661110525680862,
				"gap": 14.444017606170178
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
					360.59690868076405,
					10.44039480282754
				],
				[
					409.7002731576472,
					135.52324674412267
				]
			]
		},
		{
			"type": "text",
			"version": 141,
			"versionNonce": 943918890,
			"isDeleted": false,
			"id": "ShSOvj4S",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 738.177005125837,
			"y": 36.565139031296894,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 342.66546630859375,
			"height": 35,
			"seed": 606791696,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "aIjQqKtfT31UjZtlQbJ8P",
					"type": "arrow"
				}
			],
			"updated": 1708212522957,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Mixture density networks",
			"rawText": "Mixture density networks",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mixture density networks",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 426,
			"versionNonce": 748179574,
			"isDeleted": false,
			"id": "jZrpKEuC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 488.2699361118073,
			"y": 75.41373561153978,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 855.01904296875,
			"height": 75,
			"seed": 389381648,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Networks that are based off of a bunch of distributions that represent the outputs\nsuch that we want to learn more about those distributions and the likelihood\nof our point belonging to it",
			"rawText": "Networks that are based off of a bunch of distributions that represent the outputs\nsuch that we want to learn more about those distributions and the likelihood\nof our point belonging to it",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Networks that are based off of a bunch of distributions that represent the outputs\nsuch that we want to learn more about those distributions and the likelihood\nof our point belonging to it",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 230,
			"versionNonce": 1143708138,
			"isDeleted": false,
			"id": "6sLQLwr_aXXenKcp1_MWw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1242.1576159858048,
			"y": 145.25216349760035,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 287.57397904084587,
			"height": 67.19693480100182,
			"seed": 1546243600,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "q3BX2cRo",
				"focus": -0.22899412761956003,
				"gap": 5.636171824485018
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
					119.22036819532548,
					59.24891025464672
				],
				[
					287.57397904084587,
					-7.9480245463551
				]
			]
		},
		{
			"type": "text",
			"version": 155,
			"versionNonce": 425906614,
			"isDeleted": false,
			"id": "q3BX2cRo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1439.4414812286636,
			"y": 81.66796712676023,
			"strokeColor": "#e03131",
			"backgroundColor": "#d0bfff",
			"width": 248.4997100830078,
			"height": 50,
			"seed": 1247116528,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "6sLQLwr_aXXenKcp1_MWw",
					"type": "arrow"
				}
			],
			"updated": 1708212522958,
			"link": "[[Expectation Maximization]]",
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Think GMM in\nExpectation Maximization",
			"rawText": "Think GMM in\nExpectation Maximization",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Think GMM in\nExpectation Maximization",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 494,
			"versionNonce": 1077202090,
			"isDeleted": false,
			"id": "gXU4LCNgK-xTHfEIb7x9M",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5537766937367596,
			"x": 699.2770374803059,
			"y": 165.59288676298593,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 168,
			"height": 140,
			"seed": 1436977680,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a5b0374752dfb54041fdf8d5c93d765cb549e4a3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 485,
			"versionNonce": 600517366,
			"isDeleted": false,
			"id": "vFyMwVtP8VCMi_zWKPbNP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 847.9083541506321,
			"y": 221.63910338366577,
			"strokeColor": "transparent",
			"backgroundColor": "#d0bfff",
			"width": 104.91701062479781,
			"height": 22.98182137495571,
			"seed": 161726704,
			"groupIds": [
				"FArwQRR-GyK8sdberTIPH"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a124003092c327e18715bd3c4334e4d1e470bcfb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 716,
			"versionNonce": 839493482,
			"isDeleted": false,
			"id": "oXFzKOOaj3MS7rH_hZ391",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 843.8845258553384,
			"y": 214.26958722038967,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 113.44858767452934,
			"height": 36.5963186046869,
			"seed": 341848080,
			"groupIds": [
				"FArwQRR-GyK8sdberTIPH"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 744,
			"versionNonce": 173431862,
			"isDeleted": false,
			"id": "KHUYV3oflO4KD3uQUPvaI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 953.6734816693995,
			"y": 261.84480140648225,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 32.93668674421821,
			"height": 58.554109767499035,
			"seed": 654290448,
			"groupIds": [
				"FArwQRR-GyK8sdberTIPH"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					32.93668674421821,
					-29.277054883749518
				],
				[
					0,
					-58.554109767499035
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "image",
			"version": 332,
			"versionNonce": 838150698,
			"isDeleted": false,
			"id": "8EfPGa1eDDlamkQIDM20O",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1131.9411748051207,
			"y": 217.63505352201992,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 65.41121473811074,
			"height": 30.423820808423603,
			"seed": 1564576496,
			"groupIds": [
				"hy0dE0lkIL4X1afd7OCNm"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a222ab9a8e5d7bd8c568f9f71ddb8bef5ec0da2b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 830,
			"versionNonce": 1927898486,
			"isDeleted": false,
			"id": "eVc_Eynw-4PnKlqtZXS75",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 1108.8575292341577,
			"y": 215.03989073627713,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 113.44858767452934,
			"height": 36.5963186046869,
			"seed": 2051721456,
			"groupIds": [
				"hy0dE0lkIL4X1afd7OCNm"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 797,
			"versionNonce": 383931626,
			"isDeleted": false,
			"id": "xM0mYHt_qOaxaS9McsMqo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1220.7581553314894,
			"y": 262.61510492237016,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 32.93668674421821,
			"height": 58.554109767499035,
			"seed": 702819056,
			"groupIds": [
				"hy0dE0lkIL4X1afd7OCNm"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					32.93668674421821,
					-29.277054883749518
				],
				[
					0,
					-58.554109767499035
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 930,
			"versionNonce": 2127120054,
			"isDeleted": false,
			"id": "e2wgwThfWegfFI2pnbkQ1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 575.3691437710494,
			"y": 221.25994700840556,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 113.44858767452934,
			"height": 36.5963186046869,
			"seed": 1367577840,
			"groupIds": [
				"HRSeC_bKHvOvH_RXBdkTl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 807,
			"versionNonce": 576464810,
			"isDeleted": false,
			"id": "2BGKGNxFFpcdt4YcsSAdd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 687.2697698683812,
			"y": 269.2601189338782,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 32.93668674421821,
			"height": 58.554109767499035,
			"seed": 941848304,
			"groupIds": [
				"HRSeC_bKHvOvH_RXBdkTl"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					32.93668674421821,
					-29.277054883749518
				],
				[
					0,
					-58.554109767499035
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 234,
			"versionNonce": 1587216374,
			"isDeleted": false,
			"id": "ldQLf7N6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 598.2459230966444,
			"y": 230.08189310117996,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 66.83213806152344,
			"height": 20,
			"seed": 1716724752,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vector x",
			"rawText": "Vector x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vector x",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 92,
			"versionNonce": 747479658,
			"isDeleted": false,
			"id": "4I0cI0eU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 771.6922703785735,
			"y": 324.165207771184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 20.6080322265625,
			"height": 20,
			"seed": 94060784,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "NN",
			"rawText": "NN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "NN",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 133,
			"versionNonce": 1717801270,
			"isDeleted": false,
			"id": "NqL7sPZh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 864.7949308410507,
			"y": 254.32028472646743,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 82.35218811035156,
			"height": 40,
			"seed": 1882933488,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "3J5nS5RmT-g8rZOX0zVVl",
					"type": "arrow"
				},
				{
					"id": "wGbBChvFsE_KpD3E3IXIV",
					"type": "arrow"
				}
			],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Parameter\nvector",
			"rawText": "Parameter\nvector",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Parameter\nvector",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 125,
			"versionNonce": 1346487594,
			"isDeleted": false,
			"id": "SGOpfTXn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 992.3132907317396,
			"y": 307.14050777903435,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 107.56822204589844,
			"height": 20,
			"seed": 755107568,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Mixture model",
			"rawText": "Mixture model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mixture model",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 562559606,
			"isDeleted": false,
			"id": "hTt9iiAI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1131.623766186798,
			"y": 253.01069241937898,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 83.0081787109375,
			"height": 60,
			"seed": 1519154416,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Conditional\nprobability\ndensity",
			"rawText": "Conditional\nprobability\ndensity",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Conditional\nprobability\ndensity",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 423,
			"versionNonce": 384012266,
			"isDeleted": false,
			"id": "3J5nS5RmT-g8rZOX0zVVl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 905.4952594659401,
			"y": 306.30264480246,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 2.1321995947154875,
			"height": 78.0771639454656,
			"seed": 2000276208,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NqL7sPZh",
				"focus": 0.03233687158680035,
				"gap": 11.982360075992574
			},
			"endBinding": {
				"elementId": "IkzIsbhjUqInvVT1cn5gb",
				"focus": 0.0003190490171834176,
				"gap": 11.182048451759101
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
					2.1321995947154875,
					78.0771639454656
				]
			]
		},
		{
			"type": "image",
			"version": 175,
			"versionNonce": 1724726198,
			"isDeleted": false,
			"id": "IkzIsbhjUqInvVT1cn5gb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 778.3796140886047,
			"y": 395.5618571996847,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 260.62637883940045,
			"height": 58.721375479247634,
			"seed": 1532588784,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "3J5nS5RmT-g8rZOX0zVVl",
					"type": "arrow"
				}
			],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1aed2ca66ab831139587a32ac46cfbc96a0ace5d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 274,
			"versionNonce": 612237994,
			"isDeleted": false,
			"id": "JgUk7bph8IfLx6VscK61h",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 928.8470544575689,
			"y": 447.6092513244673,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 71.29678986965371,
			"height": 39.67821349267683,
			"seed": 1535389712,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "9yptzKys",
				"focus": 0.0557744707179253,
				"gap": 13.00935586702883
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
					1.8599162574691945,
					34.71843680609231
				],
				[
					-69.43687361218451,
					39.67821349267683
				]
			]
		},
		{
			"type": "text",
			"version": 162,
			"versionNonce": 1817728246,
			"isDeleted": false,
			"id": "9yptzKys",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 759.5846170926134,
			"y": 469.9282464140981,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 86.81620788574219,
			"height": 40,
			"seed": 907439856,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "JgUk7bph8IfLx6VscK61h",
					"type": "arrow"
				}
			],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Prior of\ndistribution",
			"rawText": "Prior of\ndistribution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Prior of\ndistribution",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 448,
			"versionNonce": 1673272682,
			"isDeleted": false,
			"id": "av_aTHQNKkTQywM94nekO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 974.1050167226534,
			"y": 446.3693071528212,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 0.9744019446403911,
			"height": 64.10143500187223,
			"seed": 1015812336,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "Zx12srK0fL1f8yxRtuMh_",
				"focus": 0.16531132306610125,
				"gap": 5.0613773755536045
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
					39.67821349267683
				],
				[
					0.9744019446403911,
					64.10143500187223
				]
			]
		},
		{
			"type": "image",
			"version": 321,
			"versionNonce": 1538147894,
			"isDeleted": false,
			"id": "Zx12srK0fL1f8yxRtuMh_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 725.0570983566076,
			"y": 515.532119530247,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 431.97406447950954,
			"height": 88.15797234275705,
			"seed": 1738840304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "av_aTHQNKkTQywM94nekO",
					"type": "arrow"
				},
				{
					"id": "AKfB9SMMzOWyqFtT4jY8E",
					"type": "arrow"
				}
			],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0732dc9282a0e9f4feaef8974b644bb34c458fa9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 309,
			"versionNonce": 837345322,
			"isDeleted": false,
			"id": "yAtiAFhu7tEOIUP3phd4A",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1248.8632244704795,
			"y": 299.2152810884056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 84.75392782742273,
			"height": 65.24319061798474,
			"seed": 1699128848,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "B4WVK16c2L_E2hJVc3bRN",
				"focus": -0.13660720476501195,
				"gap": 16.00097981587149
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
					71.93374375229189,
					19.896567420846623
				],
				[
					84.75392782742273,
					65.24319061798474
				]
			]
		},
		{
			"type": "text",
			"version": 150,
			"versionNonce": 1706299254,
			"isDeleted": false,
			"id": "7qY3W80C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1294.1022295952066,
			"y": 270.9009351433542,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 177.3603973388672,
			"height": 40,
			"seed": 1691415280,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Optimize the Likelihood\nof this model",
			"rawText": "Optimize the Likelihood\nof this model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Optimize the Likelihood\nof this model",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 179,
			"versionNonce": 183454442,
			"isDeleted": false,
			"id": "B4WVK16c2L_E2hJVc3bRN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1223.1670786649906,
			"y": 380.4594515222618,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 290.1511006611386,
			"height": 64.00391926348647,
			"seed": 173352976,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "yAtiAFhu7tEOIUP3phd4A",
					"type": "arrow"
				}
			],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f0b64e743b0df6337ecd066100b51279963b67c8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 691,
			"versionNonce": 1454289078,
			"isDeleted": false,
			"id": "wGbBChvFsE_KpD3E3IXIV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 905.8802066479277,
			"y": 304.2277138446457,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 281.71921486373185,
			"height": 84.74420353746996,
			"seed": 1783021072,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NqL7sPZh",
				"focus": -0.6357178121008368,
				"gap": 9.907429118178243
			},
			"endBinding": {
				"elementId": "k3mwOHSn",
				"focus": -0.7274305939986818,
				"gap": 4.443037401383322
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
					-115.43571349490367,
					75.55792156030066
				],
				[
					-234.2469665278495,
					84.74420353746996
				],
				[
					-281.71921486373185,
					62.88901309994549
				]
			]
		},
		{
			"type": "text",
			"version": 366,
			"versionNonce": 895114666,
			"isDeleted": false,
			"id": "k3mwOHSn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 338.9653298710938,
			"y": 339.27904192572623,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 280.75262451171875,
			"height": 60,
			"seed": 1901392624,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "wGbBChvFsE_KpD3E3IXIV",
					"type": "arrow"
				}
			],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "These parameters are subject\nto certain constraints which can be\nmodeled in the output layer",
			"rawText": "These parameters are subject\nto certain constraints which can be\nmodeled in the output layer",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "These parameters are subject\nto certain constraints which can be\nmodeled in the output layer",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 308,
			"versionNonce": 709044726,
			"isDeleted": false,
			"id": "re2nIJXGdmUk62rhvgX2B",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 329.2603436557084,
			"y": 402.5123977110338,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 150.44597459152348,
			"height": 63.92339692944561,
			"seed": 400176368,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "63e2c0de5a6dd97eadbd7e56eca4a80e06666d03",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 308,
			"versionNonce": 1851070570,
			"isDeleted": false,
			"id": "YCUS3WUpglh9wRx2FteOO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 515.1746283155798,
			"y": 411.8282320152607,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 112.33155882977462,
			"height": 43.20444570375947,
			"seed": 783391472,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3f0c6a98da54be803ba992476fda0eca5f7393b5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 142,
			"versionNonce": 527858486,
			"isDeleted": false,
			"id": "lFPIGqLQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 849.3533540003034,
			"y": 716.6361015065935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 230.47975158691406,
			"height": 25,
			"seed": 1410952208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "AKfB9SMMzOWyqFtT4jY8E",
					"type": "arrow"
				}
			],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The problem with GMMs",
			"rawText": "The problem with GMMs",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The problem with GMMs",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 57,
			"versionNonce": 363494186,
			"isDeleted": false,
			"id": "AKfB9SMMzOWyqFtT4jY8E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 970.1241256450058,
			"y": 607.9083827619365,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 0,
			"height": 93.7242938334607,
			"seed": 668134928,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Zx12srK0fL1f8yxRtuMh_",
				"focus": -0.1346376898052076,
				"gap": 4.218290888932472
			},
			"endBinding": {
				"elementId": "lFPIGqLQ",
				"focus": 0.04799463565162439,
				"gap": 15.003424911196248
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
					93.7242938334607
				]
			]
		},
		{
			"type": "image",
			"version": 182,
			"versionNonce": 823043638,
			"isDeleted": false,
			"id": "J1OYSHSiLmAFPc3QeJGXN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 514.4471905402555,
			"y": 706.6458290471032,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 269.76263828244845,
			"height": 193.52537094175648,
			"seed": 1006113008,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "r6XS_6XFn5ixpwbUjzi-2",
					"type": "arrow"
				}
			],
			"updated": 1708216626142,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d0d1d36cc01a3c23754ae18d7782b8b99eb0a196",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 379,
			"versionNonce": 1506117098,
			"isDeleted": false,
			"id": "kz26hJV9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 760.9272931549317,
			"y": 751.0094552395901,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 405.4088134765625,
			"height": 140,
			"seed": 167311600,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Gaussian mixture models capture localized\nhigh density spots in our space and identify them\nas a distribution, but this gets rather out of\nhand with global effects and spaces where\nour data is distributed across every possible\ncorner of our space IN HIGH DIMENSIONAL space\nfor example when using pictures",
			"rawText": "Gaussian mixture models capture localized\nhigh density spots in our space and identify them\nas a distribution, but this gets rather out of\nhand with global effects and spaces where\nour data is distributed across every possible\ncorner of our space IN HIGH DIMENSIONAL space\nfor example when using pictures",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gaussian mixture models capture localized\nhigh density spots in our space and identify them\nas a distribution, but this gets rather out of\nhand with global effects and spaces where\nour data is distributed across every possible\ncorner of our space IN HIGH DIMENSIONAL space\nfor example when using pictures",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "text",
			"version": 431,
			"versionNonce": 867018166,
			"isDeleted": false,
			"id": "2rJtXctP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 659.6266921764015,
			"y": 905.424758946913,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 598.9132080078125,
			"height": 100,
			"seed": 379362320,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708212522958,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Thus it is better to use Boltzmann machines\nBMs or rather RBMs are quite good at understanding\nglobal effects by drawing conclusions between inputs and outputs\nwithout learning features specific to that input... only the transitions that\nlead to the output aka Global effects",
			"rawText": "Thus it is better to use Boltzmann machines\nBMs or rather RBMs are quite good at understanding\nglobal effects by drawing conclusions between inputs and outputs\nwithout learning features specific to that input... only the transitions that\nlead to the output aka Global effects",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Thus it is better to use Boltzmann machines\nBMs or rather RBMs are quite good at understanding\nglobal effects by drawing conclusions between inputs and outputs\nwithout learning features specific to that input... only the transitions that\nlead to the output aka Global effects",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 467,
			"versionNonce": 1562586742,
			"isDeleted": false,
			"id": "pnG9iGKxMJMfiwtV2MaYj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 28.581204762370703,
			"y": 19.377815785238056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 291.2771839560761,
			"height": 1104.4281642157478,
			"seed": 775143664,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "EfWErfAq",
				"focus": 0.059853102525373486,
				"gap": 3.663552846252969
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
					11.081038507751714,
					349.62077015503377
				],
				[
					-280.1961454483244,
					492.0577480116179
				],
				[
					-257.5406436403798,
					1104.4281642157478
				]
			]
		},
		{
			"type": "text",
			"version": 322,
			"versionNonce": 62075894,
			"isDeleted": false,
			"id": "EfWErfAq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -538.8039877056922,
			"y": 1127.4695328472387,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 587.2463989257812,
			"height": 70,
			"seed": 877016304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "r6XS_6XFn5ixpwbUjzi-2",
					"type": "arrow"
				},
				{
					"id": "pnG9iGKxMJMfiwtV2MaYj",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Conditional Restricted Boltzmann Machines\n(CRBM)",
			"rawText": "Conditional Restricted Boltzmann Machines\n(CRBM)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Conditional Restricted Boltzmann Machines\n(CRBM)",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "arrow",
			"version": 704,
			"versionNonce": 1139879018,
			"isDeleted": false,
			"id": "r6XS_6XFn5ixpwbUjzi-2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 595.5366223528971,
			"y": 908.0688259391701,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 673.9040307904324,
			"height": 209.1120128405513,
			"seed": 1838907120,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216631298,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "J1OYSHSiLmAFPc3QeJGXN",
				"focus": -1.0516484323523911,
				"gap": 7.897625950310328
			},
			"endBinding": {
				"elementId": "EfWErfAq",
				"focus": 0.4709174871929175,
				"gap": 10.288694067517326
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
					-581.2653091461116,
					8.616151890902529
				],
				[
					-673.9040307904324,
					209.1120128405513
				]
			]
		},
		{
			"type": "image",
			"version": 606,
			"versionNonce": 1623648310,
			"isDeleted": false,
			"id": "ckwEFBccd56MeL9djDZay",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 661.5821643646442,
			"y": 1905.282216894596,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 403.2719901871189,
			"height": 62.23333181899982,
			"seed": 86413552,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708218247815,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0cc2d4da6a9879d99c6f2320990680238d585b86",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 512,
			"versionNonce": 1850826218,
			"isDeleted": false,
			"id": "Ga7ph4bkgS4XJ3OARaELE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2452.443340708077,
			"y": 2357.779917049323,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 486,
			"height": 54,
			"seed": 812441840,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bbb32d99227583705b743363c020f83d9727deab",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 520,
			"versionNonce": 688001194,
			"isDeleted": false,
			"id": "2muNzVq7tPy9PAlDIjdla",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2489.8249801937213,
			"y": 2190.726696801174,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 662,
			"height": 109,
			"seed": 480664304,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a0ee93c7c23aa945852fa7391fb107d5e49eb93c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 742,
			"versionNonce": 411986794,
			"isDeleted": false,
			"id": "NsnRldnX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2319.4115240942206,
			"y": 2412.9774791448476,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 758.779296875,
			"height": 175,
			"seed": 1683543280,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Can be interpreted as a two-layer neural network.\nThe lower the free energy the more likely the joint configuration\n(x,y) is to occur in the wild!\n\nThus we perform coordinate gradient descent where we set x to a certain\nvalue and minimize according to y then set y to a certain value and minimize\naccording to x",
			"rawText": "Can be interpreted as a two-layer neural network.\nThe lower the free energy the more likely the joint configuration\n(x,y) is to occur in the wild!\n\nThus we perform coordinate gradient descent where we set x to a certain\nvalue and minimize according to y then set y to a certain value and minimize\naccording to x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Can be interpreted as a two-layer neural network.\nThe lower the free energy the more likely the joint configuration\n(x,y) is to occur in the wild!\n\nThus we perform coordinate gradient descent where we set x to a certain\nvalue and minimize according to y then set y to a certain value and minimize\naccording to x",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "image",
			"version": 536,
			"versionNonce": 1933667882,
			"isDeleted": false,
			"id": "oHHTvwAfvqtvjb12e2v2d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2535.293069715963,
			"y": 2590.6346425679853,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 364,
			"height": 72,
			"seed": 2105540112,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EziFciCN9eqpUr6heLHdU",
					"type": "arrow"
				}
			],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "50c36a584ee9647a13762db7081bdb75ade49b1b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 1264,
			"versionNonce": 968263926,
			"isDeleted": false,
			"id": "97FLdIse",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2960.240729652862,
			"y": 3459.1826708515246,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 703.71923828125,
			"height": 75,
			"seed": 1100692208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We would like to proceed with a stochastic gradient descent procedure\nWe update the weights and both biases via the LR and gradient,\nthe gradient of our objective is given by",
			"rawText": "We would like to proceed with a stochastic gradient descent procedure\nWe update the weights and both biases via the LR and gradient,\nthe gradient of our objective is given by",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We would like to proceed with a stochastic gradient descent procedure\nWe update the weights and both biases via the LR and gradient,\nthe gradient of our objective is given by",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 491,
			"versionNonce": 1751608234,
			"isDeleted": false,
			"id": "9w6a2mwwTgMxJIwO5rlD-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2507.686413024715,
			"y": 2673.4774517377805,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 91.16538053648492,
			"height": 79.34764602249606,
			"seed": 1403773456,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216395355,
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
					-91.16538053648492,
					79.34764602249606
				]
			]
		},
		{
			"type": "text",
			"version": 492,
			"versionNonce": 412116586,
			"isDeleted": false,
			"id": "hMX9RftN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2310.0950205900917,
			"y": 2769.707575637404,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 157.1398468017578,
			"height": 25,
			"seed": 905922288,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Standard CRBM",
			"rawText": "Standard CRBM",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Standard CRBM",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 1434,
			"versionNonce": 1843983798,
			"isDeleted": false,
			"id": "EziFciCN9eqpUr6heLHdU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2846.1800944611077,
			"y": 2669.256832268499,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 99.60661947504832,
			"height": 81.88001770406527,
			"seed": 297898736,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216395387,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oHHTvwAfvqtvjb12e2v2d",
				"focus": -0.3411845044113983,
				"gap": 6.622189700513445
			},
			"endBinding": {
				"elementId": "IDNhkZTU",
				"focus": 0.2186628925511702,
				"gap": 13.505982301701351
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
					99.60661947504832,
					81.88001770406527
				]
			]
		},
		{
			"type": "text",
			"version": 500,
			"versionNonce": 738546666,
			"isDeleted": false,
			"id": "IDNhkZTU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2863.358049310266,
			"y": 2764.6428322742654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 181.73980712890625,
			"height": 25,
			"seed": 1127695888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "EziFciCN9eqpUr6heLHdU",
					"type": "arrow"
				}
			],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Higher order CRBM",
			"rawText": "Higher order CRBM",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Higher order CRBM",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 545,
			"versionNonce": 641524074,
			"isDeleted": false,
			"id": "TEqvlnWD9vKQwQuR9vKIr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2166.8317227449393,
			"y": 2809.4532478270007,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 149.06720353619977,
			"height": 44.93413312335208,
			"seed": 727511056,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5399d3937af064035d71662a3745b46f3012d035",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 535,
			"versionNonce": 1873880106,
			"isDeleted": false,
			"id": "T_TcU-YXGhbCR0it7eiIx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2311.542501521974,
			"y": 2807.692417930966,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 250.47500883761612,
			"height": 55.90960018696788,
			"seed": 2045591568,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0afc5abe8fa25061d8fd314a8a40f61b3f3ea83",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 522,
			"versionNonce": 1863257834,
			"isDeleted": false,
			"id": "T6yNUCsn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2333.112506091871,
			"y": 2871.0024429001646,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 77.33992004394531,
			"height": 25,
			"seed": 1189708528,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Additive",
			"rawText": "Additive",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Additive",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 533,
			"versionNonce": 149004714,
			"isDeleted": false,
			"id": "ZmrmBhQ0NLBL70NY2Qxet",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2264.897528063655,
			"y": 2899.4711331741732,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 170.43818288241812,
			"height": 123.70513273723896,
			"seed": 329000176,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cd4eb941ea5c5764e065c0b5c14bfd4c65721171",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 518,
			"versionNonce": 1481890922,
			"isDeleted": false,
			"id": "n4K8q7DKzM2XvxioskCb0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2771.905298014607,
			"y": 2797.315073617598,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 384.0601592789203,
			"height": 67.09869671262335,
			"seed": 885246992,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8a49189668af2e76c9370ae00b59946c8340461f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 493,
			"versionNonce": 1529921322,
			"isDeleted": false,
			"id": "IsGKaqfi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2886.2174087838557,
			"y": 2875.2230623694463,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 127.57984924316406,
			"height": 25,
			"seed": 397742832,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Multiplicative",
			"rawText": "Multiplicative",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Multiplicative",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 546,
			"versionNonce": 501434858,
			"isDeleted": false,
			"id": "a7YqVxFbiz-Jq-VTCORhe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2871.4988909306744,
			"y": 2912.059805744118,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 150.95405798862123,
			"height": 184.62842477069827,
			"seed": 1629162000,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0fb9e45d1795c97223225c72c522896dd707a6e2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 1698,
			"versionNonce": 1193671222,
			"isDeleted": false,
			"id": "4urkPr8F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6594.584011714099,
			"y": 4345.418874221549,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 860.279052734375,
			"height": 400,
			"seed": 579328888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "RD9mq0uEMN4YMDF9HMPrC",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We notice that we can represent the\nconditional distributions in a much\neasier way than the joint distribution\nof the latent and in the input.\n\nRemember that that their distributions are Bernoulli so the process\nof sampling from the conditional goes as follows:\n\nWe sample from a uniform distribution a value between 0 and 1\n\nwe compute the probability that our jth hidden value is 1 given our input x\n\nif this value is greater than the uniform we set the jth unit to 1 else we set it to 0\n\n\nwhich leads our jth unit to be equal to 1 with a probability of p(hj==1 | xi)",
			"rawText": "We notice that we can represent the\nconditional distributions in a much\neasier way than the joint distribution\nof the latent and in the input.\n\nRemember that that their distributions are Bernoulli so the process\nof sampling from the conditional goes as follows:\n\nWe sample from a uniform distribution a value between 0 and 1\n\nwe compute the probability that our jth hidden value is 1 given our input x\n\nif this value is greater than the uniform we set the jth unit to 1 else we set it to 0\n\n\nwhich leads our jth unit to be equal to 1 with a probability of p(hj==1 | xi)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We notice that we can represent the\nconditional distributions in a much\neasier way than the joint distribution\nof the latent and in the input.\n\nRemember that that their distributions are Bernoulli so the process\nof sampling from the conditional goes as follows:\n\nWe sample from a uniform distribution a value between 0 and 1\n\nwe compute the probability that our jth hidden value is 1 given our input x\n\nif this value is greater than the uniform we set the jth unit to 1 else we set it to 0\n\n\nwhich leads our jth unit to be equal to 1 with a probability of p(hj==1 | xi)",
			"lineHeight": 1.25,
			"baseline": 393
		},
		{
			"type": "image",
			"version": 1324,
			"versionNonce": 1724474550,
			"isDeleted": false,
			"id": "tE438Fon",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5698.562617744924,
			"y": 4791.855536822581,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 199.3163531599924,
			"height": 24.732686158539202,
			"seed": 94065,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "tJwzxrxvUyR8Z8gn1GKpf",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0edd9c2d94201837a21fb4a0d69930b86e0f8193",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 1492,
			"versionNonce": 1198796598,
			"isDeleted": false,
			"id": "XFSz3JRt59hOlnrNzUiVZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5281.6375960733885,
			"y": 4824.645624486394,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 233.45798569499385,
			"height": 14.21048608578234,
			"seed": 826768760,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-88.64636558273685,
					-14.21048608578234
				],
				[
					-140.43383267512854,
					-6.684112730777997
				],
				[
					-233.45798569499385,
					-6.090208322477886
				]
			]
		},
		{
			"type": "text",
			"version": 1332,
			"versionNonce": 315938934,
			"isDeleted": false,
			"id": "d3sokiXG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5299.978423786249,
			"y": 4806.8585493722885,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 237.31248474121094,
			"height": 80,
			"seed": 1654776584,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "the hidden units are\nconditionally independent\ngiven x due to a local markov\nproperty (the restriction)",
			"rawText": "the hidden units are\nconditionally independent\ngiven x due to a local markov\nproperty (the restriction)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the hidden units are\nconditionally independent\ngiven x due to a local markov\nproperty (the restriction)",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "image",
			"version": 1102,
			"versionNonce": 382622134,
			"isDeleted": false,
			"id": "SfQcp7md",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5726.0462501503725,
			"y": 4884.486327848676,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 290.53098197904757,
			"height": 19.14351431644887,
			"seed": 35757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d68fab0532591d3932daafad444bb1016db263c2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 1145,
			"versionNonce": 2055582454,
			"isDeleted": false,
			"id": "gYpDm3EJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5741.655735538284,
			"y": 4960.0911138804295,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 313.27715336872404,
			"height": 21.96408086348988,
			"seed": 92621,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ebf34d15c595014e0cea4549b73b2b759ff83303",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 1101,
			"versionNonce": 947905590,
			"isDeleted": false,
			"id": "9ezLqFic",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5814.881862128458,
			"y": 4836.052112649054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 451.9849548339844,
			"height": 40,
			"seed": 179246600,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Since h and x are given via bernoulli distributions, we can\nderive the following",
			"rawText": "Since h and x are given via bernoulli distributions, we can\nderive the following",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Since h and x are given via bernoulli distributions, we can\nderive the following",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 1086,
			"versionNonce": 849472886,
			"isDeleted": false,
			"id": "sRuClUB7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -5811.404877140626,
			"y": 4913.7135961872455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 438.096923828125,
			"height": 40,
			"seed": 2085665656,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "note that the conditional relation is symmetric between\nthe latent and the input",
			"rawText": "note that the conditional relation is symmetric between\nthe latent and the input",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "note that the conditional relation is symmetric between\nthe latent and the input",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 320,
			"versionNonce": 1704286058,
			"isDeleted": false,
			"id": "gOtDtMCU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2741.891644334325,
			"y": 2316.454430987564,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 270.20855712890625,
			"height": 40,
			"seed": 1139147528,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "softplus which is a smooth version\nof relu",
			"rawText": "softplus which is a smooth version\nof relu",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "softplus which is a smooth version\nof relu",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 314,
			"versionNonce": 1485494826,
			"isDeleted": false,
			"id": "-sUyQGJlRryTTlfAC90cz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2792.1334561957306,
			"y": 2275.2128583842136,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 75.34518071765899,
			"height": 32.517393783410625,
			"seed": 1759425544,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					56.31060874688205,
					17.44835763987885
				],
				[
					75.34518071765899,
					32.517393783410625
				]
			]
		},
		{
			"type": "image",
			"version": 848,
			"versionNonce": 1061291242,
			"isDeleted": false,
			"id": "8V-IcxqjbCgPz6IC0A4fU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2435.4956118449077,
			"y": 3644.483693341105,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 645.2232780331811,
			"height": 57.01326379172506,
			"seed": 951249528,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6fa4af893c110fe256a85c5e2c3b5f9e4b29fcf1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 609,
			"versionNonce": 965878838,
			"isDeleted": false,
			"id": "FdUuSBtW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -743.1752778611682,
			"y": 1206.6684726368285,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 997.298828125,
			"height": 150,
			"seed": 1857297130,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216795807,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CRBMS are a special kind of RBM that specializes in working with structured output\nsomething that the RBMs have never been able to tackle.\n\nThe difficulty in structured output prediction is that the output space typically has an exponential\nnumber of possible configuration, exact gradients are intractable,\ninstead approximations like Contrastive divergence will be used (or even better algorithms).",
			"rawText": "CRBMS are a special kind of RBM that specializes in working with structured output\nsomething that the RBMs have never been able to tackle.\n\nThe difficulty in structured output prediction is that the output space typically has an exponential\nnumber of possible configuration, exact gradients are intractable,\ninstead approximations like Contrastive divergence will be used (or even better algorithms).",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CRBMS are a special kind of RBM that specializes in working with structured output\nsomething that the RBMs have never been able to tackle.\n\nThe difficulty in structured output prediction is that the output space typically has an exponential\nnumber of possible configuration, exact gradients are intractable,\ninstead approximations like Contrastive divergence will be used (or even better algorithms).",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "line",
			"version": 376,
			"versionNonce": 1607567350,
			"isDeleted": false,
			"id": "AGwyfo_2EEwvEZtPGvbrL",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 196.59448207030584,
			"y": 1220.338333960685,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 354.60784586955344,
			"height": 1.3157990570300626,
			"seed": 1106258294,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					354.60784586955344,
					1.3157990570300626
				]
			]
		},
		{
			"type": "text",
			"version": 281,
			"versionNonce": 260643126,
			"isDeleted": false,
			"id": "iHhKxa2c",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 202.38254185649976,
			"y": 1196.5223528200875,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 246.32049560546875,
			"height": 20,
			"seed": 1258633718,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "examples of structured output",
			"rawText": "examples of structured output",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "examples of structured output",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 453,
			"versionNonce": 482116214,
			"isDeleted": false,
			"id": "w6Mi0Owz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 559.1510101045235,
			"y": 1175.0618601377219,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 327.23272705078125,
			"height": 80,
			"seed": 1560671402,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "the output space has arbitrary\nstructure but the set of likely\noutput configurations is relatively\nsmall, such as in multi-label classification",
			"rawText": "the output space has arbitrary\nstructure but the set of likely\noutput configurations is relatively\nsmall, such as in multi-label classification",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the output space has arbitrary\nstructure but the set of likely\noutput configurations is relatively\nsmall, such as in multi-label classification",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 932,
			"versionNonce": 1924458858,
			"isDeleted": false,
			"id": "DcTkOQ_DeqB2JRn1r8O71",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 852.1355526617401,
			"y": 1214.4487854580757,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 143.87206239409124,
			"height": 5.477764224974635,
			"seed": 725498998,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216649562,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "nWx5sL3DETCIXt4atseHm",
				"focus": 0.26901072467817344,
				"gap": 10.918570743282658
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
					70.4701178115788,
					-3.524509989530088
				],
				[
					143.87206239409124,
					-5.477764224974635
				]
			]
		},
		{
			"type": "image",
			"version": 381,
			"versionNonce": 54467702,
			"isDeleted": false,
			"id": "Xx6fdShZ8tO3RqeUrSdug",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1007.5629827316811,
			"y": 1161.7223632995406,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 188.27619056995613,
			"height": 125.51746037997076,
			"seed": 1120741610,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "78ae3aa134d670b3b52c56eb791c9264798564c2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 574,
			"versionNonce": 156245430,
			"isDeleted": false,
			"id": "nWx5sL3DETCIXt4atseHm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1006.9261857991139,
			"y": 1161.8768064610297,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 190.50281126854972,
			"height": 122.98633447150434,
			"seed": 1945102250,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "DcTkOQ_DeqB2JRn1r8O71",
					"type": "arrow"
				}
			],
			"updated": 1708216645700,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 290,
			"versionNonce": 6334518,
			"isDeleted": false,
			"id": "hDJ-sBcnQDJVp7zDa5Bab",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1207.7241800348274,
			"y": 1186.2533189794383,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 179.64820745777752,
			"height": 1.4108497967888525,
			"seed": 186423990,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					179.64820745777752,
					-1.4108497967888525
				]
			]
		},
		{
			"type": "line",
			"version": 278,
			"versionNonce": 1237987702,
			"isDeleted": false,
			"id": "H5VfhnPmNJjh11UOqOJ6T",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1242.995424954548,
			"y": 1165.0905720276057,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 74.77503922980804,
			"seed": 1601351978,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					74.77503922980804
				]
			]
		},
		{
			"type": "line",
			"version": 309,
			"versionNonce": 1471189686,
			"isDeleted": false,
			"id": "QUSvlAV2n89a6r5ovrnOm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1277.939515825094,
			"y": 1164.9025013321273,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 74.77503922980804,
			"seed": 780672118,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					74.77503922980804
				]
			]
		},
		{
			"type": "line",
			"version": 293,
			"versionNonce": 884526070,
			"isDeleted": false,
			"id": "ppUJVIneq7P4-E_hdSQJ5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1312.8842675428352,
			"y": 1165.6407707346148,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 74.77503922980804,
			"seed": 1325405610,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					74.77503922980804
				]
			]
		},
		{
			"type": "line",
			"version": 299,
			"versionNonce": 1323818294,
			"isDeleted": false,
			"id": "jpjc3pgAWcqc8lqC4XK-c",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1352.2586356755016,
			"y": 1167.3633993404185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 74.77503922980804,
			"seed": 2027395434,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					74.77503922980804
				]
			]
		},
		{
			"type": "text",
			"version": 258,
			"versionNonce": 195217014,
			"isDeleted": false,
			"id": "sGQrDM1K",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1208.0101588298783,
			"y": 1168.821808034265,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 32.091583251953125,
			"height": 14.832114182587476,
			"seed": 757480246,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"fontSize": 11.865691346069982,
			"fontFamily": 1,
			"text": "house",
			"rawText": "house",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "house",
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "text",
			"version": 309,
			"versionNonce": 1538164662,
			"isDeleted": false,
			"id": "gg4NzXGN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1246.4001677592278,
			"y": 1167.7812785560154,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 27.525955200195312,
			"height": 13.411745652545356,
			"seed": 496745066,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"fontSize": 10.729396522036286,
			"fontFamily": 1,
			"text": "horse",
			"rawText": "horse",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "horse",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 286,
			"versionNonce": 1328554230,
			"isDeleted": false,
			"id": "7BuvOvkG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1283.8058174852606,
			"y": 1166.9358924958628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.795166015625,
			"height": 14.257131712697914,
			"seed": 2053564470,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"fontSize": 11.405705370158332,
			"fontFamily": 1,
			"text": "tree",
			"rawText": "tree",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "tree",
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "text",
			"version": 287,
			"versionNonce": 699175478,
			"isDeleted": false,
			"id": "3aXNlPpX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1318.5044794021726,
			"y": 1167.6312709281651,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.997512817382812,
			"height": 12.823483877908055,
			"seed": 243809578,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"fontSize": 10.258787102326444,
			"fontFamily": 1,
			"text": "human",
			"rawText": "human",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "human",
			"lineHeight": 1.25,
			"baseline": 8
		},
		{
			"type": "text",
			"version": 287,
			"versionNonce": 1980291958,
			"isDeleted": false,
			"id": "o17ca1S4",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1356.1562189290348,
			"y": 1169.630479308809,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 30.61419677734375,
			"height": 14.26953270887244,
			"seed": 1964672746,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"fontSize": 11.415626167097951,
			"fontFamily": 1,
			"text": "grass",
			"rawText": "grass",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "grass",
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "text",
			"version": 259,
			"versionNonce": 445250742,
			"isDeleted": false,
			"id": "KPOBPgeg",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1221.5450978754823,
			"y": 1205.4891883578102,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 155.02432250976562,
			"height": 20,
			"seed": 1339790186,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216645700,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1    0   1    0    1",
			"rawText": "1    0   1    0    1",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1    0   1    0    1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 417,
			"versionNonce": 1429067382,
			"isDeleted": false,
			"id": "D5AdvMO7TMQp3XuS4iQO6",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 197.8279924794915,
			"y": 1221.4151313264938,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 352.82456180685676,
			"height": 112.47538213197686,
			"seed": 145386410,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					168.34533079139283,
					10.014256294196457
				],
				[
					196.81334160484516,
					108.8921350961964
				],
				[
					352.82456180685676,
					112.47538213197686
				]
			]
		},
		{
			"type": "text",
			"version": 318,
			"versionNonce": 1633130422,
			"isDeleted": false,
			"id": "Ck577QYZ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 556.6780211862754,
			"y": 1301.0851936699776,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 294.5606689453125,
			"height": 100,
			"seed": 1829076522,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "the output space is arbitrarily\nstructured but where the variability \nin it is much greater than multi-label\nclassification, such as in image\ndenoising or pixel labeling.",
			"rawText": "the output space is arbitrarily\nstructured but where the variability \nin it is much greater than multi-label\nclassification, such as in image\ndenoising or pixel labeling.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the output space is arbitrarily\nstructured but where the variability \nin it is much greater than multi-label\nclassification, such as in image\ndenoising or pixel labeling.",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "text",
			"version": 403,
			"versionNonce": 1563898102,
			"isDeleted": false,
			"id": "YQGjGDnX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -714.5142594536974,
			"y": 1387.4643451346442,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1024.839111328125,
			"height": 25,
			"seed": 2049430698,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YPhuI3lEkDk-TmHv7OHwZ",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Before moving forward to CRBMs, lets get a very very quick overview of RBM and training such models",
			"rawText": "Before moving forward to CRBMs, lets get a very very quick overview of RBM and training such models",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Before moving forward to CRBMs, lets get a very very quick overview of RBM and training such models",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 633,
			"versionNonce": 239690474,
			"isDeleted": false,
			"id": "YPhuI3lEkDk-TmHv7OHwZ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -183.58594913398758,
			"y": 1418.7747957544648,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 932.7742922781122,
			"height": 111.66511043602941,
			"seed": 975526122,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216619285,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "YQGjGDnX",
				"focus": -0.08377096435283177,
				"gap": 6.310450619820585
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
					-121.89322131636993,
					88.67659283525063
				],
				[
					-932.7742922781122,
					111.66511043602941
				]
			]
		},
		{
			"type": "text",
			"version": 662,
			"versionNonce": 992677046,
			"isDeleted": false,
			"id": "w0qbNunr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1820.394692279747,
			"y": 1419.2931932701852,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 424.25775146484375,
			"height": 35,
			"seed": 676753974,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Restricted Boltzmann machines",
			"rawText": "Restricted Boltzmann machines",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Restricted Boltzmann machines",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 729,
			"versionNonce": 1993606646,
			"isDeleted": false,
			"id": "M9eN74rn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2052.6150059605675,
			"y": 1474.4869990615937,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 898.0191650390625,
			"height": 150,
			"seed": 1597566966,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "A Restricted Boltzmann Machine is an undirected graphical model for unsupervised learning.\nthat is used to discover hidden structures in data\nThe task of an RBM is to define a probability distribution over a vector of observed\nbinary variables v and a vector of binary hidden variables h.\ni.e we want a model that after looking at a dataset would generate\nsimilarly looking data through the probability of them being \"plausible\" scenarios",
			"rawText": "A Restricted Boltzmann Machine is an undirected graphical model for unsupervised learning.\nthat is used to discover hidden structures in data\nThe task of an RBM is to define a probability distribution over a vector of observed\nbinary variables v and a vector of binary hidden variables h.\ni.e we want a model that after looking at a dataset would generate\nsimilarly looking data through the probability of them being \"plausible\" scenarios",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A Restricted Boltzmann Machine is an undirected graphical model for unsupervised learning.\nthat is used to discover hidden structures in data\nThe task of an RBM is to define a probability distribution over a vector of observed\nbinary variables v and a vector of binary hidden variables h.\ni.e we want a model that after looking at a dataset would generate\nsimilarly looking data through the probability of them being \"plausible\" scenarios",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "line",
			"version": 481,
			"versionNonce": 1569445686,
			"isDeleted": false,
			"id": "lab2-4W-yexuDzG6_Uon0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1474.192500578019,
			"y": 2506.8470275000896,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 198.0788006101211,
			"height": 13.276220387894455,
			"seed": 2144237354,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					125.9277429270046,
					-13.276220387894455
				],
				[
					198.0788006101211,
					-6.8745642481940195
				]
			]
		},
		{
			"type": "text",
			"version": 769,
			"versionNonce": 1471643766,
			"isDeleted": false,
			"id": "0ZtqANsM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1342.4673995977873,
			"y": 2490.5873719818915,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 325.7606506347656,
			"height": 120,
			"seed": 79665002,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xf0rdar_S0qESphMu_E7R",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Normalization Term\nwhich is the sum of all possible\nconfigurations over all values of h and v\nThis is generally intractable in this form\nbecause it needs to find all combinations\nof a variable that is high dimensional",
			"rawText": "Normalization Term\nwhich is the sum of all possible\nconfigurations over all values of h and v\nThis is generally intractable in this form\nbecause it needs to find all combinations\nof a variable that is high dimensional",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Normalization Term\nwhich is the sum of all possible\nconfigurations over all values of h and v\nThis is generally intractable in this form\nbecause it needs to find all combinations\nof a variable that is high dimensional",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "line",
			"version": 868,
			"versionNonce": 2031878582,
			"isDeleted": false,
			"id": "dxluseTY_41k9Bv2pJsFe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1928.6687003555844,
			"y": 2170.567089980177,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 207.0955425795339,
			"height": 41.59428353115595,
			"seed": 501691190,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-175.5153338683524,
					0.9849725170563488
				],
				[
					-207.0955425795339,
					41.59428353115595
				]
			]
		},
		{
			"type": "text",
			"version": 1864,
			"versionNonce": 350116598,
			"isDeleted": false,
			"id": "l4Xhxq1T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2312.4621923576988,
			"y": 2218.799889631183,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 353.8087158203125,
			"height": 160,
			"seed": 1182316522,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Energy functions are functions\nthat get as an input the current\nscenario of v and h and through the current\nstate of the system (weights, biases etc..)\noutput its energy.\nJust view it as a score function that can\nbe positive or negative to signify two things\nattracting or repelling each other....",
			"rawText": "Energy functions are functions\nthat get as an input the current\nscenario of v and h and through the current\nstate of the system (weights, biases etc..)\noutput its energy.\nJust view it as a score function that can\nbe positive or negative to signify two things\nattracting or repelling each other....",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Energy functions are functions\nthat get as an input the current\nscenario of v and h and through the current\nstate of the system (weights, biases etc..)\noutput its energy.\nJust view it as a score function that can\nbe positive or negative to signify two things\nattracting or repelling each other....",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "line",
			"version": 446,
			"versionNonce": 1367575606,
			"isDeleted": false,
			"id": "c0uKlkLHmLMYhwu34VFj5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1623.892735327412,
			"y": 2252.8484231208377,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.7680125328967051,
			"height": 36.864601579044574,
			"seed": 1054579062,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.7680125328967051,
					19.200313322419106
				],
				[
					-0.7680125328967051,
					36.864601579044574
				]
			]
		},
		{
			"type": "text",
			"version": 463,
			"versionNonce": 1022399862,
			"isDeleted": false,
			"id": "prIROqGj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1719.1006434901915,
			"y": 2289.713024699882,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 188.87979125976562,
			"height": 100,
			"seed": 531345142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "a matrix containing\npairwise weights\nlinking elements in v\nand elements in h",
			"rawText": "a matrix containing\npairwise weights\nlinking elements in v\nand elements in h",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a matrix containing\npairwise weights\nlinking elements in v\nand elements in h",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "line",
			"version": 406,
			"versionNonce": 1617589942,
			"isDeleted": false,
			"id": "YRovE64hkM1n9T183UeEp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1491.4105734027212,
			"y": 2255.920473252425,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.56848251652525,
			"height": 59.904977565946865,
			"seed": 1805258730,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					29.56848251652525,
					59.904977565946865
				]
			]
		},
		{
			"type": "text",
			"version": 443,
			"versionNonce": 1419128822,
			"isDeleted": false,
			"id": "rT90OzG5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1512.5517152070538,
			"y": 2318.51349468351,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 135.9798126220703,
			"height": 50,
			"seed": 1052279914,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "bias of visible\nvariable/layer",
			"rawText": "bias of visible\nvariable/layer",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "bias of visible\nvariable/layer",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 411,
			"versionNonce": 1433977142,
			"isDeleted": false,
			"id": "RCw-gNkTAn-fFllRgCLvH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1365.4565180076527,
			"y": 2246.7043228576636,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 82.56134728640131,
			"height": 48.0007833060472,
			"seed": 2027888438,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					82.56134728640131,
					48.0007833060472
				]
			]
		},
		{
			"type": "text",
			"version": 427,
			"versionNonce": 1450650230,
			"isDeleted": false,
			"id": "k1JscRnn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1342.8669471049925,
			"y": 2302.7692377591266,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 136.83982849121094,
			"height": 50,
			"seed": 1836589302,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "bias of hidden\nvariable/layer",
			"rawText": "bias of hidden\nvariable/layer",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "bias of hidden\nvariable/layer",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 870,
			"versionNonce": 374762422,
			"isDeleted": false,
			"id": "UNSc8J4Y",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1718.0643228415688,
			"y": 1708.6492937093062,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 22,
			"height": 16,
			"seed": 65171,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0a58a98342599296079bb17f9da791a5f258597d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 816,
			"versionNonce": 859538678,
			"isDeleted": false,
			"id": "kxcxdAuL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1528.8536699561528,
			"y": 1799.665044597221,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 14.91998291015625,
			"height": 25,
			"seed": 1343879914,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "W",
			"rawText": "W",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "W",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 865,
			"versionNonce": 1051424310,
			"isDeleted": false,
			"id": "VQrbc0gL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1509.7615563452514,
			"y": 1700.7675551146708,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 14.475994873046874,
			"height": 35,
			"seed": 804097590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "V",
			"rawText": "V",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 907,
			"versionNonce": 1368080246,
			"isDeleted": false,
			"id": "tgLp4uBX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1830.824229102745,
			"y": 1899.7621720309617,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 13.832061767578125,
			"height": 35,
			"seed": 250675062,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "h",
			"rawText": "h",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "h",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "line",
			"version": 911,
			"versionNonce": 538960054,
			"isDeleted": false,
			"id": "hlEHDXlE1JcIShxrsG48c",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1721.238428046051,
			"y": 1707.4760254898877,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 132.21780884800341,
			"height": 19.268724948706677,
			"seed": 182510314,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-96.03979465859447,
					-17.82149221164218
				],
				[
					-132.21780884800341,
					1.4472327370644962
				]
			]
		},
		{
			"type": "text",
			"version": 887,
			"versionNonce": 235821558,
			"isDeleted": false,
			"id": "dovmNECD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1932.1018752510333,
			"y": 1712.8765943049893,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 143.7443084716797,
			"height": 60,
			"seed": 168928566,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Binary values\nplus bias for each\nelement",
			"rawText": "Binary values\nplus bias for each\nelement",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Binary values\nplus bias for each\nelement",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 1007,
			"versionNonce": 1113303862,
			"isDeleted": false,
			"id": "FKIYlVOk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1748.1210253888135,
			"y": 1908.043483608748,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 15,
			"height": 22,
			"seed": 29578,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9cf2e388325851a7e449c3be8d3b86ea1d195fd5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 1045,
			"versionNonce": 996988022,
			"isDeleted": false,
			"id": "ngaOV11U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1867.3867190568592,
			"y": 1950.0539730851515,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 490.0008850097656,
			"height": 60,
			"seed": 2025647914,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "No two elements from V, h are connected to\neach other which is where the \"restricted\" comes into play\notherwise fully connected between every component of v and h",
			"rawText": "No two elements from V, h are connected to\neach other which is where the \"restricted\" comes into play\notherwise fully connected between every component of v and h",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "No two elements from V, h are connected to\neach other which is where the \"restricted\" comes into play\notherwise fully connected between every component of v and h",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 473,
			"versionNonce": 1661392310,
			"isDeleted": false,
			"id": "WLjowHTq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1867.3867191104332,
			"y": 2212.119848160528,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 516.8687590080037,
			"height": 41.436735954228155,
			"seed": 10034,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2682318a6f25a146b3e241f0f699ca0cc7ac86ba",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 576,
			"versionNonce": 575581942,
			"isDeleted": false,
			"id": "pWJWZtn0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1813.450652105522,
			"y": 2470.3624366881113,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 340.2013215044487,
			"height": 60.84901685445423,
			"seed": 63523,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7e3a11868a4e04a39502f3d611789ffe3abd85a2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 1670,
			"versionNonce": 1976131638,
			"isDeleted": false,
			"id": "jeAMoDX1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2086.4757543136047,
			"y": 2533.4977623377886,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fff9db",
			"width": 928.178955078125,
			"height": 225,
			"seed": 1705558518,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xf0rdar_S0qESphMu_E7R",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The energy in our case correlates to probability.\nOur energy function uses dot products,\nwhich are a measure of similarities of two vectors\nW's values signify positively or negatively if we want our v and h to be similar.\nLow energy in our context symbolizes high probability and vice versa.\n\nThis concludes that given a real input from the dataset,\nhow similar is it to the features saved in h that are learned from our\ndistribution of inputs (which means how plausible that this sample x was drawn from our dist)",
			"rawText": "The energy in our case correlates to probability.\nOur energy function uses dot products,\nwhich are a measure of similarities of two vectors\nW's values signify positively or negatively if we want our v and h to be similar.\nLow energy in our context symbolizes high probability and vice versa.\n\nThis concludes that given a real input from the dataset,\nhow similar is it to the features saved in h that are learned from our\ndistribution of inputs (which means how plausible that this sample x was drawn from our dist)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The energy in our case correlates to probability.\nOur energy function uses dot products,\nwhich are a measure of similarities of two vectors\nW's values signify positively or negatively if we want our v and h to be similar.\nLow energy in our context symbolizes high probability and vice versa.\n\nThis concludes that given a real input from the dataset,\nhow similar is it to the features saved in h that are learned from our\ndistribution of inputs (which means how plausible that this sample x was drawn from our dist)",
			"lineHeight": 1.25,
			"baseline": 218
		},
		{
			"type": "text",
			"version": 336,
			"versionNonce": 608914102,
			"isDeleted": false,
			"id": "M4WEME0i",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2035.0869163564485,
			"y": 1632.292369665409,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 850.2791137695312,
			"height": 50,
			"seed": 2009110518,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "For the sake of understanding lets defined a very simple example and walk through it\nwhile explaining",
			"rawText": "For the sake of understanding lets defined a very simple example and walk through it\nwhile explaining",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "For the sake of understanding lets defined a very simple example and walk through it\nwhile explaining",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 1193,
			"versionNonce": 1974564266,
			"isDeleted": false,
			"id": "QpZgayHWFjufaIdlQmjp8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1469.2162728801648,
			"y": 1716.3014925018533,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 263.86406716047657,
			"height": 45.972556215720715,
			"seed": 1764784438,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216619288,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "IEEYFIqV",
				"focus": 0.08072856368299319,
				"gap": 3.3508958006657394
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
					227.09364395205603,
					-4.601368886200362
				],
				[
					263.86406716047657,
					41.37118732952035
				]
			]
		},
		{
			"type": "text",
			"version": 823,
			"versionNonce": 1312068918,
			"isDeleted": false,
			"id": "IEEYFIqV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1445.2450459162503,
			"y": 1761.0235756320394,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 557.7611083984375,
			"height": 160,
			"seed": 474545770,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "QpZgayHWFjufaIdlQmjp8",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "V is this example is a datapoint from our dataset that describes\nwhether a student attended a ML lecture or not, each element i\ngives 1 if the i-th student attends and 0 if it does not.\nThe bias for v can be thought of as prior knowledge that\ni-th student is more likely to attend classes in general or not.\nif it was negative then the student is less likely to attend in general\nand vice vera\nbut the bias does not mean anything at the start of training.",
			"rawText": "V is this example is a datapoint from our dataset that describes\nwhether a student attended a ML lecture or not, each element i\ngives 1 if the i-th student attends and 0 if it does not.\nThe bias for v can be thought of as prior knowledge that\ni-th student is more likely to attend classes in general or not.\nif it was negative then the student is less likely to attend in general\nand vice vera\nbut the bias does not mean anything at the start of training.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V is this example is a datapoint from our dataset that describes\nwhether a student attended a ML lecture or not, each element i\ngives 1 if the i-th student attends and 0 if it does not.\nThe bias for v can be thought of as prior knowledge that\ni-th student is more likely to attend classes in general or not.\nif it was negative then the student is less likely to attend in general\nand vice vera\nbut the bias does not mean anything at the start of training.",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "arrow",
			"version": 679,
			"versionNonce": 1141452906,
			"isDeleted": false,
			"id": "DKGAIh59sFIgyW04oZVpk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1848.2581269969742,
			"y": 1927.3950227201876,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 270.0090485319861,
			"height": 28.78706915185967,
			"seed": 1285540982,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216619288,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "wugb9a97",
				"focus": 0.2116394346645683,
				"gap": 10.475637398752042
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
					-246.153053138848,
					1.6141183812383133
				],
				[
					-270.0090485319861,
					-27.172950770621355
				]
			]
		},
		{
			"type": "text",
			"version": 756,
			"versionNonce": 1276631286,
			"isDeleted": false,
			"id": "wugb9a97",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2398.302879652738,
			"y": 1729.7464345508142,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 555.8091430664062,
			"height": 160,
			"seed": 1091783862,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "DKGAIh59sFIgyW04oZVpk",
					"type": "arrow"
				},
				{
					"id": "Hc_RQG79EKqOPYP8LMPfh",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The hidden layer in this example are factors\nor features of the data\nthat contribute to a student attending\nfor example if j-th unit of h can be 1 if hes in korea\nbragging about his work or 0 if hes not.\nanother unit can describe whether there is a train strike or not\nnote that these states are not something we know in each datapoint\nwhich is why theyre hidden, theyre not available in the dataset.",
			"rawText": "The hidden layer in this example are factors\nor features of the data\nthat contribute to a student attending\nfor example if j-th unit of h can be 1 if hes in korea\nbragging about his work or 0 if hes not.\nanother unit can describe whether there is a train strike or not\nnote that these states are not something we know in each datapoint\nwhich is why theyre hidden, theyre not available in the dataset.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The hidden layer in this example are factors\nor features of the data\nthat contribute to a student attending\nfor example if j-th unit of h can be 1 if hes in korea\nbragging about his work or 0 if hes not.\nanother unit can describe whether there is a train strike or not\nnote that these states are not something we know in each datapoint\nwhich is why theyre hidden, theyre not available in the dataset.",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "text",
			"version": 498,
			"versionNonce": 384611510,
			"isDeleted": false,
			"id": "waiju7ZB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1979.219010445267,
			"y": 2010.0539725198837,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 713.6654663085938,
			"height": 60,
			"seed": 491474538,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "what this means for our example is that no two events in v or two events in h affect\neach other, i.e students dont attend classes because their friend does. Only factors\nin h affect factors in v, and the weights connecting them are the strength of the effect",
			"rawText": "what this means for our example is that no two events in v or two events in h affect\neach other, i.e students dont attend classes because their friend does. Only factors\nin h affect factors in v, and the weights connecting them are the strength of the effect",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "what this means for our example is that no two events in v or two events in h affect\neach other, i.e students dont attend classes because their friend does. Only factors\nin h affect factors in v, and the weights connecting them are the strength of the effect",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 640,
			"versionNonce": 1008774646,
			"isDeleted": false,
			"id": "OJivyeYg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2125.4793251263254,
			"y": 2070.1917806770425,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 996.8990478515625,
			"height": 75,
			"seed": 1073659882,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Our goal in this example is to learn what are the most plausible scenarios that happen\ni.e learn the probability distribution over h and v that describes what is happening and the patterns\nthat occur in the data often.",
			"rawText": "Our goal in this example is to learn what are the most plausible scenarios that happen\ni.e learn the probability distribution over h and v that describes what is happening and the patterns\nthat occur in the data often.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Our goal in this example is to learn what are the most plausible scenarios that happen\ni.e learn the probability distribution over h and v that describes what is happening and the patterns\nthat occur in the data often.",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 420,
			"versionNonce": 587431734,
			"isDeleted": false,
			"id": "QVXVLhwc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2007.9305136369653,
			"y": 2157.090502434093,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fff9db",
			"width": 782.7590942382812,
			"height": 50,
			"seed": 1271798506,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We define an energy function to give us a measure of score\nnote that energy = -score in this context and score = likelyness of a scenario",
			"rawText": "We define an energy function to give us a measure of score\nnote that energy = -score in this context and score = likelyness of a scenario",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We define an energy function to give us a measure of score\nnote that energy = -score in this context and score = likelyness of a scenario",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 460,
			"versionNonce": 1610229878,
			"isDeleted": false,
			"id": "9WEm90O5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2054.360414876769,
			"y": 2410.718063176396,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fff9db",
			"width": 875.618896484375,
			"height": 50,
			"seed": 851379382,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Now since we can measure scores, we can \"easily\" build a probability distribution\nusing the softmax function which maps values to the range 0..1 such that their sum is 1",
			"rawText": "Now since we can measure scores, we can \"easily\" build a probability distribution\nusing the softmax function which maps values to the range 0..1 such that their sum is 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Now since we can measure scores, we can \"easily\" build a probability distribution\nusing the softmax function which maps values to the range 0..1 such that their sum is 1",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 281,
			"versionNonce": 852076982,
			"isDeleted": false,
			"id": "eXMaCA3v7NUHfCO5D-f64",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1841.9815234128039,
			"y": 2501.982216463631,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 267.5964182545522,
			"height": 8.451644007351206,
			"seed": 1733192438,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-218.0271007622698,
					1.9125184277390872
				],
				[
					-267.5964182545522,
					8.451644007351206
				]
			]
		},
		{
			"type": "text",
			"version": 536,
			"versionNonce": 446104310,
			"isDeleted": false,
			"id": "roXTpIND",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2498.109553580802,
			"y": 2505.7565842819827,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 411.279541015625,
			"height": 200,
			"seed": 1196482678,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets take for simplified example scenario:\n\nSanad=1 , Awsam=1, Philipp=0\n\n\n\nProfessor=1 , strike=1\nis absent            ",
			"rawText": "Lets take for simplified example scenario:\n\nSanad=1 , Awsam=1, Philipp=0\n\n\n\nProfessor=1 , strike=1\nis absent            ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets take for simplified example scenario:\n\nSanad=1 , Awsam=1, Philipp=0\n\n\n\nProfessor=1 , strike=1\nis absent            ",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "line",
			"version": 339,
			"versionNonce": 1776759862,
			"isDeleted": false,
			"id": "JyDWjyRMa5jzYrCcomfJs",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2147.0139592750747,
			"y": 2562.397883367406,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 30.829473739023342,
			"height": 5.285827641298511,
			"seed": 469076150,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					15.48147810799287,
					-2.903722352756631
				],
				[
					30.829473739023342,
					-5.285827641298511
				]
			]
		},
		{
			"type": "text",
			"version": 406,
			"versionNonce": 1520385398,
			"isDeleted": false,
			"id": "yLz8cUo6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2112.003023291109,
			"y": 2546.6541041868713,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 24.37786865234375,
			"height": 13.405386438636356,
			"seed": 1276418154,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 3.5747697169696946,
			"fontFamily": 1,
			"text": "Classic philipp\ndoesnt bother\nshowing up",
			"rawText": "Classic philipp\ndoesnt bother\nshowing up",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Classic philipp\ndoesnt bother\nshowing up",
			"lineHeight": 1.25,
			"baseline": 12
		},
		{
			"type": "line",
			"version": 252,
			"versionNonce": 570695350,
			"isDeleted": false,
			"id": "gqBMpV7qkBi8xyI6BU36a",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2387.718311512195,
			"y": 2590.812171651968,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 142.08475266105302,
			"height": 58.84626022228167,
			"seed": 1869415478,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					142.08475266105302,
					58.84626022228167
				]
			]
		},
		{
			"type": "line",
			"version": 238,
			"versionNonce": 79353846,
			"isDeleted": false,
			"id": "4t0p5mT0qeAEq-4LxFTey",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2387.718311512195,
			"y": 2591.117074554674,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 36.283445422028535,
			"height": 58.84626022228167,
			"seed": 1706437610,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					36.283445422028535,
					58.84626022228167
				]
			]
		},
		{
			"type": "line",
			"version": 253,
			"versionNonce": 1791519030,
			"isDeleted": false,
			"id": "PVRdeNU7zLnhZOiMBYCxF",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2296.8572465057705,
			"y": 2584.4092106951393,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 50.00407604380416,
			"height": 67.68844440075918,
			"seed": 490604394,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-50.00407604380416,
					67.68844440075918
				]
			]
		},
		{
			"type": "line",
			"version": 239,
			"versionNonce": 1938936438,
			"isDeleted": false,
			"id": "cPmhME6gF6cmLcUn86NRU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2296.2474407003583,
			"y": 2583.494501987021,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 54.88252248710205,
			"height": 67.38354149805309,
			"seed": 1873473782,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					54.88252248710205,
					67.38354149805309
				]
			]
		},
		{
			"type": "line",
			"version": 250,
			"versionNonce": 165417910,
			"isDeleted": false,
			"id": "qUl31sdqWS8gBTXJGbZaG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2213.618754066999,
			"y": 2585.6288223059637,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 127.14451042845326,
			"height": 66.16392988722873,
			"seed": 2111705642,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-127.14451042845326,
					66.16392988722873
				]
			]
		},
		{
			"type": "line",
			"version": 268,
			"versionNonce": 2009869558,
			"isDeleted": false,
			"id": "epBBiKINQD1EWjH_sBk-9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2213.0089482615867,
			"y": 2585.0190165005515,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 24.087329313783812,
			"height": 66.46883278993482,
			"seed": 1559334518,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-24.087329313783812,
					66.46883278993482
				]
			]
		},
		{
			"type": "text",
			"version": 445,
			"versionNonce": 2061966902,
			"isDeleted": false,
			"id": "FV5apLXh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2250.367871326664,
			"y": 2584.5294697936915,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 11.39202880859375,
			"height": 20,
			"seed": 1986791862,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "2",
			"rawText": "2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 246,
			"versionNonce": 1477568374,
			"isDeleted": false,
			"id": "cNQYVdA4",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2220.6818881466293,
			"y": 2614.04465983157,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 11.008026123046875,
			"height": 20,
			"seed": 1563833206,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "0",
			"rawText": "0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 225,
			"versionNonce": 1871808694,
			"isDeleted": false,
			"id": "GJgLzdqy",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2341.504601913467,
			"y": 2595.618016635879,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 4.3360137939453125,
			"height": 20,
			"seed": 1147428010,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
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
			"type": "text",
			"version": 227,
			"versionNonce": 1359675894,
			"isDeleted": false,
			"id": "DZqFW4HP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2375.2496738973296,
			"y": 2625.8893312096384,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 4.3360137939453125,
			"height": 20,
			"seed": 334025078,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
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
			"type": "text",
			"version": 266,
			"versionNonce": 1334006582,
			"isDeleted": false,
			"id": "BFsRcpOr",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2311.828626597377,
			"y": 2598.0844306770596,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 11.008026123046875,
			"height": 20,
			"seed": 1973909878,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "0",
			"rawText": "0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 281,
			"versionNonce": 358579318,
			"isDeleted": false,
			"id": "9m0Zq2fe",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2283.240262088423,
			"y": 2589.189288357239,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 17.404739379882812,
			"height": 13.778376694060173,
			"seed": 646705066,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 11.022701355248138,
			"fontFamily": 1,
			"text": "0.5",
			"rawText": "0.5",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0.5",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 473,
			"versionNonce": 946109878,
			"isDeleted": false,
			"id": "x6l9Qnei",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2525.2016256322954,
			"y": 2712.529825051113,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 431.29693603515625,
			"height": 80,
			"seed": 292284906,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "bnt4Ic3EKc4DUORobN_WQ",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Concludes in the score of 2.5\nif we calculate every single possible scenario's\nscore then divide by their sum we will get a probability\nof each one",
			"rawText": "Concludes in the score of 2.5\nif we calculate every single possible scenario's\nscore then divide by their sum we will get a probability\nof each one",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Concludes in the score of 2.5\nif we calculate every single possible scenario's\nscore then divide by their sum we will get a probability\nof each one",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 564,
			"versionNonce": 1293652778,
			"isDeleted": false,
			"id": "bnt4Ic3EKc4DUORobN_WQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2536.3737755645543,
			"y": 2744.35094924203,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 126.84391642251171,
			"height": 88.06779689438645,
			"seed": 1028043178,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216619291,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "x6l9Qnei",
				"focus": -0.017341540691474432,
				"gap": 11.17214993225889
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
					-115.67113621949261,
					-4.60055655418455
				],
				[
					-126.84391642251171,
					-88.06779689438645
				]
			]
		},
		{
			"type": "text",
			"version": 571,
			"versionNonce": 414880118,
			"isDeleted": false,
			"id": "70PZ3G1v",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2880.144428497376,
			"y": 2557.6997976151215,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 427.7288818359375,
			"height": 120,
			"seed": 1712631402,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Note that the reason we are using Exp\nis because we dont want to map high scores to high\nnumbers and low scores to low numbers without making\nthem sum to 0 (as in no negative numbers) in order\nto not divide by 0\n",
			"rawText": "Note that the reason we are using Exp\nis because we dont want to map high scores to high\nnumbers and low scores to low numbers without making\nthem sum to 0 (as in no negative numbers) in order\nto not divide by 0\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note that the reason we are using Exp\nis because we dont want to map high scores to high\nnumbers and low scores to low numbers without making\nthem sum to 0 (as in no negative numbers) in order\nto not divide by 0\n",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"id": "xf0rdar_S0qESphMu_E7R",
			"type": "arrow",
			"x": -1137.8290660776129,
			"y": 2628.651053699469,
			"width": 253.60175398731337,
			"height": 190.9955642902828,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#fff9db",
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
			"seed": 1620533162,
			"version": 573,
			"versionNonce": 861117930,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619291,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					9.698319256772038,
					161.73868151034776
				],
				[
					-243.90343473054133,
					190.9955642902828
				]
			],
			"lastCommittedPoint": [
				-323.27441403550336,
				222.74395601226752
			],
			"startBinding": {
				"elementId": "jeAMoDX1",
				"focus": -1.0313529304900522,
				"gap": 20.46773315786686
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "b6MRqJRb",
			"type": "text",
			"x": -1906.5516581974548,
			"y": 2777.284794604088,
			"width": 570.4490966796875,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#fff9db",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 849760118,
			"version": 903,
			"versionNonce": 185674742,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Problem:\nWe cant compute an exponential number of combinations\nWe need to develop an algorithm that does not require the denominator\nin order to learn the probability distribution",
			"rawText": "Problem:\nWe cant compute an exponential number of combinations\nWe need to develop an algorithm that does not require the denominator\nin order to learn the probability distribution",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "Problem:\nWe cant compute an exponential number of combinations\nWe need to develop an algorithm that does not require the denominator\nin order to learn the probability distribution",
			"lineHeight": 1.25
		},
		{
			"id": "LpKHFnlf",
			"type": "text",
			"x": -2959.81522454926,
			"y": 2861.7904024038953,
			"width": 739.9790649414062,
			"height": 325,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#fff9db",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 180250218,
			"version": 1161,
			"versionNonce": 2067021110,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Lets explain briefly, the process of contrastive divergence\nGiven a dataset with our data v, what we are trying to do here\nto build p(v,h) is the following:\n\nfor every point vi that occurs in data\nincrease P(vi | h) over all possible values of h\nand decrease all probabilities\nafter a sufficient number of datapoints we will achieve a data\ndistribution such that it mimics the probability distribution of our dataset\nThe end goal is to update the weights and biases such that:\n\n\nWhich translates to the log likelihood of the data",
			"rawText": "Lets explain briefly, the process of contrastive divergence\nGiven a dataset with our data v, what we are trying to do here\nto build p(v,h) is the following:\n\nfor every point vi that occurs in data\nincrease P(vi | h) over all possible values of h\nand decrease all probabilities\nafter a sufficient number of datapoints we will achieve a data\ndistribution such that it mimics the probability distribution of our dataset\nThe end goal is to update the weights and biases such that:\n\n\nWhich translates to the log likelihood of the data",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 318,
			"containerId": null,
			"originalText": "Lets explain briefly, the process of contrastive divergence\nGiven a dataset with our data v, what we are trying to do here\nto build p(v,h) is the following:\n\nfor every point vi that occurs in data\nincrease P(vi | h) over all possible values of h\nand decrease all probabilities\nafter a sufficient number of datapoints we will achieve a data\ndistribution such that it mimics the probability distribution of our dataset\nThe end goal is to update the weights and biases such that:\n\n\nWhich translates to the log likelihood of the data",
			"lineHeight": 1.25
		},
		{
			"id": "FtbtMK__R4rVNJywIOyDz",
			"type": "arrow",
			"x": -2856.4606432529026,
			"y": 2989.2712493004465,
			"width": 217.26526867507732,
			"height": 0.9920788523972988,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
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
			"seed": 533671286,
			"version": 536,
			"versionNonce": 795027062,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-217.26526867507732,
					0.9920788523972988
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "hnLR68lN",
			"type": "text",
			"x": -3051.7690392201257,
			"y": 2955.8628843543756,
			"width": 175.0797882080078,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 528062518,
			"version": 468,
			"versionNonce": 1751312310,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "visual explanation",
			"rawText": "visual explanation",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "visual explanation",
			"lineHeight": 1.25
		},
		{
			"id": "Y4mDn0Zq",
			"type": "text",
			"x": -3293.208329867851,
			"y": 2919.953895858018,
			"width": 261.7125244140625,
			"height": 160,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1617549226,
			"version": 1010,
			"versionNonce": 106463478,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "lets take a scenario of all\npossible combinations of\nthe letters A, B, C\n\nlets also assume we\nhave a dataset over occurances\nof A and B, and C is our hidden\nlayer",
			"rawText": "lets take a scenario of all\npossible combinations of\nthe letters A, B, C\n\nlets also assume we\nhave a dataset over occurances\nof A and B, and C is our hidden\nlayer",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 154,
			"containerId": null,
			"originalText": "lets take a scenario of all\npossible combinations of\nthe letters A, B, C\n\nlets also assume we\nhave a dataset over occurances\nof A and B, and C is our hidden\nlayer",
			"lineHeight": 1.25
		},
		{
			"id": "90s64D8dZHFWMz8DK4lEj",
			"type": "rectangle",
			"x": -3641.645207977345,
			"y": 2977.6366439218014,
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"seed": 503651690,
			"version": 694,
			"versionNonce": 482931254,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"id": "JByCH6A8JiAyDWbR_oAZf",
			"type": "line",
			"x": -3643.0016462613185,
			"y": 3033.5811034132375,
			"width": 0.5547199100998836,
			"height": 128.69501914316538,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 785831402,
			"version": 663,
			"versionNonce": 110705526,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5547199100998836,
					-128.69501914316538
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
			"version": 730,
			"versionNonce": 2047761590,
			"isDeleted": false,
			"id": "5A2Gs3iUze3W8UtCQNpJX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3607.540456547385,
			"y": 2978.0171830053027,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 1259908330,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 741,
			"versionNonce": 483218934,
			"isDeleted": false,
			"id": "9iInP3fq-q87He0LiConk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3573.4357050335766,
			"y": 2977.6366434987326,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 1790636470,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 764,
			"versionNonce": 400238390,
			"isDeleted": false,
			"id": "wQZDsnZqOkCNBKH_0q7Gf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3539.3309538386966,
			"y": 2977.6366433965063,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 1363662186,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 767,
			"versionNonce": 731697270,
			"isDeleted": false,
			"id": "ulqtlZlb16IHiJ8_4-NIm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3505.2262026946532,
			"y": 2978.0171831348157,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 1312637430,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 762,
			"versionNonce": 1138184630,
			"isDeleted": false,
			"id": "duYe6qP_DnSFok2-TvK_i",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3471.121451449257,
			"y": 2978.0171836903023,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 169824426,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 763,
			"versionNonce": 196061942,
			"isDeleted": false,
			"id": "svwCmcbKBlNKFury8_zUm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3437.0167001678874,
			"y": 2978.0171837875937,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 1082940534,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 759,
			"versionNonce": 27974710,
			"isDeleted": false,
			"id": "gHF_XN_ouhl-aaeYdhGsE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3402.911949094134,
			"y": 2978.0171841668516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 251999082,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"id": "fLizDrpgWLIjyS2aj4zvf",
			"type": "line",
			"x": -3645.751054500578,
			"y": 3033.9202947998056,
			"width": 303.15542754404066,
			"height": 0.5327636926773139,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1734264758,
			"version": 823,
			"versionNonce": 195945846,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					303.15542754404066,
					-0.5327636926773139
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "NqUjnsbC",
			"type": "text",
			"x": -3715.631676198944,
			"y": 2912.040441279845,
			"width": 65.54670715332031,
			"height": 16.76001831425987,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"seed": 463824246,
			"version": 635,
			"versionNonce": 184403638,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "probability",
			"rawText": "probability",
			"fontSize": 13.408014651407896,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 11,
			"containerId": null,
			"originalText": "probability",
			"lineHeight": 1.25
		},
		{
			"id": "q6aNAWL3",
			"type": "text",
			"x": -3361.9443090517243,
			"y": 3033.133521879535,
			"width": 52.61143493652344,
			"height": 16.760018314259874,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1125526762,
			"version": 646,
			"versionNonce": 1883209718,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "scenario",
			"rawText": "scenario",
			"fontSize": 13.408014651407898,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 11,
			"containerId": null,
			"originalText": "scenario",
			"lineHeight": 1.25
		},
		{
			"id": "SW3dhAOW",
			"type": "text",
			"x": -3595.3981614204845,
			"y": 3038.0502083555207,
			"width": 7.03155517578125,
			"height": 13.408014651407898,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1703497962,
			"version": 632,
			"versionNonce": 1333268790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "A",
			"rawText": "A",
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 9,
			"containerId": null,
			"originalText": "A",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 652,
			"versionNonce": 1946974838,
			"isDeleted": false,
			"id": "gOuK40GM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3560.6077662300727,
			"y": 3037.403460382548,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.7925872802734375,
			"height": 13.408014651407898,
			"seed": 1880911338,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "B",
			"rawText": "B",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "B",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 674,
			"versionNonce": 1958853558,
			"isDeleted": false,
			"id": "i2ogkj5Q",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3525.3822267491505,
			"y": 3037.7942513085313,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 6.902923583984375,
			"height": 13.408014651407898,
			"seed": 653933162,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "C",
			"rawText": "C",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "C",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"id": "LLwB7AoI",
			"type": "text",
			"x": -3495.346832152917,
			"y": 3036.291649188598,
			"width": 14.824142456054688,
			"height": 13.408014651407898,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1384570678,
			"version": 624,
			"versionNonce": 1203557622,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "AB",
			"rawText": "AB",
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 9,
			"containerId": null,
			"originalText": "AB",
			"lineHeight": 1.25
		},
		{
			"id": "RYVAiBw1",
			"type": "text",
			"x": -3462.0752473019083,
			"y": 3037.268626503555,
			"width": 13.934478759765625,
			"height": 13.408014651407898,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"seed": 889751786,
			"version": 640,
			"versionNonce": 1451410998,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "AC",
			"rawText": "AC",
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 9,
			"containerId": null,
			"originalText": "AC",
			"lineHeight": 1.25
		},
		{
			"id": "BXl1xLRa",
			"type": "text",
			"x": -3426.1124793335484,
			"y": 3037.268626503555,
			"width": 14.695510864257812,
			"height": 13.408014651407898,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"seed": 21494326,
			"version": 633,
			"versionNonce": 301502326,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "BC",
			"rawText": "BC",
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 9,
			"containerId": null,
			"originalText": "BC",
			"lineHeight": 1.25
		},
		{
			"id": "PBAg8WDP",
			"type": "text",
			"x": -3395.2411467428738,
			"y": 3037.0732310405638,
			"width": 21.727066040039062,
			"height": 13.408014651407898,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"lOcynlkj8sD4BMuo-8TH0"
			],
			"frameId": null,
			"roundness": null,
			"seed": 913547830,
			"version": 636,
			"versionNonce": 107163830,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "ABC",
			"rawText": "ABC",
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 9,
			"containerId": null,
			"originalText": "ABC",
			"lineHeight": 1.25
		},
		{
			"id": "yGlCLjl13kQLpv9aud5rb",
			"type": "arrow",
			"x": -3688.0098440719157,
			"y": 3000.424688152036,
			"width": 232.4796151804976,
			"height": 1.3025408833791516,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2073739254,
			"version": 497,
			"versionNonce": 1869064694,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-232.4796151804976,
					1.3025408833791516
				]
			],
			"lastCommittedPoint": [
				-151.6247079248974,
				1.7838200932337713
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Z5FhW3jM",
			"type": "text",
			"x": -3879.2015156532807,
			"y": 2910.714006119004,
			"width": 156.04165649414062,
			"height": 82.85422601836568,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 266030826,
			"version": 835,
			"versionNonce": 1275788086,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "First datapoint samples AB\nso we increase probability\nof all scenarios that include\nAB in them over all values of\nh\nand decrease everything (including\nthose we increased)",
			"rawText": "First datapoint samples AB\nso we increase probability\nof all scenarios that include\nAB in them over all values of\nh\nand decrease everything (including\nthose we increased)",
			"fontSize": 9.469054402098935,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 78,
			"containerId": null,
			"originalText": "First datapoint samples AB\nso we increase probability\nof all scenarios that include\nAB in them over all values of\nh\nand decrease everything (including\nthose we increased)",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 774,
			"versionNonce": 1924277366,
			"isDeleted": false,
			"id": "BiZAFPMxhs5aTr_DP6JRb",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4240.854271586403,
			"y": 2982.572547485469,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.20157576342991,
			"seed": 797012650,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 727,
			"versionNonce": 622994870,
			"isDeleted": false,
			"id": "me8dRwfr2GQdVamB15hGR",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4242.210709870377,
			"y": 3029.1546621675902,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 0.5547199100998836,
			"height": 128.69501914316538,
			"seed": 483495274,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5547199100998836,
					-128.69501914316538
				]
			]
		},
		{
			"type": "rectangle",
			"version": 818,
			"versionNonce": 612368118,
			"isDeleted": false,
			"id": "d1xJAwFesub_8PQdfaMVd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4206.749520156444,
			"y": 2982.6410084086588,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.513653923740556,
			"seed": 114315306,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 826,
			"versionNonce": 1162915894,
			"isDeleted": false,
			"id": "EEPtDJzGK1i2wNXounzmA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4172.644768642635,
			"y": 2982.572547062399,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.20157576343036,
			"seed": 828947178,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 844,
			"versionNonce": 58276214,
			"isDeleted": false,
			"id": "ztycSJVFLlw7GVqt7Uluk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4138.5400174477545,
			"y": 2981.835287514628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.938835208975895,
			"seed": 723897770,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 831,
			"versionNonce": 373201590,
			"isDeleted": false,
			"id": "wEjibkYxEnnRm8ZoJb_c7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4104.435266303712,
			"y": 2973.590741889169,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 2033354858,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 847,
			"versionNonce": 71685110,
			"isDeleted": false,
			"id": "p6FitdxOuFuGYfaRbIsZ3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4070.3305150583165,
			"y": 2981.8352871288075,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 47.319375888592276,
			"seed": 1129966378,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 847,
			"versionNonce": 932439350,
			"isDeleted": false,
			"id": "TyCGsQjIjDSqFP12KMyIc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4036.2257637769453,
			"y": 2982.641008514628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.51365460006219,
			"seed": 456170,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 823,
			"versionNonce": 294506102,
			"isDeleted": false,
			"id": "W0IAuxlizATl-dyDrts9M",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4002.1210127031923,
			"y": 2973.5907429212043,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 541370538,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 887,
			"versionNonce": 2130218934,
			"isDeleted": false,
			"id": "vzyVl0XZJZ0xoAQeNtILM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4244.960118109638,
			"y": 3029.4938535541582,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 303.15542754404066,
			"height": 0.5327636926773139,
			"seed": 1002308458,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					303.15542754404066,
					-0.5327636926773139
				]
			]
		},
		{
			"type": "text",
			"version": 676,
			"versionNonce": 200878326,
			"isDeleted": false,
			"id": "hNbp7I2t",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4322.502892052579,
			"y": 2918.559931812164,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 65.54670715332031,
			"height": 16.76001831425987,
			"seed": 1019086378,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407896,
			"fontFamily": 1,
			"text": "probability",
			"rawText": "probability",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 710,
			"versionNonce": 2014616118,
			"isDeleted": false,
			"id": "CbYxbqSk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3961.1533726607836,
			"y": 3028.7070806338875,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 52.61143493652344,
			"height": 16.760018314259874,
			"seed": 204452074,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407898,
			"fontFamily": 1,
			"text": "scenario",
			"rawText": "scenario",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scenario",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 696,
			"versionNonce": 1244652406,
			"isDeleted": false,
			"id": "9cj6QbUM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4194.607225029543,
			"y": 3033.623767109873,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.03155517578125,
			"height": 13.408014651407898,
			"seed": 1033765802,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "A",
			"rawText": "A",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 716,
			"versionNonce": 1687159990,
			"isDeleted": false,
			"id": "TrWFrgqG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4159.816829839131,
			"y": 3032.9770191369003,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.7925872802734375,
			"height": 13.408014651407898,
			"seed": 993263210,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "B",
			"rawText": "B",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "B",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 738,
			"versionNonce": 416939510,
			"isDeleted": false,
			"id": "X2k7lvaA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4124.591290358208,
			"y": 3033.3678100628836,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 6.902923583984375,
			"height": 13.408014651407898,
			"seed": 1908187434,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "C",
			"rawText": "C",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "C",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 688,
			"versionNonce": 1007865654,
			"isDeleted": false,
			"id": "90CDNutQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4094.555895761976,
			"y": 3031.8652079429507,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.824142456054688,
			"height": 13.408014651407898,
			"seed": 2091052010,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AB",
			"rawText": "AB",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AB",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 704,
			"versionNonce": 983529590,
			"isDeleted": false,
			"id": "J2d0PyqR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4061.284310910967,
			"y": 3032.842185257908,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 13.934478759765625,
			"height": 13.408014651407898,
			"seed": 1374805674,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AC",
			"rawText": "AC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 697,
			"versionNonce": 742717878,
			"isDeleted": false,
			"id": "eq2h9lR7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4025.3215429426077,
			"y": 3032.842185257908,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.695510864257812,
			"height": 13.408014651407898,
			"seed": 1851029866,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "BC",
			"rawText": "BC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "BC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 700,
			"versionNonce": 1747473142,
			"isDeleted": false,
			"id": "ro9pgnhH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3994.450210351932,
			"y": 3032.6467897949165,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 21.727066040039062,
			"height": 13.408014651407898,
			"seed": 18201642,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "ABC",
			"rawText": "ABC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ABC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"id": "bQqO7Jr6ehK3Jpmy5BMSI",
			"type": "arrow",
			"x": -4099.9205908097865,
			"y": 3077.661852457368,
			"width": 1.8700850796662962,
			"height": 100.60004232852907,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 63512810,
			"version": 495,
			"versionNonce": 416187446,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.8700850796662962,
					100.60004232852907
				]
			],
			"lastCommittedPoint": [
				-1.8700850796662962,
				148.67176383345577
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "YFwi8mmr",
			"type": "text",
			"x": -4095.1967763220455,
			"y": 3101.9748285889955,
			"width": 138.7255096435547,
			"height": 46.89631377056236,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 323750890,
			"version": 535,
			"versionNonce": 1344048502,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "lets say we samples A\nnow so we repeat the\nprocess",
			"rawText": "lets say we samples A\nnow so we repeat the\nprocess",
			"fontSize": 12.505683672149962,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 41,
			"containerId": null,
			"originalText": "lets say we samples A\nnow so we repeat the\nprocess",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 847,
			"versionNonce": 458714806,
			"isDeleted": false,
			"id": "Qfbhibg77isIMXSECwiNT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4223.3483832864795,
			"y": 3267.5066227628013,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 35.84232301421708,
			"seed": 1037300022,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 784,
			"versionNonce": 388245494,
			"isDeleted": false,
			"id": "TwlS2OaBmk3VjFqwHWi9o",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4224.704821570453,
			"y": 3303.7294846957093,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 0.5547199100998836,
			"height": 128.69501914316538,
			"seed": 1810651766,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5547199100998836,
					-128.69501914316538
				]
			]
		},
		{
			"type": "rectangle",
			"version": 875,
			"versionNonce": 59226422,
			"isDeleted": false,
			"id": "zuUwkHdcRhQ5UfT6xeuTG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4189.24363185652,
			"y": 3257.215830936778,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.513653923740556,
			"seed": 631610294,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 900,
			"versionNonce": 1474765430,
			"isDeleted": false,
			"id": "d1SxX4Jj64VmW1PlPsHdj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4154.804710899188,
			"y": 3266.8382834526847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 36.17649245774056,
			"seed": 1898231030,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 921,
			"versionNonce": 1460102070,
			"isDeleted": false,
			"id": "msyuSx7RetZ4R3202zXSU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4121.034129147831,
			"y": 3266.4351933484377,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 36.91375190328609,
			"seed": 1206822454,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 908,
			"versionNonce": 588086518,
			"isDeleted": false,
			"id": "W1zefdeZEgxF578NeyG1a",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4086.929378003788,
			"y": 3255.8514616183174,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 47.878023371715706,
			"seed": 719875958,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 904,
			"versionNonce": 1367240246,
			"isDeleted": false,
			"id": "y7Lcs3IqxBEd6p6dKgXvS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4052.824626758392,
			"y": 3256.4101096569275,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 47.319375888592276,
			"seed": 911675574,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 921,
			"versionNonce": 2134849398,
			"isDeleted": false,
			"id": "8C3PXK96Qb_-5TyFkZmTP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4018.7198754770216,
			"y": 3266.5725754613914,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 37.15691018141843,
			"seed": 903842294,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 895,
			"versionNonce": 1687476406,
			"isDeleted": false,
			"id": "18ZXrkdnQYPh_F9kzal-9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3984.615124403268,
			"y": 3255.183123763306,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 48.546362258761754,
			"seed": 948362038,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 944,
			"versionNonce": 1763987958,
			"isDeleted": false,
			"id": "ZM127UGfGG1qFqdCFusmC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4227.454229809713,
			"y": 3304.068676082278,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 303.15542754404066,
			"height": 0.5327636926773139,
			"seed": 615646326,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					303.15542754404066,
					-0.5327636926773139
				]
			]
		},
		{
			"type": "text",
			"version": 733,
			"versionNonce": 938648374,
			"isDeleted": false,
			"id": "050ipAlq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4304.997003752655,
			"y": 3193.1347543402835,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 65.54670715332031,
			"height": 16.76001831425987,
			"seed": 1277560246,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407896,
			"fontFamily": 1,
			"text": "probability",
			"rawText": "probability",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 768,
			"versionNonce": 1399114870,
			"isDeleted": false,
			"id": "wPIE5DBV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3943.6474843608594,
			"y": 3303.2819031620065,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 52.61143493652344,
			"height": 16.760018314259874,
			"seed": 515830,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "PqHjF7EYnvIzD7-oXv2Cd",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407898,
			"fontFamily": 1,
			"text": "scenario",
			"rawText": "scenario",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scenario",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 753,
			"versionNonce": 648586998,
			"isDeleted": false,
			"id": "MsdctTfo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4177.101336729619,
			"y": 3308.198589637993,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.03155517578125,
			"height": 13.408014651407898,
			"seed": 618434614,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "A",
			"rawText": "A",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 773,
			"versionNonce": 1277450294,
			"isDeleted": false,
			"id": "6vJrLluM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4142.310941539207,
			"y": 3307.55184166502,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.7925872802734375,
			"height": 13.408014651407898,
			"seed": 1183390070,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "B",
			"rawText": "B",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "B",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 795,
			"versionNonce": 1100472694,
			"isDeleted": false,
			"id": "OZ4ILVrW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4107.085402058285,
			"y": 3307.9426325910035,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 6.902923583984375,
			"height": 13.408014651407898,
			"seed": 743602870,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "C",
			"rawText": "C",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "C",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 745,
			"versionNonce": 1783120566,
			"isDeleted": false,
			"id": "XmqiRVGI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4077.0500074620522,
			"y": 3306.44003047107,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.824142456054688,
			"height": 13.408014651407898,
			"seed": 1826468854,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AB",
			"rawText": "AB",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AB",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 761,
			"versionNonce": 2027584502,
			"isDeleted": false,
			"id": "nePxwTyT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4043.7784226110434,
			"y": 3307.417007786028,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 13.934478759765625,
			"height": 13.408014651407898,
			"seed": 36685110,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AC",
			"rawText": "AC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 754,
			"versionNonce": 55807286,
			"isDeleted": false,
			"id": "kdL13VA4",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4007.8156546426835,
			"y": 3307.417007786028,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.695510864257812,
			"height": 13.408014651407898,
			"seed": 1571663478,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "BC",
			"rawText": "BC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "BC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 757,
			"versionNonce": 387479158,
			"isDeleted": false,
			"id": "XcZj3Qg9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3976.944322052008,
			"y": 3307.2216123230364,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 21.727066040039062,
			"height": 13.408014651407898,
			"seed": 2082238390,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "ABC",
			"rawText": "ABC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ABC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"id": "PqHjF7EYnvIzD7-oXv2Cd",
			"type": "arrow",
			"x": -3876.7238191930865,
			"y": 3295.3050928786215,
			"width": 206.67763945111756,
			"height": 2.1362029917427208,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 667435946,
			"version": 972,
			"versionNonce": 331108522,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216619298,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					206.67763945111756,
					2.1362029917427208
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "wPIE5DBV",
				"focus": -1.9390697545306868,
				"gap": 14.312230231249487
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "XPQzNvIT",
			"type": "text",
			"x": -3914.071382420972,
			"y": 3183.718289439268,
			"width": 261.20904541015625,
			"height": 80.98449252148491,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1807803958,
			"version": 761,
			"versionNonce": 1559875830,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Overtime, points that never occur\nwill result in very low probability\nand things that did occur (or variations of them\ngiven values of the hidden layer) will be\nwith high probability exactly how the distribution\nof the original dataset is",
			"rawText": "Overtime, points that never occur\nwill result in very low probability\nand things that did occur (or variations of them\ngiven values of the hidden layer) will be\nwith high probability exactly how the distribution\nof the original dataset is",
			"fontSize": 10.797932336197988,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 76,
			"containerId": null,
			"originalText": "Overtime, points that never occur\nwill result in very low probability\nand things that did occur (or variations of them\ngiven values of the hidden layer) will be\nwith high probability exactly how the distribution\nof the original dataset is",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 905,
			"versionNonce": 851460662,
			"isDeleted": false,
			"id": "CA-x_VDslgyltR7QcvNQ0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3568.396347227988,
			"y": 3295.801987913508,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 4.921027838825923,
			"seed": 447476534,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 806,
			"versionNonce": 19303286,
			"isDeleted": false,
			"id": "Q3ntHZRoXb1I2nczz58iX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3569.75278551196,
			"y": 3301.103554671026,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 0.5547199100998836,
			"height": 128.69501914316538,
			"seed": 846470262,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5547199100998836,
					-128.69501914316538
				]
			]
		},
		{
			"type": "rectangle",
			"version": 897,
			"versionNonce": 1450290358,
			"isDeleted": false,
			"id": "S_z6vzFkVSLVJPJDPRTuc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3534.291595798027,
			"y": 3254.5899009120944,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.513653923740556,
			"seed": 166010294,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 950,
			"versionNonce": 809936374,
			"isDeleted": false,
			"id": "PIXeuLcs5Uwb2BU5dtjd9",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3499.852674840696,
			"y": 3298.2705915922,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 2.118254293541668,
			"seed": 1713633014,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 990,
			"versionNonce": 262829878,
			"isDeleted": false,
			"id": "BBzX3AGzQR-nUJxJvZIOc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3466.0820930893383,
			"y": 3298.763770913326,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 1.9592443137134987,
			"seed": 531998774,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 998,
			"versionNonce": 218243190,
			"isDeleted": false,
			"id": "csu56ltq7HbFL7csHTSLM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3431.9773419452954,
			"y": 3217.3747545786878,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 83.72880038666206,
			"seed": 914305398,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 947,
			"versionNonce": 1813160374,
			"isDeleted": false,
			"id": "WtA2eJ2ZC5m1Co1OYdkPl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3399.2169948379606,
			"y": 3252.8879102068704,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 47.319375888592276,
			"seed": 1707446966,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 968,
			"versionNonce": 805370614,
			"isDeleted": false,
			"id": "yJxpwCdFYRT3M5ZU8zbTK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3364.664108843903,
			"y": 3277.3906868173126,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 23.7128688008138,
			"seed": 942525430,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 947,
			"versionNonce": 793914422,
			"isDeleted": false,
			"id": "LQJ8nnfzoQNRyDPa74s2p",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3329.6630883447756,
			"y": 3218.050820861737,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 83.05273513564727,
			"seed": 465362230,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 966,
			"versionNonce": 669726070,
			"isDeleted": false,
			"id": "gv-Nkq1rUx2B_PgV8V-OG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3572.5021937512206,
			"y": 3301.442746057595,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 303.15542754404066,
			"height": 0.5327636926773139,
			"seed": 1977075318,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					303.15542754404066,
					-0.5327636926773139
				]
			]
		},
		{
			"type": "text",
			"version": 755,
			"versionNonce": 1393628854,
			"isDeleted": false,
			"id": "0DdmHCrR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3650.044967694162,
			"y": 3190.5088243156,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 65.54670715332031,
			"height": 16.76001831425987,
			"seed": 927172534,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407896,
			"fontFamily": 1,
			"text": "probability",
			"rawText": "probability",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 790,
			"versionNonce": 2036912118,
			"isDeleted": false,
			"id": "CwuTskK2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3288.695448302367,
			"y": 3300.655973137323,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 52.61143493652344,
			"height": 16.760018314259874,
			"seed": 1881481462,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407898,
			"fontFamily": 1,
			"text": "scenario",
			"rawText": "scenario",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scenario",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 775,
			"versionNonce": 116875574,
			"isDeleted": false,
			"id": "ZAu7nL1s",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3522.1493006711275,
			"y": 3305.5726596133095,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.03155517578125,
			"height": 13.408014651407898,
			"seed": 1677824566,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "A",
			"rawText": "A",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 795,
			"versionNonce": 522308214,
			"isDeleted": false,
			"id": "fLl5Cd9k",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3487.3589054807157,
			"y": 3304.925911640337,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.7925872802734375,
			"height": 13.408014651407898,
			"seed": 498981750,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "B",
			"rawText": "B",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "B",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 817,
			"versionNonce": 816647094,
			"isDeleted": false,
			"id": "kkHNetD2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3452.133365999792,
			"y": 3305.31670256632,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 6.902923583984375,
			"height": 13.408014651407898,
			"seed": 60751030,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "C",
			"rawText": "C",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "C",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 767,
			"versionNonce": 163456246,
			"isDeleted": false,
			"id": "zEBwwEeP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3422.0979714035598,
			"y": 3303.8141004463864,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.824142456054688,
			"height": 13.408014651407898,
			"seed": 1800009206,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AB",
			"rawText": "AB",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AB",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 783,
			"versionNonce": 1809454646,
			"isDeleted": false,
			"id": "NDKN0AMq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3388.826386552551,
			"y": 3304.7910777613447,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 13.934478759765625,
			"height": 13.408014651407898,
			"seed": 767805238,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AC",
			"rawText": "AC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 776,
			"versionNonce": 535158646,
			"isDeleted": false,
			"id": "J6PEN3ys",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3352.863618584191,
			"y": 3304.7910777613447,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.695510864257812,
			"height": 13.408014651407898,
			"seed": 997290102,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "BC",
			"rawText": "BC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "BC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 779,
			"versionNonce": 170295478,
			"isDeleted": false,
			"id": "60IqkPLs",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -3321.9922859935155,
			"y": 3304.595682298353,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 21.727066040039062,
			"height": 13.408014651407898,
			"seed": 806875574,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "ABC",
			"rawText": "ABC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ABC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "image",
			"version": 495,
			"versionNonce": 1044445686,
			"isDeleted": false,
			"id": "kHwBODb8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2684.5360466070483,
			"y": 3125.4543479271683,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 204.84841588936445,
			"height": 26.9955276753426,
			"seed": 19562,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9270c865a6e134f8fe7cb6d1ef11d7d13c584a58",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Hc_RQG79EKqOPYP8LMPfh",
			"type": "arrow",
			"x": -2419.1994698882518,
			"y": 1797.7792446563158,
			"width": 263.16132387036646,
			"height": 0.8519339579920597,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1543193334,
			"version": 470,
			"versionNonce": 838904682,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619299,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-263.16132387036646,
					-0.8519339579920597
				]
			],
			"lastCommittedPoint": [
				-263.1613238703667,
				3.3630840111229645
			],
			"startBinding": {
				"elementId": "wugb9a97",
				"focus": 0.13596940360493112,
				"gap": 20.89659023551394
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "gAqZ2LFv",
			"type": "text",
			"x": -3372.039521106919,
			"y": 1682.9868002281262,
			"width": 773.8790893554688,
			"height": 300,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 868706218,
			"version": 1108,
			"versionNonce": 930575478,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "A popular use case for RBMs is recommendation systems\nlets say you click on a yt video, which is the input x\nthe hidden layer will be (trained) to contain the structure\nof videos like \"what style is this video?\" \"whats the topic?\"\netc...\nafter enough training, we will understand the patterns\nthat activate the hidden nodes i.e learning the probability distribution\nof the dataset\nby adjusting the weights and biases, this model can figure out\nhow likely is someone who regularly watches cat videos on youtube\nto also watch animal documentaries.\nand this applies to any example where you want to learn more about ur data",
			"rawText": "A popular use case for RBMs is recommendation systems\nlets say you click on a yt video, which is the input x\nthe hidden layer will be (trained) to contain the structure\nof videos like \"what style is this video?\" \"whats the topic?\"\netc...\nafter enough training, we will understand the patterns\nthat activate the hidden nodes i.e learning the probability distribution\nof the dataset\nby adjusting the weights and biases, this model can figure out\nhow likely is someone who regularly watches cat videos on youtube\nto also watch animal documentaries.\nand this applies to any example where you want to learn more about ur data",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 293,
			"containerId": null,
			"originalText": "A popular use case for RBMs is recommendation systems\nlets say you click on a yt video, which is the input x\nthe hidden layer will be (trained) to contain the structure\nof videos like \"what style is this video?\" \"whats the topic?\"\netc...\nafter enough training, we will understand the patterns\nthat activate the hidden nodes i.e learning the probability distribution\nof the dataset\nby adjusting the weights and biases, this model can figure out\nhow likely is someone who regularly watches cat videos on youtube\nto also watch animal documentaries.\nand this applies to any example where you want to learn more about ur data",
			"lineHeight": 1.25
		},
		{
			"id": "TJVZWu2C",
			"type": "text",
			"x": -2060.485384226283,
			"y": 2900.927801322792,
			"width": 879.3389892578125,
			"height": 150,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 398706934,
			"version": 499,
			"versionNonce": 1153267126,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ZpqX4T5eiYwOfXcQ_NRQ7",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Task:\nShow to the RBM, samples form a database of visible unit combinations (possible inputs)\nand adjust the parameters (W and the biases) such that the probability distribution\ndefined by the energy function of our RBM p(v,h) encodes the observed probability\ndistribution p(h)\n",
			"rawText": "Task:\nShow to the RBM, samples form a database of visible unit combinations (possible inputs)\nand adjust the parameters (W and the biases) such that the probability distribution\ndefined by the energy function of our RBM p(v,h) encodes the observed probability\ndistribution p(h)\n",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 143,
			"containerId": null,
			"originalText": "Task:\nShow to the RBM, samples form a database of visible unit combinations (possible inputs)\nand adjust the parameters (W and the biases) such that the probability distribution\ndefined by the energy function of our RBM p(v,h) encodes the observed probability\ndistribution p(h)\n",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 447,
			"versionNonce": 307757110,
			"isDeleted": false,
			"id": "NVejqMyb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2701.1180480142916,
			"y": 3193.0326904992817,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 222.58471229363371,
			"height": 25.395571201287066,
			"seed": 73483,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bddb6e9e5ba1ba8392c44c9f81fed1f410e5e101",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ZpqX4T5eiYwOfXcQ_NRQ7",
			"type": "arrow",
			"x": -2075.377808840406,
			"y": 2970.18509997757,
			"width": 200.47414261214135,
			"height": 1.4404034114008937,
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
			"seed": 216435766,
			"version": 480,
			"versionNonce": 611036714,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619300,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-200.47414261214135,
					1.4404034114008937
				]
			],
			"lastCommittedPoint": [
				-214.77844707900294,
				0
			],
			"startBinding": {
				"elementId": "TJVZWu2C",
				"focus": 0.11526144349039587,
				"gap": 14.892424614123229
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "RJxIubTvCcTa_gL2kvQ6X",
			"type": "arrow",
			"x": -1196.4858452032222,
			"y": 2985.029543217959,
			"width": 140.59118316982483,
			"height": 0.26658349262561387,
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
			"seed": 1779455478,
			"version": 473,
			"versionNonce": 2145933546,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619300,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					140.59118316982483,
					0.26658349262561387
				]
			],
			"lastCommittedPoint": [
				126.66666666666663,
				1.9047619047619264
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "Aptb9c6w",
				"focus": -0.16745248571702337,
				"gap": 2.927048415380341
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Aptb9c6w",
			"type": "text",
			"x": -1052.967613618017,
			"y": 2927.24078706952,
			"width": 394.9395751953125,
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
			"seed": 292206902,
			"version": 609,
			"versionNonce": 1758405622,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "RJxIubTvCcTa_gL2kvQ6X",
					"type": "arrow"
				},
				{
					"id": "mxMgVeDl1SN08_M_v1bjp",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Fancy words for\nif we take our p(v,h) and theoretically\nmarginalize over all possible values of h\nthen we get something close to p(v)",
			"rawText": "Fancy words for\nif we take our p(v,h) and theoretically\nmarginalize over all possible values of h\nthen we get something close to p(v)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "Fancy words for\nif we take our p(v,h) and theoretically\nmarginalize over all possible values of h\nthen we get something close to p(v)",
			"lineHeight": 1.25
		},
		{
			"id": "mxMgVeDl1SN08_M_v1bjp",
			"type": "arrow",
			"x": -865.8885929164101,
			"y": 3043.7038908554305,
			"width": 368.1921670971583,
			"height": 108.73511367489209,
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
			"seed": 382948342,
			"version": 601,
			"versionNonce": 67218346,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619300,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-51.676093627671435,
					101.199016687523
				],
				[
					-368.1921670971583,
					108.73511367489209
				]
			],
			"lastCommittedPoint": [
				-366.03899652933865,
				94.7395049840643
			],
			"startBinding": {
				"elementId": "Aptb9c6w",
				"focus": -0.10559488573152093,
				"gap": 16.463103785910334
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "LyxgUr5T",
			"type": "text",
			"x": -1210.713720414401,
			"y": 3089.887591614332,
			"width": 294.99261474609375,
			"height": 60,
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
			"seed": 865050218,
			"version": 335,
			"versionNonce": 2035972342,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "But that is not something we can do\nbut it turns out its something\nwe can derive",
			"rawText": "But that is not something we can do\nbut it turns out its something\nwe can derive",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "But that is not something we can do\nbut it turns out its something\nwe can derive",
			"lineHeight": 1.25
		},
		{
			"id": "fnlambpY",
			"type": "text",
			"x": -1735.3889247862994,
			"y": 3099.8504731020116,
			"width": 276.8371887207031,
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
			"seed": 1408756330,
			"version": 275,
			"versionNonce": 1288432182,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Free energy function",
			"rawText": "Free energy function",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Free energy function",
			"lineHeight": 1.25
		},
		{
			"id": "1SWBHol3",
			"type": "text",
			"x": -2002.4372031105258,
			"y": 3137.343153544026,
			"width": 789.19921875,
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
			"seed": 897469674,
			"version": 494,
			"versionNonce": 729625462,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "The probability function correlates to its corresponding Energy function\nmeaning if we can derive the energy function then we can derive the distribution\nthat it builds and thus avoid having to marginalize p(v,h) to p(v) ",
			"rawText": "The probability function correlates to its corresponding Energy function\nmeaning if we can derive the energy function then we can derive the distribution\nthat it builds and thus avoid having to marginalize p(v,h) to p(v) ",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "The probability function correlates to its corresponding Energy function\nmeaning if we can derive the energy function then we can derive the distribution\nthat it builds and thus avoid having to marginalize p(v,h) to p(v) ",
			"lineHeight": 1.25
		},
		{
			"id": "JJVeFEci",
			"type": "image",
			"x": -1812.0409658539593,
			"y": 3224.2146286856196,
			"width": 934.5273531711288,
			"height": 472.5667952353375,
			"angle": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"roundness": null,
			"seed": 65115,
			"version": 535,
			"versionNonce": 1337152694,
			"updated": 1708216618471,
			"isDeleted": false,
			"groupIds": [],
			"boundElements": [],
			"link": null,
			"locked": false,
			"fileId": "9d0b0bfbcbd7fbf841215fb6c3303b2a15727338",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 349,
			"versionNonce": 1662209526,
			"isDeleted": false,
			"id": "aP5IqpaI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1895.3893006840935,
			"y": 3247.4170531002637,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 76.57551359602786,
			"height": 41.993023584918504,
			"seed": 22770,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2813ad29ca21e8d35c18edb984a5d42b7b056096",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "3e1blE5bN-qCOkk3667b_",
			"type": "arrow",
			"x": -1334.305793435019,
			"y": 3264.4184238605762,
			"width": 250.78018701690235,
			"height": 0,
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
			"seed": 563668470,
			"version": 244,
			"versionNonce": 312614710,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					250.78018701690235,
					0
				]
			],
			"lastCommittedPoint": [
				250.78018701690235,
				0
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "R9rTUWYn",
			"type": "text",
			"x": -1067.1860784284008,
			"y": 3250.289962620187,
			"width": 319.11962890625,
			"height": 50,
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
			"seed": 859898026,
			"version": 326,
			"versionNonce": 583321718,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "marginalization of p(x,h) over all\nvalues of h",
			"rawText": "marginalization of p(x,h) over all\nvalues of h",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "marginalization of p(x,h) over all\nvalues of h",
			"lineHeight": 1.25
		},
		{
			"id": "KYLRT5U7O6MMRULRSju99",
			"type": "line",
			"x": -1911.0352603964473,
			"y": 3270.633845261786,
			"width": 86.74870332974206,
			"height": 3.168219694094205,
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
			"seed": 1375845290,
			"version": 255,
			"versionNonce": 54544822,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-86.74870332974206,
					-3.168219694094205
				]
			],
			"lastCommittedPoint": [
				-73.13480496254124,
				-3.703028099369021
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "0wXWfmmQ",
			"type": "text",
			"x": -2292.939446788127,
			"y": 3245.56491307882,
			"width": 284.5285949707031,
			"height": 60,
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
			"seed": 1907852470,
			"version": 321,
			"versionNonce": 1664721654,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "We are using x instead of v\nhere because the derivation I stole\ndoes... deal with it.. ",
			"rawText": "We are using x instead of v\nhere because the derivation I stole\ndoes... deal with it.. ",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "We are using x instead of v\nhere because the derivation I stole\ndoes... deal with it.. ",
			"lineHeight": 1.25
		},
		{
			"id": "Kw6yvkI6ucRWuqktwV-5b",
			"type": "line",
			"x": -1667.229153224083,
			"y": 3381.650769011504,
			"width": 78.52854386103832,
			"height": 0.7775103352578299,
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
			"seed": 2017770986,
			"version": 219,
			"versionNonce": 1161155638,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-78.52854386103832,
					-0.7775103352578299
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "dHqM1Fbb",
			"type": "text",
			"x": -1777.295903405469,
			"y": 3383.2057896820197,
			"width": 126.83226013183594,
			"height": 60,
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
			"seed": 1257435126,
			"version": 287,
			"versionNonce": 320462198,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "unrelated to \ndifferent values\nof h",
			"rawText": "unrelated to \ndifferent values\nof h",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "unrelated to \ndifferent values\nof h",
			"lineHeight": 1.25
		},
		{
			"id": "h0RSu75lpHYIRE7ASzc0y",
			"type": "arrow",
			"x": -831.4637751500584,
			"y": 3448.5088554446584,
			"width": 69.44073238007911,
			"height": 0.7085789018374271,
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
			"seed": 980741354,
			"version": 239,
			"versionNonce": 841662134,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					69.44073238007911,
					-0.7085789018374271
				]
			],
			"lastCommittedPoint": [
				69.44073238007911,
				-0.7085789018374271
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "4m8aoMLr",
			"type": "text",
			"x": -784.3867843932019,
			"y": 3420.874278272994,
			"width": 251.6325225830078,
			"height": 80,
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
			"seed": 1461561514,
			"version": 314,
			"versionNonce": 386758646,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Exponential of a sum \n=\nproduct of all the eponentiated\nsums",
			"rawText": "Exponential of a sum \n=\nproduct of all the eponentiated\nsums",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "Exponential of a sum \n=\nproduct of all the eponentiated\nsums",
			"lineHeight": 1.25
		},
		{
			"id": "qAB2GeT-v_owIfC9MHrOO",
			"type": "arrow",
			"x": -1806.668221633946,
			"y": 3528.6618680498705,
			"width": 91.83349712693666,
			"height": 0.743121038312438,
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
			"seed": 878829750,
			"version": 259,
			"versionNonce": 1506216246,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-91.83349712693666,
					0.743121038312438
				]
			],
			"lastCommittedPoint": [
				-127.81681858975139,
				0.743121038312438
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "xjJifAaL",
			"type": "text",
			"x": -2136.526758786181,
			"y": 3508.6679638426012,
			"width": 220.41644287109375,
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
			"seed": 1340137194,
			"version": 339,
			"versionNonce": 1237086838,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "We evaluate the two cases\nwhen hj=1 and when hj=0",
			"rawText": "We evaluate the two cases\nwhen hj=1 and when hj=0",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "We evaluate the two cases\nwhen hj=1 and when hj=0",
			"lineHeight": 1.25
		},
		{
			"id": "2PgBtZQF",
			"type": "text",
			"x": -1926.4583918583814,
			"y": 3671.781424282504,
			"width": 785.9390869140625,
			"height": 25,
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
			"seed": 1383731562,
			"version": 344,
			"versionNonce": 28488630,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "This final result is also called the free energy functions (also called Softplus)",
			"rawText": "This final result is also called the free energy functions (also called Softplus)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "This final result is also called the free energy functions (also called Softplus)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 414,
			"versionNonce": 2077150454,
			"isDeleted": false,
			"id": "slJMSQek",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1885.60571610771,
			"y": 3717.2204943422253,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 231.6531267251862,
			"height": 56.73137797351499,
			"seed": 72474,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5207afc8cbaf940ad1ee7e5a5e3fb97983c8d559",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "I1seJjCP",
			"type": "text",
			"x": -1641.1994408879577,
			"y": 3738.1002373339747,
			"width": 97.95988464355469,
			"height": 25,
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
			"seed": 893137194,
			"version": 226,
			"versionNonce": 630570550,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "such that",
			"rawText": "such that",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "such that",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 362,
			"versionNonce": 1944881014,
			"isDeleted": false,
			"id": "2oT1mldg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1533.4888483501327,
			"y": 3713.863034484249,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 418.5927639313161,
			"height": 69.0881260857512,
			"seed": 60237,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "68f6888780542236d2df59319879564b2a1c94a8",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "T7NHP7MxMK0s5PBvivh0O",
			"type": "arrow",
			"x": -1471.1515161196637,
			"y": 3803.4221272984596,
			"width": 2.102068267714685,
			"height": 179.84619225654342,
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
			"seed": 275127670,
			"version": 694,
			"versionNonce": 1189258858,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619302,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.102068267714685,
					70.450168831072
				],
				[
					-1.4688327187459436,
					179.84619225654342
				]
			],
			"lastCommittedPoint": [
				-740.8710115405208,
				86.64423694287461
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "SnR4mSyv",
				"focus": 0.009613456614666279,
				"gap": 4.840592350419229
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "SnR4mSyv",
			"type": "text",
			"x": -1720.1655144005679,
			"y": 3988.1089119054222,
			"width": 490.99945068359375,
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
			"seed": 1638471606,
			"version": 668,
			"versionNonce": 1857921526,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "T7NHP7MxMK0s5PBvivh0O",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Now that we have our probability distribution\nwe can learn from it how to tune our parameters\nsuch that the likelihood of our data increases\nto a point where it matches our dataset",
			"rawText": "Now that we have our probability distribution\nwe can learn from it how to tune our parameters\nsuch that the likelihood of our data increases\nto a point where it matches our dataset",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "Now that we have our probability distribution\nwe can learn from it how to tune our parameters\nsuch that the likelihood of our data increases\nto a point where it matches our dataset",
			"lineHeight": 1.25
		},
		{
			"id": "0K5_4Oy1cVQ609HE480bN",
			"type": "arrow",
			"x": -1118.6506530805182,
			"y": 3685.7682703915116,
			"width": 164.78248520243238,
			"height": 1.6478248520243142,
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
			"seed": 1740047722,
			"version": 248,
			"versionNonce": 518659190,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					164.78248520243238,
					-1.6478248520243142
				]
			],
			"lastCommittedPoint": [
				164.78248520243238,
				-1.6478248520243142
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Tt6y1EKX-onhsjoHOfBSH",
			"type": "arrow",
			"x": -905.4077862216134,
			"y": 3721.999557434604,
			"width": 178.16210891304647,
			"height": 0.4688476550344359,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 604967670,
			"version": 554,
			"versionNonce": 1633044778,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216619303,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					178.16210891304647,
					-0.4688476550344359
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "Q0rscUAw",
				"focus": -2.8118689369796304,
				"gap": 14.896642008922527
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "1Q0_-oFQqNiQBxOnUgloF",
			"type": "arrow",
			"x": -825.6226509404989,
			"y": 3722.5722946904234,
			"width": 1.406542965102978,
			"height": 115.80537079348017,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1255531510,
			"version": 620,
			"versionNonce": 449287146,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216619303,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.406542965102978,
					-115.80537079348017
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "Q0rscUAw",
				"focus": -0.02628261199120618,
				"gap": 14.32390475310308
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Ds7kDJjsA9sqsD0bgakQh",
			"type": "line",
			"x": -824.1972401800401,
			"y": 3720.2408158794838,
			"width": 89.45899271462608,
			"height": 96.20391676850676,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 201829174,
			"version": 502,
			"versionNonce": 401319990,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					89.45899271462608,
					-96.20391676850676
				]
			],
			"lastCommittedPoint": [
				138.8586391834341,
				-149.32813975678846
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "aFIU6FP3Oi59CRyBet1GD",
			"type": "line",
			"x": -905.1363288266066,
			"y": 3720.5958118823196,
			"width": 169.688089355521,
			"height": 96.55891277134255,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 1358967402,
			"version": 512,
			"versionNonce": 938815862,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					55.37937644238759,
					-4.969944039701648
				],
				[
					82.35907265790976,
					-13.489848107761198
				],
				[
					130.28353304074517,
					-55.37937644238766
				],
				[
					169.688089355521,
					-96.55891277134255
				]
			],
			"lastCommittedPoint": [
				263.3905933717521,
				-149.87916610275443
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Q0rscUAw",
			"type": "text",
			"x": -894.2732325765065,
			"y": 3736.8961994435263,
			"width": 140.45423889160156,
			"height": 16.106126568842715,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1004922410,
			"version": 329,
			"versionNonce": 1216058038,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Tt6y1EKX-onhsjoHOfBSH",
					"type": "arrow"
				},
				{
					"id": "1Q0_-oFQqNiQBxOnUgloF",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "its like a smooth Relu",
			"rawText": "its like a smooth Relu",
			"fontSize": 12.88490125507417,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 11,
			"containerId": null,
			"originalText": "its like a smooth Relu",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 523,
			"versionNonce": 206423670,
			"isDeleted": false,
			"id": "U7VPrlgb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1655.4009933334437,
			"y": 4393.939672013119,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 464.820494496854,
			"height": 65.07486922955955,
			"seed": 72339,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "38d677b40f9a99e8245fed7311551c22e111d810",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "GnW94-QQlXeoUwTcR6h2K",
			"type": "line",
			"x": -1581.3694228486288,
			"y": 4386.546641750018,
			"width": 52.816998197281464,
			"height": 44.848611715026436,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
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
			"seed": 65391734,
			"version": 400,
			"versionNonce": 251234230,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-52.816998197281464,
					-44.848611715026436
				]
			],
			"lastCommittedPoint": [
				0.4958732449317722,
				-42.14922581921792
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "5KMNZXwO",
			"type": "text",
			"x": -1814.6514044424543,
			"y": 4221.121890020698,
			"width": 312.83270263671875,
			"height": 120,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 370423094,
			"version": 671,
			"versionNonce": 1629167862,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "if elements of x are 1 when c\nis positive and 0 when c is negative\ni.e\nif it has features that we know have\na higher prior to occur and 0 otherwise\nthe probability increases",
			"rawText": "if elements of x are 1 when c\nis positive and 0 when c is negative\ni.e\nif it has features that we know have\na higher prior to occur and 0 otherwise\nthe probability increases",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "if elements of x are 1 when c\nis positive and 0 when c is negative\ni.e\nif it has features that we know have\na higher prior to occur and 0 otherwise\nthe probability increases",
			"lineHeight": 1.25
		},
		{
			"id": "UuHTYYzLhw46xDtfzPIqi",
			"type": "line",
			"x": -1250.57075169075,
			"y": 4390.004904528959,
			"width": 0.38854286522587245,
			"height": 58.28142978385722,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1890062826,
			"version": 384,
			"versionNonce": 1178047030,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.38854286522587245,
					-58.28142978385722
				]
			],
			"lastCommittedPoint": [
				0.38854286522587245,
				-58.28142978385722
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "QCDEX3N4",
			"type": "text",
			"x": -1463.3060010232416,
			"y": 4098.736274405453,
			"width": 368.57684326171875,
			"height": 240,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 490792490,
			"version": 1274,
			"versionNonce": 1228135286,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "for this to be big\nwe want the input vector to be\nwell aligned with W's jth row, so for\na given hidden unit j, if x is positive\nfor positive values of wj and 0 for negative\nvalues of wj, then this means the features\ndetected in x via the dot product match\nwhat we learned (and is stored) in h\nthe bias of the hidden unit bj is the threshold\nof \"how present must this feature be in order\nfor us to consider it a meaningful feature\n andlet it significantly affect the prob\"",
			"rawText": "for this to be big\nwe want the input vector to be\nwell aligned with W's jth row, so for\na given hidden unit j, if x is positive\nfor positive values of wj and 0 for negative\nvalues of wj, then this means the features\ndetected in x via the dot product match\nwhat we learned (and is stored) in h\nthe bias of the hidden unit bj is the threshold\nof \"how present must this feature be in order\nfor us to consider it a meaningful feature\n andlet it significantly affect the prob\"",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 234,
			"containerId": null,
			"originalText": "for this to be big\nwe want the input vector to be\nwell aligned with W's jth row, so for\na given hidden unit j, if x is positive\nfor positive values of wj and 0 for negative\nvalues of wj, then this means the features\ndetected in x via the dot product match\nwhat we learned (and is stored) in h\nthe bias of the hidden unit bj is the threshold\nof \"how present must this feature be in order\nfor us to consider it a meaningful feature\n andlet it significantly affect the prob\"",
			"lineHeight": 1.25
		},
		{
			"id": "plDUvDd-zCZSYm5jzQoTK",
			"type": "arrow",
			"x": -2596.247900561688,
			"y": 3242.449772187304,
			"width": 0.9874417274882035,
			"height": 111.86186865827176,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 104088822,
			"version": 543,
			"versionNonce": 356615850,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619304,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.9874417274882035,
					111.86186865827176
				]
			],
			"lastCommittedPoint": [
				3.165901943158815,
				126.63607772634532
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "27OfqHbt",
				"focus": -0.0007636792881276572,
				"gap": 13.312702850164442
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "27OfqHbt",
			"type": "text",
			"x": -2844.861296777607,
			"y": 3367.62434369574,
			"width": 500.0394287109375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 213097782,
			"version": 330,
			"versionNonce": 826275318,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "plDUvDd-zCZSYm5jzQoTK",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "We can make a loss function out of this objective",
			"rawText": "We can make a loss function out of this objective",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "We can make a loss function out of this objective",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 297,
			"versionNonce": 2078765174,
			"isDeleted": false,
			"id": "EfhB04Gu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2726.476515441676,
			"y": 3392.624344055148,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 262.43211256469357,
			"height": 58.64404750049018,
			"seed": 62724,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "76d4d8d8fa1f3003df60bc193aeb940bd369e8a1",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ESllB8Zt",
			"type": "text",
			"x": -3609.0569983009477,
			"y": 3331.908607543549,
			"width": 409.53948974609375,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1259064950,
			"version": 371,
			"versionNonce": 1909322166,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "We can get the probability of A\nby enumerating over all possible scenarios\nof A and the hidden unit\nas in A and AC",
			"rawText": "We can get the probability of A\nby enumerating over all possible scenarios\nof A and the hidden unit\nas in A and AC",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "We can get the probability of A\nby enumerating over all possible scenarios\nof A and the hidden unit\nas in A and AC",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 352,
			"versionNonce": 30558966,
			"isDeleted": false,
			"id": "2QlOWrJD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2878.0203572969585,
			"y": 3591.0589645027762,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 514.2316296051622,
			"height": 52.07408907394047,
			"seed": 48434,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c0a499b0dc933d7f5542f4266a5e6a88169f7213",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 793,
			"versionNonce": 1517911094,
			"isDeleted": false,
			"id": "ii8sovVKt05kLVDuoVtWo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2553.4196099830588,
			"y": 3645.9307270262243,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 166.04831777073326,
			"height": 12.818810887148446,
			"seed": 2135800874,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.1924475243859545,
					0.2981118810964078
				],
				[
					-4.173566335350517,
					0.8943356432892234
				],
				[
					-6.8565732652188345,
					2.086783167675178
				],
				[
					-10.135803957279967,
					3.2792306920611325
				],
				[
					-13.116922768244692,
					3.875454454253948
				],
				[
					-15.50181781701644,
					4.471678216447087
				],
				[
					-18.482936627981164,
					5.067901978639902
				],
				[
					-19.973496033463526,
					5.36601385973631
				],
				[
					-21.7621673200423,
					5.664125740832718
				],
				[
					-23.550838606621067,
					5.962237621929449
				],
				[
					-25.3395098932,
					6.260349503025857
				],
				[
					-28.022516823068155,
					7.154685146315081
				],
				[
					-30.4074118718399,
					7.452797027411812
				],
				[
					-33.68664256390103,
					7.75090890850822
				],
				[
					-36.965873255962165,
					8.049020789604628
				],
				[
					-41.437551472409254,
					8.943356432894173
				],
				[
					-45.01489404556679,
					9.241468313990582
				],
				[
					-48.890348499821066,
					9.53958019508699
				],
				[
					-53.06391483517158,
					9.53958019508699
				],
				[
					-56.93936928942569,
					10.135803957279805
				],
				[
					-60.516711862583236,
					10.732027719472944
				],
				[
					-64.39216631683735,
					10.732027719472944
				],
				[
					-67.96950888999504,
					11.32825148166576
				],
				[
					-71.24873958205617,
					11.32825148166576
				],
				[
					-75.42230591740669,
					11.626363362762168
				],
				[
					-79.2977603716608,
					11.924475243858575
				],
				[
					-82.27887918262553,
					11.924475243858575
				],
				[
					-86.45244551797605,
					11.924475243858575
				],
				[
					-89.43356432894078,
					12.222587124955307
				],
				[
					-92.71279502100191,
					12.222587124955307
				],
				[
					-95.99202571306304,
					12.222587124955307
				],
				[
					-99.27125640512418,
					12.222587124955307
				],
				[
					-101.95426333499249,
					12.222587124955307
				],
				[
					-104.33915838376423,
					12.222587124955307
				],
				[
					-107.32027719472896,
					12.222587124955307
				],
				[
					-110.30139600569352,
					12.222587124955307
				],
				[
					-113.58062669775482,
					11.626363362762168
				],
				[
					-117.45608115200876,
					11.030139600569353
				],
				[
					-122.22587124955226,
					10.433915838376537
				],
				[
					-126.69754946599934,
					9.53958019508699
				],
				[
					-131.16922768244643,
					8.943356432894173
				],
				[
					-134.44845837450757,
					8.943356432894173
				],
				[
					-138.02580094766512,
					8.347132670701034
				],
				[
					-140.41069599643703,
					8.049020789604628
				],
				[
					-142.1993672830158,
					8.049020789604628
				],
				[
					-143.09370292630518,
					8.049020789604628
				],
				[
					-143.39181480740157,
					8.049020789604628
				],
				[
					-143.68992668849816,
					8.049020789604628
				],
				[
					-144.28615045069097,
					7.75090890850822
				],
				[
					-145.1804860939805,
					7.452797027411812
				],
				[
					-146.0748217372699,
					7.452797027411812
				],
				[
					-146.37293361836632,
					7.154685146315081
				],
				[
					-147.26726926165568,
					6.856573265218673
				],
				[
					-148.45971678604164,
					6.856573265218673
				],
				[
					-149.65216431042742,
					6.558461384122265
				],
				[
					-150.84461183481338,
					6.260349503025857
				],
				[
					-151.4408355970063,
					5.962237621929449
				],
				[
					-152.03705935919928,
					5.664125740832718
				],
				[
					-152.63328312139217,
					5.36601385973631
				],
				[
					-153.22950688358515,
					5.067901978639902
				],
				[
					-154.7200662890675,
					4.471678216447087
				],
				[
					-155.3162900512604,
					4.471678216447087
				],
				[
					-156.21062569454978,
					4.173566335350679
				],
				[
					-157.10496133783926,
					3.875454454253948
				],
				[
					-157.70118510003215,
					3.5773425731575403
				],
				[
					-158.29740886222504,
					2.9811188109647246
				],
				[
					-159.19174450551452,
					2.683006929868317
				],
				[
					-159.489856386611,
					2.683006929868317
				],
				[
					-160.0860801488039,
					2.3848950487715856
				],
				[
					-160.3841920299004,
					2.086783167675178
				],
				[
					-160.68230391099678,
					1.7886712865787702
				],
				[
					-160.98041579209328,
					1.4905594054823623
				],
				[
					-161.57663955428626,
					1.1924475243859545
				],
				[
					-161.87475143538273,
					0.8943356432892234
				],
				[
					-162.47097519757563,
					0.5962237621928156
				],
				[
					-162.76908707867213,
					0.2981118810964078
				],
				[
					-163.3653108408651,
					0.2981118810964078
				],
				[
					-163.66342272196152,
					0
				],
				[
					-164.2596464841545,
					-0.2981118810964078
				],
				[
					-164.5577583652509,
					-0.2981118810964078
				],
				[
					-164.8558702463474,
					-0.2981118810964078
				],
				[
					-165.15398212744387,
					-0.2981118810964078
				],
				[
					-165.45209400854037,
					-0.596223762193139
				],
				[
					-166.04831777073326,
					-0.596223762193139
				],
				[
					-166.04831777073326,
					-0.596223762193139
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 736,
			"versionNonce": 296256886,
			"isDeleted": false,
			"id": "KP1ajpwN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2684.829829256617,
			"y": 3663.8065648425877,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 78.45973205566406,
			"height": 14.222369897229989,
			"seed": 257468138,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 11.377895917783992,
			"fontFamily": 1,
			"text": "positive phase",
			"rawText": "positive phase",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "positive phase",
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "freedraw",
			"version": 772,
			"versionNonce": 950298294,
			"isDeleted": false,
			"id": "9cDEjK42I2lrRYy6hJ0Lw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2525.5853608695115,
			"y": 3648.0749781819777,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 171.0366091701144,
			"height": 6.075900858618694,
			"seed": 189501302,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.30379504293103354,
					0
				],
				[
					0.9113851287929359,
					0.6075900858617376
				],
				[
					2.126565300516576,
					0.9113851287926064
				],
				[
					3.037950429309347,
					1.2151801717238047
				],
				[
					4.253130601033152,
					1.5189752146546736
				],
				[
					5.468310772756792,
					1.8227702575855422
				],
				[
					6.9872859874114654,
					2.126565300516411
				],
				[
					9.113851287928041,
					2.126565300516411
				],
				[
					10.936621545513583,
					2.734155386378478
				],
				[
					13.06318684603016,
					3.037950429309347
				],
				[
					17.316317447063145,
					3.949335558101953
				],
				[
					22.480833176888904,
					4.860720686894889
				],
				[
					26.733963777922057,
					5.164515729825758
				],
				[
					30.987094378955042,
					5.772105815687495
				],
				[
					34.328839851195255,
					5.772105815687495
				],
				[
					37.06299523757374,
					6.075900858618694
				],
				[
					37.97438036636651,
					6.075900858618694
				],
				[
					40.10094566688292,
					6.075900858618694
				],
				[
					42.531306010330525,
					6.075900858618694
				],
				[
					45.56925643963971,
					6.075900858618694
				],
				[
					48.607206868949056,
					6.075900858618694
				],
				[
					51.34136225532737,
					6.075900858618694
				],
				[
					54.68310772756759,
					6.075900858618694
				],
				[
					56.50587798515329,
					6.075900858618694
				],
				[
					58.93623832860074,
					6.075900858618694
				],
				[
					61.67039371497921,
					6.075900858618694
				],
				[
					64.40454910135736,
					6.075900858618694
				],
				[
					67.74629457359775,
					6.075900858618694
				],
				[
					71.69563013169986,
					6.075900858618694
				],
				[
					74.7335805610092,
					6.075900858618694
				],
				[
					77.1639409044565,
					6.075900858618694
				],
				[
					80.50568637669687,
					6.075900858618694
				],
				[
					83.84743184893709,
					6.075900858618694
				],
				[
					87.1891773211773,
					6.075900858618694
				],
				[
					92.04989800807219,
					6.075900858618694
				],
				[
					96.30302860910518,
					6.075900858618694
				],
				[
					102.075134424793,
					6.075900858618694
				],
				[
					116.65729648547767,
					6.075900858618694
				],
				[
					126.68253290219832,
					5.164515729825758
				],
				[
					135.4925891471955,
					5.164515729825758
				],
				[
					141.56849000581403,
					4.5569256439640204
				],
				[
					144.91023547805423,
					4.253130601033152
				],
				[
					146.12541564977786,
					4.253130601033152
				],
				[
					146.73300573563995,
					4.253130601033152
				],
				[
					147.0368007785708,
					4.253130601033152
				],
				[
					148.25198095029444,
					4.253130601033152
				],
				[
					149.4671611220181,
					4.253130601033152
				],
				[
					150.6823412937419,
					4.253130601033152
				],
				[
					152.20131650839656,
					4.253130601033152
				],
				[
					153.72029172305125,
					4.253130601033152
				],
				[
					154.63167685184402,
					4.253130601033152
				],
				[
					156.15065206649868,
					4.253130601033152
				],
				[
					157.9734223240844,
					4.253130601033152
				],
				[
					161.6189628392555,
					3.949335558101953
				],
				[
					163.44173309684103,
					3.6455405151710845
				],
				[
					165.56829839735744,
					3.341745472240216
				],
				[
					167.39106865494313,
					2.734155386378478
				],
				[
					168.3024537837359,
					2.43036034344728
				],
				[
					169.21383891252884,
					2.126565300516411
				],
				[
					169.5176339554597,
					1.8227702575855422
				],
				[
					169.8214289983906,
					1.8227702575855422
				],
				[
					170.12522404132145,
					1.8227702575855422
				],
				[
					170.42901908425247,
					1.5189752146546736
				],
				[
					170.73281412718336,
					1.2151801717238047
				],
				[
					171.0366091701144,
					1.2151801717238047
				],
				[
					171.0366091701144,
					0.9113851287926064
				],
				[
					171.0366091701144,
					0.9113851287926064
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 732,
			"versionNonce": 1880236022,
			"isDeleted": false,
			"id": "pgWxSaM2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2478.47479172384,
			"y": 3657.1888294699065,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 84.28842163085938,
			"height": 14.493503102314778,
			"seed": 1565929654,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 11.594802481851822,
			"fontFamily": 1,
			"text": "negative phase",
			"rawText": "negative phase",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "negative phase",
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"id": "4r3-p96pbUa2BNRr-8kCU",
			"type": "line",
			"x": -2642.61492018334,
			"y": 3682.9818012629175,
			"width": 0.4351508697911868,
			"height": 30.935941160721086,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
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
			"seed": 680143914,
			"version": 282,
			"versionNonce": 2079764790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.4351508697911868,
					30.935941160721086
				]
			],
			"lastCommittedPoint": [
				0,
				64.00740726485765
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "DfO7PAS6",
			"type": "text",
			"x": -2763.412034760182,
			"y": 3709.5583863995635,
			"width": 239.0245361328125,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1854485098,
			"version": 555,
			"versionNonce": 1471617654,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "6c_3GgZ0dBKQa5v7fF6Fv",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "given our data point xi this is\nan expectation over the\nconditional distribution\np(h | xi)",
			"rawText": "given our data point xi this is\nan expectation over the\nconditional distribution\np(h | xi)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "given our data point xi this is\nan expectation over the\nconditional distribution\np(h | xi)",
			"lineHeight": 1.25
		},
		{
			"id": "9Gm9Pn2x",
			"type": "text",
			"x": -2512.396585519339,
			"y": 3560.712895021282,
			"width": 174.1923828125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 7331050,
			"version": 306,
			"versionNonce": 2034201846,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "this is derived from Z",
			"rawText": "this is derived from Z",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "this is derived from Z",
			"lineHeight": 1.25
		},
		{
			"id": "WbflxJBJ",
			"type": "text",
			"x": -2738.534976615765,
			"y": 3546.40604755981,
			"width": 199.50440979003906,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1788715946,
			"version": 304,
			"versionNonce": 2125555254,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "this is derived from sum\nover energies (numerator)",
			"rawText": "this is derived from sum\nover energies (numerator)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "this is derived from sum\nover energies (numerator)",
			"lineHeight": 1.25
		},
		{
			"id": "6c_3GgZ0dBKQa5v7fF6Fv",
			"type": "arrow",
			"x": -2770.524252978527,
			"y": 3737.461071953877,
			"width": 103.36573470290114,
			"height": 1.6084854246673785,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
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
			"seed": 399483178,
			"version": 478,
			"versionNonce": 2037326186,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619305,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-103.36573470290114,
					1.6084854246673785
				]
			],
			"lastCommittedPoint": [
				-103.36573470290114,
				0.5168286735142829
			],
			"startBinding": {
				"elementId": "DfO7PAS6",
				"focus": 0.3360682768852043,
				"gap": 7.1122182183448786
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "fBNBLyxX",
			"type": "text",
			"x": -3158.8121351899663,
			"y": 3717.2849985671296,
			"width": 263.79254150390625,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2110607658,
			"version": 316,
			"versionNonce": 728354998,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Summation over hidden vectors\ngiven a visible vector xi multiplied\nby their energy function",
			"rawText": "Summation over hidden vectors\ngiven a visible vector xi multiplied\nby their energy function",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "Summation over hidden vectors\ngiven a visible vector xi multiplied\nby their energy function",
			"lineHeight": 1.25
		},
		{
			"id": "Xb6H4eca",
			"type": "text",
			"x": -3129.8586767354745,
			"y": 3791.5631586420304,
			"width": 604.2733154296875,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 691719990,
			"version": 919,
			"versionNonce": 2056931830,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "The positive phase tells us that for all parameters that affected\nthe expectation xi, should be increased in order to increase the probability\nof having a combination of variables that includes xi and all possible values\nof h",
			"rawText": "The positive phase tells us that for all parameters that affected\nthe expectation xi, should be increased in order to increase the probability\nof having a combination of variables that includes xi and all possible values\nof h",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "The positive phase tells us that for all parameters that affected\nthe expectation xi, should be increased in order to increase the probability\nof having a combination of variables that includes xi and all possible values\nof h",
			"lineHeight": 1.25
		},
		{
			"id": "u8TDvCpP",
			"type": "text",
			"x": -2956.41948471428,
			"y": 3876.365318025066,
			"width": 256.9925231933594,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1894015926,
			"version": 282,
			"versionNonce": 401185590,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Recall the visual example above:\n",
			"rawText": "Recall the visual example above:\n",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Recall the visual example above:\n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 888,
			"versionNonce": 163366006,
			"isDeleted": false,
			"id": "Ei2p16Ws",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2904.1438377709146,
			"y": 3903.346321578607,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 156.04165649414062,
			"height": 82.85422601836568,
			"seed": 1421811510,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 9.469054402098935,
			"fontFamily": 1,
			"text": "First datapoint samples AB\nso we increase probability\nof all scenarios that include\nAB in them over all values of\nh\nand decrease everything (including\nthose we increased)",
			"rawText": "First datapoint samples AB\nso we increase probability\nof all scenarios that include\nAB in them over all values of\nh\nand decrease everything (including\nthose we increased)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "First datapoint samples AB\nso we increase probability\nof all scenarios that include\nAB in them over all values of\nh\nand decrease everything (including\nthose we increased)",
			"lineHeight": 1.25,
			"baseline": 78
		},
		{
			"id": "ioGTK8b5dsGUCm7Whffn_",
			"type": "arrow",
			"x": -2750.6208720589207,
			"y": 3934.159111602701,
			"width": 114.12036107736776,
			"height": 66.79486154641518,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
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
			"seed": 946322666,
			"version": 377,
			"versionNonce": 1104725430,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					114.12036107736776,
					-5.587599358713305
				],
				[
					113.52028987944891,
					-66.79486154641518
				]
			],
			"lastCommittedPoint": [
				111.01317161494876,
				-62.40740458353912
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "lKsXvuahxXu9rMuFuYJly",
			"type": "line",
			"x": -2406.9020938702233,
			"y": 3696.767042235621,
			"width": 6.643097423608424,
			"height": 55.3591451967377,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
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
			"seed": 436078698,
			"version": 224,
			"versionNonce": 828546806,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					6.643097423608424,
					55.3591451967377
				]
			],
			"lastCommittedPoint": [
				6.643097423608424,
				55.3591451967377
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "gsw2c8NG",
			"type": "text",
			"x": -2505.7461645364247,
			"y": 3752.9357410270386,
			"width": 240.11253356933594,
			"height": 120,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 448669098,
			"version": 406,
			"versionNonce": 1558138934,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "bbFTtyxfZ9lNT9HF4FGKz",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Go over all possible values\nof x and h (intractable)\nin the probability distribution\nbuilt by our model\nand which parameters actually\naffected them and reduce it",
			"rawText": "Go over all possible values\nof x and h (intractable)\nin the probability distribution\nbuilt by our model\nand which parameters actually\naffected them and reduce it",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "Go over all possible values\nof x and h (intractable)\nin the probability distribution\nbuilt by our model\nand which parameters actually\naffected them and reduce it",
			"lineHeight": 1.25
		},
		{
			"id": "bbFTtyxfZ9lNT9HF4FGKz",
			"type": "arrow",
			"x": -2752.9222575631893,
			"y": 3978.514538985437,
			"width": 351.9484724817214,
			"height": 96.97354626978222,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1360343402,
			"version": 713,
			"versionNonce": 580609066,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619306,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					320.29065376634844,
					-9.98934951488718
				],
				[
					351.9484724817214,
					-96.97354626978222
				]
			],
			"lastCommittedPoint": [
				335.1792140428013,
				-115.94249542361013
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "gsw2c8NG",
				"focus": -0.06825507043998834,
				"gap": 8.605251688616136
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "text",
			"version": 605,
			"versionNonce": 987263990,
			"isDeleted": false,
			"id": "zpG0xTnN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2937.1373928489056,
			"y": 4013.732681285369,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 497.13934326171875,
			"height": 25,
			"seed": 976662186,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "What this really is doing is the push pull approach",
			"rawText": "What this really is doing is the push pull approach",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What this really is doing is the push pull approach",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 620,
			"versionNonce": 1121092918,
			"isDeleted": false,
			"id": "b0Km5PyExNUYSL7de_37E",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3007.073390021501,
			"y": 4055.845138503865,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 620.2192735135363,
			"height": 218.24015833852766,
			"seed": 360663402,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1a0b42c9e99c729659c286778394c8840c120f8e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 1083,
			"versionNonce": 2079878774,
			"isDeleted": false,
			"id": "VaAfIWih",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3089.5412667974933,
			"y": 4289.375376970871,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 799.2191772460938,
			"height": 150,
			"seed": 442928170,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Since we want to associate low energy with high probability and we want\nto increase the probability of observing xi given our parameters\nand decrease the chance of finding random unrelated points samples from\nour model x,y given our parameters.\nWe traverse the loss function by reducing probabilities of all points in our space\nand only increasing the ones we just observed",
			"rawText": "Since we want to associate low energy with high probability and we want\nto increase the probability of observing xi given our parameters\nand decrease the chance of finding random unrelated points samples from\nour model x,y given our parameters.\nWe traverse the loss function by reducing probabilities of all points in our space\nand only increasing the ones we just observed",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Since we want to associate low energy with high probability and we want\nto increase the probability of observing xi given our parameters\nand decrease the chance of finding random unrelated points samples from\nour model x,y given our parameters.\nWe traverse the loss function by reducing probabilities of all points in our space\nand only increasing the ones we just observed",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 707,
			"versionNonce": 54908842,
			"isDeleted": false,
			"id": "KS2iAdGHVXYMUIzjaa36C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2385.717988038992,
			"y": 3302.0352100102177,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 645.2232780331811,
			"height": 57.01326379172506,
			"seed": 1190911094,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6fa4af893c110fe256a85c5e2c3b5f9e4b29fcf1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 888,
			"versionNonce": 616649322,
			"isDeleted": false,
			"id": "xHTt2pUZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2911.910726460726,
			"y": 3427.515410350355,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 160.1283416748047,
			"height": 80,
			"seed": 930405814,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "(soft on/off value\nindicating how well\npresent the feature\nin W is in x)",
			"rawText": "(soft on/off value\nindicating how well\npresent the feature\nin W is in x)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(soft on/off value\nindicating how well\npresent the feature\nin W is in x)",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "line",
			"version": 636,
			"versionNonce": 1719629098,
			"isDeleted": false,
			"id": "wflZ5vu-Ce1Rp6BqZuny_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2516.0138051430677,
			"y": 3388.5433168754057,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 0.596162520214989,
			"height": 39.34672633418609,
			"seed": 1270593270,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.596162520214989,
					39.34672633418609
				]
			]
		},
		{
			"type": "text",
			"version": 682,
			"versionNonce": 2045460458,
			"isDeleted": false,
			"id": "JyZSWrwT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2430.369786694044,
			"y": 3427.890043209592,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 172.48036193847656,
			"height": 40,
			"seed": 2085972022,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Expectation\nover the observations",
			"rawText": "Expectation\nover the observations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Expectation\nover the observations",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 716,
			"versionNonce": 722449066,
			"isDeleted": false,
			"id": "vC4hWI_WNIK8ep2UnHfiZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2792.0666730654025,
			"y": 3378.8502052454037,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 1.7884875606448531,
			"height": 36.96207625332636,
			"seed": 1764159862,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.7884875606448531,
					36.96207625332636
				]
			]
		},
		{
			"type": "text",
			"version": 747,
			"versionNonce": 211275114,
			"isDeleted": false,
			"id": "UlTIu2pw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2686.1456030170466,
			"y": 3420.633085429304,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 206.83248901367188,
			"height": 60,
			"seed": 1836405430,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "expectation over\nthe probability distribution\nbuilt by the model",
			"rawText": "expectation over\nthe probability distribution\nbuilt by the model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "expectation over\nthe probability distribution\nbuilt by the model",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 713,
			"versionNonce": 600739882,
			"isDeleted": false,
			"id": "0XL5bDoO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2940.4849418347144,
			"y": 3398.977010954864,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 75.95991516113281,
			"height": 25,
			"seed": 870681590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p(hj | x)",
			"rawText": "p(hj | x)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p(hj | x)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 740,
			"versionNonce": 345963242,
			"isDeleted": false,
			"id": "VoMkYguQfWyTyCXRIsqRt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2957.3574700782897,
			"y": 3369.430306815854,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 4.968686014116884,
			"height": 26.067676077461783,
			"seed": 1249680694,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.968686014116884,
					26.067676077461783
				]
			]
		},
		{
			"type": "image",
			"version": 572,
			"versionNonce": 1301548458,
			"isDeleted": false,
			"id": "3sUFIBcQaWUhyMf2DbQNW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2555.9935826568853,
			"y": 3136.8292007796567,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 278.52071537846575,
			"height": 76.41465780896368,
			"seed": 916424310,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d7e7a54e673a3f3a9b8fbb07703258013bbcb761",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 694,
			"versionNonce": 869845098,
			"isDeleted": false,
			"id": "h__xo5GTYjuxFHtgiREF-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2401.7030143514276,
			"y": 3229.6454054088676,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 615.0088752719657,
			"height": 59.21310834128335,
			"seed": 152258486,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216395355,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fe2b3efcf3c0208afe36ddc82f95c97868a12728",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "alLafyHG9zc0irS8NdEoU",
			"type": "arrow",
			"x": -3055.1739215018697,
			"y": 4140.81349967274,
			"width": 223.91250199271508,
			"height": 2.227985094455107,
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
			"seed": 1880320694,
			"version": 292,
			"versionNonce": 51326902,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-223.91250199271508,
					-2.227985094455107
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "hQqsSDDb",
			"type": "text",
			"x": -3759.8156903031445,
			"y": 4091.473476804087,
			"width": 508.199462890625,
			"height": 275,
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
			"seed": 1025821610,
			"version": 899,
			"versionNonce": 339462390,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Another and final way to look at this is\ngiven enough datapoints xi, the left term\nis calculating the expected value of xi, h\nover the DATASET distribution, and the right\nterm is calculating the expected value over the\ndistribution inferred and built by the model itself\nand this leads us to a a good solution at the\nminima when the gradient is 0\n(as in the left and right term are equal)\nBECAUSE the distribution built by the model will be\ncloser and closer to the dataset distribution",
			"rawText": "Another and final way to look at this is\ngiven enough datapoints xi, the left term\nis calculating the expected value of xi, h\nover the DATASET distribution, and the right\nterm is calculating the expected value over the\ndistribution inferred and built by the model itself\nand this leads us to a a good solution at the\nminima when the gradient is 0\n(as in the left and right term are equal)\nBECAUSE the distribution built by the model will be\ncloser and closer to the dataset distribution",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 268,
			"containerId": null,
			"originalText": "Another and final way to look at this is\ngiven enough datapoints xi, the left term\nis calculating the expected value of xi, h\nover the DATASET distribution, and the right\nterm is calculating the expected value over the\ndistribution inferred and built by the model itself\nand this leads us to a a good solution at the\nminima when the gradient is 0\n(as in the left and right term are equal)\nBECAUSE the distribution built by the model will be\ncloser and closer to the dataset distribution",
			"lineHeight": 1.25
		},
		{
			"id": "4ypsFfCgBtkmcDiens5ta",
			"type": "line",
			"x": -3426.767019954381,
			"y": 4245.549579782067,
			"width": 518.1789960480332,
			"height": 396.11173968303274,
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
			"seed": 1794341290,
			"version": 916,
			"versionNonce": 520305206,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					1.4210854715202004e-14,
					-202.99497835851662
				],
				[
					-19.326023162630463,
					-534.4191153916994
				],
				[
					-428.7961389208667,
					-530.4260534997334
				],
				[
					-439.66702694984633,
					-599.1067180415494
				],
				[
					-518.1789960480332,
					-512.8565811750826
				],
				[
					-424.1549357310637,
					-427.6947451815923
				],
				[
					-422.46279191999616,
					-501.54381288764705
				],
				[
					-84.53085557911064,
					-493.6898840936455
				],
				[
					-176.19800581608342,
					-219.6239448567435
				],
				[
					1.4210854715202004e-14,
					-202.99497835851662
				]
			],
			"lastCommittedPoint": [
				4.831505790657957,
				-2.415752895329206
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "9sUUi4Vf",
			"type": "text",
			"x": -3823.9879148979485,
			"y": 3625.2148782930194,
			"width": 361.73956298828125,
			"height": 75,
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
			"seed": 798707882,
			"version": 358,
			"versionNonce": 1514832758,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Okay cool, I get it (Kinda...) But\nyou just said the right side is\nintractable, how do we even do this?",
			"rawText": "Okay cool, I get it (Kinda...) But\nyou just said the right side is\nintractable, how do we even do this?",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "Okay cool, I get it (Kinda...) But\nyou just said the right side is\nintractable, how do we even do this?",
			"lineHeight": 1.25
		},
		{
			"id": "K0S5FDT7",
			"type": "text",
			"x": -5638.104251591058,
			"y": 3615.6678991126396,
			"width": 193.7047882080078,
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
			"seed": 966307690,
			"version": 419,
			"versionNonce": 1482073270,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Gibbs Sampling",
			"rawText": "Gibbs Sampling",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Gibbs Sampling",
			"lineHeight": 1.25
		},
		{
			"id": "KpYlSGDE",
			"type": "text",
			"x": -2226.312686971254,
			"y": 2921.7660604649814,
			"width": 105.67242431640625,
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
			"seed": 1220861226,
			"version": 238,
			"versionNonce": 449617398,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Training",
			"rawText": "Training",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Training",
			"lineHeight": 1.25
		},
		{
			"id": "SgSwTgfO",
			"type": "text",
			"x": -4591.683904787756,
			"y": 3648.1748404976915,
			"width": 472.47393798828125,
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
			"seed": 1746858666,
			"version": 313,
			"versionNonce": 3423274,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217403656,
			"link": null,
			"locked": false,
			"text": "Persistent Contrastive Divergence",
			"rawText": "Persistent Contrastive Divergence",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Persistent Contrastive Divergence",
			"lineHeight": 1.25
		},
		{
			"id": "FmCVwL49",
			"type": "text",
			"x": -4740.500100080756,
			"y": 3683.174839548534,
			"width": 774.4193115234375,
			"height": 100,
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
			"seed": 1024688170,
			"version": 558,
			"versionNonce": 935041462,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Instead of decreasing all points (over all values of h and x)\nlets just obtain one random point and decrease it and be satisfied with that\nover an infinite amount of points this will converge to the normal CD\nit just will be an approximation and is a lot slower.",
			"rawText": "Instead of decreasing all points (over all values of h and x)\nlets just obtain one random point and decrease it and be satisfied with that\nover an infinite amount of points this will converge to the normal CD\nit just will be an approximation and is a lot slower.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "Instead of decreasing all points (over all values of h and x)\nlets just obtain one random point and decrease it and be satisfied with that\nover an infinite amount of points this will converge to the normal CD\nit just will be an approximation and is a lot slower.",
			"lineHeight": 1.25
		},
		{
			"id": "uUuMKpl6",
			"type": "text",
			"x": -4398.459100270574,
			"y": 3795.0880070560997,
			"width": 71.53993225097656,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1054079350,
			"version": 226,
			"versionNonce": 197849846,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Analogy",
			"rawText": "Analogy",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Analogy",
			"lineHeight": 1.25
		},
		{
			"id": "o3YvVLVEql-Iz2S_qs6hN",
			"type": "rectangle",
			"x": -4412.536814136555,
			"y": 4185.351632027479,
			"width": 150.47024651644602,
			"height": 148.62775370195862,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 805166518,
			"version": 402,
			"versionNonce": 1864180790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"id": "2_Rrq-8EKbprZwdWLKgEa",
			"type": "ellipse",
			"x": -4413.150978408052,
			"y": 4171.840018054573,
			"width": 150.4702465164457,
			"height": 27.637392217306296,
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
			"seed": 719586986,
			"version": 409,
			"versionNonce": 597110134,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"id": "KLPxNRVy",
			"type": "text",
			"x": -4692.66879164027,
			"y": 3818.3627625726904,
			"width": 662.3052978515625,
			"height": 280,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1893391606,
			"version": 1235,
			"versionNonce": 1719537334,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Say you have a jar of Blue and red balls, and you have an external\nsupply of blue balls... you want to get rid of all the red balls and only\nfill the jar with blue balls.\none way to do this is to take all red balls out and put all blue balls in\n(which is what the normal CD algorithm tries)\n\nThe enhanced method goes as follows:\nTake exactly one ball out of the jar and throw it away\nand instead insert a blue ball from your supply...\nif the ball you took out was red, we are closer to our solution of all blue balls\nif the ball you took out was blue, we are exactly where we were on the last step\n\nwith every iteration we will always move forwards towards a solution or stand still\nand over an infinite amount of steps we will converge",
			"rawText": "Say you have a jar of Blue and red balls, and you have an external\nsupply of blue balls... you want to get rid of all the red balls and only\nfill the jar with blue balls.\none way to do this is to take all red balls out and put all blue balls in\n(which is what the normal CD algorithm tries)\n\nThe enhanced method goes as follows:\nTake exactly one ball out of the jar and throw it away\nand instead insert a blue ball from your supply...\nif the ball you took out was red, we are closer to our solution of all blue balls\nif the ball you took out was blue, we are exactly where we were on the last step\n\nwith every iteration we will always move forwards towards a solution or stand still\nand over an infinite amount of steps we will converge",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 274,
			"containerId": null,
			"originalText": "Say you have a jar of Blue and red balls, and you have an external\nsupply of blue balls... you want to get rid of all the red balls and only\nfill the jar with blue balls.\none way to do this is to take all red balls out and put all blue balls in\n(which is what the normal CD algorithm tries)\n\nThe enhanced method goes as follows:\nTake exactly one ball out of the jar and throw it away\nand instead insert a blue ball from your supply...\nif the ball you took out was red, we are closer to our solution of all blue balls\nif the ball you took out was blue, we are exactly where we were on the last step\n\nwith every iteration we will always move forwards towards a solution or stand still\nand over an infinite amount of steps we will converge",
			"lineHeight": 1.25
		},
		{
			"id": "LAPb4tb7W6bzfQY_tKGwd",
			"type": "ellipse",
			"x": -4406.286453228886,
			"y": 4295.505445758995,
			"width": 24.972338416645005,
			"height": 23.97344487997982,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
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
			"seed": 1415158326,
			"version": 431,
			"versionNonce": 74893302,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 403,
			"versionNonce": 1837521206,
			"isDeleted": false,
			"id": "ODWDzEJhmzm5Aofr2fVUK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4318.383822002295,
			"y": 4299.501019905657,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 24.972338416645005,
			"height": 23.97344487997982,
			"seed": 494693994,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 424,
			"versionNonce": 1225900662,
			"isDeleted": false,
			"id": "X7DxuBZQzyVxRubUy3W5-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4292.4125900489835,
			"y": 4293.507658685663,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 24.972338416645005,
			"height": 23.97344487997982,
			"seed": 28663658,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 419,
			"versionNonce": 165544886,
			"isDeleted": false,
			"id": "pH3LMWzTqwj7Cw82FsLjG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4410.7814741438815,
			"y": 4269.534213805685,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 24.972338416645005,
			"height": 23.97344487997982,
			"seed": 1033582442,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 403,
			"versionNonce": 34610422,
			"isDeleted": false,
			"id": "7PG0ZVr7xUmMQe_96ZFWU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4300.403738342311,
			"y": 4266.038086427354,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 24.972338416645005,
			"height": 23.97344487997982,
			"seed": 733247210,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 403,
			"versionNonce": 1999441462,
			"isDeleted": false,
			"id": "5_JaBwbSCDnzyVRVO1D87",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4344.854500723939,
			"y": 4303.996040820653,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 24.972338416645005,
			"height": 23.97344487997982,
			"seed": 167824246,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 403,
			"versionNonce": 907663222,
			"isDeleted": false,
			"id": "VWAoUaSll2iuCH7yWmKpS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4358.339563468928,
			"y": 4257.048044597361,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 24.972338416645005,
			"height": 23.97344487997982,
			"seed": 1913207850,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 394,
			"versionNonce": 656111798,
			"isDeleted": false,
			"id": "nCBkyU4ocR-bqmi0tWKAx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4379.566051123075,
			"y": 4300.74963682649,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 30.46625286830704,
			"height": 28.46846579497539,
			"seed": 1162403894,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 394,
			"versionNonce": 1641476598,
			"isDeleted": false,
			"id": "22gzqhEsaBLsJt4EfCT3_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4389.055539721401,
			"y": 4262.7916824331905,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 30.46625286830704,
			"height": 28.46846579497539,
			"seed": 1385085802,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 394,
			"versionNonce": 1095844662,
			"isDeleted": false,
			"id": "Xcnxkn9U5VaLh9CWYg7uL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4329.621374289785,
			"y": 4267.786150116519,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 30.46625286830704,
			"height": 28.46846579497539,
			"seed": 300908278,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 394,
			"versionNonce": 2012179574,
			"isDeleted": false,
			"id": "M874euFKEstuRp4wo8X3e",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4354.094265938098,
			"y": 4279.273425788177,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 30.46625286830704,
			"height": 28.46846579497539,
			"seed": 1175326890,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 394,
			"versionNonce": 594963894,
			"isDeleted": false,
			"id": "iweeLblca9QkxJhG18VPh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4321.130779228126,
			"y": 4239.317684321543,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 30.46625286830704,
			"height": 28.46846579497539,
			"seed": 1310520758,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 441,
			"versionNonce": 1628129014,
			"isDeleted": false,
			"id": "gEXvpg2uAHiHaVSUlDM9z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4411.530644296381,
			"y": 4237.319897248212,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 30.46625286830704,
			"height": 28.46846579497539,
			"seed": 1326779882,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 288,
			"versionNonce": 1630730294,
			"isDeleted": false,
			"id": "44zCIejN7vmqSc6HsaIl0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4179.795227134195,
			"y": 4155.256729341666,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 35.217231701607496,
			"height": 33.80854243354406,
			"seed": 206291702,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 325,
			"versionNonce": 2077393270,
			"isDeleted": false,
			"id": "9IqoFFWqstr6pPREC_4Ip",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4133.308481288072,
			"y": 4155.961073975699,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 35.217231701607496,
			"height": 33.80854243354406,
			"seed": 1462209706,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 312,
			"versionNonce": 1143923382,
			"isDeleted": false,
			"id": "YPB1eNhkJU7GsQgtWdYHi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4089.639113978078,
			"y": 4154.552384707634,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 35.217231701607496,
			"height": 33.80854243354406,
			"seed": 1723081014,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 321,
			"versionNonce": 485301238,
			"isDeleted": false,
			"id": "I8ibdzuu7AFPjG14jxtX1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4046.6740913021167,
			"y": 4153.1436954395695,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 35.217231701607496,
			"height": 33.80854243354406,
			"seed": 420363626,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 323,
			"versionNonce": 1276259638,
			"isDeleted": false,
			"id": "MMa_NvbW2BksmD5cPtAlF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4005.8221025282514,
			"y": 4152.439350805537,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 35.217231701607496,
			"height": 33.80854243354406,
			"seed": 1598031606,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"id": "lb5YoZlV8SQs_j8BcqkgY",
			"type": "line",
			"x": -3944.544119367455,
			"y": 4190.473961043275,
			"width": 257.79013605576756,
			"height": 0.704344634032168,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
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
			"seed": 1433339370,
			"version": 257,
			"versionNonce": 251860598,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-257.79013605576756,
					0.704344634032168
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "4MKn0Jeo",
			"type": "text",
			"x": -4105.043369207338,
			"y": 4124.969910078285,
			"width": 46.30409240722656,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1077606902,
			"version": 202,
			"versionNonce": 780457910,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Supply",
			"rawText": "Supply",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Supply",
			"lineHeight": 1.25
		},
		{
			"id": "KjEaRE94",
			"type": "text",
			"x": -4349.701236977169,
			"y": 4337.477785050138,
			"width": 27.696075439453125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 884132854,
			"version": 260,
			"versionNonce": 314339574,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Jar",
			"rawText": "Jar",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Jar",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 404,
			"versionNonce": 1462690358,
			"isDeleted": false,
			"id": "RuvKMS-ERJKkuvAE48LLd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4380.176061778589,
			"y": 4129.785903419361,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 30.46625286830704,
			"height": 28.46846579497539,
			"seed": 462727658,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "fwHC_cKRXE8Ma4_NmIdQZ",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"id": "fwHC_cKRXE8Ma4_NmIdQZ",
			"type": "arrow",
			"x": -4389.357168005981,
			"y": 4139.873644245795,
			"width": 145.02579756467776,
			"height": 51.29939180866859,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
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
			"seed": 2083014838,
			"version": 668,
			"versionNonce": 1253134058,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619310,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-92.45635667006218,
					6.280054415326049
				],
				[
					-145.02579756467776,
					51.29939180866859
				]
			],
			"lastCommittedPoint": [
				-147.93017067209894,
				49.193759586712076
			],
			"startBinding": {
				"elementId": "RuvKMS-ERJKkuvAE48LLd",
				"focus": 0.40673364837033327,
				"gap": 9.560058814573262
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "ellipse",
			"version": 771,
			"versionNonce": 532235766,
			"isDeleted": false,
			"id": "SRFdXoHzwYqsnkezL-JKN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.424524010042901,
			"x": -4649.565456700054,
			"y": 4182.819480799755,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#979fa7",
			"width": 85.67698887503977,
			"height": 32.54200717094308,
			"seed": 1328984938,
			"groupIds": [
				"Ao3IsS7uKmQjJD2U8ZWM6"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"id": "_odf-YsvUiYtJm4zutKAB",
			"type": "rectangle",
			"x": -4596.482961215956,
			"y": 4224.915421564231,
			"width": 83.70683765588167,
			"height": 112.24325958402359,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"Ao3IsS7uKmQjJD2U8ZWM6"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1024620918,
			"version": 505,
			"versionNonce": 935925558,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"id": "S9bDkHBr4K4pYMdTt8tqB",
			"type": "ellipse",
			"x": -4597.053689654518,
			"y": 4213.1203671672665,
			"width": 84.84829453300733,
			"height": 28.916907553849818,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"Ao3IsS7uKmQjJD2U8ZWM6"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1780269366,
			"version": 399,
			"versionNonce": 2018295926,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"id": "V1KczUpuQH6cq3B5PwWaw",
			"type": "line",
			"x": -4519.071155875941,
			"y": 4234.618555356383,
			"width": 71.9747178757794,
			"height": 15.36523100385896,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"Ao3IsS7uKmQjJD2U8ZWM6"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 729702838,
			"version": 782,
			"versionNonce": 1426670006,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-13.186534992467715,
					-6.142596744578246
				],
				[
					-30.856728181787712,
					-8.66691005733831
				],
				[
					-49.368359142027586,
					-8.054955314851089
				],
				[
					-67.1915410169695,
					-3.082823032142142
				],
				[
					-71.9747178757794,
					-0.2829280515386789
				],
				[
					-60.01855107757212,
					4.2800100055631285
				],
				[
					-43.122545543085806,
					6.698320946520652
				],
				[
					-24.99984500618627,
					6.491887237793595
				],
				[
					-9.202370457014352,
					3.9242608030611303
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				-1.4148328098385718,
				1.414832809838117
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "xd9XX2TQfuspuIqwOdmVK",
			"type": "rectangle",
			"x": -4588.343987121974,
			"y": 4247.453526107349,
			"width": 12.688727784700207,
			"height": 83.51489923748107,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#979fa7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"Ao3IsS7uKmQjJD2U8ZWM6"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1451580022,
			"version": 409,
			"versionNonce": 19110646,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 491,
			"versionNonce": 52481078,
			"isDeleted": false,
			"id": "eVnbwHj14MeKSbC3bLK09",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4561.565607000789,
			"y": 4247.453525765146,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#979fa7",
			"width": 12.688727784700207,
			"height": 83.51489923748107,
			"seed": 1654128054,
			"groupIds": [
				"Ao3IsS7uKmQjJD2U8ZWM6"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 442,
			"versionNonce": 1223021942,
			"isDeleted": false,
			"id": "2s2qD70K_BYvQ06aWUiWc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -4535.223869962441,
			"y": 4247.453526241637,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#979fa7",
			"width": 12.688727784700207,
			"height": 83.51489923748107,
			"seed": 1112394550,
			"groupIds": [
				"Ao3IsS7uKmQjJD2U8ZWM6"
			],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"id": "7SY5Xvef0qHbkRdCGRyEc",
			"type": "ellipse",
			"x": -4649.6625574715845,
			"y": 4182.365161736595,
			"width": 82.32881370475206,
			"height": 30.45690217979277,
			"angle": 5.424524010042901,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#979fa7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"Ao3IsS7uKmQjJD2U8ZWM6"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 502369974,
			"version": 543,
			"versionNonce": 1001895606,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"id": "khJg34LFORCsYLbmvBjnq",
			"type": "line",
			"x": -4601.045735309424,
			"y": 4188.219133887892,
			"width": 28.31891574607087,
			"height": 29.837595770308248,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [
				"Ao3IsS7uKmQjJD2U8ZWM6"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1749832170,
			"version": 577,
			"versionNonce": 1413181430,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-6.074720096949067,
					-3.126694167547086
				],
				[
					-16.616146147536828,
					11.345433122243168
				],
				[
					-11.702769598533822,
					16.080141433100184
				],
				[
					-16.348143790318506,
					20.72551562488487
				],
				[
					-24.12021214965028,
					14.918797885154124
				],
				[
					-7.057395406749579,
					-9.112080145423379
				],
				[
					4.198703596420594,
					-4.466705953638694
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				0.9179534507438802,
				-0.3671813802975521
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "2OcVMqdkjb5vzzhElC2Bb",
			"type": "arrow",
			"x": -4765.863793367633,
			"y": 3705.245957715194,
			"width": 316.43467137427706,
			"height": 2.521391803778897,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
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
			"seed": 1460883498,
			"version": 278,
			"versionNonce": 779485494,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-316.43467137427706,
					-2.521391803778897
				]
			],
			"lastCommittedPoint": [
				-287.438665630817,
				5.042783607558249
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Xu4HpERR",
			"type": "text",
			"x": -5015.129814522124,
			"y": 3642.211162620717,
			"width": 231.26451110839844,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 938319158,
			"version": 298,
			"versionNonce": 499935862,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "How do we obtain a random\nsample without iterating over\na lot of values?",
			"rawText": "How do we obtain a random\nsample without iterating over\na lot of values?",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "How do we obtain a random\nsample without iterating over\na lot of values?",
			"lineHeight": 1.25
		},
		{
			"id": "vPjLzrHa",
			"type": "text",
			"x": -5914.684968389506,
			"y": 3658.2744935623723,
			"width": 782.379150390625,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 301974058,
			"version": 437,
			"versionNonce": 1090759606,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Sampling from a joint probability distribution is hard!\nwe instead try to sample from conditional distribution some T amount of times\nand we will produce something random form the joint ",
			"rawText": "Sampling from a joint probability distribution is hard!\nwe instead try to sample from conditional distribution some T amount of times\nand we will produce something random form the joint ",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "Sampling from a joint probability distribution is hard!\nwe instead try to sample from conditional distribution some T amount of times\nand we will produce something random form the joint ",
			"lineHeight": 1.25
		},
		{
			"id": "2zqTdXa3",
			"type": "text",
			"x": -5903.183910610592,
			"y": 3762.2484994959923,
			"width": 758.1192626953125,
			"height": 400,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e9ecef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 525575670,
			"version": 925,
			"versionNonce": 373343478,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "For example:\n(stupid example)\n\nIf we want to sample from a joint probability distribution of all\npossible values of english letters and digits\n\n\n1. Start at an english letter (lets say A)\n\n2. Sample a number according to the conditional probability distribution\np( digit | A )\n\n3. We call that digit N, now we sample a letter according to the conditional\ndistribution of N p( Letter | N )\n\n4. Repeat steps 2-3, T times until you get something completely random",
			"rawText": "For example:\n(stupid example)\n\nIf we want to sample from a joint probability distribution of all\npossible values of english letters and digits\n\n\n1. Start at an english letter (lets say A)\n\n2. Sample a number according to the conditional probability distribution\np( digit | A )\n\n3. We call that digit N, now we sample a letter according to the conditional\ndistribution of N p( Letter | N )\n\n4. Repeat steps 2-3, T times until you get something completely random",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 393,
			"containerId": null,
			"originalText": "For example:\n(stupid example)\n\nIf we want to sample from a joint probability distribution of all\npossible values of english letters and digits\n\n\n1. Start at an english letter (lets say A)\n\n2. Sample a number according to the conditional probability distribution\np( digit | A )\n\n3. We call that digit N, now we sample a letter according to the conditional\ndistribution of N p( Letter | N )\n\n4. Repeat steps 2-3, T times until you get something completely random",
			"lineHeight": 1.25
		},
		{
			"id": "84IXUCOiQjQRo-zFjylXx",
			"type": "line",
			"x": -5911.557660676126,
			"y": 3890.216455043397,
			"width": 454.9355896584519,
			"height": 199.9123137454003,
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
			"seed": 1670174890,
			"version": 563,
			"versionNonce": 252229174,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.2418213039791084,
					120.02503666170699
				],
				[
					-374.9706641602924,
					97.45846620735892
				],
				[
					-370.6482357549856,
					174.6021659798995
				],
				[
					-451.6937683544728,
					80.35963827169826
				],
				[
					-374.97066416029236,
					-25.310147765500915
				],
				[
					-371.7288428563123,
					46.398162994380556
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": [
				3.2418213039791226,
				3.2418213039791226
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "ZmSqi9n7",
			"type": "text",
			"x": -6196.073792629453,
			"y": 3849.7778078593265,
			"width": 190.8197784423828,
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
			"seed": 443454710,
			"version": 243,
			"versionNonce": 608206710,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Formulated to our \nIssue",
			"rawText": "Formulated to our \nIssue",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "Formulated to our \nIssue",
			"lineHeight": 1.25
		},
		{
			"id": "FBM4WSE3",
			"type": "text",
			"x": -7035.164931049403,
			"y": 3809.6849996566134,
			"width": 678.1793212890625,
			"height": 400,
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
			"seed": 160982518,
			"version": 732,
			"versionNonce": 1781342390,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "1. Start at the current Point observed xi\n\n2. Sample an h according to the conditional distribution\np(hi|xi)\n\n3. get that value of h and sample an x according to its conditional\np(xj | hi)\n\n4. Repeat this process T times\n\n5. sample one random h value given xi and one random value\nh given xj\n\n6. Increase the probability of xi,h in your models distribution\nand decrease the probability of xj,h (after the T iterations)\nin your distribution",
			"rawText": "1. Start at the current Point observed xi\n\n2. Sample an h according to the conditional distribution\np(hi|xi)\n\n3. get that value of h and sample an x according to its conditional\np(xj | hi)\n\n4. Repeat this process T times\n\n5. sample one random h value given xi and one random value\nh given xj\n\n6. Increase the probability of xi,h in your models distribution\nand decrease the probability of xj,h (after the T iterations)\nin your distribution",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 393,
			"containerId": null,
			"originalText": "1. Start at the current Point observed xi\n\n2. Sample an h according to the conditional distribution\np(hi|xi)\n\n3. get that value of h and sample an x according to its conditional\np(xj | hi)\n\n4. Repeat this process T times\n\n5. sample one random h value given xi and one random value\nh given xj\n\n6. Increase the probability of xi,h in your models distribution\nand decrease the probability of xj,h (after the T iterations)\nin your distribution",
			"lineHeight": 1.25
		},
		{
			"id": "RD9mq0uEMN4YMDF9HMPrC",
			"type": "arrow",
			"x": -6476.416775331016,
			"y": 3989.3472068370684,
			"width": 298.6466580574606,
			"height": 350.0000224876585,
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
			"seed": 96005226,
			"version": 1250,
			"versionNonce": 909894058,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619311,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					229.53995472478618,
					139.0805541596037
				],
				[
					287.8536856108167,
					250.49333747244873
				],
				[
					298.6466580574606,
					350.0000224876585
				]
			],
			"lastCommittedPoint": [
				258.1419376447193,
				521.5520780985144
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "4urkPr8F",
				"focus": 0.019976180560826666,
				"gap": 6.071644896822363
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "image",
			"version": 362,
			"versionNonce": 1511582518,
			"isDeleted": false,
			"id": "0EVmysMg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -6302.143507683594,
			"y": 4687.1008008895315,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 319.2283718225134,
			"height": 27.83016574862937,
			"seed": 88709,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1e903a011823ca88927345ec93829c49300d480c",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "tJwzxrxvUyR8Z8gn1GKpf",
			"type": "arrow",
			"x": -5783.703154941598,
			"y": 4728.038441458303,
			"width": 168.27986928141308,
			"height": 48.204536052408,
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
			"seed": 107485110,
			"version": 1045,
			"versionNonce": 1617304682,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619311,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					149.9831072223451,
					2.4801788322156426
				],
				[
					168.27986928141308,
					48.204536052408
				]
			],
			"lastCommittedPoint": [
				821.6100916058167,
				48.05818308605376
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "tE438Fon",
				"focus": -0.05088577453694417,
				"gap": 15.612559311869518
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "SGtEQPJzWgrozjj6CF976",
			"type": "arrow",
			"x": -6688.646541664818,
			"y": 3748.3294083888322,
			"width": 1.188768656334105,
			"height": 164.86508193343707,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 2074417066,
			"version": 291,
			"versionNonce": 477369782,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.188768656334105,
					-164.86508193343707
				]
			],
			"lastCommittedPoint": [
				5.325508653644647,
				-195.97871845410418
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "eIMqYlS6",
			"type": "text",
			"x": -6682.421273063628,
			"y": 3628.645366248705,
			"width": 323.3796081542969,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 243668010,
			"version": 339,
			"versionNonce": 1007939318,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Which turns our previous example\nabout the visible layers A,B \nand latent C into",
			"rawText": "Which turns our previous example\nabout the visible layers A,B \nand latent C into",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "Which turns our previous example\nabout the visible layers A,B \nand latent C into",
			"lineHeight": 1.25
		},
		{
			"id": "j_ZrKnrdpzvgB3_MqTOV8",
			"type": "line",
			"x": -6775.598136536036,
			"y": 4061.2067340762433,
			"width": 12.17169132703657,
			"height": 0.357990921383589,
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
			"seed": 1482566826,
			"version": 204,
			"versionNonce": 619094070,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					12.17169132703657,
					-0.357990921383589
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "line",
			"version": 229,
			"versionNonce": 1523657078,
			"isDeleted": false,
			"id": "K6dx0edS5i-tPVvzDuM4S",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6674.599990285538,
			"y": 4134.955287816413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#868e96",
			"width": 12.17169132703657,
			"height": 0.357990921383589,
			"seed": 1468768490,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.17169132703657,
					-0.357990921383589
				]
			]
		},
		{
			"id": "dM7HVEDCJ1W12UAjcKZeV",
			"type": "line",
			"x": -6744.500478501639,
			"y": 4086.4229312337447,
			"width": 14.243045346445797,
			"height": 0.26376009900832287,
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
			"seed": 517117418,
			"version": 217,
			"versionNonce": 488147638,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					14.243045346445797,
					0.26376009900832287
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "line",
			"version": 221,
			"versionNonce": 2053227510,
			"isDeleted": false,
			"id": "F_6rpwiPBn1xU-09IQWor",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6657.694115059818,
			"y": 4159.898334057848,
			"strokeColor": "#e03131",
			"backgroundColor": "#868e96",
			"width": 14.243045346445797,
			"height": 0.26376009900832287,
			"seed": 2045247594,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					14.243045346445797,
					0.26376009900832287
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1033,
			"versionNonce": 1689376054,
			"isDeleted": false,
			"id": "rj6JRey-staV94gpexcPV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -7124.214104010747,
			"y": 3325.3363789967857,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 1374853034,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1002,
			"versionNonce": 1164820086,
			"isDeleted": false,
			"id": "f3URgRqnZAL_jxXKRA31I",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -7125.570542294721,
			"y": 3381.2808384882214,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 0.5547199100998836,
			"height": 128.69501914316538,
			"seed": 2144735850,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5547199100998836,
					-128.69501914316538
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1069,
			"versionNonce": 291143606,
			"isDeleted": false,
			"id": "yfvk0FXsCX0pbe5eX3hNw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -7090.109352580788,
			"y": 3325.716918080286,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 16528682,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1080,
			"versionNonce": 1553799414,
			"isDeleted": false,
			"id": "bO14HPIyMCR7fLyDrVdcC",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -7056.004601066979,
			"y": 3325.336378573716,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 651165674,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1103,
			"versionNonce": 1857718838,
			"isDeleted": false,
			"id": "wRGS4Cf-mjW7w-OhZkAip",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -7021.899849872099,
			"y": 3325.3363784714907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 1566339754,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1106,
			"versionNonce": 1452790646,
			"isDeleted": false,
			"id": "5-jNfAalfCJg6UjNcjehU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6987.7950987280565,
			"y": 3325.7169182098,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 1464634730,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1101,
			"versionNonce": 2121921718,
			"isDeleted": false,
			"id": "UBsTjnE-ARFgSGNnDukgp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6953.6903474826595,
			"y": 3325.7169187652867,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 971722794,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1102,
			"versionNonce": 1074130422,
			"isDeleted": false,
			"id": "WnQQHnb8yhnTxao3iaxBt",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6919.58559620129,
			"y": 3325.716918862577,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 1227078378,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 1098,
			"versionNonce": 2017509174,
			"isDeleted": false,
			"id": "FyqInSFKwua5p5MQ2p8s5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6885.480845127537,
			"y": 3325.7169192418355,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 327208362,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1162,
			"versionNonce": 462383222,
			"isDeleted": false,
			"id": "ZTO_Ekz4EXrYQeqQGC0kW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -7128.319950533982,
			"y": 3381.6200298747895,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 303.15542754404066,
			"height": 0.5327636926773139,
			"seed": 506300522,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					303.15542754404066,
					-0.5327636926773139
				]
			]
		},
		{
			"type": "text",
			"version": 974,
			"versionNonce": 1236724150,
			"isDeleted": false,
			"id": "Q8DMkDxu",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -7198.2005722323465,
			"y": 3259.740176354829,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 65.54670715332031,
			"height": 16.76001831425987,
			"seed": 284486442,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407896,
			"fontFamily": 1,
			"text": "probability",
			"rawText": "probability",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 985,
			"versionNonce": 1641825014,
			"isDeleted": false,
			"id": "MY4nqgZd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6844.513205085126,
			"y": 3380.8332569545187,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 52.61143493652344,
			"height": 16.760018314259874,
			"seed": 1648489962,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407898,
			"fontFamily": 1,
			"text": "scenario",
			"rawText": "scenario",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scenario",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 971,
			"versionNonce": 377779254,
			"isDeleted": false,
			"id": "Pdcl17Yd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -7077.967057453887,
			"y": 3385.749943430504,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.03155517578125,
			"height": 13.408014651407898,
			"seed": 52406442,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "A",
			"rawText": "A",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 991,
			"versionNonce": 26508662,
			"isDeleted": false,
			"id": "pa7y40WS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -7043.176662263475,
			"y": 3385.1031954575315,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.7925872802734375,
			"height": 13.408014651407898,
			"seed": 188285802,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "B",
			"rawText": "B",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "B",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 1013,
			"versionNonce": 944856758,
			"isDeleted": false,
			"id": "IynFiyxs",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -7007.951122782553,
			"y": 3385.4939863835148,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 6.902923583984375,
			"height": 13.408014651407898,
			"seed": 1691944490,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "C",
			"rawText": "C",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "C",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 963,
			"versionNonce": 1600133110,
			"isDeleted": false,
			"id": "0SwEujEw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6977.915728186321,
			"y": 3383.991384263582,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.824142456054688,
			"height": 13.408014651407898,
			"seed": 2028646634,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AB",
			"rawText": "AB",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AB",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 979,
			"versionNonce": 1053141302,
			"isDeleted": false,
			"id": "8uFBtSR4",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6944.644143335312,
			"y": 3384.9683615785393,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 13.934478759765625,
			"height": 13.408014651407898,
			"seed": 1526268842,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AC",
			"rawText": "AC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 972,
			"versionNonce": 1441206902,
			"isDeleted": false,
			"id": "kN1X1QQo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6908.68137536695,
			"y": 3384.9683615785393,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.695510864257812,
			"height": 13.408014651407898,
			"seed": 1966014058,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "BC",
			"rawText": "BC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "BC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 975,
			"versionNonce": 1871270838,
			"isDeleted": false,
			"id": "W1Lx9vqJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6877.8100427762765,
			"y": 3384.7729661155477,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 21.727066040039062,
			"height": 13.408014651407898,
			"seed": 878158122,
			"groupIds": [
				"ckWgDNeAc1w3OT11PepnS"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "ABC",
			"rawText": "ABC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ABC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"id": "v3oxX1WOJei5wCCtF0CII",
			"type": "arrow",
			"x": -6780.523039773052,
			"y": 3331.5889251144413,
			"width": 402.74288947035984,
			"height": 116.87171396133954,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 168907818,
			"version": 535,
			"versionNonce": 902917366,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					164.81349767804113,
					17.819220537835463
				],
				[
					189.30005462463123,
					109.17304737610993
				],
				[
					402.74288947035984,
					116.87171396133954
				]
			],
			"lastCommittedPoint": [
				405.6429741956381,
				108.17145978550343
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "TDJkxC-2y1lhrl2QbJTbZ",
			"type": "arrow",
			"x": -6777.5182770012325,
			"y": 3332.590512705048,
			"width": 411.4780363283753,
			"height": 110.98231675317402,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 1692671862,
			"version": 574,
			"versionNonce": 1178885686,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					164.50461363473005,
					-17.101924500982022
				],
				[
					171.58551213333612,
					-109.67184511925552
				],
				[
					411.4780363283753,
					-110.98231675317402
				]
			],
			"lastCommittedPoint": [
				406.6445617862446,
				-147.23337581915757
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "DcetZArb",
			"type": "text",
			"x": -6817.509897989728,
			"y": 3289.1720263195366,
			"width": 187.39979553222656,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1653665654,
			"version": 244,
			"versionNonce": 1170679670,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "after observing AB",
			"rawText": "after observing AB",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "after observing AB",
			"lineHeight": 1.25
		},
		{
			"id": "TLepbfFT",
			"type": "text",
			"x": -6530.675750295774,
			"y": 3169.4588996546486,
			"width": 95.53988647460938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2016051318,
			"version": 206,
			"versionNonce": 1956563126,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Previously",
			"rawText": "Previously",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Previously",
			"lineHeight": 1.25
		},
		{
			"id": "ipJsC98w",
			"type": "text",
			"x": -6515.0162199305105,
			"y": 3411.8410326551634,
			"width": 36.13996887207031,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1031683958,
			"version": 199,
			"versionNonce": 1114653174,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Now",
			"rawText": "Now",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Now",
			"lineHeight": 1.25
		},
		{
			"type": "rectangle",
			"version": 855,
			"versionNonce": 1648399158,
			"isDeleted": false,
			"id": "K52qbYoLh1r-SZsfbPZP5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6333.34085437782,
			"y": 3204.149681866222,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.20157576342991,
			"seed": 1227901494,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 808,
			"versionNonce": 1584708726,
			"isDeleted": false,
			"id": "UduH1e1zsNdAyXt7hbiqf",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6334.697292661794,
			"y": 3250.731796548344,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 0.5547199100998836,
			"height": 128.69501914316538,
			"seed": 1549112182,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5547199100998836,
					-128.69501914316538
				]
			]
		},
		{
			"type": "rectangle",
			"version": 899,
			"versionNonce": 751943094,
			"isDeleted": false,
			"id": "_Kd-phJqZYwa0ozFYH2aJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6299.236102947861,
			"y": 3204.2181427894125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.513653923740556,
			"seed": 109032630,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 907,
			"versionNonce": 1115461366,
			"isDeleted": false,
			"id": "a_k3lF4cP7pRSCHNsqOtK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6265.131351434052,
			"y": 3204.1496814431525,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.20157576343036,
			"seed": 1096003062,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 925,
			"versionNonce": 670713910,
			"isDeleted": false,
			"id": "S4VPtukIyTVbiKcqJBnuN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6231.026600239172,
			"y": 3203.4124218953807,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.938835208975895,
			"seed": 165052214,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 912,
			"versionNonce": 221237622,
			"isDeleted": false,
			"id": "AYox-KixGrpDh0dnUlQr1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6196.921849095129,
			"y": 3195.1678762699216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 1953310838,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 928,
			"versionNonce": 1566716598,
			"isDeleted": false,
			"id": "69btzU2D8p5uR1_wrLroz",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6162.817097849732,
			"y": 3203.4124215095603,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 47.319375888592276,
			"seed": 1088203190,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 928,
			"versionNonce": 1396075510,
			"isDeleted": false,
			"id": "N8By9uOPrUdPrzcqVUVxW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6128.712346568363,
			"y": 3204.2181428953813,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.51365460006219,
			"seed": 1850344182,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 904,
			"versionNonce": 212958518,
			"isDeleted": false,
			"id": "cgWM20d4or1ucI2bhQ3o6",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6094.607595494609,
			"y": 3195.167877301958,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 55.563920572744344,
			"seed": 1329214518,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 968,
			"versionNonce": 523789942,
			"isDeleted": false,
			"id": "ZWeVxy07VqkFxniu_tLds",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6337.446700901054,
			"y": 3251.070987934911,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 303.15542754404066,
			"height": 0.5327636926773139,
			"seed": 496123254,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					303.15542754404066,
					-0.5327636926773139
				]
			]
		},
		{
			"type": "text",
			"version": 757,
			"versionNonce": 730867638,
			"isDeleted": false,
			"id": "4dxuK7pa",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6414.989474843996,
			"y": 3140.1370661929172,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 65.54670715332031,
			"height": 16.76001831425987,
			"seed": 244784822,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407896,
			"fontFamily": 1,
			"text": "probability",
			"rawText": "probability",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 791,
			"versionNonce": 1910358262,
			"isDeleted": false,
			"id": "BMzzBwe7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6053.6399554522,
			"y": 3250.284215014641,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 52.61143493652344,
			"height": 16.760018314259874,
			"seed": 1726863350,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407898,
			"fontFamily": 1,
			"text": "scenario",
			"rawText": "scenario",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scenario",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 777,
			"versionNonce": 1705390646,
			"isDeleted": false,
			"id": "K6NIldma",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6287.093807820959,
			"y": 3255.2009014906257,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.03155517578125,
			"height": 13.408014651407898,
			"seed": 245066038,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "A",
			"rawText": "A",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 797,
			"versionNonce": 1104051062,
			"isDeleted": false,
			"id": "gqpKK7uK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6252.303412630547,
			"y": 3254.554153517653,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.7925872802734375,
			"height": 13.408014651407898,
			"seed": 621073014,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "B",
			"rawText": "B",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "B",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 819,
			"versionNonce": 479960246,
			"isDeleted": false,
			"id": "g44lMf7B",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6217.077873149626,
			"y": 3254.9449444436364,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 6.902923583984375,
			"height": 13.408014651407898,
			"seed": 351212470,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "C",
			"rawText": "C",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "C",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 769,
			"versionNonce": 2075301366,
			"isDeleted": false,
			"id": "vpzvY4Zx",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6187.042478553393,
			"y": 3253.4423423237045,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.824142456054688,
			"height": 13.408014651407898,
			"seed": 679423222,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AB",
			"rawText": "AB",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AB",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 785,
			"versionNonce": 1746429750,
			"isDeleted": false,
			"id": "oov1Jt5B",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6153.7708937023845,
			"y": 3254.419319638661,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 13.934478759765625,
			"height": 13.408014651407898,
			"seed": 490348086,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AC",
			"rawText": "AC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 778,
			"versionNonce": 36835446,
			"isDeleted": false,
			"id": "NIEkdIFh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6117.8081257340245,
			"y": 3254.419319638661,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.695510864257812,
			"height": 13.408014651407898,
			"seed": 939845494,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "BC",
			"rawText": "BC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "BC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 781,
			"versionNonce": 365203894,
			"isDeleted": false,
			"id": "3eM2uBCx",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6086.936793143349,
			"y": 3254.2239241756693,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 21.727066040039062,
			"height": 13.408014651407898,
			"seed": 1495566518,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "ABC",
			"rawText": "ABC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ABC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "rectangle",
			"version": 813,
			"versionNonce": 771025654,
			"isDeleted": false,
			"id": "2sCKXFzzBvv6YLF0vXVQ5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6345.557273336618,
			"y": 3430.4675284281598,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.20157576342991,
			"seed": 1674008874,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 766,
			"versionNonce": 692591670,
			"isDeleted": false,
			"id": "9m0xQGtH4LRe2qEMH-9bF",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6346.91371162059,
			"y": 3477.0496431102815,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 0.5547199100998836,
			"height": 128.69501914316538,
			"seed": 1284940778,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5547199100998836,
					-128.69501914316538
				]
			]
		},
		{
			"type": "rectangle",
			"version": 857,
			"versionNonce": 1302537590,
			"isDeleted": false,
			"id": "Y-xrHzGKdMAmhzBP21gM-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6311.452521906657,
			"y": 3430.53598935135,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.513653923740556,
			"seed": 1521391274,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 882,
			"versionNonce": 1548420790,
			"isDeleted": false,
			"id": "Jv_kC_SRQJkQ4vu969Uov",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6277.347770392848,
			"y": 3441.122941259811,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 35.54616250870959,
			"seed": 783954282,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 883,
			"versionNonce": 635748342,
			"isDeleted": false,
			"id": "KoXo7UDJAIY92v1K45Fg-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6243.243019197968,
			"y": 3429.7302684573183,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.938835208975895,
			"seed": 470053930,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 879,
			"versionNonce": 511004982,
			"isDeleted": false,
			"id": "nJ1BkkK7gKU-QlBgslJEp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6209.1382680539255,
			"y": 3415.1500717074305,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 61.89957169717309,
			"seed": 1417174762,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 886,
			"versionNonce": 1902230134,
			"isDeleted": false,
			"id": "-UAgFErlVuxe3yE4dhA69",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6175.03351680853,
			"y": 3429.730268071498,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 47.319375888592276,
			"seed": 346091946,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 886,
			"versionNonce": 359594934,
			"isDeleted": false,
			"id": "hgoyUM9dSA1NIkWl1_XE8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6140.928765527159,
			"y": 3430.535989457319,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.51365460006219,
			"seed": 1336487018,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 882,
			"versionNonce": 1623332086,
			"isDeleted": false,
			"id": "gx8XmPrz-XHYl8vKjH2_O",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6106.824014453406,
			"y": 3430.12524812448,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 34.104751248098296,
			"height": 46.92439631215985,
			"seed": 1532759850,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 926,
			"versionNonce": 484443702,
			"isDeleted": false,
			"id": "6kQ78UprQAXVxOjYvwFQQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6349.6631198598525,
			"y": 3477.3888344968486,
			"strokeColor": "#1971c2",
			"backgroundColor": "#fff9db",
			"width": 303.15542754404066,
			"height": 0.5327636926773139,
			"seed": 472160746,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					303.15542754404066,
					-0.5327636926773139
				]
			]
		},
		{
			"type": "text",
			"version": 715,
			"versionNonce": 447598454,
			"isDeleted": false,
			"id": "xBLwGkxc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6427.205893802792,
			"y": 3366.454912754855,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 65.54670715332031,
			"height": 16.76001831425987,
			"seed": 822987946,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407896,
			"fontFamily": 1,
			"text": "probability",
			"rawText": "probability",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "probability",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 749,
			"versionNonce": 1181774006,
			"isDeleted": false,
			"id": "LgXxQYYq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6065.856374410997,
			"y": 3476.6020615765788,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 52.61143493652344,
			"height": 16.760018314259874,
			"seed": 532850538,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 13.408014651407898,
			"fontFamily": 1,
			"text": "scenario",
			"rawText": "scenario",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "scenario",
			"lineHeight": 1.25,
			"baseline": 11
		},
		{
			"type": "text",
			"version": 735,
			"versionNonce": 1003284982,
			"isDeleted": false,
			"id": "g27P9Mue",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6299.310226779756,
			"y": 3481.5187480525633,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.03155517578125,
			"height": 13.408014651407898,
			"seed": 9316906,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "A",
			"rawText": "A",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 755,
			"versionNonce": 1506294582,
			"isDeleted": false,
			"id": "lkTmUWMD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6264.519831589344,
			"y": 3480.8720000795906,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 7.7925872802734375,
			"height": 13.408014651407898,
			"seed": 710628586,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "B",
			"rawText": "B",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "B",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 777,
			"versionNonce": 1455907958,
			"isDeleted": false,
			"id": "5ooY1U2r",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6229.294292108422,
			"y": 3481.262791005574,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 6.902923583984375,
			"height": 13.408014651407898,
			"seed": 1588930474,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "C",
			"rawText": "C",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "C",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 727,
			"versionNonce": 1418683830,
			"isDeleted": false,
			"id": "rEBjDczl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6199.25889751219,
			"y": 3479.760188885642,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.824142456054688,
			"height": 13.408014651407898,
			"seed": 1975951978,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AB",
			"rawText": "AB",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AB",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 743,
			"versionNonce": 1950695158,
			"isDeleted": false,
			"id": "Vw6Autku",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6165.987312661181,
			"y": 3480.7371662005985,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 13.934478759765625,
			"height": 13.408014651407898,
			"seed": 173720874,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "AC",
			"rawText": "AC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "AC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 736,
			"versionNonce": 1785589814,
			"isDeleted": false,
			"id": "LljYdUpO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6130.024544692821,
			"y": 3480.7371662005985,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 14.695510864257812,
			"height": 13.408014651407898,
			"seed": 635211754,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "BC",
			"rawText": "BC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "BC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 739,
			"versionNonce": 317618550,
			"isDeleted": false,
			"id": "u42TsBOv",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6099.1532121021455,
			"y": 3480.541770737607,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 21.727066040039062,
			"height": 13.408014651407898,
			"seed": 1817641642,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"fontSize": 10.726411721126318,
			"fontFamily": 1,
			"text": "ABC",
			"rawText": "ABC",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ABC",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"id": "BbsP89LBf61i5B0nLzAg8",
			"type": "line",
			"x": -6095.341487540304,
			"y": 3418.707032010339,
			"width": 50.58764139058803,
			"height": 63.656115416488774,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 253509110,
			"version": 284,
			"versionNonce": 84662966,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-10.117528278117788,
					-44.68574989501849
				],
				[
					-50.58764139058803,
					-50.16607771233248
				],
				[
					-50.16607771233248,
					-63.656115416488774
				]
			],
			"lastCommittedPoint": [
				-50.16607771233248,
				-63.656115416488774
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "ySlktUSajFW5px-Sa4MCu",
			"type": "line",
			"x": -6191.8795698606755,
			"y": 3402.687612236653,
			"width": 46.79356828629352,
			"height": 48.0582593210579,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 1445344938,
			"version": 252,
			"versionNonce": 661328886,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.107818391275032,
					-33.725094260391415
				],
				[
					41.73480414723508,
					-34.568221616901155
				],
				[
					46.79356828629352,
					-48.0582593210579
				]
			],
			"lastCommittedPoint": [
				46.79356828629352,
				-48.0582593210579
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "AwFTcixQ",
			"type": "text",
			"x": -6245.540969003587,
			"y": 3308.2926717047208,
			"width": 211.10858154296875,
			"height": 48.4416969638866,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 984091562,
			"version": 394,
			"versionNonce": 1141974326,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "choose only one randomly between\nh that correlate to AB\nto increase",
			"rawText": "choose only one randomly between\nh that correlate to AB\nto increase",
			"fontSize": 12.917785857036426,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "choose only one randomly between\nh that correlate to AB\nto increase",
			"lineHeight": 1.25
		},
		{
			"id": "DcLmcGXsD0Us1sJO591GS",
			"type": "line",
			"x": -6219.785890173889,
			"y": 3324.998305204413,
			"width": 11.911813857602283,
			"height": 0.5179049503303759,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 1222768438,
			"version": 231,
			"versionNonce": 476253814,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					11.911813857602283,
					-0.5179049503303759
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "vrJHgrsHtodx9uCmG0_UB",
			"type": "line",
			"x": -6125.044053376772,
			"y": 3501.843456601822,
			"width": 82.17359545400723,
			"height": 61.173676615760996,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 1688577270,
			"version": 304,
			"versionNonce": 2099630006,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.0009063268353202,
					28.942220526266283
				],
				[
					-74.41275588335066,
					34.238998105836345
				],
				[
					-82.17359545400723,
					61.173676615760996
				]
			],
			"lastCommittedPoint": [
				-82.17359545400723,
				61.173676615760996
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "qI26sNu8TwJijNS1tV3vn",
			"type": "line",
			"x": -6260.910138541081,
			"y": 3504.4149307665757,
			"width": 53.96951510342478,
			"height": 56.486228242962625,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 346613302,
			"version": 329,
			"versionNonce": 1384016118,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8389043798460989,
					27.963479328199355
				],
				[
					47.7569968544467,
					30.917173098831427
				],
				[
					53.96951510342478,
					56.486228242962625
				]
			],
			"lastCommittedPoint": [
				53.96951510342478,
				56.486228242962625
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "0aFx05Ssvm3s0DVTNZCZ_",
			"type": "line",
			"x": -6160.939106448117,
			"y": 3503.0167568001657,
			"width": 46.29389974003698,
			"height": 59.00294138250047,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 1229290346,
			"version": 361,
			"versionNonce": 1005705782,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4337936417905439,
					27.801763139161267
				],
				[
					-38.43862961371087,
					32.41414373366206
				],
				[
					-45.86010609824643,
					59.00294138250047
				]
			],
			"lastCommittedPoint": [
				-45.86010609824643,
				59.00294138250047
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "dLrITPN1bBp4073JAI0J0",
			"type": "line",
			"x": -6227.633598140525,
			"y": 3503.0167568001657,
			"width": 25.918803702098558,
			"height": 54.5287846899887,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 691964534,
			"version": 430,
			"versionNonce": 543499126,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-4.107289826102715,
					28.09414588965865
				],
				[
					19.137454898645046,
					35.16150346500217
				],
				[
					21.811513875995843,
					54.5287846899887
				]
			],
			"lastCommittedPoint": [
				21.811513875995843,
				54.5287846899887
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "d63JyfDZz4Yv3YAmVR4ro",
			"type": "line",
			"x": -6295.025583321484,
			"y": 3508.050183079242,
			"width": 88.08814687313043,
			"height": 51.732436757168216,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 258239530,
			"version": 307,
			"versionNonce": 1109214390,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.28282178258541535,
					24.44732898169923
				],
				[
					81.6533596383415,
					27.40420974163544
				],
				[
					87.80532509054501,
					51.732436757168216
				]
			],
			"lastCommittedPoint": [
				87.80532509054501,
				51.732436757168216
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "3M-qusIQsFQ9N_ZRSeNbR",
			"type": "line",
			"x": -6328.861393308605,
			"y": 3508.889087459088,
			"width": 121.92076987094879,
			"height": 51.452801963886486,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 367338282,
			"version": 353,
			"versionNonce": 1388264950,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.1185391731278287,
					25.44676618866106
				],
				[
					113.25209127920698,
					26.565305361789342
				],
				[
					121.92076987094879,
					51.452801963886486
				]
			],
			"lastCommittedPoint": [
				121.92076987094879,
				51.452801963886486
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "RtXoOckV",
			"type": "text",
			"x": -6316.277380343106,
			"y": 3564.19195751994,
			"width": 244.36029052734375,
			"height": 41.36531613495582,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#868e96",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1588596406,
			"version": 406,
			"versionNonce": 122687286,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "choose randomly another x by using Gibbs\nthen choose randomly a variation one h of it\nto decrease",
			"rawText": "choose randomly another x by using Gibbs\nthen choose randomly a variation one h of it\nto decrease",
			"fontSize": 11.03075096932155,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 37,
			"containerId": null,
			"originalText": "choose randomly another x by using Gibbs\nthen choose randomly a variation one h of it\nto decrease",
			"lineHeight": 1.25
		},
		{
			"id": "ls_uDRkF9TZvKOf1h-I5_",
			"type": "line",
			"x": -6111.150203037709,
			"y": 3579.772398433831,
			"width": 11.661405970602573,
			"height": 0.21595196241878512,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 1860765494,
			"version": 214,
			"versionNonce": 741652598,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					11.661405970602573,
					-0.21595196241878512
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "RW8vfkM9qW1t7j5bp8516",
			"type": "line",
			"x": -6089.416943473806,
			"y": 3500.7057800850826,
			"width": 117.07264458009922,
			"height": 60.31967187530154,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 1835102902,
			"version": 410,
			"versionNonce": 959592886,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-4.886582277428715,
					31.89605096521518
				],
				[
					-103.21437434609925,
					33.655832549799925
				],
				[
					-117.07264458009922,
					60.31967187530154
				]
			],
			"lastCommittedPoint": [
				-115.65853566716942,
				58.76415207107948
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "RSqb7zfZBaRVmMMn4dzoB",
			"type": "line",
			"x": -6196.307992331647,
			"y": 3495.89780400654,
			"width": 9.883061939226536,
			"height": 62.77079880319843,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 503624234,
			"version": 230,
			"versionNonce": 1701679862,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-9.883061939226536,
					62.77079880319843
				]
			],
			"lastCommittedPoint": [
				-9.883061939226536,
				62.77079880319843
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "TCphrlyX_XKlY0DCSMfRX",
			"type": "arrow",
			"x": -5829.254284261708,
			"y": 4916.6539825530035,
			"width": 122.54272301267702,
			"height": 3.124845830290724,
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
			"seed": 970757302,
			"version": 548,
			"versionNonce": 653983530,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216619317,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-122.54272301267702,
					3.124845830290724
				]
			],
			"lastCommittedPoint": [
				-188.46564557953934,
				2.2172428891708478
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "4nQMV7u0DHP8E2EtlImrH",
				"focus": -0.1385108635615155,
				"gap": 16.214217518326677
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "cmqMaVqB",
			"type": "text",
			"x": -5934.531622346189,
			"y": 4886.620433811144,
			"width": 79.53617858886719,
			"height": 20,
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
			"seed": 831308522,
			"version": 245,
			"versionNonce": 756141430,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708216618471,
			"link": null,
			"locked": false,
			"text": "Derivation",
			"rawText": "Derivation",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Derivation",
			"lineHeight": 1.25
		},
		{
			"id": "4nQMV7u0DHP8E2EtlImrH",
			"type": "embeddable",
			"x": -6517.368912849884,
			"y": 4795.060819134947,
			"width": 549.3576880571718,
			"height": 309.01369953215914,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1514663210,
			"version": 348,
			"versionNonce": 665104054,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "TCphrlyX_XKlY0DCSMfRX",
					"type": "arrow"
				}
			],
			"updated": 1708216618471,
			"link": "https://youtu.be/lekCh_i32iE?si=PwOeatD6--ll7D81&t=277",
			"locked": false,
			"scale": [
				1,
				1
			]
		},
		{
			"id": "PnzGzl_Gl4jtJ_FG27Ifp",
			"type": "arrow",
			"x": -1077.0221771864676,
			"y": 1558.9734175968154,
			"width": 918.5231007966734,
			"height": 179.05785485915544,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1099820650,
			"version": 712,
			"versionNonce": 592918058,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708216824845,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					885.081805978002,
					-10.996305760246969
				],
				[
					918.5231007966734,
					168.06154909890847
				]
			],
			"lastCommittedPoint": [
				962.3863852978134,
				184.02572523400136
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "32zhlyHu",
			"type": "text",
			"x": -449.2134161769212,
			"y": 1750.086592432076,
			"width": 647.4193115234375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 177728490,
			"version": 273,
			"versionNonce": 1337128182,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708218121026,
			"link": null,
			"locked": false,
			"text": "Oh sorry that took longer than expected, anyway where were we?",
			"rawText": "Oh sorry that took longer than expected, anyway where were we?",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Oh sorry that took longer than expected, anyway where were we?",
			"lineHeight": 1.25
		},
		{
			"id": "ys83Zgbs",
			"type": "text",
			"x": -2034.8772812857649,
			"y": 4474.134868166071,
			"width": 1223.7730712890625,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1641722026,
			"version": 138,
			"versionNonce": 1290199350,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217013747,
			"link": null,
			"locked": false,
			"text": "THIS WILL BE A REPLACEMENT FUNCTION FOR THE STANDARD ENERGY FUNCTION\n(Read the training part first)",
			"rawText": "THIS WILL BE A REPLACEMENT FUNCTION FOR THE STANDARD ENERGY FUNCTION\n(Read the training part first)",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "THIS WILL BE A REPLACEMENT FUNCTION FOR THE STANDARD ENERGY FUNCTION\n(Read the training part first)",
			"lineHeight": 1.25
		},
		{
			"id": "VlpMmdHL",
			"type": "text",
			"x": -1620.080958206137,
			"y": 4564.323296329237,
			"width": 404.6995849609375,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2146153130,
			"version": 104,
			"versionNonce": 291677558,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217113655,
			"link": null,
			"locked": false,
			"text": "The log-likelihood of the data turns into\n\n\n\nDeriving our gradient we  arrive at",
			"rawText": "The log-likelihood of the data turns into\n\n\n\nDeriving our gradient we  arrive at",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 118,
			"containerId": null,
			"originalText": "The log-likelihood of the data turns into\n\n\n\nDeriving our gradient we  arrive at",
			"lineHeight": 1.25
		},
		{
			"id": "vJyrLNGQL-GYSeFrElFHx",
			"type": "image",
			"x": -1620.0809583763735,
			"y": 4689.32329640889,
			"width": 416,
			"height": 91,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 532955126,
			"version": 21,
			"versionNonce": 776587626,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217124746,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ab6d835db2b83ed0b87761035db276ae3569e3a1",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Czg4afqGBABJZ9bykAI4g",
			"type": "line",
			"x": -1432.4205125770347,
			"y": 4782.148035028565,
			"width": 48.46076859789923,
			"height": 1.346132461052548,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1713290742,
			"version": 43,
			"versionNonce": 1993487658,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217138615,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-48.46076859789923,
					-1.346132461052548
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "qLve7r-ca0vPd5kvIVSJg",
			"type": "line",
			"x": -1457.548318516686,
			"y": 4782.596745848916,
			"width": 91.89210335170014,
			"height": 74.16154967280818,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1910898666,
			"version": 65,
			"versionNonce": 1588801002,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217221784,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					5.833240664561799,
					47.56334695719761
				],
				[
					-86.05886268713834,
					74.16154967280818
				]
			],
			"lastCommittedPoint": [
				-30.06362496351153,
				69.55017715439226
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "4RbcuHhQ",
			"type": "text",
			"x": -1828.4686058238053,
			"y": 4854.1232255112,
			"width": 529.2993774414062,
			"height": 150,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1062310634,
			"version": 91,
			"versionNonce": 1153914346,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217219570,
			"link": null,
			"locked": false,
			"text": "positive phase\ncorresponds to the expected gradient of\nthe energy This simplification occurs because\nthe gradient of F w.r.t. p(h|v)\nis zero, so the effect of changing the parameters on\np(h|v) can be ignored",
			"rawText": "positive phase\ncorresponds to the expected gradient of\nthe energy This simplification occurs because\nthe gradient of F w.r.t. p(h|v)\nis zero, so the effect of changing the parameters on\np(h|v) can be ignored",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 143,
			"containerId": null,
			"originalText": "positive phase\ncorresponds to the expected gradient of\nthe energy This simplification occurs because\nthe gradient of F w.r.t. p(h|v)\nis zero, so the effect of changing the parameters on\np(h|v) can be ignored",
			"lineHeight": 1.25
		},
		{
			"id": "bZ4CQXzDCvLB4SFBULjs7",
			"type": "line",
			"x": -1376.4446530433463,
			"y": 4785.687970884557,
			"width": 183.1373657313909,
			"height": 5.928907523677481,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 381434730,
			"version": 47,
			"versionNonce": 645984746,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217227547,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					183.1373657313909,
					-5.928907523677481
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "XM0tY3Vj6dsxMIx5NR8mM",
			"type": "line",
			"x": -1282.8996676697582,
			"y": 4783.052900874034,
			"width": 129.11843051565688,
			"height": 88.9336128551713,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
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
			"seed": 1917997814,
			"version": 72,
			"versionNonce": 1497929706,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217231505,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					19.10425757629605,
					61.26537774467306
				],
				[
					129.11843051565688,
					88.9336128551713
				]
			],
			"lastCommittedPoint": [
				129.11843051565688,
				88.9336128551713
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "GCzeHR4j",
			"type": "text",
			"x": -1250.8961590556835,
			"y": 4875.939118744991,
			"width": 552.599365234375,
			"height": 150,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 528623798,
			"version": 189,
			"versionNonce": 1115652790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708217328919,
			"link": null,
			"locked": false,
			"text": "negative phase, is an expectation over the model\ndistribution, p(v), and is intractable to compute exactly\nfor all but the smallest model\nGibbs sampling is still possible ofc\nWe can then ignore the sampled h and only keep the\nsampled v",
			"rawText": "negative phase, is an expectation over the model\ndistribution, p(v), and is intractable to compute exactly\nfor all but the smallest model\nGibbs sampling is still possible ofc\nWe can then ignore the sampled h and only keep the\nsampled v",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 143,
			"containerId": null,
			"originalText": "negative phase, is an expectation over the model\ndistribution, p(v), and is intractable to compute exactly\nfor all but the smallest model\nGibbs sampling is still possible ofc\nWe can then ignore the sampled h and only keep the\nsampled v",
			"lineHeight": 1.25
		},
		{
			"id": "O3nofUTz",
			"type": "text",
			"x": -449.21341593015615,
			"y": 1780.4156018838198,
			"width": 653.4193115234375,
			"height": 175,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1971239338,
			"version": 155,
			"versionNonce": 482013302,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708218119261,
			"link": null,
			"locked": false,
			"text": "Unlike RBMS, CRBMS model the distribution of two inputs u and v\np(v|u) by using an RBM to model v and using u to dynamically\ndetermine the biases or weights of that RBM\n\n\n\nAssociated with the distribution",
			"rawText": "Unlike RBMS, CRBMS model the distribution of two inputs u and v\np(v|u) by using an RBM to model v and using u to dynamically\ndetermine the biases or weights of that RBM\n\n\n\nAssociated with the distribution",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 168,
			"containerId": null,
			"originalText": "Unlike RBMS, CRBMS model the distribution of two inputs u and v\np(v|u) by using an RBM to model v and using u to dynamically\ndetermine the biases or weights of that RBM\n\n\n\nAssociated with the distribution",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 141,
			"versionNonce": 966694698,
			"isDeleted": false,
			"id": "v1C4Fj4S",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -535.1028498507133,
			"y": 1862.4349009891414,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 830.8655119051506,
			"height": 36.6274819633361,
			"seed": 3674,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708217625272,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2f1183fa1f8aa17584d1e81bdf626d196593895e",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "QLZ69Vla",
			"type": "text",
			"x": -616.8892259181008,
			"y": 2015.0838204283875,
			"width": 1011.5990600585938,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 911103146,
			"version": 288,
			"versionNonce": 358026986,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708218105102,
			"link": null,
			"locked": false,
			"text": "The energy function is defined like RBM but with an additional layer u and weights associated with it\nWe can turn this energy function the same way we did with RBMs into a free energy function\nmarginalized over h values",
			"rawText": "The energy function is defined like RBM but with an additional layer u and weights associated with it\nWe can turn this energy function the same way we did with RBMs into a free energy function\nmarginalized over h values",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "The energy function is defined like RBM but with an additional layer u and weights associated with it\nWe can turn this energy function the same way we did with RBMs into a free energy function\nmarginalized over h values",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 165,
			"versionNonce": 640262570,
			"isDeleted": false,
			"id": "WIdOlqwm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -529.4436000656558,
			"y": 2100.6340628428106,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 867.8937029396532,
			"height": 65.17778796780004,
			"seed": 64624,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708218105102,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9b64c0af91848b6f3c0b2a7186db887d8cf2aa0b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "gFuD3017",
			"type": "text",
			"x": -403.42103184577957,
			"y": 2176.3620934533424,
			"width": 574.21923828125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 909128758,
			"version": 135,
			"versionNonce": 211541098,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708218105102,
			"link": null,
			"locked": false,
			"text": "This free energy function defined the following distribution",
			"rawText": "This free energy function defined the following distribution",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "This free energy function defined the following distribution",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 225,
			"versionNonce": 1182318378,
			"isDeleted": false,
			"id": "gD4VABQo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -298.41093755076855,
			"y": 2212.537900580595,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 351.8143551318557,
			"height": 70.36287102637114,
			"seed": 68663,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708218105102,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9334036148bc15cfb8b2a244e14f2e86159cf47a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 129,
			"versionNonce": 739520502,
			"isDeleted": false,
			"id": "unyzMo3X",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -355.31704222907894,
			"y": 1960.7446122744684,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 459.62656349122614,
			"height": 37.320105582620926,
			"seed": 39539,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708218184934,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "31ee164613b395561a3aa7005888276f3ec2d4b8",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "UguVEdWduBpTJpOL3b04H",
			"type": "line",
			"x": 310.4902274793068,
			"y": 1890.8571004446358,
			"width": 344.6354629548323,
			"height": 30.431387457380424,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
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
			"seed": 530576182,
			"version": 86,
			"versionNonce": 956753130,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708218205312,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					197.8040184729722,
					0.7607846864343628
				],
				[
					344.6354629548323,
					30.431387457380424
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "vg0gDQA7",
			"type": "text",
			"x": 366.4591653089054,
			"y": 1909.2257319954153,
			"width": 247.15249633789062,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1807314934,
			"version": 154,
			"versionNonce": 1811291370,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708218246632,
			"link": null,
			"locked": false,
			"text": "sometimes seen in a simpler\nform where the biases are 0\nand v and u are not connected\n(x and y here)",
			"rawText": "sometimes seen in a simpler\nform where the biases are 0\nand v and u are not connected\n(x and y here)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "sometimes seen in a simpler\nform where the biases are 0\nand v and u are not connected\n(x and y here)",
			"lineHeight": 1.25
		},
		{
			"id": "0t50sLMnti6UxIpHOi0Hw",
			"type": "image",
			"x": 320.8917975387892,
			"y": 2196.8206130082845,
			"width": 586,
			"height": 103,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 690164778,
			"version": 26,
			"versionNonce": 1353743030,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708218520633,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0dc9ce934cb083f3e671aaeda8271cd54f2b2665",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 334,
			"versionNonce": 2064473002,
			"isDeleted": true,
			"id": "mY4dmr91",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2463.9721257967262,
			"y": 1952.7638554220107,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 505.0794982910156,
			"height": 50,
			"seed": 1006893808,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708218276270,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "and the system associates each state of x,y,h to\na probability",
			"rawText": "and the system associates each state of x,y,h to\na probability",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "and the system associates each state of x,y,h to\na probability",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 216,
			"versionNonce": 1184980970,
			"isDeleted": true,
			"id": "7AJTJQ1CN03zNKBdB6Opn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3004.4330620017217,
			"y": 2045.1424117561032,
			"strokeColor": "#e03131",
			"backgroundColor": "#2f9e44",
			"width": 26.858294917492913,
			"height": 0,
			"seed": 1048971128,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708218189480,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.858294917492913,
					0
				]
			]
		},
		{
			"type": "image",
			"version": 490,
			"versionNonce": 1516462518,
			"isDeleted": true,
			"id": "NaAXZ1jJclcEAmzb9BUB9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 447.800072529203,
			"y": 2166.7961494453516,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"width": 542,
			"height": 80,
			"seed": 1168876272,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708218179512,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6d5ecdc71557037be5b1a79e541cbffd92613064",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "xKNHspjb",
			"type": "text",
			"x": 894.1370193295787,
			"y": 2211.575880871169,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 148858358,
			"version": 2,
			"versionNonce": 1840217898,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708218179072,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "U2fJ12uC",
			"type": "text",
			"x": -12.068617617745304,
			"y": 2359.6861330296197,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1248118710,
			"version": 2,
			"versionNonce": 590139754,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1708218306179,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
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
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 9209.552286167667,
		"scrollY": 1937.4426435917903,
		"zoom": {
			"value": 0.1
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