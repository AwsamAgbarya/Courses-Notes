---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - DeepLearning
---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Optimization ^kI8DN9xe

Motivation behind optimization ^9F3v6Zuv

Alongside the building process of our neural network and having devised an algorithm
in order to train it, comes a bunch of questions left unanswered, including

"How do we know that we are not stuck at a saddle point/local minima/plateu?"
"How fast does this converge and are there ways to improve upon it?"
"what are the best initializations that we can provide?"

and although some of those questions are only answered through heuristics and bullshit
with the power of love and friendship, we are going to try to reason through most of them! ^H0oWks4G

The great escape: Local minima edition ^VuE1lGh5

Previously on Dragon Ball Z, we have proven that the perceptron algorithm is equivalent
to the gradient descent of such function, thus guaranteeing us that we are always heading
towards a minimum of sorts.
and the function given by the error of a perceptron is a convex function ^fUuEAvUY

Now Lets take a more slightly more
complicated neural network and see if
this applies ^A9Q3BYOB

Such that its error function is given by ^izygGd0u

%%***>>>text element-link:[[Normalization]]<<<***%%What is this
unholy norm? ^c5fbq0Ub

While we can still perform Gradient descent this function
is clearly no longer convex, its much more complicated
and consists of a saddle point and two minimas
thus not being a convex function ^ed144UqR

What is a saddle Point? ^FRLl4Pfm

A saddle point is a point in a function
that looks like a global minimum from certain
angles but is a maximum point from other angles ^bKDQwp2d

Well shit then, what do we do? ^zuw0II8M

This can also be observed from nonlinear
activation functions applied to the neurons ^arYDH0ZC

Not only does this result in many minimas, we also get plateaus where our gradient
will be almost 0, resulting in barely in movement in gradient descent which gets us
stuck on minimizing the error ^n8lLcjXp

Lets start with some practical
recommendations based on Heuristics ^Q593qS24

Initializing parameters at constant c provides parameter symmetry,
all your parameters will move together towards each detection which limits 
the space that we traverse making us only able to find the saddle point as a minimum
furthermore, with certain activations like ReLu there will be absolutely
no learning at all as the result will always be 0 and as such from error
backpropagation, the gradients will get multiplied by 0! ^wc0JF6DG

1) Initializations ^D8wFJKzr

Randomly initialize your variables i.e drawn from a gaussian distribution with a fixed scale,
The scale of this distribution should not be too large to avoid plateaus of nonlinear functions
do not set them to 0 nor apply symmetry to their values
 ^HrrGzsnq

2) Retraining ^UCZNPKg7

The results of random parameter initializations are not guaranteed to be
optimal as you can still land in local minimas, try to retrain the network
multiple times with multiple random initializations and keep the lowest error model ^mdxcwVSc

3) Learning rate
The learning rate of gradient descent should not be too large or too little
too little steps will be a lot harder
a larger LR will help escape local minima! ^SnLfQHYK

Too large ^cxufzZGD

Too small ^eLIJSYe6

High enough to
escape local minimum ^ddWn75MT

4) Number of Neurons
Use a sufficient number of neurons at each layer,
using more neurons will help with escaping local minima and not underfit the problem
too many neurons will cause your model to overfit though! ^cZMeQWSn

5) Number of layers
Do not go deeper than necessary, deeper neural networks are harder to optimize
Earlier layers in deeper neural networks are way slower at training
and deeper neural networks will cause unstable weights that either explode or
vanish ^FmXbTP0S

Applying varying learning rates is more beneficial
We want higher learning rates at the start to help us escape
local minima, and slowly decay that learning rate the closer we 
actually get to the minima in order to not overshoot the optimum
and fine tune parameters closer to it
here are some options ^wPEU5yxu

Apply step decay that decays the learning rate every k iterations by a factor ^vBQO2JVu

Exponential decay, were the learning rate decays smoothly over time ^AciZiu57

Cyclical decay where we shrink and grow our learning rate repeatedly ^Qqn4PNe1

How do we make sure our Error function converges well? ^wqJ1pHoH

A Well conditioned Error function is one that its optimum is not flat
Meaning that the convergence to the minima from all sides is about the same rate, such
that we can easily converge to it without moving much at the bottom
Whilst a poorly conditioned function converges too fast from one side and too slow
from another, making it fast in one direction and really slow in the other
this causes a lot of iterations to search in the slower side for an optimal solution ^RdMYEbzF

Suppose that we have an error function taking this following form ^aQVpxhvM

Positive 
coefficient
describing the 
curvature of that
dimension ^cq5asjoL

Parameter to
optimize ^mhZxzZ4f

Theoritical
best solution ^00Hoox0c

We can observe that the function
is much more well-conditioned when
all dimensions have similar curvatures 
 ^AAw0w606

and is poorly conditioned when one
side converges way faster than 
the other ^9XR61gBY

Can we quantify this
difficulty of the
optimization? ^e5KbwmuO

Using gradient descent we perform a step ^2hYF0bbs

Using our initial solution we can perform
t iterations and get ^AkzwVoIk

We can observe that if the
solution to the optimum decreases ^5qOYYjbp

Then this term has to decrease ^MT7mGYOu

Since this is static ^SdvsqZZM

Meaning that if we decrease our convergence along every dimension
our optimal solution gets closer and closer to the solution exponentially
fast ^Buq49OcN

Likewise that our Error function also decreases exponentially
fast since it is a linear combination of our optimum solutions 
in each dimension ^V11hs5GO

How do we choose our batch size? ^PJrxSZir

We can think of five interrelated aspects when it comes to the choice


1. statistical efficiency
Larger batches typically determine the quality of the gradient
estimate when training. This is assuming that the larger batch does
not have redundancy, rendering it somewhat useless/ less useful
than what we hope.



2. Computational efficiency
While larger batches take more time to compute the gradient and perform
a step in the right direction,
due to multi-core technology or hardware that allows computation of
gradients related to the same batch in parallel, smaller batches
may under utilize the power the hardware holds and thus making
the process unnecessarily slow
Available memory should also be considered when choosing a batchsize
as we do not want to choose something that exceeds our memory limits 



3. Regularization strategy
Small batches can offer a regularization effect because the gradient estimate is no
longer sensitive to the training set (due to having a small batch) and thus allowing us
to generalize more in our gradient
Keep in mind we choose a small learning rate for smaller batches because we dont want
to take large steps in very general directions with low confidence



4. Optimization strategy
Depending on our optimization strategy, sometimes we ought to compute
second order derivative (Hessian) estimates which requires a large batch size
if the Hessian is ill-conditioned and has a poor condition number
(aka very sensitive to errors when estimating the gradient because
its much more prone to miscalculations when multiplied with other vectors H * g)
These strategies require larger batch sizes in order to get more accurate estimations



5. Computation of choosing the batchsize
Ideally we want our batches to be chosen independently from the dataset, such that
each batch is unbiased and diverse. This can sometimes be very costly with larger datasets.
(Although its advantageous in bootstrap aggregating because we want diversity in batches)
In other cases, we usually Shuffle the entire dataset ones and we choose our batches deterministically
through some interval. (This can be useful for bench-marking different models)



*We usually go over the data multiple times (We call this iteration an epoch)
which is a bit counter intuitive because it makes the model
generalize less in some cases BUT for most starting cases our epochs are used
in order to not underfit the data and actually extract all information of features.
underfitting and computational efficiency is typically more of a concern in larger datasets.
More on this in Early-Stopping ^vjo9h2zX

for rich and diverse datasets we like larger batchsizes ^1eli204b

Our batch size needs to depend and be chosen with our architecture in mind! ^KiLCAHvq

small batches with small learning rates make it harder to overfit ^orQTirpE

-1 ^ltCZ6Xsd

depending on your optimization strategy, larger batches offer less errors in estimates of the gradient ^DPiq1RjB

choosing how much computation are you willing to spend on making the batches is dependent on your strategy ^3e6bSQNu

Poor condition number means that the ratio
between the minimum and maximum eigenvalues of
the hessian is large ^SAAk8xWL

and what do the eigenvalues
of the hessian represent?

it represents how much the first order
derivative changes in the direction of the
eigenvector
(can be thought of as sensitivity or acceleration) ^rakYpU8D

And what is the direction
of the eigenvector of a hessian? ^utZDuOMF

the eigenvectors of the Hessian form the principal
axes of the paraboloid that acts as a local
approximation of the behavior, with the
eigenvalues being related to the relative axis lengths ^KtPOWupt

In conclusion a bad condition number
means that the curvature of the error function
in each dimension has high discrepancy
(one way larger than the other)
resulting taco shaped error functions that
bounce a lot when going towards the minima ^2eI63SkX

Why is this bad ^EGwBtFFt

One side here clearly converges faster than the other
and since it has an effect on the gradient that we choose to
update our parameters, and its much more steep
(Its eigenvalue is higher in the Hessian)
it will affect our gradient proportionally larger than
the other dimension that we also care about when
getting near the minima. This causes it to bounce a lot in directions
we dont want it to! (overshooting) ^GPdEgVSP

This effect is apparent for both first order and second order
methods of updating the gradient, but it is even more sensitive in 
second order derivative methods (Hessian) due to the matrix Multiplication
H * g practically amplifying the errors ^f8IXykpW

This bouncing direction is very sensitive to errors
when the large discrepancy (Aka poor condition number)
between the different eigen-basis of the hessian (Which are
just it eigenvectors used as its basis).
Our choice of gradient direction has projections along
each eigenvector, and depending on its eigenvalue the direction
will be influenced by one of the eigenvectors more than the other ^dAAstCiN

This is a similar effect to choosing a
high learning rate in SGD ^HAB4mVAV

We can notice this in Gradient descent
of the error function if we try to approximate
it through second order taylor series expansion ^D1gqcZwO

g marks the Gradient vector (First order)
H marks the second order derivative matrix
Epsilon is the learning rate ^NSuKI0nU

Gradient descent heads in the direction of the gradient with magnitude ^C5g4yr7T

norm of gradient
but opposite
direction ^bL14ySgP

quadratic form representation
of how that gradient vector
is affected by all the other dimensions
and their curvatures
(Sensitivity along different directions) ^Rlu5PKWs

naively we usually assume this is significant
but as we observed this is not necessarily true
depending on the conditioning of the Hessian
if the Hessian is well conditioned this term wont get affected
much by the discrepancy of its eigenvalues and thus will be
almost insignificant, but if its ill conditioned this will be taken
into consideration ^qr64a9nI

If the left term is more dominant, and our Hessian
is ill conditioned then we require a very small epsilon
to counteract the bouncing effect brought by the Hessian
WHICH slows down our training a lot in order to achieve
a stable result

on the other hand if our Hessian is conditioned well epsilon
can be larger because the denominator is smaller ^N0mJW5Tj

Rayleigh Quotient
which is a function of a matrix and a vector
The range of this quotient for any matrix 
is called the spectrum of this matrix
Analyzing this spectrum is important because we
want to understand the range of this quotient
for different values of the gradient ^kqVLWNYv

Analyzing
the learning rate ^xZHLjZUA

our gradient descent converges
if all our dimensions have the following
condition ^4FbLs6aD

What is the best learning rate we could pick
such that we converge to a solution? ^rsyvI3FM

Picking a learning rate that matches the smallest
1/alpha term such that it applies the condition alongside
that dimension and everything bigger than it
this results in 0.99 (best learning rate) scaled down
by 1/max alpha ^rgzvb5B0

using this we can deduce
the amount of time it takes us
to converge
which is equivalent to
the convergence of the dimensions with
the lowest curvature ^9grlC23d

quantifying the difficulty of optimization
is equivalent to the inverse of the speed
of convergence of our error function
(the lower the ratio the easier to optimize)
Introducing:
The condition number
 ^oy0uvdXX

This analysis is a bit naive because it assumes
that our parameters do not interact and thus
reducing this from a general case to a very specific
form of error functions ^Qdd2Hdcq

Lets generalize this
to every error function
Using taylor expansions
near some local minima
solution ^F6qGc4mi

overall error
function ^EvaThEmR

error of that
local minima
(How bad it is
in comparsion to
the global minima) ^lswDZ2a2

Often insignificant or
unnecessary for our
approximation ^8CD8ODII

the gradient
g ^B0Le3hvQ

Hessian matrix
H
of size
num of parameters ^PnsL0XPS

Hessian based local approximation of the error
aka
quadratic form representation
g^T H g
of how the gradient is
influenced by the curvature
or
the effect/sensitvity of an infinitely
small step in the direction of
the gradient ^9BVn7FFx

This is just the definition of
a derivative of a function
taking an infinitely small step in
x direction how will f(x) be
affected ^cB5MGj91

Lets diagonalize the
Hessian matrix for ease of
computation
 ^up3joeiZ

%%***>>>text element-link:[[Diagonalizing]]<<<***%%What is diagonalizing? ^0wrYuaVo

V is the eigenvector
matrix of the Hessian ^uCz9ZEaG

D is the diagonal
eigenvalue matrix
of the hessian ^lFxhXwjY

transposed eigenvector
matrix of the Hessian ^4gPymu7Q

~ ^z3jccqPw

~ ^Y4Sjp6rm

This has a very similar structure to what we anaylzed before


but as you can notice now that we analyze the projection of the
gradient onto our eigenvectors
AND
the eigenvalues are actually the "coefficients" alpha ^qtBCc841

projection of gradient
onto eigenvector of the
Hessian ^VU8EfBEg

In larger neural networks
computing the Hessian is quite a demanding task thus
we cannot always extract the condition number and optimize
accordingly! through the analysis we can take steps that help
shape and condition the error function ^CRwcDqgs

Optimizing the Condition Number ^lg10QQ73

1) Center and normalize the data
From linear models we can see ^k6p3xf8r

goes away in 2nd
derivative ^zgEAtMwK

The Hessian is influenced by the mean and covariance of the data
Thus if we can center our data (aka set it to 0) our condition number is lower
and if we normalize the data aka make the covariance closer to the identity, our
condition number is also lowered! ^nYsnZO8u

2) Use centered activations
The general formula for The hessian matrix is given by ^8yiUtWVz

derivative of the neural network
output w.r.t the pre-activation
of neuron k ^bf5WtazM

This is also dependent on the activations of each neuron
Meaning we should also normalize the output data of each neuron similar to tip 1.
This can actually be done through the activation function itself by choosing
a function that is centered and somewhat linear such that the outputs wont drift
away/explode/vanish if theyre skewed in a certain direction ^wzAHkOSk

not centered ^ZW2hTBMJ

centered ^JDGjKYwL

Skewed ^UxsRMkhK

The output will
not be centered ^rKJ9fjgs

3) Number of neurons
The number of neurons affects the variance of the neuron outputs
we want that variance to also equal 1 for an identity-like covariance output
Use similar number of neurons per layer determined by ^hBSwAnt0

We can justify this using the block-digonal Hessian made out of the hessians associated with each neuron
The eigenvalues of H are the eigenvalues of all the mini-Hessians
Reducing the condition number requires ensuring that each eigenvector is on a similar scale
i.e each block of mini hessian is on a similar scale as all the other ones
Remember the mini-Hessians are based off of the neurons connected to our Hessian's neuron
thus it depends on how many are connected to it.  ^1sBuCftA

4) Batch Normalization
Perform Batch normalization between each layer in order to ensure that
the data stays centered between layers in order to reduce the covariance matrix and thus
the Hessian.
This also helps reduce interactions between different parameters, allowing us to be closer to
the initial simplification of the error function that we analyzed ^7dwDeO4g

5) Connection skipping
Connection skipping is sometimes useful to reduce interaction between  parameters at
different layers, it also helps send the most important information towards the output in certain cases ^XaeVWBGG

How do we deal with poorly conditioned Error functions? ^h46NGruE

Despite all our effort to optimize the Hessian, it can still be poorly conditioned,
and since its computationally costly to compute everytime, we have developed ways that 
deal with poorly conditioned error functions more efficiently ^NuAEBhVO

Introducing the new 4-Wheel drive technology
hot on the market
guaranteed to get you laid ^VebfsNC9

Momentum ^fpEf4H1A

how beta males traverse
gradient descent ^zoH6EoLA

Calculate the gradient at each point and
use it to move to the next point
which causes bouncing in ill-conditioned
error functions ^hpm4bvvr

how Sigma males traverse
gradient descent ^QqJTx0dP

by taking into account a portion
of the previous gradient descent
we can simulate physical momentum
and traverse the error function as an accumlation
of previous gradients that all aim to go
towards the minimum to some extent ^qxGMGUs5

Strength of
momentum ^B2lNABon

Previous
gradient/momentum ^wyeO4oge

Current gradient ^H92EXTW3

And we update our parameters according to the momentum ^VmQ2TTGv

Using the closed form of a geometric series



We can derive that our effective learning rate
alongside the direction of the momentum is ^cED0bUlK

When the function is poorly conditioned
choose a momentum of 0.9 / 0.99 ^IRAU8BHE

Previously we discussed that we
cant use high learning rates with gradient descent
due to the issue of overshooting thus slowing down the
process, we can see here that momentum simulates
different learning rates in each direction! ^EffzcTW9

(Horizontal)
The direction thats causing
the most bounces will always
cancel each other out and
thus have low effective
"learning rate" which stops it
from oscillating ^n5LBKz6N

(Vertical)
Whereas the direction thats all
roughly aiming in the same direction
downwards will get stronger
and have an effective learning
rate ^gTY06DE0

Which roughly averages the last 10 gradients
and all the gradients past 10 decay too little
This is often enough and does not require bias
correction but if we choose different momentums
we do need to preform a bias correction ^ubFk6ymu

note that if we do
change the momentum we also
have to change the learning rate
to counteract the scaling ^owfh5xEw

Didnt get laid yet?
yucks youre really not good with girls huh?
okay lets try this ^aOKXXLIo

Data Redundancies ^wLooiro6

The error function can be decomposed as the sum of the errors
on individual datapoints, which even for different datapoints
will usually have very similar shape at the start ^0oQcQlwD

it is computationally inefficient to compute the gradient of every datapoint
we have during each iteration, why not perform it only on a batch of data?
This algorithm of taking minibatches to perform on each step is called
Stoachstic Gradient descent
such that its computation is O(K) which is way smaller than O(N)
and we reach a decent estimator of the proper gradient descent ^qH2rHDyy

Keep in mind, due to random sampling, SGD may not converge because it will
keep bouncing in random directions driven by those samples ^sbGXICFM

Learning rate decay ^ZMMuoOD8

We can combat this by using


We decay our learning rate the further we are in the process in order to put
less importance on later samples and allow their effect to be less significant 
the closer we are to convergence ^lcmS4d0X

decays to 0
aka
converging to 0 the
further we go on ^GZcrAlOI

cannot converge to a
constant otherwise it
decays too quickly
and becomes irrelevant
to train past a certain 
point ^iiPQGnje

How does this
compare to GD? ^0jIkZZZO

Phase 2 is often irrelevant because we need
to stop the model before it starts
overfitting WHICH happens in phase 2 ^Zy9D4rby

Needs the right balance of batch-Size ^kce1tyjl

can escape local minima
due to random noise
is also better at generalizing
due to mini-batches ^5Owl2mrd

How Efficient is our model? ^LS2qAOdS

How much time does it take to produce on forward/backward pass? ^7630unSI

The number of neurons should not be chosen larger than necessary!
it will lead to very many parameters and very slow forward pass. ^Zh6TG3UU

only relevant computations are computed, irrelevant features are not extracted and stored
in neurons  ^JmFGD2h3

Does our model require long range interaction or not? ^wtiUV9F2

some models emphasize the connectivity between local features, others require
relations between features very far apart, depending on the task we need
to design the neural network with Global or Local connectivity
Local connectivity is much computationally cheaper per forward pass ^lr1XhXgw

less connections ^s5xKMdEd

Do you have bottlenecks? ^yJU9aWVn

Sometimes are main computational issue is that we dont utilize our
hardware capabilities as we should, this can come from a plethora
of reasons. 
One of which is that we have a bottleneck of information in our layers
no Layer should be significantly dominant in terms of computational time  ^3HPHqRBw

number of connections
is never too high at any layer ^zqRdOT0t

Spatial information is converted
into semantic information
more on this in CNNs ^tgumxxOa

Are you utilizing Parallelization to compute Matrix multiplication? ^EwpUXWgn

Computing the forward and backward pass for millions of variables is
costly considering that we have high dimensionality
we can abuse parallelization technology to compute the values Layer
by layer instead of neuron by neuron ^Xll4LHmC

typically in short, we need to choose different batchsizes depending
on many choices, some of the more important ones being
whether our machine is actually good enough to handle computation on
large batches.
Another factor in SGD during Phase1 we usually use smaller
batches due to corrolation, whereas in Phase2 we are allowed
to go bigger as the corrolation falls off.
Other factors: ^la25nI5Z

In order for the training procedure to match the hardware specifications
(e.g. CPU cache, GPU block size) optimally, neural network
computations (e.g. batch computations) must be decomposed into
blocks of appropriate size ^7nSTKz38

Can you distribute the data? ^2Y5niKbX

Model Parallelism ^i7XjhfeP

v.s ^Rzj7Xh32

Data Parallelism ^6jRGghwD

Produce replicas of the models

Shard our data into different sections

Give each model a shard of our data
and let it produce an output

combine parameters in backprop step ^4eVP5gIA

Shards the model into different layers

each layer runs on a machine on its own

data is sent to each machine in order to be processed 
potentially in parallel ^mOVbrEHe

ಠ_ಠ ^8DtmfcLE


