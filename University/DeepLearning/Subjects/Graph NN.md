---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Graph Neural Networks ^aW8lf5LW

Graph neural networks are
used to represent:

Knowledge Graphs
Chemical compounds
Social network
Topology ^9rHjKFvq

Lets take a few 
1) A graph is invariant to the order of nodes and edges
{v1,v2,v3} = {v3,v2,v1}

2) Edges are symmetric in their representation
(u,v) = (v,u)

3) Input graphs may have a varying number of nodes and edges

4) Labels may be attached to nodes and edges which provide us
with extra information
 ^e3onwHrL

Graph Properties ^2L1fgXPO

Subgraphs ^A74Lulfu

Random walks ^DvaQf7hg

Represent the graph as a bunch
of sub-graphs

This number exponentially grows with
the size of the graph

This does not capture global information ^g3lnGk1E

Sample a random walk in a random direction
alongside the graph

information about (non)locality
of walks may be hard to recover

many walks are required to represent
the graph ^5jMLhFcc

Similar to RNN ^FJJgnZjV

Same as embedding into
a feature space ^xvhwdoKh


Weisfeiler-Lehman
isomorphism test ^cxKgBSbJ

Step 1:
if nodes are not labeled, assign the same label to each node. ^Lzr6egqH

Step 2:
Relabel nodes with tuple of own label and
sorted multi-set of neighbor labels. ^IEQZjcYh

Step 3:
Compress labels using hash function (here: sequential id).
Its important to note that this hash function encodes the label of the current node
its neighbors, moving  forward we will use this has function multiple times ^eBLV6iL7

Step 4:
We check our stop conditions and compare:

If the labels of the graph nodes differed from the last iteration -> We continue with step 2
If the labels of the graph nodes did not differ from the last iteration -> Stop and check isomorphism

If both graphs have the same representation -> Isomorphic
If the graphs have a different representation -> Not isomorphic ^za4I4aPx

Graph neural networks are typically formulated as func-
tions that take a graph as input and output a representation
of the graph. The representation usually takes the form of an
embedding of the graph nodes in Euclidean space ^ycueD74u

This test has its own limitations as sometimes it can wrongly identify isomorphism but it never wrongly identifies
non-isomorphism so the test is necessary but not sufficient ^a5iPDV05

To give a more intuitive understanding of what
the purpose of this hash function does lets demonstrate using
colors as the result of hash functions ^uqHuBhzA

4 ^kKPDb7Wi

2 ^s6SbLblz

 ^8M3c4MPl

2 ^4lGgFUxo

3 ^WGexIE7F

3 ^hFyDboF4

Hashing ^UEsGXW7U

-2
-3
-4 ^Y3BO2uiR

Hashing ^gU5Mrijt

- 2 red 2 blue neighbors
- 1 green 1 blue 1 red neighbors
- 1 green 1 blue neighbors ^bFl8MMpo

We can observe that
the last 2 steps
are identical (while they
do have different
colors, they have the
same distribution of colors
over the specific nodes)
thus there is no
reason to continue ^PQd4QVv2

Graph neural network model  ^uNIBiWYh

the current model takes a graph as input and returns an output for each node
Similar to Weisfeiler-Lehman, nodes are updated using a message function (for undirected graphs
but it can be modified to contain directional information in connections) ^5bOXK8ml

label of
current node
n ^wC7npHuZ

labels of the
edges connected
to n ^zkGKrPTi

states of
connected nodes ^pn5z975D

labels of
connected nodes
one may wish to remove these labels
since they include information
that is implicitly contained in  ^ObveooVU

state of current node
a representation of the concept
denoted by n and can be
used to produce an output On ^MH1z6zDj

The states of the points are updated recurrently until we reach a fixed point ^TbG3Jw9z

We can guarantee the convergences to a unique fixed
point according to Banach fixed-point theorem ^XlVbPUAW

Let ( X , d ) be a metric space. Then a map T : X → X is called a
contraction mapping on X if there exists q ∈ [ 0 , 1 ) such that


for all x,y in X

in our case we can achieve this by adding Lipschitz regularization
which is basically a gradient penalty to the loss function



Lipschitz regularization enforces Lipschitz continuity which ensures
a certain smoothness (in the sense that there are no sudden
jumps and step function like movement) to the function applied. ^iA7stX5H

local transition
function that expresses the
dependence of a node on
its neighborhood ^x1ZcmkYi

the local output function
that describes how
the output is produced ^viEex0cJ

This rewrite of the
function simplifies
our equation but only
works for nonpositional
graphs ^jJwpklmF

 parametric function that is not affected by
the positions and the number of the children ^XLD2YT7c

can be interpreted as the representation of a network consisting of units, which
compute f and g. Such a network will be called an encoding
network ach unit stores the current state
of node Xn(t), and, when activated, it calculates the state Xn(t+1)
The output of node n is produced by another unit, which implements g ^esmnm0cR

this turns out to be a recurrent neural
network where the connections between the neurons can be di-
vided into internal and external connections. The internal con-
nectivity is determined by the neural network architecture used
to implement the unit. The external connectivity depends on the
edges of the processed graph. ^2uYx7I3Z

The Learning algorithm ^0tQn4ycP

Learning in GNNs consists of estimating the parameter w
such that phi_w approximates the data in the learning data set
The learning task can be posed as the minimization of a quadratic cost function ^5bvCsKZ2

number of supervised
nodes in Gi ^WZdMl8Rw

Graph focused
applications ^zhHq1TFa

graph-focused applications, the function Tau is independent
of the node n and implements a classifier or a
regressor on a graph structured data set.
For example, a chemical compound can be
modeled by a graph , the nodes of which
stand for atoms (or chemical groups) and the edges of which
represent chemical bonds linking together some
of the atoms. The mapping may be used to estimate the
probability that the chemical compound causes a certain disease ^9GcQUcIM

V.S ^Yr3BIzjb

Node focused
applications ^Pt0dwnRG

In node-focused applications, Tau depends on the node n, so
that the classification (or the regression) depends on the properties
of each node. Object detection is an example of this class of
applications. It consists of finding whether an image contains a
given object, and, if so, localizing its position. This problem
can be solved by a function Tau, which classifies the nodes of the
region adjacency graph according to whether the corresponding
region belongs to the object ^sSXglXt1

+ some regularization term depending on the objective ^kNBavbKw

The gradient descent algorithm goes as follows:

a) The states xn are iteratively updated by f until a time T where they approach a fixed point

b) The gradient above is computed w.r.t w (which influence both f and g)

c) The weights w are updated according to the gradient computed ^6rmrrMn2

since x(t) has reached a stable point before the gradient computation it allows us to
only yhe need to store the final product for backpropagation as opposed to x at
every iteration through time.
this is good because backpropagation through time (RNN) requires to store the states of
every instance of the units. When the graphs and time are large, the memory required may be considerable ^I7ZedLwY

Transition and Output Function Implementations ^y9Gr52Rf

The local transition function f plays a crucial role n the proposed
model, since its implementation determines the number and the
existence of the solutions
The assumption behind GNN is that the design of f is such
that the global transition function is a contraction map w.r.t. the state .  ^7PJHbWFT

Linear (nonpositional) GNN ^NKRnA5Xf

output of two feed forward
neural networks whose parameters
correspond to the
parameters of the GNN ^bm3o2roZ

The transition network is basically a FFNN that
has to generate A and the forcing network is a FFNN
that has to generate b ^1qhuVwlG

We then define such outputs as the following: ^r6oLsQ2x

allocates the elements
of a s^2-dimensional
vector into as matrix sxs ^rFgkh6Qp

(0,1) ^LSu6MUrh

This transition function is a contraction map if the entries of A are bounded
between -1 and 1 with tanh for example ^ME6iqJjQ

hw is realized by a multilayered FNN. Since three-layered neural
networks are universal approximators, hw can approximate
any desired function. However, not all the parameters
can be used, because it must be ensured that the corresponding
transition function is a contraction map which is ensure by the lipdogshit regularization ^l0y3P3cG

Graph convolutional networks ^NmIxJUKV

idea: Instead of iterating until convergence, stack a couple of convolutional layers
which means constraining of parameters is not required.
Thing is Convolution operator cannot directly be applied to graphs as there is no
corresponding translation operator but we can derive one. ^yamu5MWP

How the fuck did we
derive this operator????? ^WJjsMp5V

adjacency matrix
such that aij is
1 if nodes i and j 
are connected and
0 otherwise ^mvVeK6is

Rank matrix
indicating how many
nodes Aij is connected
to (diagonal) ^d0pKkTxq

 Filter matrix ^2rWuJ9OG

C is the number of 
channels and F is
the dimensionality of x ^6jkb8meQ

Let me show you the horrors of this derivation
and then you'll learn to never ask for an explanation ever again
also no I did not understand shit from this and id rather get castrated
than spend the time to do so (at the moment at least) ^YInmLx64

The normalized Graph laplacian is DEFINED as (this is a definition, dont
ask me where it comes from) ^aCOa7979

Using the eigen-decomposition of the graph Laplacian  ^b8ll2wFC

eigenvectors ^SDLUi4hz

We can also define the following ^xJvfj9kM

Graph fourier transform
for function f that assigns
values to each node ^XfuDxSNl

Generalized Convolution can be defined in the spectral
domain using the convolution theorem
its a theorem so dont question it ^N42vKnUc

Who the fuck
is that guy? ^yOVSTs0p

Convolution filter
defined in the fourier
transform ^wqAdZrh3

Which can be approximated using
Chebyshev polynomials ^3REhKLpl

using this property which is
about the only thing I UNNDERSTAND
here (because we explained it before
in RNN note) ^HnjgoGUy

We can rewrite ^lKPbAGZd

This filter is now K localized
and in english this means
nodes up to a distance of K edges influence a
central node xi, and ones outside of it do not. ^TD11q9uU

We set K=1 and arrive at  ^7i5jmpj5

WHich if normalized into [-1,1] area to avid exploding and vanishing gradients
becomes ^tHLfMOI4

Viola! The magic happens because a wizard
decided its gonna happen ^2lBgNvm5

The output ^nVoZDJjS

Finally, the node representation has to be transformed to the prediction

this depends if youre graph focused on Node focused, obviously for node
focused outputs you need y to output a prediction for every node
whereas for graph-wise you input the entire graph and y outputs one prediction

Common methods ^JolUgm45

Sum ^NXXm3PXB

Average ^A8vDfIrK

Warning, this note
is a fucking mess and
doesnt explain everything
because its too difficult
for my tiny pea brain ^8EWCERiv