# Embedded files
08c8a3d0a4d8e9cc62eb8d486378446243f9712d: $$\frac{1}{2} \epsilon^2 g^T H g - \epsilon g^T g$$
5e54cf31f3eb995cd97dd7e2439897fb9d17a83a: $$\frac{1}{2} \epsilon \frac{g^T H g }{g^T g}$$
0e1d84d340af613e2599b0038ca32500f21b70ca: $$\frac{\alpha_{max}}{\alpha_{min}}$$
8fd0bc8001ecb8b65b5bfd2f5361af66ee853620: $$\mathcal{E^~}(\theta) = \frac{1}{2} g^T V D V^T g$$
f5bc95d8509fd365e3d0f80e2999092a40c318d8: $$\mathcal{E}(\theta) = \frac{1}{2} D (g^TV)^2$$
d03726ba3d2fa5d47d1ea179c11b3c80c86c4670: $$H = \frac{\partial^2 \mathcal{E}}{\partial W^2} = \frac{\partial y}{\partial W}^T \frac{\partial^2\mathcal{E}}{\partial y^2} \frac{\partial y}{\partial W} + \frac{\partial \mathcal{E}}{\partial y} \frac{\partial^2 y}{\partial W^2} $$
bcb30d90e97f40e23a15510eeda5b98cc6dbe2de: $$\sigma^2 = \frac{1}{\text{number of neurons}}$$
5a8464103ff5489002b02542a91125adb053b4a9: $$\gamma_{eff} = \gamma \frac{1}{1-\mu}$$
30560d0785affa6d6c63d16416affa6347083048: $$1 - \mu^t$$
d9a795d78b8c71ae8160b1709ae81e8323c1611a: [[Pasted Image 20240104142347_383.png]]
62d8bf6f879f4789244b1fb798286e410e846e27: [[Pasted Image 20240104142428_422.png]]
c63001b5d2ff3300e9748b29d195e4d88db7c43e: [[Pasted Image 20240104142543_426.png]]
5750d24381764a7d4b09d0d18d1b07d72090fa70: [[Pasted Image 20240104142559_428.png]]
bbb282b10e67cf94cfc670720cd35b488f0e4ad0: [[Pasted Image 20240104142716_434.png]]
0beafb695d217a5d9e2fd2cffa30b99403229b2f: [[Pasted Image 20240104142830_447.png]]
09f088956ea14fc1a6899e2dd4b958d9a8f34123: [[Pasted Image 20240104143537_548.png]]
98ec17355e0fa88c5b7bdcbf833d0c53c82bbee4: [[Pasted Image 20240104144053_605.png]]
bae943263f3d862a6accb67c7a16bd01ae50fda3: [[Pasted Image 20240104144108_619.png]]
713b6bfcfd5dfa90a5f41f09d5e9534d5118a896: [[Pasted Image 20240104144123_621.png]]
e95fbe89d4bcdfbfe037122e6b58b82ecafebfcc: [[Pasted Image 20240104203622_814.png]]
341f497e30247884b60ac299ee2b1acfa7418d56: [[Pasted Image 20240104203652_826.png]]
47f1a996dc9c2a16ea211cdfb258cd498cd35504: [[Pasted Image 20240104203707_841.png]]
e6cb1c94291a121e039ecd09d75169e8ba0778d0: [[Pasted Image 20240104203955_896.png]]
918a86f852203dcdb569c03876bff0cc82574a15: [[Pasted Image 20240104204347_987.png]]
2df0a63669c557dc630db3b7d2f0a2c010c64523: [[Pasted Image 20240104204432_997.png]]
e28b6ceecc54986c0a888598041d6b049999fdcf: [[Pasted Image 20240104205224_051.png]]
94997c5e230cfe92fc6e979f3019ca93db05c68c: [[Pasted Image 20240104205309_066.png]]
eb052215b4350d59b1ddf009875e5ea5b4f907ad: [[Pasted Image 20240104205524_105.png]]
a34acdc6c5d0182da2e958532d8cd58bd4c8b66b: [[Pasted Image 20240105152522_958.png]]
8f79f3410a3574336075e97a0a30eee5df0b32f2: [[Pasted Image 20240105152522_975.png]]
3561f7eef12e4a998123166377e776af200c4a1f: [[Pasted Image 20240105152754_012.png]]
92919d120a94f04c528e5f0e561625edb5cbdb1e: [[Pasted Image 20240105152918_061.png]]
9ca7b64c74f622c1fd2bc3e8b5f39fc8bbb76e46: [[Pasted Image 20240105153635_160.png]]
7dd6ceee7adec4ef05286c1dfb841de9eb774b2a: [[Pasted Image 20240105160629_518.png]]
1eeea0f618cae4cb003d8efd81b3325ad6674625: [[Pasted Image 20240105161211_579.png]]
e0ba209b9aa087be8fec1e94bc4e0f557a89d600: [[Pasted Image 20240105162527_697.png]]
71f36b5e0b7710cf10a5898e1a0b3ad30d163189: [[Pasted Image 20240105162944_739.png]]
d4a1430361e8a8ad2a0713aef89ef4ec070a0494: [[Pasted Image 20240105164115_848.png]]
c69aed6c37f4843176244af593dedd57176f935e: [[Pasted Image 20240105164646_927.png]]
371e48ad858d5cb7613cfe638d643a8f74a8786d: [[Pasted Image 20240105164704_940.png]]
d5cc3b5b5e6129ecf0ecb7cca2976eddc5174ede: [[Pasted Image 20240105165818_079.png]]
e29cd722eb6e44234c9566c65a16b90fca2e8904: [[Pasted Image 20240105173633_396.png]]
474041720ef7385b2f903dde38e95d87a622fcfa: [[Pasted Image 20240105173800_449.png]]
e92ed28f3ada06ba772f76aab9809b759b842261: [[Pasted Image 20240105173941_501.png]]
bb4cfc4476c711b6420294d3015b7f0ffc524728: [[Pasted Image 20240105174121_521.png]]
16da4e30552b76adc63917e23ba5f29039d79db8: [[Pasted Image 20240105175210_581.png]]
b6c25ba768c52f01cca3e86adbcdeff79dee4b36: [[Pasted Image 20240105181520_789.png]]
357af37ec97252c19d63fb7bbaa88a986dc25ce8: [[Pasted Image 20240105182422_878.png]]
29f2140a7df14f5bdd98f096a659bf573a7e0252: [[Pasted Image 20240105183839_030.png]]
f5b6e0de9485576adf80e8312fafb25ecd45a5c2: [[Pasted Image 20240105184141_065.png]]
f76df9d0e64ec0a880b5a0feebe10c023c1dfe4c: [[Pasted Image 20240105184439_102.png]]
503a917a7ec286e219737a7db980202952ab36f0: [[Pasted Image 20240105185018_176.png]]
cea4b5a1c2b559ae8313b3fc6329b2cd35bb2fc3: [[Pasted Image 20240105185239_253.png]]
e754c4137ffdae003de99a1bdffb5fc58fbb5b1d: [[Pasted Image 20240105185256_257.png]]
14f882e0140b160821097aaf633d15989774cf70: [[Pasted Image 20240105185615_296.png]]
b9f537f8ae0bb701d95a337ea4cf3486727329b6: [[Pasted Image 20240105185959_414.png]]
fb9cd8c89f727272be05782754b4d1add14994c4: [[Pasted Image 20240105190453_457.png]]
6a8cdd190269c13de488c6728ff705d4e2f70050: [[Pasted Image 20240115192153_007.png]]
4e34ee84c26c6895525f8745ad511eeadc81497d: [[Pasted Image 20240115192324_030.png]]
12149e2cb3ba7cb26319f8843be1412b0263e11f: [[Pasted Image 20240115192710_055.png]]
5acf030cdae06cf317d2a8bef1d909190e446e2e: [[Pasted Image 20240115192842_086.png]]

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
			"version": 692,
			"versionNonce": 1472689425,
			"isDeleted": false,
			"id": "2r1T6Jdc3SgkEd6WvebHY",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3206.862936313602,
			"y": 391.2587147490956,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 167.29938149756575,
			"height": 158.43818544366928,
			"seed": 932150233,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "12149e2cb3ba7cb26319f8843be1412b0263e11f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 72,
			"versionNonce": 40034431,
			"isDeleted": false,
			"id": "jMsCah7l5p0RDVOxbgLuC",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2626.5220904243693,
			"y": 1437.7159340004325,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 210,
			"height": 282,
			"seed": 511097497,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5acf030cdae06cf317d2a8bef1d909190e446e2e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 149,
			"versionNonce": 1914219249,
			"isDeleted": false,
			"id": "PvQC6kf1R2_hZu2HIQyrP",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 122.69754194649397,
			"y": 1715.50659223821,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 160,
			"height": 205,
			"seed": 833197017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6a8cdd190269c13de488c6728ff705d4e2f70050",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 81,
			"versionNonce": 1498445983,
			"isDeleted": false,
			"id": "abqoTWocC8pdFOtgthOJP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2858.9875447419554,
			"y": 2382.0062047962892,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 238,
			"height": 149,
			"seed": 967873657,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "29f2140a7df14f5bdd98f096a659bf573a7e0252",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 198,
			"versionNonce": 2089297105,
			"isDeleted": false,
			"id": "Ex-g_i72nGrqNUrhOSmw3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2752.2945087174244,
			"y": 1710.5395388112495,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 440.8117913832198,
			"height": 287.1886541586644,
			"seed": 2018394103,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "357af37ec97252c19d63fb7bbaa88a986dc25ce8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 78,
			"versionNonce": 185994431,
			"isDeleted": false,
			"id": "dVNekMqjVf5hY6BiaFvi_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3615.3679343712483,
			"y": 1397.0961288347087,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 46,
			"height": 44,
			"seed": 1297040441,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b6c25ba768c52f01cca3e86adbcdeff79dee4b36",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 335,
			"versionNonce": 1655530161,
			"isDeleted": false,
			"id": "lCKr4O_-G1rduU7cpVx7i",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.18196468595918613,
			"x": 4069.993181773668,
			"y": 1227.90463536582,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 213,
			"height": 256,
			"seed": 1859825207,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e29cd722eb6e44234c9566c65a16b90fca2e8904",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 115,
			"versionNonce": 1934892255,
			"isDeleted": false,
			"id": "YTFarkfPs0qlwN28jT50E",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3533.890159798526,
			"y": 1031.2577448034176,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 147,
			"height": 49,
			"seed": 581384633,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "16da4e30552b76adc63917e23ba5f29039d79db8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 101,
			"versionNonce": 825222289,
			"isDeleted": false,
			"id": "kQVlZFyKFVQOp3UbD9Og2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2841.295464813838,
			"y": 1255.868643181675,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 245,
			"height": 70,
			"seed": 1150748599,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bb4cfc4476c711b6420294d3015b7f0ffc524728",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 117,
			"versionNonce": 630925567,
			"isDeleted": false,
			"id": "O9TXJJz8Hbr8KGbgs20Ge",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2750.686020852452,
			"y": 987.5285101218046,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 419.2042047406434,
			"height": 76.62872559775202,
			"seed": 374938905,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e92ed28f3ada06ba772f76aab9809b759b842261",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 180,
			"versionNonce": 1942432369,
			"isDeleted": false,
			"id": "V_8DlO9k6KO0etGZdStkr",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.27475042812318584,
			"x": 3048.6727873273453,
			"y": 598.8611800751343,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 225,
			"height": 245,
			"seed": 40658361,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "474041720ef7385b2f903dde38e95d87a622fcfa",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 259,
			"versionNonce": 1869328671,
			"isDeleted": false,
			"id": "fBAuIcbS4DhyH1HKJ3Fi_",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.18196468595918613,
			"x": 2672.4592217907616,
			"y": 590.9482792114075,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 213,
			"height": 256,
			"seed": 582600823,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e29cd722eb6e44234c9566c65a16b90fca2e8904",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 344,
			"versionNonce": 1396356177,
			"isDeleted": false,
			"id": "qJavEuL1hG5IT_IRbzHCl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2580.8571467989887,
			"y": 390.27876757558624,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 800.7816807019846,
			"height": 967.3203973185093,
			"seed": 1909933017,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "IrDTOD8wBsKVbTBn1kPgp",
					"type": "arrow"
				}
			],
			"updated": 1706890392122,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 810,
			"versionNonce": 439760191,
			"isDeleted": false,
			"id": "7EYuabDuT0EuYrYIL_tCL",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -741.7327176289975,
			"y": 2947.7039953016047,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1200.0000000000005,
			"height": 2309.794337392822,
			"seed": 57292663,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "2XMRIeXKzFMZqpsc_q62P",
					"type": "arrow"
				}
			],
			"updated": 1706890392122,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 171,
			"versionNonce": 1935802929,
			"isDeleted": false,
			"id": "HKirUaFjsRO8Ibiw1PFUB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1789.8822283343147,
			"y": 1899.236240046337,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 687,
			"height": 246,
			"seed": 1714724669,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "713b6bfcfd5dfa90a5f41f09d5e9534d5118a896",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 205,
			"versionNonce": 1834693983,
			"isDeleted": false,
			"id": "7QS8YDMJzSox2RazkVJIe",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2953.1294667658613,
			"y": 1844.219308631686,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 924.4444444444438,
			"height": 1655.5555555555557,
			"seed": 1680767411,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "oW1eaoEX4jq92OhXp_z10",
					"type": "arrow"
				}
			],
			"updated": 1706890392122,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 580,
			"versionNonce": 287609873,
			"isDeleted": false,
			"id": "U-FDqyWjeMTTpnvCsH5ET",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1452.8888770275837,
			"y": 1302.2787007425648,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 270,
			"height": 257,
			"seed": 1366359059,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bbb282b10e67cf94cfc670720cd35b488f0e4ad0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 212,
			"versionNonce": 1881878911,
			"isDeleted": false,
			"id": "RrQ2Ux715JX_y6AizM1DT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1102.4515498197184,
			"y": -791.4863376780555,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 801.1253184378087,
			"height": 392.940959572033,
			"seed": 526525875,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "kI8DN9xe"
				}
			],
			"updated": 1706890392122,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 233,
			"versionNonce": 1618602481,
			"isDeleted": false,
			"id": "kI8DN9xe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1322.946671082788,
			"y": -633.0499646860624,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 359.6539306640625,
			"height": 76.2169964687133,
			"seed": 276367475,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"fontSize": 60.97359717497064,
			"fontFamily": 1,
			"text": "Optimization",
			"rawText": "Optimization",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "RrQ2Ux715JX_y6AizM1DT",
			"originalText": "Optimization",
			"lineHeight": 1.25,
			"baseline": 53
		},
		{
			"type": "text",
			"version": 248,
			"versionNonce": 1810278815,
			"isDeleted": false,
			"id": "9F3v6Zuv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1171.893702157879,
			"y": -373.13971261645133,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 693.5526123046875,
			"height": 59.279886142332565,
			"seed": 1498116125,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"fontSize": 47.42390891386605,
			"fontFamily": 1,
			"text": "Motivation behind optimization",
			"rawText": "Motivation behind optimization",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Motivation behind optimization",
			"lineHeight": 1.25,
			"baseline": 41
		},
		{
			"type": "text",
			"version": 1045,
			"versionNonce": 711558097,
			"isDeleted": false,
			"id": "H0oWks4G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 782.1200256347647,
			"y": -307.0849823435665,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1537.4920654296875,
			"height": 381.0849823435665,
			"seed": 996384531,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"fontSize": 33.874220652761466,
			"fontFamily": 1,
			"text": "Alongside the building process of our neural network and having devised an algorithm\nin order to train it, comes a bunch of questions left unanswered, including\n\n\"How do we know that we are not stuck at a saddle point/local minima/plateu?\"\n\"How fast does this converge and are there ways to improve upon it?\"\n\"what are the best initializations that we can provide?\"\n\nand although some of those questions are only answered through heuristics and bullshit\nwith the power of love and friendship, we are going to try to reason through most of them!",
			"rawText": "Alongside the building process of our neural network and having devised an algorithm\nin order to train it, comes a bunch of questions left unanswered, including\n\n\"How do we know that we are not stuck at a saddle point/local minima/plateu?\"\n\"How fast does this converge and are there ways to improve upon it?\"\n\"what are the best initializations that we can provide?\"\n\nand although some of those questions are only answered through heuristics and bullshit\nwith the power of love and friendship, we are going to try to reason through most of them!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Alongside the building process of our neural network and having devised an algorithm\nin order to train it, comes a bunch of questions left unanswered, including\n\n\"How do we know that we are not stuck at a saddle point/local minima/plateu?\"\n\"How fast does this converge and are there ways to improve upon it?\"\n\"what are the best initializations that we can provide?\"\n\nand although some of those questions are only answered through heuristics and bullshit\nwith the power of love and friendship, we are going to try to reason through most of them!",
			"lineHeight": 1.25,
			"baseline": 368
		},
		{
			"type": "text",
			"version": 170,
			"versionNonce": 767434175,
			"isDeleted": false,
			"id": "VuE1lGh5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1725.7854580696244,
			"y": 319.5203672446827,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 536.4542236328125,
			"height": 35,
			"seed": 523492125,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "The great escape: Local minima edition",
			"rawText": "The great escape: Local minima edition",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The great escape: Local minima edition",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 546,
			"versionNonce": 722133425,
			"isDeleted": false,
			"id": "fUuEAvUY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1921.337941255078,
			"y": 366.96690727263734,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 917.239013671875,
			"height": 100,
			"seed": 1783598973,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Previously on Dragon Ball Z, we have proven that the perceptron algorithm is equivalent\nto the gradient descent of such function, thus guaranteeing us that we are always heading\ntowards a minimum of sorts.\nand the function given by the error of a perceptron is a convex function",
			"rawText": "Previously on Dragon Ball Z, we have proven that the perceptron algorithm is equivalent\nto the gradient descent of such function, thus guaranteeing us that we are always heading\ntowards a minimum of sorts.\nand the function given by the error of a perceptron is a convex function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Previously on Dragon Ball Z, we have proven that the perceptron algorithm is equivalent\nto the gradient descent of such function, thus guaranteeing us that we are always heading\ntowards a minimum of sorts.\nand the function given by the error of a perceptron is a convex function",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 179,
			"versionNonce": 147983839,
			"isDeleted": false,
			"id": "M_90VpGC8rpggVE_nngBP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1626.1131712612455,
			"y": 480.8910684903456,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 341.52631578947376,
			"height": 67.47057562439706,
			"seed": 1972132723,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d9a795d78b8c71ae8160b1709ae81e8323c1611a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 182,
			"versionNonce": 797279121,
			"isDeleted": false,
			"id": "JQL3JJRewuAeMPoASBrBR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1598.4255759792309,
			"y": 553.1434808215231,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 266,
			"height": 245,
			"seed": 820244061,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "p5cL556bEJzykX8zeVC5q",
					"type": "arrow"
				}
			],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "62d8bf6f879f4789244b1fb798286e410e846e27",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 413,
			"versionNonce": 405993983,
			"isDeleted": false,
			"id": "p5cL556bEJzykX8zeVC5q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1469.5174980619126,
			"y": 816.7596211290451,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 3.336706131601204,
			"height": 153.48848205365346,
			"seed": 423446643,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JQL3JJRewuAeMPoASBrBR",
				"focus": 0.05277534750595071,
				"gap": 18.61614030752196
			},
			"endBinding": {
				"elementId": "ZZK85fJqwH9YDsIIYZ_Mx",
				"focus": 0.009372752937627038,
				"gap": 22.539755959173988
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
					3.336706131601204,
					153.48848205365346
				]
			]
		},
		{
			"type": "text",
			"version": 290,
			"versionNonce": 1947265393,
			"isDeleted": false,
			"id": "A9Q3BYOB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1463.0848492089365,
			"y": 839.8309164098504,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 298.56060791015625,
			"height": 60,
			"seed": 568650525,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Now Lets take a more slightly more\ncomplicated neural network and see if\nthis applies",
			"rawText": "Now Lets take a more slightly more\ncomplicated neural network and see if\nthis applies",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Now Lets take a more slightly more\ncomplicated neural network and see if\nthis applies",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 165,
			"versionNonce": 1088512543,
			"isDeleted": false,
			"id": "ZZK85fJqwH9YDsIIYZ_Mx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1652.142006785777,
			"y": 992.7878591418724,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 372,
			"height": 120,
			"seed": 1388752221,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "p5cL556bEJzykX8zeVC5q",
					"type": "arrow"
				}
			],
			"updated": 1706890392122,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c63001b5d2ff3300e9748b29d195e4d88db7c43e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 205,
			"versionNonce": 1106547537,
			"isDeleted": false,
			"id": "izygGd0u",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1622.1823510240583,
			"y": 1117.972068888873,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 312.0806884765625,
			"height": 20,
			"seed": 200225779,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Such that its error function is given by",
			"rawText": "Such that its error function is given by",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Such that its error function is given by",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 222,
			"versionNonce": 1942865471,
			"isDeleted": false,
			"id": "Gf-6z8uvL1OeQSql-f_6d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1674.631193572351,
			"y": 1151.6218341191807,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 426.80065175420236,
			"height": 54.38988815458351,
			"seed": 1417730131,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5750d24381764a7d4b09d0d18d1b07d72090fa70",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 171,
			"versionNonce": 1300758833,
			"isDeleted": false,
			"id": "KEobDEo5DblzTkPxfoIrf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1234.8720023409385,
			"y": 1182.263344255778,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 108.04505999160415,
			"height": 72.32768478776802,
			"seed": 1684563,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					74.11355354795978,
					-24.10922826258934
				],
				[
					108.04505999160415,
					-72.32768478776802
				]
			]
		},
		{
			"type": "text",
			"version": 186,
			"versionNonce": 854817142,
			"isDeleted": false,
			"id": "c5fbq0Ub",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1146.6931590685897,
			"y": 1066.181874843311,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 96.88023376464844,
			"height": 40,
			"seed": 1039211037,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707763125219,
			"link": "[[Normalization]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What is this\nunholy norm?",
			"rawText": "What is this\nunholy norm?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is this\nunholy norm?",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 563,
			"versionNonce": 1412608785,
			"isDeleted": false,
			"id": "ed144UqR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1665.3504991208597,
			"y": 1218.4527224482665,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 450.06494140625,
			"height": 80,
			"seed": 1938000893,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "While we can still perform Gradient descent this function\nis clearly no longer convex, its much more complicated\nand consists of a saddle point and two minimas\nthus not being a convex function",
			"rawText": "While we can still perform Gradient descent this function\nis clearly no longer convex, its much more complicated\nand consists of a saddle point and two minimas\nthus not being a convex function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "While we can still perform Gradient descent this function\nis clearly no longer convex, its much more complicated\nand consists of a saddle point and two minimas\nthus not being a convex function",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "line",
			"version": 651,
			"versionNonce": 1137869439,
			"isDeleted": false,
			"id": "F7HGj1FkaoEWHHl4Yf6PT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1712.583004673123,
			"y": 1400.5242511961787,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 229.76552758590606,
			"height": 25.811163550541096,
			"seed": 1911491709,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-123.66723096757914,
					8.541220838505751
				],
				[
					-229.76552758590606,
					-17.269942712035345
				]
			]
		},
		{
			"type": "text",
			"version": 306,
			"versionNonce": 2053908721,
			"isDeleted": false,
			"id": "FRLl4Pfm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2253.5958492586833,
			"y": 1329.0473063507052,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 191.85641479492188,
			"height": 20,
			"seed": 279554525,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What is a saddle Point?",
			"rawText": "What is a saddle Point?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is a saddle Point?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 330,
			"versionNonce": 1350294175,
			"isDeleted": false,
			"id": "bKDQwp2d",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2350.2419595009223,
			"y": 1364.370539115622,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 383.23284912109375,
			"height": 60,
			"seed": 177388669,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "A saddle point is a point in a function\nthat looks like a global minimum from certain\nangles but is a maximum point from other angles",
			"rawText": "A saddle point is a point in a function\nthat looks like a global minimum from certain\nangles but is a maximum point from other angles",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A saddle point is a point in a function\nthat looks like a global minimum from certain\nangles but is a maximum point from other angles",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 299,
			"versionNonce": 1773920977,
			"isDeleted": false,
			"id": "80A-nAteXgpdhmNeAX4YM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2360.53097379915,
			"y": 1410.3851884564424,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 396.14176949407835,
			"height": 309.3206983466262,
			"seed": 1873358067,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "09f088956ea14fc1a6899e2dd4b958d9a8f34123",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 528,
			"versionNonce": 176500415,
			"isDeleted": false,
			"id": "FHWVNCec0tOGte6NE4O6B",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2246.725208873341,
			"y": 1472.7726905792151,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 179.3434730492054,
			"height": 90.53952752322812,
			"seed": 1371094835,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.388646320043335,
					13.884655978003138
				],
				[
					32.68679428154883,
					48.59629592301076
				],
				[
					65.3735885630972,
					78.679717208684
				],
				[
					90.53952752322766,
					88.80394552597772
				],
				[
					110.4987204916074,
					90.53952752322812
				],
				[
					145.7888877690316,
					76.07634421280841
				],
				[
					165.4588170712027,
					56.98494224305409
				],
				[
					179.3434730492054,
					40.207649602967194
				]
			]
		},
		{
			"type": "line",
			"version": 387,
			"versionNonce": 783900849,
			"isDeleted": false,
			"id": "ocYPNAmZ2MpOX54OLR8U6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2208.8316686000417,
			"y": 1666.0008196064239,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 64.79506123068086,
			"height": 108.76313849435701,
			"seed": 174808275,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					10.70275564971098,
					-34.42237627879899
				],
				[
					30.372684951881638,
					-78.96898087489217
				],
				[
					52.067459917511314,
					-105.00271083364782
				],
				[
					64.79506123068086,
					-108.76313849435701
				]
			]
		},
		{
			"type": "freedraw",
			"version": 244,
			"versionNonce": 1016004319,
			"isDeleted": false,
			"id": "oCoXfEZhmaslIE7yLdUmu",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2155.762419706295,
			"y": 1561.685974697718,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#e03131",
			"width": 5.793906569187584,
			"height": 4.138504692276683,
			"seed": 687435699,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.413850469227782,
					0
				],
				[
					-0.413850469227782,
					-0.413850469227782
				],
				[
					-0.413850469227782,
					-0.8277009384553367
				],
				[
					0,
					-0.8277009384553367
				],
				[
					0,
					-0.413850469227782
				],
				[
					-0.413850469227782,
					-0.413850469227782
				],
				[
					-0.827700938455564,
					-0.413850469227782
				],
				[
					-0.827700938455564,
					-0.8277009384553367
				],
				[
					-0.827700938455564,
					-1.2415514076831187
				],
				[
					-0.413850469227782,
					-1.6554018769106733
				],
				[
					-0.413850469227782,
					-1.2415514076831187
				],
				[
					-0.413850469227782,
					-0.8277009384553367
				],
				[
					-0.413850469227782,
					-0.413850469227782
				],
				[
					-0.413850469227782,
					0
				],
				[
					-0.413850469227782,
					0.41385046922755464
				],
				[
					-1.2415514076828913,
					0.41385046922755464
				],
				[
					-1.6554018769106733,
					0.41385046922755464
				],
				[
					-2.0692523461384553,
					0.41385046922755464
				],
				[
					-2.0692523461384553,
					0
				],
				[
					-2.4831028153662373,
					-0.413850469227782
				],
				[
					-2.4831028153662373,
					-0.8277009384553367
				],
				[
					-2.4831028153662373,
					-1.2415514076831187
				],
				[
					-2.4831028153662373,
					-1.6554018769106733
				],
				[
					-2.0692523461384553,
					-1.6554018769106733
				],
				[
					-1.2415514076828913,
					-2.0692523461384553
				],
				[
					-0.827700938455564,
					-2.0692523461384553
				],
				[
					-0.413850469227782,
					-2.0692523461384553
				],
				[
					0,
					-2.0692523461384553
				],
				[
					0,
					-1.6554018769106733
				],
				[
					0.413850469227782,
					-1.6554018769106733
				],
				[
					0.413850469227782,
					-1.2415514076831187
				],
				[
					0.413850469227782,
					-0.413850469227782
				],
				[
					0,
					0
				],
				[
					0,
					0.41385046922755464
				],
				[
					-0.413850469227782,
					0.41385046922755464
				],
				[
					-0.827700938455564,
					0.41385046922755464
				],
				[
					-0.827700938455564,
					0
				],
				[
					-1.2415514076828913,
					-0.413850469227782
				],
				[
					-1.2415514076828913,
					-1.2415514076831187
				],
				[
					-1.6554018769106733,
					-1.2415514076831187
				],
				[
					-1.6554018769106733,
					-1.6554018769106733
				],
				[
					-0.827700938455564,
					-2.0692523461384553
				],
				[
					-0.413850469227782,
					-2.0692523461384553
				],
				[
					0.413850469227782,
					-2.0692523461384553
				],
				[
					1.2415514076828913,
					-1.6554018769106733
				],
				[
					1.6554018769106733,
					-1.6554018769106733
				],
				[
					2.0692523461380006,
					-1.2415514076831187
				],
				[
					2.4831028153657826,
					-0.8277009384553367
				],
				[
					2.4831028153657826,
					-0.413850469227782
				],
				[
					2.8969532845935646,
					-0.413850469227782
				],
				[
					2.8969532845935646,
					0
				],
				[
					3.3108037538213466,
					0.41385046922755464
				],
				[
					3.3108037538213466,
					0.8277009384551093
				],
				[
					3.3108037538213466,
					1.2415514076828913
				],
				[
					3.3108037538213466,
					1.6554018769106733
				],
				[
					2.8969532845935646,
					1.6554018769106733
				],
				[
					2.4831028153657826,
					2.069252346138228
				],
				[
					2.0692523461380006,
					2.069252346138228
				],
				[
					1.6554018769106733,
					2.069252346138228
				],
				[
					1.2415514076828913,
					2.069252346138228
				],
				[
					0.8277009384551093,
					2.069252346138228
				],
				[
					0.8277009384551093,
					1.6554018769106733
				],
				[
					0,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "image",
			"version": 524,
			"versionNonce": 1460413073,
			"isDeleted": false,
			"id": "zJBJfn4_M52G5zS1Y4FSY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1733.6867140168729,
			"y": 1338.416176281638,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 318.2617905393668,
			"height": 145.35332857966753,
			"seed": 233387197,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VmS-T8oufQSn9RqKMeWBq",
					"type": "arrow"
				}
			],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0beafb695d217a5d9e2fd2cffa30b99403229b2f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 280,
			"versionNonce": 153733887,
			"isDeleted": false,
			"id": "zuw0II8M",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2019.593123015782,
			"y": 2012.2148966836182,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 242.7685089111328,
			"height": 20,
			"seed": 516671005,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Well shit then, what do we do?",
			"rawText": "Well shit then, what do we do?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Well shit then, what do we do?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 366,
			"versionNonce": 1332455537,
			"isDeleted": false,
			"id": "VmS-T8oufQSn9RqKMeWBq",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1449.6793020193961,
			"y": 1511.8660610911147,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 3.986231841572817,
			"height": 150.1480660325792,
			"seed": 2132712349,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zJBJfn4_M52G5zS1Y4FSY",
				"focus": -0.7587287044494452,
				"gap": 28.096556229809266
			},
			"endBinding": {
				"elementId": "-Cf_QoSTSxiqG6QdBF9NO",
				"focus": 0.0006914423209134201,
				"gap": 12.40283857612053
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
					3.986231841572817,
					150.1480660325792
				]
			]
		},
		{
			"type": "text",
			"version": 211,
			"versionNonce": 1825968927,
			"isDeleted": false,
			"id": "arYDH0ZC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1806.0308316904425,
			"y": 1554.923527627394,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 341.93670654296875,
			"height": 40,
			"seed": 601991709,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This can also be observed from nonlinear\nactivation functions applied to the neurons",
			"rawText": "This can also be observed from nonlinear\nactivation functions applied to the neurons",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This can also be observed from nonlinear\nactivation functions applied to the neurons",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 141,
			"versionNonce": 27226705,
			"isDeleted": false,
			"id": "-Cf_QoSTSxiqG6QdBF9NO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1620.956953139204,
			"y": 1674.4169656998145,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 355.00000000000006,
			"height": 153,
			"seed": 188029555,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VmS-T8oufQSn9RqKMeWBq",
					"type": "arrow"
				}
			],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "98ec17355e0fa88c5b7bdcbf833d0c53c82bbee4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 126,
			"versionNonce": 284479,
			"isDeleted": false,
			"id": "7wz1LjEnRHSACjOMhsDNF",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1818.9640975233137,
			"y": 1817.8087419128008,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 732,
			"height": 90,
			"seed": 130383805,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bae943263f3d862a6accb67c7a16bd01ae50fda3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 375,
			"versionNonce": 847183921,
			"isDeleted": false,
			"id": "n8lLcjXp",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1811.4178872616058,
			"y": 2157.6886027214805,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 660.46533203125,
			"height": 60,
			"seed": 713674099,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Not only does this result in many minimas, we also get plateaus where our gradient\nwill be almost 0, resulting in barely in movement in gradient descent which gets us\nstuck on minimizing the error",
			"rawText": "Not only does this result in many minimas, we also get plateaus where our gradient\nwill be almost 0, resulting in barely in movement in gradient descent which gets us\nstuck on minimizing the error",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Not only does this result in many minimas, we also get plateaus where our gradient\nwill be almost 0, resulting in barely in movement in gradient descent which gets us\nstuck on minimizing the error",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 425,
			"versionNonce": 2031425375,
			"isDeleted": false,
			"id": "Q593qS24",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2751.2644402362457,
			"y": 1860.510199822367,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 502.2940979003906,
			"height": 70,
			"seed": 1891114099,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Lets start with some practical\nrecommendations based on Heuristics",
			"rawText": "Lets start with some practical\nrecommendations based on Heuristics",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets start with some practical\nrecommendations based on Heuristics",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 943,
			"versionNonce": 535941649,
			"isDeleted": false,
			"id": "wc0JF6DG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2919.5298823804187,
			"y": 2014.7792575823744,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 861.01904296875,
			"height": 150,
			"seed": 176972563,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Initializing parameters at constant c provides parameter symmetry,\nall your parameters will move together towards each detection which limits \nthe space that we traverse making us only able to find the saddle point as a minimum\nfurthermore, with certain activations like ReLu there will be absolutely\nno learning at all as the result will always be 0 and as such from error\nbackpropagation, the gradients will get multiplied by 0!",
			"rawText": "Initializing parameters at constant c provides parameter symmetry,\nall your parameters will move together towards each detection which limits \nthe space that we traverse making us only able to find the saddle point as a minimum\nfurthermore, with certain activations like ReLu there will be absolutely\nno learning at all as the result will always be 0 and as such from error\nbackpropagation, the gradients will get multiplied by 0!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Initializing parameters at constant c provides parameter symmetry,\nall your parameters will move together towards each detection which limits \nthe space that we traverse making us only able to find the saddle point as a minimum\nfurthermore, with certain activations like ReLu there will be absolutely\nno learning at all as the result will always be 0 and as such from error\nbackpropagation, the gradients will get multiplied by 0!",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "text",
			"version": 343,
			"versionNonce": 1851315071,
			"isDeleted": false,
			"id": "D8wFJKzr",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2571.9976522191773,
			"y": 1986.5816055649118,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 157.19981384277344,
			"height": 25,
			"seed": 180313555,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Initializations",
			"rawText": "1) Initializations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Initializations",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 655,
			"versionNonce": 1592748017,
			"isDeleted": false,
			"id": "HrrGzsnq",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2878.2351098384615,
			"y": 2175.5880963109266,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 757.16943359375,
			"height": 80,
			"seed": 326910749,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Randomly initialize your variables i.e drawn from a gaussian distribution with a fixed scale,\nThe scale of this distribution should not be too large to avoid plateaus of nonlinear functions\ndo not set them to 0 nor apply symmetry to their values\n",
			"rawText": "Randomly initialize your variables i.e drawn from a gaussian distribution with a fixed scale,\nThe scale of this distribution should not be too large to avoid plateaus of nonlinear functions\ndo not set them to 0 nor apply symmetry to their values\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Randomly initialize your variables i.e drawn from a gaussian distribution with a fixed scale,\nThe scale of this distribution should not be too large to avoid plateaus of nonlinear functions\ndo not set them to 0 nor apply symmetry to their values\n",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 347,
			"versionNonce": 1477446559,
			"isDeleted": false,
			"id": "UCZNPKg7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2575.024026256996,
			"y": 2295.122541285351,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 126.19985961914062,
			"height": 25,
			"seed": 1850152083,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2) Retraining",
			"rawText": "2) Retraining",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2) Retraining",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 487,
			"versionNonce": 2038383057,
			"isDeleted": false,
			"id": "mdxcwVSc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2920.46286376823,
			"y": 2329.253027832243,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 803.2391967773438,
			"height": 75,
			"seed": 612641203,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The results of random parameter initializations are not guaranteed to be\noptimal as you can still land in local minimas, try to retrain the network\nmultiple times with multiple random initializations and keep the lowest error model",
			"rawText": "The results of random parameter initializations are not guaranteed to be\noptimal as you can still land in local minimas, try to retrain the network\nmultiple times with multiple random initializations and keep the lowest error model",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The results of random parameter initializations are not guaranteed to be\noptimal as you can still land in local minimas, try to retrain the network\nmultiple times with multiple random initializations and keep the lowest error model",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 525,
			"versionNonce": 1382760383,
			"isDeleted": false,
			"id": "SnLfQHYK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2887.4552665455694,
			"y": 2465.659501065711,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 753.0392456054688,
			"height": 100,
			"seed": 1286316691,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3) Learning rate\nThe learning rate of gradient descent should not be too large or too little\ntoo little steps will be a lot harder\na larger LR will help escape local minima!",
			"rawText": "3) Learning rate\nThe learning rate of gradient descent should not be too large or too little\ntoo little steps will be a lot harder\na larger LR will help escape local minima!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3) Learning rate\nThe learning rate of gradient descent should not be too large or too little\ntoo little steps will be a lot harder\na larger LR will help escape local minima!",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "line",
			"version": 548,
			"versionNonce": 1287184305,
			"isDeleted": false,
			"id": "7iHkYtynd-TBjVBeI_R6j",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2811.4905094439273,
			"y": 2710.833935766591,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 8.582778464682562,
			"height": 140.98564499002055,
			"seed": 777496477,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.582778464682562,
					-140.98564499002055
				]
			]
		},
		{
			"type": "line",
			"version": 592,
			"versionNonce": 529199071,
			"isDeleted": false,
			"id": "E4BES0S0UY-ixejDePcxm",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2811.4905094439273,
			"y": 2711.970916774575,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 171.68413220558926,
			"height": 1.7054715119759525,
			"seed": 136943165,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					171.68413220558926,
					1.7054715119759525
				]
			]
		},
		{
			"type": "line",
			"version": 881,
			"versionNonce": 650363281,
			"isDeleted": false,
			"id": "Au5XwmbDaN60BwWFX3_t0",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2793.732437689284,
			"y": 2576.301965707514,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 115.24571500409363,
			"height": 138.91422077268865,
			"seed": 160965181,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.829657332509507,
					88.48039539661696
				],
				[
					37.382967055070715,
					129.84498024453535
				],
				[
					59.281864915733365,
					136.2598089107901
				],
				[
					78.74755190298926,
					129.62377925604372
				],
				[
					100.42524877516013,
					89.80760132756608
				],
				[
					115.24571500409363,
					-2.6544118618985513
				]
			]
		},
		{
			"type": "line",
			"version": 1372,
			"versionNonce": 1769970687,
			"isDeleted": false,
			"id": "Lk4yD_ZsU1qADcUt2oLCN",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2793.732437689284,
			"y": 2576.301965707514,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 103.74326360253339,
			"height": 131.61458815246772,
			"seed": 316244275,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					102.63725866007559,
					-0.22120098849162487
				],
				[
					103.74326360253339,
					72.9963262022089
				],
				[
					18.138481056306453,
					71.66912027125963
				],
				[
					19.24448599876426,
					106.39767546443179
				],
				[
					84.49877760376913,
					106.17647447594017
				],
				[
					84.27757661527767,
					123.65135256677206
				],
				[
					30.525736411832867,
					122.76654861280603
				],
				[
					82.5079687073453,
					126.08456344017898
				],
				[
					32.51654530825686,
					125.42096047470443
				],
				[
					79.85355684544675,
					128.51777431358607
				],
				[
					35.61335914713835,
					128.51777431358607
				],
				[
					77.64154696053129,
					131.3933871639761
				]
			]
		},
		{
			"type": "line",
			"version": 511,
			"versionNonce": 618096497,
			"isDeleted": false,
			"id": "QW6gMQovE4BW5F95GubmB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2575.95226287462,
			"y": 2708.518170207837,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 8.084961246991528,
			"height": 132.808213659116,
			"seed": 1720080189,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.084961246991528,
					-132.808213659116
				]
			]
		},
		{
			"type": "line",
			"version": 555,
			"versionNonce": 1145685023,
			"isDeleted": false,
			"id": "pXincUxTjeE7b-eZJEveY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2575.95226287462,
			"y": 2709.5892041889592,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 161.72613114940714,
			"height": 1.6065509716827584,
			"seed": 697460637,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					161.72613114940714,
					1.6065509716827584
				]
			]
		},
		{
			"type": "line",
			"version": 844,
			"versionNonce": 1362841937,
			"isDeleted": false,
			"id": "NqZcYIZKq_emdw8XAqQZo",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2559.224192524398,
			"y": 2581.7893062525573,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 108.56124779685648,
			"height": 130.85693592404195,
			"seed": 1702718461,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.08551319043704,
					83.34836683059996
				],
				[
					35.21468498592853,
					122.31372832390538
				],
				[
					55.843405776501974,
					128.35648491912391
				],
				[
					74.18004647923411,
					122.10535740682882
				],
				[
					94.60039635273083,
					84.59859233305882
				],
				[
					108.56124779685648,
					-2.500451004918039
				]
			]
		},
		{
			"type": "line",
			"version": 1008,
			"versionNonce": 1876551743,
			"isDeleted": false,
			"id": "L1q6j0uk6mQsqb_BfTosZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2559.495949482807,
			"y": 2583.668662272262,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 47.524684552989626,
			"height": 127.46589776712358,
			"seed": 2036211539,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.867245006541902,
					-0.44004337549062406
				],
				[
					6.013926131705468,
					40.190628294812214
				],
				[
					11.294446637593254,
					40.043947169648874
				],
				[
					13.054620139555825,
					81.99474896642373
				],
				[
					18.62850289577067,
					81.40802446576947
				],
				[
					19.068546271261294,
					97.5429482337598
				],
				[
					24.642429027476137,
					97.6896293589233
				],
				[
					24.78911015263963,
					108.25067037069887
				],
				[
					30.362992908854547,
					108.54403262102586
				],
				[
					30.50967403401804,
					114.99800212822203
				],
				[
					36.08355679023288,
					114.5579587527314
				],
				[
					35.936875665069316,
					121.01192825992757
				],
				[
					41.804120671611294,
					120.71856600960044
				],
				[
					41.95080179677486,
					127.02585439163296
				],
				[
					47.524684552989626,
					125.55904313999744
				]
			]
		},
		{
			"type": "text",
			"version": 499,
			"versionNonce": 21430065,
			"isDeleted": false,
			"id": "cxufzZGD",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2770.6152637100804,
			"y": 2598.8609070087477,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 53.47236633300781,
			"height": 13.881040057185976,
			"seed": 1965277843,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 11.10483204574878,
			"fontFamily": 1,
			"text": "Too large",
			"rawText": "Too large",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Too large",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 413,
			"versionNonce": 1511032927,
			"isDeleted": false,
			"id": "eLIJSYe6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2531.137831159997,
			"y": 2608.646586868371,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 49.97686767578125,
			"height": 13.075913748920986,
			"seed": 1751454941,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 10.46073099913679,
			"fontFamily": 1,
			"text": "Too small",
			"rawText": "Too small",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Too small",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "line",
			"version": 566,
			"versionNonce": 1935798545,
			"isDeleted": false,
			"id": "njM8QGTYGhDLlSUaNpPOj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2363.0382525786094,
			"y": 2711.453315554075,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 5.0437825193558865,
			"height": 132.50409578635254,
			"seed": 724339539,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.0437825193558865,
					-132.50409578635254
				]
			]
		},
		{
			"type": "line",
			"version": 603,
			"versionNonce": 1623073919,
			"isDeleted": false,
			"id": "9x3wsuVVtQqNCbFZByZ-y",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2363.0382525786094,
			"y": 2712.524349535197,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 161.72613114940714,
			"height": 1.6065509716827584,
			"seed": 1388685555,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					161.72613114940714,
					1.6065509716827584
				]
			]
		},
		{
			"type": "line",
			"version": 1991,
			"versionNonce": 755214065,
			"isDeleted": false,
			"id": "HwdhTqQEUtMjrfDrAxrD0",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2361.488299299063,
			"y": 2581.133774890197,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 174.86777683904847,
			"height": 124.7622990763914,
			"seed": 19877779,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.4309770199523655,
					44.96766222481983
				],
				[
					17.658025910375045,
					73.01020224455192
				],
				[
					28.70079160888679,
					73.63898902577193
				],
				[
					39.879862530609785,
					58.91393968215152
				],
				[
					59.05092577816504,
					60.55164497909254
				],
				[
					78.3473378582828,
					70.86286871792095
				],
				[
					86.57907145859167,
					80.16585481383072
				],
				[
					98.63898857226411,
					91.79630522217758
				],
				[
					109.31530241813243,
					106.33094826214597
				],
				[
					121.08205804968986,
					113.34416775299405
				],
				[
					131.41042846020025,
					116.24699863901174
				],
				[
					152.6671721273084,
					112.52361292251817
				],
				[
					164.83188703785095,
					88.19418310143328
				],
				[
					174.86777683904847,
					-8.515300437379665
				]
			]
		},
		{
			"type": "line",
			"version": 836,
			"versionNonce": 1403206815,
			"isDeleted": false,
			"id": "gC-n3Jf9xTUXz9lUiGGi9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2361.1798645664876,
			"y": 2583.0136578771426,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 132.0211861842331,
			"height": 115.7397530355081,
			"seed": 1161497757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					17.166293645939277,
					-0.5309162983278384
				],
				[
					16.989321546496512,
					70.43489557818339
				],
				[
					45.65880165620945,
					69.37306298152748
				],
				[
					45.8357737556521,
					55.39226712555637
				],
				[
					75.03617016369299,
					55.746211324441674
				],
				[
					75.03617016369299,
					67.24939778821545
				],
				[
					100.87409668232306,
					67.24939778821545
				],
				[
					102.11290137842184,
					95.0340174007149
				],
				[
					131.34861576060052,
					94.32612900294498
				],
				[
					132.0211861842331,
					115.20883673718026
				]
			]
		},
		{
			"type": "text",
			"version": 423,
			"versionNonce": 414425297,
			"isDeleted": false,
			"id": "ddWn75MT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2319.45704318097,
			"y": 2593.7971547604748,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 102.76411437988281,
			"height": 25.94730520678731,
			"seed": 581060915,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 10.378922082714924,
			"fontFamily": 1,
			"text": "High enough to\nescape local minimum",
			"rawText": "High enough to\nescape local minimum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "High enough to\nescape local minimum",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "text",
			"version": 715,
			"versionNonce": 913330367,
			"isDeleted": false,
			"id": "cZMeQWSn",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2886.131474910988,
			"y": 3031.203807426814,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 815.5191650390625,
			"height": 100,
			"seed": 1578106419,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "4) Number of Neurons\nUse a sufficient number of neurons at each layer,\nusing more neurons will help with escaping local minima and not underfit the problem\ntoo many neurons will cause your model to overfit though!",
			"rawText": "4) Number of Neurons\nUse a sufficient number of neurons at each layer,\nusing more neurons will help with escaping local minima and not underfit the problem\ntoo many neurons will cause your model to overfit though!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "4) Number of Neurons\nUse a sufficient number of neurons at each layer,\nusing more neurons will help with escaping local minima and not underfit the problem\ntoo many neurons will cause your model to overfit though!",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 689,
			"versionNonce": 1678335665,
			"isDeleted": false,
			"id": "FmXbTP0S",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2876.1439630278724,
			"y": 3194.443394216404,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 805.0390625,
			"height": 125,
			"seed": 978756509,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "5) Number of layers\nDo not go deeper than necessary, deeper neural networks are harder to optimize\nEarlier layers in deeper neural networks are way slower at training\nand deeper neural networks will cause unstable weights that either explode or\nvanish",
			"rawText": "5) Number of layers\nDo not go deeper than necessary, deeper neural networks are harder to optimize\nEarlier layers in deeper neural networks are way slower at training\nand deeper neural networks will cause unstable weights that either explode or\nvanish",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "5) Number of layers\nDo not go deeper than necessary, deeper neural networks are harder to optimize\nEarlier layers in deeper neural networks are way slower at training\nand deeper neural networks will cause unstable weights that either explode or\nvanish",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 864,
			"versionNonce": 1120264415,
			"isDeleted": false,
			"id": "wPEU5yxu",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2805.322613617488,
			"y": 2725.8636572926534,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 651.9193115234375,
			"height": 150,
			"seed": 712339517,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Applying varying learning rates is more beneficial\nWe want higher learning rates at the start to help us escape\nlocal minima, and slowly decay that learning rate the closer we \nactually get to the minima in order to not overshoot the optimum\nand fine tune parameters closer to it\nhere are some options",
			"rawText": "Applying varying learning rates is more beneficial\nWe want higher learning rates at the start to help us escape\nlocal minima, and slowly decay that learning rate the closer we \nactually get to the minima in order to not overshoot the optimum\nand fine tune parameters closer to it\nhere are some options",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Applying varying learning rates is more beneficial\nWe want higher learning rates at the start to help us escape\nlocal minima, and slowly decay that learning rate the closer we \nactually get to the minima in order to not overshoot the optimum\nand fine tune parameters closer to it\nhere are some options",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "text",
			"version": 469,
			"versionNonce": 497836177,
			"isDeleted": false,
			"id": "vBQO2JVu",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2892.8577470375076,
			"y": 2881.3352254049532,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 787.339111328125,
			"height": 25,
			"seed": 353076989,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Apply step decay that decays the learning rate every k iterations by a factor",
			"rawText": "Apply step decay that decays the learning rate every k iterations by a factor",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Apply step decay that decays the learning rate every k iterations by a factor",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 448,
			"versionNonce": 708078847,
			"isDeleted": false,
			"id": "AciZiu57",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2833.894127190756,
			"y": 2910.551359009949,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 677.7593383789062,
			"height": 25,
			"seed": 576427581,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Exponential decay, were the learning rate decays smoothly over time",
			"rawText": "Exponential decay, were the learning rate decays smoothly over time",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Exponential decay, were the learning rate decays smoothly over time",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 504,
			"versionNonce": 324281969,
			"isDeleted": false,
			"id": "Qqn4PNe1",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2839.451259726247,
			"y": 2940.8109259579805,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 678.4392700195312,
			"height": 25,
			"seed": 87683315,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Cyclical decay where we shrink and grow our learning rate repeatedly",
			"rawText": "Cyclical decay where we shrink and grow our learning rate repeatedly",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cyclical decay where we shrink and grow our learning rate repeatedly",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 385,
			"versionNonce": 406615327,
			"isDeleted": false,
			"id": "wqJ1pHoH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -313.07367443889325,
			"y": 319.52036699184777,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 772.1033935546875,
			"height": 35,
			"seed": 1104902461,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "How do we make sure our Error function converges well?",
			"rawText": "How do we make sure our Error function converges well?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we make sure our Error function converges well?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 404,
			"versionNonce": 1875390545,
			"isDeleted": false,
			"id": "m5OtliEPDDoBigPCwpLpK",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -123.77780841678111,
			"y": 494.8169601634228,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 432.6328174088892,
			"height": 350.36165868851026,
			"seed": 851214333,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e95fbe89d4bcdfbfe037122e6b58b82ecafebfcc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 772,
			"versionNonce": 1951299903,
			"isDeleted": false,
			"id": "RdMYEbzF",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -360.4318835093917,
			"y": 364.79712544947984,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 881.8190307617188,
			"height": 150,
			"seed": 1666029811,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "A Well conditioned Error function is one that its optimum is not flat\nMeaning that the convergence to the minima from all sides is about the same rate, such\nthat we can easily converge to it without moving much at the bottom\nWhilst a poorly conditioned function converges too fast from one side and too slow\nfrom another, making it fast in one direction and really slow in the other\nthis causes a lot of iterations to search in the slower side for an optimal solution",
			"rawText": "A Well conditioned Error function is one that its optimum is not flat\nMeaning that the convergence to the minima from all sides is about the same rate, such\nthat we can easily converge to it without moving much at the bottom\nWhilst a poorly conditioned function converges too fast from one side and too slow\nfrom another, making it fast in one direction and really slow in the other\nthis causes a lot of iterations to search in the slower side for an optimal solution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A Well conditioned Error function is one that its optimum is not flat\nMeaning that the convergence to the minima from all sides is about the same rate, such\nthat we can easily converge to it without moving much at the bottom\nWhilst a poorly conditioned function converges too fast from one side and too slow\nfrom another, making it fast in one direction and really slow in the other\nthis causes a lot of iterations to search in the slower side for an optimal solution",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 436,
			"versionNonce": 417332785,
			"isDeleted": false,
			"id": "7qsk94K28uydYg80KAhVF",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -132.6647198626516,
			"y": 1137.4363957440787,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 174.2787357666388,
			"height": 161.57826109538576,
			"seed": 17000371,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "341f497e30247884b60ac299ee2b1acfa7418d56",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 447,
			"versionNonce": 1674246495,
			"isDeleted": false,
			"id": "X42A5t14iA2kjHlDIto97",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 81.84432015902055,
			"y": 1152.541486692429,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 157.53259613568218,
			"height": 159.52667963107058,
			"seed": 1152325683,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "47f1a996dc9c2a16ea211cdfb258cd498cd35504",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 576,
			"versionNonce": 1300434961,
			"isDeleted": false,
			"id": "7_dQ8xxdrT6A-9Yl7uzH9",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 6.056568977380039,
			"y": 1256.238631733246,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 44.664521973604764,
			"height": 38.625375340554,
			"seed": 954479069,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
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
					-2.3904955422492833,
					-17.236731015165788
				],
				[
					-17.110915460310565,
					-12.959002150088168
				],
				[
					-16.85928435060012,
					-29.189208726412176
				],
				[
					-29.440839836122564,
					-27.176159848728503
				],
				[
					-35.35417091431813,
					-38.625375340554
				],
				[
					-44.664521973604764,
					-37.11558868229133
				]
			]
		},
		{
			"type": "arrow",
			"version": 560,
			"versionNonce": 201487743,
			"isDeleted": false,
			"id": "aqjSqGTzQ7ielVyMkMxjH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 171.40801190551136,
			"y": 1179.6748319996793,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 27.37693165329756,
			"height": 45.09141684072529,
			"seed": 1359346621,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
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
					7.381035494761591,
					14.896271634882396
				],
				[
					-3.891818715419788,
					23.485112937877716
				],
				[
					4.160220006138331,
					32.073954240873036
				],
				[
					1.7446083896708728,
					41.06539747994623
				],
				[
					-5.502226459731389,
					45.09141684072529
				],
				[
					-7.246834849402319,
					37.03937811916717
				],
				[
					-12.07805808233718,
					44.55461425928809
				],
				[
					-16.23827808847551,
					36.636776183089296
				],
				[
					-19.99589615853597,
					44.01781167785089
				]
			]
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 61400561,
			"isDeleted": false,
			"id": "aQVpxhvM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -231.41186139720133,
			"y": 876.7608269600634,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 651.6593017578125,
			"height": 25,
			"seed": 430026813,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Suppose that we have an error function taking this following form",
			"rawText": "Suppose that we have an error function taking this following form",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Suppose that we have an error function taking this following form",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 275,
			"versionNonce": 339045791,
			"isDeleted": false,
			"id": "EVBHYnRFrNxrGXmZ78OsT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -116.20865158356594,
			"y": 913.1336153317604,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 354,
			"height": 112,
			"seed": 1526168125,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e6cb1c94291a121e039ecd09d75169e8ba0778d0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 381,
			"versionNonce": 106495953,
			"isDeleted": false,
			"id": "neWvw0Zh0wF7XB2a1KOs7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 76.26119463919994,
			"y": 999.8009417845428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 73.23332521636735,
			"height": 58.27500295837922,
			"seed": 681477395,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-28.38832413432911,
					58.27500295837922
				],
				[
					-73.23332521636735,
					55.92428873166341
				]
			]
		},
		{
			"type": "text",
			"version": 375,
			"versionNonce": 1737777599,
			"isDeleted": false,
			"id": "cq5asjoL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -136.11810810603495,
			"y": 1017.1355510609999,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 146.0963134765625,
			"height": 100,
			"seed": 1724076915,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Positive \ncoefficient\ndescribing the \ncurvature of that\ndimension",
			"rawText": "Positive \ncoefficient\ndescribing the \ncurvature of that\ndimension",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Positive \ncoefficient\ndescribing the \ncurvature of that\ndimension",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "line",
			"version": 324,
			"versionNonce": 1403706801,
			"isDeleted": false,
			"id": "kvTpnwLKzhdV_ZIQjv_pX",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 123.86299775076301,
			"y": 999.8009417845428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 10.074229883039067,
			"height": 98.46747272776895,
			"seed": 1540432829,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-10.074229883039067,
					98.46747272776895
				]
			]
		},
		{
			"type": "text",
			"version": 271,
			"versionNonce": 926929375,
			"isDeleted": false,
			"id": "mhZxzZ4f",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 56.735871027704206,
			"y": 1104.1179673476247,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 108.25624084472656,
			"height": 40,
			"seed": 672316349,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Parameter to\noptimize",
			"rawText": "Parameter to\noptimize",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Parameter to\noptimize",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 288,
			"versionNonce": 986054545,
			"isDeleted": false,
			"id": "YeKOrOeHjIScZMxbvbmy_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 183.98340189148,
			"y": 997.2011405244036,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 41.27184500470838,
			"height": 60.77035445575177,
			"seed": 684464413,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					41.27184500470838,
					60.77035445575177
				]
			]
		},
		{
			"type": "text",
			"version": 275,
			"versionNonce": 1011367423,
			"isDeleted": false,
			"id": "00Hoox0c",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 180.91161912495198,
			"y": 1063.1710975004337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 102.33621215820312,
			"height": 40,
			"seed": 1692937587,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Theoritical\nbest solution",
			"rawText": "Theoritical\nbest solution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Theoritical\nbest solution",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 666,
			"versionNonce": 971105649,
			"isDeleted": false,
			"id": "AAw0w606",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -488.74727741537004,
			"y": 1159.6768019071997,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 380.03955078125,
			"height": 100,
			"seed": 923252659,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "v5k1v6pRkPwvEi32KKzeP",
					"type": "arrow"
				}
			],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can observe that the function\nis much more well-conditioned when\nall dimensions have similar curvatures \n",
			"rawText": "We can observe that the function\nis much more well-conditioned when\nall dimensions have similar curvatures \n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can observe that the function\nis much more well-conditioned when\nall dimensions have similar curvatures \n",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 351,
			"versionNonce": 967714335,
			"isDeleted": false,
			"id": "QzUXsTQViC8-8yynqGmHb",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -403.3279039389812,
			"y": 1246.189990473677,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 193,
			"height": 43,
			"seed": 1032635645,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "918a86f852203dcdb569c03876bff0cc82574a15",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 387,
			"versionNonce": 474353489,
			"isDeleted": false,
			"id": "KawigzSAfn-aD04eDvb4C",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 296.844151814498,
			"y": 1255.2453870040722,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 192,
			"height": 50,
			"seed": 857221811,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2df0a63669c557dc630db3b7d2f0a2c010c64523",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 181,
			"versionNonce": 1046612543,
			"isDeleted": false,
			"id": "oW1eaoEX4jq92OhXp_z10",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1822.0467022179798,
			"y": 2055.920515922785,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 192.25733147915798,
			"height": 4.0053610724826285,
			"seed": 690978941,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "7QS8YDMJzSox2RazkVJIe",
				"focus": -0.7190549910695321,
				"gap": 14.38098862427978
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
					-192.25733147915798,
					4.0053610724826285
				]
			]
		},
		{
			"type": "ellipse",
			"version": 75,
			"versionNonce": 1481243953,
			"isDeleted": false,
			"id": "Zc9picqEy66OsIZT1UM-n",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2417.748292384687,
			"y": 1257.6327285451061,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 512.8571428571427,
			"height": 527.1428571428571,
			"seed": 1781811123,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392123,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 212,
			"versionNonce": 658795103,
			"isDeleted": false,
			"id": "9XR61gBY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 228.2467894315015,
			"y": 1171.1407938264913,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 332.899658203125,
			"height": 75,
			"seed": 1238362547,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ow93vdZ1rJE7xNcjNBRCi",
					"type": "arrow"
				}
			],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "and is poorly conditioned when one\nside converges way faster than \nthe other",
			"rawText": "and is poorly conditioned when one\nside converges way faster than \nthe other",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "and is poorly conditioned when one\nside converges way faster than \nthe other",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 827,
			"versionNonce": 760557329,
			"isDeleted": false,
			"id": "v5k1v6pRkPwvEi32KKzeP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -507.82464552483145,
			"y": 1196.1083410616532,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 225.16820099713857,
			"height": 139.07229068964602,
			"seed": 1345589363,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "AAw0w606",
				"focus": 0.5211047913895016,
				"gap": 19.077368109461418
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
					-204.91988814140677,
					23.245464275417362
				],
				[
					-225.16820099713857,
					139.07229068964602
				]
			]
		},
		{
			"type": "text",
			"version": 429,
			"versionNonce": 1629865599,
			"isDeleted": false,
			"id": "e5KbwmuO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -711.7164311918707,
			"y": 1127.2785255146146,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 163.8723602294922,
			"height": 60,
			"seed": 2100171699,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Can we quantify this\ndifficulty of the\noptimization?",
			"rawText": "Can we quantify this\ndifficulty of the\noptimization?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Can we quantify this\ndifficulty of the\noptimization?",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 541,
			"versionNonce": 31401201,
			"isDeleted": false,
			"id": "2hYF0bbs",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -928.6331903994202,
			"y": 1352.2233524127446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 413.85955810546875,
			"height": 25,
			"seed": 266313309,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Using gradient descent we perform a step",
			"rawText": "Using gradient descent we perform a step",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Using gradient descent we perform a step",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 474,
			"versionNonce": 1791401631,
			"isDeleted": false,
			"id": "6XCEl08BS5e3PW2MWBOpX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -898.7568987424305,
			"y": 1384.970463742535,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 360,
			"height": 45,
			"seed": 306353661,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e28b6ceecc54986c0a888598041d6b049999fdcf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 645,
			"versionNonce": 24075985,
			"isDeleted": false,
			"id": "MSm_-V4AjvAt6szVjvuE9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -946.0551445488118,
			"y": 1424.6407506726669,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 472.09761774112854,
			"height": 163.17160380178814,
			"seed": 1575022749,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "z-6eo91J-bLZ-UpOcYL1X",
					"type": "arrow"
				}
			],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "94997c5e230cfe92fc6e979f3019ca93db05c68c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 1158,
			"versionNonce": 383218367,
			"isDeleted": false,
			"id": "z-6eo91J-bLZ-UpOcYL1X",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -460.9173260948777,
			"y": 1463.0829912967024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 249.79567088952422,
			"height": 122.41637506171583,
			"seed": 644116957,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "MSm_-V4AjvAt6szVjvuE9",
				"focus": -0.6252777014507614,
				"gap": 13.040200712805557
			},
			"endBinding": {
				"elementId": "7lHesTeR3wCFEv-p7r_G2",
				"focus": 0.05275863234645771,
				"gap": 23.925497276399483
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
					229.92739928414778,
					17.829607744962686
				],
				[
					249.79567088952422,
					122.41637506171583
				]
			]
		},
		{
			"type": "image",
			"version": 476,
			"versionNonce": 2057133233,
			"isDeleted": false,
			"id": "7lHesTeR3wCFEv-p7r_G2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -533.9277868139694,
			"y": 1609.4248636348177,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 673,
			"height": 299,
			"seed": 804540029,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "z-6eo91J-bLZ-UpOcYL1X",
					"type": "arrow"
				},
				{
					"id": "T3WpkYE48AlkgLppl9Zs1",
					"type": "arrow"
				}
			],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "eb052215b4350d59b1ddf009875e5ea5b4f907ad",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 454,
			"versionNonce": 234406623,
			"isDeleted": false,
			"id": "AkzwVoIk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -453.5344547798062,
			"y": 1408.1667143241225,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 315.4086608886719,
			"height": 40,
			"seed": 1709898003,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Using our initial solution we can perform\nt iterations and get",
			"rawText": "Using our initial solution we can perform\nt iterations and get",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Using our initial solution we can perform\nt iterations and get",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 495,
			"versionNonce": 2098241169,
			"isDeleted": false,
			"id": "gH1l7sbqNgDRaLHw-l_8u",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -440.36350379438977,
			"y": 1883.499453711641,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.72216576197161,
			"height": 81.02010827360846,
			"seed": 1533633651,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.72216576197161,
					81.02010827360846
				]
			]
		},
		{
			"type": "text",
			"version": 683,
			"versionNonce": 280694527,
			"isDeleted": false,
			"id": "5qOYYjbp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -591.7482831957027,
			"y": 1978.3932387450868,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 272.28857421875,
			"height": 40,
			"seed": 2054690333,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can observe that if the\nsolution to the optimum decreases",
			"rawText": "We can observe that if the\nsolution to the optimum decreases",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can observe that if the\nsolution to the optimum decreases",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 287,
			"versionNonce": 931177585,
			"isDeleted": false,
			"id": "2PBWDUOrAQcx7zu_0jBg4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -175.22874197988904,
			"y": 1930.6855912294166,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.061605513321126,
			"height": 61.30860003807993,
			"seed": 643020473,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					14.061605513321126,
					61.30860003807993
				]
			]
		},
		{
			"type": "text",
			"version": 429,
			"versionNonce": 2040452895,
			"isDeleted": false,
			"id": "MT7mGYOu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -269.34516944860184,
			"y": 1986.9320132827015,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 255.7285614013672,
			"height": 20,
			"seed": 1862076727,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "eRY0-u409a99SruDpdzCp",
					"type": "arrow"
				},
				{
					"id": "AcvZG-f3M39NPHCxyxWI_",
					"type": "arrow"
				}
			],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Then this term has to decrease",
			"rawText": "Then this term has to decrease",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Then this term has to decrease",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 622,
			"versionNonce": 364179025,
			"isDeleted": false,
			"id": "eRY0-u409a99SruDpdzCp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -320.9069750978963,
			"y": 1993.1191197085627,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 41.03776861567043,
			"height": 1.141084045630123,
			"seed": 1014959481,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "MT7mGYOu",
				"focus": -0.08676828832565928,
				"gap": 10.52403703362404
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
					41.03776861567043,
					1.141084045630123
				]
			]
		},
		{
			"type": "arrow",
			"version": 750,
			"versionNonce": 2132056895,
			"isDeleted": false,
			"id": "AcvZG-f3M39NPHCxyxWI_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -6.489475820035125,
			"y": 1994.8065123701608,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 33.185389011437906,
			"height": 17.436390836518513,
			"seed": 1099051961,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "MT7mGYOu",
				"focus": 0.8914172235794103,
				"gap": 7.1271322271995246
			},
			"endBinding": {
				"elementId": "SdvsqZZM",
				"focus": 0.8109710746910657,
				"gap": 4.5362043369784715
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
					33.185389011437906,
					-17.436390836518513
				]
			]
		},
		{
			"type": "text",
			"version": 277,
			"versionNonce": 512031793,
			"isDeleted": false,
			"id": "SdvsqZZM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 31.232117528381252,
			"y": 1965.558372902453,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 151.7923583984375,
			"height": 20,
			"seed": 815838903,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "AcvZG-f3M39NPHCxyxWI_",
					"type": "arrow"
				}
			],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Since this is static",
			"rawText": "Since this is static",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Since this is static",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 276,
			"versionNonce": 897375071,
			"isDeleted": false,
			"id": "SgrdJNHytWI7Bo8WsofUQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 47.50708935111817,
			"y": 1864.8772774270733,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 42.747280760496324,
			"height": 98.43123859324828,
			"seed": 93573687,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					42.747280760496324,
					98.43123859324828
				]
			]
		},
		{
			"type": "text",
			"version": 512,
			"versionNonce": 299388433,
			"isDeleted": false,
			"id": "Buq49OcN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -480.33758787747274,
			"y": 2032.3871361181718,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 572.1130981445312,
			"height": 60,
			"seed": 1932483449,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Meaning that if we decrease our convergence along every dimension\nour optimal solution gets closer and closer to the solution exponentially\nfast",
			"rawText": "Meaning that if we decrease our convergence along every dimension\nour optimal solution gets closer and closer to the solution exponentially\nfast",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Meaning that if we decrease our convergence along every dimension\nour optimal solution gets closer and closer to the solution exponentially\nfast",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 306,
			"versionNonce": 1361581951,
			"isDeleted": false,
			"id": "V11hs5GO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -438.80693851260344,
			"y": 2098.2100571033625,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 491.72894287109375,
			"height": 60,
			"seed": 1954900153,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Likewise that our Error function also decreases exponentially\nfast since it is a linear combination of our optimum solutions \nin each dimension",
			"rawText": "Likewise that our Error function also decreases exponentially\nfast since it is a linear combination of our optimum solutions \nin each dimension",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Likewise that our Error function also decreases exponentially\nfast since it is a linear combination of our optimum solutions \nin each dimension",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 785,
			"versionNonce": 1185309681,
			"isDeleted": false,
			"id": "PJrxSZir",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3705.310132644983,
			"y": 2048.2413198062186,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 471.01800537109375,
			"height": 35,
			"seed": 1650060345,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "How do we choose our batch size?",
			"rawText": "How do we choose our batch size?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we choose our batch size?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 3673,
			"versionNonce": 1792263313,
			"isDeleted": false,
			"id": "vjo9h2zX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3416.8694145924055,
			"y": 2290.4603870437977,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1036.8590087890625,
			"height": 1425,
			"seed": 692202711,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8LLggFzLbmGRC1a9UBlK8",
					"type": "arrow"
				}
			],
			"updated": 1706890553170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can think of five interrelated aspects when it comes to the choice\n\n\n1. statistical efficiency\nLarger batches typically determine the quality of the gradient\nestimate when training. This is assuming that the larger batch does\nnot have redundancy, rendering it somewhat useless/ less useful\nthan what we hope.\n\n\n\n2. Computational efficiency\nWhile larger batches take more time to compute the gradient and perform\na step in the right direction,\ndue to multi-core technology or hardware that allows computation of\ngradients related to the same batch in parallel, smaller batches\nmay under utilize the power the hardware holds and thus making\nthe process unnecessarily slow\nAvailable memory should also be considered when choosing a batchsize\nas we do not want to choose something that exceeds our memory limits \n\n\n\n3. Regularization strategy\nSmall batches can offer a regularization effect because the gradient estimate is no\nlonger sensitive to the training set (due to having a small batch) and thus allowing us\nto generalize more in our gradient\nKeep in mind we choose a small learning rate for smaller batches because we dont want\nto take large steps in very general directions with low confidence\n\n\n\n4. Optimization strategy\nDepending on our optimization strategy, sometimes we ought to compute\nsecond order derivative (Hessian) estimates which requires a large batch size\nif the Hessian is ill-conditioned and has a poor condition number\n(aka very sensitive to errors when estimating the gradient because\nits much more prone to miscalculations when multiplied with other vectors H * g)\nThese strategies require larger batch sizes in order to get more accurate estimations\n\n\n\n5. Computation of choosing the batchsize\nIdeally we want our batches to be chosen independently from the dataset, such that\neach batch is unbiased and diverse. This can sometimes be very costly with larger datasets.\n(Although its advantageous in bootstrap aggregating because we want diversity in batches)\nIn other cases, we usually Shuffle the entire dataset ones and we choose our batches deterministically\nthrough some interval. (This can be useful for bench-marking different models)\n\n\n\n*We usually go over the data multiple times (We call this iteration an epoch)\nwhich is a bit counter intuitive because it makes the model\ngeneralize less in some cases BUT for most starting cases our epochs are used\nin order to not underfit the data and actually extract all information of features.\nunderfitting and computational efficiency is typically more of a concern in larger datasets.\nMore on this in Early-Stopping",
			"rawText": "We can think of five interrelated aspects when it comes to the choice\n\n\n1. statistical efficiency\nLarger batches typically determine the quality of the gradient\nestimate when training. This is assuming that the larger batch does\nnot have redundancy, rendering it somewhat useless/ less useful\nthan what we hope.\n\n\n\n2. Computational efficiency\nWhile larger batches take more time to compute the gradient and perform\na step in the right direction,\ndue to multi-core technology or hardware that allows computation of\ngradients related to the same batch in parallel, smaller batches\nmay under utilize the power the hardware holds and thus making\nthe process unnecessarily slow\nAvailable memory should also be considered when choosing a batchsize\nas we do not want to choose something that exceeds our memory limits \n\n\n\n3. Regularization strategy\nSmall batches can offer a regularization effect because the gradient estimate is no\nlonger sensitive to the training set (due to having a small batch) and thus allowing us\nto generalize more in our gradient\nKeep in mind we choose a small learning rate for smaller batches because we dont want\nto take large steps in very general directions with low confidence\n\n\n\n4. Optimization strategy\nDepending on our optimization strategy, sometimes we ought to compute\nsecond order derivative (Hessian) estimates which requires a large batch size\nif the Hessian is ill-conditioned and has a poor condition number\n(aka very sensitive to errors when estimating the gradient because\nits much more prone to miscalculations when multiplied with other vectors H * g)\nThese strategies require larger batch sizes in order to get more accurate estimations\n\n\n\n5. Computation of choosing the batchsize\nIdeally we want our batches to be chosen independently from the dataset, such that\neach batch is unbiased and diverse. This can sometimes be very costly with larger datasets.\n(Although its advantageous in bootstrap aggregating because we want diversity in batches)\nIn other cases, we usually Shuffle the entire dataset ones and we choose our batches deterministically\nthrough some interval. (This can be useful for bench-marking different models)\n\n\n\n*We usually go over the data multiple times (We call this iteration an epoch)\nwhich is a bit counter intuitive because it makes the model\ngeneralize less in some cases BUT for most starting cases our epochs are used\nin order to not underfit the data and actually extract all information of features.\nunderfitting and computational efficiency is typically more of a concern in larger datasets.\nMore on this in Early-Stopping",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can think of five interrelated aspects when it comes to the choice\n\n\n1. statistical efficiency\nLarger batches typically determine the quality of the gradient\nestimate when training. This is assuming that the larger batch does\nnot have redundancy, rendering it somewhat useless/ less useful\nthan what we hope.\n\n\n\n2. Computational efficiency\nWhile larger batches take more time to compute the gradient and perform\na step in the right direction,\ndue to multi-core technology or hardware that allows computation of\ngradients related to the same batch in parallel, smaller batches\nmay under utilize the power the hardware holds and thus making\nthe process unnecessarily slow\nAvailable memory should also be considered when choosing a batchsize\nas we do not want to choose something that exceeds our memory limits \n\n\n\n3. Regularization strategy\nSmall batches can offer a regularization effect because the gradient estimate is no\nlonger sensitive to the training set (due to having a small batch) and thus allowing us\nto generalize more in our gradient\nKeep in mind we choose a small learning rate for smaller batches because we dont want\nto take large steps in very general directions with low confidence\n\n\n\n4. Optimization strategy\nDepending on our optimization strategy, sometimes we ought to compute\nsecond order derivative (Hessian) estimates which requires a large batch size\nif the Hessian is ill-conditioned and has a poor condition number\n(aka very sensitive to errors when estimating the gradient because\nits much more prone to miscalculations when multiplied with other vectors H * g)\nThese strategies require larger batch sizes in order to get more accurate estimations\n\n\n\n5. Computation of choosing the batchsize\nIdeally we want our batches to be chosen independently from the dataset, such that\neach batch is unbiased and diverse. This can sometimes be very costly with larger datasets.\n(Although its advantageous in bootstrap aggregating because we want diversity in batches)\nIn other cases, we usually Shuffle the entire dataset ones and we choose our batches deterministically\nthrough some interval. (This can be useful for bench-marking different models)\n\n\n\n*We usually go over the data multiple times (We call this iteration an epoch)\nwhich is a bit counter intuitive because it makes the model\ngeneralize less in some cases BUT for most starting cases our epochs are used\nin order to not underfit the data and actually extract all information of features.\nunderfitting and computational efficiency is typically more of a concern in larger datasets.\nMore on this in Early-Stopping",
			"lineHeight": 1.25,
			"baseline": 1418
		},
		{
			"type": "text",
			"version": 760,
			"versionNonce": 216782527,
			"isDeleted": false,
			"id": "1eli204b",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3719.1445958931,
			"y": 2492.511527276227,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 440.512939453125,
			"height": 20,
			"seed": 772463481,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890696693,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "for rich and diverse datasets we like larger batchsizes",
			"rawText": "for rich and diverse datasets we like larger batchsizes",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "for rich and diverse datasets we like larger batchsizes",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 827,
			"versionNonce": 1966703551,
			"isDeleted": false,
			"id": "KiLCAHvq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3618.3974509817313,
			"y": 2797.724417312301,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 608.5612182617188,
			"height": 20,
			"seed": 565371833,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Our batch size needs to depend and be chosen with our architecture in mind!",
			"rawText": "Our batch size needs to depend and be chosen with our architecture in mind!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Our batch size needs to depend and be chosen with our architecture in mind!",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 805,
			"versionNonce": 937483185,
			"isDeleted": false,
			"id": "orQTirpE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3673.6104196073725,
			"y": 3018.8001683424836,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 519.3931884765625,
			"height": 20,
			"seed": 1202885463,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "small batches with small learning rates make it harder to overfit",
			"rawText": "small batches with small learning rates make it harder to overfit",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "small batches with small learning rates make it harder to overfit",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 697,
			"versionNonce": 1475392479,
			"isDeleted": false,
			"id": "ltCZ6Xsd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4281.323728353676,
			"y": 3208.059429955654,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 10.912033081054688,
			"height": 20,
			"seed": 320891833,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "-1",
			"rawText": "-1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "-1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 819,
			"versionNonce": 1670135185,
			"isDeleted": false,
			"id": "DPiq1RjB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3526.4472728394126,
			"y": 3271.6284278021194,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 813.0416259765625,
			"height": 20,
			"seed": 2146332247,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "depending on your optimization strategy, larger batches offer less errors in estimates of the gradient",
			"rawText": "depending on your optimization strategy, larger batches offer less errors in estimates of the gradient",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "depending on your optimization strategy, larger batches offer less errors in estimates of the gradient",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 824,
			"versionNonce": 411885567,
			"isDeleted": false,
			"id": "3e6bSQNu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3520.351019299382,
			"y": 3494.1282922912687,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 860.44970703125,
			"height": 20,
			"seed": 47598199,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "choosing how much computation are you willing to spend on making the batches is dependent on your strategy",
			"rawText": "choosing how much computation are you willing to spend on making the batches is dependent on your strategy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "choosing how much computation are you willing to spend on making the batches is dependent on your strategy",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 305,
			"versionNonce": 724591473,
			"isDeleted": false,
			"id": "SAAk8xWL",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1346.0292007861633,
			"y": 1541.2763795313142,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 245.6245574951172,
			"height": 38.70527330491065,
			"seed": 2025290647,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 10.32140621464284,
			"fontFamily": 1,
			"text": "Poor condition number means that the ratio\nbetween the minimum and maximum eigenvalues of\nthe hessian is large",
			"rawText": "Poor condition number means that the ratio\nbetween the minimum and maximum eigenvalues of\nthe hessian is large",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Poor condition number means that the ratio\nbetween the minimum and maximum eigenvalues of\nthe hessian is large",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 348,
			"versionNonce": 688818207,
			"isDeleted": false,
			"id": "qZJHVAWRiWs441i_tcReD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1608.2246516652774,
			"y": 1559.7256709782328,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 59.13591520871592,
			"height": 62.70788324145676,
			"seed": 238331383,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					41.276075045009456,
					16.66918415279232
				],
				[
					59.13591520871592,
					62.70788324145676
				]
			]
		},
		{
			"type": "text",
			"version": 458,
			"versionNonce": 454348113,
			"isDeleted": false,
			"id": "rakYpU8D",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1548.053892342432,
			"y": 1631.4901817227917,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 255.00900268554688,
			"height": 90.31230437812485,
			"seed": 1463410999,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 10.32140621464284,
			"fontFamily": 1,
			"text": "and what do the eigenvalues\nof the hessian represent?\n\nit represents how much the first order\nderivative changes in the direction of the\neigenvector\n(can be thought of as sensitivity or acceleration)",
			"rawText": "and what do the eigenvalues\nof the hessian represent?\n\nit represents how much the first order\nderivative changes in the direction of the\neigenvector\n(can be thought of as sensitivity or acceleration)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "and what do the eigenvalues\nof the hessian represent?\n\nit represents how much the first order\nderivative changes in the direction of the\neigenvector\n(can be thought of as sensitivity or acceleration)",
			"lineHeight": 1.25,
			"baseline": 85
		},
		{
			"type": "line",
			"version": 269,
			"versionNonce": 1734749247,
			"isDeleted": false,
			"id": "k9M516VcQi7HReEzoBLmj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1674.9013882764464,
			"y": 1726.814397843127,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 133.75035855930957,
			"height": 54.37329116506068,
			"seed": 866664439,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.11278943519483,
					51.19820846929066
				],
				[
					-133.75035855930957,
					54.37329116506068
				]
			]
		},
		{
			"type": "text",
			"version": 281,
			"versionNonce": 1251015473,
			"isDeleted": false,
			"id": "utZDuOMF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1329.5836653869842,
			"y": 1734.5453161125201,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 167.07379150390625,
			"height": 25.8035155366071,
			"seed": 1446381913,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 10.32140621464284,
			"fontFamily": 1,
			"text": "And what is the direction\nof the eigenvector of a hessian?",
			"rawText": "And what is the direction\nof the eigenvector of a hessian?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "And what is the direction\nof the eigenvector of a hessian?",
			"lineHeight": 1.25,
			"baseline": 21
		},
		{
			"type": "text",
			"version": 407,
			"versionNonce": 527715423,
			"isDeleted": false,
			"id": "KtPOWupt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1279.180820818151,
			"y": 1765.3930537806236,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 274.09759521484375,
			"height": 51.6070310732142,
			"seed": 1896181625,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 10.32140621464284,
			"fontFamily": 1,
			"text": "the eigenvectors of the Hessian form the principal\naxes of the paraboloid that acts as a local\napproximation of the behavior, with the\neigenvalues being related to the relative axis lengths",
			"rawText": "the eigenvectors of the Hessian form the principal\naxes of the paraboloid that acts as a local\napproximation of the behavior, with the\neigenvalues being related to the relative axis lengths",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the eigenvectors of the Hessian form the principal\naxes of the paraboloid that acts as a local\napproximation of the behavior, with the\neigenvalues being related to the relative axis lengths",
			"lineHeight": 1.25,
			"baseline": 47
		},
		{
			"type": "line",
			"version": 322,
			"versionNonce": 2047634705,
			"isDeleted": false,
			"id": "zYhoEay0WL59_u-piCzYP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1284.3036725314225,
			"y": 1783.8169829494893,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 57.82489910772367,
			"height": 88.92369232674486,
			"seed": 889044887,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-55.79648062056046,
					-16.71199418373598
				],
				[
					-57.82489910772367,
					-88.92369232674486
				]
			]
		},
		{
			"type": "text",
			"version": 561,
			"versionNonce": 1292462207,
			"isDeleted": false,
			"id": "2eI63SkX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1105.7192203766178,
			"y": 1612.6449996050787,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 246.6661376953125,
			"height": 77.4105466098213,
			"seed": 202058617,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "LtGxneqxznC6XB_ZWBnsG",
					"type": "arrow"
				}
			],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 10.32140621464284,
			"fontFamily": 1,
			"text": "In conclusion a bad condition number\nmeans that the curvature of the error function\nin each dimension has high discrepancy\n(one way larger than the other)\nresulting taco shaped error functions that\nbounce a lot when going towards the minima",
			"rawText": "In conclusion a bad condition number\nmeans that the curvature of the error function\nin each dimension has high discrepancy\n(one way larger than the other)\nresulting taco shaped error functions that\nbounce a lot when going towards the minima",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In conclusion a bad condition number\nmeans that the curvature of the error function\nin each dimension has high discrepancy\n(one way larger than the other)\nresulting taco shaped error functions that\nbounce a lot when going towards the minima",
			"lineHeight": 1.25,
			"baseline": 73
		},
		{
			"type": "arrow",
			"version": 415,
			"versionNonce": 1895736049,
			"isDeleted": false,
			"id": "Ow93vdZ1rJE7xNcjNBRCi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 571.3850215577868,
			"y": 1209.9082106008307,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 193.04382620329648,
			"height": 83.54842338590902,
			"seed": 1042576601,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9XR61gBY",
				"focus": -0.18686862252615927,
				"gap": 10.238573923160288
			},
			"endBinding": {
				"elementId": "GPdEgVSP",
				"focus": 0.07568030466309619,
				"gap": 27.788264727669684
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
					170.85328449851136,
					9.711285290460637
				],
				[
					193.04382620329648,
					83.54842338590902
				]
			]
		},
		{
			"type": "image",
			"version": 734,
			"versionNonce": 501612703,
			"isDeleted": false,
			"id": "zD4aJW1r4uFDEhA6n36EC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 684.3164503471027,
			"y": 1473.927393656539,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 157.53259613568218,
			"height": 159.52667963107058,
			"seed": 1137992505,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "47f1a996dc9c2a16ea211cdfb258cd498cd35504",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 105,
			"versionNonce": 468655313,
			"isDeleted": false,
			"id": "EGwBtFFt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 653.5979942170824,
			"y": 1184.6867872881287,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 120.57627868652344,
			"height": 20,
			"seed": 1002788663,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Why is this bad",
			"rawText": "Why is this bad",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Why is this bad",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 672,
			"versionNonce": 867865791,
			"isDeleted": false,
			"id": "GPdEgVSP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 502.2196717728607,
			"y": 1321.2448987144094,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 544.3692016601562,
			"height": 160,
			"seed": 1949653143,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ow93vdZ1rJE7xNcjNBRCi",
					"type": "arrow"
				}
			],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "One side here clearly converges faster than the other\nand since it has an effect on the gradient that we choose to\nupdate our parameters, and its much more steep\n(Its eigenvalue is higher in the Hessian)\nit will affect our gradient proportionally larger than\nthe other dimension that we also care about when\ngetting near the minima. This causes it to bounce a lot in directions\nwe dont want it to! (overshooting)",
			"rawText": "One side here clearly converges faster than the other\nand since it has an effect on the gradient that we choose to\nupdate our parameters, and its much more steep\n(Its eigenvalue is higher in the Hessian)\nit will affect our gradient proportionally larger than\nthe other dimension that we also care about when\ngetting near the minima. This causes it to bounce a lot in directions\nwe dont want it to! (overshooting)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "One side here clearly converges faster than the other\nand since it has an effect on the gradient that we choose to\nupdate our parameters, and its much more steep\n(Its eigenvalue is higher in the Hessian)\nit will affect our gradient proportionally larger than\nthe other dimension that we also care about when\ngetting near the minima. This causes it to bounce a lot in directions\nwe dont want it to! (overshooting)",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "line",
			"version": 487,
			"versionNonce": 1786075825,
			"isDeleted": false,
			"id": "sIGIcqaBxP6w7LWqSyZJP",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 779.8932654237856,
			"y": 1499.6010855705135,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 28.2963202876349,
			"height": 52.14153401317003,
			"seed": 2005365143,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.907617098042806,
					15.366915512011474
				],
				[
					3.1793618300713433,
					24.481086091549514
				],
				[
					-3.391319285409395,
					35.18493758612294
				],
				[
					-4.239149106761715,
					45.994767808365395
				],
				[
					-13.565277141637694,
					34.443086492439534
				],
				[
					-11.021787677580619,
					51.505661647155875
				],
				[
					-19.92400080178038,
					36.24472486281343
				],
				[
					-19.182149708097086,
					52.14153401317003
				],
				[
					-25.116958457563555,
					35.71483122446807
				],
				[
					-24.481086091549287,
					45.35889544235124
				]
			]
		},
		{
			"type": "text",
			"version": 307,
			"versionNonce": 640132319,
			"isDeleted": false,
			"id": "f8IXykpW",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 472.1290938526073,
			"y": 1616.1278496681327,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 592.4971313476562,
			"height": 80,
			"seed": 27554425,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This effect is apparent for both first order and second order\nmethods of updating the gradient, but it is even more sensitive in \nsecond order derivative methods (Hessian) due to the matrix Multiplication\nH * g practically amplifying the errors",
			"rawText": "This effect is apparent for both first order and second order\nmethods of updating the gradient, but it is even more sensitive in \nsecond order derivative methods (Hessian) due to the matrix Multiplication\nH * g practically amplifying the errors",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This effect is apparent for both first order and second order\nmethods of updating the gradient, but it is even more sensitive in \nsecond order derivative methods (Hessian) due to the matrix Multiplication\nH * g practically amplifying the errors",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 312,
			"versionNonce": 1832443025,
			"isDeleted": false,
			"id": "LrUEClWUGTYFNkYZhl7B6",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 771.4176262611444,
			"y": 1546.9204593660165,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 186.04277099779256,
			"height": 1.0072101202238173,
			"seed": 728446649,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
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
					150.6581146120352,
					-0.2110057627619426
				],
				[
					186.04277099779256,
					0.7962043574618747
				]
			]
		},
		{
			"type": "text",
			"version": 794,
			"versionNonce": 1153282303,
			"isDeleted": false,
			"id": "dAAstCiN",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 978.7243085173883,
			"y": 1512.9396146562508,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 254.8404083251953,
			"height": 69.23187061761892,
			"seed": 792766521,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "J9G5osXz-Bf2-l01vR_XA",
					"type": "arrow"
				}
			],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 7.912213784870734,
			"fontFamily": 1,
			"text": "This bouncing direction is very sensitive to errors\nwhen the large discrepancy (Aka poor condition number)\nbetween the different eigen-basis of the hessian (Which are\njust it eigenvectors used as its basis).\nOur choice of gradient direction has projections along\neach eigenvector, and depending on its eigenvalue the direction\nwill be influenced by one of the eigenvectors more than the other",
			"rawText": "This bouncing direction is very sensitive to errors\nwhen the large discrepancy (Aka poor condition number)\nbetween the different eigen-basis of the hessian (Which are\njust it eigenvectors used as its basis).\nOur choice of gradient direction has projections along\neach eigenvector, and depending on its eigenvalue the direction\nwill be influenced by one of the eigenvectors more than the other",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This bouncing direction is very sensitive to errors\nwhen the large discrepancy (Aka poor condition number)\nbetween the different eigen-basis of the hessian (Which are\njust it eigenvectors used as its basis).\nOur choice of gradient direction has projections along\neach eigenvector, and depending on its eigenvalue the direction\nwill be influenced by one of the eigenvectors more than the other",
			"lineHeight": 1.25,
			"baseline": 65
		},
		{
			"type": "arrow",
			"version": 56,
			"versionNonce": 871441009,
			"isDeleted": false,
			"id": "J9G5osXz-Bf2-l01vR_XA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1245.0798292103539,
			"y": 1534.5229158288328,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 78.96781660946863,
			"height": 15.692322531368745,
			"seed": 1462500855,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "dAAstCiN",
				"focus": -0.6791965665062974,
				"gap": 11.515112367770428
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
					50.62039526247986,
					10.124079052495972
				],
				[
					78.96781660946863,
					15.692322531368745
				]
			]
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 419248415,
			"isDeleted": false,
			"id": "HAB4mVAV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 479.745263938382,
			"y": 1531.6899516875362,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 214.35714721679688,
			"height": 28.660602471057622,
			"seed": 135122647,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 11.464240988423049,
			"fontFamily": 1,
			"text": "This is a similar effect to choosing a\nhigh learning rate in SGD",
			"rawText": "This is a similar effect to choosing a\nhigh learning rate in SGD",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is a similar effect to choosing a\nhigh learning rate in SGD",
			"lineHeight": 1.25,
			"baseline": 24
		},
		{
			"type": "arrow",
			"version": 71,
			"versionNonce": 1801825361,
			"isDeleted": false,
			"id": "LtGxneqxznC6XB_ZWBnsG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1101.72007526064,
			"y": 1648.3770080699564,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 52.56358387541127,
			"height": 2.1542452407954897,
			"seed": 894516087,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "2eI63SkX",
				"focus": 0.17368443653631646,
				"gap": 3.9991451159778535
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
					-32.813503484556804,
					1.1615927546458806
				],
				[
					-52.56358387541127,
					2.1542452407954897
				]
			]
		},
		{
			"type": "arrow",
			"version": 322,
			"versionNonce": 676773183,
			"isDeleted": false,
			"id": "6qgrYpnwj3QuMdSukMoHc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 768.2716266704739,
			"y": 1716.923781056907,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 145.51648373047544,
			"height": 277.7938079846306,
			"seed": 1788293847,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "rwQi3psj0G64QfR0gg4Cq",
				"focus": -0.09597244753522881,
				"gap": 14.2640621537804
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
					17.939692772783815,
					210.9454008061648
				],
				[
					145.51648373047544,
					277.7938079846306
				]
			]
		},
		{
			"type": "text",
			"version": 301,
			"versionNonce": 997063217,
			"isDeleted": false,
			"id": "D1gqcZwO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 780.0358392446403,
			"y": 1756.922864450559,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 374.3687744140625,
			"height": 60,
			"seed": 1365318201,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can notice this in Gradient descent\nof the error function if we try to approximate\nit through second order taylor series expansion",
			"rawText": "We can notice this in Gradient descent\nof the error function if we try to approximate\nit through second order taylor series expansion",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can notice this in Gradient descent\nof the error function if we try to approximate\nit through second order taylor series expansion",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 1982512479,
			"isDeleted": false,
			"id": "NSuKI0nU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 414.94937189184,
			"y": 1757.0402006989902,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 344.2247314453125,
			"height": 60,
			"seed": 1734852087,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "g marks the Gradient vector (First order)\nH marks the second order derivative matrix\nEpsilon is the learning rate",
			"rawText": "g marks the Gradient vector (First order)\nH marks the second order derivative matrix\nEpsilon is the learning rate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "g marks the Gradient vector (First order)\nH marks the second order derivative matrix\nEpsilon is the learning rate",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 317,
			"versionNonce": 1693551633,
			"isDeleted": false,
			"id": "jlev2En0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1226.2315264633826,
			"y": 2041.592008050348,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 122,
			"height": 34,
			"seed": 83753,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "08c8a3d0a4d8e9cc62eb8d486378446243f9712d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 323,
			"versionNonce": 1170848127,
			"isDeleted": false,
			"id": "C5g4yr7T",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1039.737399965405,
			"y": 2002.297789751153,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 566.5772094726562,
			"height": 20,
			"seed": 834375767,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Gradient descent heads in the direction of the gradient with magnitude",
			"rawText": "Gradient descent heads in the direction of the gradient with magnitude",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gradient descent heads in the direction of the gradient with magnitude",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 262,
			"versionNonce": 535290353,
			"isDeleted": false,
			"id": "0Dx1FhIiQBLucJhr6erfy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1331.702613300333,
			"y": 2080.4687607987007,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.458553213874552,
			"height": 27.42080042084058,
			"seed": 1944040759,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.458553213874552,
					27.42080042084058
				]
			]
		},
		{
			"type": "text",
			"version": 291,
			"versionNonce": 477376927,
			"isDeleted": false,
			"id": "bL14ySgP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1276.0335002820188,
			"y": 2118.099433716663,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 129.42428588867188,
			"height": 60,
			"seed": 148648503,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "norm of gradient\nbut opposite\ndirection",
			"rawText": "norm of gradient\nbut opposite\ndirection",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "norm of gradient\nbut opposite\ndirection",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "line",
			"version": 350,
			"versionNonce": 962100177,
			"isDeleted": false,
			"id": "Oxe-a-bdH0tImBRD4jQhT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1197.6924888298001,
			"y": 2069.6184257021405,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 243.29228262347135,
			"height": 19.64039414412673,
			"seed": 217818359,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-243.29228262347135,
					19.64039414412673
				]
			]
		},
		{
			"type": "text",
			"version": 524,
			"versionNonce": 56272319,
			"isDeleted": false,
			"id": "Rlu5PKWs",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 751.4368602561012,
			"y": 2104.161529203352,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 308.128662109375,
			"height": 100,
			"seed": 1143473879,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_Gv1u1KXKxDI_BCFdgDPT",
					"type": "arrow"
				}
			],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "quadratic form representation\nof how that gradient vector\nis affected by all the other dimensions\nand their curvatures\n(Sensitivity along different directions)",
			"rawText": "quadratic form representation\nof how that gradient vector\nis affected by all the other dimensions\nand their curvatures\n(Sensitivity along different directions)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "quadratic form representation\nof how that gradient vector\nis affected by all the other dimensions\nand their curvatures\n(Sensitivity along different directions)",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 646,
			"versionNonce": 1901779377,
			"isDeleted": false,
			"id": "_Gv1u1KXKxDI_BCFdgDPT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 892.0198186753107,
			"y": 2211.7088823168806,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 129.3159740502383,
			"height": 44.62396329093053,
			"seed": 1845116217,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Rlu5PKWs",
				"focus": -0.005970337576447029,
				"gap": 7.547353113528516
			},
			"endBinding": {
				"elementId": "qr64a9nI",
				"focus": 0.1712427751921154,
				"gap": 16.948068266232667
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
					-9.729716652599564,
					38.67840126563215
				],
				[
					119.58625739763875,
					44.62396329093053
				]
			]
		},
		{
			"type": "text",
			"version": 747,
			"versionNonce": 161322463,
			"isDeleted": false,
			"id": "qr64a9nI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1028.5541443391821,
			"y": 2212.323416716516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 491.1530456542969,
			"height": 140,
			"seed": 1794307513,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "316JsZ40ADydvDXHSRX-8",
					"type": "arrow"
				},
				{
					"id": "_Gv1u1KXKxDI_BCFdgDPT",
					"type": "arrow"
				}
			],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "naively we usually assume this is significant\nbut as we observed this is not necessarily true\ndepending on the conditioning of the Hessian\nif the Hessian is well conditioned this term wont get affected\nmuch by the discrepancy of its eigenvalues and thus will be\nalmost insignificant, but if its ill conditioned this will be taken\ninto consideration",
			"rawText": "naively we usually assume this is significant\nbut as we observed this is not necessarily true\ndepending on the conditioning of the Hessian\nif the Hessian is well conditioned this term wont get affected\nmuch by the discrepancy of its eigenvalues and thus will be\nalmost insignificant, but if its ill conditioned this will be taken\ninto consideration",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "naively we usually assume this is significant\nbut as we observed this is not necessarily true\ndepending on the conditioning of the Hessian\nif the Hessian is well conditioned this term wont get affected\nmuch by the discrepancy of its eigenvalues and thus will be\nalmost insignificant, but if its ill conditioned this will be taken\ninto consideration",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "arrow",
			"version": 479,
			"versionNonce": 420903825,
			"isDeleted": false,
			"id": "316JsZ40ADydvDXHSRX-8",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1538.7070182919297,
			"y": 2270.674330364554,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 161.5605656554378,
			"height": 2.6652492574139615,
			"seed": 25479545,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "qr64a9nI",
				"focus": -0.21625261783420704,
				"gap": 18.999828298450666
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
					161.5605656554378,
					2.6652492574139615
				]
			]
		},
		{
			"type": "image",
			"version": 268,
			"versionNonce": 105742847,
			"isDeleted": false,
			"id": "r4jWrCRM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1747.781886023291,
			"y": 2246.7034074272906,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 98.73109456571443,
			"height": 57.82821253134702,
			"seed": 68348,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5e54cf31f3eb995cd97dd7e2439897fb9d17a83a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 747,
			"versionNonce": 1891819889,
			"isDeleted": false,
			"id": "N0mJW5Tj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1560.3064978651257,
			"y": 2313.282808652351,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 463.5208740234375,
			"height": 160,
			"seed": 1996779641,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "If the left term is more dominant, and our Hessian\nis ill conditioned then we require a very small epsilon\nto counteract the bouncing effect brought by the Hessian\nWHICH slows down our training a lot in order to achieve\na stable result\n\non the other hand if our Hessian is conditioned well epsilon\ncan be larger because the denominator is smaller",
			"rawText": "If the left term is more dominant, and our Hessian\nis ill conditioned then we require a very small epsilon\nto counteract the bouncing effect brought by the Hessian\nWHICH slows down our training a lot in order to achieve\na stable result\n\non the other hand if our Hessian is conditioned well epsilon\ncan be larger because the denominator is smaller",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If the left term is more dominant, and our Hessian\nis ill conditioned then we require a very small epsilon\nto counteract the bouncing effect brought by the Hessian\nWHICH slows down our training a lot in order to achieve\na stable result\n\non the other hand if our Hessian is conditioned well epsilon\ncan be larger because the denominator is smaller",
			"lineHeight": 1.25,
			"baseline": 154
		},
		{
			"type": "arrow",
			"version": 238,
			"versionNonce": 443214367,
			"isDeleted": false,
			"id": "F9m8xjdm92W3sOWGeDCKS",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1777.0573229986057,
			"y": 2206.0932852707356,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 159.18741955240262,
			"height": 122.33847984119848,
			"seed": 1942702745,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
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
					39.05987609387648,
					-109.07286154516487
				],
				[
					159.18741955240262,
					-122.33847984119848
				]
			]
		},
		{
			"type": "text",
			"version": 478,
			"versionNonce": 1168608081,
			"isDeleted": false,
			"id": "kqVLWNYv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1857.32013593783,
			"y": 2077.1219962815203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 380.41680908203125,
			"height": 140,
			"seed": 1522248855,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Rayleigh Quotient\nwhich is a function of a matrix and a vector\nThe range of this quotient for any matrix \nis called the spectrum of this matrix\nAnalyzing this spectrum is important because we\nwant to understand the range of this quotient\nfor different values of the gradient",
			"rawText": "Rayleigh Quotient\nwhich is a function of a matrix and a vector\nThe range of this quotient for any matrix \nis called the spectrum of this matrix\nAnalyzing this spectrum is important because we\nwant to understand the range of this quotient\nfor different values of the gradient",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Rayleigh Quotient\nwhich is a function of a matrix and a vector\nThe range of this quotient for any matrix \nis called the spectrum of this matrix\nAnalyzing this spectrum is important because we\nwant to understand the range of this quotient\nfor different values of the gradient",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "arrow",
			"version": 103,
			"versionNonce": 1927695935,
			"isDeleted": false,
			"id": "T3WpkYE48AlkgLppl9Zs1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -546.8730228129353,
			"y": 1822.9940160450947,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 124.44444444444446,
			"height": 0,
			"seed": 302575289,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "7lHesTeR3wCFEv-p7r_G2",
				"focus": -0.4285562034132237,
				"gap": 12.945235998965927
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
					-124.44444444444446,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 53,
			"versionNonce": 1344010545,
			"isDeleted": false,
			"id": "xZHLjZUA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -674.9922897468003,
			"y": 1764.105127156206,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 134.0163116455078,
			"height": 40,
			"seed": 1537925463,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Analyzing\nthe learning rate",
			"rawText": "Analyzing\nthe learning rate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Analyzing\nthe learning rate",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 139,
			"versionNonce": 1252011615,
			"isDeleted": false,
			"id": "4FbLs6aD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -993.5625074511088,
			"y": 1802.793610783827,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 303.42462158203125,
			"height": 60,
			"seed": 2139214103,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "our gradient descent converges\nif all our dimensions have the following\ncondition",
			"rawText": "our gradient descent converges\nif all our dimensions have the following\ncondition",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "our gradient descent converges\nif all our dimensions have the following\ncondition",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 120,
			"versionNonce": 1367845649,
			"isDeleted": false,
			"id": "I-KMSORQrr5ct9CFamEZV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -923.1659525916041,
			"y": 1869.072966854376,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 164.88136874515337,
			"height": 49.15331370138535,
			"seed": 294048921,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a34acdc6c5d0182da2e958532d8cd58bd4c8b66b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 140,
			"versionNonce": 745081471,
			"isDeleted": false,
			"id": "PUUAMIxEvrgV7cxMfeP_W",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -911.0361101313945,
			"y": 1909.324605625705,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 141.1318232591522,
			"height": 65.81932564552389,
			"seed": 1508559287,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392124,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8f79f3410a3574336075e97a0a30eee5df0b32f2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 184,
			"versionNonce": 1919033585,
			"isDeleted": false,
			"id": "rsyvI3FM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1016.1449176196429,
			"y": 1981.6163396625525,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 353.37677001953125,
			"height": 40,
			"seed": 142575897,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What is the best learning rate we could pick\nsuch that we converge to a solution?",
			"rawText": "What is the best learning rate we could pick\nsuch that we converge to a solution?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is the best learning rate we could pick\nsuch that we converge to a solution?",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 120,
			"versionNonce": 1963025055,
			"isDeleted": false,
			"id": "Xf4H-ZAHn3zXPdxlp8zPP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -988.5633678364843,
			"y": 2028.765120356536,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 301.4962432960629,
			"height": 58.26014363208945,
			"seed": 791981721,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3561f7eef12e4a998123166377e776af200c4a1f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 276,
			"versionNonce": 1613945553,
			"isDeleted": false,
			"id": "rgzvb5B0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1057.8980534577336,
			"y": 2091.582529897983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 447.824951171875,
			"height": 100,
			"seed": 1410908535,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "gBx-qxvxLueYdUujlTp12",
					"type": "arrow"
				}
			],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Picking a learning rate that matches the smallest\n1/alpha term such that it applies the condition alongside\nthat dimension and everything bigger than it\nthis results in 0.99 (best learning rate) scaled down\nby 1/max alpha",
			"rawText": "Picking a learning rate that matches the smallest\n1/alpha term such that it applies the condition alongside\nthat dimension and everything bigger than it\nthis results in 0.99 (best learning rate) scaled down\nby 1/max alpha",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Picking a learning rate that matches the smallest\n1/alpha term such that it applies the condition alongside\nthat dimension and everything bigger than it\nthis results in 0.99 (best learning rate) scaled down\nby 1/max alpha",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 173,
			"versionNonce": 354006719,
			"isDeleted": false,
			"id": "gBx-qxvxLueYdUujlTp12",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -844.6353762367273,
			"y": 2212.469231668223,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 155.1954137059172,
			"height": 107.63221428423367,
			"seed": 1083443193,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rgzvb5B0",
				"focus": 0.09212311600151782,
				"gap": 20.88670177024005
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
					16.20269892450824,
					107.63221428423367
				],
				[
					155.1954137059172,
					106.11774780677888
				]
			]
		},
		{
			"type": "text",
			"version": 328,
			"versionNonce": 730945713,
			"isDeleted": false,
			"id": "9grlC23d",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -648.7675276018798,
			"y": 2258.9104793328947,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 303.7926025390625,
			"height": 120,
			"seed": 1497649913,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "aZ3Ra874YNgTjW72Eaxw7",
					"type": "arrow"
				}
			],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "using this we can deduce\nthe amount of time it takes us\nto converge\nwhich is equivalent to\nthe convergence of the dimensions with\nthe lowest curvature",
			"rawText": "using this we can deduce\nthe amount of time it takes us\nto converge\nwhich is equivalent to\nthe convergence of the dimensions with\nthe lowest curvature",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "using this we can deduce\nthe amount of time it takes us\nto converge\nwhich is equivalent to\nthe convergence of the dimensions with\nthe lowest curvature",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "image",
			"version": 144,
			"versionNonce": 324175583,
			"isDeleted": false,
			"id": "kt9k-GSpuzRAXUgD47DWh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -634.0007493229059,
			"y": 2390.007433809052,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 279.13589877233073,
			"height": 37.73203282823657,
			"seed": 1244537753,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "92919d120a94f04c528e5f0e561625edb5cbdb1e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 254,
			"versionNonce": 1713707665,
			"isDeleted": false,
			"id": "aZ3Ra874YNgTjW72Eaxw7",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -332.57408014355127,
			"y": 2322.502852166741,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 99.66070255380845,
			"height": 1.4265481378088225,
			"seed": 1423487479,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9grlC23d",
				"focus": 0.01995384715036526,
				"gap": 12.400844919266035
			},
			"endBinding": {
				"elementId": "oy0uvdXX",
				"focus": 0.22596509194173361,
				"gap": 19.879371507476662
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
					99.66070255380845,
					1.4265481378088225
				]
			]
		},
		{
			"type": "text",
			"version": 334,
			"versionNonce": 1312576255,
			"isDeleted": false,
			"id": "oy0uvdXX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -213.03400608226616,
			"y": 2273.089593822888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 348.5287780761719,
			"height": 140,
			"seed": 1612279159,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "aZ3Ra874YNgTjW72Eaxw7",
					"type": "arrow"
				}
			],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "quantifying the difficulty of optimization\nis equivalent to the inverse of the speed\nof convergence of our error function\n(the lower the ratio the easier to optimize)\nIntroducing:\nThe condition number\n",
			"rawText": "quantifying the difficulty of optimization\nis equivalent to the inverse of the speed\nof convergence of our error function\n(the lower the ratio the easier to optimize)\nIntroducing:\nThe condition number\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "quantifying the difficulty of optimization\nis equivalent to the inverse of the speed\nof convergence of our error function\n(the lower the ratio the easier to optimize)\nIntroducing:\nThe condition number\n",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "image",
			"version": 36,
			"versionNonce": 10854513,
			"isDeleted": false,
			"id": "ltG3iN07",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -52.46383030156119,
			"y": 2399.5300337820613,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 43,
			"height": 33,
			"seed": 55535,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0e1d84d340af613e2599b0038ca32500f21b70ca",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 240,
			"versionNonce": 2119670559,
			"isDeleted": false,
			"id": "Qdd2Hdcq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -238.26744244915142,
			"y": 2444.8394878465556,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 413.4568786621094,
			"height": 80,
			"seed": 10689881,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "A6ldjbOsd2DnYOQ3vUoOS",
					"type": "arrow"
				}
			],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This analysis is a bit naive because it assumes\nthat our parameters do not interact and thus\nreducing this from a general case to a very specific\nform of error functions",
			"rawText": "This analysis is a bit naive because it assumes\nthat our parameters do not interact and thus\nreducing this from a general case to a very specific\nform of error functions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This analysis is a bit naive because it assumes\nthat our parameters do not interact and thus\nreducing this from a general case to a very specific\nform of error functions",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 129,
			"versionNonce": 1759144529,
			"isDeleted": false,
			"id": "A6ldjbOsd2DnYOQ3vUoOS",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -56.969059356770344,
			"y": 2539.982932472978,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 146.57575871866516,
			"height": 173.54569832289963,
			"seed": 2105483673,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Qdd2Hdcq",
				"focus": 0.12812356750872034,
				"gap": 15.143444626422479
			},
			"endBinding": {
				"elementId": "MDudiV0THduDj3KrYK4fr",
				"focus": -0.2565586848953302,
				"gap": 23.935535101093933
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
					3.5178182092480483,
					166.5100619044033
				],
				[
					146.57575871866516,
					173.54569832289963
				]
			]
		},
		{
			"type": "text",
			"version": 167,
			"versionNonce": 2014633791,
			"isDeleted": false,
			"id": "F6qGc4mi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -251.9204809289066,
			"y": 2596.2680238209455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 183.264404296875,
			"height": 100,
			"seed": 401188279,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Lets generalize this\nto every error function\nUsing taylor expansions\nnear some local minima\nsolution",
			"rawText": "Lets generalize this\nto every error function\nUsing taylor expansions\nnear some local minima\nsolution",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets generalize this\nto every error function\nUsing taylor expansions\nnear some local minima\nsolution",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "image",
			"version": 116,
			"versionNonce": 1738209329,
			"isDeleted": false,
			"id": "MDudiV0THduDj3KrYK4fr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 113.54223446298869,
			"y": 2644.8920676881808,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 589.4305451322075,
			"height": 128.2698595624493,
			"seed": 870798265,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "A6ldjbOsd2DnYOQ3vUoOS",
					"type": "arrow"
				},
				{
					"id": "IPY1Kj5MeGk48r2j20Hu2",
					"type": "arrow"
				}
			],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9ca7b64c74f622c1fd2bc3e8b5f39fc8bbb76e46",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 149,
			"versionNonce": 768909151,
			"isDeleted": false,
			"id": "eeY9v2InEq2O-jGH76POu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 150.7134715399462,
			"y": 2689.3187924567433,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.5097184130044639,
			"height": 53.52043336546831,
			"seed": 1140735575,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5097184130044639,
					-53.52043336546831
				]
			]
		},
		{
			"type": "text",
			"version": 91,
			"versionNonce": 1053739537,
			"isDeleted": false,
			"id": "EvaThEmR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 120.66108866375868,
			"y": 2608.1490855714433,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.3111572265625,
			"height": 23.79976579209005,
			"seed": 1374624279,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 9.51990631683602,
			"fontFamily": 1,
			"text": "overall error\nfunction",
			"rawText": "overall error\nfunction",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "overall error\nfunction",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "line",
			"version": 46,
			"versionNonce": 1910987647,
			"isDeleted": false,
			"id": "UM67o1TkO4BUqh-eF88i5",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 214.39823662734617,
			"y": 2681.058662906404,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.071879799679493,
			"height": 43.1018594627767,
			"seed": 1182494743,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.071879799679493,
					-43.1018594627767
				]
			]
		},
		{
			"type": "text",
			"version": 191,
			"versionNonce": 124608497,
			"isDeleted": false,
			"id": "lswDZ2a2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 203.7249429990472,
			"y": 2574.7593180309077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 80.97688293457031,
			"height": 59.34093511000049,
			"seed": 725136345,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 9.494549617600077,
			"fontFamily": 1,
			"text": "error of that\nlocal minima\n(How bad it is\nin comparsion to\nthe global minima)",
			"rawText": "error of that\nlocal minima\n(How bad it is\nin comparsion to\nthe global minima)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "error of that\nlocal minima\n(How bad it is\nin comparsion to\nthe global minima)",
			"lineHeight": 1.25,
			"baseline": 55
		},
		{
			"type": "line",
			"version": 32,
			"versionNonce": 2022544287,
			"isDeleted": false,
			"id": "WmVq-2ZV6b1KiV37ORLhI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 611.7347146905745,
			"y": 2678.6594347724413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.43748631965866025,
			"height": 54.24830363767933,
			"seed": 166784153,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.43748631965866025,
					-54.24830363767933
				]
			]
		},
		{
			"type": "text",
			"version": 160,
			"versionNonce": 1333672401,
			"isDeleted": false,
			"id": "8CD8ODII",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 548.4559221427645,
			"y": 2575.8447698149857,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 121.69734191894531,
			"height": 44.255872329946094,
			"seed": 1335402167,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 11.801565954652292,
			"fontFamily": 1,
			"text": "Often insignificant or\nunnecessary for our\napproximation",
			"rawText": "Often insignificant or\nunnecessary for our\napproximation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Often insignificant or\nunnecessary for our\napproximation",
			"lineHeight": 1.25,
			"baseline": 39
		},
		{
			"type": "line",
			"version": 85,
			"versionNonce": 435668927,
			"isDeleted": false,
			"id": "9Qfq4EdRKVKkuwv0Ca1Yh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 328.79930293648306,
			"y": 2738.9070920955523,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.71912302643409,
			"height": 104.7734306933562,
			"seed": 1207459223,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					69.71912302643409,
					104.7734306933562
				]
			]
		},
		{
			"type": "text",
			"version": 131,
			"versionNonce": 2014894001,
			"isDeleted": false,
			"id": "B0Le3hvQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 365.9194953323622,
			"y": 2851.7231811330284,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.05734252929688,
			"height": 28.45191088918789,
			"seed": 26441495,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 11.380764355675156,
			"fontFamily": 1,
			"text": "the gradient\ng",
			"rawText": "the gradient\ng",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the gradient\ng",
			"lineHeight": 1.25,
			"baseline": 24
		},
		{
			"type": "line",
			"version": 84,
			"versionNonce": 1413904351,
			"isDeleted": false,
			"id": "oa3hYmA9LdE0iosFJLVEE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 495.11251820065814,
			"y": 2742.4125228622447,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 84.51983070802345,
			"height": 100.87850761925347,
			"seed": 90474265,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-84.51983070802345,
					100.87850761925347
				]
			]
		},
		{
			"type": "line",
			"version": 38,
			"versionNonce": 1399110033,
			"isDeleted": false,
			"id": "9sca6OVEW28eXIXOtyr7P",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 426.5618720964548,
			"y": 2779.8037843736283,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 71.2770922560751,
			"height": 33.49633843728134,
			"seed": 536707255,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					71.2770922560751,
					33.49633843728134
				]
			]
		},
		{
			"type": "text",
			"version": 146,
			"versionNonce": 227156991,
			"isDeleted": false,
			"id": "PnsL0XPS",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 488.637081152962,
			"y": 2820.310984344294,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 93.88658142089844,
			"height": 50.917907713368535,
			"seed": 268031607,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 10.183581542673707,
			"fontFamily": 1,
			"text": "Hessian matrix\nH\nof size\nnum of parameters",
			"rawText": "Hessian matrix\nH\nof size\nnum of parameters",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hessian matrix\nH\nof size\nnum of parameters",
			"lineHeight": 1.25,
			"baseline": 46
		},
		{
			"type": "line",
			"version": 58,
			"versionNonce": 43605873,
			"isDeleted": false,
			"id": "bgZP8mVFyCdv1Co90MsAw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 410.9300933571516,
			"y": 2638.895904044088,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.0692853445665378,
			"height": 58.4542655029727,
			"seed": 1526268055,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.0692853445665378,
					-58.4542655029727
				]
			]
		},
		{
			"type": "text",
			"version": 726,
			"versionNonce": 365120543,
			"isDeleted": false,
			"id": "9BVn7FFx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 266.58526061791673,
			"y": 2424.1379977422466,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 276.7139587402344,
			"height": 149.27319532410903,
			"seed": 697456695,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "cUIGAi1oKyzyB_Fc_kecT",
					"type": "arrow"
				}
			],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 11.941855625928723,
			"fontFamily": 1,
			"text": "Hessian based local approximation of the error\naka\nquadratic form representation\ng^T H g\nof how the gradient is\ninfluenced by the curvature\nor\nthe effect/sensitvity of an infinitely\nsmall step in the direction of\nthe gradient",
			"rawText": "Hessian based local approximation of the error\naka\nquadratic form representation\ng^T H g\nof how the gradient is\ninfluenced by the curvature\nor\nthe effect/sensitvity of an infinitely\nsmall step in the direction of\nthe gradient",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hessian based local approximation of the error\naka\nquadratic form representation\ng^T H g\nof how the gradient is\ninfluenced by the curvature\nor\nthe effect/sensitvity of an infinitely\nsmall step in the direction of\nthe gradient",
			"lineHeight": 1.25,
			"baseline": 144
		},
		{
			"type": "arrow",
			"version": 412,
			"versionNonce": 335432017,
			"isDeleted": false,
			"id": "cX67SmWKLVC-qK75tlKAG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 273.58843211480865,
			"y": 2536.691382047295,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 52.2016413874386,
			"height": 148.3066974219414,
			"seed": 1392195191,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "cB5MGj91",
				"focus": 0.6260873370512807,
				"gap": 14.630395505414526
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
					-52.2016413874386,
					-70.02673570531942
				],
				[
					-35.26510623854324,
					-148.3066974219414
				]
			]
		},
		{
			"type": "text",
			"version": 319,
			"versionNonce": 1759670335,
			"isDeleted": false,
			"id": "cB5MGj91",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 223.4387858414628,
			"y": 2311.9665888965947,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 154.68295288085938,
			"height": 61.78770022334439,
			"seed": 2118082007,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "cX67SmWKLVC-qK75tlKAG",
					"type": "arrow"
				}
			],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 9.886032035735102,
			"fontFamily": 1,
			"text": "This is just the definition of\na derivative of a function\ntaking an infinitely small step in\nx direction how will f(x) be\naffected",
			"rawText": "This is just the definition of\na derivative of a function\ntaking an infinitely small step in\nx direction how will f(x) be\naffected",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is just the definition of\na derivative of a function\ntaking an infinitely small step in\nx direction how will f(x) be\naffected",
			"lineHeight": 1.25,
			"baseline": 57
		},
		{
			"type": "arrow",
			"version": 268,
			"versionNonce": 1626011441,
			"isDeleted": false,
			"id": "IPY1Kj5MeGk48r2j20Hu2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 711.4110567072253,
			"y": 2712.61986686723,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 276.6367692805321,
			"height": 4.496624617967427,
			"seed": 1484218425,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "up3joeiZ",
				"focus": -1.3714035423821456,
				"gap": 19.87195525019763
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
					276.6367692805321,
					-4.496624617967427
				]
			]
		},
		{
			"type": "text",
			"version": 165,
			"versionNonce": 818417759,
			"isDeleted": false,
			"id": "up3joeiZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 731.2830119574229,
			"y": 2727.801471753622,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 214.8324737548828,
			"height": 80,
			"seed": 1448760791,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "IPY1Kj5MeGk48r2j20Hu2",
					"type": "arrow"
				}
			],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Lets diagonalize the\nHessian matrix for ease of\ncomputation\n",
			"rawText": "Lets diagonalize the\nHessian matrix for ease of\ncomputation\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets diagonalize the\nHessian matrix for ease of\ncomputation\n",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 48,
			"versionNonce": 734456081,
			"isDeleted": false,
			"id": "yCdYnimmurQ0kjYY0Dppn",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 875.4636033453221,
			"y": 2791.782112039516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.796907433943034,
			"height": 113.44236261856395,
			"seed": 189526871,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
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
					28.796907433943034,
					46.2495786060299
				],
				[
					6.9810684688345646,
					113.44236261856395
				]
			]
		},
		{
			"type": "text",
			"version": 40,
			"versionNonce": 121941119,
			"isDeleted": false,
			"id": "0wrYuaVo",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 791.6560382344928,
			"y": 2924.4224129473755,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 169.3603973388672,
			"height": 20,
			"seed": 362656345,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": "[[Diagonalizing]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What is diagonalizing?",
			"rawText": "What is diagonalizing?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is diagonalizing?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 144,
			"versionNonce": 2114559729,
			"isDeleted": false,
			"id": "DbUja1qG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1020.4292225802419,
			"y": 2696.322034062725,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 148,
			"height": 34,
			"seed": 96892,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8fd0bc8001ecb8b65b5bfd2f5361af66ee853620",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 100,
			"versionNonce": 2014889119,
			"isDeleted": false,
			"id": "m4P5La6ls7dTZRocQqQ-d",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1112.2345894893208,
			"y": 2697.946382200024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 53.31594835203646,
			"height": 40.73205992112116,
			"seed": 1256964025,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-53.31594835203646,
					-40.73205992112116
				]
			]
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 1178245329,
			"isDeleted": false,
			"id": "uCz9ZEaG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 994.1855304765697,
			"y": 2630.721925582239,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 98.00650024414062,
			"height": 22.7814709744434,
			"seed": 1628091767,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 9.112588389777361,
			"fontFamily": 1,
			"text": "V is the eigenvector\nmatrix of the Hessian",
			"rawText": "V is the eigenvector\nmatrix of the Hessian",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V is the eigenvector\nmatrix of the Hessian",
			"lineHeight": 1.25,
			"baseline": 19
		},
		{
			"type": "line",
			"version": 50,
			"versionNonce": 1123342527,
			"isDeleted": false,
			"id": "ccZrsqgU6ypUK9bp4GIg1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1131.4415770944022,
			"y": 2696.952917323899,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.61656405029089,
			"height": 83.4510495944919,
			"seed": 1818593815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.61656405029089,
					-83.4510495944919
				]
			]
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 905008817,
			"isDeleted": false,
			"id": "lFxhXwjY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1083.201874546312,
			"y": 2576.1226070743733,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 70.98054504394531,
			"height": 31.189518592377546,
			"seed": 398127673,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 8.317204957967345,
			"fontFamily": 1,
			"text": "D is the diagonal\neigenvalue matrix\nof the hessian",
			"rawText": "D is the diagonal\neigenvalue matrix\nof the hessian",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "D is the diagonal\neigenvalue matrix\nof the hessian",
			"lineHeight": 1.25,
			"baseline": 28
		},
		{
			"type": "line",
			"version": 45,
			"versionNonce": 1568237791,
			"isDeleted": false,
			"id": "e4knji7sfU1jJ10_5HS-H",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1147.0058601536923,
			"y": 2695.297142530357,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 52.65363843461978,
			"height": 55.302878104286265,
			"seed": 569594999,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					52.65363843461978,
					-55.302878104286265
				]
			]
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 1607817361,
			"isDeleted": false,
			"id": "4gPymu7Q",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1186.0904582401167,
			"y": 2619.4626569861557,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.79443359375,
			"height": 15.494533055585642,
			"seed": 1332055065,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 6.197813222234257,
			"fontFamily": 1,
			"text": "transposed eigenvector\nmatrix of the Hessian",
			"rawText": "transposed eigenvector\nmatrix of the Hessian",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "transposed eigenvector\nmatrix of the Hessian",
			"lineHeight": 1.25,
			"baseline": 13
		},
		{
			"type": "image",
			"version": 50,
			"versionNonce": 892794111,
			"isDeleted": false,
			"id": "ik8uFISK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1024.0184701464188,
			"y": 2747.3370024226538,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 132,
			"height": 34,
			"seed": 99055,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f5bc95d8509fd365e3d0f80e2999092a40c318d8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 200,
			"versionNonce": 362684017,
			"isDeleted": false,
			"id": "SWDunZBsncK-t-kCUonbF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1158.4278208169626,
			"y": 2738.8292656593662,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 191.7792821546229,
			"height": 46.19893071511924,
			"seed": 757007481,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7dd6ceee7adec4ef05286c1dfb841de9eb774b2a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 56,
			"versionNonce": 833486111,
			"isDeleted": false,
			"id": "z3jccqPw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1024.2443390041326,
			"y": 2747.786216204939,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 13.456024169921875,
			"height": 20,
			"seed": 958770713,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "~",
			"rawText": "~",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "~",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 81,
			"versionNonce": 101918801,
			"isDeleted": false,
			"id": "Y4Sjp6rm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1020.8761907369735,
			"y": 2696.756046405001,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 13.456024169921875,
			"height": 20,
			"seed": 1129021047,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "~",
			"rawText": "~",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "~",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 446,
			"versionNonce": 1984889151,
			"isDeleted": false,
			"id": "qtBCc841",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 954.2304563986779,
			"y": 2793.4243724291587,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 521.1530151367188,
			"height": 140,
			"seed": 736339289,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-17U3pnXDwWBj6qtNHXLs",
					"type": "arrow"
				}
			],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This has a very similar structure to what we anaylzed before\n\n\nbut as you can notice now that we analyze the projection of the\ngradient onto our eigenvectors\nAND\nthe eigenvalues are actually the \"coefficients\" alpha",
			"rawText": "This has a very similar structure to what we anaylzed before\n\n\nbut as you can notice now that we analyze the projection of the\ngradient onto our eigenvectors\nAND\nthe eigenvalues are actually the \"coefficients\" alpha",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This has a very similar structure to what we anaylzed before\n\n\nbut as you can notice now that we analyze the projection of the\ngradient onto our eigenvectors\nAND\nthe eigenvalues are actually the \"coefficients\" alpha",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "line",
			"version": 39,
			"versionNonce": 453768753,
			"isDeleted": false,
			"id": "7O6FAiiqwFHdOS6Y5FD4t",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1302.8831661548952,
			"y": 2737.24417940455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.397551355175892,
			"height": 35.32942705205869,
			"seed": 584095671,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.397551355175892,
					-35.32942705205869
				]
			]
		},
		{
			"type": "text",
			"version": 166,
			"versionNonce": 1685750111,
			"isDeleted": false,
			"id": "VU8EfBEg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1252.559388458703,
			"y": 2661.4439025350525,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 115.78474426269531,
			"height": 37.17229301583329,
			"seed": 1928414457,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 9.912611470888878,
			"fontFamily": 1,
			"text": "projection of gradient\nonto eigenvector of the\nHessian",
			"rawText": "projection of gradient\nonto eigenvector of the\nHessian",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "projection of gradient\nonto eigenvector of the\nHessian",
			"lineHeight": 1.25,
			"baseline": 33
		},
		{
			"type": "image",
			"version": 441,
			"versionNonce": 393218065,
			"isDeleted": false,
			"id": "MrBbGkcfKkCNwEXO6xtK4",
			"fillStyle": "cross-hatch",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1146.7366922551626,
			"y": 2813.152920872058,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 127.77522295301699,
			"height": 40.426059239372606,
			"seed": 358693079,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e6cb1c94291a121e039ecd09d75169e8ba0778d0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 53,
			"versionNonce": 1568734591,
			"isDeleted": false,
			"id": "-17U3pnXDwWBj6qtNHXLs",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1192.4531712197922,
			"y": 2948.397901186474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.704851505631268,
			"height": 100.07950570835146,
			"seed": 757282999,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "qtBCc841",
				"focus": 0.09391749504413802,
				"gap": 14.973528757315307
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
					2.704851505631268,
					100.07950570835146
				]
			]
		},
		{
			"type": "rectangle",
			"version": 88,
			"versionNonce": 1966530033,
			"isDeleted": false,
			"id": "V21VpGkkpwllUozLlCRbU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 979.6396987443395,
			"y": 3082.7759987949767,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 432.77624090098107,
			"height": 175.81534786602333,
			"seed": 689097975,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "2XMRIeXKzFMZqpsc_q62P",
					"type": "arrow"
				}
			],
			"updated": 1706890392125,
			"link": null,
			"locked": false
		},
		{
			"type": "image",
			"version": 161,
			"versionNonce": 1151530399,
			"isDeleted": false,
			"id": "HncsxyBfrOXSArw5MrWMK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 991.4567683132541,
			"y": 3112.5567708967505,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 410.6109250352427,
			"height": 88.0730679785738,
			"seed": 1576968409,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1eeea0f618cae4cb003d8efd81b3325ad6674625",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 815,
			"versionNonce": 57145297,
			"isDeleted": false,
			"id": "2XMRIeXKzFMZqpsc_q62P",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 957.9453105174937,
			"y": 3174.717966694536,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 488.5157467256487,
			"height": 7.455281743130854,
			"seed": 1522416375,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "V21VpGkkpwllUozLlCRbU",
				"focus": -0.08406636029768136,
				"gap": 21.69438822684583
			},
			"endBinding": {
				"elementId": "7EYuabDuT0EuYrYIL_tCL",
				"focus": -0.8115307582399971,
				"gap": 11.162281420842078
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
					-488.5157467256487,
					-7.455281743130854
				]
			]
		},
		{
			"type": "text",
			"version": 613,
			"versionNonce": 1091627455,
			"isDeleted": false,
			"id": "CRwcDqgs",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 472.6700928254361,
			"y": 3019.884633361203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 493.21710205078125,
			"height": 100,
			"seed": 1020370425,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "In larger neural networks\ncomputing the Hessian is quite a demanding task thus\nwe cannot always extract the condition number and optimize\naccordingly! through the analysis we can take steps that help\nshape and condition the error function",
			"rawText": "In larger neural networks\ncomputing the Hessian is quite a demanding task thus\nwe cannot always extract the condition number and optimize\naccordingly! through the analysis we can take steps that help\nshape and condition the error function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In larger neural networks\ncomputing the Hessian is quite a demanding task thus\nwe cannot always extract the condition number and optimize\naccordingly! through the analysis we can take steps that help\nshape and condition the error function",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "text",
			"version": 76,
			"versionNonce": 1142609329,
			"isDeleted": false,
			"id": "lg10QQ73",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -374.21795969374966,
			"y": 3018.429918141781,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 428.62579345703125,
			"height": 35,
			"seed": 136253303,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Optimizing the Condition Number",
			"rawText": "Optimizing the Condition Number",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Optimizing the Condition Number",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 139,
			"versionNonce": 1072388575,
			"isDeleted": false,
			"id": "k6p3xf8r",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -322.2848847425778,
			"y": 3136.929918141781,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 328.7596435546875,
			"height": 50,
			"seed": 946006233,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Center and normalize the data\nFrom linear models we can see",
			"rawText": "1) Center and normalize the data\nFrom linear models we can see",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Center and normalize the data\nFrom linear models we can see",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 162,
			"versionNonce": 175568785,
			"isDeleted": false,
			"id": "xq1_GpuFZWkc80zqc5jTc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -502.494019313084,
			"y": 3200.17267597189,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 717,
			"height": 188.64214046822744,
			"seed": 1780963161,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0ba209b9aa087be8fec1e94bc4e0f557a89d600",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 288,
			"versionNonce": 910345727,
			"isDeleted": false,
			"id": "1yoHUl5qhD8awwHLqioLC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -504.994019313084,
			"y": 3199.8148164401173,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 720,
			"height": 189.99999999999994,
			"seed": 562912825,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 90,
			"versionNonce": 1488182641,
			"isDeleted": false,
			"id": "SYimaUQPzkIo1qQGjU4Sv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 64.89805740494171,
			"y": 3310.337586288414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 22.934497769907694,
			"height": 38.49719268520221,
			"seed": 1300304697,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					22.934497769907694,
					-38.49719268520221
				]
			]
		},
		{
			"type": "line",
			"version": 63,
			"versionNonce": 588754463,
			"isDeleted": false,
			"id": "GJAWhEEGzyzWpCWL8UAC8",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 132.88246150859652,
			"y": 3299.6894266095283,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 39.31628189127025,
			"height": 23.75358697597585,
			"seed": 101703289,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-39.31628189127025,
					-23.75358697597585
				]
			]
		},
		{
			"type": "text",
			"version": 87,
			"versionNonce": 2115569489,
			"isDeleted": false,
			"id": "zgEAtMwK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 16.62805198827209,
			"y": 3221.9614167966474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 135.85629272460938,
			"height": 40,
			"seed": 410553911,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "goes away in 2nd\nderivative",
			"rawText": "goes away in 2nd\nderivative",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "goes away in 2nd\nderivative",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 330,
			"versionNonce": 1364890175,
			"isDeleted": false,
			"id": "nYsnZO8u",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -559.201966928987,
			"y": 3406.58409654512,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 816.4391479492188,
			"height": 100,
			"seed": 732671543,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The Hessian is influenced by the mean and covariance of the data\nThus if we can center our data (aka set it to 0) our condition number is lower\nand if we normalize the data aka make the covariance closer to the identity, our\ncondition number is also lowered!",
			"rawText": "The Hessian is influenced by the mean and covariance of the data\nThus if we can center our data (aka set it to 0) our condition number is lower\nand if we normalize the data aka make the covariance closer to the identity, our\ncondition number is also lowered!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The Hessian is influenced by the mean and covariance of the data\nThus if we can center our data (aka set it to 0) our condition number is lower\nand if we normalize the data aka make the covariance closer to the identity, our\ncondition number is also lowered!",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 120,
			"versionNonce": 1962800433,
			"isDeleted": false,
			"id": "dVLD1mwP29aZSnz1pdf7w",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -273.5592546291849,
			"y": 3520.696107521017,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 247.75039324409155,
			"height": 189.91816888451976,
			"seed": 1714025817,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "71f36b5e0b7710cf10a5898e1a0b3ad30d163189",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 71,
			"versionNonce": 1508635231,
			"isDeleted": false,
			"id": "EvCGystwLy27oVlaMrSwD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -273.69204416729343,
			"y": 3522.6491133504865,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 248.9016113538392,
			"height": 184.55854716954627,
			"seed": 2079522745,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 109,
			"versionNonce": 13248273,
			"isDeleted": false,
			"id": "8yiUtWVz",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -429.8142601852346,
			"y": 3809.7310900440725,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 544.6994018554688,
			"height": 50,
			"seed": 1272431641,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2) Use centered activations\nThe general formula for The hessian matrix is given by",
			"rawText": "2) Use centered activations\nThe general formula for The hessian matrix is given by",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2) Use centered activations\nThe general formula for The hessian matrix is given by",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 76,
			"versionNonce": 1704742527,
			"isDeleted": false,
			"id": "ndVVfMFf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -348.658996498875,
			"y": 3866.0982767159803,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 378.49220063216825,
			"height": 52.63798816738764,
			"seed": 67256,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d03726ba3d2fa5d47d1ea179c11b3c80c86c4670",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 95,
			"versionNonce": 200613105,
			"isDeleted": false,
			"id": "jNdVtKrEYgEgfwBAQCGq7",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -386.589884903142,
			"y": 3938.2085568863263,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 473.7229541764642,
			"height": 141.23417267372847,
			"seed": 206336823,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d4a1430361e8a8ad2a0713aef89ef4ec070a0494",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 114,
			"versionNonce": 791422623,
			"isDeleted": false,
			"id": "h0dv5EJvxS0-VfPZQH7TZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -388.56176423231034,
			"y": 3939.9844761526087,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 473.9522738356767,
			"height": 137.0152937088592,
			"seed": 1020816695,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 55,
			"versionNonce": 1174820561,
			"isDeleted": false,
			"id": "hr9NnQnrsN3DUdvRrLTYD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -128.90649192419698,
			"y": 3988.0431328157983,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.90174485302367,
			"height": 35.17144055204881,
			"seed": 230377111,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					38.90174485302367,
					35.17144055204881
				]
			]
		},
		{
			"type": "text",
			"version": 174,
			"versionNonce": 1162607295,
			"isDeleted": false,
			"id": "bf5WtazM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -110.27419504798007,
			"y": 4032.2624562855394,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 128.4464111328125,
			"height": 30.00449004760887,
			"seed": 3485687,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 8.001197346029032,
			"fontFamily": 1,
			"text": "derivative of the neural network\noutput w.r.t the pre-activation\nof neuron k",
			"rawText": "derivative of the neural network\noutput w.r.t the pre-activation\nof neuron k",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "derivative of the neural network\noutput w.r.t the pre-activation\nof neuron k",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "text",
			"version": 409,
			"versionNonce": 26563761,
			"isDeleted": false,
			"id": "wzAHkOSk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -501.08553717313396,
			"y": 4091.4652279918414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 663.2653198242188,
			"height": 100,
			"seed": 2055224215,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is also dependent on the activations of each neuron\nMeaning we should also normalize the output data of each neuron similar to tip 1.\nThis can actually be done through the activation function itself by choosing\na function that is centered and somewhat linear such that the outputs wont drift\naway/explode/vanish if theyre skewed in a certain direction",
			"rawText": "This is also dependent on the activations of each neuron\nMeaning we should also normalize the output data of each neuron similar to tip 1.\nThis can actually be done through the activation function itself by choosing\na function that is centered and somewhat linear such that the outputs wont drift\naway/explode/vanish if theyre skewed in a certain direction",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is also dependent on the activations of each neuron\nMeaning we should also normalize the output data of each neuron similar to tip 1.\nThis can actually be done through the activation function itself by choosing\na function that is centered and somewhat linear such that the outputs wont drift\naway/explode/vanish if theyre skewed in a certain direction",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "image",
			"version": 127,
			"versionNonce": 211569375,
			"isDeleted": false,
			"id": "deOsXX9IuBXPlRnOqZT_2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -496.84990081668377,
			"y": 4205.930686385209,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 388.274780661677,
			"height": 157.5330057768502,
			"seed": 1954386711,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xReEpL9w-ibtnSksyiAeA",
					"type": "arrow"
				}
			],
			"updated": 1706890392125,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c69aed6c37f4843176244af593dedd57176f935e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 290,
			"versionNonce": 1380554385,
			"isDeleted": false,
			"id": "gJX-uoyKUOqKCwTlLt4_c",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -110.96710803425168,
			"y": 4205.930686000001,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 350.0040245490005,
			"height": 157.5330057016446,
			"seed": 319466873,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xReEpL9w-ibtnSksyiAeA",
					"type": "arrow"
				}
			],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "371e48ad858d5cb7613cfe638d643a8f74a8786d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 105,
			"versionNonce": 28153599,
			"isDeleted": false,
			"id": "IoS16m-X3xIGFxYZf0gEF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -494.9179263321647,
			"y": 4207.592928369323,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 730.240915834284,
			"height": 148.39120214814375,
			"seed": 810528089,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 35,
			"versionNonce": 1792711793,
			"isDeleted": false,
			"id": "27iw6OKsqAOPBQBf01muu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -388.4706838467383,
			"y": 4283.150191721089,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 16.933491162663472,
			"height": 13.454006677185134,
			"seed": 671295351,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.933491162663472,
					13.454006677185134
				]
			]
		},
		{
			"type": "line",
			"version": 34,
			"versionNonce": 989880095,
			"isDeleted": false,
			"id": "e2IXR4Tig2NfbiwgRdPE3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -373.1609521106316,
			"y": 4281.526432294532,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 13.222041044819434,
			"height": 15.309731736107096,
			"seed": 2125637049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-13.222041044819434,
					15.309731736107096
				]
			]
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 990897745,
			"isDeleted": false,
			"id": "ZW2hTBMJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -404.6838025345949,
			"y": 4306.611682819126,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 58.10008239746094,
			"height": 11.616275005703727,
			"seed": 920560375,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 9.293020004562981,
			"fontFamily": 1,
			"text": "not centered",
			"rawText": "not centered",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "not centered",
			"lineHeight": 1.25,
			"baseline": 8
		},
		{
			"type": "line",
			"version": 15,
			"versionNonce": 721756991,
			"isDeleted": false,
			"id": "RosFX9kinqXPrhqhXWvV8",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -268.544451913902,
			"y": 4266.448666190791,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 7.886831500418623,
			"height": 9.974522191705546,
			"seed": 741406361,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					7.886831500418623,
					9.974522191705546
				]
			]
		},
		{
			"type": "line",
			"version": 40,
			"versionNonce": 1304491057,
			"isDeleted": false,
			"id": "tN9KUrH7x9Lvt_MzMOGvJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -261.1215516782139,
			"y": 4275.727291485401,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 25.28425392781267,
			"height": 22.268700707064454,
			"seed": 1310622391,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					25.28425392781267,
					-22.268700707064454
				]
			]
		},
		{
			"type": "line",
			"version": 22,
			"versionNonce": 572285791,
			"isDeleted": false,
			"id": "sk8CAG6HDKKd9qRCMKhXu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -171.11888632049548,
			"y": 4254.618418940163,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 11.366315985897444,
			"height": 10.206487824070791,
			"seed": 944919351,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-11.366315985897444,
					10.206487824070791
				]
			]
		},
		{
			"type": "line",
			"version": 15,
			"versionNonce": 1725253137,
			"isDeleted": false,
			"id": "OK6YWXzeX7GA4RsglkR0x",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -178.77375218854885,
			"y": 4256.24217836672,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 6.72700333859234,
			"height": 9.27862529461072,
			"seed": 727035545,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.72700333859234,
					9.27862529461072
				]
			]
		},
		{
			"type": "text",
			"version": 75,
			"versionNonce": 278306687,
			"isDeleted": false,
			"id": "JDGjKYwL",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -250.44014848438206,
			"y": 4272.711738264653,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 30.326446533203125,
			"height": 9.097615278832777,
			"seed": 1399278263,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 7.2780922230662215,
			"fontFamily": 1,
			"text": "centered",
			"rawText": "centered",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "centered",
			"lineHeight": 1.25,
			"baseline": 6
		},
		{
			"type": "text",
			"version": 49,
			"versionNonce": 1631869937,
			"isDeleted": false,
			"id": "UxsRMkhK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -185.5288002172054,
			"y": 4269.837673736156,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 29.724441528320312,
			"height": 11.043817277869387,
			"seed": 869929751,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 8.83505382229551,
			"fontFamily": 1,
			"text": "Skewed",
			"rawText": "Skewed",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Skewed",
			"lineHeight": 1.25,
			"baseline": 8
		},
		{
			"type": "arrow",
			"version": 39,
			"versionNonce": 146036639,
			"isDeleted": false,
			"id": "xReEpL9w-ibtnSksyiAeA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -139.47333293338193,
			"y": 4276.482753281795,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 34.04069579204756,
			"height": 0.6609843843116323,
			"seed": 437333559,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "gJX-uoyKUOqKCwTlLt4_c",
				"focus": -0.05188145873125321,
				"gap": 28.506224899130245
			},
			"endBinding": {
				"elementId": "deOsXX9IuBXPlRnOqZT_2",
				"focus": 0.13792898322854,
				"gap": 3.1424830136723756
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
					34.04069579204756,
					0.6609843843116323
				]
			]
		},
		{
			"type": "text",
			"version": 82,
			"versionNonce": 1293268433,
			"isDeleted": false,
			"id": "rKJ9fjgs",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 106.62870821125682,
			"y": 4308.7948241752665,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 91.0938720703125,
			"height": 29.18871422732884,
			"seed": 1647988695,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 11.675485690931536,
			"fontFamily": 1,
			"text": "The output will\nnot be centered",
			"rawText": "The output will\nnot be centered",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The output will\nnot be centered",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 254,
			"versionNonce": 10881983,
			"isDeleted": false,
			"id": "hBSwAnt0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -565.8319351889487,
			"y": 4442.044839004869,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 766.5391845703125,
			"height": 100,
			"seed": 571630007,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3) Number of neurons\nThe number of neurons affects the variance of the neuron outputs\nwe want that variance to also equal 1 for an identity-like covariance output\nUse similar number of neurons per layer determined by",
			"rawText": "3) Number of neurons\nThe number of neurons affects the variance of the neuron outputs\nwe want that variance to also equal 1 for an identity-like covariance output\nUse similar number of neurons per layer determined by",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3) Number of neurons\nThe number of neurons affects the variance of the neuron outputs\nwe want that variance to also equal 1 for an identity-like covariance output\nUse similar number of neurons per layer determined by",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 125,
			"versionNonce": 1298191281,
			"isDeleted": false,
			"id": "kX14wMJn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -286.10006650829564,
			"y": 4558.840423348292,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 255.54207618990267,
			"height": 48.2690588358705,
			"seed": 29508,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bcb30d90e97f40e23a15510eeda5b98cc6dbe2de",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 568,
			"versionNonce": 1418476511,
			"isDeleted": false,
			"id": "1sBuCftA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -688.3950028220524,
			"y": 4631.881463797172,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1052.2388916015625,
			"height": 150,
			"seed": 1129413785,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can justify this using the block-digonal Hessian made out of the hessians associated with each neuron\nThe eigenvalues of H are the eigenvalues of all the mini-Hessians\nReducing the condition number requires ensuring that each eigenvector is on a similar scale\ni.e each block of mini hessian is on a similar scale as all the other ones\nRemember the mini-Hessians are based off of the neurons connected to our Hessian's neuron\nthus it depends on how many are connected to it. ",
			"rawText": "We can justify this using the block-digonal Hessian made out of the hessians associated with each neuron\nThe eigenvalues of H are the eigenvalues of all the mini-Hessians\nReducing the condition number requires ensuring that each eigenvector is on a similar scale\ni.e each block of mini hessian is on a similar scale as all the other ones\nRemember the mini-Hessians are based off of the neurons connected to our Hessian's neuron\nthus it depends on how many are connected to it. ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can justify this using the block-digonal Hessian made out of the hessians associated with each neuron\nThe eigenvalues of H are the eigenvalues of all the mini-Hessians\nReducing the condition number requires ensuring that each eigenvector is on a similar scale\ni.e each block of mini hessian is on a similar scale as all the other ones\nRemember the mini-Hessians are based off of the neurons connected to our Hessian's neuron\nthus it depends on how many are connected to it. ",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 43,
			"versionNonce": 911029649,
			"isDeleted": false,
			"id": "h1BcMSqMXdRHmXWtyHC0T",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -512.4813377800153,
			"y": 4792.975551164807,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 724,
			"height": 56,
			"seed": 1712589303,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d5cc3b5b5e6129ecf0ecb7cca2976eddc5174ede",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 69,
			"versionNonce": 142043135,
			"isDeleted": false,
			"id": "KNkQr2Mz_oT6JlIWh0xTx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -505.1393132470303,
			"y": 4793.435188117485,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 714.7545904289177,
			"height": 55.180089007781135,
			"seed": 1031196695,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 397,
			"versionNonce": 1796365169,
			"isDeleted": false,
			"id": "7dwDeO4g",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -627.0634205098434,
			"y": 4945.298801950588,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 930.1190185546875,
			"height": 150,
			"seed": 1336401335,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "4) Batch Normalization\nPerform Batch normalization between each layer in order to ensure that\nthe data stays centered between layers in order to reduce the covariance matrix and thus\nthe Hessian.\nThis also helps reduce interactions between different parameters, allowing us to be closer to\nthe initial simplification of the error function that we analyzed",
			"rawText": "4) Batch Normalization\nPerform Batch normalization between each layer in order to ensure that\nthe data stays centered between layers in order to reduce the covariance matrix and thus\nthe Hessian.\nThis also helps reduce interactions between different parameters, allowing us to be closer to\nthe initial simplification of the error function that we analyzed",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "4) Batch Normalization\nPerform Batch normalization between each layer in order to ensure that\nthe data stays centered between layers in order to reduce the covariance matrix and thus\nthe Hessian.\nThis also helps reduce interactions between different parameters, allowing us to be closer to\nthe initial simplification of the error function that we analyzed",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "text",
			"version": 226,
			"versionNonce": 1248333855,
			"isDeleted": false,
			"id": "XaeVWBGG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -707.2322726634204,
			"y": 5141.544415985675,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1035.298828125,
			"height": 75,
			"seed": 1160692313,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "5) Connection skipping\nConnection skipping is sometimes useful to reduce interaction between  parameters at\ndifferent layers, it also helps send the most important information towards the output in certain cases",
			"rawText": "5) Connection skipping\nConnection skipping is sometimes useful to reduce interaction between  parameters at\ndifferent layers, it also helps send the most important information towards the output in certain cases",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "5) Connection skipping\nConnection skipping is sometimes useful to reduce interaction between  parameters at\ndifferent layers, it also helps send the most important information towards the output in certain cases",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "ellipse",
			"version": 535,
			"versionNonce": 2079835473,
			"isDeleted": false,
			"id": "rwQi3psj0G64QfR0gg4Cq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 624.287937269876,
			"y": 1934.8820023758935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1698.4615384615386,
			"height": 603.0769230769229,
			"seed": 1492552887,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "6qgrYpnwj3QuMdSukMoHc",
					"type": "arrow"
				},
				{
					"id": "cUIGAi1oKyzyB_Fc_kecT",
					"type": "arrow"
				}
			],
			"updated": 1706890392126,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 55,
			"versionNonce": 877573183,
			"isDeleted": false,
			"id": "cUIGAi1oKyzyB_Fc_kecT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 556.9805502124884,
			"y": 2483.253797247687,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 139.9999999999999,
			"height": 118.46153846153857,
			"seed": 231702007,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9BVn7FFx",
				"focus": 0.5901009292979572,
				"gap": 13.681330854337403
			},
			"endBinding": {
				"elementId": "rwQi3psj0G64QfR0gg4Cq",
				"focus": 0.6784425386408126,
				"gap": 4.942471918435331
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
					139.9999999999999,
					-118.46153846153857
				]
			]
		},
		{
			"type": "text",
			"version": 147,
			"versionNonce": 72676145,
			"isDeleted": false,
			"id": "h46NGruE",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2591.4597891116537,
			"y": 259.85793963884987,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 763.7313232421875,
			"height": 35,
			"seed": 1937434551,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "How do we deal with poorly conditioned Error functions?",
			"rawText": "How do we deal with poorly conditioned Error functions?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we deal with poorly conditioned Error functions?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 339,
			"versionNonce": 1309398111,
			"isDeleted": false,
			"id": "NuAEBhVO",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2521.3983470613152,
			"y": 303.0167457450244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 888.9790649414062,
			"height": 75,
			"seed": 1819492887,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Despite all our effort to optimize the Hessian, it can still be poorly conditioned,\nand since its computationally costly to compute everytime, we have developed ways that \ndeal with poorly conditioned error functions more efficiently",
			"rawText": "Despite all our effort to optimize the Hessian, it can still be poorly conditioned,\nand since its computationally costly to compute everytime, we have developed ways that \ndeal with poorly conditioned error functions more efficiently",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Despite all our effort to optimize the Hessian, it can still be poorly conditioned,\nand since its computationally costly to compute everytime, we have developed ways that \ndeal with poorly conditioned error functions more efficiently",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 246,
			"versionNonce": 1217488145,
			"isDeleted": false,
			"id": "VebfsNC9",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2748.2111964545165,
			"y": 399.41922252521005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 439.35955810546875,
			"height": 75,
			"seed": 1121505689,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Introducing the new 4-Wheel drive technology\nhot on the market\nguaranteed to get you laid",
			"rawText": "Introducing the new 4-Wheel drive technology\nhot on the market\nguaranteed to get you laid",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Introducing the new 4-Wheel drive technology\nhot on the market\nguaranteed to get you laid",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 1332736127,
			"isDeleted": false,
			"id": "fpEf4H1A",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2909.3260509229603,
			"y": 490.114161572448,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 132.52456665039062,
			"height": 35,
			"seed": 1565216121,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Momentum",
			"rawText": "Momentum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Momentum",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 154,
			"versionNonce": 337943281,
			"isDeleted": false,
			"id": "zoH6EoLA",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2665.250890692275,
			"y": 558.4112710186686,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 246.97970581054688,
			"height": 50,
			"seed": 1078666745,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "how beta males traverse\ngradient descent",
			"rawText": "how beta males traverse\ngradient descent",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "how beta males traverse\ngradient descent",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 271,
			"versionNonce": 574326943,
			"isDeleted": false,
			"id": "hpm4bvvr",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2629.08744020763,
			"y": 839.2200472760552,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 331.20068359375,
			"height": 80,
			"seed": 2418807,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Calculate the gradient at each point and\nuse it to move to the next point\nwhich causes bouncing in ill-conditioned\nerror functions",
			"rawText": "Calculate the gradient at each point and\nuse it to move to the next point\nwhich causes bouncing in ill-conditioned\nerror functions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Calculate the gradient at each point and\nuse it to move to the next point\nwhich causes bouncing in ill-conditioned\nerror functions",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 163,
			"versionNonce": 1469453521,
			"isDeleted": false,
			"id": "QqJTx0dP",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3046.2633521899556,
			"y": 555.6070844823748,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 253.79969787597656,
			"height": 50,
			"seed": 628773367,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "how Sigma males traverse\ngradient descent",
			"rawText": "how Sigma males traverse\ngradient descent",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "how Sigma males traverse\ngradient descent",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 319,
			"versionNonce": 606018751,
			"isDeleted": false,
			"id": "qxGMGUs5",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2970.4051684977094,
			"y": 837.57596003487,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 403.6968688964844,
			"height": 120,
			"seed": 1688122329,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "by taking into account a portion\nof the previous gradient descent\nwe can simulate physical momentum\nand traverse the error function as an accumlation\nof previous gradients that all aim to go\ntowards the minimum to some extent",
			"rawText": "by taking into account a portion\nof the previous gradient descent\nwe can simulate physical momentum\nand traverse the error function as an accumlation\nof previous gradients that all aim to go\ntowards the minimum to some extent",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "by taking into account a portion\nof the previous gradient descent\nwe can simulate physical momentum\nand traverse the error function as an accumlation\nof previous gradients that all aim to go\ntowards the minimum to some extent",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "line",
			"version": 115,
			"versionNonce": 108876465,
			"isDeleted": false,
			"id": "SKDOkFtDDRTAFa9Fg6u-y",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2885.895545596302,
			"y": 1057.468466828548,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.8929343800959941,
			"height": 49.111390905274675,
			"seed": 791374487,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.8929343800959941,
					49.111390905274675
				]
			]
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 683355359,
			"isDeleted": false,
			"id": "B2lNABon",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2840.1594387237433,
			"y": 1110.1515952542063,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 91.47221374511719,
			"height": 40,
			"seed": 1552502839,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Strength of\nmomentum",
			"rawText": "Strength of\nmomentum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Strength of\nmomentum",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 129,
			"versionNonce": 897701009,
			"isDeleted": false,
			"id": "cKaqfWiXvmfZAxBBFeak5",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2940.364542782152,
			"y": 1053.0037949280684,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 108.93799437170014,
			"seed": 1765059287,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					108.93799437170014
				]
			]
		},
		{
			"type": "text",
			"version": 124,
			"versionNonce": 1000356095,
			"isDeleted": false,
			"id": "wyeO4oge",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2867.8443859218005,
			"y": 1161.9417892997685,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 145.04031372070312,
			"height": 40,
			"seed": 705551703,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Previous\ngradient/momentum",
			"rawText": "Previous\ngradient/momentum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Previous\ngradient/momentum",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 151,
			"versionNonce": 2019236465,
			"isDeleted": false,
			"id": "xw21d2t8gl_i-VEY3xhrH",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3077.876437316921,
			"y": 1056.5755324484521,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 4.464671900479516,
			"height": 75.00648792805578,
			"seed": 319426969,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.464671900479516,
					75.00648792805578
				]
			]
		},
		{
			"type": "text",
			"version": 94,
			"versionNonce": 575586591,
			"isDeleted": false,
			"id": "H92EXTW3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3017.412962855096,
			"y": 1131.582020376508,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 129.85629272460938,
			"height": 20,
			"seed": 421678681,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Current gradient",
			"rawText": "Current gradient",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Current gradient",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 163,
			"versionNonce": 2144379985,
			"isDeleted": false,
			"id": "VmQ2TTGv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2664.352076611317,
			"y": 1223.6625284790962,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 581.33935546875,
			"height": 25,
			"seed": 301796759,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "And we update our parameters according to the momentum",
			"rawText": "And we update our parameters according to the momentum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "And we update our parameters according to the momentum",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 543,
			"versionNonce": 506938687,
			"isDeleted": false,
			"id": "99hmUjApC01SchTKJ-kle",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3081.735656780904,
			"y": 1289.8705732492965,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 291.4276037984505,
			"height": 285.60531680287045,
			"seed": 100696823,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "cED0bUlK",
				"focus": 1.0157278870030082,
				"gap": 18.305230564229532
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
					201.0048429810936,
					-29.036712304971388
				],
				[
					217.5191310212249,
					-252.54077145523206
				],
				[
					291.4276037984505,
					-285.60531680287045
				]
			]
		},
		{
			"type": "text",
			"version": 389,
			"versionNonce": 2008674865,
			"isDeleted": false,
			"id": "cED0bUlK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3391.468491143584,
			"y": 998.894973508448,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 465.97943115234375,
			"height": 150,
			"seed": 1170220919,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "99hmUjApC01SchTKJ-kle",
					"type": "arrow"
				}
			],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Using the closed form of a geometric series\n\n\n\nWe can derive that our effective learning rate\nalongside the direction of the momentum is",
			"rawText": "Using the closed form of a geometric series\n\n\n\nWe can derive that our effective learning rate\nalongside the direction of the momentum is",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Using the closed form of a geometric series\n\n\n\nWe can derive that our effective learning rate\nalongside the direction of the momentum is",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 179,
			"versionNonce": 1857701215,
			"isDeleted": false,
			"id": "GcK03a54",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3525.754891765035,
			"y": 1160.1117595128778,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 185.6804192882133,
			"height": 64.81297654399899,
			"seed": 44357,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5a8464103ff5489002b02542a91125adb053b4a9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 195,
			"versionNonce": 620659729,
			"isDeleted": false,
			"id": "IRAU8BHE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3435.976636533424,
			"y": 1239.760067569406,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 378.89959716796875,
			"height": 50,
			"seed": 1544947609,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "When the function is poorly conditioned\nchoose a momentum of 0.9 / 0.99",
			"rawText": "When the function is poorly conditioned\nchoose a momentum of 0.9 / 0.99",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "When the function is poorly conditioned\nchoose a momentum of 0.9 / 0.99",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 243,
			"versionNonce": 321405311,
			"isDeleted": false,
			"id": "Kmx5fv83bfMgCUDRT_cK2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3840.255963660999,
			"y": 1204.0401145484855,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 109.46107212000288,
			"height": 1.0525103088461947,
			"seed": 1927138681,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "EffzcTW9",
				"focus": -0.0833135693129906,
				"gap": 12.996349299927942
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
					109.46107212000288,
					1.0525103088461947
				]
			]
		},
		{
			"type": "text",
			"version": 376,
			"versionNonce": 1133894129,
			"isDeleted": false,
			"id": "EffzcTW9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3962.71338508093,
			"y": 1152.9876042396393,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 439.21685791015625,
			"height": 100,
			"seed": 2053449305,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Kmx5fv83bfMgCUDRT_cK2",
					"type": "arrow"
				}
			],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Previously we discussed that we\ncant use high learning rates with gradient descent\ndue to the issue of overshooting thus slowing down the\nprocess, we can see here that momentum simulates\ndifferent learning rates in each direction!",
			"rawText": "Previously we discussed that we\ncant use high learning rates with gradient descent\ndue to the issue of overshooting thus slowing down the\nprocess, we can see here that momentum simulates\ndifferent learning rates in each direction!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Previously we discussed that we\ncant use high learning rates with gradient descent\ndue to the issue of overshooting thus slowing down the\nprocess, we can see here that momentum simulates\ndifferent learning rates in each direction!",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "text",
			"version": 315,
			"versionNonce": 1287764383,
			"isDeleted": false,
			"id": "n5LBKz6N",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3855.654933073381,
			"y": 1276.0780274951208,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 227.6165313720703,
			"height": 140,
			"seed": 1683126809,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "(Horizontal)\nThe direction thats causing\nthe most bounces will always\ncancel each other out and\nthus have low effective\n\"learning rate\" which stops it\nfrom oscillating",
			"rawText": "(Horizontal)\nThe direction thats causing\nthe most bounces will always\ncancel each other out and\nthus have low effective\n\"learning rate\" which stops it\nfrom oscillating",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(Horizontal)\nThe direction thats causing\nthe most bounces will always\ncancel each other out and\nthus have low effective\n\"learning rate\" which stops it\nfrom oscillating",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "text",
			"version": 241,
			"versionNonce": 612856785,
			"isDeleted": false,
			"id": "gTY06DE0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4281.9546785182465,
			"y": 1282.5679956146898,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 275.8246154785156,
			"height": 120,
			"seed": 179448537,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "(Vertical)\nWhereas the direction thats all\nroughly aiming in the same direction\ndownwards will get stronger\nand have an effective learning\nrate",
			"rawText": "(Vertical)\nWhereas the direction thats all\nroughly aiming in the same direction\ndownwards will get stronger\nand have an effective learning\nrate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(Vertical)\nWhereas the direction thats all\nroughly aiming in the same direction\ndownwards will get stronger\nand have an effective learning\nrate",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "text",
			"version": 341,
			"versionNonce": 1622617535,
			"isDeleted": false,
			"id": "ubFk6ymu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3430.427228650279,
			"y": 1295.9466492249226,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 382.80078125,
			"height": 100,
			"seed": 1651357239,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Which roughly averages the last 10 gradients\nand all the gradients past 10 decay too little\nThis is often enough and does not require bias\ncorrection but if we choose different momentums\nwe do need to preform a bias correction",
			"rawText": "Which roughly averages the last 10 gradients\nand all the gradients past 10 decay too little\nThis is often enough and does not require bias\ncorrection but if we choose different momentums\nwe do need to preform a bias correction",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which roughly averages the last 10 gradients\nand all the gradients past 10 decay too little\nThis is often enough and does not require bias\ncorrection but if we choose different momentums\nwe do need to preform a bias correction",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "line",
			"version": 124,
			"versionNonce": 199938481,
			"isDeleted": false,
			"id": "bU-2s7YTc_qjNjm3xoBgt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3606.284622765163,
			"y": 1438.3461157983597,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 67.08328790363294,
			"height": 0.5833329382924148,
			"seed": 2126480695,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					67.08328790363294,
					0.5833329382924148
				]
			]
		},
		{
			"type": "image",
			"version": 105,
			"versionNonce": 438902239,
			"isDeleted": false,
			"id": "qEFL1BGv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3607.472107062289,
			"y": 1446.2275555970832,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 64.416652840236,
			"height": 26.352267071005635,
			"seed": 70372,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "30560d0785affa6d6c63d16416affa6347083048",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 117,
			"versionNonce": 1323791249,
			"isDeleted": false,
			"id": "LQaMcjgqgWQyElidlnqTz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3793.7557979667317,
			"y": 1195.0951856009215,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 224.79114201572384,
			"height": 139.9049764992967,
			"seed": 164353145,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					122.61335019039507,
					-58.948726053074324
				],
				[
					142.26292554141946,
					-139.9049764992967
				],
				[
					224.79114201572384,
					-138.33301047121472
				]
			]
		},
		{
			"type": "text",
			"version": 234,
			"versionNonce": 203950591,
			"isDeleted": false,
			"id": "owfh5xEw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4028.0055996911055,
			"y": 1022.178922511903,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 262.464599609375,
			"height": 80,
			"seed": 816987737,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "note that if we do\nchange the momentum we also\nhave to change the learning rate\nto counteract the scaling",
			"rawText": "note that if we do\nchange the momentum we also\nhave to change the learning rate\nto counteract the scaling",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "note that if we do\nchange the momentum we also\nhave to change the learning rate\nto counteract the scaling",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 476,
			"versionNonce": 833935729,
			"isDeleted": false,
			"id": "IrDTOD8wBsKVbTBn1kPgp",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2969.2075020780153,
			"y": 1362.6107615979568,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 0,
			"height": 174.15373367151255,
			"seed": 460023353,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "qJavEuL1hG5IT_IRbzHCl",
				"focus": 0.030071829468952385,
				"gap": 5.011596703861187
			},
			"endBinding": {
				"elementId": "LemBSt9Ub6D_bzgNSaLlu",
				"focus": -0.027563180088523966,
				"gap": 20.746021193460024
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
					174.15373367151255
				]
			]
		},
		{
			"type": "rectangle",
			"version": 293,
			"versionNonce": 330592799,
			"isDeleted": false,
			"id": "LemBSt9Ub6D_bzgNSaLlu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2573.4150457518913,
			"y": 1557.5105164629292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 814.0219461499911,
			"height": 1207.4712776526453,
			"seed": 688082679,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "IrDTOD8wBsKVbTBn1kPgp",
					"type": "arrow"
				},
				{
					"id": "8LLggFzLbmGRC1a9UBlK8",
					"type": "arrow"
				}
			],
			"updated": 1706890392126,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 235,
			"versionNonce": 94012241,
			"isDeleted": false,
			"id": "aOKXXLIo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2543.1341035562004,
			"y": 1415.3056795118441,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 418.0994873046875,
			"height": 75,
			"seed": 1251076185,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Didnt get laid yet?\nyucks youre really not good with girls huh?\nokay lets try this",
			"rawText": "Didnt get laid yet?\nyucks youre really not good with girls huh?\nokay lets try this",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Didnt get laid yet?\nyucks youre really not good with girls huh?\nokay lets try this",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 122,
			"versionNonce": 431937087,
			"isDeleted": false,
			"id": "wLooiro6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2840.120873932484,
			"y": 1579.8314742450218,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 266.6170959472656,
			"height": 35,
			"seed": 113684281,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Data Redundancies",
			"rawText": "Data Redundancies",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Data Redundancies",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 289,
			"versionNonce": 116388145,
			"isDeleted": false,
			"id": "0oQcQlwD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2650.184350256575,
			"y": 1627.4763873606,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 638.1192626953125,
			"height": 75,
			"seed": 1741475863,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The error function can be decomposed as the sum of the errors\non individual datapoints, which even for different datapoints\nwill usually have very similar shape at the start",
			"rawText": "The error function can be decomposed as the sum of the errors\non individual datapoints, which even for different datapoints\nwill usually have very similar shape at the start",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The error function can be decomposed as the sum of the errors\non individual datapoints, which even for different datapoints\nwill usually have very similar shape at the start",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 511,
			"versionNonce": 354924127,
			"isDeleted": false,
			"id": "qH2rHDyy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2607.9668160516812,
			"y": 1978.7320808736051,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 751.8591918945312,
			"height": 150,
			"seed": 243283159,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8LLggFzLbmGRC1a9UBlK8",
					"type": "arrow"
				}
			],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "it is computationally inefficient to compute the gradient of every datapoint\nwe have during each iteration, why not perform it only on a batch of data?\nThis algorithm of taking minibatches to perform on each step is called\nStoachstic Gradient descent\nsuch that its computation is O(K) which is way smaller than O(N)\nand we reach a decent estimator of the proper gradient descent",
			"rawText": "it is computationally inefficient to compute the gradient of every datapoint\nwe have during each iteration, why not perform it only on a batch of data?\nThis algorithm of taking minibatches to perform on each step is called\nStoachstic Gradient descent\nsuch that its computation is O(K) which is way smaller than O(N)\nand we reach a decent estimator of the proper gradient descent",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "it is computationally inefficient to compute the gradient of every datapoint\nwe have during each iteration, why not perform it only on a batch of data?\nThis algorithm of taking minibatches to perform on each step is called\nStoachstic Gradient descent\nsuch that its computation is O(K) which is way smaller than O(N)\nand we reach a decent estimator of the proper gradient descent",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "text",
			"version": 264,
			"versionNonce": 2065474321,
			"isDeleted": false,
			"id": "sbGXICFM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2617.449757153704,
			"y": 2136.5832490247412,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 746.3992919921875,
			"height": 50,
			"seed": 81487481,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Keep in mind, due to random sampling, SGD may not converge because it will\nkeep bouncing in random directions driven by those samples",
			"rawText": "Keep in mind, due to random sampling, SGD may not converge because it will\nkeep bouncing in random directions driven by those samples",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Keep in mind, due to random sampling, SGD may not converge because it will\nkeep bouncing in random directions driven by those samples",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 104,
			"versionNonce": 1287623295,
			"isDeleted": false,
			"id": "ZMMuoOD8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2849.232334454258,
			"y": 2247.228222483054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 276.0811462402344,
			"height": 35,
			"seed": 718385719,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Learning rate decay",
			"rawText": "Learning rate decay",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Learning rate decay",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 324,
			"versionNonce": 244848881,
			"isDeleted": false,
			"id": "lcmS4d0X",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2595.3151285366625,
			"y": 2223.4632667288006,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 780.5390625,
			"height": 150,
			"seed": 1786466329,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-fQen8pKPEztUohWCtnOZ",
					"type": "arrow"
				}
			],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can combat this by using\n\n\nWe decay our learning rate the further we are in the process in order to put\nless importance on later samples and allow their effect to be less significant \nthe closer we are to convergence",
			"rawText": "We can combat this by using\n\n\nWe decay our learning rate the further we are in the process in order to put\nless importance on later samples and allow their effect to be less significant \nthe closer we are to convergence",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can combat this by using\n\n\nWe decay our learning rate the further we are in the process in order to put\nless importance on later samples and allow their effect to be less significant \nthe closer we are to convergence",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "arrow",
			"version": 174,
			"versionNonce": 1497819807,
			"isDeleted": false,
			"id": "9jC5FRazQgxo55gvljlGR",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3059.86756244602,
			"y": 2417.6765056788972,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 121.55384071531307,
			"height": 0.41347480007152626,
			"seed": 1513545815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "GZcrAlOI",
				"focus": 0.4058733587477433,
				"gap": 18.393835393950212
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
					121.55384071531307,
					0.41347480007152626
				]
			]
		},
		{
			"type": "text",
			"version": 187,
			"versionNonce": 1927926481,
			"isDeleted": false,
			"id": "GZcrAlOI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3199.8152385552835,
			"y": 2394.7556738184994,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 153.9843292236328,
			"height": 80,
			"seed": 1639210039,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "9jC5FRazQgxo55gvljlGR",
					"type": "arrow"
				}
			],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "decays to 0\naka\nconverging to 0 the\nfurther we go on",
			"rawText": "decays to 0\naka\nconverging to 0 the\nfurther we go on",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "decays to 0\naka\nconverging to 0 the\nfurther we go on",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "arrow",
			"version": 176,
			"versionNonce": 1735278271,
			"isDeleted": false,
			"id": "1yW4IOIWAAGAJgqf7hh7v",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2891.042783674752,
			"y": 2488.5829127628303,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 103.82723894433002,
			"height": 1.6882477877124984,
			"seed": 589776281,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "iiPQGnje",
				"focus": -0.06782527350392528,
				"gap": 11.779120895481356
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
					-103.82723894433002,
					1.6882477877124984
				]
			]
		},
		{
			"type": "text",
			"version": 205,
			"versionNonce": 1017729201,
			"isDeleted": false,
			"id": "iiPQGnje",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2578.6519694892377,
			"y": 2436.2405928597536,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 196.78445434570312,
			"height": 120,
			"seed": 307494297,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "1yW4IOIWAAGAJgqf7hh7v",
					"type": "arrow"
				}
			],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "cannot converge to a\nconstant otherwise it\ndecays too quickly\nand becomes irrelevant\nto train past a certain \npoint",
			"rawText": "cannot converge to a\nconstant otherwise it\ndecays too quickly\nand becomes irrelevant\nto train past a certain \npoint",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "cannot converge to a\nconstant otherwise it\ndecays too quickly\nand becomes irrelevant\nto train past a certain \npoint",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "image",
			"version": 508,
			"versionNonce": 970329823,
			"isDeleted": false,
			"id": "jhA0Z9NVn0_vbpi2z52ux",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2705.721620785113,
			"y": 2556.240592226308,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 544.5298641664707,
			"height": 195.2669309284742,
			"seed": 1898003449,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f5b6e0de9485576adf80e8312fafb25ecd45a5c2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 146,
			"versionNonce": 25039505,
			"isDeleted": false,
			"id": "N_9MddK9lMvc7k4H9aNg1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2704.825621427197,
			"y": 2555.5708584424765,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 545.1645023387732,
			"height": 196.66286453424618,
			"seed": 633279257,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 728,
			"versionNonce": 1796135679,
			"isDeleted": false,
			"id": "8LLggFzLbmGRC1a9UBlK8",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3392.6897758173627,
			"y": 2070.529436786831,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 275.5944803496741,
			"height": 1.2793621210489619,
			"seed": 499787033,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "LemBSt9Ub6D_bzgNSaLlu",
				"focus": -0.1466301796411042,
				"gap": 5.25278391548045
			},
			"endBinding": {
				"elementId": "la25nI5Z",
				"focus": 1.191889421131718,
				"gap": 19.862986359992647
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
					275.5944803496741,
					-1.2793621210489619
				]
			]
		},
		{
			"type": "arrow",
			"version": 240,
			"versionNonce": 908040305,
			"isDeleted": false,
			"id": "-fQen8pKPEztUohWCtnOZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2579.5296289125554,
			"y": 2398.4315410040153,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 330.4331450630689,
			"height": 349.579060594222,
			"seed": 1795114201,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "lcmS4d0X",
				"focus": 0.24525336409834123,
				"gap": 24.968274275214753
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
					-302.02347127140274,
					115.19034718258172
				],
				[
					-330.4331450630689,
					349.579060594222
				]
			]
		},
		{
			"type": "text",
			"version": 45,
			"versionNonce": 1872306975,
			"isDeleted": false,
			"id": "0jIkZZZO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2341.499221769591,
			"y": 2382.9791773575716,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 127.68025207519531,
			"height": 40,
			"seed": 713341209,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "How does this\ncompare to GD?",
			"rawText": "How does this\ncompare to GD?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How does this\ncompare to GD?",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 134,
			"versionNonce": 1280664145,
			"isDeleted": false,
			"id": "yU6QO5wD8nTRoqJAbpjot",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1905.273271359209,
			"y": 2789.368006452516,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 922,
			"height": 444,
			"seed": 2129013207,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f76df9d0e64ec0a880b5a0feebe10c023c1dfe4c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 187,
			"versionNonce": 1474651967,
			"isDeleted": false,
			"id": "Zy9D4rby",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2624.9392535180937,
			"y": 2866.038273119197,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 357.2967529296875,
			"height": 60,
			"seed": 1540452887,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Phase 2 is often irrelevant because we need\nto stop the model before it starts\noverfitting WHICH happens in phase 2",
			"rawText": "Phase 2 is often irrelevant because we need\nto stop the model before it starts\noverfitting WHICH happens in phase 2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Phase 2 is often irrelevant because we need\nto stop the model before it starts\noverfitting WHICH happens in phase 2",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 78,
			"versionNonce": 284618801,
			"isDeleted": false,
			"id": "kce1tyjl",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2053.3531271363986,
			"y": 3141.5803007742816,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 302.7046813964844,
			"height": 20,
			"seed": 1821863735,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Needs the right balance of batch-Size",
			"rawText": "Needs the right balance of batch-Size",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Needs the right balance of batch-Size",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 142,
			"versionNonce": 1381246815,
			"isDeleted": false,
			"id": "5Owl2mrd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2735.6586861085516,
			"y": 2984.1277135428045,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 233.3285369873047,
			"height": 80,
			"seed": 47580183,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "can escape local minima\ndue to random noise\nis also better at generalizing\ndue to mini-batches",
			"rawText": "can escape local minima\ndue to random noise\nis also better at generalizing\ndue to mini-batches",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "can escape local minima\ndue to random noise\nis also better at generalizing\ndue to mini-batches",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 36,
			"versionNonce": 1240187409,
			"isDeleted": false,
			"id": "LS2qAOdS",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5243.958740406004,
			"y": 363.86943880995443,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 370.30157470703125,
			"height": 35,
			"seed": 1144880407,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "How Efficient is our model?",
			"rawText": "How Efficient is our model?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How Efficient is our model?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 91,
			"versionNonce": 1832248191,
			"isDeleted": false,
			"id": "7630unSI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5097.74991611613,
			"y": 405.45637759022765,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 666.7391967773438,
			"height": 25,
			"seed": 2060426647,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How much time does it take to produce on forward/backward pass?",
			"rawText": "How much time does it take to produce on forward/backward pass?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How much time does it take to produce on forward/backward pass?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 173,
			"versionNonce": 338384881,
			"isDeleted": false,
			"id": "Zh6TG3UU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5089.085106907924,
			"y": 446.8787362700513,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 667.8993530273438,
			"height": 50,
			"seed": 388326839,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The number of neurons should not be chosen larger than necessary!\nit will lead to very many parameters and very slow forward pass.",
			"rawText": "The number of neurons should not be chosen larger than necessary!\nit will lead to very many parameters and very slow forward pass.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The number of neurons should not be chosen larger than necessary!\nit will lead to very many parameters and very slow forward pass.",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 76,
			"versionNonce": 415964063,
			"isDeleted": false,
			"id": "BNbVxazt3Hcgeyny5XCRK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5155.681695108039,
			"y": 511.7664463509233,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 554.2278027050704,
			"height": 203.593886707985,
			"seed": 1289379639,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "503a917a7ec286e219737a7db980202952ab36f0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 29176273,
			"isDeleted": false,
			"id": "JmFGD2h3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4996.916703269887,
			"y": 720.4545310968067,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 920.5989990234375,
			"height": 50,
			"seed": 89235001,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "only relevant computations are computed, irrelevant features are not extracted and stored\nin neurons ",
			"rawText": "only relevant computations are computed, irrelevant features are not extracted and stored\nin neurons ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "only relevant computations are computed, irrelevant features are not extracted and stored\nin neurons ",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 98,
			"versionNonce": 1766084543,
			"isDeleted": false,
			"id": "wtiUV9F2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5174.625214440654,
			"y": 826.6609435863505,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 529.2794189453125,
			"height": 25,
			"seed": 723562967,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Does our model require long range interaction or not?",
			"rawText": "Does our model require long range interaction or not?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Does our model require long range interaction or not?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 319,
			"versionNonce": 2008600497,
			"isDeleted": false,
			"id": "lr1XhXgw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5056.971727821265,
			"y": 861.709845465022,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 777.4991455078125,
			"height": 100,
			"seed": 1744820087,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "some models emphasize the connectivity between local features, others require\nrelations between features very far apart, depending on the task we need\nto design the neural network with Global or Local connectivity\nLocal connectivity is much computationally cheaper per forward pass",
			"rawText": "some models emphasize the connectivity between local features, others require\nrelations between features very far apart, depending on the task we need\nto design the neural network with Global or Local connectivity\nLocal connectivity is much computationally cheaper per forward pass",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "some models emphasize the connectivity between local features, others require\nrelations between features very far apart, depending on the task we need\nto design the neural network with Global or Local connectivity\nLocal connectivity is much computationally cheaper per forward pass",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 179,
			"versionNonce": 415367135,
			"isDeleted": false,
			"id": "KGcud1tyWS59zFN78PUjd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4983.967640726353,
			"y": 992.2625899622735,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 435.39497593879946,
			"height": 218.58363785258587,
			"seed": 2050298521,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cea4b5a1c2b559ae8313b3fc6329b2cd35bb2fc3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 325,
			"versionNonce": 1279635857,
			"isDeleted": false,
			"id": "AJX2Gyn9wjZgtI2m8G_GD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5450.435182891528,
			"y": 979.221276730108,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 451.90582393361706,
			"height": 222.2888106916711,
			"seed": 1274113815,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392126,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e754c4137ffdae003de99a1bdffb5fc58fbb5b1d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 52,
			"versionNonce": 1230285823,
			"isDeleted": false,
			"id": "s5xKMdEd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5449.35271956336,
			"y": 1183.3968806277903,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 155.6598358154297,
			"height": 25,
			"seed": 1168436729,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "less connections",
			"rawText": "less connections",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "less connections",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 28,
			"versionNonce": 614160241,
			"isDeleted": false,
			"id": "yJU9aWVn",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5296.286036886083,
			"y": 1298.3948076330603,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 253.39971923828125,
			"height": 25,
			"seed": 1215273081,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Do you have bottlenecks?",
			"rawText": "Do you have bottlenecks?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Do you have bottlenecks?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 378,
			"versionNonce": 117232671,
			"isDeleted": false,
			"id": "3HPHqRBw",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5054.275438631798,
			"y": 1329.1900046235705,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 722.6392211914062,
			"height": 125,
			"seed": 960968953,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Sometimes are main computational issue is that we dont utilize our\nhardware capabilities as we should, this can come from a plethora\nof reasons. \nOne of which is that we have a bottleneck of information in our layers\nno Layer should be significantly dominant in terms of computational time ",
			"rawText": "Sometimes are main computational issue is that we dont utilize our\nhardware capabilities as we should, this can come from a plethora\nof reasons. \nOne of which is that we have a bottleneck of information in our layers\nno Layer should be significantly dominant in terms of computational time ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sometimes are main computational issue is that we dont utilize our\nhardware capabilities as we should, this can come from a plethora\nof reasons. \nOne of which is that we have a bottleneck of information in our layers\nno Layer should be significantly dominant in terms of computational time ",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "image",
			"version": 156,
			"versionNonce": 318849361,
			"isDeleted": false,
			"id": "sXraYxbDq7HlJvnoM4rDy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5411.303043411154,
			"y": 1472.319097643713,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 375.74726064176116,
			"height": 165.51463567681907,
			"seed": 1214474455,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "14f882e0140b160821097aaf633d15989774cf70",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 50,
			"versionNonce": 162199615,
			"isDeleted": false,
			"id": "DSu55o5L5Uq7u4bv0iezg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5479.381199259301,
			"y": 1486.0745093766109,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 170.9250091851418,
			"height": 35.01428759587816,
			"seed": 1123511223,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-103.66071985621784,
					-2.3035715523603812
				],
				[
					-170.9250091851418,
					32.71071604351778
				]
			]
		},
		{
			"type": "text",
			"version": 92,
			"versionNonce": 1959718705,
			"isDeleted": false,
			"id": "zqRdOT0t",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5161.408357491809,
			"y": 1522.8637967991847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 237.88851928710938,
			"height": 40,
			"seed": 1897224505,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "number of connections\nis never too high at any layer",
			"rawText": "number of connections\nis never too high at any layer",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "number of connections\nis never too high at any layer",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 43,
			"versionNonce": 926914655,
			"isDeleted": false,
			"id": "JTpv1HcmWsOw9Hvnq6Cmt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5573.827632906077,
			"y": 1628.8959456229559,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 194.88215332968957,
			"height": 33.63214466446175,
			"seed": 1666080471,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-109.65000589235478,
					33.63214466446175
				],
				[
					-194.88215332968957,
					28.103572938796788
				]
			]
		},
		{
			"type": "text",
			"version": 121,
			"versionNonce": 275505425,
			"isDeleted": false,
			"id": "tgumxxOa",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5151.91605191462,
			"y": 1605.3995157888799,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 251.3445587158203,
			"height": 60,
			"seed": 1516841207,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Spatial information is converted\ninto semantic information\nmore on this in CNNs",
			"rawText": "Spatial information is converted\ninto semantic information\nmore on this in CNNs",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Spatial information is converted\ninto semantic information\nmore on this in CNNs",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 122,
			"versionNonce": 1703621759,
			"isDeleted": false,
			"id": "EwpUXWgn",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5092.873155730182,
			"y": 1718.236242889156,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 643.8792724609375,
			"height": 25,
			"seed": 2144437655,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Are you utilizing Parallelization to compute Matrix multiplication?",
			"rawText": "Are you utilizing Parallelization to compute Matrix multiplication?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Are you utilizing Parallelization to compute Matrix multiplication?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 282,
			"versionNonce": 1934595825,
			"isDeleted": false,
			"id": "Xll4LHmC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5086.029917935829,
			"y": 1778.51726074204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 686.13916015625,
			"height": 100,
			"seed": 1864167415,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Computing the forward and backward pass for millions of variables is\ncostly considering that we have high dimensionality\nwe can abuse parallelization technology to compute the values Layer\nby layer instead of neuron by neuron",
			"rawText": "Computing the forward and backward pass for millions of variables is\ncostly considering that we have high dimensionality\nwe can abuse parallelization technology to compute the values Layer\nby layer instead of neuron by neuron",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Computing the forward and backward pass for millions of variables is\ncostly considering that we have high dimensionality\nwe can abuse parallelization technology to compute the values Layer\nby layer instead of neuron by neuron",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 113,
			"versionNonce": 1548635295,
			"isDeleted": false,
			"id": "FuHV39WbYmp1Gqcn6NJmm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5259.2544706492345,
			"y": 1886.9304030314036,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 341.6106137536859,
			"height": 170.52483839264454,
			"seed": 1173089943,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b9f537f8ae0bb701d95a337ea4cf3486727329b6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 601,
			"versionNonce": 268538065,
			"isDeleted": false,
			"id": "la25nI5Z",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3589.7392879501367,
			"y": 2089.1130610257746,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 694.71923828125,
			"height": 200,
			"seed": 1078854713,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8LLggFzLbmGRC1a9UBlK8",
					"type": "arrow"
				}
			],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "typically in short, we need to choose different batchsizes depending\non many choices, some of the more important ones being\nwhether our machine is actually good enough to handle computation on\nlarge batches.\nAnother factor in SGD during Phase1 we usually use smaller\nbatches due to corrolation, whereas in Phase2 we are allowed\nto go bigger as the corrolation falls off.\nOther factors:",
			"rawText": "typically in short, we need to choose different batchsizes depending\non many choices, some of the more important ones being\nwhether our machine is actually good enough to handle computation on\nlarge batches.\nAnother factor in SGD during Phase1 we usually use smaller\nbatches due to corrolation, whereas in Phase2 we are allowed\nto go bigger as the corrolation falls off.\nOther factors:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "typically in short, we need to choose different batchsizes depending\non many choices, some of the more important ones being\nwhether our machine is actually good enough to handle computation on\nlarge batches.\nAnother factor in SGD during Phase1 we usually use smaller\nbatches due to corrolation, whereas in Phase2 we are allowed\nto go bigger as the corrolation falls off.\nOther factors:",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "arrow",
			"version": 227,
			"versionNonce": 389636287,
			"isDeleted": false,
			"id": "0s8plFPZ5JwiLYICzXFyJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4337.074980626303,
			"y": 2692.792949140893,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 144.61643584296326,
			"height": 1.137852404505793,
			"seed": 1498419129,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "GeB70Bk3T2bqUFM-r4yFd",
				"gap": 29.838788197059785,
				"focus": 0.058295398615094765
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
					144.61643584296326,
					-1.137852404505793
				]
			]
		},
		{
			"type": "image",
			"version": 176,
			"versionNonce": 471420593,
			"isDeleted": false,
			"id": "GeB70Bk3T2bqUFM-r4yFd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4511.5302046663255,
			"y": 2578.9876155898028,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 522.0088028374759,
			"height": 234.67830905661742,
			"seed": 1092803001,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "0s8plFPZ5JwiLYICzXFyJ",
					"type": "arrow"
				}
			],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fb9cd8c89f727272be05782754b4d1add14994c4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 47,
			"versionNonce": 1206710495,
			"isDeleted": false,
			"id": "7nSTKz38",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4450.597877391181,
			"y": 2807.3189724081703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 581.0892333984375,
			"height": 80,
			"seed": 2102512311,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "In order for the training procedure to match the hardware specifications\n(e.g. CPU cache, GPU block size) optimally, neural network\ncomputations (e.g. batch computations) must be decomposed into\nblocks of appropriate size",
			"rawText": "In order for the training procedure to match the hardware specifications\n(e.g. CPU cache, GPU block size) optimally, neural network\ncomputations (e.g. batch computations) must be decomposed into\nblocks of appropriate size",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In order for the training procedure to match the hardware specifications\n(e.g. CPU cache, GPU block size) optimally, neural network\ncomputations (e.g. batch computations) must be decomposed into\nblocks of appropriate size",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 775835793,
			"isDeleted": false,
			"id": "2Y5niKbX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5272.689076440857,
			"y": 2107.345257376691,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 292.83966064453125,
			"height": 25,
			"seed": 162760921,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Can you distribute the data?",
			"rawText": "Can you distribute the data?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Can you distribute the data?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 89,
			"versionNonce": 402226431,
			"isDeleted": false,
			"id": "i7XjhfeP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5044.688897428732,
			"y": 2171.1809772305814,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 167.0998077392578,
			"height": 25,
			"seed": 500658969,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Model Parallelism",
			"rawText": "Model Parallelism",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Model Parallelism",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 39,
			"versionNonce": 472389233,
			"isDeleted": false,
			"id": "Rzj7Xh32",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5425.101237987601,
			"y": 2252.2385297561123,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 48.24000549316406,
			"height": 45,
			"seed": 504604023,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "v.s",
			"rawText": "v.s",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "v.s",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 102,
			"versionNonce": 719291679,
			"isDeleted": false,
			"id": "6jRGghwD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5654.567977631902,
			"y": 2149.2385297561123,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 166.69979858398438,
			"height": 25,
			"seed": 1552795097,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Data Parallelism",
			"rawText": "Data Parallelism",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Data Parallelism",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 308,
			"versionNonce": 413016145,
			"isDeleted": false,
			"id": "4eVP5gIA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5544.948075620226,
			"y": 2187.050838070311,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 386.97955322265625,
			"height": 200,
			"seed": 488144345,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Produce replicas of the models\n\nShard our data into different sections\n\nGive each model a shard of our data\nand let it produce an output\n\ncombine parameters in backprop step",
			"rawText": "Produce replicas of the models\n\nShard our data into different sections\n\nGive each model a shard of our data\nand let it produce an output\n\ncombine parameters in backprop step",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Produce replicas of the models\n\nShard our data into different sections\n\nGive each model a shard of our data\nand let it produce an output\n\ncombine parameters in backprop step",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "text",
			"version": 205,
			"versionNonce": 1611630911,
			"isDeleted": false,
			"id": "mOVbrEHe",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4864.962643086005,
			"y": 2217.989220414994,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 556.559326171875,
			"height": 150,
			"seed": 799224729,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Shards the model into different layers\n\neach layer runs on a machine on its own\n\ndata is sent to each machine in order to be processed \npotentially in parallel",
			"rawText": "Shards the model into different layers\n\neach layer runs on a machine on its own\n\ndata is sent to each machine in order to be processed \npotentially in parallel",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Shards the model into different layers\n\neach layer runs on a machine on its own\n\ndata is sent to each machine in order to be processed \npotentially in parallel",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "ellipse",
			"version": 2848,
			"versionNonce": 293072433,
			"isDeleted": false,
			"id": "XM5Xz3MrqtSD7idN49kAn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 442.31328314235674,
			"y": 1372.9687222190419,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 55.62921974281601,
			"height": 51.201385977351684,
			"seed": 1751809975,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2912,
			"versionNonce": 1424623967,
			"isDeleted": false,
			"id": "8nWEzmas4ccw6ZPBBiojv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 466.963131838856,
			"y": 1423.886331447404,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 2.7296292860039104,
			"height": 62.07302017561529,
			"seed": 1552904407,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.7296292860039104,
					62.07302017561529
				]
			]
		},
		{
			"type": "line",
			"version": 2865,
			"versionNonce": 1302134801,
			"isDeleted": false,
			"id": "anVXUfMMRFQRZZsQNumzv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 464.4769722248488,
			"y": 1487.5490975885207,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 24.57187279022971,
			"height": 37.855374086622675,
			"seed": 490290679,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					24.57187279022971,
					37.855374086622675
				]
			]
		},
		{
			"type": "line",
			"version": 2842,
			"versionNonce": 650085759,
			"isDeleted": false,
			"id": "sx0Pjgdi5zU6--bxuVZgU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 460.9807433045166,
			"y": 1485.098282579807,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 21.02439656166357,
			"height": 35.16741853017612,
			"seed": 2104256279,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-21.02439656166357,
					35.16741853017612
				]
			]
		},
		{
			"type": "line",
			"version": 2903,
			"versionNonce": 1258608113,
			"isDeleted": false,
			"id": "PaHIb04gB5D_ksQm-ogmz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 433.02892408623933,
			"y": 1459.158836550545,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 32.48711994829731,
			"height": 20.807832195149214,
			"seed": 2073914423,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					32.48711994829731,
					-20.807832195149214
				]
			]
		},
		{
			"type": "line",
			"version": 2946,
			"versionNonce": 1959820703,
			"isDeleted": false,
			"id": "ETNcQE4wRJA4ohH-ull07",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 464.7445971807023,
			"y": 1437.1578205359385,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 23.240467669169806,
			"height": 27.692151644718507,
			"seed": 1404095831,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					23.240467669169806,
					27.692151644718507
				]
			]
		},
		{
			"type": "text",
			"version": 645,
			"versionNonce": 1555492817,
			"isDeleted": false,
			"id": "8DtmfcLE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 453.09616552430765,
			"y": 1396.9768873228732,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 38.35841369628906,
			"height": 26.082132711038955,
			"seed": 1358629495,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"fontSize": 18.410917207792217,
			"fontFamily": 1,
			"text": "ಠ_ಠ",
			"rawText": "ಠ_ಠ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ಠ_ಠ",
			"lineHeight": 1.4166666666666656,
			"baseline": 17
		},
		{
			"type": "image",
			"version": 273,
			"versionNonce": 575500735,
			"isDeleted": false,
			"id": "1ElEnnV7MTR87pEr2xZ86",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1437.6920696605907,
			"y": 1587.6985258629657,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 46.65422137129943,
			"height": 140.71921905505448,
			"seed": 1385101751,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4e34ee84c26c6895525f8745ad511eeadc81497d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 2917,
			"versionNonce": 147508657,
			"isDeleted": false,
			"id": "oxNEhnjThZK_5dBC9MJ9S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 702.4020411847232,
			"y": 3185.0505564143887,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 55.5018958676587,
			"height": 51.08419650559211,
			"seed": 167172921,
			"groupIds": [
				"cszq7IDYrkXMbsSfuSHDp"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2981,
			"versionNonce": 1482088927,
			"isDeleted": false,
			"id": "2EeNOBMHHZr83ajdttw-_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 729.5328504507852,
			"y": 3238.416123428378,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 2.723381724379938,
			"height": 61.930947762807584,
			"seed": 1758006297,
			"groupIds": [
				"cszq7IDYrkXMbsSfuSHDp"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-2.723381724379938,
					61.930947762807584
				]
			]
		},
		{
			"type": "line",
			"version": 2937,
			"versionNonce": 644345745,
			"isDeleted": false,
			"id": "xPH9jMtW89MFp7CjCt91v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 728.0368991858631,
			"y": 3301.885307960222,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 24.515632812786453,
			"height": 37.76873089898643,
			"seed": 333586681,
			"groupIds": [
				"cszq7IDYrkXMbsSfuSHDp"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					24.515632812786453,
					37.76873089898643
				]
			]
		},
		{
			"type": "line",
			"version": 2914,
			"versionNonce": 1207782911,
			"isDeleted": false,
			"id": "xf4K-jXJlYWH11OF3mWmS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 723.4066741022107,
			"y": 3297.6708580006652,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 20.97627602976596,
			"height": 35.086927521543586,
			"seed": 684038617,
			"groupIds": [
				"cszq7IDYrkXMbsSfuSHDp"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.97627602976596,
					35.086927521543586
				]
			]
		},
		{
			"type": "line",
			"version": 3712,
			"versionNonce": 1002820977,
			"isDeleted": false,
			"id": "hjjuSUyRYSZ86GtZmscCv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 729.0250965232954,
			"y": 3252.293338384817,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 40.47473533519768,
			"height": 20.865892343741145,
			"seed": 1216804537,
			"groupIds": [
				"cszq7IDYrkXMbsSfuSHDp"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					18.60673419716477,
					13.683914799148056
				],
				[
					33.21064628236198,
					-6.883032608842589
				],
				[
					40.47473533519768,
					-7.181977544593087
				]
			]
		},
		{
			"type": "line",
			"version": 4130,
			"versionNonce": 742471199,
			"isDeleted": false,
			"id": "L7u960YNLHfZJh1P5XLq5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 689.2741691109513,
			"y": 3244.4926227405176,
			"strokeColor": "#000000",
			"backgroundColor": "#ced4da",
			"width": 37.772869676107796,
			"height": 21.549781572354593,
			"seed": 633976729,
			"groupIds": [
				"cszq7IDYrkXMbsSfuSHDp"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1706890392127,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.741371741017304,
					1.6861264404047913
				],
				[
					21.9487128024392,
					21.549781572354593
				],
				[
					37.772869676107796,
					9.328625461176804
				]
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 0.5,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1536.1126172024362,
		"scrollY": -899.0342190269632,
		"zoom": {
			"value": 1.2784162669587371
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