# Embedded files
394cdd721d0265ce87cc753cb87a3fcdb020c3e9: $$b_n = \rho_w (l_n)$$
059468076d5f8a425d17725236e7cf7d981e4789: [[Pasted Image 20240503184422_662.png]]
c353a70af325f9ef7e8cf9c7e536647dbdf86414: [[Pasted Image 20240503184527_852.png]]
d115c8e13badfc51411be92ff2d4fb73af18fbf5: [[Pasted Image 20240503184643_860.png]]
9242be0c8d76f13cf6e103a2ebfbae75b1a01deb: [[Pasted Image 20240508150745_996.png]]
5cc061cf0bb3ce98a26909ace1da220a9d977496: [[Pasted Image 20240508150801_008.png]]
7d1b3ae93d00105b127c4540af27952e8a866386: [[Pasted Image 20240508151726_055.png]]
57fa9808d0bf03c8fe0567d2ede2a0a2dd91b1e3: [[Pasted Image 20240508152128_102.png]]
fb7bdf92e7ac15d798e0cccb1ea29a3a5a56a62e: [[Pasted Image 20240508152316_125.png]]
8e9ad7eae0f56baf082cbca693ece6f633196320: [[Pasted Image 20240508163716_813.png]]
f219c77ee819d1bda72fe5c0819685c62ea680e0: [[Pasted Image 20240508165633_914.png]]
97d50a86b9cfe347e9ce2c3a4aa8972ed60da4fb: [[Pasted Image 20240508170035_956.png]]
61d2b986b39655d7e0adc1c78a5cec0e2e6970ca: [[Pasted Image 20240508170052_969.png]]
6d288500a8224f297c23b8fde715b63415346734: [[Pasted Image 20240508171205_106.png]]
eaf445af9fe9c512962fa97b580c7600a20255df: [[Pasted Image 20240508172832_211.png]]
ede0c8c770ae654819ee337e30c6459c125082a2: [[Pasted Image 20240508173336_270.png]]
227f10e792a5ca119d58e7824e74659617c26b96: [[Pasted Image 20240508173854_326.png]]
42154746d86aca9ac56aeac04541bf4492a3cf95: [[Pasted Image 20240508173909_342.png]]
10335c3ee4d23c486a70de0c3f8153e08ccd1533: [[Pasted Image 20240508174542_393.png]]
cf36ca2c6503e84800c086507ac82ae4a5781b79: [[Pasted Image 20240508174844_412.png]]
5324e2faf3cb21f41a3ebb2db6e22f14257a2887: [[Pasted Image 20240508174947_438.png]]
966a0cad5691da707d0f709dcda15e144e645df7: [[Pasted Image 20240508180002_465.png]]
b7a97f23950ba32f6424aef4dc2a44cf3e485fca: [[Pasted Image 20240508180117_478.png]]
ab287ec144cb8c63ee8156229be102677588ded5: [[Pasted Image 20240508180317_487.png]]
3e8de24e8aafa43f9ca868a558fac4a99f7c06dd: [[Pasted Image 20240508180453_497.png]]
eac9ece4de522b2d388c46f5e905b0af897cf85b: [[Pasted Image 20240508180840_571.png]]
5a6d4c9b08a875cda405d7d687c1ca53d181814f: [[Pasted Image 20240508181004_591.png]]
4f2812f79f0ef1f7e198fc939cad6dca80811502: [[Pasted Image 20240508181052_632.png]]
e230dcd86368f530550e761cf798216984e0beed: [[Pasted Image 20240508181137_638.png]]
a17e022d59c201eb34d2eeabd13702365b17f154: [[Pasted Image 20240508181402_649.png]]
09e078e53aa33c0b29a5319d99f5b29c72ecd7ee: [[Pasted Image 20240508183558_714.png]]
f9734408fe1baaaa8bb6fc36057d673f225d3101: [[Pasted Image 20240508183717_773.png]]
f81db5877151bddf22f44a7aeeb36e17b2f05502: [[Pasted Image 20240508183734_776.png]]
04fce44f93dbf1e9ff165aef3769a572914b2e4b: [[Pasted Image 20240508183849_783.png]]
3dc9000f18ec048c16c834420c3d8beef33ae2cd: [[Pasted Image 20240508184005_816.png]]
c1f3efc402dc5be4410bc7e4e033d1e17a1aa01a: [[Pasted Image 20240508184237_837.png]]
9ba3dcc8f4ca0b68c628c10eae8c42e7264cc8a9: [[Pasted Image 20240508184256_854.png]]
126bf3078bf339983ce258e13b81b36cf10e844f: [[Pasted Image 20240508184356_860.png]]
5b76451e8930b5b5bef3e924d3f55abf35b69986: [[Pasted Image 20240508184822_951.png]]
cd530f337cab0b76ced9b5a4a512cd56fbf272a3: [[Pasted Image 20240508184838_963.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.1.6",
	"elements": [
		{
			"type": "line",
			"version": 55,
			"versionNonce": 445302160,
			"isDeleted": false,
			"id": "CrCwxbtpw9GjA-lcWkr70",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -45.28623342872814,
			"y": -421.963060709748,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 45.32945055872776,
			"height": 35.55251024213942,
			"seed": 956418228,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					45.32945055872776,
					35.55251024213942
				]
			]
		},
		{
			"type": "line",
			"version": 442,
			"versionNonce": 1016732528,
			"isDeleted": false,
			"id": "HQpyN8fxzUWVn3QzUQgJj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 38.558436558984,
			"y": -332.2016355435435,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 97.47313224719892,
			"height": 127.9890368717019,
			"seed": 1302470068,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-38.21894851029987,
					-54.513849037947125
				],
				[
					2.370167349475963,
					-57.77282914347654
				],
				[
					-54.513849037947125,
					-78.51179345139121
				],
				[
					-57.47655822479206,
					-10.962023991326305
				],
				[
					-55.40266179400061,
					-80.58568988218269
				],
				[
					-95.10296489772296,
					-127.9890368717019
				],
				[
					-54.21757811926261,
					-109.3239689945787
				]
			]
		},
		{
			"type": "line",
			"version": 756,
			"versionNonce": 104567696,
			"isDeleted": false,
			"id": "IUVNRurJkYud56mRQ8TO4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -17.73303799107009,
			"y": -496.62333221824076,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 113.47176185616166,
			"height": 161.4676506830499,
			"seed": 1078434100,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					53.328765363209186
				],
				[
					-17.77625512106971,
					111.39786542537018
				],
				[
					-1.1850836747379674,
					151.39443944777702
				],
				[
					17.479984202385225,
					111.99040726273915
				],
				[
					-0.29627091868448474,
					54.513849037947125
				],
				[
					36.14505207950842,
					37.92267759161541
				],
				[
					30.219633705818524,
					74.0677296711238
				],
				[
					-27.553195437658047,
					75.54908426454631
				],
				[
					-55.99520363136958,
					103.10227970220433
				],
				[
					-0.5925418373689695,
					86.2148373371881
				],
				[
					56.88401638742309,
					106.36125980773375
				],
				[
					30.812175543187493,
					77.32670977665327
				],
				[
					-15.109816852909233,
					108.13888531984071
				],
				[
					-53.32876536320913,
					161.4676506830499
				],
				[
					-17.183713283700712,
					110.21278175063219
				],
				[
					-56.587745468738575,
					106.95380164510277
				]
			]
		},
		{
			"type": "line",
			"version": 269,
			"versionNonce": 1000680816,
			"isDeleted": false,
			"id": "gz0IlyxMeRQ6By52qh2BQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 69.96315393954046,
			"y": -438.5542321560797,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 179.24390580411955,
			"height": 45.9219923960967,
			"seed": 62567604,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-58.06910006216103,
					17.479984202385253
				],
				[
					-51.25486893241765,
					-20.146422470545645
				],
				[
					-87.10365009324155,
					25.775569925551054
				],
				[
					-124.13751492880345,
					-18.665067877123192
				],
				[
					-118.80463839248253,
					15.109816852909262
				],
				[
					-179.24390580411955,
					1.4813545934224521
				]
			]
		},
		{
			"type": "line",
			"version": 244,
			"versionNonce": 513974672,
			"isDeleted": false,
			"id": "_YDPyeriv-hCuJTCv5-Ss",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -16.892431175911952,
			"y": -503.17124695551865,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 181.11347901157683,
			"height": 172.11405148305118,
			"seed": 1559702452,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					87.7444184031242,
					64.68338536127737
				],
				[
					55.121493612218956,
					172.11405148305118
				],
				[
					-58.496278935416115,
					172.11405148305118
				],
				[
					-93.36906060845263,
					64.68338536127743
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
			"versionNonce": 192806768,
			"isDeleted": false,
			"id": "jV1Qv_YgQE5cB64sSvANi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -17.791818344629434,
			"y": -498.8690238386681,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 177.54668542990925,
			"height": 168.18387194044135,
			"seed": 2043393076,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					59.64458963661016,
					112.35376187361442
				],
				[
					-55.48333919684666,
					165.40970498059903
				],
				[
					-36.41094134793062,
					39.53187917775324
				],
				[
					87.38625923503346,
					60.338131376570686
				],
				[
					-1.3870834799211593,
					153.61949540126915
				],
				[
					-90.1604261948758,
					61.37844398651157
				],
				[
					36.06417047795031,
					40.57219178769412
				],
				[
					55.48333919684663,
					168.18387194044135
				],
				[
					-59.29781876662986,
					106.11188621396917
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 206,
			"versionNonce": 1928851344,
			"isDeleted": false,
			"id": "M7sM_EHh2lgPqhrQR6-Yr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -25.48752276662077,
			"y": -509.43099144293285,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1627220364,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 220,
			"versionNonce": 1282183536,
			"isDeleted": false,
			"id": "PfgMkorYyqljdfkN_5wwa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 10.406378336176886,
			"y": -466.27020611534067,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 937265844,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 235,
			"versionNonce": 1802730896,
			"isDeleted": false,
			"id": "MyzTb6lYAVbo2VJeRdzkv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 63.84047928679735,
			"y": -445.4590299556253,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 2042256692,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 244,
			"versionNonce": 1438180208,
			"isDeleted": false,
			"id": "KtX8QTS_2RenMgA8mLx0h",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -25.591331777925348,
			"y": -449.3962794993552,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1139189940,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 246,
			"versionNonce": 692931472,
			"isDeleted": false,
			"id": "PXAZyKP4EEzowbUQvDyiz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -61.589041892027524,
			"y": -465.7077418948079,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 385602228,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 250,
			"versionNonce": 1437267312,
			"isDeleted": false,
			"id": "gjBqE9W1oSpIgrAAS1Sc_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -117.83546394531226,
			"y": -446.58395839669106,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 45312820,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 238,
			"versionNonce": 1723685264,
			"isDeleted": false,
			"id": "y6aQWyiPuzYnqfEoSRwnu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -26.153795998458122,
			"y": -418.46074737004864,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1223554868,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 238,
			"versionNonce": 1904920432,
			"isDeleted": false,
			"id": "Ms55q5pij1jTpczvu6df6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3.656807689782795,
			"y": -428.02263911910705,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1183016844,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 223,
			"versionNonce": 1459333008,
			"isDeleted": false,
			"id": "yDaBd-xe3Xz7VD9Jl3545",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -54.27700702510049,
			"y": -429.1475675601728,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 211702540,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 235,
			"versionNonce": 1705007472,
			"isDeleted": false,
			"id": "AUg3RBtYEJ6oQsZaYjVAG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -8.717405161939894,
			"y": -394.2747858871363,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 401068468,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 250,
			"versionNonce": 104871312,
			"isDeleted": false,
			"id": "eXNwnqAY2Ay8Api5pG4A3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 30.655090275359328,
			"y": -339.1532922749172,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1055990668,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 259,
			"versionNonce": 624143216,
			"isDeleted": false,
			"id": "teyi1giQGQaCfEhxCZM-f",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -81.27528961067713,
			"y": -339.71575649545014,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1149520308,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 248,
			"versionNonce": 969081744,
			"isDeleted": false,
			"id": "E4dj7sO5ZcOI6UYsuTTDI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 34.02987559855649,
			"y": -396.5246427692677,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1486112652,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018565,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 248,
			"versionNonce": 2056043888,
			"isDeleted": false,
			"id": "DjnZdjONVqQau6juz5tTu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -26.153795998458122,
			"y": -350.96504090610705,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 761463476,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 243,
			"versionNonce": 1337725328,
			"isDeleted": false,
			"id": "9rosZc7HW8N6XBvVeDR3U",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -85.77500337494001,
			"y": -397.08710698980053,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 1037934348,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 251,
			"versionNonce": 653496176,
			"isDeleted": false,
			"id": "P3H3CDnLtR1j9bLtnvxa5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -43.59018683497641,
			"y": -394.27478588713626,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 15.147944321895352,
			"height": 15.06726516383393,
			"seed": 13558708,
			"groupIds": [
				"izdSpc31mUWuRItWlM1Vo"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 203,
			"versionNonce": 526606224,
			"isDeleted": false,
			"id": "aW8lf5LW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -178.6181917779269,
			"y": -324.08602748629244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 318.38934326171875,
			"height": 35,
			"seed": 173161780,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Graph Neural Networks",
			"rawText": "Graph Neural Networks",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph Neural Networks",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 685,
			"versionNonce": 45097328,
			"isDeleted": false,
			"id": "jcQmvpyaPUxiYnlpB5Y2I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -509.2798066317089,
			"y": 125.58259425407039,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 49.454167879081595,
			"height": 40.75389760405794,
			"seed": 417586316,
			"groupIds": [
				"36_9Y4p4htyMV0nArt8lU",
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-15.568904702673773,
					-4.808044099355162
				],
				[
					-31.137809405347614,
					-2.7474537710600906
				],
				[
					-44.41716929880468,
					14.65308677898712
				],
				[
					-46.477759627099765,
					28.84826459613089
				],
				[
					-26.32976530599245,
					35.487944542859424
				],
				[
					-13.279359893457,
					35.945853504702775
				],
				[
					2.976408251981825,
					27.24558322967917
				],
				[
					2.7474537710600737,
					10.302951641475309
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 628,
			"versionNonce": 1492184464,
			"isDeleted": false,
			"id": "WFqJYWDouk3Km_bI-TbiG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -509.2798066317089,
			"y": 125.12468529222707,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 35.48794454285947,
			"height": 26.329765305992485,
			"seed": 2077256460,
			"groupIds": [
				"36_9Y4p4htyMV0nArt8lU",
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-17.858449511890544,
					-3.89222617566846
				],
				[
					-30.221991481660943,
					-2.7474537710600906
				],
				[
					-32.51153629087765,
					10.76086060331866
				],
				[
					-25.413947382305782,
					20.147994321107284
				],
				[
					-10.989815084240295,
					22.437539130324023
				],
				[
					2.976408251981825,
					16.94263158820386
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 816,
			"versionNonce": 487224176,
			"isDeleted": false,
			"id": "6VV9cmTNAmFFz9DqEEeIe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -523.4749844488526,
			"y": 156.2624946975747,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 92.26865581143456,
			"height": 50.36998580276823,
			"seed": 522660236,
			"groupIds": [
				"hFgKK480UbYdIsx3VOyAs",
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					14.653086778987104,
					-13.50831437437875
				],
				[
					39.609125199449586,
					-34.343172138251056
				],
				[
					54.26221197843675,
					-41.21180656590127
				],
				[
					68.68634427650211,
					-42.35657897050964
				],
				[
					89.52120204037448,
					-20.834857763872304
				],
				[
					92.26865581143456,
					-6.410725465806866
				],
				[
					71.66275252848394,
					5.265953061198497
				],
				[
					29.993037000739328,
					8.013406832258587
				],
				[
					0.9158179236867361,
					5.723862023041848
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 754,
			"versionNonce": 1704770448,
			"isDeleted": false,
			"id": "XERs-mVAtGJBP1VFBOmkK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -523.246029967931,
			"y": 158.5520395067914,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 91.5817923686695,
			"height": 38.23539831391953,
			"seed": 1445074956,
			"groupIds": [
				"hFgKK480UbYdIsx3VOyAs",
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.471315794101905,
					-1.3737268855300369
				],
				[
					20.376948802028934,
					0
				],
				[
					35.71689902378109,
					-6.181770984885199
				],
				[
					52.43057613106328,
					-16.94263158820386
				],
				[
					65.70993602452035,
					-29.764082519817592
				],
				[
					75.55497870415229,
					-31.824672848112666
				],
				[
					85.17106690286262,
					-28.84826459613089
				],
				[
					91.5817923686695,
					-14.195177817143769
				],
				[
					86.08688482654935,
					-2.9764082519817574
				],
				[
					64.565163619912,
					2.9764082519817574
				],
				[
					38.23539831391948,
					5.952816503963515
				],
				[
					11.90563300792703,
					6.410725465806866
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1433,
			"versionNonce": 1548387696,
			"isDeleted": false,
			"id": "ag2ePSNbUmzcGI-3usQjf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -505.4657995612393,
			"y": 139.45385433559397,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#7e3f09",
			"width": 62.76608777371724,
			"height": 390.1802322052721,
			"seed": 2092643980,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-7.026054601535481,
					-70.72894965545747
				],
				[
					-8.431265521842564,
					-122.72175370682025
				],
				[
					-15.223118303326865,
					-165.3464849561357
				],
				[
					-20.37555834445297,
					-205.62919800493927
				],
				[
					-32.08564934701213,
					-335.8454099533975
				],
				[
					-32.55405298711449,
					-358.3287846783111
				],
				[
					-37.47229120818935,
					-374.722912081894
				],
				[
					-33.95926390742157,
					-384.5593885240437
				],
				[
					-20.60976016450415,
					-390.1802322052721
				],
				[
					-14.988916483275684,
					-387.83821400476023
				],
				[
					-9.133870981996106,
					-356.4551701179017
				],
				[
					6.089247321330827,
					-172.13833773762
				],
				[
					16.15992558353172,
					-98.36476442149713
				],
				[
					17.799338323889984,
					-60.892473213307746
				],
				[
					25.293796565527895,
					-19.907154704350592
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1435,
			"versionNonce": 1201588624,
			"isDeleted": false,
			"id": "slA09Djy8oFL5I40kMM-2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -519.5238260612009,
			"y": -22.816076999059135,
			"strokeColor": "transparent",
			"backgroundColor": "#6e3907",
			"width": 34.16254141944461,
			"height": 114.62853143454836,
			"seed": 1605141772,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.665972190198041,
					-25.050451064776514
				],
				[
					-3.8333780749100597,
					-28.914942047508056
				],
				[
					-2.607914297285965,
					-32.54290274121007
				],
				[
					7.718953060063368,
					-33.5731400858038
				],
				[
					17.001154986357253,
					-34.33941404654336
				],
				[
					18.185631164522302,
					-25.95543536064383
				],
				[
					23.854916223830823,
					24.4220629384446
				],
				[
					28.6808442323942,
					54.00098303415614
				],
				[
					30.32916334453455,
					80.289117388005
				],
				[
					20.427844242472787,
					36.59633823511649
				],
				[
					13.313193906247108,
					18.568516251234556
				],
				[
					7.871992925936983,
					6.215582836034514
				],
				[
					1.742587064089289,
					0.4752510174789062
				]
			]
		},
		{
			"type": "line",
			"version": 657,
			"versionNonce": 498620272,
			"isDeleted": false,
			"id": "ZqoxDFb5hYGv0RUSm9e1y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -531.942915655558,
			"y": -215.66679308832897,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 4.392330848271322,
			"height": 24.23163736195687,
			"seed": 611320716,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.0619818974496806,
					-9.349024729222403
				],
				[
					-2.3303489508216413,
					-24.23163736195687
				]
			]
		},
		{
			"type": "line",
			"version": 578,
			"versionNonce": 2049906576,
			"isDeleted": false,
			"id": "7oVp0HAANTqYWXKsMVsVV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -515.9938504048949,
			"y": -55.44057853708679,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 6.583673741404226,
			"height": 59.95345449619171,
			"seed": 826257932,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.14007816471065934,
					18.630395906526864
				],
				[
					6.443595576693567,
					36.56040098950009
				],
				[
					4.6225794354540515,
					59.95345449619171
				]
			]
		},
		{
			"type": "line",
			"version": 478,
			"versionNonce": 1436281200,
			"isDeleted": false,
			"id": "HTLGpHtYc7qtVaVcnMsWN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -503.5082163109872,
			"y": -9.439349708810255,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 5.1394523958532305,
			"height": 34.30285668860183,
			"seed": 353734796,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					5.1394523958532305,
					16.135490080004345
				],
				[
					0,
					34.30285668860183
				]
			]
		},
		{
			"type": "line",
			"version": 569,
			"versionNonce": 1367713168,
			"isDeleted": false,
			"id": "f1Zqoh9Vqryv9I9tUb0ke",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -506.0867689704987,
			"y": 14.95799929831935,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 16.32641249812652,
			"height": 49.98704073500464,
			"seed": 1873518348,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.62809166625033,
					29.83097592250277
				],
				[
					6.853062036250654,
					49.98704073500464
				],
				[
					12.698320831876188,
					28.823172681877672
				],
				[
					0.6046819443750437,
					23.179474534377157
				],
				[
					5.039016203125454,
					37.691841199378494
				]
			]
		},
		{
			"type": "freedraw",
			"version": 480,
			"versionNonce": 792542064,
			"isDeleted": false,
			"id": "G29AZE6FkGNVC2jRNB0dd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -492.1790842498724,
			"y": 73.0074659583247,
			"strokeColor": "#6c3507",
			"backgroundColor": "#672f14",
			"width": 10.88427499875099,
			"height": 36.48247731062839,
			"seed": 1501289868,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					-2.4187277775002425,
					21.566989349376993
				],
				[
					8.465547221250748,
					36.48247731062839
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 499,
			"versionNonce": 1524265872,
			"isDeleted": false,
			"id": "YSBMCE0kejz4Xk7Q6XBNe",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -505.0991700376908,
			"y": 76.63555762457503,
			"strokeColor": "#90511c",
			"backgroundColor": "#672f14",
			"width": 15.11704860937643,
			"height": 47.56831295750442,
			"seed": 1270893580,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					0.40312129625007415,
					20.55918610875191
				],
				[
					5.643698147500499,
					42.32773610625392
				],
				[
					15.11704860937643,
					47.56831295750442
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 468,
			"versionNonce": 753159536,
			"isDeleted": false,
			"id": "tBz9QOlkCiiQqb2kCBjVs",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -527.0223083424362,
			"y": -245.3037127205829,
			"strokeColor": "#90511c",
			"backgroundColor": "#672f14",
			"width": 7.542820682825842,
			"height": 20.011565076885013,
			"seed": 141748876,
			"groupIds": [
				"2Qu4IrkUERBQ0nrcwwukq",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018566,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					7.388885566849841,
					10.62152300234666
				],
				[
					7.542820682825842,
					20.011565076885013
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 3024,
			"versionNonce": 1013285264,
			"isDeleted": false,
			"id": "GHFEzN2bDQXRBvi4ZiBGN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.220026921067632,
			"x": -389.864756147833,
			"y": -58.552630664026026,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#c07912",
			"width": 268.18598082559777,
			"height": 170.32836614427762,
			"seed": 38648076,
			"groupIds": [
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-15.522548150365772,
					11.343400571421165
				],
				[
					-38.507859834561316,
					13.731484902246674
				],
				[
					-53.13487636086755,
					7.761274075182903
				],
				[
					-100.89656297737773,
					13.134463819540315
				],
				[
					-131.3446381954029,
					17.015100857131756
				],
				[
					-164.18079774425368,
					19.403185187957266
				],
				[
					-210.74844219535112,
					23.58233276690189
				],
				[
					-232.5397117141338,
					22.68680114284235
				],
				[
					-246.24270647836673,
					18.263643135772373
				],
				[
					-248.84080145497632,
					7.703242327004764
				],
				[
					-250.56408486590377,
					1.0255191096605671
				],
				[
					-244.10177207492558,
					-5.652204107683629
				],
				[
					-246.2919166747582,
					-17.068956705078563
				],
				[
					-245.39423463312124,
					-25.900784186082188
				],
				[
					-249.34370298005467,
					-34.30752034015829
				],
				[
					-255.0877038195886,
					-47.01100596994452
				],
				[
					-244.29343280740054,
					-59.76199098751274
				],
				[
					-255.7339350986864,
					-78.24551779300613
				],
				[
					-255.96736569313885,
					-94.48483949440701
				],
				[
					-265.2119938587879,
					-102.5868959723576
				],
				[
					-261.119195757835,
					-110.7724921742634
				],
				[
					-262.84247916876257,
					-127.14368457807498
				],
				[
					-250.13326401317195,
					-137.05256419090833
				],
				[
					-200.37345552263935,
					-137.48338504364023
				],
				[
					-67.68063288121894,
					-145.88439167191197
				],
				[
					-15.766720127026929,
					-146.74603337737574
				],
				[
					-5.4270196614617605,
					-133.8214077954192
				],
				[
					2.9739869668099135,
					-115.29611112794818
				],
				[
					-1.3342215605088732,
					-105.60264194148078
				],
				[
					2.7585765404440146,
					-98.0632770186728
				],
				[
					-4.349967529632131,
					-91.60096422769452
				],
				[
					-8.227355204219053,
					-78.89174907210396
				],
				[
					0.6044722767846213,
					-64.67466093195178
				],
				[
					-1.9804528396067045,
					-46.58018511721266
				],
				[
					2.1123452613461833,
					-40.548693178966275
				],
				[
					-1.7650424132408058,
					-27.408657170643814
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 2861,
			"versionNonce": 1205411696,
			"isDeleted": false,
			"id": "tyisHYBiBxB5RkTV15BGP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.220026921067632,
			"x": -389.57795052867266,
			"y": -62.262793746363684,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f0a548",
			"width": 268.18598082559777,
			"height": 170.32836614427762,
			"seed": 1154135948,
			"groupIds": [
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-15.522548150365772,
					11.343400571421165
				],
				[
					-38.507859834561316,
					13.731484902246674
				],
				[
					-53.13487636086755,
					7.761274075182903
				],
				[
					-100.89656297737773,
					13.134463819540315
				],
				[
					-131.3446381954029,
					17.015100857131756
				],
				[
					-164.18079774425368,
					19.403185187957266
				],
				[
					-210.74844219535112,
					23.58233276690189
				],
				[
					-232.5397117141338,
					22.68680114284235
				],
				[
					-248.3607704058529,
					17.910632481191332
				],
				[
					-248.84080145497632,
					7.703242327004764
				],
				[
					-250.56408486590377,
					1.0255191096605671
				],
				[
					-244.10177207492558,
					-5.652204107683629
				],
				[
					-248.40998060224436,
					-17.068956705078563
				],
				[
					-245.39423463312124,
					-25.900784186082188
				],
				[
					-253.57983083502702,
					-30.424403139766973
				],
				[
					-255.0877038195886,
					-47.01100596994452
				],
				[
					-247.1175180440487,
					-57.99693771460759
				],
				[
					-255.7339350986864,
					-78.24551779300613
				],
				[
					-257.02639765688207,
					-90.95473294859673
				],
				[
					-265.2119938587879,
					-102.5868959723576
				],
				[
					-261.119195757835,
					-110.7724921742634
				],
				[
					-262.84247916876257,
					-127.14368457807498
				],
				[
					-250.13326401317195,
					-137.05256419090833
				],
				[
					-200.37345552263935,
					-137.48338504364023
				],
				[
					-67.68063288121894,
					-145.88439167191197
				],
				[
					-15.766720127026929,
					-146.74603337737574
				],
				[
					-5.4270196614617605,
					-133.8214077954192
				],
				[
					2.9739869668099135,
					-115.29611112794818
				],
				[
					-1.3342215605088732,
					-105.60264194148078
				],
				[
					2.7585765404440146,
					-98.0632770186728
				],
				[
					-4.349967529632131,
					-91.60096422769452
				],
				[
					-8.227355204219053,
					-78.89174907210396
				],
				[
					0.6044722767846213,
					-64.67466093195178
				],
				[
					-1.9804528396067045,
					-46.58018511721266
				],
				[
					2.1123452613461833,
					-40.548693178966275
				],
				[
					-1.7650424132408058,
					-27.408657170643814
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1866,
			"versionNonce": 358535056,
			"isDeleted": false,
			"id": "CJiWdIRqWuQoBf1kdgbhh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 6.220026921067632,
			"x": -637.0706457261848,
			"y": -44.010883904698574,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#bb7b1d",
			"width": 27.44861594293937,
			"height": 156.73736450651668,
			"seed": 1545856524,
			"groupIds": [
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.196071719383391,
					-7.896177189064788
				],
				[
					3.0080675005960456,
					-16.92037969085311
				],
				[
					-0.7520168751491125,
					-26.69659906779046
				],
				[
					1.8800421878725115,
					-36.09681000715329
				],
				[
					-6.956156095128549,
					-43.24097032106904
				],
				[
					-6.580147657553993,
					-60.16135001192215
				],
				[
					0.9400210939361883,
					-68.6215398573487
				],
				[
					-8.272185626639294,
					-88.36198283001067
				],
				[
					-8.836198283001195,
					-100.9582654887569
				],
				[
					-17.108383909640352,
					-110.35847642811972
				],
				[
					-14.332932257265957,
					-121.85196074955834
				],
				[
					-15.792354378129609,
					-137.0550754959102
				],
				[
					-9.201083240299699,
					-145.93943578488887
				],
				[
					-1.1280253127236688,
					-146.83129487284754
				],
				[
					-7.520168751490315,
					-135.1750333080376
				],
				[
					-4.888109688468692,
					-120.51070424263159
				],
				[
					-7.708172970277526,
					-111.29849752205601
				],
				[
					-2.8200632818088347,
					-103.59032455177848
				],
				[
					-1.1280253127236688,
					-89.30200392394696
				],
				[
					7.708172970277526,
					-77.26973392156255
				],
				[
					6.956156095128414,
					-64.29744282524183
				],
				[
					1.5040337502979553,
					-53.017189698006426
				],
				[
					4.888109688468692,
					-39.48088594532394
				],
				[
					8.83619828300106,
					-34.21676781928074
				],
				[
					6.392143438766647,
					-21.43248094174728
				],
				[
					10.340232033299015,
					-13.160295315107986
				],
				[
					6.353082220130187,
					-0.35244707526476476
				],
				[
					7.688788316258965,
					9.906069633669148
				],
				[
					0.24615818084262298,
					8.064796753833573
				],
				[
					-0.9400210939363232,
					2.2560506254470676
				]
			]
		},
		{
			"type": "line",
			"version": 1707,
			"versionNonce": 274968944,
			"isDeleted": false,
			"id": "8ux1MpPYr-2WsomhNbmT4",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -523.7330787674775,
			"y": -192.14421237701555,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#bfc2c9",
			"width": 4.7583393648275765,
			"height": 9.324144766916493,
			"seed": 1028867212,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					3.6856501438548923,
					-3.6306404402152728
				],
				[
					2.94301914471995,
					-7.233776028610724
				],
				[
					1.8153202201076262,
					-9.324144766916493
				],
				[
					1.3202328873510045,
					-7.481319694989046
				],
				[
					1.5952814055491256,
					-3.7681646993143527
				],
				[
					-1.0726892209726837,
					-1.3477377391708247
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1914,
			"versionNonce": 1576951184,
			"isDeleted": false,
			"id": "nKvIuOFfy7GEDwm62wlcl",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -519.9364345908868,
			"y": -195.62821969764332,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 4.361662741519731,
			"height": 5.271922791923865,
			"seed": 772985612,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.9343026071087412,
					-0.45513002520205686
				],
				[
					3.8306777121173115,
					1.3274625735060386
				],
				[
					4.361662741519731,
					3.7927502100171795
				],
				[
					3.034200168013712,
					4.816792766721808
				],
				[
					2.654925147011998,
					3.944460218417865
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1825,
			"versionNonce": 1305215856,
			"isDeleted": false,
			"id": "Fi5u-UzZr04Q0Ihx2pNTM",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.695950991298414,
			"x": -520.210987088111,
			"y": -193.9283518640022,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d3d8de",
			"width": 5.8496183240156485,
			"height": 3.08529683268918,
			"seed": 752652684,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1285,
			"versionNonce": 1199319952,
			"isDeleted": false,
			"id": "MVKZ3FrurJQ7SWqIDmmVs",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -519.7981211951901,
			"y": -193.18553766917483,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.5846447270415157,
			"height": 0.42224341397442033,
			"seed": 1491763212,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5846447270415157,
					-0.42224341397442033
				]
			]
		},
		{
			"type": "line",
			"version": 1292,
			"versionNonce": 509220208,
			"isDeleted": false,
			"id": "iJJFB8Ukl2_EVWnEZin1h",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -519.3219834042958,
			"y": -193.7659764422475,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a6acb2",
			"width": 0.5846447270415157,
			"height": 0.42224341397442033,
			"seed": 1513528972,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.5846447270415157,
					-0.42224341397442033
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1298,
			"versionNonce": 470825360,
			"isDeleted": false,
			"id": "k2t17i8KNaHY60h6685Q2",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.163527388836053,
			"x": -517.0337707224,
			"y": -193.74376647212046,
			"strokeColor": "transparent",
			"backgroundColor": "#f8f9fb",
			"width": 1.46161181760374,
			"height": 2.0509849273307346,
			"seed": 1232792844,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2178,
			"versionNonce": 391505776,
			"isDeleted": false,
			"id": "FT2z1-G9HxuvWpl3FIjId",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -522.9921557727903,
			"y": -192.1598352816472,
			"strokeColor": "transparent",
			"backgroundColor": "#9ca2ad",
			"width": 2.804532686468228,
			"height": 8.240253842546117,
			"seed": 405891980,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6592190224049781,
					-1.2965560194709926
				],
				[
					1.5567395434369034,
					-3.3217780542430075
				],
				[
					1.3035543557284017,
					-6.760538454249467
				],
				[
					1.394200224343422,
					-8.240253842546117
				],
				[
					2.1453136640632504,
					-3.7319134961512406
				],
				[
					0.07641673116997168,
					-1.3445397008114737
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1201,
			"versionNonce": 519210896,
			"isDeleted": false,
			"id": "kSTJMcDlrtIETvdtH0-V6",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -527.338605607276,
			"y": -197.77051083121455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9ca2ad",
			"width": 2.949133760561057,
			"height": 0.4870186020583785,
			"seed": 2022971916,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1588761711542,
					0.3772252964002685
				],
				[
					2.0965935904378203,
					0.0862095455882212
				],
				[
					2.949133760561057,
					0.4870186020583785
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1113,
			"versionNonce": 1694988656,
			"isDeleted": false,
			"id": "FTwYHrpisNICCUJ-JrjwV",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.721270659659561,
			"x": -528.6840726999246,
			"y": -198.5220485269743,
			"strokeColor": "#f0a548",
			"backgroundColor": "#f0a548",
			"width": 2.5665145560719322,
			"height": 2.4277840395274923,
			"seed": 1167915148,
			"groupIds": [
				"9cQUyqBfSElINXdKakccX",
				"ERXgZQhGMbwZ-Quj0mkS5",
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 451,
			"versionNonce": 1817908624,
			"isDeleted": false,
			"id": "sVLRwdrvMUsCdYnB6eaYf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -601.8460726916425,
			"y": -121.69255462746389,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 49.9634588412713,
			"height": 16.007710114193728,
			"seed": 1795557132,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					20.858531360919113,
					-16.007710114193728
				],
				[
					49.9634588412713,
					-10.186724618123284
				]
			]
		},
		{
			"type": "line",
			"version": 619,
			"versionNonce": 1790364528,
			"isDeleted": false,
			"id": "_RfzABGexbRVcTN8Q_3XU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -502.4042371337723,
			"y": -145.46157873641823,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 98.47167130852509,
			"height": 26.67951685698959,
			"seed": 1296647564,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					36.86624147511291,
					4.365739122052841
				],
				[
					77.1280578229335,
					-11.641970992140887
				],
				[
					98.47167130852509,
					4.850821246725387
				],
				[
					58.69493708537705,
					15.037545864848704
				],
				[
					74.70264719957078,
					0.48508212467254536
				]
			]
		},
		{
			"type": "line",
			"version": 560,
			"versionNonce": 1501684624,
			"isDeleted": false,
			"id": "yPSeGbBjuFRRIHKQCNX8N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -512.105879627223,
			"y": -117.32681550541105,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 100.41199980721528,
			"height": 62.0905119580848,
			"seed": 832615436,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-31.53033810371498,
					18.91820286222893
				],
				[
					-83.919207568349,
					20.858531360919113
				],
				[
					-100.41199980721528,
					46.56788396856361
				],
				[
					-65.48608683079254,
					62.0905119580848
				],
				[
					-53.844115838651724,
					43.172309095855866
				],
				[
					-78.09822207227859,
					44.14247334520089
				]
			]
		},
		{
			"type": "freedraw",
			"version": 495,
			"versionNonce": 1655430512,
			"isDeleted": false,
			"id": "Mk44r7ZLAT8OehoJDN7Z7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -538.1584390394563,
			"y": -73.66942428488261,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 134.8528306589654,
			"height": 16.492792238866272,
			"seed": 637948556,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					50.44854096594391,
					6.791149745415501
				],
				[
					75.67281144891587,
					-9.701642493450773
				],
				[
					119.3302026694442,
					1.4552463740175687
				],
				[
					134.8528306589654,
					-8.731478244105682
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 511,
			"versionNonce": 1419702672,
			"isDeleted": false,
			"id": "aPvpcBwOyZ61T-b3oweNh",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -413.00725087394164,
			"y": -104.71468026392506,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 87.7998645657293,
			"height": 11.641970992140887,
			"seed": 1765024012,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					-37.35132359978539,
					-11.641970992140887
				],
				[
					-58.209854960704504,
					-4.365739122052841
				],
				[
					-87.7998645657293,
					-3.880656997380296
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 480,
			"versionNonce": 2116988784,
			"isDeleted": false,
			"id": "Wjk3sv7STeMQHClORA03F",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -507.59826518508646,
			"y": -184.75323083489377,
			"strokeColor": "#d4831a",
			"backgroundColor": "#c07912",
			"width": 94.59101431114486,
			"height": 15.522627989521183,
			"seed": 1386487692,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					30.560173854369886,
					-12.612135241485978
				],
				[
					69.36674382817291,
					-2.910492748035205
				],
				[
					94.59101431114486,
					-15.522627989521183
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 533,
			"versionNonce": 1156202384,
			"isDeleted": false,
			"id": "G57mtP3w0F3Vwbal4IXQO",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -626.4433857298582,
			"y": -165.83502797266482,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 127.09151666420473,
			"height": 12.127053116813432,
			"seed": 982535692,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					50.933623090616386,
					-12.127053116813432
				],
				[
					87.79986456572922,
					-2.910492748035205
				],
				[
					127.09151666420473,
					-7.761313994760592
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 466,
			"versionNonce": 92750192,
			"isDeleted": false,
			"id": "LlUFN9qtXMlFi_uwvsxdP",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": -624.6860329202025,
			"y": -134.2343435103008,
			"strokeColor": "#d5851f",
			"backgroundColor": "#c07912",
			"width": 89.9080957268816,
			"height": 26.54429492888883,
			"seed": 1643293836,
			"groupIds": [
				"iG88P-yABHplsmWyf1aHE",
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"customData": {
				"strokeOptions": {
					"options": {
						"thinning": 4,
						"smoothing": 0.5,
						"streamline": 0.5,
						"easing": "linear",
						"start": {
							"taper": true,
							"easing": "linear",
							"cap": true
						},
						"end": {
							"taper": true,
							"easing": "linear",
							"cap": false
						}
					}
				}
			},
			"points": [
				[
					0,
					0
				],
				[
					41.10084376086011,
					-26.54429492888883
				],
				[
					89.9080957268816,
					-15.412816410322558
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": false,
			"pressures": [
				1,
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 480,
			"versionNonce": 1788595600,
			"isDeleted": false,
			"id": "9rHjKFvq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.151000877772952,
			"x": -608.8215844705112,
			"y": -191.22161148095904,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 190.01113891601562,
			"height": 126.5222472784381,
			"seed": 1347302924,
			"groupIds": [
				"zEJ7iP9abG3CevkexwLzh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"fontSize": 14.45968540325007,
			"fontFamily": 1,
			"text": "Graph neural networks are\nused to represent:\n\nKnowledge Graphs\nChemical compounds\nSocial network\nTopology",
			"rawText": "Graph neural networks are\nused to represent:\n\nKnowledge Graphs\nChemical compounds\nSocial network\nTopology",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph neural networks are\nused to represent:\n\nKnowledge Graphs\nChemical compounds\nSocial network\nTopology",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 336,
			"versionNonce": 2013107056,
			"isDeleted": false,
			"id": "e3onwHrL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -340.1115521735639,
			"y": -105.43631917077795,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 639.559326171875,
			"height": 300,
			"seed": 1004891956,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets take a few \n1) A graph is invariant to the order of nodes and edges\n{v1,v2,v3} = {v3,v2,v1}\n\n2) Edges are symmetric in their representation\n(u,v) = (v,u)\n\n3) Input graphs may have a varying number of nodes and edges\n\n4) Labels may be attached to nodes and edges which provide us\nwith extra information\n",
			"rawText": "Lets take a few \n1) A graph is invariant to the order of nodes and edges\n{v1,v2,v3} = {v3,v2,v1}\n\n2) Edges are symmetric in their representation\n(u,v) = (v,u)\n\n3) Input graphs may have a varying number of nodes and edges\n\n4) Labels may be attached to nodes and edges which provide us\nwith extra information\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets take a few \n1) A graph is invariant to the order of nodes and edges\n{v1,v2,v3} = {v3,v2,v1}\n\n2) Edges are symmetric in their representation\n(u,v) = (v,u)\n\n3) Input graphs may have a varying number of nodes and edges\n\n4) Labels may be attached to nodes and edges which provide us\nwith extra information\n",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 114,
			"versionNonce": 1055628176,
			"isDeleted": false,
			"id": "sbLlxQ2ri_z1qwoPw1883",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -353.201994029977,
			"y": 179.19476955859847,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 665.7402097891381,
			"height": 1.3586534893656221,
			"seed": 437798924,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					665.7402097891381,
					1.3586534893656221
				]
			]
		},
		{
			"type": "text",
			"version": 120,
			"versionNonce": 735683952,
			"isDeleted": false,
			"id": "2L1fgXPO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -147.79735228651998,
			"y": 212.67939262277037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 234.13699340820312,
			"height": 35,
			"seed": 1973951500,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Graph Properties",
			"rawText": "Graph Properties",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph Properties",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 505,
			"versionNonce": 1410443664,
			"isDeleted": false,
			"id": "1KzszdM2j96SfxAwztlW4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -33.834360050332634,
			"y": 264.08378064403905,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 224.5372516464995,
			"height": 186.16502272488367,
			"seed": 711744308,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "DvaQf7hg",
				"focus": 0.029294804789040903,
				"gap": 2.917871080170528
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
					31.24903025540857,
					80.44961622004871
				],
				[
					205.7688046888652,
					85.74820177869742
				],
				[
					224.5372516464995,
					186.16502272488367
				]
			]
		},
		{
			"type": "arrow",
			"version": 458,
			"versionNonce": 1852012400,
			"isDeleted": false,
			"id": "0iOELPpawCvZNz8qYH9VM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -32.475706560966955,
			"y": 266.8010876227703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 212.7738012594541,
			"height": 174.01129843667593,
			"seed": 1173445772,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "A74Lulfu",
				"focus": -0.06707438656943593,
				"gap": 7.247107597893546
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
					-23.097109319215065,
					75.202041310955
				],
				[
					-194.99228104873956,
					93.36532614394753
				],
				[
					-212.7738012594541,
					174.01129843667593
				]
			]
		},
		{
			"type": "text",
			"version": 91,
			"versionNonce": 893777808,
			"isDeleted": false,
			"id": "A74Lulfu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -313.29675347173827,
			"y": 448.0594936573398,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 134.736572265625,
			"height": 35,
			"seed": 1556188980,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "0iOELPpawCvZNz8qYH9VM",
					"type": "arrow"
				}
			],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Subgraphs",
			"rawText": "Subgraphs",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Subgraphs",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 165,
			"versionNonce": 602081648,
			"isDeleted": false,
			"id": "DvaQf7hg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 98.78286896406264,
			"y": 453.16667444909325,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 185.83677673339844,
			"height": 35,
			"seed": 1654285324,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "1KzszdM2j96SfxAwztlW4",
					"type": "arrow"
				}
			],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Random walks",
			"rawText": "Random walks",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Random walks",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 301,
			"versionNonce": 1187022224,
			"isDeleted": false,
			"id": "g3lnGk1E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -448.63964473553636,
			"y": 489.53759808642894,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 402.9595031738281,
			"height": 175,
			"seed": 1574412340,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Represent the graph as a bunch\nof sub-graphs\n\nThis number exponentially grows with\nthe size of the graph\n\nThis does not capture global information",
			"rawText": "Represent the graph as a bunch\nof sub-graphs\n\nThis number exponentially grows with\nthe size of the graph\n\nThis does not capture global information",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Represent the graph as a bunch\nof sub-graphs\n\nThis number exponentially grows with\nthe size of the graph\n\nThis does not capture global information",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 505,
			"versionNonce": 1738562416,
			"isDeleted": false,
			"id": "5jMLhFcc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -21.966084043355416,
			"y": 491.473720025396,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 429.3794860839844,
			"height": 200,
			"seed": 1202975244,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Sample a random walk in a random direction\nalongside the graph\n\ninformation about (non)locality\nof walks may be hard to recover\n\nmany walks are required to represent\nthe graph",
			"rawText": "Sample a random walk in a random direction\nalongside the graph\n\ninformation about (non)locality\nof walks may be hard to recover\n\nmany walks are required to represent\nthe graph",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sample a random walk in a random direction\nalongside the graph\n\ninformation about (non)locality\nof walks may be hard to recover\n\nmany walks are required to represent\nthe graph",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 105,
			"versionNonce": 632902544,
			"isDeleted": false,
			"id": "FJJgnZjV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 134.70913083185096,
			"y": 706.8983344152031,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 113.9842529296875,
			"height": 20,
			"seed": 386921356,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "B_YkoMY9eQmKMvMDrHLYt",
					"type": "arrow"
				}
			],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Similar to RNN",
			"rawText": "Similar to RNN",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Similar to RNN",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 124,
			"versionNonce": 736324976,
			"isDeleted": false,
			"id": "xvhwdoKh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -339.4000966795656,
			"y": 691.4737203474965,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 184.48040771484375,
			"height": 40,
			"seed": 299733772,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Same as embedding into\na feature space",
			"rawText": "Same as embedding into\na feature space",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Same as embedding into\na feature space",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 100,
			"versionNonce": 141058448,
			"isDeleted": false,
			"id": "cxKgBSbJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -150.5837049049919,
			"y": 767.2937906310167,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 234.22097778320312,
			"height": 105,
			"seed": 117684404,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "B_YkoMY9eQmKMvMDrHLYt",
					"type": "arrow"
				},
				{
					"id": "JORTZXfAetttBm0N9jeK4",
					"type": "arrow"
				}
			],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "\nWeisfeiler-Lehman\nisomorphism test",
			"rawText": "\nWeisfeiler-Lehman\nisomorphism test",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "\nWeisfeiler-Lehman\nisomorphism test",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 676,
			"versionNonce": 1509179248,
			"isDeleted": false,
			"id": "B_YkoMY9eQmKMvMDrHLYt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 199.13567270116528,
			"y": 737.2337217977408,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 107.78360242713222,
			"height": 96.27273226501143,
			"seed": 1291521204,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FJJgnZjV",
				"focus": -0.14550453342736983,
				"gap": 10.33538738253776
			},
			"endBinding": {
				"elementId": "cxKgBSbJ",
				"focus": 0.3277221756688303,
				"gap": 7.714797395821819
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
					-4.185770968043926,
					92.08696129696727
				],
				[
					-107.78360242713222,
					96.27273226501143
				]
			]
		},
		{
			"type": "arrow",
			"version": 398,
			"versionNonce": 503689104,
			"isDeleted": false,
			"id": "JORTZXfAetttBm0N9jeK4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -274.90288942981334,
			"y": 747.6981492178509,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 115.10870162120904,
			"height": 91.04051855495618,
			"seed": 1101875084,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "cxKgBSbJ",
				"focus": -0.4677367358315535,
				"gap": 9.210482903612416
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
					8.371541936087908,
					82.66897661886821
				],
				[
					115.10870162120904,
					91.04051855495618
				]
			]
		},
		{
			"type": "text",
			"version": 77,
			"versionNonce": 1914360176,
			"isDeleted": false,
			"id": "Lzr6egqH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -340.0728555959515,
			"y": 905.2465759715654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 613.1992797851562,
			"height": 50,
			"seed": 340254900,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Step 1:\nif nodes are not labeled, assign the same label to each node.",
			"rawText": "Step 1:\nif nodes are not labeled, assign the same label to each node.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Step 1:\nif nodes are not labeled, assign the same label to each node.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 136,
			"versionNonce": 1858682256,
			"isDeleted": false,
			"id": "zkD4ftaKprHB6CzBAwnvq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -167.18170512114253,
			"y": 955.246575680155,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 267.4169790085489,
			"height": 160.62966188768542,
			"seed": 1830366476,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018567,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "059468076d5f8a425d17725236e7cf7d981e4789",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 155,
			"versionNonce": 731849584,
			"isDeleted": false,
			"id": "IEQZjcYh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -910.1822658344752,
			"y": 1056.8426375306954,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 411.9395446777344,
			"height": 75,
			"seed": 1190423860,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Step 2:\nRelabel nodes with tuple of own label and\nsorted multi-set of neighbor labels.",
			"rawText": "Step 2:\nRelabel nodes with tuple of own label and\nsorted multi-set of neighbor labels.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Step 2:\nRelabel nodes with tuple of own label and\nsorted multi-set of neighbor labels.",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 329,
			"versionNonce": 1005259664,
			"isDeleted": false,
			"id": "OAeOAVD1yKL3bWJ5NVLdu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -849.2790092061687,
			"y": 1144.985832061393,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 288.7875131136889,
			"height": 173.46632499110842,
			"seed": 809374092,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c353a70af325f9ef7e8cf9c7e536647dbdf86414",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 408,
			"versionNonce": 348730736,
			"isDeleted": false,
			"id": "eBLV6iL7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -876.5368277748032,
			"y": 1484.341589037349,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 850.21923828125,
			"height": 100,
			"seed": 2064149260,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "56ojMKtYrjytFqBY4HD6s",
					"type": "arrow"
				}
			],
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Step 3:\nCompress labels using hash function (here: sequential id).\nIts important to note that this hash function encodes the label of the current node\nits neighbors, moving  forward we will use this has function multiple times",
			"rawText": "Step 3:\nCompress labels using hash function (here: sequential id).\nIts important to note that this hash function encodes the label of the current node\nits neighbors, moving  forward we will use this has function multiple times",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Step 3:\nCompress labels using hash function (here: sequential id).\nIts important to note that this hash function encodes the label of the current node\nits neighbors, moving  forward we will use this has function multiple times",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 458,
			"versionNonce": 1604524432,
			"isDeleted": false,
			"id": "hrRna-N7mLv1OrkPTEchD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -600.2021650323363,
			"y": 1609.6502308554832,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 282.73509802988673,
			"height": 169.83081391728095,
			"seed": 342793868,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "W_GpI3bwL1Wl4ibQ7GIpd",
					"type": "arrow"
				}
			],
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d115c8e13badfc51411be92ff2d4fb73af18fbf5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 959,
			"versionNonce": 853608304,
			"isDeleted": false,
			"id": "za4I4aPx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 77.06846138511321,
			"y": 1101.7870077004923,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1013.2989501953125,
			"height": 200,
			"seed": 1808089228,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "F2d6OKcSHXmFjdHpeQt3e",
					"type": "arrow"
				}
			],
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Step 4:\nWe check our stop conditions and compare:\n\nIf the labels of the graph nodes differed from the last iteration -> We continue with step 2\nIf the labels of the graph nodes did not differ from the last iteration -> Stop and check isomorphism\n\nIf both graphs have the same representation -> Isomorphic\nIf the graphs have a different representation -> Not isomorphic",
			"rawText": "Step 4:\nWe check our stop conditions and compare:\n\nIf the labels of the graph nodes differed from the last iteration -> We continue with step 2\nIf the labels of the graph nodes did not differ from the last iteration -> Stop and check isomorphism\n\nIf both graphs have the same representation -> Isomorphic\nIf the graphs have a different representation -> Not isomorphic",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Step 4:\nWe check our stop conditions and compare:\n\nIf the labels of the graph nodes differed from the last iteration -> We continue with step 2\nIf the labels of the graph nodes did not differ from the last iteration -> Stop and check isomorphism\n\nIf both graphs have the same representation -> Isomorphic\nIf the graphs have a different representation -> Not isomorphic",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 793,
			"versionNonce": 757688208,
			"isDeleted": false,
			"id": "UlQWKs01duRvRkQHe-NPG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 456.5841989033133,
			"y": 1314.072737426236,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 282.73509802988673,
			"height": 169.83081391728095,
			"seed": 1490014064,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d115c8e13badfc51411be92ff2d4fb73af18fbf5",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ycueD74u",
			"type": "text",
			"x": -333.2019941545415,
			"y": -244.76117337660926,
			"width": 628.479248046875,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1399878032,
			"version": 37,
			"versionNonce": 573479280,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"text": "Graph neural networks are typically formulated as func-\ntions that take a graph as input and output a representation\nof the graph. The representation usually takes the form of an\nembedding of the graph nodes in Euclidean space",
			"rawText": "Graph neural networks are typically formulated as func-\ntions that take a graph as input and output a representation\nof the graph. The representation usually takes the form of an\nembedding of the graph nodes in Euclidean space",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph neural networks are typically formulated as func-\ntions that take a graph as input and output a representation\nof the graph. The representation usually takes the form of an\nembedding of the graph nodes in Euclidean space",
			"lineHeight": 1.25
		},
		{
			"id": "a5iPDV05",
			"type": "text",
			"x": 28.408548556390883,
			"y": 1496.1892803211358,
			"width": 1110.6187744140625,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2125862768,
			"version": 598,
			"versionNonce": 1354102160,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "W_GpI3bwL1Wl4ibQ7GIpd",
					"type": "arrow"
				}
			],
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"text": "This test has its own limitations as sometimes it can wrongly identify isomorphism but it never wrongly identifies\nnon-isomorphism so the test is necessary but not sufficient",
			"rawText": "This test has its own limitations as sometimes it can wrongly identify isomorphism but it never wrongly identifies\nnon-isomorphism so the test is necessary but not sufficient",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This test has its own limitations as sometimes it can wrongly identify isomorphism but it never wrongly identifies\nnon-isomorphism so the test is necessary but not sufficient",
			"lineHeight": 1.25
		},
		{
			"id": "JzklF8l9m8vAQNiYxdTip",
			"type": "arrow",
			"x": -723.6859914100453,
			"y": 1670.8747469380064,
			"width": 317.4648584513309,
			"height": 145.46660227040934,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 552101776,
			"version": 901,
			"versionNonce": 905571184,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-294.9997360924226,
					-19.87592159732003
				],
				[
					-317.4648584513309,
					125.59068067308931
				]
			],
			"lastCommittedPoint": [
				154.3209876543209,
				3.7037037037036953
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "uqHuBhzA",
				"focus": 0.10596378991608797,
				"gap": 5.9143217110338355
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "uqHuBhzA",
			"type": "text",
			"x": -1392.8327408784849,
			"y": 1802.3797493221296,
			"width": 622.7392578125,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1920770928,
			"version": 555,
			"versionNonce": 796967824,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "JzklF8l9m8vAQNiYxdTip",
					"type": "arrow"
				}
			],
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"text": "To give a more intuitive understanding of what\nthe purpose of this hash function does lets demonstrate using\ncolors as the result of hash functions",
			"rawText": "To give a more intuitive understanding of what\nthe purpose of this hash function does lets demonstrate using\ncolors as the result of hash functions",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "To give a more intuitive understanding of what\nthe purpose of this hash function does lets demonstrate using\ncolors as the result of hash functions",
			"lineHeight": 1.25
		},
		{
			"id": "Kl3tMpBlKctCDWvngewhY",
			"type": "line",
			"x": -1235.4996223865332,
			"y": 1927.1644665379204,
			"width": 51.9973902219067,
			"height": 58.408027372552624,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 91960720,
			"version": 272,
			"versionNonce": 411762032,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					51.9973902219067,
					58.408027372552624
				]
			],
			"lastCommittedPoint": [
				94.0226782094752,
				50.5728041884297
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "N-L5zPCo7Fv4BslK6fr_Z",
			"type": "ellipse",
			"x": -1188.4882832817955,
			"y": 1980.5864427933038,
			"width": 35.61465083692235,
			"height": 35.614650836922465,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1124918640,
			"version": 228,
			"versionNonce": 1203884432,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "E-2u211UrgtJN4ounwf69",
					"type": "arrow"
				}
			],
			"updated": 1715180018568,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 232,
			"versionNonce": 1797902192,
			"isDeleted": false,
			"id": "V1pIbeuBMFFJtB5v5bOPX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1250.4577757380403,
			"y": 2040.4190561993337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 35.61465083692235,
			"height": 42,
			"seed": 1843049840,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "hFyDboF4"
				}
			],
			"updated": 1715180018568,
			"link": null,
			"locked": false
		},
		{
			"id": "hFyDboF4",
			"type": "text",
			"x": -1238.1901441834327,
			"y": 2051.5698137944164,
			"width": 10.896026611328125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1622337424,
			"version": 194,
			"versionNonce": 280043408,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"text": "3",
			"rawText": "3",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "V1pIbeuBMFFJtB5v5bOPX",
			"originalText": "3",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 294,
			"versionNonce": 1713267056,
			"isDeleted": false,
			"id": "eZ2XRIvOE1VrEF8jKPfmR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1339.4944028303466,
			"y": 2024.0363168143494,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 35.61465083692235,
			"height": 42,
			"seed": 81795440,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "WGexIE7F"
				}
			],
			"updated": 1715180018568,
			"link": null,
			"locked": false
		},
		{
			"id": "WGexIE7F",
			"type": "text",
			"x": -1327.226771275739,
			"y": 2035.187074409432,
			"width": 10.896026611328125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1616190352,
			"version": 195,
			"versionNonce": 1518775696,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"text": "3",
			"rawText": "3",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "eZ2XRIvOE1VrEF8jKPfmR",
			"originalText": "3",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 229,
			"versionNonce": 2024846192,
			"isDeleted": false,
			"id": "a799MSqyLDZYzMupqYh3B",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1350.891091098162,
			"y": 1942.8349129061662,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 35.61465083692235,
			"height": 35.614650836922465,
			"seed": 484212080,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018568,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 259,
			"versionNonce": 779778960,
			"isDeleted": false,
			"id": "Z-Oca3G7BcbENPoQ4-zEp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1264.7036360728096,
			"y": 1895.11128078469,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 35.61465083692235,
			"height": 35.614650836922465,
			"seed": 605020528,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018568,
			"link": null,
			"locked": false
		},
		{
			"id": "rbFFVwI7RBYq2hCMENHjE",
			"type": "line",
			"x": -1261.8544640058558,
			"y": 1916.4800712868434,
			"width": 61.96949245624512,
			"height": 30.62859971975331,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 132778352,
			"version": 237,
			"versionNonce": 1764279664,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-61.96949245624512,
					30.62859971975331
				]
			],
			"lastCommittedPoint": [
				-57.69573435581435,
				31.340892736491696
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "NnYxurPZXBDb9uMH4_ELJ",
			"type": "line",
			"x": -1333.0837656797007,
			"y": 1977.0249777096117,
			"width": 8.547516200861423,
			"height": 49.14821815495293,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 161087888,
			"version": 215,
			"versionNonce": 784632208,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					8.547516200861423,
					49.14821815495293
				]
			],
			"lastCommittedPoint": [
				8.547516200861423,
				49.14821815495293
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "0XHCRy7zarGKovQ5zf_oW",
			"type": "line",
			"x": -1182.789939147888,
			"y": 2009.7904564795804,
			"width": 36.32694385366085,
			"height": 36.32694385366085,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2096561008,
			"version": 212,
			"versionNonce": 1959696240,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-36.32694385366085,
					36.32694385366085
				]
			],
			"lastCommittedPoint": [
				-36.32694385366085,
				36.32694385366085
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "8iKOe-68lAQWy9wBLijcK",
			"type": "line",
			"x": -1251.170068754779,
			"y": 2059.6509676512715,
			"width": 54.13426927212208,
			"height": 12.821274301292078,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 938484080,
			"version": 253,
			"versionNonce": 1989990288,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-54.13426927212208,
					-12.821274301292078
				]
			],
			"lastCommittedPoint": [
				-54.13426927212208,
				-12.821274301292078
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "vGMPJZqcT5FEyy-qn6VMZ",
			"type": "line",
			"x": -1235.4996223865332,
			"y": 2040.4190561993337,
			"width": 14.245860334768963,
			"height": 111.83000362793655,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 306644336,
			"version": 220,
			"versionNonce": 1877617008,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-14.245860334768963,
					-111.83000362793655
				]
			],
			"lastCommittedPoint": [
				-14.245860334768963,
				-111.83000362793655
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "yJ9KGvBu7uLCqu5iTOPdX",
			"type": "line",
			"x": -1311.714975177547,
			"y": 2028.31007491478,
			"width": 60.54490642276801,
			"height": 99.00872932664447,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1698371440,
			"version": 235,
			"versionNonce": 2050712976,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					60.54490642276801,
					-99.00872932664447
				]
			],
			"lastCommittedPoint": [
				60.54490642276801,
				-99.00872932664447
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "8M3c4MPl",
			"type": "text",
			"x": -1146.0352741902066,
			"y": 1933.494132372855,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1515981168,
			"version": 195,
			"versionNonce": 1707309936,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "kKPDb7Wi",
			"type": "text",
			"x": -1250.2964471170485,
			"y": 1903.0912071066978,
			"width": 10.240020751953125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 526224272,
			"version": 220,
			"versionNonce": 1725445008,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"text": "4",
			"rawText": "4",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "4",
			"lineHeight": 1.25
		},
		{
			"id": "s6SbLblz",
			"type": "text",
			"x": -1175.1359397086562,
			"y": 1990.287848563439,
			"width": 11.39202880859375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 392977808,
			"version": 225,
			"versionNonce": 950177136,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"text": "2",
			"rawText": "2",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 256,
			"versionNonce": 44777872,
			"isDeleted": false,
			"id": "4lGgFUxo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1338.56735912472,
			"y": 1951.388390252062,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.39202880859375,
			"height": 20,
			"seed": 1545571728,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715180018568,
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
			"lineHeight": 1.25
		},
		{
			"id": "E-2u211UrgtJN4ounwf69",
			"type": "arrow",
			"x": -1142.6370209166926,
			"y": 1993.447596944531,
			"width": 125.16838500836832,
			"height": 0.6684157680419958,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1755731856,
			"version": 554,
			"versionNonce": 1104109424,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					125.16838500836832,
					-0.6684157680419958
				]
			],
			"lastCommittedPoint": [
				119.5839654263882,
				1.9930660904399247
			],
			"startBinding": {
				"elementId": "N-L5zPCo7Fv4BslK6fr_Z",
				"focus": -0.2693467112856646,
				"gap": 10.669454765963287
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "UEsGXW7U",
			"type": "text",
			"x": -1112.7689547606212,
			"y": 1897.6102753579883,
			"width": 55.0721435546875,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1542603120,
			"version": 230,
			"versionNonce": 216829840,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"text": "Hashing",
			"rawText": "Hashing",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hashing",
			"lineHeight": 1.25
		},
		{
			"id": "lio-wrLPauWMVN8GeFG8U",
			"type": "ellipse",
			"x": -1102.6722112746259,
			"y": 1929.997599327635,
			"width": 14.449729155688487,
			"height": 14.947995678298412,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 333677456,
			"version": 266,
			"versionNonce": 1905389936,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false
		},
		{
			"id": "ZLdu8e8IDuThMNRyZPBDt",
			"type": "ellipse",
			"x": -1102.6722112746259,
			"y": 1949.4299937094231,
			"width": 14.947995678298525,
			"height": 14.947995678298408,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1478623088,
			"version": 289,
			"versionNonce": 500440464,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false
		},
		{
			"id": "XXih5Poa8pUnj_4RV3mgo",
			"type": "ellipse",
			"x": -1102.6722112746259,
			"y": 1968.3641215686011,
			"width": 15.944528723518488,
			"height": 16.941061768738336,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 717610384,
			"version": 307,
			"versionNonce": 1865565040,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "E-2u211UrgtJN4ounwf69",
					"type": "arrow"
				}
			],
			"updated": 1715180018568,
			"link": null,
			"locked": false
		},
		{
			"id": "Y3BO2uiR",
			"type": "text",
			"x": -1085.24810962415,
			"y": 1927.506266714585,
			"width": 17.968048095703125,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 278222192,
			"version": 234,
			"versionNonce": 110750608,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"text": "-2\n-3\n-4",
			"rawText": "-2\n-3\n-4",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "-2\n-3\n-4",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 348,
			"versionNonce": 955798896,
			"isDeleted": false,
			"id": "dSSboB78UBicgPlaFVoKM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -880.5053980517316,
			"y": 1912.742617885829,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 51.9973902219067,
			"height": 58.408027372552624,
			"seed": 227484048,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018568,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					51.9973902219067,
					58.408027372552624
				]
			]
		},
		{
			"type": "ellipse",
			"version": 307,
			"versionNonce": 829815184,
			"isDeleted": false,
			"id": "no0OuYmcTQzV6DGvoAT37",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -832.995792424384,
			"y": 1966.164594141213,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 35.61465083692235,
			"height": 35.614650836922465,
			"seed": 1347710864,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018568,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 314,
			"versionNonce": 1143744368,
			"isDeleted": false,
			"id": "yikoYKKfVe92vw4D7mw7D",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -897.3515420639876,
			"y": 2025.9972075472429,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 35.61465083692235,
			"height": 42,
			"seed": 1765801360,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018568,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 374,
			"versionNonce": 27281296,
			"isDeleted": false,
			"id": "BqwFEwaLIc1JZr8PbcI9H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -985.195040564615,
			"y": 2009.6144681622586,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 35.61465083692235,
			"height": 42,
			"seed": 996792720,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018568,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 307,
			"versionNonce": 487962992,
			"isDeleted": false,
			"id": "Qsg102hCvPlR5WUzMw4Ph",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -995.8968667633605,
			"y": 1928.4130642540754,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 35.61465083692235,
			"height": 35.614650836922465,
			"seed": 2043458960,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 337,
			"versionNonce": 860935568,
			"isDeleted": false,
			"id": "Vx8hP5T3FGxxHIWuqMZvS",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -909.7094117380082,
			"y": 1880.689432132599,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#2f9e44",
			"width": 35.61465083692235,
			"height": 35.614650836922465,
			"seed": 129991568,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 313,
			"versionNonce": 117246832,
			"isDeleted": false,
			"id": "imwBkgUwsXzY9a_Jaz-e5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -906.8602396710542,
			"y": 1902.0582226347524,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 61.96949245624512,
			"height": 30.62859971975331,
			"seed": 707301776,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-61.96949245624512,
					30.62859971975331
				]
			]
		},
		{
			"type": "line",
			"version": 291,
			"versionNonce": 1002414992,
			"isDeleted": false,
			"id": "baO6ihCplUUQkIcBMM6aF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -978.0895413448991,
			"y": 1962.6031290575206,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.547516200861423,
			"height": 49.14821815495293,
			"seed": 2017451920,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.547516200861423,
					49.14821815495293
				]
			]
		},
		{
			"type": "line",
			"version": 288,
			"versionNonce": 472522096,
			"isDeleted": false,
			"id": "dtxJt2QlLk0OvhdU4ct4Z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -827.7957148130865,
			"y": 1995.368607827489,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 36.32694385366085,
			"height": 36.32694385366085,
			"seed": 1648192912,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-36.32694385366085,
					36.32694385366085
				]
			]
		},
		{
			"type": "line",
			"version": 329,
			"versionNonce": 690270608,
			"isDeleted": false,
			"id": "lfYmQrUfvIuXvjqnHlaJ8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -896.1758444199777,
			"y": 2045.2291189991806,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.13426927212208,
			"height": 12.821274301292078,
			"seed": 291060624,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-54.13426927212208,
					-12.821274301292078
				]
			]
		},
		{
			"type": "line",
			"version": 296,
			"versionNonce": 1843720048,
			"isDeleted": false,
			"id": "xLe_fGb3C4hIOggcYStyj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -880.5053980517316,
			"y": 2025.9972075472429,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.245860334768963,
			"height": 111.83000362793655,
			"seed": 1204504976,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-14.245860334768963,
					-111.83000362793655
				]
			]
		},
		{
			"type": "line",
			"version": 311,
			"versionNonce": 45612944,
			"isDeleted": false,
			"id": "PGTA4WiIBPMna-OGE6RtW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -956.7207508427457,
			"y": 2013.888226262689,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60.54490642276801,
			"height": 99.00872932664447,
			"seed": 1087084432,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					60.54490642276801,
					-99.00872932664447
				]
			]
		},
		{
			"id": "TDwN8DZsE_aYXQXnpxeys",
			"type": "arrow",
			"x": -911.11061931006,
			"y": 2078.4054695319046,
			"width": 2.77944827627789,
			"height": 110.48306898205146,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1748305808,
			"version": 270,
			"versionNonce": 611680624,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.77944827627789,
					110.48306898205146
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "gU5Mrijt",
			"type": "text",
			"x": -878.8885531474264,
			"y": 2081.184917808183,
			"width": 55.0721435546875,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 922479472,
			"version": 226,
			"versionNonce": 682724752,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"text": "Hashing",
			"rawText": "Hashing",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hashing",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 313,
			"versionNonce": 522441584,
			"isDeleted": false,
			"id": "GnRRIKRtUNOGCWdYYLwzy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -881.5603319420657,
			"y": 2112.594401674238,
			"strokeColor": "transparent",
			"backgroundColor": "#f08c00",
			"width": 14.449729155688487,
			"height": 14.947995678298412,
			"seed": 661161840,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 334,
			"versionNonce": 877222800,
			"isDeleted": false,
			"id": "KILcAjNuTV5Fz2rm9hUM-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -880.8654698729963,
			"y": 2132.026796056026,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"width": 14.947995678298525,
			"height": 14.947995678298408,
			"seed": 432413040,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 354,
			"versionNonce": 339207536,
			"isDeleted": false,
			"id": "CZJm0QHa-3YeX7GKkIDMv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -880.8654698729963,
			"y": 2150.266061846134,
			"strokeColor": "transparent",
			"backgroundColor": "#846358",
			"width": 15.944528723518488,
			"height": 16.941061768738336,
			"seed": 1319201648,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false
		},
		{
			"id": "bFl8MMpo",
			"type": "text",
			"x": -858.6503480160022,
			"y": 2108.9794005709628,
			"width": 238.57652282714844,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#846358",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1139161456,
			"version": 350,
			"versionNonce": 1471637904,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"text": "- 2 red 2 blue neighbors\n- 1 green 1 blue 1 red neighbors\n- 1 green 1 blue neighbors",
			"rawText": "- 2 red 2 blue neighbors\n- 1 green 1 blue 1 red neighbors\n- 1 green 1 blue neighbors",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- 2 red 2 blue neighbors\n- 1 green 1 blue 1 red neighbors\n- 1 green 1 blue neighbors",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 395,
			"versionNonce": 821671792,
			"isDeleted": false,
			"id": "FgU7yo0kvmcJhJOkU6mu8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -878.3003235287119,
			"y": 2239.1606296800546,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 51.9973902219067,
			"height": 58.408027372552624,
			"seed": 1168186256,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					51.9973902219067,
					58.408027372552624
				]
			]
		},
		{
			"type": "ellipse",
			"version": 356,
			"versionNonce": 1043576720,
			"isDeleted": false,
			"id": "ADw3w-6I6YNoXohgh3iJp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -831.4855799704342,
			"y": 2292.5826059354386,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#846358",
			"width": 35.61465083692235,
			"height": 35.614650836922465,
			"seed": 1746348432,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 362,
			"versionNonce": 967919984,
			"isDeleted": false,
			"id": "tGYBbEy1xqnY1BuQrmiVl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -895.1464675409684,
			"y": 2352.4152193414684,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"width": 35.61465083692235,
			"height": 42,
			"seed": 748386192,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 422,
			"versionNonce": 1811301776,
			"isDeleted": false,
			"id": "dpn8lQ1aOM1x3txfVXKm3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -982.9899660415954,
			"y": 2336.032479956484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"width": 35.61465083692235,
			"height": 42,
			"seed": 929432976,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 356,
			"versionNonce": 698784624,
			"isDeleted": false,
			"id": "wN7GOUCzku0PFfunVTw5y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -993.6917922403411,
			"y": 2254.831076048301,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#846358",
			"width": 35.61465083692235,
			"height": 35.614650836922465,
			"seed": 1705956240,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 386,
			"versionNonce": 506925968,
			"isDeleted": false,
			"id": "eMltLkOsObIZQAp5-rzHh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -907.5043372149889,
			"y": 2207.107443926824,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#f08c00",
			"width": 35.61465083692235,
			"height": 35.614650836922465,
			"seed": 766370192,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 360,
			"versionNonce": 1394716016,
			"isDeleted": false,
			"id": "mAmxhbcjaH0kBf0TnKvkC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -904.6551651480345,
			"y": 2228.4762344289775,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 61.96949245624512,
			"height": 30.62859971975331,
			"seed": 2124099472,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-61.96949245624512,
					30.62859971975331
				]
			]
		},
		{
			"type": "line",
			"version": 338,
			"versionNonce": 724443536,
			"isDeleted": false,
			"id": "YciU2OqjO4zTB7XnHYj2x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -975.8844668218796,
			"y": 2289.021140851746,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.547516200861423,
			"height": 49.14821815495293,
			"seed": 548322704,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.547516200861423,
					49.14821815495293
				]
			]
		},
		{
			"type": "line",
			"version": 335,
			"versionNonce": 2137685872,
			"isDeleted": false,
			"id": "Mk9vEtmcTbRiL5L2B8DwY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -825.5906402900669,
			"y": 2321.7866196217146,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 36.32694385366085,
			"height": 36.32694385366085,
			"seed": 354454416,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-36.32694385366085,
					36.32694385366085
				]
			]
		},
		{
			"type": "line",
			"version": 376,
			"versionNonce": 1645440912,
			"isDeleted": false,
			"id": "MeCX7abqZtKoitqV2awzO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -893.9707698969582,
			"y": 2371.647130793406,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.13426927212208,
			"height": 12.821274301292078,
			"seed": 1982372240,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-54.13426927212208,
					-12.821274301292078
				]
			]
		},
		{
			"type": "line",
			"version": 343,
			"versionNonce": 248058224,
			"isDeleted": false,
			"id": "U2Z6otI4Rw4gfycKh3eGE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -878.3003235287119,
			"y": 2352.4152193414684,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.245860334768963,
			"height": 111.83000362793655,
			"seed": 1459546000,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-14.245860334768963,
					-111.83000362793655
				]
			]
		},
		{
			"type": "line",
			"version": 358,
			"versionNonce": 1797193104,
			"isDeleted": false,
			"id": "Ne-UYsP6OSBeFp4Xlnsg5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -954.515676319726,
			"y": 2340.3062380569145,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60.54490642276801,
			"height": 99.00872932664447,
			"seed": 601585040,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					60.54490642276801,
					-99.00872932664447
				]
			]
		},
		{
			"id": "GFWNGFGfQHfcQfdewf1bT",
			"type": "arrow",
			"x": -1022.9834124302504,
			"y": 2293.8127109434517,
			"width": 109.78820691298176,
			"height": 0.07562624096021864,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1663480176,
			"version": 601,
			"versionNonce": 411394928,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-109.78820691298176,
					-0.07562624096021864
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "PQd4QVv2",
				"focus": 0.1717191194471631,
				"gap": 4.996970895998402
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "PQd4QVv2",
			"type": "text",
			"x": -1349.0010426318086,
			"y": 2188.1936764448865,
			"width": 211.23245239257812,
			"height": 180,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1116513168,
			"version": 665,
			"versionNonce": 663276432,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "GFWNGFGfQHfcQfdewf1bT",
					"type": "arrow"
				}
			],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"text": "We can observe that\nthe last 2 steps\nare identical (while they\ndo have different\ncolors, they have the\nsame distribution of colors\nover the specific nodes)\nthus there is no\nreason to continue",
			"rawText": "We can observe that\nthe last 2 steps\nare identical (while they\ndo have different\ncolors, they have the\nsame distribution of colors\nover the specific nodes)\nthus there is no\nreason to continue",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can observe that\nthe last 2 steps\nare identical (while they\ndo have different\ncolors, they have the\nsame distribution of colors\nover the specific nodes)\nthus there is no\nreason to continue",
			"lineHeight": 1.25
		},
		{
			"id": "AgZa0F3kSmKhUIj-GbRr9",
			"type": "arrow",
			"x": -361.9059247956784,
			"y": 893.644617782794,
			"width": 378.14380754207104,
			"height": 142.31915502445497,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 985784720,
			"version": 339,
			"versionNonce": 182941040,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-204.4341515961678,
					-11.05667154150251
				],
				[
					-351.2873260804113,
					43.97891873255867
				],
				[
					-378.14380754207104,
					131.26248348295246
				]
			],
			"lastCommittedPoint": [
				-404.52575201624813,
				3.357060182707528
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "56ojMKtYrjytFqBY4HD6s",
			"type": "arrow",
			"x": -468.0373222094396,
			"y": 1154.0810842631533,
			"width": 116.52099859300574,
			"height": 311.9089716120477,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1545484176,
			"version": 265,
			"versionNonce": 294181264,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					96.37863749676114,
					65.53550759962559
				],
				[
					116.52099859300574,
					167.9258431722028
				],
				[
					20.844783385843357,
					311.9089716120477
				]
			],
			"lastCommittedPoint": [
				18.463831004891063,
				275.2789349820109
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "eBLV6iL7",
				"focus": -0.026627355519335334,
				"gap": 18.351533162147916
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "W_GpI3bwL1Wl4ibQ7GIpd",
			"type": "arrow",
			"x": -319.2046039904676,
			"y": 1804.8121968663575,
			"width": 870.1524282169439,
			"height": 279.9007444168735,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 610228624,
			"version": 302,
			"versionNonce": 1261913968,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					372.7047146401985,
					31.0173697270468
				],
				[
					799.0901571546733,
					-36.80727874276272
				],
				[
					870.1524282169439,
					-248.88337468982672
				]
			],
			"lastCommittedPoint": [
				769.2307692307693,
				-56.41025641025658
			],
			"startBinding": {
				"elementId": "hrRna-N7mLv1OrkPTEchD",
				"focus": 1.0201268309623728,
				"gap": 25.331152093593346
			},
			"endBinding": {
				"elementId": "a5iPDV05",
				"focus": 0.03748470393822174,
				"gap": 9.739541855394918
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "F2d6OKcSHXmFjdHpeQt3e",
			"type": "arrow",
			"x": 560.0749662972493,
			"y": 1082.2641913728196,
			"width": 1066.3577032900353,
			"height": 388.4145162398089,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 905463184,
			"version": 723,
			"versionNonce": 259416976,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180822690,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					132.47945985661238,
					-229.59024509627432
				],
				[
					1026.2472316759354,
					-212.35099115447292
				],
				[
					1066.3577032900353,
					158.8242711435346
				]
			],
			"lastCommittedPoint": [
				661.9047619047619,
				-290.4761904761905
			],
			"startBinding": {
				"elementId": "za4I4aPx",
				"focus": -0.16410094079240642,
				"gap": 19.522816327672672
			},
			"endBinding": {
				"elementId": "uNIBiWYh",
				"focus": -0.4497564433898899,
				"gap": 8.901204574781787
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "uNIBiWYh",
			"type": "text",
			"x": 1521.9798708726048,
			"y": 1249.989667091136,
			"width": 393.1217041015625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 460728720,
			"version": 147,
			"versionNonce": 1438439792,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "F2d6OKcSHXmFjdHpeQt3e",
					"type": "arrow"
				}
			],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"text": "Graph neural network model ",
			"rawText": "Graph neural network model ",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph neural network model ",
			"lineHeight": 1.25
		},
		{
			"id": "5bOXK8ml",
			"type": "text",
			"x": 1227.7030381552029,
			"y": 1292.0052326342327,
			"width": 957.0389404296875,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1916065648,
			"version": 283,
			"versionNonce": 338408848,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"text": "the current model takes a graph as input and returns an output for each node\nSimilar to Weisfeiler-Lehman, nodes are updated using a message function (for undirected graphs\nbut it can be modified to contain directional information in connections)",
			"rawText": "the current model takes a graph as input and returns an output for each node\nSimilar to Weisfeiler-Lehman, nodes are updated using a message function (for undirected graphs\nbut it can be modified to contain directional information in connections)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the current model takes a graph as input and returns an output for each node\nSimilar to Weisfeiler-Lehman, nodes are updated using a message function (for undirected graphs\nbut it can be modified to contain directional information in connections)",
			"lineHeight": 1.25
		},
		{
			"id": "J6-yzuE2opah8TUA16eHP",
			"type": "image",
			"x": 1389.8960498359947,
			"y": 1375.3752824603953,
			"width": 364.25,
			"height": 58.922794117647065,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"oJS1MuLpLcVbfovcjtCLs"
			],
			"frameId": null,
			"roundness": null,
			"seed": 958173040,
			"version": 107,
			"versionNonce": 1572875120,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9242be0c8d76f13cf6e103a2ebfbae75b1a01deb",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ZOXxp9bMUjC61Wqq6pQJZ",
			"type": "image",
			"x": 1746.7710498359943,
			"y": 1381.4128746880083,
			"width": 309.8750000000002,
			"height": 72.67686855670108,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [
				"oJS1MuLpLcVbfovcjtCLs"
			],
			"frameId": null,
			"roundness": null,
			"seed": 1672656272,
			"version": 172,
			"versionNonce": 2118026128,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "7nt1624RzHqVAmmDRXW5z",
					"type": "arrow"
				}
			],
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5cc061cf0bb3ce98a26909ace1da220a9d977496",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "J__fukLkRBdMRKNXm5K_o",
			"type": "line",
			"x": 1512.6460498359943,
			"y": 1432.5480765780426,
			"width": 41.666666666666515,
			"height": 88.54166666666674,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 452088688,
			"version": 100,
			"versionNonce": 1837710704,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-32.29166666666674,
					38.54166666666663
				],
				[
					-41.666666666666515,
					88.54166666666674
				]
			],
			"lastCommittedPoint": [
				-41.666666666666515,
				88.54166666666674
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "wC7npHuZ",
			"type": "text",
			"x": 1410.7000343181826,
			"y": 1524.6431464908314,
			"width": 98.33619689941406,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1076577680,
			"version": 115,
			"versionNonce": 2026344848,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018569,
			"link": null,
			"locked": false,
			"text": "label of\ncurrent node\nn",
			"rawText": "label of\ncurrent node\nn",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "label of\ncurrent node\nn",
			"lineHeight": 1.25
		},
		{
			"id": "3MeSdetuN_sgjVzpb3BIT",
			"type": "line",
			"x": 1558.4793831693278,
			"y": 1446.0897432447093,
			"width": 30.208333333333485,
			"height": 119.79166666666652,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1370913168,
			"version": 83,
			"versionNonce": 106958704,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					28.125,
					45.83333333333326
				],
				[
					-2.083333333333485,
					119.79166666666652
				]
			],
			"lastCommittedPoint": [
				-2.083333333333485,
				119.79166666666652
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "zkGKrPTi",
			"type": "text",
			"x": 1480.4799273994709,
			"y": 1582.339743244709,
			"width": 126.83224487304688,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1603602288,
			"version": 134,
			"versionNonce": 452910992,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"text": "labels of the\nedges connected\nto n",
			"rawText": "labels of the\nedges connected\nto n",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "labels of the\nedges connected\nto n",
			"lineHeight": 1.25
		},
		{
			"id": "mD_O-mGHxaFgue3FBN0kl",
			"type": "line",
			"x": 1625.1460498359943,
			"y": 1432.5480765780426,
			"width": 35.41666666666674,
			"height": 79.16666666666674,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1829824400,
			"version": 108,
			"versionNonce": 1082958192,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					35.41666666666674,
					48.95833333333326
				],
				[
					28.125,
					79.16666666666674
				]
			],
			"lastCommittedPoint": [
				28.125,
				79.16666666666674
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "pn5z975D",
			"type": "text",
			"x": 1590.0709308174396,
			"y": 1518.7980765780426,
			"width": 126.40023803710938,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1534950288,
			"version": 109,
			"versionNonce": 1427926416,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"text": "states of\nconnected nodes",
			"rawText": "states of\nconnected nodes",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "states of\nconnected nodes",
			"lineHeight": 1.25
		},
		{
			"id": "CgAORqExMcpBOa4ZCH3lF",
			"type": "line",
			"x": 1711.6043831693278,
			"y": 1444.006409911376,
			"width": 36.45833333333303,
			"height": 153.1249999999999,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1354882960,
			"version": 110,
			"versionNonce": 1800860528,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					36.45833333333303,
					92.70833333333337
				],
				[
					11.45833333333303,
					153.1249999999999
				]
			],
			"lastCommittedPoint": [
				11.45833333333303,
				153.1249999999999
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "ObveooVU",
			"type": "text",
			"x": 1578.7264127917233,
			"y": 1602.1314099113758,
			"width": 288.672607421875,
			"height": 100,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1951977360,
			"version": 154,
			"versionNonce": 1347959696,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"text": "labels of\nconnected nodes\none may wish to remove these labels\nsince they include information\nthat is implicitly contained in ",
			"rawText": "labels of\nconnected nodes\none may wish to remove these labels\nsince they include information\nthat is implicitly contained in ",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "labels of\nconnected nodes\none may wish to remove these labels\nsince they include information\nthat is implicitly contained in ",
			"lineHeight": 1.25
		},
		{
			"id": "0vhEdU9S_1rf6btI0sCvV",
			"type": "line",
			"x": 1392.8543831693278,
			"y": 1423.1730765780426,
			"width": 60.936873193527845,
			"height": 147.91666666666674,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 787834256,
			"version": 197,
			"versionNonce": 755434864,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-53.99270732973787,
					77.72006991278909
				],
				[
					-60.936873193527845,
					147.91666666666674
				]
			],
			"lastCommittedPoint": [
				-31.25,
				147.91666666666674
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "MH1z6zDj",
			"type": "text",
			"x": 1205.4922559239008,
			"y": 1579.886271691551,
			"width": 255.74453735351562,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1569385360,
			"version": 221,
			"versionNonce": 1323977104,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"text": "state of current node\na representation of the concept\ndenoted by n and can be\nused to produce an output On",
			"rawText": "state of current node\na representation of the concept\ndenoted by n and can be\nused to produce an output On",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "state of current node\na representation of the concept\ndenoted by n and can be\nused to produce an output On",
			"lineHeight": 1.25
		},
		{
			"id": "TbG3Jw9z",
			"type": "text",
			"x": 1349.4505056366847,
			"y": 1717.2249975268403,
			"width": 786.55908203125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1104818032,
			"version": 177,
			"versionNonce": 585422704,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "y7N5qxzyiDw90MZx4WhHn",
					"type": "arrow"
				}
			],
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"text": "The states of the points are updated recurrently until we reach a fixed point",
			"rawText": "The states of the points are updated recurrently until we reach a fixed point",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The states of the points are updated recurrently until we reach a fixed point",
			"lineHeight": 1.25
		},
		{
			"id": "MTLvrpBeZmIp0opqOtDui",
			"type": "image",
			"x": 1586.7976455806752,
			"y": 1742.2158230010673,
			"width": 281.08510638297867,
			"height": 58.07543520309477,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 978920848,
			"version": 196,
			"versionNonce": 967974768,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180033968,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7d1b3ae93d00105b127c4540af27952e8a866386",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "y7N5qxzyiDw90MZx4WhHn",
			"type": "arrow",
			"x": 2109.386613069202,
			"y": 1705.5228698672656,
			"width": 256.1809997825126,
			"height": 97.24341031049948,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1633386352,
			"version": 354,
			"versionNonce": 20474224,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					98.27273463913161,
					-97.24341031049948
				],
				[
					256.1809997825126,
					-90.83650218333923
				]
			],
			"lastCommittedPoint": [
				202.127659574468,
				-37.23404255319133
			],
			"startBinding": {
				"elementId": "TbG3Jw9z",
				"focus": 0.8430358839266505,
				"gap": 11.702127659574671
			},
			"endBinding": {
				"elementId": "iA7stX5H",
				"focus": 0.364866175366237,
				"gap": 19.174832573603908
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "XlVbPUAW",
			"type": "text",
			"x": 2450.203203715712,
			"y": 1469.834287707339,
			"width": 534.159423828125,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2089385360,
			"version": 242,
			"versionNonce": 468788624,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "y7N5qxzyiDw90MZx4WhHn",
					"type": "arrow"
				}
			],
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"text": "We can guarantee the convergences to a unique fixed\npoint according to Banach fixed-point theorem",
			"rawText": "We can guarantee the convergences to a unique fixed\npoint according to Banach fixed-point theorem",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can guarantee the convergences to a unique fixed\npoint according to Banach fixed-point theorem",
			"lineHeight": 1.25
		},
		{
			"id": "iA7stX5H",
			"type": "text",
			"x": 2384.7424454253187,
			"y": 1523.025777069041,
			"width": 675.71923828125,
			"height": 350,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1386411408,
			"version": 607,
			"versionNonce": 860470128,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "y7N5qxzyiDw90MZx4WhHn",
					"type": "arrow"
				}
			],
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"text": "Let ( X , d ) be a metric space. Then a map T : X → X is called a\ncontraction mapping on X if there exists q ∈ [ 0 , 1 ) such that\n\n\nfor all x,y in X\n\nin our case we can achieve this by adding Lipschitz regularization\nwhich is basically a gradient penalty to the loss function\n\n\n\nLipschitz regularization enforces Lipschitz continuity which ensures\na certain smoothness (in the sense that there are no sudden\njumps and step function like movement) to the function applied.",
			"rawText": "Let ( X , d ) be a metric space. Then a map T : X → X is called a\ncontraction mapping on X if there exists q ∈ [ 0 , 1 ) such that\n\n\nfor all x,y in X\n\nin our case we can achieve this by adding Lipschitz regularization\nwhich is basically a gradient penalty to the loss function\n\n\n\nLipschitz regularization enforces Lipschitz continuity which ensures\na certain smoothness (in the sense that there are no sudden\njumps and step function like movement) to the function applied.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Let ( X , d ) be a metric space. Then a map T : X → X is called a\ncontraction mapping on X if there exists q ∈ [ 0 , 1 ) such that\n\n\nfor all x,y in X\n\nin our case we can achieve this by adding Lipschitz regularization\nwhich is basically a gradient penalty to the loss function\n\n\n\nLipschitz regularization enforces Lipschitz continuity which ensures\na certain smoothness (in the sense that there are no sudden\njumps and step function like movement) to the function applied.",
			"lineHeight": 1.25
		},
		{
			"id": "K1Fdsygt6dMKBJJxofurL",
			"type": "image",
			"x": 2590.293553927646,
			"y": 1577.0576919626578,
			"width": 271,
			"height": 43,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 378676592,
			"version": 150,
			"versionNonce": 1272312720,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "57fa9808d0bf03c8fe0567d2ede2a0a2dd91b1e3",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "wrNNxOKuwQzauutseQM2e",
			"type": "image",
			"x": 2687.36905171488,
			"y": 1723.0257771328706,
			"width": 76.8490048043928,
			"height": 61.0851063829789,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1481562000,
			"version": 155,
			"versionNonce": 2069941616,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fb7bdf92e7ac15d798e0cccb1ea29a3a5a56a62e",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "hAd9VaEaOhLr-C3zqw4W1",
			"type": "line",
			"x": 1470.8864457226045,
			"y": 1388.3303932334284,
			"width": 164.92707329737777,
			"height": 28.58735937154529,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 933355408,
			"version": 71,
			"versionNonce": 494555024,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-105.55332691032163,
					-4.398055287929992
				],
				[
					-164.92707329737777,
					24.189304083615298
				]
			],
			"lastCommittedPoint": [
				-164.92707329737777,
				24.189304083615298
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "x1ZcmkYi",
			"type": "text",
			"x": 1129.247816449743,
			"y": 1413.226017631271,
			"width": 223.68048095703125,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 220836208,
			"version": 79,
			"versionNonce": 1237332336,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"text": "local transition\nfunction that expresses the\ndependence of a node on\nits neighborhood",
			"rawText": "local transition\nfunction that expresses the\ndependence of a node on\nits neighborhood",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "local transition\nfunction that expresses the\ndependence of a node on\nits neighborhood",
			"lineHeight": 1.25
		},
		{
			"id": "E294CAhRgUBq_cvDbqmjC",
			"type": "image",
			"x": 1230.3477041528072,
			"y": 1659.5996113467256,
			"width": 204,
			"height": 49,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1842919280,
			"version": 21,
			"versionNonce": 1453972880,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8e9ad7eae0f56baf082cbca693ece6f633196320",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "6MinuVx77fPxcggb6hkfb",
			"type": "line",
			"x": 1301.5613171372968,
			"y": 1702.7913463204284,
			"width": 94.55818869049654,
			"height": 35.18444230344062,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1474389872,
			"version": 66,
			"versionNonce": 664306544,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018570,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-21.990276439650415,
					30.7863870155104
				],
				[
					-94.55818869049654,
					35.18444230344062
				]
			],
			"lastCommittedPoint": [
				-94.55818869049654,
				35.18444230344062
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "viEex0cJ",
			"type": "text",
			"x": 1013.5762528946925,
			"y": 1704.9903739643933,
			"width": 199.9364013671875,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1868147088,
			"version": 28,
			"versionNonce": 982353776,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180018571,
			"link": null,
			"locked": false,
			"text": "the local output function\nthat describes how\nthe output is produced",
			"rawText": "the local output function\nthat describes how\nthe output is produced",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the local output function\nthat describes how\nthe output is produced",
			"lineHeight": 1.25
		},
		{
			"id": "7nt1624RzHqVAmmDRXW5z",
			"type": "arrow",
			"x": 1848.019686662608,
			"y": 1459.798791662292,
			"width": 94.89760385124964,
			"height": 127.54360334997205,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 869605264,
			"version": 126,
			"versionNonce": 612689808,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180018571,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					19.791248795685306,
					70.36888460688124
				],
				[
					94.89760385124964,
					127.54360334997205
				]
			],
			"lastCommittedPoint": [
				71.46839842886357,
				87.96110575860143
			],
			"startBinding": {
				"elementId": "ZOXxp9bMUjC61Wqq6pQJZ",
				"focus": 0.3966798022393606,
				"gap": 5.709048417582494
			},
			"endBinding": {
				"elementId": "jJwpklmF",
				"focus": 0.07767362830314965,
				"gap": 6.597082931895102
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "jJwpklmF",
			"type": "text",
			"x": 1916.2499724712443,
			"y": 1593.939477944159,
			"width": 178.00038146972656,
			"height": 100,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 580465520,
			"version": 146,
			"versionNonce": 1352758672,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "7nt1624RzHqVAmmDRXW5z",
					"type": "arrow"
				}
			],
			"updated": 1715180018571,
			"link": null,
			"locked": false,
			"text": "This rewrite of the\nfunction simplifies\nour equation but only\nworks for nonpositional\ngraphs",
			"rawText": "This rewrite of the\nfunction simplifies\nour equation but only\nworks for nonpositional\ngraphs",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This rewrite of the\nfunction simplifies\nour equation but only\nworks for nonpositional\ngraphs",
			"lineHeight": 1.25
		},
		{
			"id": "J-HIdPI_gWsw16twS8N9x",
			"type": "arrow",
			"x": 1875.5075322121706,
			"y": 1436.7090014006592,
			"width": 128.6431171719546,
			"height": 53.87617727714337,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1592338320,
			"version": 89,
			"versionNonce": 478571376,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180018571,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					52.776663455160815,
					41.781525235335494
				],
				[
					128.6431171719546,
					53.87617727714337
				]
			],
			"lastCommittedPoint": [
				128.6431171719546,
				53.87617727714337
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "XLD2YT7c",
				"focus": -0.6995659056668572,
				"gap": 1
			},
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "XLD2YT7c",
			"type": "text",
			"x": 2004.7425226345708,
			"y": 1465.2963607722045,
			"width": 359.456787109375,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 627167600,
			"version": 65,
			"versionNonce": 2038922608,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "J-HIdPI_gWsw16twS8N9x",
					"type": "arrow"
				}
			],
			"updated": 1715180018571,
			"link": null,
			"locked": false,
			"text": " parametric function that is not affected by\nthe positions and the number of the children",
			"rawText": " parametric function that is not affected by\nthe positions and the number of the children",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " parametric function that is not affected by\nthe positions and the number of the children",
			"lineHeight": 1.25
		},
		{
			"id": "esmnm0cR",
			"type": "text",
			"x": 1384.0832334988067,
			"y": 1788.5534244350645,
			"width": 637.6012573242188,
			"height": 100,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 301654384,
			"version": 99,
			"versionNonce": 2044272016,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180190164,
			"link": null,
			"locked": false,
			"text": "can be interpreted as the representation of a network consisting of units, which\ncompute f and g. Such a network will be called an encoding\nnetwork ach unit stores the current state\nof node Xn(t), and, when activated, it calculates the state Xn(t+1)\nThe output of node n is produced by another unit, which implements g",
			"rawText": "can be interpreted as the representation of a network consisting of units, which\ncompute f and g. Such a network will be called an encoding\nnetwork ach unit stores the current state\nof node Xn(t), and, when activated, it calculates the state Xn(t+1)\nThe output of node n is produced by another unit, which implements g",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "can be interpreted as the representation of a network consisting of units, which\ncompute f and g. Such a network will be called an encoding\nnetwork ach unit stores the current state\nof node Xn(t), and, when activated, it calculates the state Xn(t+1)\nThe output of node n is produced by another unit, which implements g",
			"lineHeight": 1.25
		},
		{
			"id": "yZaCO_QMpuRIff7GE1mwH",
			"type": "image",
			"x": 1509.9371890712373,
			"y": 1895.7528840396608,
			"width": 390.2914014672869,
			"height": 231.42907222683343,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1956946832,
			"version": 105,
			"versionNonce": 669257616,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715180258902,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f219c77ee819d1bda72fe5c0819685c62ea680e0",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "2uYx7I3Z",
			"type": "text",
			"x": 1460.9332901002185,
			"y": 2120.1714342442338,
			"width": 504.625,
			"height": 120,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1304097648,
			"version": 152,
			"versionNonce": 297629040,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180312657,
			"link": null,
			"locked": false,
			"text": "this turns out to be a recurrent neural\nnetwork where the connections between the neurons can be di-\nvided into internal and external connections. The internal con-\nnectivity is determined by the neural network architecture used\nto implement the unit. The external connectivity depends on the\nedges of the processed graph.",
			"rawText": "this turns out to be a recurrent neural\nnetwork where the connections between the neurons can be di-\nvided into internal and external connections. The internal con-\nnectivity is determined by the neural network architecture used\nto implement the unit. The external connectivity depends on the\nedges of the processed graph.",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "this turns out to be a recurrent neural\nnetwork where the connections between the neurons can be di-\nvided into internal and external connections. The internal con-\nnectivity is determined by the neural network architecture used\nto implement the unit. The external connectivity depends on the\nedges of the processed graph.",
			"lineHeight": 1.25
		},
		{
			"id": "s7i3BrHhjhU3_TXaAOCZe",
			"type": "line",
			"x": 1345.0668524852983,
			"y": 2247.0518784288843,
			"width": 727.9203331354802,
			"height": 1.5687938214132373,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1807226736,
			"version": 100,
			"versionNonce": 1351824240,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180319133,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					727.9203331354802,
					-1.5687938214132373
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "0tQn4ycP",
			"type": "text",
			"x": 1554.0743670754996,
			"y": 2256.8086104644235,
			"width": 309.9053039550781,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1623349136,
			"version": 84,
			"versionNonce": 1587257712,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180374059,
			"link": null,
			"locked": false,
			"text": "The Learning algorithm",
			"rawText": "The Learning algorithm",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The Learning algorithm",
			"lineHeight": 1.25
		},
		{
			"id": "5bvCsKZ2",
			"type": "text",
			"x": 1318.3388994054562,
			"y": 2356.2782490346804,
			"width": 804.9391479492188,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 957041040,
			"version": 104,
			"versionNonce": 2032730480,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715181103255,
			"link": null,
			"locked": false,
			"text": "Learning in GNNs consists of estimating the parameter w\nsuch that phi_w approximates the data in the learning data set\nThe learning task can be posed as the minimization of a quadratic cost function",
			"rawText": "Learning in GNNs consists of estimating the parameter w\nsuch that phi_w approximates the data in the learning data set\nThe learning task can be posed as the minimization of a quadratic cost function",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Learning in GNNs consists of estimating the parameter w\nsuch that phi_w approximates the data in the learning data set\nThe learning task can be posed as the minimization of a quadratic cost function",
			"lineHeight": 1.25
		},
		{
			"id": "BdCLAdG4NW0trFrMb8_HM",
			"type": "image",
			"x": 1289.3057920595468,
			"y": 2303.3438755213224,
			"width": 419,
			"height": 37,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 952740240,
			"version": 87,
			"versionNonce": 2127340400,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180455385,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "97d50a86b9cfe347e9ce2c3a4aa8972ed60da4fb",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "NvvMUwHuGzXwWzeyf3WxV",
			"type": "image",
			"x": 1708.1600957014894,
			"y": 2299.953204635923,
			"width": 451,
			"height": 40,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 807334768,
			"version": 86,
			"versionNonce": 642168176,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180455385,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "61d2b986b39655d7e0adc1c78a5cec0e2e6970ca",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "6NBGmhBxGyNnlGZy5DmQh",
			"type": "line",
			"x": 2126.5085260122637,
			"y": 2311.4451856516243,
			"width": 53.8841202338931,
			"height": 34.97741137989533,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 362566032,
			"version": 37,
			"versionNonce": 1929676144,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180480530,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					26.469392395596515,
					-31.196069609095957
				],
				[
					53.8841202338931,
					-34.97741137989533
				]
			],
			"lastCommittedPoint": [
				53.8841202338931,
				-34.97741137989533
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "WZdMl8Rw",
			"type": "text",
			"x": 2152.8766047368854,
			"y": 2244.5996920064335,
			"width": 162.80032348632812,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1783832432,
			"version": 86,
			"versionNonce": 1813523856,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180495766,
			"link": null,
			"locked": false,
			"text": "number of supervised\nnodes in Gi",
			"rawText": "number of supervised\nnodes in Gi",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "number of supervised\nnodes in Gi",
			"lineHeight": 1.25
		},
		{
			"id": "zhHq1TFa",
			"type": "text",
			"x": 774.7180137121543,
			"y": 577.3471479182087,
			"width": 142.83982849121094,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 262035344,
			"version": 34,
			"versionNonce": 1919058320,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180594691,
			"link": null,
			"locked": false,
			"text": "Graph focused\napplications",
			"rawText": "Graph focused\napplications",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph focused\napplications",
			"lineHeight": 1.25
		},
		{
			"id": "9GcQUcIM",
			"type": "text",
			"x": 592.8490449655329,
			"y": 628.71657602186,
			"width": 512.4490966796875,
			"height": 180,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1244194672,
			"version": 81,
			"versionNonce": 985561488,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180672245,
			"link": null,
			"locked": false,
			"text": "graph-focused applications, the function Tau is independent\nof the node n and implements a classifier or a\nregressor on a graph structured data set.\nFor example, a chemical compound can be\nmodeled by a graph , the nodes of which\nstand for atoms (or chemical groups) and the edges of which\nrepresent chemical bonds linking together some\nof the atoms. The mapping may be used to estimate the\nprobability that the chemical compound causes a certain disease",
			"rawText": "graph-focused applications, the function Tau is independent\nof the node n and implements a classifier or a\nregressor on a graph structured data set.\nFor example, a chemical compound can be\nmodeled by a graph , the nodes of which\nstand for atoms (or chemical groups) and the edges of which\nrepresent chemical bonds linking together some\nof the atoms. The mapping may be used to estimate the\nprobability that the chemical compound causes a certain disease",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "graph-focused applications, the function Tau is independent\nof the node n and implements a classifier or a\nregressor on a graph structured data set.\nFor example, a chemical compound can be\nmodeled by a graph , the nodes of which\nstand for atoms (or chemical groups) and the edges of which\nrepresent chemical bonds linking together some\nof the atoms. The mapping may be used to estimate the\nprobability that the chemical compound causes a certain disease",
			"lineHeight": 1.25
		},
		{
			"id": "Yr3BIzjb",
			"type": "text",
			"x": 1155.2136661336654,
			"y": 702.5658251460114,
			"width": 50.364013671875,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 869802896,
			"version": 7,
			"versionNonce": 116995952,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180713821,
			"link": null,
			"locked": false,
			"text": "V.S",
			"rawText": "V.S",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V.S",
			"lineHeight": 1.25
		},
		{
			"id": "Pt0dwnRG",
			"type": "text",
			"x": 1448.2076375865931,
			"y": 574.9294527142472,
			"width": 131.65985107421875,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 464953744,
			"version": 190,
			"versionNonce": 2112362384,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180809503,
			"link": null,
			"locked": false,
			"text": "Node focused\napplications",
			"rawText": "Node focused\napplications",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Node focused\napplications",
			"lineHeight": 1.25
		},
		{
			"id": "sSXglXt1",
			"type": "text",
			"x": 1255.49320412521,
			"y": 628.7165760000966,
			"width": 545.921142578125,
			"height": 160,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 516370288,
			"version": 172,
			"versionNonce": 523686800,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715180804970,
			"link": null,
			"locked": false,
			"text": "In node-focused applications, Tau depends on the node n, so\nthat the classification (or the regression) depends on the properties\nof each node. Object detection is an example of this class of\napplications. It consists of finding whether an image contains a\ngiven object, and, if so, localizing its position. This problem\ncan be solved by a function Tau, which classifies the nodes of the\nregion adjacency graph according to whether the corresponding\nregion belongs to the object",
			"rawText": "In node-focused applications, Tau depends on the node n, so\nthat the classification (or the regression) depends on the properties\nof each node. Object detection is an example of this class of\napplications. It consists of finding whether an image contains a\ngiven object, and, if so, localizing its position. This problem\ncan be solved by a function Tau, which classifies the nodes of the\nregion adjacency graph according to whether the corresponding\nregion belongs to the object",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In node-focused applications, Tau depends on the node n, so\nthat the classification (or the regression) depends on the properties\nof each node. Object detection is an example of this class of\napplications. It consists of finding whether an image contains a\ngiven object, and, if so, localizing its position. This problem\ncan be solved by a function Tau, which classifies the nodes of the\nregion adjacency graph according to whether the corresponding\nregion belongs to the object",
			"lineHeight": 1.25
		},
		{
			"id": "SnAbZdV19zLH8tLN06-uz",
			"type": "image",
			"x": 1535.3897031523293,
			"y": 2433.905942108997,
			"width": 376,
			"height": 77,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1913349488,
			"version": 58,
			"versionNonce": 1292912528,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715181113441,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6d288500a8224f297c23b8fde715b63415346734",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "kNBavbKw",
			"type": "text",
			"x": 1886.6305294926924,
			"y": 2466.012729271604,
			"width": 424.7208557128906,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 997519216,
			"version": 153,
			"versionNonce": 1757512560,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715181155630,
			"link": null,
			"locked": false,
			"text": "+ some regularization term depending on the objective",
			"rawText": "+ some regularization term depending on the objective",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "+ some regularization term depending on the objective",
			"lineHeight": 1.25
		},
		{
			"id": "6rmrrMn2",
			"type": "text",
			"x": 1231.849584817321,
			"y": 2529.0431608548765,
			"width": 965.4989013671875,
			"height": 175,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1374484848,
			"version": 355,
			"versionNonce": 268675984,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715181336084,
			"link": null,
			"locked": false,
			"text": "The gradient descent algorithm goes as follows:\n\na) The states xn are iteratively updated by f until a time T where they approach a fixed point\n\nb) The gradient above is computed w.r.t w (which influence both f and g)\n\nc) The weights w are updated according to the gradient computed",
			"rawText": "The gradient descent algorithm goes as follows:\n\na) The states xn are iteratively updated by f until a time T where they approach a fixed point\n\nb) The gradient above is computed w.r.t w (which influence both f and g)\n\nc) The weights w are updated according to the gradient computed",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The gradient descent algorithm goes as follows:\n\na) The states xn are iteratively updated by f until a time T where they approach a fixed point\n\nb) The gradient above is computed w.r.t w (which influence both f and g)\n\nc) The weights w are updated according to the gradient computed",
			"lineHeight": 1.25
		},
		{
			"id": "I7ZedLwY",
			"type": "text",
			"x": 1187.7304258884283,
			"y": 2736.925123256112,
			"width": 1052.138916015625,
			"height": 125,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1641136016,
			"version": 212,
			"versionNonce": 612555152,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715181655857,
			"link": null,
			"locked": false,
			"text": "since x(t) has reached a stable point before the gradient computation it allows us to\nonly yhe need to store the final product for backpropagation as opposed to x at\nevery iteration through time.\nthis is good because backpropagation through time (RNN) requires to store the states of\nevery instance of the units. When the graphs and time are large, the memory required may be considerable",
			"rawText": "since x(t) has reached a stable point before the gradient computation it allows us to\nonly yhe need to store the final product for backpropagation as opposed to x at\nevery iteration through time.\nthis is good because backpropagation through time (RNN) requires to store the states of\nevery instance of the units. When the graphs and time are large, the memory required may be considerable",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "since x(t) has reached a stable point before the gradient computation it allows us to\nonly yhe need to store the final product for backpropagation as opposed to x at\nevery iteration through time.\nthis is good because backpropagation through time (RNN) requires to store the states of\nevery instance of the units. When the graphs and time are large, the memory required may be considerable",
			"lineHeight": 1.25
		},
		{
			"id": "86RToLamqja83ypN8_9I7",
			"type": "arrow",
			"x": 1334.5862530048917,
			"y": 1859.0319603280404,
			"width": 732.4324324324323,
			"height": 214.86486486486456,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1654839664,
			"version": 254,
			"versionNonce": 179834736,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715181854536,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-636.4864864864863,
					6.756756756756658
				],
				[
					-732.4324324324323,
					214.86486486486456
				]
			],
			"lastCommittedPoint": [
				-732.4324324324323,
				214.86486486486456
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "y9Gr52Rf",
			"type": "text",
			"x": 266.9917367662408,
			"y": 2095.923852219932,
			"width": 664.9187622070312,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1885275504,
			"version": 6,
			"versionNonce": 1813578128,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715181872901,
			"link": null,
			"locked": false,
			"text": "Transition and Output Function Implementations",
			"rawText": "Transition and Output Function Implementations",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Transition and Output Function Implementations",
			"lineHeight": 1.25
		},
		{
			"id": "7PJHbWFT",
			"type": "text",
			"x": 207.39527152658752,
			"y": 2143.7616900577696,
			"width": 751.6792602539062,
			"height": 125,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1507830672,
			"version": 78,
			"versionNonce": 1268400496,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "wrKmClQJQNAwclTEjQwrq",
					"type": "arrow"
				},
				{
					"id": "WdRRGtUeOtoqsWy2IKUjJ",
					"type": "arrow"
				}
			],
			"updated": 1715183226342,
			"link": null,
			"locked": false,
			"text": "The local transition function f plays a crucial role n the proposed\nmodel, since its implementation determines the number and the\nexistence of the solutions\nThe assumption behind GNN is that the design of f is such\nthat the global transition function is a contraction map w.r.t. the state . ",
			"rawText": "The local transition function f plays a crucial role n the proposed\nmodel, since its implementation determines the number and the\nexistence of the solutions\nThe assumption behind GNN is that the design of f is such\nthat the global transition function is a contraction map w.r.t. the state . ",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The local transition function f plays a crucial role n the proposed\nmodel, since its implementation determines the number and the\nexistence of the solutions\nThe assumption behind GNN is that the design of f is such\nthat the global transition function is a contraction map w.r.t. the state . ",
			"lineHeight": 1.25
		},
		{
			"id": "wrKmClQJQNAwclTEjQwrq",
			"type": "arrow",
			"x": 554.9333043825854,
			"y": 2276.5995278956066,
			"width": 264.8648648648648,
			"height": 209.45945945946005,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1073165200,
			"version": 269,
			"versionNonce": 82872176,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715182080845,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					32.432432432432506,
					151.3513513513517
				],
				[
					244.59459459459447,
					136.48648648648623
				],
				[
					264.8648648648648,
					209.45945945946005
				]
			],
			"lastCommittedPoint": [
				-383.78378378378375,
				227.02702702702754
			],
			"startBinding": {
				"elementId": "7PJHbWFT",
				"focus": 0.11143466311763085,
				"gap": 7.837837837837014
			},
			"endBinding": {
				"elementId": "NKRnA5Xf",
				"focus": 0.03844135208969649,
				"gap": 5.405405405405418
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "NKRnA5Xf",
			"type": "text",
			"x": 640.6466505911987,
			"y": 2486.464392760472,
			"width": 358.14947509765625,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 72057744,
			"version": 33,
			"versionNonce": 1398569360,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "wrKmClQJQNAwclTEjQwrq",
					"type": "arrow"
				}
			],
			"updated": 1715182153388,
			"link": null,
			"locked": false,
			"text": "Linear (nonpositional) GNN",
			"rawText": "Linear (nonpositional) GNN",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Linear (nonpositional) GNN",
			"lineHeight": 1.25
		},
		{
			"id": "TviuXPUP1Rm8Xdej84sI2",
			"type": "image",
			"x": 681.8929058115449,
			"y": 2527.2588249510254,
			"width": 295.61538461538487,
			"height": 35.21180481568296,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 725242256,
			"version": 107,
			"versionNonce": 1204983152,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182111978,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "eaf445af9fe9c512962fa97b580c7600a20255df",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Fy5Y450hprqjzYhiH0xZL",
			"type": "line",
			"x": 880.8052359156561,
			"y": 2563.1201541229375,
			"width": 18.269492384090654,
			"height": 32.47909757171692,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 422474128,
			"version": 43,
			"versionNonce": 72408944,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182150829,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					18.269492384090654,
					32.47909757171692
				]
			],
			"lastCommittedPoint": [
				18.269492384090654,
				32.47909757171692
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "k9w1dn6qQQsSMBM4yWgOf",
			"type": "line",
			"x": 962.6796277110257,
			"y": 2561.0902105247055,
			"width": 43.30546342895582,
			"height": 31.802449705639447,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1319094128,
			"version": 41,
			"versionNonce": 1296240528,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182150829,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-43.30546342895582,
					31.802449705639447
				]
			],
			"lastCommittedPoint": [
				-43.30546342895582,
				31.802449705639447
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "bm3o2roZ",
			"type": "text",
			"x": 786.0998171088177,
			"y": 2604.6591388911193,
			"width": 270.60858154296875,
			"height": 80,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1279672720,
			"version": 86,
			"versionNonce": 1688949648,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182182506,
			"link": null,
			"locked": false,
			"text": "output of two feed forward\nneural networks whose parameters\ncorrespond to the\nparameters of the GNN",
			"rawText": "output of two feed forward\nneural networks whose parameters\ncorrespond to the\nparameters of the GNN",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "output of two feed forward\nneural networks whose parameters\ncorrespond to the\nparameters of the GNN",
			"lineHeight": 1.25
		},
		{
			"id": "1qhuVwlG",
			"type": "text",
			"x": 583.2349018776072,
			"y": 2692.0767076511347,
			"width": 534.8394775390625,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2063285648,
			"version": 209,
			"versionNonce": 1969931664,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182299545,
			"link": null,
			"locked": false,
			"text": "The transition network is basically a FFNN that\nhas to generate A and the forcing network is a FFNN\nthat has to generate b",
			"rawText": "The transition network is basically a FFNN that\nhas to generate A and the forcing network is a FFNN\nthat has to generate b",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The transition network is basically a FFNN that\nhas to generate A and the forcing network is a FFNN\nthat has to generate b",
			"lineHeight": 1.25
		},
		{
			"id": "r6oLsQ2x",
			"type": "text",
			"x": 624.9610108363875,
			"y": 2774.689915466711,
			"width": 452.75946044921875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 970452880,
			"version": 74,
			"versionNonce": 444648816,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182340617,
			"link": null,
			"locked": false,
			"text": "We then define such outputs as the following:",
			"rawText": "We then define such outputs as the following:",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We then define such outputs as the following:",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 135,
			"versionNonce": 1188596080,
			"isDeleted": false,
			"id": "LtdVV0vc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 774.5419896553653,
			"y": 2807.8782451638813,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 125.26841318616268,
			"height": 25.970280782497138,
			"seed": 80555,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715182382635,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "394cdd721d0265ce87cc753cb87a3fcdb020c3e9",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "b_6YKscOVrqhqfon61Zpu",
			"type": "image",
			"x": 658.9819699160555,
			"y": 2854.3933399192683,
			"width": 401.8405912347004,
			"height": 60.789244646506745,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 777015664,
			"version": 103,
			"versionNonce": 1481432976,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182410219,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ede0c8c770ae654819ee337e30c6459c125082a2",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "flkTc5bF3yTzHaIhTaDQI",
			"type": "line",
			"x": 847.9635003623524,
			"y": 2895.595132478184,
			"width": 73.62384723044988,
			"height": 49.30771420020983,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 924386672,
			"version": 45,
			"versionNonce": 269034384,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182456865,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					73.62384723044988,
					49.30771420020983
				]
			],
			"lastCommittedPoint": [
				73.62384723044988,
				49.30771420020983
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "rFgkh6Qp",
			"type": "text",
			"x": 876.7956614742336,
			"y": 2949.902846678393,
			"width": 205.7604522705078,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1309731216,
			"version": 46,
			"versionNonce": 913989488,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182487799,
			"link": null,
			"locked": false,
			"text": "allocates the elements\nof a s^2-dimensional\nvector into as matrix sxs",
			"rawText": "allocates the elements\nof a s^2-dimensional\nvector into as matrix sxs",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "allocates the elements\nof a s^2-dimensional\nvector into as matrix sxs",
			"lineHeight": 1.25
		},
		{
			"id": "eralJfE66CfzrjEPHzM8A",
			"type": "line",
			"x": 758.128897778409,
			"y": 2860.4718292122816,
			"width": 170.21293121168242,
			"height": 31.070614427529563,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1964852080,
			"version": 79,
			"versionNonce": 366911888,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182502766,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-82.40467304692561,
					-31.070614427529563
				],
				[
					-170.21293121168242,
					-14.184410934306925
				]
			],
			"lastCommittedPoint": [
				-170.21293121168242,
				-14.184410934306925
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "LSu6MUrh",
			"type": "text",
			"x": 544.470555789502,
			"y": 2844.2610738587878,
			"width": 31.504074096679688,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1219995536,
			"version": 45,
			"versionNonce": 629986704,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182515904,
			"link": null,
			"locked": false,
			"text": "(0,1)",
			"rawText": "(0,1)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(0,1)",
			"lineHeight": 1.25
		},
		{
			"id": "ME6iqJjQ",
			"type": "text",
			"x": 573.3432681886411,
			"y": 3045.5446194979986,
			"width": 616.7852783203125,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1316224912,
			"version": 54,
			"versionNonce": 458488688,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182671897,
			"link": null,
			"locked": false,
			"text": "This transition function is a contraction map if the entries of A are bounded\nbetween -1 and 1 with tanh for example",
			"rawText": "This transition function is a contraction map if the entries of A are bounded\nbetween -1 and 1 with tanh for example",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This transition function is a contraction map if the entries of A are bounded\nbetween -1 and 1 with tanh for example",
			"lineHeight": 1.25
		},
		{
			"id": "XqabWZm2FHt3iC_xKTH6Z",
			"type": "image",
			"x": 572.9635003623523,
			"y": 3081.649163487277,
			"width": 336.5583878456682,
			"height": 75.87861835065975,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 759160688,
			"version": 146,
			"versionNonce": 711934320,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182766700,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "227f10e792a5ca119d58e7824e74659617c26b96",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "HQlf3TRoTJDWSRh6VlmF6",
			"type": "image",
			"x": 910.3450927773747,
			"y": 3084.8997258094864,
			"width": 289.96197296349936,
			"height": 70.45260788872173,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 86207344,
			"version": 242,
			"versionNonce": 1072010096,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715182766700,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "42154746d86aca9ac56aeac04541bf4492a3cf95",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "l0y3P3cG",
			"type": "text",
			"x": 548.9378493186605,
			"y": 3180.6708551339725,
			"width": 689.4732666015625,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 193405808,
			"version": 117,
			"versionNonce": 465059216,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715183135880,
			"link": null,
			"locked": false,
			"text": "hw is realized by a multilayered FNN. Since three-layered neural\nnetworks are universal approximators, hw can approximate\nany desired function. However, not all the parameters\ncan be used, because it must be ensured that the corresponding\ntransition function is a contraction map which is ensure by the lipdogshit regularization",
			"rawText": "hw is realized by a multilayered FNN. Since three-layered neural\nnetworks are universal approximators, hw can approximate\nany desired function. However, not all the parameters\ncan be used, because it must be ensured that the corresponding\ntransition function is a contraction map which is ensure by the lipdogshit regularization",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "hw is realized by a multilayered FNN. Since three-layered neural\nnetworks are universal approximators, hw can approximate\nany desired function. However, not all the parameters\ncan be used, because it must be ensured that the corresponding\ntransition function is a contraction map which is ensure by the lipdogshit regularization",
			"lineHeight": 1.25
		},
		{
			"id": "ap3nV5-tcazXlJYBoWxKb",
			"type": "image",
			"x": 820.8104033467295,
			"y": 3280.6708547629823,
			"width": 158,
			"height": 72,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1557272976,
			"version": 52,
			"versionNonce": 1938382192,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715183141188,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "10335c3ee4d23c486a70de0c3f8153e08ccd1533",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "WdRRGtUeOtoqsWy2IKUjJ",
			"type": "arrow",
			"x": 555.0575976295677,
			"y": 2277.144292914317,
			"width": 513.3411166204447,
			"height": 249.12142424227432,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 867585424,
			"version": 230,
			"versionNonce": 1497003376,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715183230514,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-64.92255298435043,
					131.35493278228978
				],
				[
					-465.0266585855793,
					152.4925081725437
				],
				[
					-513.3411166204447,
					249.12142424227432
				]
			],
			"lastCommittedPoint": [
				-513.3411166204447,
				249.12142424227432
			],
			"startBinding": {
				"elementId": "7PJHbWFT",
				"focus": -0.016857912607788548,
				"gap": 8.382602856547237
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "NmIxJUKV",
			"type": "text",
			"x": -180.3057686068296,
			"y": 2536.883638919666,
			"width": 398.74969482421875,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 357086608,
			"version": 47,
			"versionNonce": 1689831312,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715183263465,
			"link": null,
			"locked": false,
			"text": "Graph convolutional networks",
			"rawText": "Graph convolutional networks",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph convolutional networks",
			"lineHeight": 1.25
		},
		{
			"id": "yamu5MWP",
			"type": "text",
			"x": -384.6315123151361,
			"y": 2742.6414710591275,
			"width": 825.5191040039062,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 788110704,
			"version": 189,
			"versionNonce": 1658066320,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715183401000,
			"link": null,
			"locked": false,
			"text": "idea: Instead of iterating until convergence, stack a couple of convolutional layers\nwhich means constraining of parameters is not required.\nThing is Convolution operator cannot directly be applied to graphs as there is no\ncorresponding translation operator but we can derive one.",
			"rawText": "idea: Instead of iterating until convergence, stack a couple of convolutional layers\nwhich means constraining of parameters is not required.\nThing is Convolution operator cannot directly be applied to graphs as there is no\ncorresponding translation operator but we can derive one.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "idea: Instead of iterating until convergence, stack a couple of convolutional layers\nwhich means constraining of parameters is not required.\nThing is Convolution operator cannot directly be applied to graphs as there is no\ncorresponding translation operator but we can derive one.",
			"lineHeight": 1.25
		},
		{
			"id": "U9gBRbN0KQNgAu3EQT3Ja",
			"type": "image",
			"x": -114.86553844729536,
			"y": 2580.3628119380496,
			"width": 309.8947269057044,
			"height": 147.2689045269802,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 951223184,
			"version": 108,
			"versionNonce": 1325463952,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715183328387,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cf36ca2c6503e84800c086507ac82ae4a5781b79",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "sdfYfwzTfGPIrEyTpc12b",
			"type": "image",
			"x": -115.33789995892967,
			"y": 2854.26107428788,
			"width": 286.9318808939605,
			"height": 57.7715196430793,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 148500368,
			"version": 133,
			"versionNonce": 1366021488,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ECryC-FGwXub8pa0CG4Jy",
					"type": "arrow"
				}
			],
			"updated": 1715183976466,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5324e2faf3cb21f41a3ebb2db6e22f14257a2887",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ECryC-FGwXub8pa0CG4Jy",
			"type": "arrow",
			"x": 8.579497358937033,
			"y": 2923.3634075634145,
			"width": 2.5273913543059052,
			"height": 102.78058174177295,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1120712592,
			"version": 58,
			"versionNonce": 859611504,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715183993430,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-2.5273913543059052,
					102.78058174177295
				]
			],
			"lastCommittedPoint": [
				-2.5273913543059052,
				102.78058174177295
			],
			"startBinding": {
				"elementId": "sdfYfwzTfGPIrEyTpc12b",
				"focus": 0.12872863254389785,
				"gap": 11.330813632455147
			},
			"endBinding": {
				"elementId": "DXU-Zu7_F5z0htGK-JOS8",
				"focus": -0.0049459713391512275,
				"gap": 5.013623821208057
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "DXU-Zu7_F5z0htGK-JOS8",
			"type": "image",
			"x": -152.44789399536876,
			"y": 3031.1576131263955,
			"width": 317,
			"height": 54,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 810090864,
			"version": 80,
			"versionNonce": 134673264,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ECryC-FGwXub8pa0CG4Jy",
					"type": "arrow"
				}
			],
			"updated": 1715183993430,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "966a0cad5691da707d0f709dcda15e144e645df7",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "WJjsMp5V",
			"type": "text",
			"x": -249.63473401954695,
			"y": 2950.1427580805125,
			"width": 244.51971435546875,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2012855152,
			"version": 91,
			"versionNonce": 1737905552,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184332601,
			"link": null,
			"locked": false,
			"text": "How the fuck did we\nderive this operator?????",
			"rawText": "How the fuck did we\nderive this operator?????",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How the fuck did we\nderive this operator?????",
			"lineHeight": 1.25
		},
		{
			"id": "vujS9qIIUGUEzjah_Y-yR",
			"type": "line",
			"x": 48.535658977735466,
			"y": 3083.408315519566,
			"width": 10.661244595124117,
			"height": 47.97560067805853,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1636593008,
			"version": 62,
			"versionNonce": 2044744048,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184066839,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-10.661244595124117,
					47.97560067805853
				]
			],
			"lastCommittedPoint": [
				-10.661244595124117,
				47.97560067805853
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "_U-2xy8vOeeITb1e3HTXI",
			"type": "image",
			"x": -13.249348228765712,
			"y": 3142.484549594786,
			"width": 96.91690292519195,
			"height": 26.779670545118826,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2109678960,
			"version": 68,
			"versionNonce": 1692886928,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184077053,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b7a97f23950ba32f6424aef4dc2a44cf3e485fca",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "8E5H5u-_V5K_9NdlJoCsx",
			"type": "line",
			"x": 35.20910323383032,
			"y": 3166.921398181372,
			"width": 5.3306222975620585,
			"height": 44.42185247968382,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1883267440,
			"version": 30,
			"versionNonce": 740930960,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184084405,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					5.3306222975620585,
					44.42185247968382
				]
			],
			"lastCommittedPoint": [
				5.3306222975620585,
				44.42185247968382
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "mvVeK6is",
			"type": "text",
			"x": -22.223614994366244,
			"y": 3219.8969988594304,
			"width": 145.07229614257812,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 245958000,
			"version": 89,
			"versionNonce": 262146960,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184118380,
			"link": null,
			"locked": false,
			"text": "adjacency matrix\nsuch that aij is\n1 if nodes i and j \nare connected and\n0 otherwise",
			"rawText": "adjacency matrix\nsuch that aij is\n1 if nodes i and j \nare connected and\n0 otherwise",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "adjacency matrix\nsuch that aij is\n1 if nodes i and j \nare connected and\n0 otherwise",
			"lineHeight": 1.25
		},
		{
			"id": "S80REK6VqcxT953W6KmlI",
			"type": "line",
			"x": -26.98149023772703,
			"y": 3082.5198784699724,
			"width": 72.85183806668147,
			"height": 62.19059347155735,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1469998992,
			"version": 44,
			"versionNonce": 217828720,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184124594,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-72.85183806668147,
					62.19059347155735
				]
			],
			"lastCommittedPoint": [
				-72.85183806668147,
				62.19059347155735
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "YocvBvHMdMcnQvCqyzJTs",
			"type": "image",
			"x": -178.89520961009703,
			"y": 3144.6707690525336,
			"width": 121.6978435780363,
			"height": 53.86625863290132,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 921745808,
			"version": 79,
			"versionNonce": 895300976,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184193961,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ab287ec144cb8c63ee8156229be102677588ded5",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ce8Gkrb9e9INZQxBrrt1Y",
			"type": "line",
			"x": -164.68923292474693,
			"y": 3185.578576222839,
			"width": 7.107496396749411,
			"height": 43.53341543009037,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2019685776,
			"version": 42,
			"versionNonce": 140360560,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184201045,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					7.107496396749411,
					43.53341543009037
				]
			],
			"lastCommittedPoint": [
				7.107496396749411,
				43.53341543009037
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "d0pKkTxq",
			"type": "text",
			"x": -244.50191017301705,
			"y": 3229.111991652929,
			"width": 173.84034729003906,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 312279440,
			"version": 69,
			"versionNonce": 1654973328,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184225033,
			"link": null,
			"locked": false,
			"text": "Rank matrix\nindicating how many\nnodes Aij is connected\nto (diagonal)",
			"rawText": "Rank matrix\nindicating how many\nnodes Aij is connected\nto (diagonal)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Rank matrix\nindicating how many\nnodes Aij is connected\nto (diagonal)",
			"lineHeight": 1.25
		},
		{
			"id": "bNFygeLe-j832s2swXKRI",
			"type": "line",
			"x": 160.4787272265388,
			"y": 3081.631441420379,
			"width": 53.306222975620585,
			"height": 40.86810428130866,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 558710672,
			"version": 35,
			"versionNonce": 147903344,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184242573,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					53.306222975620585,
					40.86810428130866
				]
			],
			"lastCommittedPoint": [
				53.306222975620585,
				40.86810428130866
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "2rWuJ9OG",
			"type": "text",
			"x": 160.39282221143674,
			"y": 3122.4995457016876,
			"width": 106.78425598144531,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2130340240,
			"version": 19,
			"versionNonce": 1685502832,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184247673,
			"link": null,
			"locked": false,
			"text": " Filter matrix",
			"rawText": " Filter matrix",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " Filter matrix",
			"lineHeight": 1.25
		},
		{
			"id": "U5fPZuMGt_n9scU93h2DJ",
			"type": "image",
			"x": 175.26868398753174,
			"y": 3142.621543407601,
			"width": 88.58221407397295,
			"height": 27.642676732303613,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 162791824,
			"version": 46,
			"versionNonce": 743805840,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184297692,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3e8de24e8aafa43f9ca868a558fac4a99f7c06dd",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "6jkb8meQ",
			"type": "text",
			"x": 133.79712831528366,
			"y": 3174.9173316277147,
			"width": 177.744384765625,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1131581808,
			"version": 96,
			"versionNonce": 924772240,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184316163,
			"link": null,
			"locked": false,
			"text": "C is the number of \nchannels and F is\nthe dimensionality of x",
			"rawText": "C is the number of \nchannels and F is\nthe dimensionality of x",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "C is the number of \nchannels and F is\nthe dimensionality of x",
			"lineHeight": 1.25
		},
		{
			"id": "gFrj5hYT8HCNLRG_gpAX0",
			"type": "arrow",
			"x": -274.85542707436275,
			"y": 2972.3536843203565,
			"width": 419.3638651764063,
			"height": 96.83963840571096,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 705311120,
			"version": 238,
			"versionNonce": 1186103696,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715184443456,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-278.08079652282083,
					-75.51714921546272
				],
				[
					-419.3638651764063,
					21.322489190248234
				]
			],
			"lastCommittedPoint": [
				-443.33008774724476,
				21.322489190248234
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "YInmLx64",
				"focus": 0.024827121338953154,
				"gap": 10.661244595124117
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "YInmLx64",
			"type": "text",
			"x": -1068.5429411494774,
			"y": 3004.337418105729,
			"width": 583.441162109375,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 50270064,
			"version": 283,
			"versionNonce": 1791456144,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "gFrj5hYT8HCNLRG_gpAX0",
					"type": "arrow"
				}
			],
			"updated": 1715184443455,
			"link": null,
			"locked": false,
			"text": "Let me show you the horrors of this derivation\nand then you'll learn to never ask for an explanation ever again\nalso no I did not understand shit from this and id rather get castrated\nthan spend the time to do so (at the moment at least)",
			"rawText": "Let me show you the horrors of this derivation\nand then you'll learn to never ask for an explanation ever again\nalso no I did not understand shit from this and id rather get castrated\nthan spend the time to do so (at the moment at least)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Let me show you the horrors of this derivation\nand then you'll learn to never ask for an explanation ever again\nalso no I did not understand shit from this and id rather get castrated\nthan spend the time to do so (at the moment at least)",
			"lineHeight": 1.25
		},
		{
			"id": "aCOa7979",
			"type": "text",
			"x": -1074.5344991313905,
			"y": 3098.358014498732,
			"width": 582.0653076171875,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2028546960,
			"version": 153,
			"versionNonce": 1313624944,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184540815,
			"link": null,
			"locked": false,
			"text": "The normalized Graph laplacian is DEFINED as (this is a definition, dont\nask me where it comes from)",
			"rawText": "The normalized Graph laplacian is DEFINED as (this is a definition, dont\nask me where it comes from)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The normalized Graph laplacian is DEFINED as (this is a definition, dont\nask me where it comes from)",
			"lineHeight": 1.25
		},
		{
			"id": "C2pmqVAR2Or8XPYDfG1XY",
			"type": "image",
			"x": -858.1013093023355,
			"y": 3142.851832549958,
			"width": 170.76220279740187,
			"height": 26.320489904862693,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1261054352,
			"version": 97,
			"versionNonce": 1258635152,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184543396,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "eac9ece4de522b2d388c46f5e905b0af897cf85b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "b8ll2wFC",
			"type": "text",
			"x": -995.8887489456174,
			"y": 3181.9157044972376,
			"width": 422.97686767578125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1469406064,
			"version": 4,
			"versionNonce": 1317289360,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184565850,
			"link": null,
			"locked": false,
			"text": "Using the eigen-decomposition of the graph Laplacian ",
			"rawText": "Using the eigen-decomposition of the graph Laplacian ",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Using the eigen-decomposition of the graph Laplacian ",
			"lineHeight": 1.25
		},
		{
			"id": "6XbsZOcrFsnuqOKge6frS",
			"type": "image",
			"x": -847.2271412410488,
			"y": 3208.1813649294936,
			"width": 108.15439459272366,
			"height": 25.015302150697988,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1805530480,
			"version": 96,
			"versionNonce": 424546704,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184629633,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5a6d4c9b08a875cda405d7d687c1ca53d181814f",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "YRk0Mz_hxtfanP_C-OmVY",
			"type": "line",
			"x": -735.8615169348175,
			"y": 3226.2253711385197,
			"width": 80.22408604460179,
			"height": 17.440018705348393,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 142677904,
			"version": 64,
			"versionNonce": 1884620144,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184634633,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					42.35433114156001,
					17.440018705348393
				],
				[
					80.22408604460179,
					10.464011223209127
				]
			],
			"lastCommittedPoint": [
				80.22408604460179,
				10.464011223209127
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "emIpX5OZ1w7-iQCnjCKio",
			"type": "image",
			"x": -649.0710099629841,
			"y": 3216.674558966244,
			"width": 127.88216653449574,
			"height": 24.078232192687484,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 159580560,
			"version": 120,
			"versionNonce": 252944752,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184645444,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4f2812f79f0ef1f7e198fc939cad6dca80811502",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "SDLUi4hz",
			"type": "text",
			"x": -623.4717278350608,
			"y": 3237.6859548591774,
			"width": 95.12019348144531,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1242778000,
			"version": 43,
			"versionNonce": 1272512880,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184651542,
			"link": null,
			"locked": false,
			"text": "eigenvectors",
			"rawText": "eigenvectors",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "eigenvectors",
			"lineHeight": 1.25
		},
		{
			"id": "xJvfj9kM",
			"type": "text",
			"x": -916.9158791680159,
			"y": 3259.686815528893,
			"width": 253.00851440429688,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1684185488,
			"version": 47,
			"versionNonce": 1812167536,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184693524,
			"link": null,
			"locked": false,
			"text": "We can also define the following",
			"rawText": "We can also define the following",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can also define the following",
			"lineHeight": 1.25
		},
		{
			"id": "rEs3ZwnS_BIQZkwwz6TVQ",
			"type": "image",
			"x": -908.6078481066598,
			"y": 3282.5215430721682,
			"width": 245.9146637238538,
			"height": 82.64900543887097,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 940531568,
			"version": 359,
			"versionNonce": 1620965744,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "IiFbNWvFSF5xOjR1-sb7k",
					"type": "arrow"
				}
			],
			"updated": 1715186141013,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e230dcd86368f530550e761cf798216984e0beed",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "V7sbjaXY3gKs_ITyYo1Ac",
			"type": "line",
			"x": -904.6150518334919,
			"y": 3313.152840747818,
			"width": 75.2801635082468,
			"height": 26.091420306835516,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 996037520,
			"version": 51,
			"versionNonce": 1452318576,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184718997,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-42.34509197338889,
					-26.091420306835516
				],
				[
					-75.2801635082468,
					-6.843651228022281
				]
			],
			"lastCommittedPoint": [
				-75.2801635082468,
				-6.843651228022281
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "XfuDxSNl",
			"type": "text",
			"x": -1142.6809379919987,
			"y": 3308.0201023268014,
			"width": 216.92848205566406,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1359935856,
			"version": 108,
			"versionNonce": 1457754512,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184743925,
			"link": null,
			"locked": false,
			"text": "Graph fourier transform\nfor function f that assigns\nvalues to each node",
			"rawText": "Graph fourier transform\nfor function f that assigns\nvalues to each node",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Graph fourier transform\nfor function f that assigns\nvalues to each node",
			"lineHeight": 1.25
		},
		{
			"id": "N42vKnUc",
			"type": "text",
			"x": -1604.3242238164892,
			"y": 3200.646146869753,
			"width": 430.2728271484375,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 890054032,
			"version": 209,
			"versionNonce": 1325143440,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184854618,
			"link": null,
			"locked": false,
			"text": "Generalized Convolution can be defined in the spectral\ndomain using the convolution theorem\nits a theorem so dont question it",
			"rawText": "Generalized Convolution can be defined in the spectral\ndomain using the convolution theorem\nits a theorem so dont question it",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Generalized Convolution can be defined in the spectral\ndomain using the convolution theorem\nits a theorem so dont question it",
			"lineHeight": 1.25
		},
		{
			"id": "Xh38dnz_ZRqh3B_x2cqb7",
			"type": "image",
			"x": -1543.3109510929933,
			"y": 3262.0230060190306,
			"width": 281.8964187993804,
			"height": 30.349096847966422,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1433090960,
			"version": 98,
			"versionNonce": 2090433392,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184836394,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a17e022d59c201eb34d2eeabd13702365b17f154",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "8AOX0YSSC7aGKO0ONEhne",
			"type": "arrow",
			"x": -1434.0361096286258,
			"y": 3290.3427456424624,
			"width": 153.10281514652092,
			"height": 23.97064277546542,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1059798928,
			"version": 121,
			"versionNonce": 1892942704,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715184872459,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-107.48126921902258,
					23.97064277546542
				],
				[
					-153.10281514652092,
					17.011423905169067
				]
			],
			"lastCommittedPoint": [
				-153.10281514652092,
				17.011423905169067
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "yOVSTs0p",
			"type": "text",
			"x": -1711.3682051724725,
			"y": 3281.063787148734,
			"width": 103.08821105957031,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 84900208,
			"version": 50,
			"versionNonce": 2043689872,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715184882270,
			"link": null,
			"locked": false,
			"text": "Who the fuck\nis that guy?",
			"rawText": "Who the fuck\nis that guy?",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Who the fuck\nis that guy?",
			"lineHeight": 1.25
		},
		{
			"id": "A05knTzPwu6if63eIQ4jS",
			"type": "arrow",
			"x": -1427.0240406870055,
			"y": 3312.618462946558,
			"width": 640.0771979903482,
			"height": 274.7454224655303,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 399351664,
			"version": 196,
			"versionNonce": 1000709520,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715186144012,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					39.8181771689176,
					174.2045251140139
				],
				[
					562.4317525109592,
					157.28179981722406
				],
				[
					640.0771979903482,
					274.7454224655303
				]
			],
			"lastCommittedPoint": [
				640.0771979903482,
				274.7454224655303
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "pzVIbdDg9xI0mroZGRR1Q",
				"focus": 0.13714465046569926,
				"gap": 8.840905022802872
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "IiFbNWvFSF5xOjR1-sb7k",
			"type": "arrow",
			"x": -792.9195692719948,
			"y": 3375.332091987603,
			"width": 3.9818177168915554,
			"height": 213.02724785370856,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 612439440,
			"version": 65,
			"versionNonce": 686258576,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186144012,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					3.9818177168915554,
					213.02724785370856
				]
			],
			"lastCommittedPoint": [
				3.9818177168915554,
				213.02724785370856
			],
			"startBinding": {
				"elementId": "rEs3ZwnS_BIQZkwwz6TVQ",
				"focus": 0.06652732157278006,
				"gap": 10.161543476563793
			},
			"endBinding": {
				"elementId": "pzVIbdDg9xI0mroZGRR1Q",
				"focus": -0.0022893456032373563,
				"gap": 7.845450593579699
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "pzVIbdDg9xI0mroZGRR1Q",
			"type": "image",
			"x": -945.9422971258803,
			"y": 3596.204790434891,
			"width": 316,
			"height": 52,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1265352592,
			"version": 26,
			"versionNonce": 249677712,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "A05knTzPwu6if63eIQ4jS",
					"type": "arrow"
				},
				{
					"id": "IiFbNWvFSF5xOjR1-sb7k",
					"type": "arrow"
				}
			],
			"updated": 1715186144012,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "09e078e53aa33c0b29a5319d99f5b29c72ecd7ee",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "haz7PCxNCx-UBwDQ3qeVn",
			"type": "line",
			"x": -742.1513933816244,
			"y": 3608.268428425771,
			"width": 96.55907963462482,
			"height": 71.67271890405118,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 298027888,
			"version": 71,
			"versionNonce": 200567184,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186156065,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					29.86363287668803,
					-71.67271890405118
				],
				[
					96.55907963462482,
					-70.67726447482846
				]
			],
			"lastCommittedPoint": [
				96.55907963462482,
				-70.67726447482846
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "wqAdZrh3",
			"type": "text",
			"x": -653.3779550435368,
			"y": 3520.668438654153,
			"width": 166.88035583496094,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1919932784,
			"version": 74,
			"versionNonce": 1084113776,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "2q1TbcjosyWcRqKBPMgfp",
					"type": "arrow"
				}
			],
			"updated": 1715186199708,
			"link": null,
			"locked": false,
			"text": "Convolution filter\ndefined in the fourier\ntransform",
			"rawText": "Convolution filter\ndefined in the fourier\ntransform",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Convolution filter\ndefined in the fourier\ntransform",
			"lineHeight": 1.25
		},
		{
			"id": "2q1TbcjosyWcRqKBPMgfp",
			"type": "arrow",
			"x": -484.3286962128832,
			"y": 3537.5911639509427,
			"width": 101.53635178073944,
			"height": 11.945453150675348,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 753154448,
			"version": 33,
			"versionNonce": 1114180464,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715186200172,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					101.53635178073944,
					11.945453150675348
				]
			],
			"lastCommittedPoint": [
				101.53635178073944,
				11.945453150675348
			],
			"startBinding": {
				"elementId": "wqAdZrh3",
				"focus": -0.581390534366271,
				"gap": 2.1689029956926333
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "3REhKLpl",
			"type": "text",
			"x": -395.05936302560747,
			"y": 3517.6820753664842,
			"width": 253.48855590820312,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 123830640,
			"version": 99,
			"versionNonce": 1848928144,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186222141,
			"link": null,
			"locked": false,
			"text": "Which can be approximated using\nChebyshev polynomials",
			"rawText": "Which can be approximated using\nChebyshev polynomials",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which can be approximated using\nChebyshev polynomials",
			"lineHeight": 1.25
		},
		{
			"id": "gTgfNEsX4E0RxiDEe2zl_",
			"type": "image",
			"x": -380.5696370350215,
			"y": 3573.7047904348924,
			"width": 215.31397847771362,
			"height": 62.159094977197086,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1950097296,
			"version": 87,
			"versionNonce": 127663984,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186231688,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f9734408fe1baaaa8bb6fc36057d673f225d3101",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "i-HThhnwvRlavWWvpPxN0",
			"type": "image",
			"x": -416.12419666982316,
			"y": 3639.7373243389,
			"width": 315.78196291415014,
			"height": 20.890191392782242,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1119725456,
			"version": 154,
			"versionNonce": 1766354800,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ihrjWPQJJDNUWSAHU44Eo",
					"type": "arrow"
				}
			],
			"updated": 1715186332428,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f81db5877151bddf22f44a7aeeb36e17b2f05502",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "mT_GUTFxnqHyudCtx60Kq",
			"type": "image",
			"x": -141.5696626059762,
			"y": 3792.8138585625884,
			"width": 211.81299684286017,
			"height": 35.06363799087888,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1129842544,
			"version": 143,
			"versionNonce": 575470960,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186364843,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "04fce44f93dbf1e9ff165aef3769a572914b2e4b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ihrjWPQJJDNUWSAHU44Eo",
			"type": "arrow",
			"x": -251.39235977471662,
			"y": 3672.972966325262,
			"width": 97.55453406384777,
			"height": 50.76817589037,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1410415504,
			"version": 48,
			"versionNonce": 513619824,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715186333129,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					97.55453406384777,
					50.76817589037
				]
			],
			"lastCommittedPoint": [
				97.55453406384777,
				50.76817589037
			],
			"startBinding": {
				"elementId": "i-HThhnwvRlavWWvpPxN0",
				"focus": 0.20764406878134997,
				"gap": 12.345450593579699
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "HnjgoGUy",
			"type": "text",
			"x": -187.4876185449367,
			"y": 3705.822962489619,
			"width": 306.2086486816406,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 109106576,
			"version": 184,
			"versionNonce": 1283309968,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186360881,
			"link": null,
			"locked": false,
			"text": "using this property which is\nabout the only thing I UNNDERSTAND\nhere (because we explained it before\nin RNN note)",
			"rawText": "using this property which is\nabout the only thing I UNNDERSTAND\nhere (because we explained it before\nin RNN note)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "using this property which is\nabout the only thing I UNNDERSTAND\nhere (because we explained it before\nin RNN note)",
			"lineHeight": 1.25
		},
		{
			"id": "4ZEoqJSzmQnH9bPLuCGXJ",
			"type": "arrow",
			"x": -160.80600671542936,
			"y": 3822.2911307087024,
			"width": 440.98631214576096,
			"height": 96.33346881758189,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1734369648,
			"version": 185,
			"versionNonce": 401841008,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715186427608,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-440.98631214576096,
					-96.33346881758189
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "hFO2aBKPKl8iJvrq408Nw",
				"focus": -0.24388088522229928,
				"gap": 1.8882016338523044
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "lKPbAGZd",
			"type": "text",
			"x": -444.9822844024539,
			"y": 3738.672958653976,
			"width": 116.41624450683594,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1135288688,
			"version": 47,
			"versionNonce": 1585887088,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186413801,
			"link": null,
			"locked": false,
			"text": "We can rewrite",
			"rawText": "We can rewrite",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can rewrite",
			"lineHeight": 1.25
		},
		{
			"id": "hFO2aBKPKl8iJvrq408Nw",
			"type": "image",
			"x": -963.7604870802745,
			"y": 3664.7547789279633,
			"width": 360.0799665852319,
			"height": 82.13636712331154,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1556730768,
			"version": 154,
			"versionNonce": 961429904,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "4ZEoqJSzmQnH9bPLuCGXJ",
					"type": "arrow"
				}
			],
			"updated": 1715186410982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3dc9000f18ec048c16c834420c3d8beef33ae2cd",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "TD11q9uU",
			"type": "text",
			"x": -960.4222864351183,
			"y": 3752.609320663097,
			"width": 372.83270263671875,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1716940688,
			"version": 123,
			"versionNonce": 1784216976,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186473573,
			"link": null,
			"locked": false,
			"text": "This filter is now K localized\nand in english this means\nnodes up to a distance of K edges influence a\ncentral node xi, and ones outside of it do not.",
			"rawText": "This filter is now K localized\nand in english this means\nnodes up to a distance of K edges influence a\ncentral node xi, and ones outside of it do not.",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This filter is now K localized\nand in english this means\nnodes up to a distance of K edges influence a\ncentral node xi, and ones outside of it do not.",
			"lineHeight": 1.25
		},
		{
			"id": "7i5jmpj5",
			"type": "text",
			"x": -880.6016169019389,
			"y": 3854.1456724438362,
			"width": 211.20045471191406,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 644199824,
			"version": 66,
			"versionNonce": 812221808,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186538591,
			"link": null,
			"locked": false,
			"text": "We set K=1 and arrive at ",
			"rawText": "We set K=1 and arrive at ",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We set K=1 and arrive at ",
			"lineHeight": 1.25
		},
		{
			"id": "80Lv97h0IIfRYEN66ZkhS",
			"type": "image",
			"x": -1054.0422868974986,
			"y": 3877.765453330183,
			"width": 265.4181925114899,
			"height": 31.225669707234108,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2038648176,
			"version": 93,
			"versionNonce": 196601232,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186557600,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c1f3efc402dc5be4410bc7e4e033d1e17a1aa01a",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "D9qkbrxbYThEFVyml9W5f",
			"type": "image",
			"x": -780.6923163040956,
			"y": 3868.927485046537,
			"width": 228.75290251563501,
			"height": 48.08182027398698,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1736105840,
			"version": 75,
			"versionNonce": 285670800,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186594916,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9ba3dcc8f4ca0b68c628c10eae8c42e7264cc8a9",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "tHLfMOI4",
			"type": "text",
			"x": -1086.256045249856,
			"y": 3911.882029338767,
			"width": 600.6093139648438,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 455163248,
			"version": 109,
			"versionNonce": 488878480,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186628283,
			"link": null,
			"locked": false,
			"text": "WHich if normalized into [-1,1] area to avid exploding and vanishing gradients\nbecomes",
			"rawText": "WHich if normalized into [-1,1] area to avid exploding and vanishing gradients\nbecomes",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "WHich if normalized into [-1,1] area to avid exploding and vanishing gradients\nbecomes",
			"lineHeight": 1.25
		},
		{
			"id": "ScHQocoBMw_iC_Sppj3c2",
			"type": "image",
			"x": -922.9827907103387,
			"y": 3962.9788642565004,
			"width": 292.3208616533886,
			"height": 40.08182027398709,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 759752048,
			"version": 144,
			"versionNonce": 1665296752,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186642044,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "126bf3078bf339983ce258e13b81b36cf10e844f",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "2lBgNvm5",
			"type": "text",
			"x": -938.645041754824,
			"y": 3997.4911102519395,
			"width": 339.2327575683594,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1562416496,
			"version": 128,
			"versionNonce": 245720944,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186688883,
			"link": null,
			"locked": false,
			"text": "Viola! The magic happens because a wizard\ndecided its gonna happen",
			"rawText": "Viola! The magic happens because a wizard\ndecided its gonna happen",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Viola! The magic happens because a wizard\ndecided its gonna happen",
			"lineHeight": 1.25
		},
		{
			"id": "WOI4thjQz8WN4BIAG6beP",
			"type": "line",
			"x": 1255.8861053556186,
			"y": 2887.5764106748993,
			"width": 884.9999999999998,
			"height": 4,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 229446512,
			"version": 107,
			"versionNonce": 1137498512,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186766164,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					884.9999999999998,
					-4
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "nVoZDJjS",
			"type": "text",
			"x": 1630.67375641763,
			"y": 2900.0764106748993,
			"width": 158.42469787597656,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 91207056,
			"version": 35,
			"versionNonce": 1543058288,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186774539,
			"link": null,
			"locked": false,
			"text": "The output",
			"rawText": "The output",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The output",
			"lineHeight": 1.25
		},
		{
			"id": "JolUgm45",
			"type": "text",
			"x": 1329.3765228360871,
			"y": 2943.5764106748993,
			"width": 785.0191650390625,
			"height": 175,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 884465520,
			"version": 259,
			"versionNonce": 830122864,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186894310,
			"link": null,
			"locked": false,
			"text": "Finally, the node representation has to be transformed to the prediction\n\nthis depends if youre graph focused on Node focused, obviously for node\nfocused outputs you need y to output a prediction for every node\nwhereas for graph-wise you input the entire graph and y outputs one prediction\n\nCommon methods",
			"rawText": "Finally, the node representation has to be transformed to the prediction\n\nthis depends if youre graph focused on Node focused, obviously for node\nfocused outputs you need y to output a prediction for every node\nwhereas for graph-wise you input the entire graph and y outputs one prediction\n\nCommon methods",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Finally, the node representation has to be transformed to the prediction\n\nthis depends if youre graph focused on Node focused, obviously for node\nfocused outputs you need y to output a prediction for every node\nwhereas for graph-wise you input the entire graph and y outputs one prediction\n\nCommon methods",
			"lineHeight": 1.25
		},
		{
			"id": "q0dJmvZSmnr_LSzuaE-KK",
			"type": "image",
			"x": 1442.8861053556184,
			"y": 3129.5764106748993,
			"width": 198,
			"height": 112,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 685535600,
			"version": 106,
			"versionNonce": 393900944,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186909110,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5b76451e8930b5b5bef3e924d3f55abf35b69986",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "IJhRNRUKXehIb9D-GEMGo",
			"type": "image",
			"x": 1794.8861053556184,
			"y": 3132.5764106748993,
			"width": 230,
			"height": 104,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 357982064,
			"version": 90,
			"versionNonce": 575333232,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186933064,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cd530f337cab0b76ced9b5a4a512cd56fbf272a3",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "NXXm3PXB",
			"type": "text",
			"x": 1522.7961242765168,
			"y": 3116.5764106748993,
			"width": 36.179962158203125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 156339600,
			"version": 71,
			"versionNonce": 1353835376,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186921503,
			"link": null,
			"locked": false,
			"text": "Sum",
			"rawText": "Sum",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sum",
			"lineHeight": 1.25
		},
		{
			"id": "A8vDfIrK",
			"type": "text",
			"x": 1883.1761444181184,
			"y": 3115.5764106748993,
			"width": 77.419921875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 926505328,
			"version": 78,
			"versionNonce": 1073542512,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715186933064,
			"link": null,
			"locked": false,
			"text": "Average",
			"rawText": "Average",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Average",
			"lineHeight": 1.25
		},
		{
			"id": "8EWCERiv",
			"type": "text",
			"x": 232.18579762869518,
			"y": -376.4174313228846,
			"width": 196.1444091796875,
			"height": 100,
			"angle": 0.4755744906968733,
			"strokeColor": "#e03131",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 125968752,
			"version": 192,
			"versionNonce": 291322768,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715187020023,
			"link": null,
			"locked": false,
			"text": "Warning, this note\nis a fucking mess and\ndoesnt explain everything\nbecause its too difficult\nfor my tiny pea brain",
			"rawText": "Warning, this note\nis a fucking mess and\ndoesnt explain everything\nbecause its too difficult\nfor my tiny pea brain",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Warning, this note\nis a fucking mess and\ndoesnt explain everything\nbecause its too difficult\nfor my tiny pea brain",
			"lineHeight": 1.25
		},
		{
			"id": "jV7bjJSI",
			"type": "text",
			"x": 916.5873552221968,
			"y": 2944.902846678394,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 388198256,
			"version": 2,
			"versionNonce": 1600851344,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715182457455,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "rlKVI3VQ",
			"type": "text",
			"x": 583.9159589373321,
			"y": 2846.2874182779747,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 108040560,
			"version": 2,
			"versionNonce": 436816784,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715182503388,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "hlb1NcCR",
			"type": "text",
			"x": 304.93769224086316,
			"y": 2415.2403716754143,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1005099920,
			"version": 2,
			"versionNonce": 30628720,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715183227355,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "WdRRGtUeOtoqsWy2IKUjJ",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "bT3dsahS",
			"type": "text",
			"x": 2.3158093111786116,
			"y": 2962.253698434301,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 932497296,
			"version": 2,
			"versionNonce": 1311272816,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715183977485,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ECryC-FGwXub8pa0CG4Jy",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "BVpyIcWy",
			"type": "text",
			"x": 35.53973316078691,
			"y": 3211.3432506610557,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 808140144,
			"version": 2,
			"versionNonce": 196927376,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715184085270,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "CwgUZpw4",
			"type": "text",
			"x": -103.83333593380303,
			"y": 3144.7104719415297,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1282363280,
			"version": 2,
			"versionNonce": 991134576,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715184125328,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "folgW3yT",
			"type": "text",
			"x": -556.9362312265781,
			"y": 2886.8365351048938,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 181403024,
			"version": 2,
			"versionNonce": 2113657200,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715184340384,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "gFrj5hYT8HCNLRG_gpAX0",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "H5GWmaKB",
			"type": "text",
			"x": -659.6374385196102,
			"y": 3236.1910961130043,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 173840272,
			"version": 2,
			"versionNonce": 1364704112,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715184635501,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "5nooWBvP",
			"type": "text",
			"x": -984.7506793746361,
			"y": 3306.7369177215473,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 879680912,
			"version": 2,
			"versionNonce": 1044485488,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715184719635,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "7HaC4G1b",
			"type": "text",
			"x": -1545.517386477043,
			"y": 3304.313388417928,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 987595152,
			"version": 2,
			"versionNonce": 543298928,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715184872460,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "8AOX0YSSC7aGKO0ONEhne",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "sde8NJiw",
			"type": "text",
			"x": -1122.5042835484278,
			"y": 3469.7689914428665,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 31306096,
			"version": 2,
			"versionNonce": 1675134864,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715186135399,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "A05knTzPwu6if63eIQ4jS",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "MZOoH7RB",
			"type": "text",
			"x": -649.5923213763941,
			"y": 3537.5911639509427,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2036615536,
			"version": 2,
			"versionNonce": 2140410768,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715186156745,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "Dp4ovsIw",
			"type": "text",
			"x": -593.8468733399097,
			"y": 3532.613891804828,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1345351568,
			"version": 2,
			"versionNonce": 676881264,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715186158300,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "t17UDltV",
			"type": "text",
			"x": -437.560527951908,
			"y": 3533.5638905262804,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1917450640,
			"version": 2,
			"versionNonce": 169221488,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715186200172,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "2q1TbcjosyWcRqKBPMgfp",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "XNdFF9HI",
			"type": "text",
			"x": -206.61510037218727,
			"y": 3688.357054270447,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1622543760,
			"version": 2,
			"versionNonce": 652527984,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715186333129,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ihrjWPQJJDNUWSAHU44Eo",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "3YL3kOA6",
			"type": "text",
			"x": -463.94007032631635,
			"y": 3770.9797718959508,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1118984592,
			"version": 2,
			"versionNonce": 776453488,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715186378255,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "4ZEoqJSzmQnH9bPLuCGXJ",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "hENwk5HV",
			"type": "text",
			"x": -791.9423047552746,
			"y": 3926.813845777111,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9c36b5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 298796912,
			"version": 2,
			"versionNonce": 101954960,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715186596165,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "#9c36b5",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "triangle",
		"scrollX": 5528.819540807122,
		"scrollY": 3387.6593983327366,
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
		},
		"objectsSnapModeEnabled": false
	},
	"files": {}
}
```
%%