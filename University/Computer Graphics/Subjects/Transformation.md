---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Transformations ^dh18yBga

What is Geometry? ^K9cGYJRe

Points, Lines, Solid Geometric shapes
but more often than not, triangles!
or something composed of many triangles... ^p5vbGDZB


. Efficient computations and rendering
. basic shape
. Can form many shapes
. Easy to store ^QQuKUFBM

Store vertex coordinates -> store triangles as 3 indices of vertices ^dqLByBwu

Why triangles? ^yiRfgbX9

How to reference in the scene? ^sId0zKic

Objects are stored in the scene local to their ecosystem
    . If teapot on table -> teapot's world is the table
that way small ecosystems are attached to each other
and can detect changes in one another.  ^VrFiKz5i

Protective Transformations ^DWvfEkuy

Affine Transformations ^885TJtcd

Linear Transformations ^FnsWsTks

Non-Linear Transformations ^VCc77dbc

TRANSLATION ^r8Ve8AtG

Similar to addition! ^KAnucQva

From Linear Algebra! ^qohSgiSB

%%***>>>text element-link:[[Subspaces]]<<<***%%Key notes:
. Origin is preserved
. Can be modeled as a 3x3
  Matrix that describes how
  each axis is transformed ^NpUK2a7g

Scaling ^BC8dlz7t

Reminder ^1fqWDxzC

How the standard basis
get transformed by this
matrix, aka its basis ^tG5oiyN4

If S1=S2=S3  => isotropic
else           => anisotropic ^0tBoPkSf

Shearing ^uy7KIduA

Rotating ^7QnKs3Y6

We want to rotate around an
axis x/y/z by an angle a ^cUUmOXRG

We want to combine linear
and non-linear transformations
into one transformation that 
way we can composite them using
matrix multiplication to make it more
compact! ^XEnBLgpo

Using
Affine subspaces! ^uc4txuvp

Using
Projective subspaces! ^BESVIZlk

Homogeneous
Coordinates ^FZ5mjH8J

Affine transformations ^MFBs87UN

We can now do both transformations all within one matrix!

We define out coordinates in
homogeneous coordinates first.

 ^EM7IOfRV

And we define our transformation
matrix as from 2 parts, A being
the linear part as a composite
of all linear transformations and
b being the translation part! ^djqoZTaM

3x3 ^9C1fIMfn

1X3 ^hP1seoQU

3X1 ^qYhmLHM1

But what if we want to rotate around an arbitrary axis?
 ^ocMvDHj4

Well we know how to rotate around xyz axis...
So if we rotate our coordinates to align back with xyz, preform our
actual rotation THEN rotate back to our old axis, this works just fine! ^mDNbMMJK

How do we do so? ^HtoxQCkP

We want to find our orthonormal axis (r,s,t)

r: we already have r its our rotation axis! (We assume its unit length)

s: we pick one of the canonical basis to preform a cross-product with r

   which one do we pick?
   to avoid division by 0 (picking a parallel line)
   we go over the components of r and pick the smallest one!
   then take the smallest canonical basis of that component
   that way the cross-product is maximized and far away from
   zero as we could find (in all the standard basis)
   and preform the cross-product, normalized of course.

t: we preform a cross-product between r and s t=rxs ^Rv4Nd2es

z ^k2SGY2z6

x ^6qPTR9av

y ^9BsiM0Js

r ^8QIn14i8

s ^ef6DfTQ9

t ^5SXNVg0Q

x ^CCKL63Bw

y ^11qW697Y

z ^GeDc7GDi

r ^x84eM93P

s ^BcszR6Qy

t ^2aDUbfg2

z ^amLddJwB

x ^3bHdtKEU

y ^j1EES5h8

r ^zGms4suI

s ^9PcXM7fn

t ^svhXM0LJ

rotate to the
standard axis via R ^xWzRtbDt

preform our actual
rotation around r
which is now x ^BUr7dzAH

rotate back to our
original axis via R^-1 ^WnHCr1oL

Now that we have the axis, how do we get R? ^6DN3Oi1Y

*Orthogonal matrices comply with R^-1 = R^T

for R we can write rst as row vectors
for R^-1 we can write rst as column vectors ^lwjG8G5b

%%***>>>text element-link:[[Cross-Product]]<<<***%%whats a cross-product?? ^MWlvgGJc

%%***>>>text element-link:[[Orthonormal]]<<<***%%whats orthonormal? ^AyghFyOc

why?? ^CHcCGdnn

Rotation around an arbitrary axis ^tANJDrtW

such that ^3StyNZhT

Rotation around an arbitrary point
 ^dhypH821

1. Translate to origin
2. preform rotation around arbitrary axis if needed
   if not then just rotate normally
3. Translate back to our point ^IOf9E8Wu

If Point on table in room in house in world ^yC9TCnyY

p is out point
T transforms p into table coords
R transforms table coords t into room coords
H transforms room coords r into house coords
W transforms house coords h into world coords

Our point p in world coords is:

 ^35WeuQH1

W*h = W*H*r = W*H*R*t = W*H*R*T*p ^AK2t7LvJ

Local to Global ^k8MHbT7x

Global to local
 ^8CmpyYLH

read after transformations ^iKpmbZGu

Or in a Graph: ^NxZAtSu7

Gj = L1 * L2 * ... * Lj = Gj-1 * Lj
such that
j=1 at root ^HSPhekBv

Rotation vs Orientation ^IPyk4e6J

Rotation is a rigid body transformation,
meaning its origin stays the same and it moves
around aka a motion.
it has many representations as well ^ap10iMZY

V.S ^Qy2MqKO1

Orientation is a state of being
it requires context in order to be understood
just like a point needs a coordinate system.
Orientations are results of rotations
you can always go from one orientation to another
via maximum 1 rotation!
Every orientation can be described as the rotation from
the identity to itself ^qQEQH1Np

How do we represent orientation? ^ps7TZXbN

2D ^J2WpPzYK

Each point on the circle is
an orientation, we can describe this
with the vector from the origin
to that unit circle by using the angle theta ^Icm6Ueql

X = cos
y = sin   ^fVrUqRS0

If we take another basis 90
degrees from it we can describe
those 2 basis in a rotation matrix
that translates from our original
basis (orientation) to the current
one then we represent our current 
orientation from the origin ^u61lRJiE

We can do this even better with
unit length complex numbers! ^f3ItihiJ

X = cos
y = sin   ^qqKG6rrS

x + iy = cos(a) + isin(a) = e^ia ^h8Sz2MEj

The exponential turns many different angles
to the same orientation

The inverse of this operation is the logarithm!

the logarithm will turn an orientation to many different angles ^JBonYUKz

BEST ORIENTATION REPRESENTATION ^O34mOJ01

BEST ROTATION REPRESENTATION ^js6CamVh

Connected via exponential function ^Y8EJWj9i

3D ^itTPTVLQ

How do we represent orientation? ^WLAksvX5

Usually we want to describe a vector
with an angle theta

But we can encode theta to be the length 
of the vector that way we have to keep up
with less parameters ^zUmvJV2d

||V|| = theta , V = [x,y,z] ^lClaeWhg

To describe an Orientation however we need more parameters.

e0 = cos(a/2)           [e1,e2,e3] = v * sin(a/2)
 ^P2NpMxtX

%%***>>>text element-link:[[Quarternions]]<<<***%%This is not a bad option but perhaps
an even better option, albeit less
intuitive is to use Quarternions
which are complex numbers in 3D
Please review their section before 
continuing!  ^WlNAitpa

Consider the unit sphere of quarternions in R4 ^38VwvPPA


We first consider the point as a purely imaginary quarternion
                         p = (0,x,y,z)

Then we encode our q using previous methodology
                 q = ( cos a/2 , v * sin a/2 )
                    s.t ||v||=1

                 p' = q p q^-1
 ^EUolliwC

To rotate a point P around an axis v by theta:
 ^4mqGi49E

Notice that q and -q
lead to the same orientation this is like taking
2 points on the same axis of a sphere and
gluing them together somehow
 ^FGe0TxM8

We have a 2-1 mapping from the Unit sphere
to the special orthogonal group

The special orthogonal group are the rotations.
as if we are looking at a 3x3 orthogonal matrices
and they have determinant 1, they dont change angles nor
distances

* columns and rows of matrix are
orthogonal to each other ^KOpPWJl9

BEST WAY TO REPRESENT ORIENTATION ^mQJGdI1r

BEST WAY TO
REPRESENT
ROTATION ^Ub4xaYGy

Infinitesimal Rotation! ^I09Ql5PR

We represented our orientation in 3D space as 
a unit quarternion, now we want to move from
one orientation to another! ^zTuGfZ4X

Step1: 
Move your point to the origin of the unit sphere
using q^-1
This does not affect its tangent sphere nor its
tangent vector (the amount I want to rotate) ^rq42AtUY

The exponential function takes a description
of a rotation vector in the tangent space and maps
it onto the sphere into a different orientation

vice versa, the log takes a description of an 
orientation of a sphere and produces a tangent
vector describing its rotation from the origin ^f5oN5tLP

Step 2:
We want to get out Tangent
vector, we do so by describing it
as p1 + the distance to p2
which after translating them to the
origin point is now:


v = log (q1^-1 * q2)
     ^Ted6zjKU

Step3: 
compute the following
and take the shortest path if possible ^wMWqLKKC

This allows for linear interpolation between orientation
if we multiply the logarithm with t such that it scales 
our rotation ^dTrQm2fo

Projective Transformations ^72nxFFSh

Parallel projection ^0PrghZ1C

Is a projection onto a plane namely the 
projection plane such that we turn our image
from 3D space to 2D space.



This is called a Parallel projection because all of
the rays are parallel to each other, meaning
two things that have the same size, in different
depths will still look like they're the same size


 ^TatBMUng

Primary View ^1K1QZUlc

is p orthgonal
to projection plane? ^KNfHQ4NZ

P = projection direction ^Xs8PBvIj

Yes ^ufTWwczU

Is p along one of
the standard axes? ^BfMyrrPg

We omit the axis that we want to look
along and keep the rest ^hSJyvrIG

1  0  0  0
0  1  0  0
0 0  0  1 ^sTQqUcXu

x
y
z
1 ^Eu1Okq4J

x'
y'
1 ^TkLRSoHX

Orthographic projection ^1q0rKeF1

Firstly we transform into camera space!
Then we can preform a primary view projection ^Hq0rBH1E

P ^vXpp275w

K ^QWGwdshr

P ^ntq6DQCP

This is just a change of basis aka affine transformation
Which will include translation to the center of the camera
followed up by rotation to align the axes! ^5AQ0lSQj

example of Orthographic projection ^464ryi3L

Isometric:
   * All ratios are preserved
   * All sides of a cube will project to
     the same length
   * All angles of the cube will be 120 degrees
     and thus the main axes
    
 ^Jimyd8VX

It is quite common to pick a projection direction
p = [-1,-1,-1] because its origin is the image of the 
world origin, and the up direction is [0,0,1] on Z axis ^7SOU3gv2

How to find our K matrix (example isometry) ^yE1HwXJd

1. we define our z' direction as our projection direction
2. we define our x' as the cross-product of out up
   and projection direction that way its orthogonal
   to both of them NORMALIZED!
3. we define our y' as the cross product of x' and z'
4. We write them as row vectors! ^fSJN2NSO

no ^7FsGwihU

Yes ^xcVtE0Ol

no ^GLLBItcg

Oblique projection ^9PFoyWkM

We need to shear in our camera matrix
in order to transform the projection to
a primary one ^hwiXylA5

Using spherical coordinates
we can shear the object
such that the rays are orthogonal
to our screen ^gPt5DQAM

s ^BSKdZqrw

Perspective projection ^8tlLDGc8

Is a projection onto a plane namely the 
projection plane such that we turn our image
from 3D space to 2D space.



This is called a Perspective projection due to the nature
of our eyes and seeing this perspective.
the key elements of this is that there's an eye at
a certain point x0 such that all the rays
in front of us intersect it


 ^HwjvGbMU

Key note:
Parallel projection is just
Perspective projection when
the eye is at infinity! ^PlbXiplJ

2D First ^n2L7irF7

y ^ld6KvDRI

x ^YKVwkrYv

x0 ^Yuqo4AvM

Project onto x=0 / y axis ^iNiaPAVj

y0 ^lXELDPvF

We can calculate y0
with the law of proportions ^NtlKVGtc

(x,y) ^3ED4l2cI

       y * x0
 y0 = _____
       x + x0 ^rN4IljCC

How can we make
this look logical?
using homogeneous
coordinates ofc! ^I2YBTgIS

Defined in 4x4 matrices, Projective transformations
are transformations that deal with points in R3
using homogeneous coordinates
 ^Wb0sNIAe

Two transformation matrices are
the same if theyre scalar products
of each other ^2V4coVXE

Projective transformations are affine transformations
that can deal with points at infinity! 
Previously we could not map points from infinity to a finite
point and vice versa.... WELL NOW WE CAN! ^LZq4OgM1

P!=0 ^7KhIBRFV

From ^Y1ksmA1p

To ^bBWLeA7f

+ ^h3Pnn1Cw

Primary view
Parallel projection
over x ^06TNkd8p

Then in 3D ^yEjmOZys

Now that we understand how to make
Perspective projection and thats its
composed of the Parallel projection part
plus the perspective transformation part
we can write down and analyze its properties in 3D! ^E0QbqmGf

We can see as we go to infinity
with our eye we turn it into a 
parallel projection! ^xplCUUwb

1. Points on the projection screen stay on the projection screen
This is quite intuitive and doesnt need any explanation ^pZ15tj5D

2. Lines Parallel to the projection screen stay Parallel
but are moved around ^gHs0vV6q

3. Points that are on the eye line go to infinity aka behind us
alongside the eye or points where the center of the eye is ^50vhWbyN

4. Straight lines stay Straight lines ^Q771drwG

5. Lines that go through the eye are actually Parallel to the x axis
because the eye goes to infinity and thus it straightens up to
a line that is parallel ^FMJVIGx6

6. Infinity points map to a new finite point where all parallel lines intersect
at the end of the horizon called the vanishing line!  ^RukZjSNL

The vanishing point is the point at the same distance from
the projection screen as the eye is, which is where all
lines that are parallel to that screen intersect ^xZgolPj9

Canonical View Volume ^k6Jfr6sE

We always assume our cannonical view volume is the box [-1,1]^3 ^BzFnCZSl

For Orthographic cameras ^RAHtshuW

Our view volume is already a box!
we just need to center it, scale it down
and rotate it to align the axes if needed ^7IUlVtQS

For perspective cameras ^EauuioT2

We use our perspective transformation
that turns our frustum into a box!
and then preform the same actions as
the orthographic cameras ^nLYV5HV2

We want to map our current view volume described
by out camera's limitations to the canonical view volume
in order to project it and clip it! ^XsswdOKx

We first specify our near and far plane
by specifying the Z (because z is usually
our direction where we look) and we need to map
then to 1 and -1  ^vspXJpcU

Using n,f values alongside
distance t,b,l,r ^N0VCBWTg

Transforming from local coords to screen ^ozUYBdKv

2d Screen    Canonical View      Camera     World      Local
   Space         Space            Space     Space     Space ^QNI3CCmD

Tp ^M4crVMnY

P ^L59V466B

K ^y3gYN24c

K ^eCLwJ0N0

P ^6E76urkM

Tp ^JO6vUDdO

W ^N0D7er9e

W ^3hmnmxlW

Turning an object described in
local coords into World coords
by doing a composite Affine
Transformation compromised from
Rotation around arbitrary point
and other affine transformations ^fwN6mmng

Turning world Coords into Camera space
by switching basis from the canonical ones
into the ViewDir, Up and right of the camera
making all points in space be referenced
from the view of the camera ^ANBGHCKh

Perspective transformation of turning
parallel lines into lines that intersect
at a finite point to add the perspective
PLUS some extra calculations to turn
our view box into the canonical one
by translating it and scaling it and
rotating it ^3bjiABhC

We project Our cannonical view space 
into 2d by removing one of the viewing
axes and turning the coords in the geometry
into 2d coords on a screen ^cTpGZpqr

[[Subspaces]] ^iDfXTaAH

[[Subspaces]] ^Q9UofkTN

[[Subspaces]] ^5qzql3zp

[[Subspaces]] ^XXqDLL9d


# Embedded files
56e1fbe897520c33ca3187123ef815a8378b6a99: $$	\begin{bmatrix} 
	a & b & c \\
	c & d & d\\
	e & f & g \\
	\end{bmatrix}$$
b0f289b6a6940e6c74e91025eddcab2517b18f90: $$R_\mathcal{x}(a) = 
	\begin{bmatrix} 
	1 & 0 & 0 \\
	0 & cos(a) & -sin(a)\\
	0 & sin(a) & cos(a) \\
	\end{bmatrix}$$
01d52910c5c0f8ff24dcaf4ff2bcc516fefbc10f: $$R_\mathcal{y}(a) = 
	\begin{bmatrix} 
	cos(a) & 0 & sin(a) \\
	0 & 1 & 0 \\
	-sin(a) & 0 & cos(a) \\
	\end{bmatrix}$$
024eefd71a9227fa8e33bf6e93c24df21f8575ba: $$R_\mathcal{z}(a) = 
	\begin{bmatrix} 
	cos(a) & -sin(a) & 0 \\
	sin(a) & cos(a) & 0 \\
	0 & 0 & 1 \\
	\end{bmatrix}$$
adfea0d5d4680e27ceb330d823a412431c625821: $$	\begin{bmatrix} 
	L & T \\
	p^T & 1 \\
	\end{bmatrix}$$
74f1cf0680639b42bfe0a955a59434ae417f7148: [[Pasted Image 20231216102725_920.png]]
1003521ff939ff225915b417a750d9ade73b85e4: [[Pasted Image 20231216103037_946.png]]
bdd68025d3241513e368acc295153967f492a603: [[Pasted Image 20231216104011_588.png]]
0412cff84722d3bec408300bd5cb6e16fac4787d: [[Pasted Image 20231216172931_509.png]]
5fd039a40b016c84faef9326546ffbbf26866f7b: [[Pasted Image 20231216173516_585.png]]
e50699b61629977a96f2bdc460c57c21f84f8dd3: [[Pasted Image 20231216175550_782.png]]
990e347ab0ab4c2f1fa4afcca6083e366323adff: [[Pasted Image 20231216175635_796.png]]
420b4003007dcbaf2170f78b6d75c267f87ce4f7: [[Pasted Image 20231216180104_826.png]]
820bd1d1eb0398066a9e9b53bddc2abebf424a25: [[Pasted Image 20231216180134_839.png]]
8639316851ba35be5f0fb8797029cbd3ccdcee70: [[Pasted Image 20231216180504_849.png]]
52ca1b972c1374069e9d871dc4006eebbd29c047: [[Pasted Image 20231216180905_901.png]]
2e077ab36bb4f1220f347792d6f486ab76edbfc4: [[Pasted Image 20231216194806_649.png]]
c56a2f031a7ede8cd268b8dea77b33fd2fc51896: [[Pasted Image 20231216202906_349.png]]
bf596258a73f2b95ad7f91017045ba3b07468507: [[Pasted Image 20231216202951_368.png]]
cdac767cff891d74e7a727d5fc71eb0d0444244b: [[Pasted Image 20231216203208_398.png]]
58a49ff8b3198fbb445d5d0f765356c4c297a555: [[Pasted Image 20231216203805_485.png]]
ffc6bcdbba6cdabf9746692342da6a61409dde32: [[Pasted Image 20231216215545_928.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.3",
	"elements": [
		{
			"type": "rectangle",
			"version": 231,
			"versionNonce": 223277451,
			"isDeleted": false,
			"id": "l1xm4WoE3dQLdqoGtS0J4",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -539.5731728295202,
			"y": 2883.949119812834,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#d0bfff",
			"width": 1268.3333333333333,
			"height": 815,
			"seed": 1842145125,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "BBEGJCXzZwMim1GL2MZh3",
					"type": "arrow"
				},
				{
					"id": "3PYD6sw3NdcRk0ldAdyVP",
					"type": "arrow"
				},
				{
					"id": "rnukGoBeIddhnPdAqnBqf",
					"type": "arrow"
				},
				{
					"id": "S31y0Gd0SnWShYRqMqc6E",
					"type": "arrow"
				}
			],
			"updated": 1702760833697,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 728,
			"versionNonce": 1409110283,
			"isDeleted": false,
			"id": "milxS8KS--39lXDc3MqBB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -335.2536445259308,
			"y": 1807.0789616699772,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 270.5213688047804,
			"height": 205.56654534575983,
			"seed": 1810117835,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "P1FrDQhbJLGTPZ2Ih3peG",
					"type": "arrow"
				},
				{
					"id": "Kjm1S5gb3dtkYe17yGuj6",
					"type": "arrow"
				},
				{
					"id": "ayp9K0VF6J42WHGxd2KmX",
					"type": "arrow"
				},
				{
					"id": "QVbjWhULnRRs7J8zBfOc7",
					"type": "arrow"
				},
				{
					"id": "3PYD6sw3NdcRk0ldAdyVP",
					"type": "arrow"
				}
			],
			"updated": 1702760726441,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 367,
			"versionNonce": 1912887589,
			"isDeleted": false,
			"id": "xLSQjpXmifRsEmMdeoh8r",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 800.1753054577264,
			"y": 2861.0117123977006,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 1457.888762981807,
			"height": 1117.7147182860522,
			"seed": 889168069,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1702760726441,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 173,
			"versionNonce": 1642395563,
			"isDeleted": false,
			"id": "EzP03LiQWtu4Yq-WKSthL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3026.7952800552684,
			"y": 1406.1650278505113,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 236.65068137381468,
			"height": 227.15010657413586,
			"seed": 1894311627,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "0bBwvV4mDvPxrEn-jGCHv",
					"type": "arrow"
				}
			],
			"updated": 1702760726441,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 689,
			"versionNonce": 1917664042,
			"isDeleted": false,
			"id": "iDfXTaAH",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -128.9314797996804,
			"y": 820.7691320196353,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 387.20294960499893,
			"height": 191.48329674120305,
			"seed": 1558155723,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "WKvV5NchnfD0fO2xeb5_6",
					"type": "arrow"
				},
				{
					"id": "_mJx42VVx5762e0vd2fy6",
					"type": "arrow"
				},
				{
					"id": "m5dOeP9pSssSez89Yfzb5",
					"type": "arrow"
				},
				{
					"id": "08MC8vK6HzoUH9lqrBRk0",
					"type": "arrow"
				},
				{
					"id": "GxWkBi4wjsG2uLJbvOclH",
					"type": "arrow"
				},
				{
					"id": "kRXxgchF7_0tSG5dvTZvu",
					"type": "arrow"
				}
			],
			"updated": 1702813780271,
			"link": "[[Subspaces]]",
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 613,
			"versionNonce": 1356690901,
			"isDeleted": false,
			"id": "qyPOCIZmYEwHE1yxD-Rev",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -631.2170697121364,
			"y": -612.1305718431349,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1202.4285714285716,
			"height": 319.57142857142867,
			"seed": 1655215725,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "dh18yBga"
				}
			],
			"updated": 1702995847203,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 562,
			"versionNonce": 767161141,
			"isDeleted": false,
			"id": "dh18yBga",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -142.53194599569554,
			"y": -469.8304196655854,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 224.81292724609375,
			"height": 35,
			"seed": 722573475,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702995847203,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Transformations",
			"rawText": "Transformations",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "qyPOCIZmYEwHE1yxD-Rev",
			"originalText": "Transformations",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 309,
			"versionNonce": 457525483,
			"isDeleted": false,
			"id": "K9cGYJRe",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -758,
			"y": -221,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 258.5531005859375,
			"height": 35,
			"seed": 538505869,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726441,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is Geometry?",
			"rawText": "What is Geometry?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is Geometry?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 503,
			"versionNonce": 490753861,
			"isDeleted": false,
			"id": "p5vbGDZB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -758,
			"y": -185,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 414.0395202636719,
			"height": 75,
			"seed": 407248035,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "9v-iQg6aFGMGD0ry4zUin",
					"type": "arrow"
				}
			],
			"updated": 1702760726441,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Points, Lines, Solid Geometric shapes\nbut more often than not, triangles!\nor something composed of many triangles...",
			"rawText": "Points, Lines, Solid Geometric shapes\nbut more often than not, triangles!\nor something composed of many triangles...",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Points, Lines, Solid Geometric shapes\nbut more often than not, triangles!\nor something composed of many triangles...",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 559,
			"versionNonce": 287503243,
			"isDeleted": false,
			"id": "QQuKUFBM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -240,
			"y": -242,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 372.97955322265625,
			"height": 125,
			"seed": 1507779235,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "9v-iQg6aFGMGD0ry4zUin",
					"type": "arrow"
				}
			],
			"updated": 1702760726441,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "\n. Efficient computations and rendering\n. basic shape\n. Can form many shapes\n. Easy to store",
			"rawText": "\n. Efficient computations and rendering\n. basic shape\n. Can form many shapes\n. Easy to store",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "\n. Efficient computations and rendering\n. basic shape\n. Can form many shapes\n. Easy to store",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "text",
			"version": 502,
			"versionNonce": 1029709477,
			"isDeleted": false,
			"id": "dqLByBwu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -235,
			"y": -112.5,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 545.6810913085938,
			"height": 20,
			"seed": 1809048877,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726441,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Store vertex coordinates -> store triangles as 3 indices of vertices",
			"rawText": "Store vertex coordinates -> store triangles as 3 indices of vertices",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Store vertex coordinates -> store triangles as 3 indices of vertices",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 277,
			"versionNonce": 1597131307,
			"isDeleted": false,
			"id": "9v-iQg6aFGMGD0ry4zUin",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -327.99999999999994,
			"y": -161,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 71.99999999999994,
			"height": 1,
			"seed": 245722381,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702760726441,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "p5vbGDZB",
				"focus": -0.2576589847802986,
				"gap": 15.960479736328125
			},
			"endBinding": {
				"elementId": "QQuKUFBM",
				"focus": -0.225650811971541,
				"gap": 16
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
					71.99999999999994,
					-1
				]
			]
		},
		{
			"type": "arrow",
			"version": 372,
			"versionNonce": 462356997,
			"isDeleted": false,
			"id": "Kxw7h_WZWa4Y-bBX-nxJh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 309.2561749365181,
			"y": -160.74735065779,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 72,
			"height": 1,
			"seed": 1556612259,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702760726441,
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
					72,
					-1
				]
			]
		},
		{
			"type": "text",
			"version": 273,
			"versionNonce": 1784532171,
			"isDeleted": false,
			"id": "yiRfgbX9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -235,
			"y": -256,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 192.55679321289062,
			"height": 35,
			"seed": 1255588291,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726441,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Why triangles?",
			"rawText": "Why triangles?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Why triangles?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 381,
			"versionNonce": 1288337765,
			"isDeleted": false,
			"id": "sId0zKic",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 422,
			"y": -244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 425.60186767578125,
			"height": 35,
			"seed": 1857977229,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726441,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "How to reference in the scene?",
			"rawText": "How to reference in the scene?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How to reference in the scene?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 584,
			"versionNonce": 373291883,
			"isDeleted": false,
			"id": "VrFiKz5i",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 414,
			"y": -197,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 569.8992919921875,
			"height": 100,
			"seed": 1968823405,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726441,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Objects are stored in the scene local to their ecosystem\n    . If teapot on table -> teapot's world is the table\nthat way small ecosystems are attached to each other\nand can detect changes in one another. ",
			"rawText": "Objects are stored in the scene local to their ecosystem\n    . If teapot on table -> teapot's world is the table\nthat way small ecosystems are attached to each other\nand can detect changes in one another. ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Objects are stored in the scene local to their ecosystem\n    . If teapot on table -> teapot's world is the table\nthat way small ecosystems are attached to each other\nand can detect changes in one another. ",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "ellipse",
			"version": 540,
			"versionNonce": 1784677573,
			"isDeleted": false,
			"id": "Mb19cauT1lXSa87jjqcHz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -752.1880341880338,
			"y": 61.34188034188048,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 387.179487179487,
			"height": 401.025641025641,
			"seed": 607203,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "DWvfEkuy"
				},
				{
					"id": "1lDU55Y3he0IJ5rliyz8G",
					"type": "arrow"
				},
				{
					"id": "1K5pdzJR8SBMFFQCsADaO",
					"type": "arrow"
				}
			],
			"updated": 1702760726441,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 578,
			"versionNonce": 1864586763,
			"isDeleted": false,
			"id": "DWvfEkuy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -684.8289597037825,
			"y": 194.57072575524452,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 252.68409729003906,
			"height": 135,
			"seed": 875144643,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726441,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Protective\nTransformatio\nns",
			"rawText": "Protective Transformations",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Mb19cauT1lXSa87jjqcHz",
			"originalText": "Protective Transformations",
			"lineHeight": 1.25,
			"baseline": 122
		},
		{
			"type": "ellipse",
			"version": 991,
			"versionNonce": 132981797,
			"isDeleted": false,
			"id": "N5kfUjMxrLrOI-DuLdj9K",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -114.34161364445174,
			"y": 98.95182203185914,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 339.8600575519579,
			"height": 290.85949425624324,
			"seed": 1202879085,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "885TJtcd"
				},
				{
					"id": "1lDU55Y3he0IJ5rliyz8G",
					"type": "arrow"
				},
				{
					"id": "ty8Yo_-5S_oMuYzl7q6Ea",
					"type": "arrow"
				}
			],
			"updated": 1702760726441,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 896,
			"versionNonce": 335699115,
			"isDeleted": false,
			"id": "885TJtcd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -56.97672416623955,
			"y": 209.54720877944112,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 224.81292724609375,
			"height": 70,
			"seed": 1099129677,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726441,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Affine\nTransformations",
			"rawText": "Affine Transformations",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "N5kfUjMxrLrOI-DuLdj9K",
			"originalText": "Affine Transformations",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "ellipse",
			"version": 849,
			"versionNonce": 1836913115,
			"isDeleted": false,
			"id": "FsIf1pbSBkEiTP0PpjiaC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 469.78404048913086,
			"y": 322.39735505725605,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 243.53054816392012,
			"height": 218.2004754801679,
			"seed": 898582595,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "FnsWsTks"
				},
				{
					"id": "kAFQZ4v1_-klO7lK6ipba",
					"type": "arrow"
				},
				{
					"id": "1qPkV-4anvnRly9SUGNVh",
					"type": "arrow"
				},
				{
					"id": "BeG12LlljrdmLA3OWJfrL",
					"type": "arrow"
				},
				{
					"id": "2yCi7qKzOZaXKm_t6nJzt",
					"type": "arrow"
				}
			],
			"updated": 1702995800935,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 799,
			"versionNonce": 1802154395,
			"isDeleted": false,
			"id": "FnsWsTks",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 511.1583541919054,
			"y": 406.35207486226216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 160.57981872558594,
			"height": 50,
			"seed": 558296835,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702995800935,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Linear\nTransformations",
			"rawText": "Linear Transformations",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "FsIf1pbSBkEiTP0PpjiaC",
			"originalText": "Linear Transformations",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 1165,
			"versionNonce": 554660859,
			"isDeleted": false,
			"id": "1lDU55Y3he0IJ5rliyz8G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -358.6561455750095,
			"y": 254.5054721696559,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 235.8631631996844,
			"height": 0.41446203959174,
			"seed": 1190220973,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702995800934,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Mb19cauT1lXSa87jjqcHz",
				"gap": 6.478544754082492,
				"focus": -0.03840432102435988
			},
			"endBinding": {
				"elementId": "N5kfUjMxrLrOI-DuLdj9K",
				"gap": 8.8688765202796,
				"focus": -0.07461882227145628
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
					235.8631631996844,
					0.41446203959174
				]
			]
		},
		{
			"type": "arrow",
			"version": 973,
			"versionNonce": 223616635,
			"isDeleted": false,
			"id": "kAFQZ4v1_-klO7lK6ipba",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 224.4362580159854,
			"y": 241.44841148931602,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 244.48405932553965,
			"height": 213.89758669330462,
			"seed": 2064825347,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702995800935,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "FsIf1pbSBkEiTP0PpjiaC",
				"gap": 3.699873972031611,
				"focus": -0.330214752864965
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
					93.16531498457977,
					26.453869164011735
				],
				[
					110.0883919076569,
					200.30002301016555
				],
				[
					244.48405932553965,
					213.89758669330462
				]
			]
		},
		{
			"type": "arrow",
			"version": 611,
			"versionNonce": 2134460123,
			"isDeleted": false,
			"id": "COK22VMIOZlgSnEMtlkka",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 223.75541915441158,
			"y": 241.74843449948162,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 231.05151886717897,
			"height": 197.86163002947978,
			"seed": 132368781,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702995800936,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "rs36NiUl2gpMOu1ZeOZms",
				"gap": 7.5104734847174655,
				"focus": 0.04181438043755942
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
					92.30769230769215,
					-21.538461538461547
				],
				[
					98.46153846153834,
					-184.61538461538464
				],
				[
					231.05151886717897,
					-197.86163002947978
				]
			]
		},
		{
			"type": "ellipse",
			"version": 840,
			"versionNonce": 66569787,
			"isDeleted": false,
			"id": "rs36NiUl2gpMOu1ZeOZms",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 461.9901450724515,
			"y": -73.50564939444848,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 243.53054816392012,
			"height": 218.2004754801679,
			"seed": 1398863363,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "VCc77dbc"
				},
				{
					"id": "COK22VMIOZlgSnEMtlkka",
					"type": "arrow"
				},
				{
					"id": "8iXEFhCNXXKE4Ku-CBMAZ",
					"type": "arrow"
				}
			],
			"updated": 1702995800936,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 803,
			"versionNonce": 2103529659,
			"isDeleted": false,
			"id": "VCc77dbc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 503.36445877522607,
			"y": 10.44907041055761,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 160.57981872558594,
			"height": 50,
			"seed": 142163363,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702995800936,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Non-Linear\nTransformations",
			"rawText": "Non-Linear Transformations",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "rs36NiUl2gpMOu1ZeOZms",
			"originalText": "Non-Linear Transformations",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 1472,
			"versionNonce": 1104383003,
			"isDeleted": false,
			"id": "8iXEFhCNXXKE4Ku-CBMAZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 710.4750649476673,
			"y": 35.70513770029838,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 285.3748180192597,
			"height": 2.896014906921941,
			"seed": 1071259747,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702995800936,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "rs36NiUl2gpMOu1ZeOZms",
				"gap": 4.954431236452351,
				"focus": -0.010773029721865317
			},
			"endBinding": {
				"elementId": "Be4cCZ6aXUI4115e3trs_",
				"gap": 10.701913911133204,
				"focus": 0.1511790331599008
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
					285.3748180192597,
					2.896014906921941
				]
			]
		},
		{
			"type": "rectangle",
			"version": 742,
			"versionNonce": 1335422213,
			"isDeleted": false,
			"id": "Be4cCZ6aXUI4115e3trs_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1006.5517968780601,
			"y": -49.83594513203596,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 359.203940798982,
			"height": 213.5759316505192,
			"seed": 842856973,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "8iXEFhCNXXKE4Ku-CBMAZ",
					"type": "arrow"
				}
			],
			"updated": 1702760726442,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 475,
			"versionNonce": 1148981707,
			"isDeleted": false,
			"id": "r8Ve8AtG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1114.590281012912,
			"y": -38.113507644096245,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 166.8402862548828,
			"height": 28.33718561258228,
			"seed": 777022659,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"fontSize": 22.669748490065825,
			"fontFamily": 1,
			"text": "TRANSLATION",
			"rawText": "TRANSLATION",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "TRANSLATION",
			"lineHeight": 1.25,
			"baseline": 20
		},
		{
			"type": "freedraw",
			"version": 419,
			"versionNonce": 1583285349,
			"isDeleted": false,
			"id": "-J2GN10KAlEjk7Z95ZuAM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1036.551740743195,
			"y": 11.740148128587975,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffd43b",
			"width": 6.061377022725105,
			"height": 8.182858980678839,
			"seed": 526860803,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.30306885113625165
				],
				[
					-0.30306885113616217,
					0
				],
				[
					-0.6061377022724674,
					0
				],
				[
					-0.6061377022724674,
					-0.6061377022725033
				],
				[
					-0.30306885113616217,
					-1.2122754045450155
				],
				[
					0,
					-1.2122754045450155
				],
				[
					0.30306885113630533,
					-1.515344255681267
				],
				[
					0.6061377022726107,
					-1.8184131068175187
				],
				[
					0.9092065534087728,
					-1.8184131068175187
				],
				[
					1.8184131068175455,
					-1.8184131068175187
				],
				[
					2.424550809090013,
					-1.2122754045450155
				],
				[
					3.030688511362624,
					-0.9092065534087549
				],
				[
					3.333757362498786,
					-0.30306885113625165
				],
				[
					3.636826213635091,
					0
				],
				[
					3.636826213635091,
					0.30306885113625165
				],
				[
					3.636826213635091,
					0.9092065534087549
				],
				[
					3.333757362498786,
					1.515344255681267
				],
				[
					2.424550809090013,
					1.515344255681267
				],
				[
					1.8184131068175455,
					1.515344255681267
				],
				[
					1.212275404545078,
					1.8184131068175187
				],
				[
					0.9092065534087728,
					1.8184131068175187
				],
				[
					0.30306885113630533,
					1.8184131068175187
				],
				[
					0,
					1.515344255681267
				],
				[
					-0.6061377022724674,
					1.2122754045450155
				],
				[
					-0.9092065534086297,
					0.6061377022725033
				],
				[
					-1.2122754045449349,
					0
				],
				[
					-1.2122754045449349,
					-0.9092065534087549
				],
				[
					-1.2122754045449349,
					-1.515344255681267
				],
				[
					-1.2122754045449349,
					-2.1214819579537703
				],
				[
					-1.2122754045449349,
					-2.424550809090022
				],
				[
					-0.6061377022724674,
					-2.7276196602262734
				],
				[
					-0.30306885113616217,
					-2.7276196602262734
				],
				[
					0.30306885113630533,
					-2.7276196602262734
				],
				[
					0.9092065534087728,
					-2.7276196602262734
				],
				[
					1.8184131068175455,
					-2.7276196602262734
				],
				[
					2.121481957953851,
					-2.424550809090022
				],
				[
					2.424550809090013,
					-1.515344255681267
				],
				[
					2.7276196602263183,
					-0.6061377022725033
				],
				[
					2.7276196602263183,
					0.6061377022725033
				],
				[
					2.424550809090013,
					1.515344255681267
				],
				[
					1.8184131068175455,
					3.030688511362534
				],
				[
					1.212275404545078,
					3.939895064771289
				],
				[
					0.30306885113630533,
					4.849101618180053
				],
				[
					-0.30306885113616217,
					5.152170469316305
				],
				[
					-0.9092065534086297,
					5.152170469316305
				],
				[
					-1.2122754045449349,
					5.152170469316305
				],
				[
					-1.5153442556812402,
					4.546032767043792
				],
				[
					-1.8184131068174023,
					3.939895064771289
				],
				[
					-2.424550809090013,
					2.7276196602262734
				],
				[
					-2.424550809090013,
					1.8184131068175187
				],
				[
					-2.424550809090013,
					1.2122754045450155
				],
				[
					-2.424550809090013,
					0
				],
				[
					-2.1214819579537076,
					-1.2122754045450155
				],
				[
					-1.8184131068174023,
					-1.8184131068175187
				],
				[
					-1.2122754045449349,
					-2.7276196602262734
				],
				[
					-0.6061377022724674,
					-3.030688511362534
				],
				[
					0,
					-3.030688511362534
				],
				[
					0.30306885113630533,
					-3.030688511362534
				],
				[
					1.212275404545078,
					-2.7276196602262734
				],
				[
					1.8184131068175455,
					-1.8184131068175187
				],
				[
					1.8184131068175455,
					-1.2122754045450155
				],
				[
					2.121481957953851,
					-0.30306885113625165
				],
				[
					2.121481957953851,
					0.6061377022725033
				],
				[
					2.121481957953851,
					1.2122754045450155
				],
				[
					2.121481957953851,
					1.515344255681267
				],
				[
					1.5153442556812402,
					1.8184131068175187
				],
				[
					1.212275404545078,
					1.8184131068175187
				],
				[
					0.9092065534087728,
					1.8184131068175187
				],
				[
					0.6061377022726107,
					1.8184131068175187
				],
				[
					0.6061377022726107,
					1.515344255681267
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
			"type": "freedraw",
			"version": 412,
			"versionNonce": 2119016555,
			"isDeleted": false,
			"id": "IHqkCL4Clxul1kOYPBlJj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1051.099045597735,
			"y": 11.134010426315484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 53.94625550225304,
			"height": 1.515344255681267,
			"seed": 461394403,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.30306885113616217,
					0
				],
				[
					0.6061377022724674,
					0
				],
				[
					1.5153442556812402,
					0
				],
				[
					2.424550809090013,
					0
				],
				[
					3.333757362498786,
					0
				],
				[
					4.849101618180026,
					0
				],
				[
					5.758308171588799,
					0
				],
				[
					7.273652427270039,
					0
				],
				[
					8.485927831815117,
					0
				],
				[
					9.39513438522389,
					0
				],
				[
					10.304340938632519,
					0
				],
				[
					11.516616343177597,
					0
				],
				[
					12.425822896586372,
					0
				],
				[
					13.638098301131306,
					0.30306885113625165
				],
				[
					14.850373705676384,
					0.30306885113625165
				],
				[
					15.759580259085157,
					0.30306885113625165
				],
				[
					16.97185566363009,
					0.30306885113625165
				],
				[
					17.881062217038863,
					0.30306885113625165
				],
				[
					18.790268770447636,
					0.30306885113625165
				],
				[
					19.69947532385641,
					0.30306885113625165
				],
				[
					20.608681877265184,
					0
				],
				[
					22.124026132946423,
					0
				],
				[
					23.3363015374915,
					0
				],
				[
					24.851645793172743,
					-0.6061377022725122
				],
				[
					26.36699004885398,
					-0.6061377022725122
				],
				[
					28.185403155671526,
					-0.9092065534087639
				],
				[
					29.397678560216463,
					-0.9092065534087639
				],
				[
					31.216091667034007,
					-1.2122754045450155
				],
				[
					32.42836707157909,
					-1.2122754045450155
				],
				[
					33.64064247612402,
					-1.2122754045450155
				],
				[
					34.246780178396634,
					-1.2122754045450155
				],
				[
					34.8529178806691,
					-1.2122754045450155
				],
				[
					35.76212443407787,
					-1.2122754045450155
				],
				[
					36.97439983862281,
					-1.2122754045450155
				],
				[
					37.58053754089527,
					-1.2122754045450155
				],
				[
					38.18667524316788,
					-1.2122754045450155
				],
				[
					39.095881796576656,
					-1.2122754045450155
				],
				[
					39.702019498849126,
					-1.2122754045450155
				],
				[
					40.9142949033942,
					-1.2122754045450155
				],
				[
					41.52043260566667,
					-1.2122754045450155
				],
				[
					42.42963915907544,
					-1.2122754045450155
				],
				[
					43.03577686134791,
					-1.2122754045450155
				],
				[
					43.641914563620375,
					-1.2122754045450155
				],
				[
					44.248052265892845,
					-1.2122754045450155
				],
				[
					44.551121117029155,
					-1.2122754045450155
				],
				[
					44.85418996816546,
					-0.9092065534087639
				],
				[
					45.46032767043793,
					-0.9092065534087639
				],
				[
					46.06646537271039,
					-0.9092065534087639
				],
				[
					46.3695342238467,
					-0.9092065534087639
				],
				[
					46.672603074983,
					-0.6061377022725122
				],
				[
					47.27874077725547,
					-0.6061377022725122
				],
				[
					47.884878479527934,
					-0.30306885113625165
				],
				[
					48.187947330664244,
					-0.30306885113625165
				],
				[
					49.097153884073016,
					-0.30306885113625165
				],
				[
					49.703291586345486,
					-0.30306885113625165
				],
				[
					50.30942928861795,
					-0.30306885113625165
				],
				[
					50.61249813975426,
					-0.30306885113625165
				],
				[
					51.52170469316303,
					-0.30306885113625165
				],
				[
					51.82477354429919,
					-0.30306885113625165
				],
				[
					52.4309112465718,
					-0.30306885113625165
				],
				[
					52.73398009770796,
					-0.30306885113625165
				],
				[
					53.340117799980575,
					-0.30306885113625165
				],
				[
					53.643186651116736,
					-0.30306885113625165
				],
				[
					53.94625550225304,
					-0.30306885113625165
				],
				[
					53.94625550225304,
					-0.30306885113625165
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 388,
			"versionNonce": 254488517,
			"isDeleted": false,
			"id": "lLuwQwg5IDwnDAdLYC-hX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1105.3483699511244,
			"y": 0.8296694876828496,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 13.031960598858982,
			"height": 17.577993365902675,
			"seed": 1679769795,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.3030688511362606
				],
				[
					0,
					0.6061377022725122
				],
				[
					0,
					1.2122754045450155
				],
				[
					0,
					1.8184131068175187
				],
				[
					0.30306885113630533,
					2.121481957953779
				],
				[
					0.9092065534087728,
					3.030688511362534
				],
				[
					1.5153442556813834,
					3.939895064771289
				],
				[
					2.424550809090013,
					4.849101618180053
				],
				[
					3.030688511362624,
					5.758308171588808
				],
				[
					3.333757362498786,
					6.061377022725068
				],
				[
					3.9398950647713966,
					6.970583576133824
				],
				[
					4.849101618180169,
					7.5767212784063265
				],
				[
					6.061377022725105,
					8.48592783181509
				],
				[
					6.667514724997715,
					8.788996682951343
				],
				[
					7.273652427270182,
					9.395134385223846
				],
				[
					8.182858980678812,
					10.001272087496357
				],
				[
					8.788996682951423,
					10.60740978976886
				],
				[
					9.698203236360195,
					11.516616343177615
				],
				[
					10.304340938632663,
					12.122754045450128
				],
				[
					10.304340938632663,
					12.728891747722631
				],
				[
					10.607409789768969,
					13.031960598858882
				],
				[
					10.607409789768969,
					13.335029449995135
				],
				[
					10.001272087496357,
					13.638098301131386
				],
				[
					8.788996682951423,
					14.244236003403898
				],
				[
					6.970583576133877,
					14.54730485454015
				],
				[
					5.1521704693163315,
					14.850373705676402
				],
				[
					3.030688511362624,
					15.456511407948906
				],
				[
					1.8184131068175455,
					15.759580259085165
				],
				[
					0.30306885113630533,
					16.062649110221418
				],
				[
					-0.30306885113616217,
					16.062649110221418
				],
				[
					-1.2122754045449349,
					16.365717961357667
				],
				[
					-1.5153442556812402,
					16.365717961357667
				],
				[
					-1.8184131068174023,
					16.66878681249392
				],
				[
					-2.1214819579537076,
					16.66878681249392
				],
				[
					-2.1214819579537076,
					16.971855663630173
				],
				[
					-2.424550809090013,
					16.971855663630173
				],
				[
					-2.424550809090013,
					17.274924514766425
				],
				[
					-2.424550809090013,
					17.577993365902675
				],
				[
					-2.1214819579537076,
					17.577993365902675
				],
				[
					-2.1214819579537076,
					17.577993365902675
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 464,
			"versionNonce": 808737547,
			"isDeleted": false,
			"id": "aGToXvzPXBz_oUU-AW-zw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1126.5631895306622,
			"y": 15.073905491086776,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffd43b",
			"width": 11.213547492041435,
			"height": 8.788996682951334,
			"seed": 1352374445,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.30306885113630533,
					-0.30306885113625165
				],
				[
					-0.30306885113630533,
					-0.6061377022725122
				],
				[
					-0.30306885113630533,
					-1.2122754045450155
				],
				[
					0,
					-1.515344255681267
				],
				[
					0.30306885113616217,
					-1.8184131068175187
				],
				[
					1.2122754045449349,
					-1.8184131068175187
				],
				[
					1.8184131068175455,
					-1.8184131068175187
				],
				[
					2.1214819579537076,
					-1.8184131068175187
				],
				[
					2.424550809090013,
					-1.8184131068175187
				],
				[
					3.0306885113624804,
					-1.8184131068175187
				],
				[
					3.333757362498786,
					-1.2122754045450155
				],
				[
					3.636826213635091,
					-0.30306885113625165
				],
				[
					3.636826213635091,
					0
				],
				[
					3.333757362498786,
					0.6061377022725033
				],
				[
					2.424550809090013,
					1.2122754045450066
				],
				[
					1.8184131068175455,
					1.2122754045450066
				],
				[
					1.2122754045449349,
					1.2122754045450066
				],
				[
					0.9092065534087728,
					1.2122754045450066
				],
				[
					0.30306885113616217,
					0.6061377022725033
				],
				[
					0,
					0
				],
				[
					-0.30306885113630533,
					-0.6061377022725122
				],
				[
					-0.30306885113630533,
					-1.515344255681267
				],
				[
					-0.30306885113630533,
					-1.8184131068175187
				],
				[
					-0.30306885113630533,
					-2.424550809090031
				],
				[
					-0.30306885113630533,
					-2.7276196602262828
				],
				[
					0,
					-3.333757362498786
				],
				[
					1.2122754045449349,
					-3.6368262136350373
				],
				[
					2.1214819579537076,
					-3.6368262136350373
				],
				[
					3.0306885113624804,
					-3.6368262136350373
				],
				[
					3.636826213635091,
					-3.6368262136350373
				],
				[
					4.54603276704372,
					-3.6368262136350373
				],
				[
					4.849101618180026,
					-3.333757362498786
				],
				[
					5.1521704693163315,
					-3.030688511362534
				],
				[
					5.455239320452494,
					-2.7276196602262828
				],
				[
					5.455239320452494,
					-2.1214819579537703
				],
				[
					5.455239320452494,
					-1.2122754045450155
				],
				[
					5.1521704693163315,
					-0.9092065534087639
				],
				[
					4.242963915907558,
					0
				],
				[
					3.939895064771253,
					0
				],
				[
					3.333757362498786,
					0.30306885113625165
				],
				[
					2.7276196602263183,
					0.30306885113625165
				],
				[
					0.6061377022724674,
					-0.6061377022725122
				],
				[
					0,
					-1.2122754045450155
				],
				[
					-0.9092065534087728,
					-2.1214819579537703
				],
				[
					-1.212275404545078,
					-2.7276196602262828
				],
				[
					-1.212275404545078,
					-3.333757362498786
				],
				[
					-0.9092065534087728,
					-3.939895064771289
				],
				[
					-0.6061377022726107,
					-4.546032767043801
				],
				[
					0.30306885113616217,
					-5.152170469316305
				],
				[
					1.2122754045449349,
					-5.758308171588808
				],
				[
					2.424550809090013,
					-5.758308171588808
				],
				[
					3.333757362498786,
					-6.061377022725059
				],
				[
					3.939895064771253,
					-6.36444587386132
				],
				[
					4.54603276704372,
					-6.36444587386132
				],
				[
					5.1521704693163315,
					-6.36444587386132
				],
				[
					6.061377022724961,
					-6.061377022725059
				],
				[
					7.273652427270039,
					-5.455239320452557
				],
				[
					8.182858980678812,
					-4.546032767043801
				],
				[
					8.182858980678812,
					-3.939895064771289
				],
				[
					8.485927831815117,
					-3.030688511362534
				],
				[
					8.182858980678812,
					-1.8184131068175187
				],
				[
					6.667514724997572,
					-1.2122754045450155
				],
				[
					5.455239320452494,
					-1.2122754045450155
				],
				[
					3.939895064771253,
					-1.2122754045450155
				],
				[
					1.8184131068175455,
					-1.2122754045450155
				],
				[
					0.6061377022724674,
					-1.8184131068175187
				],
				[
					-0.6061377022726107,
					-2.424550809090031
				],
				[
					-1.5153442556812402,
					-3.030688511362534
				],
				[
					-1.5153442556812402,
					-3.939895064771289
				],
				[
					-1.5153442556812402,
					-4.546032767043801
				],
				[
					-1.212275404545078,
					-5.455239320452557
				],
				[
					-0.30306885113630533,
					-6.667514724997572
				],
				[
					0.30306885113616217,
					-7.273652427270075
				],
				[
					1.5153442556812402,
					-7.5767212784063265
				],
				[
					2.7276196602263183,
					-7.5767212784063265
				],
				[
					3.939895064771253,
					-7.5767212784063265
				],
				[
					4.242963915907558,
					-7.5767212784063265
				],
				[
					5.1521704693163315,
					-7.273652427270075
				],
				[
					5.758308171588799,
					-6.667514724997572
				],
				[
					6.667514724997572,
					-6.061377022725059
				],
				[
					6.970583576133734,
					-5.152170469316305
				],
				[
					6.970583576133734,
					-4.2429639159075405
				],
				[
					6.667514724997572,
					-3.030688511362534
				],
				[
					5.455239320452494,
					-2.1214819579537703
				],
				[
					3.939895064771253,
					-1.2122754045450155
				],
				[
					2.1214819579537076,
					0
				],
				[
					0,
					0.30306885113625165
				],
				[
					-1.212275404545078,
					0.30306885113625165
				],
				[
					-1.8184131068175455,
					0
				],
				[
					-2.424550809090013,
					-0.9092065534087639
				],
				[
					-2.7276196602263183,
					-1.8184131068175187
				],
				[
					-2.7276196602263183,
					-3.333757362498786
				],
				[
					-2.424550809090013,
					-4.2429639159075405
				],
				[
					-1.5153442556812402,
					-5.152170469316305
				],
				[
					-0.30306885113630533,
					-5.758308171588808
				],
				[
					1.2122754045449349,
					-6.36444587386132
				],
				[
					3.333757362498786,
					-6.36444587386132
				],
				[
					3.939895064771253,
					-6.36444587386132
				],
				[
					4.849101618180026,
					-6.061377022725059
				],
				[
					5.758308171588799,
					-5.455239320452557
				],
				[
					6.364445873861267,
					-4.546032767043801
				],
				[
					6.667514724997572,
					-3.6368262136350373
				],
				[
					6.667514724997572,
					-3.030688511362534
				],
				[
					6.667514724997572,
					-2.1214819579537703
				],
				[
					6.061377022724961,
					-1.515344255681267
				],
				[
					5.758308171588799,
					-0.9092065534087639
				],
				[
					4.54603276704372,
					-0.30306885113625165
				],
				[
					3.333757362498786,
					-0.30306885113625165
				],
				[
					2.1214819579537076,
					-0.6061377022725122
				],
				[
					1.2122754045449349,
					-0.9092065534087639
				],
				[
					0.9092065534087728,
					-1.515344255681267
				],
				[
					0.9092065534087728,
					-2.1214819579537703
				],
				[
					0.9092065534087728,
					-2.7276196602262828
				],
				[
					1.2122754045449349,
					-3.030688511362534
				],
				[
					2.1214819579537076,
					-3.333757362498786
				],
				[
					2.424550809090013,
					-3.6368262136350373
				],
				[
					2.424550809090013,
					-3.6368262136350373
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 381,
			"versionNonce": 1612377893,
			"isDeleted": false,
			"id": "86saPQuQnc8cO5C8aAcVb",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1013.8381014191885,
			"y": 27.980725428354503,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.860082652277007,
			"height": 14.572802085411286,
			"seed": 260320675,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.13619441201319102
				],
				[
					-0.13619441201320445,
					0.4085832360395686
				],
				[
					-0.4085832360395417,
					0.6809720600659506
				],
				[
					-0.5447776480527462,
					1.0895552961055193
				],
				[
					-0.817166472079155,
					1.6343329441582743
				],
				[
					-1.0895552961054924,
					2.4514994162374157
				],
				[
					-1.3619441201319011,
					3.268665888316553
				],
				[
					-1.4981385321451057,
					3.6772491243561216
				],
				[
					-1.63433294415831,
					4.358221184422068
				],
				[
					-1.9067217681846473,
					5.175387656501205
				],
				[
					-1.9067217681846473,
					5.856359716567155
				],
				[
					-2.0429161801978517,
					6.673526188646293
				],
				[
					-2.0429161801978517,
					7.218303836699052
				],
				[
					-2.0429161801978517,
					7.8992758967649985
				],
				[
					-2.1791105922110563,
					8.716442368844136
				],
				[
					-2.1791105922110563,
					9.533608840923273
				],
				[
					-2.1791105922110563,
					10.078386488976033
				],
				[
					-2.1791105922110563,
					10.623164137028791
				],
				[
					-2.0429161801978517,
					11.16794178508155
				],
				[
					-1.9067217681846473,
					11.712719433134307
				],
				[
					-1.770527356171443,
					12.121302669173875
				],
				[
					-1.4981385321451057,
					12.529885905213444
				],
				[
					-1.3619441201319011,
					12.802274729239826
				],
				[
					-1.0895552961054924,
					13.074663553266207
				],
				[
					-0.817166472079155,
					13.483246789305776
				],
				[
					-0.6809720600659506,
					13.75563561333215
				],
				[
					-0.4085832360395417,
					14.164218849371718
				],
				[
					0,
					14.4366076733981
				],
				[
					0.13619441201320445,
					14.4366076733981
				],
				[
					0.2723888240264089,
					14.572802085411286
				],
				[
					0.4085832360395417,
					14.572802085411286
				],
				[
					0.5447776480527462,
					14.572802085411286
				],
				[
					0.6809720600659506,
					14.572802085411286
				],
				[
					0.6809720600659506,
					14.4366076733981
				],
				[
					0.6809720600659506,
					14.300413261384913
				],
				[
					0.6809720600659506,
					14.300413261384913
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 360,
			"versionNonce": 1990902187,
			"isDeleted": false,
			"id": "QL7jb1Z_1I7GYlpAQc4qI",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1019.5582667237426,
			"y": 31.24939131667108,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.404860300329825,
			"height": 7.763081484751807,
			"seed": 211749731,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.13619441201319102
				],
				[
					-0.2723888240264089,
					0.27238882402637754
				],
				[
					-0.6809720600660222,
					0.8171664720791372
				],
				[
					-1.3619441201319011,
					1.3619441201318967
				],
				[
					-1.906721768184719,
					2.179110592211034
				],
				[
					-2.7238882402638023,
					4.085832360395686
				],
				[
					-3.1324714763034156,
					5.175387656501205
				],
				[
					-3.26866588831662,
					5.856359716567151
				],
				[
					-3.404860300329825,
					6.537331776633102
				],
				[
					-3.404860300329825,
					6.94591501267267
				],
				[
					-3.404860300329825,
					7.49069266072543
				],
				[
					-3.404860300329825,
					7.626887072738616
				],
				[
					-3.404860300329825,
					7.354498248712239
				],
				[
					-3.404860300329825,
					7.2183038366990475
				],
				[
					-3.404860300329825,
					7.2183038366990475
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 367,
			"versionNonce": 798737029,
			"isDeleted": false,
			"id": "FK284X1sYiBcv9VGR5ISy",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1016.5619896594524,
			"y": 30.977002492644687,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.7705273561715145,
			"height": 7.8992758967649985,
			"seed": 836616451,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.13619441201319102
				],
				[
					0,
					0.27238882402638204
				],
				[
					0,
					0.6809720600659506
				],
				[
					0,
					0.9533608840923281
				],
				[
					0.13619441201320445,
					1.4981385321450877
				],
				[
					0.2723888240264089,
					2.4514994162374157
				],
				[
					0.6809720600658791,
					3.268665888316553
				],
				[
					0.6809720600658791,
					4.222026772408881
				],
				[
					0.9533608840922879,
					4.902998832474827
				],
				[
					0.9533608840922879,
					5.447776480527587
				],
				[
					0.9533608840922879,
					5.720165304553965
				],
				[
					1.0895552961054924,
					5.9925541285803465
				],
				[
					1.2257497081186968,
					6.264942952606724
				],
				[
					1.2257497081186968,
					6.401137364619915
				],
				[
					1.3619441201319011,
					6.673526188646293
				],
				[
					1.3619441201319011,
					6.945915012672675
				],
				[
					1.3619441201319011,
					7.218303836699052
				],
				[
					1.4981385321451057,
					7.49069266072543
				],
				[
					1.4981385321451057,
					7.763081484751812
				],
				[
					1.4981385321451057,
					7.8992758967649985
				],
				[
					1.63433294415831,
					7.763081484751812
				],
				[
					1.7705273561715145,
					7.62688707273862
				],
				[
					1.7705273561715145,
					7.62688707273862
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 354,
			"versionNonce": 2061194315,
			"isDeleted": false,
			"id": "O4ggfhRC80fXEt2SY_Ww8",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1021.8735717279667,
			"y": 37.105751033238235,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.2257497081186968,
			"height": 2.723888240263798,
			"seed": 387346339,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.27238882402638204
				],
				[
					-0.2723888240264089,
					0.9533608840923281
				],
				[
					-0.5447776480528178,
					1.3619441201318967
				],
				[
					-0.8171664720790834,
					1.9067217681846562
				],
				[
					-1.0895552961054924,
					2.4514994162374157
				],
				[
					-1.2257497081186968,
					2.5876938282506026
				],
				[
					-1.2257497081186968,
					2.723888240263798
				],
				[
					-0.9533608840922879,
					2.5876938282506026
				],
				[
					-0.9533608840922879,
					2.5876938282506026
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 427,
			"versionNonce": 845883877,
			"isDeleted": false,
			"id": "noDfMPeJVtDbQ0yjTpSRM",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1025.9594040883624,
			"y": 29.615058372512777,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.856359716567218,
			"height": 15.389968557490423,
			"seed": 933669485,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.27238882402638204
				],
				[
					0,
					0.6809720600659506
				],
				[
					0,
					1.0895552961055193
				],
				[
					0,
					2.4514994162374157
				],
				[
					0,
					2.8600826522769847
				],
				[
					0.2723888240264089,
					3.8134435363693124
				],
				[
					0.5447776480526746,
					4.494415596435259
				],
				[
					1.0895552961054924,
					5.3115820685143955
				],
				[
					1.4981385321451057,
					5.447776480527587
				],
				[
					1.7705273561713712,
					5.447776480527587
				],
				[
					2.179110592210985,
					5.039193244488018
				],
				[
					2.4514994162373935,
					4.494415596435259
				],
				[
					2.7238882402638023,
					3.8134435363693124
				],
				[
					2.860082652277007,
					2.9962770642901755
				],
				[
					2.9962770642902115,
					2.4514994162374157
				],
				[
					3.1324714763032726,
					1.9067217681846562
				],
				[
					3.268665888316477,
					1.6343329441582788
				],
				[
					3.541054712342886,
					1.22574970811871
				],
				[
					3.6772491243560905,
					0.8171664720791416
				],
				[
					3.9496379483824993,
					0.5447776480527596
				],
				[
					4.085832360395703,
					0.27238882402638204
				],
				[
					4.222026772408908,
					0.13619441201319102
				],
				[
					4.222026772408908,
					0
				],
				[
					4.222026772408908,
					-0.13619441201318655
				],
				[
					4.222026772408908,
					0
				],
				[
					3.9496379483824993,
					0.27238882402638204
				],
				[
					3.8134435363692947,
					0.9533608840923281
				],
				[
					3.6772491243560905,
					1.6343329441582788
				],
				[
					3.541054712342886,
					2.4514994162374157
				],
				[
					3.541054712342886,
					3.132471476303362
				],
				[
					3.541054712342886,
					3.9496379483824993
				],
				[
					3.4048603003296813,
					4.766804420461641
				],
				[
					3.268665888316477,
					5.9925541285803465
				],
				[
					3.1324714763032726,
					6.8097206006594835
				],
				[
					2.9962770642902115,
					8.035470308778189
				],
				[
					2.860082652277007,
					9.125025604883708
				],
				[
					2.7238882402638023,
					10.214580900989228
				],
				[
					2.4514994162373935,
					11.16794178508155
				],
				[
					2.179110592210985,
					12.25749708118707
				],
				[
					2.04291618019778,
					12.802274729239826
				],
				[
					1.7705273561713712,
					13.483246789305776
				],
				[
					1.4981385321451057,
					14.028024437358532
				],
				[
					1.2257497081186968,
					14.4366076733981
				],
				[
					0.6809720600658791,
					14.845190909437669
				],
				[
					0.40858323603961333,
					14.981385321450864
				],
				[
					0,
					15.117579733464051
				],
				[
					-0.2723888240264089,
					15.253774145477237
				],
				[
					-0.9533608840922879,
					15.253774145477237
				],
				[
					-1.2257497081186968,
					15.253774145477237
				],
				[
					-1.3619441201319011,
					15.253774145477237
				],
				[
					-1.4981385321451057,
					14.981385321450864
				],
				[
					-1.63433294415831,
					14.4366076733981
				],
				[
					-1.63433294415831,
					14.028024437358532
				],
				[
					-1.63433294415831,
					13.483246789305776
				],
				[
					-1.63433294415831,
					13.074663553266207
				],
				[
					-1.4981385321451057,
					12.666080317226639
				],
				[
					-1.2257497081186968,
					12.25749708118707
				],
				[
					-0.9533608840922879,
					12.121302669173875
				],
				[
					-0.6809720600660222,
					11.848913845147502
				],
				[
					-0.40858323603961333,
					11.440330609107933
				],
				[
					0,
					11.304136197094738
				],
				[
					0.13619441201320445,
					11.304136197094738
				],
				[
					0.5447776480526746,
					11.304136197094738
				],
				[
					0.8171664720790834,
					11.57652502112112
				],
				[
					1.0895552961054924,
					11.712719433134307
				],
				[
					1.2257497081186968,
					11.985108257160688
				],
				[
					1.63433294415831,
					12.393691493200258
				],
				[
					1.7705273561713712,
					12.666080317226639
				],
				[
					2.04291618019778,
					12.938469141253012
				],
				[
					2.315305004224189,
					13.34705237729259
				],
				[
					2.587693828250598,
					13.483246789305776
				],
				[
					2.860082652277007,
					13.755635613332158
				],
				[
					2.9962770642902115,
					14.164218849371727
				],
				[
					3.268665888316477,
					14.300413261384913
				],
				[
					3.4048603003296813,
					14.300413261384913
				],
				[
					3.541054712342886,
					14.300413261384913
				],
				[
					3.6772491243560905,
					14.300413261384913
				],
				[
					3.8134435363692947,
					14.300413261384913
				],
				[
					3.8134435363692947,
					14.164218849371727
				],
				[
					3.9496379483824993,
					14.028024437358532
				],
				[
					4.085832360395703,
					13.755635613332158
				],
				[
					4.085832360395703,
					13.483246789305776
				],
				[
					4.085832360395703,
					13.483246789305776
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 351,
			"versionNonce": 1554027243,
			"isDeleted": false,
			"id": "cZfvamTKJEEPz4Sfjxlgf",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1034.40345763318,
			"y": 37.24194544525142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.04291618019778,
			"height": 2.996277064290171,
			"seed": 1388700749,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.13619441201319102
				],
				[
					0,
					0
				],
				[
					-0.4085832360394701,
					0.6809720600659506
				],
				[
					-0.9533608840922879,
					1.2257497081187056
				],
				[
					-1.4981385321449625,
					1.7705273561714654
				],
				[
					-1.7705273561713712,
					2.315305004224225
				],
				[
					-2.04291618019778,
					2.86008265227698
				],
				[
					-2.04291618019778,
					2.86008265227698
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 388,
			"versionNonce": 697738565,
			"isDeleted": false,
			"id": "6MKnI3LVAH3E8Gvb8q7qR",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1037.263540285457,
			"y": 30.296030432578732,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.264942952606831,
			"height": 10.486969725015602,
			"seed": 1162878797,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.13619441201320445,
					0
				],
				[
					0,
					0
				],
				[
					0.6809720600660222,
					0.13619441201319102
				],
				[
					1.4981385321451057,
					0.27238882402637754
				],
				[
					2.7238882402638023,
					0.4085832360395686
				],
				[
					3.26866588831662,
					0.4085832360395686
				],
				[
					3.8134435363692947,
					0.6809720600659461
				],
				[
					3.9496379483824993,
					0.6809720600659461
				],
				[
					4.222026772408908,
					0.8171664720791372
				],
				[
					4.358221184422113,
					0.9533608840923281
				],
				[
					4.630610008448522,
					1.0895552961055146
				],
				[
					4.7668044204617255,
					1.2257497081187056
				],
				[
					4.90299883247493,
					1.3619441201318967
				],
				[
					4.90299883247493,
					1.4981385321450833
				],
				[
					4.630610008448522,
					1.7705273561714654
				],
				[
					4.358221184422113,
					2.042916180197843
				],
				[
					3.6772491243560905,
					2.5876938282506026
				],
				[
					2.7238882402638023,
					3.4048603003297395
				],
				[
					2.042916180197923,
					4.358221184422068
				],
				[
					1.0895552961054924,
					5.583970892540774
				],
				[
					0.5447776480528178,
					6.264942952606724
				],
				[
					0,
					7.082109424685862
				],
				[
					-0.2723888240264089,
					7.763081484751807
				],
				[
					-0.8171664720790834,
					8.444053544817757
				],
				[
					-1.0895552961054924,
					9.125025604883708
				],
				[
					-1.3619441201319011,
					9.397414428910082
				],
				[
					-1.3619441201319011,
					9.942192076962845
				],
				[
					-1.3619441201319011,
					10.214580900989219
				],
				[
					-1.2257497081186968,
					10.486969725015602
				],
				[
					-1.0895552961054924,
					10.486969725015602
				],
				[
					-0.8171664720790834,
					10.486969725015602
				],
				[
					-0.5447776480526746,
					10.486969725015602
				],
				[
					0,
					10.486969725015602
				],
				[
					0.2723888240264089,
					10.350775313002414
				],
				[
					0.8171664720792267,
					10.078386488976033
				],
				[
					0.953360884092431,
					9.942192076962845
				],
				[
					1.3619441201319011,
					9.669803252936465
				],
				[
					1.63433294415831,
					9.533608840923277
				],
				[
					1.906721768184719,
					9.533608840923277
				],
				[
					2.042916180197923,
					9.397414428910082
				],
				[
					2.179110592211128,
					9.261220016896894
				],
				[
					2.4514994162373935,
					9.261220016896894
				],
				[
					2.4514994162373935,
					9.125025604883708
				],
				[
					2.587693828250598,
					9.125025604883708
				],
				[
					2.587693828250598,
					9.125025604883708
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 352,
			"versionNonce": 1552219531,
			"isDeleted": false,
			"id": "Tx7YWYZGCzJaX7kB8Q0TF",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1037.5359291094835,
			"y": 34.79044602901399,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.9962770642902115,
			"height": 0,
			"seed": 1129273069,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.13619441201320445,
					0
				],
				[
					0.2723888240264089,
					0
				],
				[
					0.6809720600660222,
					0
				],
				[
					1.2257497081186968,
					0
				],
				[
					1.63433294415831,
					0
				],
				[
					2.315305004224189,
					0
				],
				[
					2.587693828250598,
					0
				],
				[
					2.7238882402638023,
					0
				],
				[
					2.860082652277007,
					0
				],
				[
					2.860082652277007,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 372,
			"versionNonce": 1484502181,
			"isDeleted": false,
			"id": "8-h5DINJY8AVURh6gAR_M",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1044.0732608861167,
			"y": 29.206475136473244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.4048603003296813,
			"height": 12.25749708118707,
			"seed": 945355629,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.13619441201320445,
					0
				],
				[
					0.40858323603961333,
					0.27238882402638204
				],
				[
					0.5447776480528178,
					0.4085832360395686
				],
				[
					1.0895552961054924,
					0.8171664720791372
				],
				[
					1.4981385321451057,
					1.22574970811871
				],
				[
					1.906721768184719,
					1.7705273561714654
				],
				[
					2.179110592210985,
					2.315305004224225
				],
				[
					2.7238882402638023,
					3.6772491243561216
				],
				[
					2.7238882402638023,
					4.358221184422068
				],
				[
					2.7238882402638023,
					5.447776480527587
				],
				[
					2.7238882402638023,
					5.9925541285803465
				],
				[
					2.587693828250598,
					6.673526188646293
				],
				[
					2.4514994162373935,
					7.354498248712243
				],
				[
					2.179110592210985,
					8.035470308778189
				],
				[
					1.906721768184719,
					8.580247956830949
				],
				[
					1.7705273561715145,
					9.125025604883708
				],
				[
					1.63433294415831,
					9.805997664949654
				],
				[
					1.4981385321451057,
					10.486969725015602
				],
				[
					1.2257497081186968,
					11.16794178508155
				],
				[
					0.9533608840922879,
					11.57652502112112
				],
				[
					0.6809720600660222,
					11.985108257160688
				],
				[
					0.5447776480528178,
					12.121302669173875
				],
				[
					0.40858323603961333,
					12.25749708118707
				],
				[
					0.2723888240264089,
					12.25749708118707
				],
				[
					0,
					12.25749708118707
				],
				[
					-0.2723888240264089,
					12.25749708118707
				],
				[
					-0.5447776480528178,
					12.25749708118707
				],
				[
					-0.6809720600658791,
					12.25749708118707
				],
				[
					-0.6809720600658791,
					12.25749708118707
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 378,
			"versionNonce": 1170412587,
			"isDeleted": false,
			"id": "N_uRHFj-TDFVyaaAdfmFN",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1110.6723283605663,
			"y": 24.848253952051152,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 4.494415596435174,
			"height": 17.97766238574103,
			"seed": 1876341005,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.1361944120130613,
					0
				],
				[
					-0.27238882402626574,
					0.13619441201319102
				],
				[
					-0.6809720600658792,
					0.4085832360395686
				],
				[
					-1.0895552961054926,
					1.0895552961055193
				],
				[
					-1.7705273561713717,
					1.6343329441582788
				],
				[
					-2.1791105922109852,
					2.315305004224225
				],
				[
					-2.7238882402638027,
					3.132471476303362
				],
				[
					-2.9962770642900685,
					3.8134435363693124
				],
				[
					-3.677249124356091,
					4.494415596435259
				],
				[
					-4.085832360395561,
					5.583970892540778
				],
				[
					-4.222026772408766,
					6.401137364619915
				],
				[
					-4.222026772408766,
					7.354498248712243
				],
				[
					-4.222026772408766,
					8.307859132804566
				],
				[
					-4.222026772408766,
					9.261220016896894
				],
				[
					-4.085832360395561,
					10.214580900989223
				],
				[
					-3.9496379483824997,
					11.16794178508155
				],
				[
					-3.8134435363692956,
					12.257497081187067
				],
				[
					-3.4048603003296822,
					13.347052377292586
				],
				[
					-3.132471476303273,
					14.4366076733981
				],
				[
					-2.8600826522768643,
					15.117579733464051
				],
				[
					-2.451499416237394,
					16.070940617556374
				],
				[
					-2.3153050042241894,
					16.479523853595943
				],
				[
					-2.0429161801977807,
					16.751912677622325
				],
				[
					-1.906721768184576,
					17.024301501648708
				],
				[
					-1.7705273561713717,
					17.29669032567508
				],
				[
					-1.634332944158167,
					17.432884737688276
				],
				[
					-1.4981385321449627,
					17.569079149701462
				],
				[
					-1.225749708118697,
					17.841467973727845
				],
				[
					-0.953360884092288,
					17.841467973727845
				],
				[
					-0.6809720600658792,
					17.97766238574103
				],
				[
					-0.4085832360394702,
					17.97766238574103
				],
				[
					0,
					17.97766238574103
				],
				[
					0.13619441201320445,
					17.97766238574103
				],
				[
					0.2723888240264089,
					17.841467973727845
				],
				[
					0.2723888240264089,
					17.841467973727845
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 354,
			"versionNonce": 986175493,
			"isDeleted": false,
			"id": "ISSPlmycOtNAk9WkuduBC",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1114.758160720962,
			"y": 31.385585728684248,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.541054712342886,
			"height": 8.035470308778194,
			"seed": 1758295277,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.4085832360394701,
					0.4085832360395686
				],
				[
					-0.9533608840922879,
					1.4981385321450877
				],
				[
					-1.4981385321449625,
					2.4514994162374157
				],
				[
					-2.179110592210985,
					3.404860300329744
				],
				[
					-2.996277064290068,
					5.17538765650121
				],
				[
					-3.4048603003296813,
					6.8097206006594835
				],
				[
					-3.4048603003296813,
					7.49069266072543
				],
				[
					-3.541054712342886,
					7.8992758967649985
				],
				[
					-3.541054712342886,
					8.035470308778194
				],
				[
					-3.541054712342886,
					7.8992758967649985
				],
				[
					-3.541054712342886,
					7.8992758967649985
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 360,
			"versionNonce": 407197387,
			"isDeleted": false,
			"id": "5FCBLiWgT6mUVA1l2wFT-",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1111.4894948326455,
			"y": 32.2027522007634,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.179110592210985,
			"height": 5.447776480527582,
			"seed": 286155725,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.27238882402637754
				],
				[
					0,
					0.5447776480527551
				],
				[
					0.2723888240264089,
					1.2257497081187056
				],
				[
					0.5447776480526746,
					1.6343329441582743
				],
				[
					0.8171664720790834,
					2.5876938282506026
				],
				[
					1.0895552961054924,
					3.677249124356117
				],
				[
					1.3619441201319011,
					4.358221184422068
				],
				[
					1.3619441201319011,
					4.630610008448445
				],
				[
					1.4981385321451057,
					5.039193244488014
				],
				[
					1.63433294415831,
					5.311582068514391
				],
				[
					1.63433294415831,
					5.447776480527582
				],
				[
					1.7705273561715145,
					5.447776480527582
				],
				[
					1.9067217681845758,
					5.447776480527582
				],
				[
					2.04291618019778,
					5.447776480527582
				],
				[
					2.04291618019778,
					5.311582068514391
				],
				[
					2.179110592210985,
					5.039193244488014
				],
				[
					2.179110592210985,
					5.039193244488014
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 353,
			"versionNonce": 2054721381,
			"isDeleted": false,
			"id": "-E-344xc5DCW280MrK9iI",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1115.439132781028,
			"y": 28.1169198403677,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.3619441201319011,
			"height": 3.813443536369308,
			"seed": 2114289901,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.13619441201319102
				],
				[
					0.13619441201320445,
					0.6809720600659461
				],
				[
					0.4085832360394701,
					1.0895552961055146
				],
				[
					0.8171664720790834,
					1.9067217681846518
				],
				[
					1.0895552961054924,
					2.7238882402637934
				],
				[
					1.2257497081186968,
					3.132471476303362
				],
				[
					1.3619441201319011,
					3.541054712342931
				],
				[
					1.3619441201319011,
					3.677249124356117
				],
				[
					1.3619441201319011,
					3.813443536369308
				],
				[
					1.3619441201319011,
					3.813443536369308
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 354,
			"versionNonce": 1923499371,
			"isDeleted": false,
			"id": "50TsZ1djnCvXhiAvB19FX",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1120.2059372014896,
			"y": 37.3781398572646,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.587693828250598,
			"height": 4.08583236039569,
			"seed": 912270701,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.40858323603961333,
					0.27238882402637754
				],
				[
					-0.8171664720790834,
					0.8171664720791372
				],
				[
					-1.2257497081186968,
					1.3619441201318967
				],
				[
					-1.7705273561713712,
					2.179110592211034
				],
				[
					-1.9067217681845758,
					2.4514994162374157
				],
				[
					-2.04291618019778,
					2.996277064290171
				],
				[
					-2.315305004224189,
					3.5410547123429263
				],
				[
					-2.4514994162373935,
					3.949637948382495
				],
				[
					-2.587693828250598,
					3.949637948382495
				],
				[
					-2.587693828250598,
					4.08583236039569
				],
				[
					-2.587693828250598,
					4.08583236039569
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 427,
			"versionNonce": 635132613,
			"isDeleted": false,
			"id": "4NXB9pa8NqBCwOM_qq48b",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1122.657436617727,
			"y": 29.615058372512777,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 8.171664720791407,
			"height": 16.20713502956957,
			"seed": 2140816461,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4085832360395686
				],
				[
					0,
					1.0895552961055193
				],
				[
					0,
					1.4981385321450877
				],
				[
					0,
					2.179110592211034
				],
				[
					0,
					2.8600826522769847
				],
				[
					0,
					3.6772491243561216
				],
				[
					0.2723888240264089,
					4.222026772408881
				],
				[
					0.5447776480528178,
					4.494415596435259
				],
				[
					0.8171664720792267,
					4.494415596435259
				],
				[
					1.3619441201319011,
					4.358221184422073
				],
				[
					1.63433294415831,
					3.8134435363693124
				],
				[
					1.906721768184719,
					3.268665888316553
				],
				[
					2.179110592211128,
					2.315305004224225
				],
				[
					2.3153050042243324,
					1.9067217681846562
				],
				[
					2.3153050042243324,
					1.3619441201318967
				],
				[
					2.3153050042243324,
					1.0895552961055193
				],
				[
					2.3153050042243324,
					0.9533608840923281
				],
				[
					2.3153050042243324,
					1.3619441201318967
				],
				[
					2.3153050042243324,
					1.9067217681846562
				],
				[
					2.3153050042243324,
					2.587693828250607
				],
				[
					2.3153050042243324,
					3.268665888316553
				],
				[
					2.3153050042243324,
					3.9496379483824993
				],
				[
					2.3153050042243324,
					4.766804420461641
				],
				[
					2.3153050042243324,
					5.447776480527587
				],
				[
					2.3153050042243324,
					5.856359716567155
				],
				[
					2.179110592211128,
					6.537331776633106
				],
				[
					2.042916180197923,
					7.354498248712243
				],
				[
					1.906721768184719,
					8.17166472079138
				],
				[
					1.7705273561715145,
					8.71644236884414
				],
				[
					1.63433294415831,
					9.669803252936465
				],
				[
					1.4981385321451057,
					10.623164137028796
				],
				[
					1.22574970811884,
					11.712719433134307
				],
				[
					1.22574970811884,
					11.985108257160688
				],
				[
					1.0895552961054924,
					12.666080317226639
				],
				[
					0.953360884092431,
					13.34705237729259
				],
				[
					0.8171664720792267,
					13.891830025345344
				],
				[
					0.6809720600660222,
					14.4366076733981
				],
				[
					0.5447776480528178,
					14.981385321450864
				],
				[
					0.13619441201320445,
					15.389968557490432
				],
				[
					-0.13619441201320445,
					15.79855179353
				],
				[
					-0.5447776480526746,
					16.070940617556374
				],
				[
					-0.8171664720790834,
					16.20713502956957
				],
				[
					-1.0895552961054924,
					16.20713502956957
				],
				[
					-1.4981385321449625,
					16.20713502956957
				],
				[
					-1.7705273561713712,
					16.20713502956957
				],
				[
					-2.04291618019778,
					15.934746205543188
				],
				[
					-2.315305004224189,
					15.662357381516806
				],
				[
					-2.315305004224189,
					15.389968557490432
				],
				[
					-2.4514994162373935,
					15.117579733464051
				],
				[
					-2.4514994162373935,
					14.708996497424483
				],
				[
					-2.4514994162373935,
					14.572802085411295
				],
				[
					-2.315305004224189,
					14.300413261384913
				],
				[
					-1.9067217681845758,
					13.891830025345344
				],
				[
					-1.3619441201319011,
					13.34705237729259
				],
				[
					-1.0895552961054924,
					13.074663553266207
				],
				[
					-0.6809720600658791,
					12.802274729239826
				],
				[
					-0.4085832360394701,
					12.666080317226639
				],
				[
					-0.2723888240262657,
					12.529885905213444
				],
				[
					-0.13619441201320445,
					12.529885905213444
				],
				[
					0,
					12.529885905213444
				],
				[
					0.40858323603961333,
					12.529885905213444
				],
				[
					0.5447776480528178,
					12.666080317226639
				],
				[
					0.6809720600660222,
					12.802274729239826
				],
				[
					0.953360884092431,
					12.938469141253012
				],
				[
					1.4981385321451057,
					13.210857965279395
				],
				[
					1.906721768184719,
					13.34705237729259
				],
				[
					2.179110592211128,
					13.619441201318963
				],
				[
					2.587693828250598,
					13.755635613332158
				],
				[
					3.26866588831662,
					14.028024437358532
				],
				[
					3.541054712343029,
					14.028024437358532
				],
				[
					3.6772491243562335,
					14.164218849371727
				],
				[
					4.085832360395703,
					14.300413261384913
				],
				[
					4.494415596435317,
					14.300413261384913
				],
				[
					4.630610008448522,
					14.300413261384913
				],
				[
					4.90299883247493,
					14.300413261384913
				],
				[
					5.039193244487992,
					14.300413261384913
				],
				[
					5.311582068514401,
					14.300413261384913
				],
				[
					5.4477764805276045,
					14.300413261384913
				],
				[
					5.583970892540809,
					14.300413261384913
				],
				[
					5.583970892540809,
					14.164218849371727
				],
				[
					5.720165304554014,
					14.028024437358532
				],
				[
					5.720165304554014,
					13.755635613332158
				],
				[
					5.720165304554014,
					13.619441201318963
				],
				[
					5.720165304554014,
					13.619441201318963
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 353,
			"versionNonce": 1009803275,
			"isDeleted": false,
			"id": "eM22LlGaRbemOAYrbYqAA",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1128.377601922281,
			"y": 28.661697488420458,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.4981385321451057,
			"height": 4.902998832474823,
			"seed": 1549649037,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.13619441201320445,
					0
				],
				[
					0.2723888240264089,
					0.27238882402637754
				],
				[
					0.40858323603961333,
					0.6809720600659461
				],
				[
					0.6809720600660222,
					1.2257497081187056
				],
				[
					0.9533608840922879,
					1.9067217681846518
				],
				[
					1.2257497081186968,
					2.996277064290171
				],
				[
					1.2257497081186968,
					3.677249124356117
				],
				[
					1.3619441201319011,
					4.494415596435254
				],
				[
					1.4981385321451057,
					4.902998832474823
				],
				[
					1.4981385321451057,
					4.902998832474823
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 363,
			"versionNonce": 630045221,
			"isDeleted": false,
			"id": "StILqKkDrDSAmBFHoilwS",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1135.7321001709934,
			"y": 36.697167797198645,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.1324714763034156,
			"height": 4.630610008448445,
			"seed": 2076440845,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.13619441201334762,
					0
				],
				[
					-0.2723888240264089,
					0
				],
				[
					-0.40858323603961333,
					0.27238882402638204
				],
				[
					-0.5447776480528178,
					0.5447776480527596
				],
				[
					-0.8171664720792267,
					1.22574970811871
				],
				[
					-1.0895552961056356,
					2.179110592211034
				],
				[
					-1.22574970811884,
					2.723888240263798
				],
				[
					-1.3619441201320444,
					2.996277064290171
				],
				[
					-1.4981385321451057,
					3.4048603003297395
				],
				[
					-1.63433294415831,
					3.5410547123429352
				],
				[
					-1.7705273561715145,
					3.6772491243561216
				],
				[
					-2.042916180197923,
					3.813443536369308
				],
				[
					-2.3153050042243324,
					3.9496379483825037
				],
				[
					-2.587693828250741,
					4.08583236039569
				],
				[
					-2.7238882402638023,
					4.358221184422073
				],
				[
					-2.860082652277007,
					4.494415596435259
				],
				[
					-2.9962770642902115,
					4.630610008448445
				],
				[
					-3.1324714763034156,
					4.630610008448445
				],
				[
					-3.1324714763034156,
					4.494415596435259
				],
				[
					-3.1324714763034156,
					4.494415596435259
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 407,
			"versionNonce": 249439915,
			"isDeleted": false,
			"id": "ae8RjWEj3y6CjTi7fm5gD",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1138.7283772352835,
			"y": 30.023641608552367,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.809720600659506,
			"height": 11.985108257160688,
			"seed": 71220835,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.2723888240264089,
					0
				],
				[
					0.40858323603961333,
					0
				],
				[
					0.5447776480528178,
					0
				],
				[
					0.8171664720790834,
					0
				],
				[
					1.2257497081186968,
					0
				],
				[
					1.7705273561715145,
					0
				],
				[
					2.4514994162373935,
					0
				],
				[
					2.9962770642902115,
					0
				],
				[
					3.541054712342886,
					0
				],
				[
					3.8134435363692947,
					0
				],
				[
					4.222026772408908,
					0
				],
				[
					4.494415596435317,
					0
				],
				[
					4.630610008448522,
					0
				],
				[
					4.7668044204615825,
					0
				],
				[
					4.90299883247493,
					0.13619441201319102
				],
				[
					5.039193244487992,
					0.27238882402638204
				],
				[
					5.175387656501196,
					0.27238882402638204
				],
				[
					5.311582068514401,
					0.40858323603957303
				],
				[
					5.311582068514401,
					0.5447776480527596
				],
				[
					5.039193244487992,
					0.6809720600659506
				],
				[
					4.7668044204615825,
					0.8171664720791416
				],
				[
					4.494415596435317,
					0.9533608840923281
				],
				[
					4.222026772408908,
					1.0895552961055193
				],
				[
					3.9496379483824993,
					1.4981385321450877
				],
				[
					3.6772491243560905,
					1.7705273561714654
				],
				[
					3.26866588831662,
					2.315305004224225
				],
				[
					2.9962770642902115,
					2.9962770642901755
				],
				[
					2.7238882402638023,
					3.404860300329744
				],
				[
					2.315305004224189,
					4.08583236039569
				],
				[
					2.179110592211128,
					4.63061000844845
				],
				[
					2.042916180197923,
					5.039193244488018
				],
				[
					1.906721768184719,
					5.447776480527587
				],
				[
					1.63433294415831,
					5.856359716567155
				],
				[
					1.4981385321451057,
					6.401137364619915
				],
				[
					1.3619441201319011,
					6.945915012672675
				],
				[
					1.0895552961054924,
					7.49069266072543
				],
				[
					0.953360884092431,
					7.899275896765003
				],
				[
					0.6809720600660222,
					8.444053544817757
				],
				[
					0.40858323603961333,
					8.852636780857326
				],
				[
					0.2723888240264089,
					9.125025604883708
				],
				[
					0.13619441201320445,
					9.533608840923277
				],
				[
					-0.13619441201320445,
					9.80599766494966
				],
				[
					-0.2723888240264089,
					10.078386488976033
				],
				[
					-0.40858323603961333,
					10.350775313002414
				],
				[
					-0.6809720600658791,
					10.623164137028796
				],
				[
					-0.9533608840922879,
					11.031747373068365
				],
				[
					-1.0895552961054924,
					11.16794178508155
				],
				[
					-1.2257497081186968,
					11.440330609107933
				],
				[
					-1.3619441201319011,
					11.57652502112112
				],
				[
					-1.4981385321451057,
					11.712719433134307
				],
				[
					-1.4981385321451057,
					11.848913845147502
				],
				[
					-1.4981385321451057,
					11.985108257160688
				],
				[
					-0.9533608840922879,
					11.985108257160688
				],
				[
					-0.40858323603961333,
					11.985108257160688
				],
				[
					0.13619441201320445,
					11.985108257160688
				],
				[
					0.6809720600660222,
					11.848913845147502
				],
				[
					1.0895552961054924,
					11.712719433134307
				],
				[
					1.7705273561715145,
					11.57652502112112
				],
				[
					2.179110592211128,
					11.440330609107933
				],
				[
					2.315305004224189,
					11.440330609107933
				],
				[
					2.7238882402638023,
					11.304136197094738
				],
				[
					3.1324714763034156,
					11.304136197094738
				],
				[
					3.404860300329825,
					11.16794178508155
				],
				[
					3.6772491243560905,
					11.031747373068365
				],
				[
					4.222026772408908,
					11.031747373068365
				],
				[
					4.494415596435317,
					10.89555296105517
				],
				[
					4.494415596435317,
					10.89555296105517
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 356,
			"versionNonce": 1920806277,
			"isDeleted": false,
			"id": "bMRadWxJr06EQoHP4UWRg",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1139.0007660593099,
			"y": 34.109473968948066,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 4.358221184422113,
			"height": 0.13619441201319102,
			"seed": 539543683,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.13619441201320445,
					0
				],
				[
					-0.13619441201320445,
					0.13619441201319102
				],
				[
					0,
					0.13619441201319102
				],
				[
					0.6809720600660222,
					0.13619441201319102
				],
				[
					1.2257497081186968,
					0.13619441201319102
				],
				[
					1.63433294415831,
					0.13619441201319102
				],
				[
					2.179110592210985,
					0.13619441201319102
				],
				[
					2.587693828250598,
					0.13619441201319102
				],
				[
					2.7238882402638023,
					0.13619441201319102
				],
				[
					3.1324714763034156,
					0.13619441201319102
				],
				[
					3.4048603003296813,
					0.13619441201319102
				],
				[
					3.541054712342886,
					0.13619441201319102
				],
				[
					3.6772491243560905,
					0.13619441201319102
				],
				[
					3.8134435363692947,
					0.13619441201319102
				],
				[
					4.085832360395703,
					0.13619441201319102
				],
				[
					4.222026772408908,
					0.13619441201319102
				],
				[
					4.222026772408908,
					0.13619441201319102
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 351,
			"versionNonce": 1633294667,
			"isDeleted": false,
			"id": "KyP-7KAUYud95Hr0O-Ttg",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1144.5847369518506,
			"y": 26.074003660169865,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.315305004224189,
			"height": 5.3115820685143955,
			"seed": 1053863267,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.2723888240264089,
					0.40858323603957303
				],
				[
					0.8171664720790834,
					1.22574970811871
				],
				[
					1.2257497081186968,
					1.9067217681846562
				],
				[
					1.4981385321451057,
					2.587693828250607
				],
				[
					1.9067217681845758,
					3.8134435363693124
				],
				[
					2.179110592210985,
					4.358221184422073
				],
				[
					2.179110592210985,
					4.63061000844845
				],
				[
					2.179110592210985,
					5.039193244488018
				],
				[
					2.315305004224189,
					5.17538765650121
				],
				[
					2.315305004224189,
					5.3115820685143955
				],
				[
					2.315305004224189,
					5.3115820685143955
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 367,
			"versionNonce": 199701733,
			"isDeleted": false,
			"id": "nn4hIAsTJjVdMYtg4WilR",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1149.6239301963385,
			"y": 27.299753368288577,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.63433294415831,
			"height": 15.526162969503615,
			"seed": 586087555,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.13619441201320445,
					0
				],
				[
					0,
					0.13619441201318655
				],
				[
					0.2723888240264089,
					0.4085832360395686
				],
				[
					0.5447776480526746,
					0.9533608840923281
				],
				[
					0.6809720600658791,
					1.4981385321450833
				],
				[
					0.8171664720790834,
					2.179110592211034
				],
				[
					1.0895552961054924,
					2.996277064290171
				],
				[
					1.2257497081186968,
					3.677249124356117
				],
				[
					1.2257497081186968,
					4.630610008448445
				],
				[
					1.2257497081186968,
					5.583970892540774
				],
				[
					1.2257497081186968,
					7.082109424685862
				],
				[
					1.2257497081186968,
					8.035470308778185
				],
				[
					1.2257497081186968,
					9.261220016896894
				],
				[
					1.0895552961054924,
					10.078386488976033
				],
				[
					1.0895552961054924,
					11.031747373068361
				],
				[
					0.9533608840922879,
					11.848913845147498
				],
				[
					0.8171664720790834,
					12.938469141253016
				],
				[
					0.6809720600658791,
					13.619441201318958
				],
				[
					0.5447776480526746,
					13.89183002534534
				],
				[
					0.40858323603961333,
					14.300413261384909
				],
				[
					0.2723888240264089,
					14.572802085411292
				],
				[
					0.2723888240264089,
					14.845190909437664
				],
				[
					0.13619441201320445,
					15.117579733464046
				],
				[
					-0.13619441201320445,
					15.389968557490429
				],
				[
					-0.2723888240264089,
					15.526162969503615
				],
				[
					-0.40858323603961333,
					15.526162969503615
				],
				[
					-0.40858323603961333,
					15.526162969503615
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 373,
			"versionNonce": 1895741419,
			"isDeleted": false,
			"id": "nwNIV7KWHy8RUhT_qITL5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1067.9072829884249,
			"y": -11.65184846748366,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 20.429161801978374,
			"height": 1.3619441201318967,
			"seed": 1316457347,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.2723888240264089,
					0
				],
				[
					0.6809720600658791,
					0
				],
				[
					1.0895552961054924,
					0
				],
				[
					1.7705273561715145,
					0
				],
				[
					2.315305004224189,
					0
				],
				[
					2.860082652277007,
					0
				],
				[
					3.541054712342886,
					0.27238882402637754
				],
				[
					4.222026772408908,
					0.27238882402637754
				],
				[
					4.7668044204615825,
					0.27238882402637754
				],
				[
					5.4477764805276045,
					0.27238882402637754
				],
				[
					6.264942952606688,
					0.27238882402637754
				],
				[
					6.94591501267271,
					0.27238882402637754
				],
				[
					7.626887072738589,
					0.27238882402637754
				],
				[
					8.580247956830878,
					0.27238882402637754
				],
				[
					9.942192076962778,
					0.27238882402637754
				],
				[
					11.440330609107884,
					0.27238882402637754
				],
				[
					12.802274729239786,
					0.27238882402637754
				],
				[
					13.891830025345278,
					0.13619441201318655
				],
				[
					14.708996497424504,
					0.13619441201318655
				],
				[
					15.389968557490384,
					0.13619441201318655
				],
				[
					16.20713502956961,
					0.13619441201318655
				],
				[
					16.88810708963549,
					0
				],
				[
					17.705273561714716,
					0
				],
				[
					18.113856797754185,
					-0.13619441201319102
				],
				[
					18.658634445807003,
					-0.27238882402638204
				],
				[
					19.067217681846472,
					-0.4085832360395686
				],
				[
					19.475800917886087,
					-0.5447776480527596
				],
				[
					19.61199532989929,
					-0.6809720600659506
				],
				[
					19.8843841539257,
					-0.8171664720791372
				],
				[
					20.020578565938905,
					-0.9533608840923281
				],
				[
					20.15677297795211,
					-0.9533608840923281
				],
				[
					20.29296738996517,
					-1.0895552961055193
				],
				[
					20.429161801978374,
					-1.0895552961055193
				],
				[
					20.429161801978374,
					-1.0895552961055193
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 393,
			"versionNonce": 760827973,
			"isDeleted": false,
			"id": "tG16vUImsKQEbeMXOhMn0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1077.4408918293482,
			"y": -11.65184846748366,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 0.9533608840922879,
			"height": 15.934746205543188,
			"seed": 949831597,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.13619441201318655
				],
				[
					0,
					0.27238882402637754
				],
				[
					0.13619441201320445,
					0.4085832360395686
				],
				[
					0.2723888240264089,
					0.6809720600659461
				],
				[
					0.4085832360394701,
					1.3619441201318967
				],
				[
					0.4085832360394701,
					1.9067217681846518
				],
				[
					0.5447776480526746,
					2.5876938282506026
				],
				[
					0.5447776480526746,
					2.996277064290171
				],
				[
					0.6809720600658791,
					3.5410547123429263
				],
				[
					0.6809720600658791,
					3.949637948382495
				],
				[
					0.8171664720790834,
					4.358221184422063
				],
				[
					0.8171664720790834,
					4.902998832474827
				],
				[
					0.9533608840922879,
					5.175387656501201
				],
				[
					0.9533608840922879,
					5.583970892540778
				],
				[
					0.9533608840922879,
					5.856359716567151
				],
				[
					0.9533608840922879,
					6.128748540593533
				],
				[
					0.9533608840922879,
					6.401137364619915
				],
				[
					0.9533608840922879,
					6.537331776633102
				],
				[
					0.9533608840922879,
					6.94591501267267
				],
				[
					0.8171664720790834,
					7.354498248712239
				],
				[
					0.8171664720790834,
					7.763081484751807
				],
				[
					0.8171664720790834,
					8.035470308778189
				],
				[
					0.8171664720790834,
					8.307859132804563
				],
				[
					0.8171664720790834,
					8.444053544817757
				],
				[
					0.8171664720790834,
					8.716442368844131
				],
				[
					0.8171664720790834,
					8.852636780857326
				],
				[
					0.8171664720790834,
					9.261220016896894
				],
				[
					0.6809720600658791,
					9.669803252936465
				],
				[
					0.6809720600658791,
					10.078386488976033
				],
				[
					0.5447776480526746,
					10.623164137028787
				],
				[
					0.5447776480526746,
					10.759358549041982
				],
				[
					0.4085832360394701,
					11.440330609107924
				],
				[
					0.2723888240264089,
					11.848913845147493
				],
				[
					0.2723888240264089,
					12.121302669173875
				],
				[
					0.13619441201320445,
					12.393691493200258
				],
				[
					0.13619441201320445,
					12.529885905213444
				],
				[
					0.13619441201320445,
					12.66608031722663
				],
				[
					0.13619441201320445,
					12.802274729239826
				],
				[
					0.13619441201320445,
					12.938469141253012
				],
				[
					0.13619441201320445,
					13.210857965279395
				],
				[
					0.13619441201320445,
					13.34705237729258
				],
				[
					0.13619441201320445,
					13.483246789305776
				],
				[
					0.13619441201320445,
					13.75563561333215
				],
				[
					0.13619441201320445,
					13.891830025345344
				],
				[
					0.2723888240264089,
					14.300413261384913
				],
				[
					0.2723888240264089,
					14.572802085411286
				],
				[
					0.4085832360394701,
					14.708996497424483
				],
				[
					0.4085832360394701,
					14.845190909437669
				],
				[
					0.4085832360394701,
					15.117579733464051
				],
				[
					0.5447776480526746,
					15.253774145477237
				],
				[
					0.5447776480526746,
					15.52616296950362
				],
				[
					0.6809720600658791,
					15.662357381516806
				],
				[
					0.6809720600658791,
					15.798551793529992
				],
				[
					0.6809720600658791,
					15.934746205543188
				],
				[
					0.6809720600658791,
					15.934746205543188
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 502,
			"versionNonce": 1809220235,
			"isDeleted": false,
			"id": "KAnucQva",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1184.9330207071364,
			"y": 11.735281612294472,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 163.61370849609375,
			"height": 22.04003325423066,
			"seed": 1252163341,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"fontSize": 17.632026603384528,
			"fontFamily": 1,
			"text": "Similar to addition!",
			"rawText": "Similar to addition!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Similar to addition!",
			"lineHeight": 1.25,
			"baseline": 15
		},
		{
			"type": "freedraw",
			"version": 447,
			"versionNonce": 1152450469,
			"isDeleted": false,
			"id": "Kjh08EylqrTS0pBxsU8hb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1121.7427728143134,
			"y": 65.04824664164761,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 8.433983018915978,
			"height": 72.57664334698772,
			"seed": 230988557,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.22194692155039594,
					0.6658407646512606
				],
				[
					-0.6658407646513043,
					1.7755753724033714
				],
				[
					-0.8877876862017002,
					2.663363058605057
				],
				[
					-1.3316815293024922,
					3.7730976663571534
				],
				[
					-1.7755753724034005,
					5.326726117210099
				],
				[
					-1.9975222939537964,
					6.4364607249622106
				],
				[
					-2.2194692155041924,
					7.990089175815156
				],
				[
					-2.441416137054588,
					9.321770705117693
				],
				[
					-2.8853099801554967,
					10.653452234420213
				],
				[
					-3.5511507448066846,
					12.429027606823583
				],
				[
					-3.7730976663570805,
					13.760709136126104
				],
				[
					-4.216991509457989,
					14.870443743878216
				],
				[
					-5.104779195659689,
					17.7557537240337
				],
				[
					-5.548673038760481,
					19.53132909643707
				],
				[
					-6.214513803411785,
					21.52885139039085
				],
				[
					-6.658407646512694,
					23.748320605895074
				],
				[
					-7.1023014896134855,
					25.96778982139928
				],
				[
					-7.5461953327142774,
					28.40920595845391
				],
				[
					-7.990089175815186,
					30.62867517395812
				],
				[
					-8.212036097365582,
					32.84814438946234
				],
				[
					-8.212036097365582,
					34.62371976186571
				],
				[
					-8.433983018915978,
					36.177348212718655
				],
				[
					-8.433983018915978,
					38.17487050667244
				],
				[
					-8.433983018915978,
					39.950445879075815
				],
				[
					-8.433983018915978,
					41.060180486827925
				],
				[
					-8.433983018915978,
					42.16991509458001
				],
				[
					-8.433983018915978,
					43.94549046698339
				],
				[
					-8.212036097365582,
					46.164959682487606
				],
				[
					-7.5461953327142774,
					47.94053505489098
				],
				[
					-7.3242484111638815,
					49.71611042729435
				],
				[
					-6.8803545680630895,
					52.15752656434896
				],
				[
					-6.214513803411785,
					53.93310193675234
				],
				[
					-5.548673038760481,
					57.04035883845823
				],
				[
					-5.326726117210085,
					59.92566881861374
				],
				[
					-4.660885352558897,
					61.701244191017096
				],
				[
					-4.438938431008385,
					63.03292572031962
				],
				[
					-4.216991509457989,
					64.36460724962214
				],
				[
					-3.995044587907593,
					65.69628877892467
				],
				[
					-3.5511507448066846,
					66.80602338667678
				],
				[
					-3.3292038232562886,
					67.91575799442889
				],
				[
					-2.8853099801554967,
					68.80354568063056
				],
				[
					-2.6633630586051007,
					69.46938644528183
				],
				[
					-2.441416137054588,
					70.1352272099331
				],
				[
					-2.441416137054588,
					70.57912105303393
				],
				[
					-2.2194692155041924,
					70.80106797458436
				],
				[
					-1.9975222939537964,
					71.02301489613477
				],
				[
					-1.7755753724034005,
					71.46690873923562
				],
				[
					-1.7755753724034005,
					71.68885566078606
				],
				[
					-1.5536284508528881,
					72.13274950388687
				],
				[
					-1.5536284508528881,
					72.3546964254373
				],
				[
					-1.3316815293024922,
					72.3546964254373
				],
				[
					-1.3316815293024922,
					72.57664334698772
				],
				[
					-1.3316815293024922,
					72.57664334698772
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 426,
			"versionNonce": 1520171307,
			"isDeleted": false,
			"id": "cnWJmyMbqZAsyN-QhORWf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1082.458167699889,
			"y": 84.80152265963508,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 23.30442676279425,
			"height": 0.4438938431008501,
			"seed": 59936173,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.1097346077520962,
					0.22194692155042506
				],
				[
					2.441416137054588,
					0.22194692155042506
				],
				[
					4.882832274109293,
					0.22194692155042506
				],
				[
					6.880354568062973,
					0.22194692155042506
				],
				[
					8.433983018915978,
					0.22194692155042506
				],
				[
					9.543717626668073,
					0.22194692155042506
				],
				[
					9.987611469768865,
					0.22194692155042506
				],
				[
					10.875399155970564,
					0.22194692155042506
				],
				[
					11.763186842172265,
					0.22194692155042506
				],
				[
					12.42902760682357,
					0.22194692155042506
				],
				[
					13.31681529302527,
					0.22194692155042506
				],
				[
					13.760709136126062,
					0.22194692155042506
				],
				[
					14.426549900777365,
					0.22194692155042506
				],
				[
					15.314337586979066,
					0.22194692155042506
				],
				[
					16.424072194731163,
					0.4438938431008501
				],
				[
					17.08991295938235,
					0.4438938431008501
				],
				[
					17.97770064558405,
					0.4438938431008501
				],
				[
					18.865488331785752,
					0.4438938431008501
				],
				[
					19.309382174886657,
					0.4438938431008501
				],
				[
					19.75327601798745,
					0.4438938431008501
				],
				[
					19.975222939537847,
					0.4438938431008501
				],
				[
					20.19716986108824,
					0.4438938431008501
				],
				[
					20.419116782638756,
					0.4438938431008501
				],
				[
					20.863010625739545,
					0.4438938431008501
				],
				[
					21.08495754728994,
					0.4438938431008501
				],
				[
					21.306904468840457,
					0.4438938431008501
				],
				[
					21.750798311941246,
					0.4438938431008501
				],
				[
					21.97274523349164,
					0.4438938431008501
				],
				[
					22.638585998142947,
					0.4438938431008501
				],
				[
					23.08247984124374,
					0.4438938431008501
				],
				[
					23.30442676279425,
					0.4438938431008501
				],
				[
					23.30442676279425,
					0.4438938431008501
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 444,
			"versionNonce": 672908037,
			"isDeleted": false,
			"id": "EEz_xpeKrm7ZMp4kPPu1e",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1093.7774606989603,
			"y": 86.35515111048801,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.5536284508530045,
			"height": 35.95540129116823,
			"seed": 703910509,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.22194692155042506
				],
				[
					0,
					0.6658407646512752
				],
				[
					0,
					1.5536284508529608
				],
				[
					0,
					2.4414161370546466
				],
				[
					0,
					3.3292038232563175
				],
				[
					0,
					3.7730976663571676
				],
				[
					0,
					4.438938431008428
				],
				[
					0,
					4.882832274109279
				],
				[
					0.22194692155039594,
					5.326726117210114
				],
				[
					0.22194692155039594,
					6.2145138034117995
				],
				[
					0.22194692155039594,
					7.546195332714321
				],
				[
					0.22194692155039594,
					8.655929940466432
				],
				[
					0.22194692155039594,
					9.543717626668117
				],
				[
					0,
					10.875399155970639
				],
				[
					0,
					12.429027606823599
				],
				[
					0,
					13.76070913612612
				],
				[
					-0.22194692155039594,
					14.648496822327806
				],
				[
					-0.22194692155039594,
					15.536284508529492
				],
				[
					-0.22194692155039594,
					16.646019116281604
				],
				[
					-0.22194692155039594,
					17.311859880932865
				],
				[
					-0.22194692155039594,
					18.199647567134548
				],
				[
					-0.22194692155039594,
					19.087435253336235
				],
				[
					-0.22194692155039594,
					19.975222939537918
				],
				[
					-0.22194692155039594,
					21.084957547290017
				],
				[
					-0.22194692155039594,
					21.750798311941292
				],
				[
					-0.4438938431009083,
					22.860532919693387
				],
				[
					-0.4438938431009083,
					23.970267527445483
				],
				[
					-0.6658407646513043,
					24.85805521364718
				],
				[
					-0.6658407646513043,
					25.52389597829846
				],
				[
					-0.8877876862017002,
					26.411683664500128
				],
				[
					-0.8877876862017002,
					27.2994713507018
				],
				[
					-1.1097346077520962,
					27.74336519380265
				],
				[
					-1.1097346077520962,
					28.63115288000435
				],
				[
					-1.3316815293026085,
					29.296993644655597
				],
				[
					-1.3316815293026085,
					29.740887487756446
				],
				[
					-1.3316815293026085,
					30.184781330857298
				],
				[
					-1.3316815293026085,
					30.62867517395812
				],
				[
					-1.3316815293026085,
					31.072569017058967
				],
				[
					-1.3316815293026085,
					31.738409781710246
				],
				[
					-1.3316815293026085,
					32.18230362481109
				],
				[
					-1.3316815293026085,
					32.84814438946234
				],
				[
					-1.3316815293026085,
					33.292038232563186
				],
				[
					-1.3316815293026085,
					33.73593207566404
				],
				[
					-1.3316815293026085,
					34.17982591876486
				],
				[
					-1.3316815293026085,
					34.62371976186571
				],
				[
					-1.3316815293026085,
					34.845666683416134
				],
				[
					-1.3316815293026085,
					35.51150744806741
				],
				[
					-1.3316815293026085,
					35.73345436961781
				],
				[
					-1.3316815293026085,
					35.95540129116823
				],
				[
					-1.3316815293026085,
					35.95540129116823
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 413,
			"versionNonce": 1253678027,
			"isDeleted": false,
			"id": "Cx8K0vbDpUaOxSr2D1fmT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1132.618171970284,
			"y": 64.38240587699633,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.436460724962181,
			"height": 14.426549900777365,
			"seed": 2005998307,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.22194692155039594,
					0.2219469215504105
				],
				[
					-0.6658407646513043,
					1.1097346077520962
				],
				[
					-1.3316815293026085,
					2.219469215504207
				],
				[
					-1.7755753724034005,
					3.3292038232563175
				],
				[
					-2.2194692155041924,
					3.995044587907578
				],
				[
					-2.4414161370547047,
					5.104779195659675
				],
				[
					-3.1072569017058926,
					6.214513803411785
				],
				[
					-3.551150744806801,
					7.324248411163896
				],
				[
					-3.995044587907593,
					7.990089175815156
				],
				[
					-4.438938431008385,
					9.099823783567267
				],
				[
					-4.882832274109293,
					9.765664548218528
				],
				[
					-5.104779195659689,
					10.653452234420213
				],
				[
					-5.326726117210201,
					11.763186842172324
				],
				[
					-5.770619960310993,
					12.429027606823583
				],
				[
					-5.992566881861389,
					13.094868371474844
				],
				[
					-5.992566881861389,
					13.538762214575682
				],
				[
					-6.214513803411785,
					13.98265605767653
				],
				[
					-6.214513803411785,
					14.204602979226955
				],
				[
					-6.436460724962181,
					14.426549900777365
				],
				[
					-6.436460724962181,
					14.204602979226955
				],
				[
					-6.436460724962181,
					14.204602979226955
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 412,
			"versionNonce": 202840677,
			"isDeleted": false,
			"id": "hjOZqefEGHi6nWihb9_cB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1126.4036581668722,
			"y": 63.71656511234505,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.8803545680630895,
			"height": 15.092390665428642,
			"seed": 1768907331,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.22194692155039594,
					0
				],
				[
					-0.22194692155039594,
					0.22194692155042506
				],
				[
					-0.4438938431009083,
					0.4438938431008501
				],
				[
					-0.4438938431009083,
					1.1097346077521106
				],
				[
					0,
					2.2194692155042213
				],
				[
					0.8877876862015838,
					3.3292038232563175
				],
				[
					1.5536284508528881,
					4.882832274109279
				],
				[
					2.6633630586049843,
					6.658407646512635
				],
				[
					3.1072569017058926,
					7.9900891758151715
				],
				[
					3.5511507448066846,
					8.877876862016857
				],
				[
					4.216991509457989,
					9.765664548218542
				],
				[
					4.438938431008385,
					11.31929299907149
				],
				[
					4.882832274109176,
					12.429027606823599
				],
				[
					5.326726117210085,
					13.09486837147486
				],
				[
					5.548673038760481,
					13.538762214575694
				],
				[
					5.992566881861389,
					14.204602979226955
				],
				[
					6.214513803411785,
					14.648496822327806
				],
				[
					6.214513803411785,
					14.870443743878232
				],
				[
					6.436460724962181,
					15.092390665428642
				],
				[
					6.436460724962181,
					15.092390665428642
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 465,
			"versionNonce": 944368235,
			"isDeleted": false,
			"id": "oBVRWP9I1X2Cv1KbKseXj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1125.737817402221,
			"y": 85.91125726738719,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 11.097346077521077,
			"height": 18.643541410235386,
			"seed": 2019929603,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.22194692155042506
				],
				[
					0.4438938431009083,
					1.1097346077521106
				],
				[
					0.6658407646513043,
					1.7755753724033714
				],
				[
					1.5536284508528881,
					2.663363058605057
				],
				[
					2.6633630586051007,
					3.3292038232563175
				],
				[
					3.3292038232562886,
					3.3292038232563175
				],
				[
					4.438938431008385,
					3.3292038232563175
				],
				[
					4.882832274109293,
					3.3292038232563175
				],
				[
					5.326726117210085,
					2.885309980155482
				],
				[
					5.770619960310993,
					2.663363058605057
				],
				[
					6.214513803411785,
					1.3316815293025213
				],
				[
					6.436460724962181,
					0.6658407646512606
				],
				[
					6.658407646512694,
					-0.22194692155042506
				],
				[
					6.658407646512694,
					-0.8877876862016857
				],
				[
					6.658407646512694,
					-1.3316815293025213
				],
				[
					6.658407646512694,
					-1.7755753724033714
				],
				[
					6.658407646512694,
					-2.219469215504207
				],
				[
					6.658407646512694,
					-2.441416137054632
				],
				[
					6.658407646512694,
					-1.7755753724033714
				],
				[
					6.658407646512694,
					-1.1097346077521106
				],
				[
					6.436460724962181,
					0.22194692155042506
				],
				[
					6.436460724962181,
					1.3316815293025213
				],
				[
					6.214513803411785,
					2.219469215504207
				],
				[
					6.214513803411785,
					3.7730976663571534
				],
				[
					6.214513803411785,
					4.882832274109264
				],
				[
					6.214513803411785,
					5.326726117210114
				],
				[
					6.214513803411785,
					6.4364607249622106
				],
				[
					6.214513803411785,
					7.990089175815156
				],
				[
					5.992566881861389,
					9.099823783567267
				],
				[
					5.548673038760481,
					11.097346077521063
				],
				[
					5.104779195659689,
					12.429027606823583
				],
				[
					4.882832274109293,
					13.538762214575694
				],
				[
					4.216991509457989,
					14.426549900777381
				],
				[
					3.995044587907593,
					15.092390665428642
				],
				[
					3.1072569017058926,
					15.758231430079903
				],
				[
					2.2194692155041924,
					16.20212527318075
				],
				[
					1.5536284508528881,
					16.20212527318075
				],
				[
					1.1097346077520962,
					16.20212527318075
				],
				[
					0.22194692155039594,
					16.20212527318075
				],
				[
					-0.6658407646513043,
					15.980178351630327
				],
				[
					-0.8877876862017002,
					15.758231430079903
				],
				[
					-1.5536284508528881,
					15.536284508529477
				],
				[
					-1.7755753724034005,
					15.092390665428642
				],
				[
					-1.9975222939537964,
					14.648496822327806
				],
				[
					-1.9975222939537964,
					13.98265605767653
				],
				[
					-1.7755753724034005,
					13.538762214575694
				],
				[
					-1.5536284508528881,
					13.094868371474844
				],
				[
					-1.1097346077520962,
					12.65097452837401
				],
				[
					-0.6658407646513043,
					12.20708068527316
				],
				[
					-0.22194692155039594,
					11.98513376372275
				],
				[
					0.22194692155039594,
					11.763186842172324
				],
				[
					0.8877876862017002,
					11.5412399206219
				],
				[
					1.3316815293024922,
					11.319292999071473
				],
				[
					1.7755753724034005,
					11.319292999071473
				],
				[
					2.4414161370547047,
					11.097346077521063
				],
				[
					2.6633630586051007,
					11.097346077521063
				],
				[
					3.3292038232562886,
					11.097346077521063
				],
				[
					3.5511507448066846,
					11.097346077521063
				],
				[
					3.995044587907593,
					11.319292999071473
				],
				[
					4.660885352558897,
					11.5412399206219
				],
				[
					5.326726117210085,
					12.20708068527316
				],
				[
					5.770619960310993,
					12.429027606823583
				],
				[
					6.436460724962181,
					13.094868371474844
				],
				[
					6.8803545680630895,
					13.31681529302527
				],
				[
					7.5461953327142774,
					13.76070913612612
				],
				[
					7.768142254264673,
					13.98265605767653
				],
				[
					8.212036097365582,
					13.98265605767653
				],
				[
					8.433983018915978,
					13.98265605767653
				],
				[
					8.65592994046649,
					13.98265605767653
				],
				[
					8.877876862016885,
					13.98265605767653
				],
				[
					9.099823783567281,
					13.98265605767653
				],
				[
					9.099823783567281,
					13.538762214575694
				],
				[
					9.099823783567281,
					13.538762214575694
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 436,
			"versionNonce": 963675589,
			"isDeleted": false,
			"id": "WiynuHTDimAGR-EIIFgh4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1125.9597643237714,
			"y": 117.64966704909742,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 11.319292999071473,
			"height": 11.319292999071473,
			"seed": 1552514733,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4438938431009082,
					0
				],
				[
					1.5536284508530043,
					0
				],
				[
					3.329203823256288,
					0
				],
				[
					4.882832274109292,
					0
				],
				[
					6.436460724962297,
					0
				],
				[
					7.990089175815184,
					0
				],
				[
					9.099823783567281,
					0
				],
				[
					9.321770705117677,
					0
				],
				[
					9.765664548218584,
					0.22194692155042506
				],
				[
					9.765664548218584,
					0.4438938431008501
				],
				[
					9.98761146976898,
					0.6658407646512752
				],
				[
					9.98761146976898,
					1.3316815293025213
				],
				[
					9.765664548218584,
					1.5536284508529463
				],
				[
					8.877876862016885,
					1.7755753724033714
				],
				[
					7.546195332714276,
					2.2194692155042213
				],
				[
					6.214513803411784,
					2.8853099801554674
				],
				[
					4.882832274109292,
					3.7730976663571676
				],
				[
					3.5511507448068,
					5.104779195659689
				],
				[
					2.4414161370547043,
					6.4364607249622106
				],
				[
					1.7755753724034,
					7.546195332714335
				],
				[
					1.5536284508530043,
					7.990089175815156
				],
				[
					1.109734607752096,
					8.655929940466432
				],
				[
					0.8877876862017,
					8.655929940466432
				],
				[
					0.4438938431009082,
					8.877876862016857
				],
				[
					0.22194692155051235,
					9.099823783567281
				],
				[
					-0.2219469215503959,
					9.321770705117707
				],
				[
					-0.4438938431007918,
					9.543717626668103
				],
				[
					-0.6658407646513042,
					9.543717626668103
				],
				[
					-1.109734607752096,
					9.765664548218528
				],
				[
					-1.331681529302492,
					10.209558391319378
				],
				[
					-1.331681529302492,
					10.431505312869803
				],
				[
					-1.109734607752096,
					10.653452234420229
				],
				[
					-0.6658407646513042,
					10.875399155970651
				],
				[
					0.22194692155051235,
					11.097346077521077
				],
				[
					1.7755753724034,
					11.097346077521077
				],
				[
					2.6633630586051003,
					11.097346077521077
				],
				[
					3.773097666357196,
					11.319292999071473
				],
				[
					4.4389384310085,
					11.319292999071473
				],
				[
					5.326726117210084,
					11.319292999071473
				],
				[
					5.5486730387605965,
					11.319292999071473
				],
				[
					5.992566881861388,
					11.319292999071473
				],
				[
					6.436460724962297,
					11.319292999071473
				],
				[
					6.658407646512693,
					11.319292999071473
				],
				[
					6.880354568063089,
					11.319292999071473
				],
				[
					6.880354568063089,
					11.319292999071473
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 409,
			"versionNonce": 941057291,
			"isDeleted": false,
			"id": "tLOGv8Nt1tBIBt9quTeQu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1124.4061358729184,
			"y": 121.644711637005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 11.097346077520962,
			"height": 2.6633630586050425,
			"seed": 2072044109,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6658407646511878,
					0
				],
				[
					1.9975222939537964,
					0.22194692155042506
				],
				[
					3.3292038232562886,
					0.443893843100821
				],
				[
					4.438938431008385,
					0.6658407646512461
				],
				[
					5.770619960310877,
					0.8877876862016711
				],
				[
					7.1023014896134855,
					1.3316815293025213
				],
				[
					7.5461953327142774,
					1.5536284508529463
				],
				[
					7.990089175815186,
					1.5536284508529463
				],
				[
					8.212036097365582,
					1.5536284508529463
				],
				[
					8.655929940466374,
					1.7755753724033714
				],
				[
					9.099823783567164,
					1.9975222939537964
				],
				[
					9.543717626668073,
					2.2194692155041924
				],
				[
					9.765664548218469,
					2.4414161370546172
				],
				[
					9.987611469768982,
					2.4414161370546172
				],
				[
					10.209558391319378,
					2.6633630586050425
				],
				[
					10.65345223442017,
					2.6633630586050425
				],
				[
					10.875399155970564,
					2.6633630586050425
				],
				[
					11.097346077520962,
					2.6633630586050425
				],
				[
					11.097346077520962,
					2.6633630586050425
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 471,
			"versionNonce": 54887717,
			"isDeleted": false,
			"id": "zhyhkQoEqH6u8MyozUJQg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1139.498526538347,
			"y": 62.828777426143375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 8.65592994046649,
			"height": 73.90832487629028,
			"seed": 516446253,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.22194692155051235,
					0.4438938431008501
				],
				[
					0.6658407646513042,
					0.8877876862016857
				],
				[
					1.1097346077522123,
					1.7755753724033714
				],
				[
					1.997522293953796,
					2.885309980155482
				],
				[
					2.2194692155043083,
					3.995044587907593
				],
				[
					2.6633630586051003,
					5.548673038760539
				],
				[
					3.1072569017060085,
					6.88035456806306
				],
				[
					3.1072569017060085,
					7.768142254264746
				],
				[
					3.5511507448068,
					9.765664548218542
				],
				[
					3.995044587907592,
					11.097346077521063
				],
				[
					4.4389384310085,
					12.872921449924434
				],
				[
					4.660885352558896,
					14.426549900777381
				],
				[
					4.882832274109292,
					16.20212527318075
				],
				[
					5.1047791956598045,
					17.7557537240337
				],
				[
					5.1047791956598045,
					19.309382174886647
				],
				[
					5.1047791956598045,
					21.084957547290017
				],
				[
					5.1047791956598045,
					22.416639076592553
				],
				[
					5.1047791956598045,
					24.19221444899592
				],
				[
					5.1047791956598045,
					25.52389597829844
				],
				[
					5.1047791956598045,
					27.07752442915139
				],
				[
					5.1047791956598045,
					28.1872590369035
				],
				[
					5.1047791956598045,
					29.29699364465561
				],
				[
					5.1047791956598045,
					30.85062209550856
				],
				[
					4.882832274109292,
					31.960356703260654
				],
				[
					4.882832274109292,
					33.07009131101277
				],
				[
					4.660885352558896,
					33.95787899721445
				],
				[
					4.660885352558896,
					35.28956052651697
				],
				[
					4.660885352558896,
					37.065135898920346
				],
				[
					4.4389384310085,
					37.95292358512203
				],
				[
					4.4389384310085,
					39.284605114424565
				],
				[
					4.4389384310085,
					40.17239280062625
				],
				[
					4.4389384310085,
					41.50407432992877
				],
				[
					4.4389384310085,
					42.61380893768088
				],
				[
					4.4389384310085,
					44.16743738853381
				],
				[
					4.4389384310085,
					45.499118917836356
				],
				[
					4.4389384310085,
					47.27469429023973
				],
				[
					4.4389384310085,
					48.828322741092684
				],
				[
					4.216991509457988,
					50.160004270395206
				],
				[
					3.995044587907592,
					51.269738878147294
				],
				[
					3.773097666357196,
					52.379473485899425
				],
				[
					3.773097666357196,
					52.82336732900025
				],
				[
					3.5511507448068,
					53.48920809365152
				],
				[
					3.5511507448068,
					53.933101936752365
				],
				[
					3.3292038232564045,
					54.598942701403615
				],
				[
					3.3292038232564045,
					55.04283654450447
				],
				[
					3.3292038232564045,
					55.70867730915574
				],
				[
					3.3292038232564045,
					56.15257115225656
				],
				[
					3.1072569017060085,
					57.04035883845826
				],
				[
					2.6633630586051003,
					58.37204036776078
				],
				[
					2.4414161370547043,
					59.25982805396245
				],
				[
					2.2194692155043083,
					60.147615740164156
				],
				[
					1.997522293953796,
					61.035403426365825
				],
				[
					1.997522293953796,
					62.14513803411795
				],
				[
					1.5536284508530043,
					63.25487264187005
				],
				[
					1.3316815293026083,
					64.14266032807174
				],
				[
					1.1097346077522123,
					65.03044801427342
				],
				[
					0.8877876862017,
					65.91823570047512
				],
				[
					0.6658407646513042,
					67.02797030822721
				],
				[
					0.4438938431009082,
					67.69381107287846
				],
				[
					0.4438938431009082,
					68.13770491597931
				],
				[
					0.22194692155051235,
					68.80354568063058
				],
				[
					0.22194692155051235,
					69.24743952373143
				],
				[
					0,
					69.69133336683225
				],
				[
					0,
					69.91328028838268
				],
				[
					-0.2219469215503959,
					70.1352272099331
				],
				[
					-0.2219469215503959,
					70.35717413148353
				],
				[
					-0.2219469215503959,
					70.57912105303396
				],
				[
					-0.4438938431007918,
					71.24496181768521
				],
				[
					-0.8877876862015835,
					71.68885566078606
				],
				[
					-1.109734607752096,
					72.1327495038869
				],
				[
					-1.553628450852888,
					72.57664334698775
				],
				[
					-1.7755753724032834,
					73.02053719008858
				],
				[
					-1.997522293953796,
					73.242484111639
				],
				[
					-2.4414161370545875,
					73.46443103318943
				],
				[
					-2.4414161370545875,
					73.68637795473985
				],
				[
					-2.663363058604984,
					73.68637795473985
				],
				[
					-2.88530998015538,
					73.68637795473985
				],
				[
					-3.107256901705776,
					73.68637795473985
				],
				[
					-3.329203823256288,
					73.90832487629028
				],
				[
					-3.551150744806684,
					73.90832487629028
				],
				[
					-3.551150744806684,
					73.90832487629028
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 399,
			"versionNonce": 1637649323,
			"isDeleted": false,
			"id": "X5dwA4BwpquNhnm6AUM3I",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1155.256757968427,
			"y": 93.01355875700065,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 9.099823783567281,
			"height": 0.4438938431008501,
			"seed": 236662147,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726442,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6658407646511878,
					0
				],
				[
					1.7755753724034005,
					0
				],
				[
					3.3292038232562886,
					0
				],
				[
					4.66088535255878,
					0.22194692155042506
				],
				[
					5.770619960310993,
					0.4438938431008501
				],
				[
					6.214513803411785,
					0.4438938431008501
				],
				[
					7.5461953327142774,
					0.4438938431008501
				],
				[
					8.433983018915978,
					0.4438938431008501
				],
				[
					8.87787686201677,
					0.4438938431008501
				],
				[
					9.099823783567281,
					0.4438938431008501
				],
				[
					9.099823783567281,
					0.4438938431008501
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 401,
			"versionNonce": 2097387653,
			"isDeleted": false,
			"id": "mXADlz6ML6IrOwjTC5cB3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1151.48366030207,
			"y": 99.00612563886204,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 11.76318684217238,
			"height": 1.9975222939537964,
			"seed": 1992247459,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8877876862017002,
					0
				],
				[
					1.3316815293026085,
					0
				],
				[
					2.2194692155041924,
					0
				],
				[
					3.329203823256405,
					0.22194692155042506
				],
				[
					5.104779195659689,
					0.4438938431008501
				],
				[
					5.770619960310993,
					0.8877876862016857
				],
				[
					7.3242484111638815,
					1.1097346077521106
				],
				[
					8.65592994046649,
					1.5536284508529608
				],
				[
					10.431505312869772,
					1.7755753724033714
				],
				[
					11.319292999071473,
					1.9975222939537964
				],
				[
					11.541239920621987,
					1.9975222939537964
				],
				[
					11.76318684217238,
					1.9975222939537964
				],
				[
					11.76318684217238,
					1.9975222939537964
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 471,
			"versionNonce": 2030296651,
			"isDeleted": false,
			"id": "du0FQsmOpORyL4spWrHG_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1194.9852569259524,
			"y": 65.270193563198,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 16.202125273180766,
			"height": 71.68885566078606,
			"seed": 1818786563,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.22194692155039594,
					0.6658407646512606
				],
				[
					-0.6658407646513043,
					1.3316815293025213
				],
				[
					-1.1097346077520962,
					2.441416137054632
				],
				[
					-1.3316815293024922,
					3.5511507448067428
				],
				[
					-1.3316815293024922,
					4.216991509458003
				],
				[
					-1.5536284508530045,
					5.104779195659689
				],
				[
					-1.7755753724034005,
					5.992566881861375
				],
				[
					-1.9975222939537964,
					7.990089175815156
				],
				[
					-2.441416137054588,
					9.987611469768954
				],
				[
					-2.6633630586049843,
					11.5412399206219
				],
				[
					-2.8853099801554967,
					13.31681529302527
				],
				[
					-3.1072569017058926,
					14.870443743878216
				],
				[
					-3.3292038232562886,
					16.646019116281586
				],
				[
					-3.3292038232562886,
					18.199647567134534
				],
				[
					-3.3292038232562886,
					19.53132909643707
				],
				[
					-3.3292038232562886,
					20.641063704189165
				],
				[
					-3.3292038232562886,
					21.9727452334917
				],
				[
					-3.3292038232562886,
					23.526373684344648
				],
				[
					-3.3292038232562886,
					24.63610829209676
				],
				[
					-3.3292038232562886,
					26.1897367429497
				],
				[
					-3.3292038232562886,
					27.74336519380265
				],
				[
					-3.3292038232562886,
					29.74088748775643
				],
				[
					-3.3292038232562886,
					31.294515938609393
				],
				[
					-3.773097666357197,
					32.626197467911915
				],
				[
					-3.773097666357197,
					34.17982591876486
				],
				[
					-3.773097666357197,
					35.5115074480674
				],
				[
					-3.773097666357197,
					37.065135898920346
				],
				[
					-3.773097666357197,
					39.28460511442455
				],
				[
					-3.3292038232562886,
					41.72602125147918
				],
				[
					-3.3292038232562886,
					43.72354354543296
				],
				[
					-3.1072569017058926,
					45.05522507473552
				],
				[
					-2.8853099801554967,
					46.60885352558846
				],
				[
					-2.441416137054588,
					47.71858813334056
				],
				[
					-2.2194692155041924,
					48.60637581954225
				],
				[
					-1.5536284508530045,
					49.71611042729435
				],
				[
					-1.1097346077520962,
					51.269738878147294
				],
				[
					-0.6658407646513043,
					52.379473485899396
				],
				[
					-0.4438938431007919,
					53.48920809365152
				],
				[
					0,
					55.04283654450447
				],
				[
					0.22194692155039594,
					55.70867730915571
				],
				[
					0.6658407646513043,
					56.81841191690784
				],
				[
					1.3316815293024922,
					57.484252681559084
				],
				[
					1.5536284508530045,
					58.15009344621036
				],
				[
					1.9975222939537964,
					59.03788113241203
				],
				[
					2.2194692155041924,
					59.7037218970633
				],
				[
					2.441416137054588,
					60.147615740164156
				],
				[
					3.1072569017058926,
					60.813456504815406
				],
				[
					3.3292038232562886,
					61.47929726946668
				],
				[
					3.773097666357197,
					61.92319111256753
				],
				[
					4.216991509457989,
					62.58903187721877
				],
				[
					4.66088535255878,
					62.8109787987692
				],
				[
					5.104779195659689,
					63.25487264187005
				],
				[
					5.326726117210085,
					63.698766484970896
				],
				[
					5.770619960310993,
					64.14266032807171
				],
				[
					5.992566881861389,
					64.36460724962214
				],
				[
					6.436460724962181,
					64.58655417117257
				],
				[
					6.8803545680630895,
					65.25239493582384
				],
				[
					7.1023014896134855,
					65.47434185737427
				],
				[
					7.3242484111638815,
					65.9182357004751
				],
				[
					7.5461953327142774,
					66.14018262202552
				],
				[
					7.990089175815186,
					66.36212954357593
				],
				[
					8.433983018915978,
					66.80602338667678
				],
				[
					8.655929940466374,
					67.02797030822721
				],
				[
					9.099823783567281,
					67.24991722977761
				],
				[
					9.321770705117677,
					67.47186415132803
				],
				[
					9.543717626668073,
					67.91575799442889
				],
				[
					9.765664548218586,
					67.91575799442889
				],
				[
					9.987611469768982,
					68.13770491597931
				],
				[
					9.987611469768982,
					68.35965183752973
				],
				[
					10.209558391319378,
					68.58159875908017
				],
				[
					10.65345223442017,
					69.02549260218098
				],
				[
					10.875399155970564,
					69.24743952373142
				],
				[
					11.097346077521077,
					69.46938644528183
				],
				[
					11.319292999071473,
					69.91328028838268
				],
				[
					11.319292999071473,
					70.1352272099331
				],
				[
					11.76318684217238,
					70.57912105303393
				],
				[
					11.985133763722779,
					71.02301489613477
				],
				[
					12.207080685273173,
					71.46690873923562
				],
				[
					12.42902760682357,
					71.68885566078606
				],
				[
					12.42902760682357,
					71.24496181768521
				],
				[
					12.42902760682357,
					70.57912105303393
				],
				[
					12.42902760682357,
					69.46938644528183
				],
				[
					12.42902760682357,
					69.46938644528183
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 406,
			"versionNonce": 1885880293,
			"isDeleted": false,
			"id": "S09Nm9rV1COuZrdklVGnj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1212.741010649986,
			"y": 68.37745046490392,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.992566881861273,
			"height": 11.097346077521063,
			"seed": 666598179,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.22194692155039594,
					0.22194692155042506
				],
				[
					-1.1097346077520962,
					0.6658407646512606
				],
				[
					-1.775575372403284,
					1.3316815293025357
				],
				[
					-2.441416137054588,
					2.441416137054632
				],
				[
					-2.8853099801554967,
					3.1072569017058926
				],
				[
					-3.5511507448066846,
					4.216991509458003
				],
				[
					-4.438938431008385,
					5.548673038760539
				],
				[
					-5.326726117210085,
					6.658407646512635
				],
				[
					-5.770619960310877,
					7.324248411163896
				],
				[
					-5.992566881861273,
					8.212036097365582
				],
				[
					-5.992566881861273,
					8.877876862016857
				],
				[
					-5.992566881861273,
					9.543717626668117
				],
				[
					-5.992566881861273,
					10.209558391319378
				],
				[
					-5.992566881861273,
					10.653452234420213
				],
				[
					-5.992566881861273,
					11.097346077521063
				],
				[
					-5.992566881861273,
					10.431505312869803
				],
				[
					-5.992566881861273,
					9.987611469768954
				],
				[
					-5.992566881861273,
					9.987611469768954
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 411,
			"versionNonce": 1495784683,
			"isDeleted": false,
			"id": "xn_r03e6xyOhztpGdoNE8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1206.3045499250238,
			"y": 68.59939738645434,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.326726117210085,
			"height": 10.875399155970639,
			"seed": 2099653539,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.22194692155039594,
					-0.22194692155042509
				],
				[
					0.4438938431009083,
					0
				],
				[
					0.6658407646513043,
					0.22194692155042509
				],
				[
					1.3316815293024922,
					1.3316815293025215
				],
				[
					1.5536284508528881,
					1.7755753724033716
				],
				[
					1.9975222939537964,
					3.551150744806743
				],
				[
					2.4414161370547047,
					4.882832274109265
				],
				[
					2.8853099801554967,
					5.770619960310951
				],
				[
					3.1072569017058926,
					6.658407646512637
				],
				[
					3.3292038232562886,
					7.102301489613472
				],
				[
					3.3292038232562886,
					7.768142254264747
				],
				[
					3.773097666357197,
					8.212036097365583
				],
				[
					3.995044587907593,
					8.655929940466434
				],
				[
					4.216991509457989,
					9.099823783567269
				],
				[
					4.216991509457989,
					9.321770705117695
				],
				[
					4.660885352558897,
					9.987611469768956
				],
				[
					4.882832274109293,
					10.43150531286979
				],
				[
					5.104779195659689,
					10.43150531286979
				],
				[
					5.104779195659689,
					10.653452234420214
				],
				[
					5.326726117210085,
					10.653452234420214
				],
				[
					5.326726117210085,
					10.43150531286979
				],
				[
					5.326726117210085,
					10.43150531286979
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 399,
			"versionNonce": 327220037,
			"isDeleted": false,
			"id": "tJwBtCN8GyLGryMsSqxvB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1221.6188875120029,
			"y": 73.03833581746278,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.990089175815186,
			"height": 0.4438938431008356,
			"seed": 1178530467,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.22194692155039594,
					0
				],
				[
					-0.4438938431007919,
					0
				],
				[
					0.6658407646513043,
					0.2219469215504105
				],
				[
					1.9975222939537964,
					0.4438938431008356
				],
				[
					3.551150744806801,
					0.4438938431008356
				],
				[
					4.438938431008385,
					0.4438938431008356
				],
				[
					5.548673038760597,
					0.4438938431008356
				],
				[
					6.436460724962181,
					0.4438938431008356
				],
				[
					7.3242484111638815,
					0.2219469215504105
				],
				[
					7.546195332714394,
					0
				],
				[
					7.546195332714394,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 400,
			"versionNonce": 496174987,
			"isDeleted": false,
			"id": "LakuMayj6DgaQon-pF5Xx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1225.8358790214609,
			"y": 68.82134430800477,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 0.22194692155039594,
			"height": 7.324248411163896,
			"seed": 231258563,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.2219469215504105
				],
				[
					0,
					1.1097346077520962
				],
				[
					0,
					2.219469215504207
				],
				[
					0,
					3.1072569017058926
				],
				[
					0,
					4.438938431008414
				],
				[
					0,
					5.326726117210099
				],
				[
					0,
					6.658407646512635
				],
				[
					0,
					7.102301489613471
				],
				[
					0,
					7.324248411163896
				],
				[
					0,
					7.102301489613471
				],
				[
					0.22194692155039594,
					6.880354568063046
				],
				[
					0.22194692155039594,
					6.880354568063046
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 404,
			"versionNonce": 2125154981,
			"isDeleted": false,
			"id": "RsQWd8Kd8CxMw23FLFvaF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1240.4843758437887,
			"y": 68.37745046490392,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 4.438938431008501,
			"height": 7.9900891758151715,
			"seed": 1561024643,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.22194692155051238,
					-0.22194692155042506
				],
				[
					0.22194692155051238,
					0.6658407646512606
				],
				[
					0.22194692155051238,
					1.1097346077521106
				],
				[
					-0.22194692155039594,
					2.2194692155042213
				],
				[
					-0.6658407646511878,
					3.1072569017058926
				],
				[
					-1.1097346077519796,
					4.216991509458003
				],
				[
					-1.775575372403284,
					4.882832274109264
				],
				[
					-2.2194692155041924,
					5.548673038760539
				],
				[
					-2.8853099801553803,
					6.436460724962225
				],
				[
					-3.1072569017057763,
					6.658407646512635
				],
				[
					-3.5511507448066846,
					7.1023014896134855
				],
				[
					-3.7730976663570805,
					7.324248411163896
				],
				[
					-3.995044587907593,
					7.546195332714321
				],
				[
					-3.995044587907593,
					7.768142254264746
				],
				[
					-4.216991509457989,
					7.768142254264746
				],
				[
					-4.216991509457989,
					7.768142254264746
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 407,
			"versionNonce": 209706539,
			"isDeleted": false,
			"id": "86brf9gY9Cbit6-O1f2G9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1236.7112781774315,
			"y": 68.82134430800477,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.5511507448066846,
			"height": 8.655929940466418,
			"seed": 1211755971,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.22194692155041051
				],
				[
					0.22194692155039594,
					0.8877876862016858
				],
				[
					0.22194692155039594,
					1.9975222939537822
				],
				[
					0.6658407646513043,
					2.8853099801554682
				],
				[
					0.8877876862017002,
					3.3292038232563184
				],
				[
					1.3316815293024922,
					4.216991509458004
				],
				[
					1.775575372403284,
					5.10477919565969
				],
				[
					2.2194692155041924,
					5.770619960310951
				],
				[
					2.441416137054588,
					6.214513803411786
				],
				[
					2.6633630586051007,
					6.658407646512637
				],
				[
					3.1072569017058926,
					6.880354568063047
				],
				[
					3.3292038232562886,
					7.3242484111638975
				],
				[
					3.3292038232562886,
					7.546195332714323
				],
				[
					3.5511507448066846,
					7.768142254264733
				],
				[
					3.5511507448066846,
					7.990089175815158
				],
				[
					3.5511507448066846,
					8.212036097365583
				],
				[
					3.5511507448066846,
					8.433983018916008
				],
				[
					3.5511507448066846,
					8.655929940466418
				],
				[
					3.5511507448066846,
					8.655929940466418
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 423,
			"versionNonce": 1653911045,
			"isDeleted": false,
			"id": "5F0Jp-JpU8G6nFTeRikRi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1244.2574735101457,
			"y": 76.14559271916866,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.8803545680630895,
			"height": 6.4364607249622106,
			"seed": 243813859,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.6658407646512606
				],
				[
					0,
					-1.3316815293025213
				],
				[
					0.22194692155039594,
					-1.7755753724033714
				],
				[
					0.4438938431007919,
					-1.9975222939537964
				],
				[
					0.8877876862017002,
					-2.219469215504207
				],
				[
					1.5536284508530045,
					-2.219469215504207
				],
				[
					2.6633630586051007,
					-2.219469215504207
				],
				[
					3.329203823256405,
					-1.9975222939537964
				],
				[
					3.995044587907593,
					-1.7755753724033714
				],
				[
					4.660885352558897,
					-1.3316815293025213
				],
				[
					5.104779195659689,
					-0.8877876862016857
				],
				[
					5.326726117210085,
					-0.4438938431008501
				],
				[
					5.992566881861389,
					0.4438938431008356
				],
				[
					6.436460724962181,
					1.1097346077521106
				],
				[
					6.658407646512694,
					1.7755753724033714
				],
				[
					6.8803545680630895,
					2.441416137054632
				],
				[
					6.8803545680630895,
					3.1072569017058926
				],
				[
					6.8803545680630895,
					3.7730976663571534
				],
				[
					6.8803545680630895,
					3.995044587907578
				],
				[
					6.658407646512694,
					4.216991509458003
				],
				[
					6.436460724962181,
					4.216991509458003
				],
				[
					5.992566881861389,
					4.216991509458003
				],
				[
					5.770619960310993,
					4.216991509458003
				],
				[
					5.548673038760597,
					4.216991509458003
				],
				[
					5.326726117210085,
					4.216991509458003
				],
				[
					4.660885352558897,
					3.995044587907578
				],
				[
					4.438938431008385,
					3.995044587907578
				],
				[
					4.216991509457989,
					3.7730976663571534
				],
				[
					3.329203823256405,
					2.8853099801554674
				],
				[
					2.8853099801554967,
					2.663363058605057
				],
				[
					2.6633630586051007,
					2.441416137054632
				],
				[
					2.6633630586051007,
					2.219469215504207
				],
				[
					2.441416137054588,
					2.219469215504207
				],
				[
					2.441416137054588,
					1.9975222939537964
				],
				[
					2.441416137054588,
					1.9975222939537964
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 433,
			"versionNonce": 1087955147,
			"isDeleted": false,
			"id": "7JMj4R6ktAKf96wOXx1jT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1207.4142845327758,
			"y": 91.2379833845973,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.1023014896134855,
			"height": 11.31929299907149,
			"seed": 127169539,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4438938431008356
				],
				[
					0,
					1.1097346077521106
				],
				[
					0,
					1.9975222939537964
				],
				[
					0.4438938431007919,
					2.663363058605057
				],
				[
					1.3316815293026085,
					3.3292038232563175
				],
				[
					1.7755753724034005,
					3.5511507448067428
				],
				[
					3.1072569017058926,
					3.5511507448067428
				],
				[
					3.995044587907593,
					3.3292038232563175
				],
				[
					4.882832274109293,
					2.885309980155482
				],
				[
					5.770619960310993,
					2.219469215504207
				],
				[
					6.214513803411785,
					1.7755753724033714
				],
				[
					6.658407646512694,
					0.8877876862016857
				],
				[
					7.1023014896134855,
					-0.4438938431008356
				],
				[
					7.1023014896134855,
					-0.8877876862016857
				],
				[
					7.1023014896134855,
					-1.5536284508529463
				],
				[
					7.1023014896134855,
					-1.7755753724033714
				],
				[
					7.1023014896134855,
					-1.5536284508529463
				],
				[
					6.8803545680630895,
					-0.8877876862016857
				],
				[
					6.658407646512694,
					-0.22194692155042506
				],
				[
					6.214513803411785,
					1.3316815293025213
				],
				[
					6.214513803411785,
					2.441416137054632
				],
				[
					6.214513803411785,
					4.438938431008428
				],
				[
					6.214513803411785,
					5.326726117210114
				],
				[
					6.214513803411785,
					7.324248411163896
				],
				[
					5.992566881861389,
					8.212036097365582
				],
				[
					5.770619960310993,
					8.877876862016842
				],
				[
					5.326726117210085,
					9.321770705117693
				],
				[
					4.660885352558897,
					9.543717626668117
				],
				[
					4.216991509457989,
					9.543717626668117
				],
				[
					3.551150744806801,
					9.543717626668117
				],
				[
					2.8853099801554967,
					9.099823783567267
				],
				[
					2.2194692155041924,
					8.655929940466432
				],
				[
					1.5536284508530045,
					8.433983018916006
				],
				[
					0.8877876862017002,
					7.990089175815156
				],
				[
					0.6658407646513043,
					7.546195332714321
				],
				[
					0.4438938431007919,
					7.1023014896134855
				],
				[
					0.22194692155039594,
					6.658407646512635
				],
				[
					0,
					6.4364607249622106
				],
				[
					0.22194692155039594,
					6.2145138034117995
				],
				[
					0.6658407646513043,
					5.992566881861375
				],
				[
					1.3316815293026085,
					5.5486730387605245
				],
				[
					1.9975222939537964,
					5.104779195659689
				],
				[
					2.2194692155041924,
					4.882832274109264
				],
				[
					2.2194692155041924,
					4.6608853525588385
				],
				[
					2.2194692155041924,
					4.6608853525588385
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 399,
			"versionNonce": 2117772645,
			"isDeleted": false,
			"id": "GpbkoKCR4y8PbmEks5MuN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1228.055348236965,
			"y": 93.01355875700068,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.880354568062973,
			"height": 0.4438938431008356,
			"seed": 1767081571,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.22194692155042506
				],
				[
					-0.6658407646511878,
					0.22194692155042506
				],
				[
					-1.5536284508528881,
					0.22194692155042506
				],
				[
					-2.441416137054588,
					0.22194692155042506
				],
				[
					-3.5511507448066846,
					0.22194692155042506
				],
				[
					-4.882832274109176,
					0.22194692155042506
				],
				[
					-5.770619960310877,
					0.22194692155042506
				],
				[
					-6.436460724962181,
					0.4438938431008356
				],
				[
					-6.658407646512577,
					0.4438938431008356
				],
				[
					-6.880354568062973,
					0.4438938431008356
				],
				[
					-6.880354568062973,
					0.4438938431008356
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 399,
			"versionNonce": 339251051,
			"isDeleted": false,
			"id": "yzSOb9doR0W3W0KEgmnIe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1224.7261444137087,
			"y": 89.0185141690931,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 0.4438938431009083,
			"height": 7.990089175815156,
			"seed": 2046899587,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.6658407646512606
				],
				[
					0,
					1.3316815293025213
				],
				[
					0,
					2.441416137054632
				],
				[
					0.22194692155039594,
					3.3292038232563175
				],
				[
					0.4438938431009083,
					4.882832274109264
				],
				[
					0.4438938431009083,
					5.77061996031095
				],
				[
					0.4438938431009083,
					7.102301489613471
				],
				[
					0.4438938431009083,
					7.324248411163896
				],
				[
					0.4438938431009083,
					7.768142254264731
				],
				[
					0.4438938431009083,
					7.990089175815156
				],
				[
					0.4438938431009083,
					7.990089175815156
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 447,
			"versionNonce": 1424666821,
			"isDeleted": false,
			"id": "s6_GH5oJJDEsNZh4QKE38",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1238.9307473929357,
			"y": 88.79656724754267,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 10.431505312869772,
			"height": 11.98513376372275,
			"seed": 307777699,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.22194692155039586,
					0.22194692155042506
				],
				[
					-0.4438938431009081,
					1.1097346077521106
				],
				[
					-0.4438938431009081,
					1.7755753724033714
				],
				[
					-0.4438938431009081,
					2.663363058605057
				],
				[
					-0.4438938431009081,
					3.5511507448067428
				],
				[
					0.22194692155039586,
					4.438938431008428
				],
				[
					0.665840764651304,
					5.104779195659689
				],
				[
					1.1097346077520958,
					5.77061996031095
				],
				[
					1.5536284508528875,
					6.214513803411785
				],
				[
					2.2194692155041915,
					6.4364607249622106
				],
				[
					3.1072569017058913,
					6.4364607249622106
				],
				[
					3.9950445879075915,
					6.4364607249622106
				],
				[
					5.326726117210083,
					6.214513803411785
				],
				[
					6.436460724962179,
					5.5486730387605245
				],
				[
					7.324248411163879,
					4.882832274109264
				],
				[
					7.768142254264671,
					3.995044587907578
				],
				[
					7.990089175815183,
					3.1072569017058926
				],
				[
					7.990089175815183,
					2.441416137054632
				],
				[
					8.212036097365578,
					1.5536284508529463
				],
				[
					8.212036097365578,
					1.1097346077521106
				],
				[
					8.212036097365578,
					0.8877876862016857
				],
				[
					8.212036097365578,
					0.6658407646512606
				],
				[
					7.990089175815183,
					0.6658407646512606
				],
				[
					7.990089175815183,
					1.5536284508529463
				],
				[
					7.768142254264671,
					2.663363058605057
				],
				[
					7.768142254264671,
					3.5511507448067428
				],
				[
					7.768142254264671,
					4.438938431008428
				],
				[
					7.768142254264671,
					5.77061996031095
				],
				[
					7.768142254264671,
					6.4364607249622106
				],
				[
					7.768142254264671,
					7.324248411163896
				],
				[
					7.768142254264671,
					7.768142254264746
				],
				[
					7.102301489613483,
					8.655929940466432
				],
				[
					6.658407646512691,
					9.987611469768954
				],
				[
					6.214513803411783,
					10.653452234420213
				],
				[
					5.548673038760479,
					11.319292999071473
				],
				[
					4.882832274109291,
					11.763186842172324
				],
				[
					4.438938431008383,
					11.98513376372275
				],
				[
					3.9950445879075915,
					11.98513376372275
				],
				[
					3.3292038232562873,
					11.98513376372275
				],
				[
					2.6633630586051,
					11.98513376372275
				],
				[
					2.2194692155041915,
					11.98513376372275
				],
				[
					1.3316815293024917,
					11.98513376372275
				],
				[
					0.8877876862016999,
					11.98513376372275
				],
				[
					0.4438938431009081,
					11.98513376372275
				],
				[
					0.22194692155039586,
					11.98513376372275
				],
				[
					-0.4438938431009081,
					11.98513376372275
				],
				[
					-0.665840764651304,
					11.763186842172324
				],
				[
					-1.1097346077520958,
					11.763186842172324
				],
				[
					-1.3316815293024917,
					11.5412399206219
				],
				[
					-1.5536284508528875,
					11.097346077521063
				],
				[
					-1.9975222939537958,
					10.653452234420213
				],
				[
					-1.9975222939537958,
					10.431505312869788
				],
				[
					-2.2194692155041915,
					9.987611469768954
				],
				[
					-2.2194692155041915,
					9.765664548218528
				],
				[
					-1.9975222939537958,
					9.765664548218528
				],
				[
					-1.7755753724033998,
					9.765664548218528
				],
				[
					-1.3316815293024917,
					9.987611469768954
				],
				[
					-1.3316815293024917,
					9.987611469768954
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 429,
			"versionNonce": 1223256587,
			"isDeleted": false,
			"id": "Fk02r7N-M9ktFMK38cBfr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1252.0256157644105,
			"y": 98.78417871731162,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.104779195659689,
			"height": 6.436460724962225,
			"seed": 94069283,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.22194692155042506
				],
				[
					0,
					0.4438938431008356
				],
				[
					-0.22194692155039597,
					0.4438938431008356
				],
				[
					-0.22194692155039597,
					0.22194692155042506
				],
				[
					-0.22194692155039597,
					-0.4438938431008356
				],
				[
					-0.22194692155039597,
					-1.3316815293025213
				],
				[
					-0.22194692155039597,
					-1.9975222939537964
				],
				[
					0,
					-2.441416137054632
				],
				[
					0,
					-2.663363058605057
				],
				[
					0.22194692155039597,
					-2.663363058605057
				],
				[
					0.6658407646511879,
					-2.663363058605057
				],
				[
					1.1097346077520964,
					-2.441416137054632
				],
				[
					1.5536284508528884,
					-1.9975222939537964
				],
				[
					1.9975222939537967,
					-1.5536284508529463
				],
				[
					2.663363058604985,
					-1.1097346077521106
				],
				[
					3.329203823256289,
					-0.4438938431008356
				],
				[
					3.7730976663571973,
					0.22194692155042506
				],
				[
					3.9950445879075933,
					0.4438938431008356
				],
				[
					4.438938431008386,
					1.1097346077521106
				],
				[
					4.660885352558781,
					1.7755753724033714
				],
				[
					4.660885352558781,
					1.9975222939537964
				],
				[
					4.660885352558781,
					2.441416137054632
				],
				[
					4.660885352558781,
					2.663363058605057
				],
				[
					4.660885352558781,
					3.1072569017058926
				],
				[
					4.660885352558781,
					3.3292038232563175
				],
				[
					4.438938431008386,
					3.3292038232563175
				],
				[
					4.21699150945799,
					3.5511507448067428
				],
				[
					3.551150744806685,
					3.7730976663571676
				],
				[
					3.329203823256289,
					3.7730976663571676
				],
				[
					2.663363058604985,
					3.7730976663571676
				],
				[
					2.219469215504193,
					3.7730976663571676
				],
				[
					1.5536284508528884,
					3.5511507448067428
				],
				[
					0.8877876862015839,
					3.1072569017058926
				],
				[
					0.22194692155039597,
					2.885309980155482
				],
				[
					-0.22194692155039597,
					2.441416137054632
				],
				[
					-0.44389384310090835,
					1.7755753724033714
				],
				[
					-0.44389384310090835,
					1.3316815293025213
				],
				[
					-0.44389384310090835,
					0.8877876862016857
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
			"type": "freedraw",
			"version": 434,
			"versionNonce": 608325669,
			"isDeleted": false,
			"id": "gfTlxH_ZCsHWxjgV83m-A",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1208.524019140528,
			"y": 119.86913626460165,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 10.875399155970682,
			"height": 10.209558391319378,
			"seed": 709776995,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8877876862017002,
					0
				],
				[
					2.2194692155043088,
					0
				],
				[
					3.551150744806801,
					0.22194692155042506
				],
				[
					4.438938431008501,
					0.22194692155042506
				],
				[
					5.992566881861389,
					0.6658407646512752
				],
				[
					7.3242484111638815,
					0.8877876862016711
				],
				[
					7.990089175815186,
					0.8877876862016711
				],
				[
					8.212036097365582,
					1.1097346077520962
				],
				[
					8.65592994046649,
					1.1097346077520962
				],
				[
					8.877876862016885,
					1.1097346077520962
				],
				[
					8.65592994046649,
					1.3316815293025213
				],
				[
					7.76814225426479,
					1.5536284508529463
				],
				[
					6.8803545680630895,
					1.9975222939537964
				],
				[
					5.548673038760597,
					2.6633630586050425
				],
				[
					4.216991509457989,
					3.7730976663571676
				],
				[
					3.773097666357197,
					4.216991509457989
				],
				[
					3.551150744806801,
					4.6608853525588385
				],
				[
					3.3292038232562886,
					5.104779195659689
				],
				[
					2.8853099801554967,
					5.548673038760539
				],
				[
					2.8853099801554967,
					5.770619960310964
				],
				[
					2.6633630586051007,
					6.4364607249622106
				],
				[
					2.6633630586051007,
					6.658407646512635
				],
				[
					2.6633630586051007,
					7.324248411163911
				],
				[
					2.6633630586051007,
					7.768142254264731
				],
				[
					2.6633630586051007,
					8.433983018916006
				],
				[
					2.6633630586051007,
					9.099823783567281
				],
				[
					2.6633630586051007,
					9.321770705117677
				],
				[
					2.8853099801554967,
					9.543717626668103
				],
				[
					3.1072569017058926,
					9.765664548218528
				],
				[
					3.3292038232562886,
					9.987611469768954
				],
				[
					3.773097666357197,
					10.209558391319378
				],
				[
					5.104779195659689,
					10.209558391319378
				],
				[
					5.992566881861389,
					10.209558391319378
				],
				[
					6.658407646512694,
					10.209558391319378
				],
				[
					7.3242484111638815,
					10.209558391319378
				],
				[
					7.990089175815186,
					10.209558391319378
				],
				[
					8.433983018916093,
					9.987611469768954
				],
				[
					8.877876862016885,
					9.765664548218528
				],
				[
					9.321770705117677,
					9.543717626668103
				],
				[
					9.543717626668073,
					9.543717626668103
				],
				[
					9.987611469768982,
					9.321770705117677
				],
				[
					10.43150531286989,
					9.321770705117677
				],
				[
					10.653452234420286,
					9.099823783567281
				],
				[
					10.875399155970682,
					8.877876862016857
				],
				[
					10.875399155970682,
					8.655929940466432
				],
				[
					10.875399155970682,
					8.655929940466432
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 400,
			"versionNonce": 1944449195,
			"isDeleted": false,
			"id": "Bs8W4Jvgw7WMq5nn0Sq9J",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1208.0801252974272,
			"y": 122.97639316630753,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 8.212036097365582,
			"height": 1.3316815293025213,
			"seed": 837968995,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8877876862017002,
					0.22194692155042506
				],
				[
					1.775575372403284,
					0.4438938431008501
				],
				[
					3.1072569017058926,
					0.8877876862017002
				],
				[
					3.995044587907593,
					0.8877876862017002
				],
				[
					5.548673038760481,
					1.1097346077520962
				],
				[
					6.8803545680630895,
					1.3316815293025213
				],
				[
					7.3242484111638815,
					1.3316815293025213
				],
				[
					7.5461953327142774,
					1.3316815293025213
				],
				[
					7.768142254264673,
					1.3316815293025213
				],
				[
					7.990089175815069,
					1.3316815293025213
				],
				[
					8.212036097365582,
					1.3316815293025213
				],
				[
					8.212036097365582,
					1.3316815293025213
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 400,
			"versionNonce": 439288709,
			"isDeleted": false,
			"id": "J3kzh5e3z0aKocn8ZbG60",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1235.1576497265785,
			"y": 123.64223393095881,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 9.321770705117677,
			"height": 0.22194692155042506,
			"seed": 1518856995,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.22194692155039594,
					0
				],
				[
					-0.4438938431007919,
					0
				],
				[
					-1.1097346077520962,
					0
				],
				[
					-2.2194692155041924,
					0
				],
				[
					-3.995044587907593,
					0
				],
				[
					-4.882832274109293,
					0
				],
				[
					-6.658407646512577,
					-0.22194692155042506
				],
				[
					-7.5461953327142774,
					-0.22194692155042506
				],
				[
					-8.212036097365582,
					-0.22194692155042506
				],
				[
					-8.877876862016885,
					-0.22194692155042506
				],
				[
					-9.321770705117677,
					-0.22194692155042506
				],
				[
					-9.321770705117677,
					-0.22194692155042506
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 405,
			"versionNonce": 651731787,
			"isDeleted": false,
			"id": "5J4J-KmFBABNaja5oTpew",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1229.1650828447173,
			"y": 118.75940165684955,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.1097346077519796,
			"height": 9.987611469768954,
			"seed": 1686544867,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.22194692155039594
				],
				[
					0,
					0.8877876862016711
				],
				[
					0,
					1.7755753724033714
				],
				[
					0,
					2.6633630586050425
				],
				[
					0,
					3.7730976663571387
				],
				[
					0,
					4.6608853525588385
				],
				[
					0,
					5.770619960310935
				],
				[
					0,
					7.102301489613456
				],
				[
					0.22194692155039594,
					7.990089175815156
				],
				[
					0.22194692155039594,
					8.655929940466402
				],
				[
					0.4438938431007919,
					9.099823783567253
				],
				[
					0.4438938431007919,
					9.321770705117677
				],
				[
					0.6658407646511878,
					9.543717626668103
				],
				[
					0.8877876862015838,
					9.765664548218528
				],
				[
					1.1097346077519796,
					9.765664548218528
				],
				[
					1.1097346077519796,
					9.987611469768954
				],
				[
					1.1097346077519796,
					9.987611469768954
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 423,
			"versionNonce": 1257130725,
			"isDeleted": false,
			"id": "-Dsn0kqK3S2wB9ikkIwMw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1244.2574735101457,
			"y": 120.7569239508033,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 10.431505312869772,
			"height": 9.765664548218528,
			"seed": 169984707,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.22194692155039594
				],
				[
					0.22194692155039594,
					-0.22194692155039594
				],
				[
					0.4438938431007919,
					-0.22194692155039594
				],
				[
					1.5536284508530045,
					0
				],
				[
					3.551150744806801,
					0.6658407646512752
				],
				[
					4.882832274109293,
					1.1097346077521253
				],
				[
					5.326726117210085,
					1.1097346077521253
				],
				[
					6.658407646512694,
					1.3316815293025503
				],
				[
					8.433983018915978,
					1.5536284508529754
				],
				[
					9.099823783567281,
					1.5536284508529754
				],
				[
					9.54371762666819,
					1.5536284508529754
				],
				[
					9.765664548218586,
					1.5536284508529754
				],
				[
					9.099823783567281,
					1.7755753724033714
				],
				[
					7.990089175815186,
					2.4414161370546466
				],
				[
					5.326726117210085,
					3.7730976663571676
				],
				[
					4.216991509457989,
					4.4389384310084425
				],
				[
					3.551150744806801,
					4.882832274109293
				],
				[
					2.8853099801554967,
					5.548673038760539
				],
				[
					2.2194692155041924,
					5.992566881861389
				],
				[
					1.3316815293026085,
					6.88035456806306
				],
				[
					0.6658407646513043,
					7.324248411163911
				],
				[
					0.22194692155039594,
					7.7681422542647605
				],
				[
					-0.22194692155039594,
					8.21203609736561
				],
				[
					-0.4438938431007919,
					8.655929940466432
				],
				[
					-0.6658407646511878,
					8.877876862016857
				],
				[
					-0.6658407646511878,
					9.099823783567281
				],
				[
					-0.4438938431007919,
					9.321770705117707
				],
				[
					0.4438938431007919,
					9.543717626668132
				],
				[
					1.5536284508530045,
					9.543717626668132
				],
				[
					2.6633630586051007,
					9.543717626668132
				],
				[
					4.438938431008385,
					9.543717626668132
				],
				[
					4.882832274109293,
					9.543717626668132
				],
				[
					5.326726117210085,
					9.321770705117707
				],
				[
					5.326726117210085,
					9.099823783567281
				],
				[
					5.326726117210085,
					9.099823783567281
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 401,
			"versionNonce": 1511784939,
			"isDeleted": false,
			"id": "tCugn8hQyxojcUGWQ6xkU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1243.1477389023937,
			"y": 124.30807469561006,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 8.877876862016885,
			"height": 3.1072569017058926,
			"seed": 1997364451,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6658407646513042,
					0.4438938431008501
				],
				[
					1.7755753724034,
					0.8877876862017002
				],
				[
					3.107256901705892,
					1.3316815293025503
				],
				[
					4.4389384310085,
					1.7755753724033714
				],
				[
					6.214513803411784,
					2.2194692155042213
				],
				[
					6.880354568063089,
					2.2194692155042213
				],
				[
					7.546195332714276,
					2.6633630586050714
				],
				[
					7.768142254264788,
					2.6633630586050714
				],
				[
					7.990089175815184,
					2.8853099801554967
				],
				[
					8.433983018915976,
					2.8853099801554967
				],
				[
					8.65592994046649,
					3.1072569017058926
				],
				[
					8.877876862016885,
					3.1072569017058926
				],
				[
					8.877876862016885,
					3.1072569017058926
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 422,
			"versionNonce": 1728947781,
			"isDeleted": false,
			"id": "CLvC_Mt6TFDDglEcjv_8h",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1258.018182646272,
			"y": 131.41037618522356,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.770619960310877,
			"height": 4.882832274109264,
			"seed": 924030787,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.22194692155042506
				],
				[
					-0.22194692155039594,
					0.22194692155042506
				],
				[
					-0.4438938431009083,
					0.22194692155042506
				],
				[
					-0.6658407646513043,
					0.22194692155042506
				],
				[
					-1.5536284508530045,
					-1.1097346077520962
				],
				[
					-1.7755753724034005,
					-1.5536284508529463
				],
				[
					-1.9975222939537964,
					-2.4414161370546172
				],
				[
					-1.9975222939537964,
					-3.1072569017058926
				],
				[
					-1.7755753724034005,
					-3.3292038232563175
				],
				[
					-1.3316815293026085,
					-3.5511507448067428
				],
				[
					-0.6658407646513043,
					-3.5511507448067428
				],
				[
					0,
					-3.5511507448067428
				],
				[
					0.6658407646511878,
					-3.5511507448067428
				],
				[
					1.3316815293024922,
					-3.3292038232563175
				],
				[
					1.9975222939537964,
					-2.8853099801554674
				],
				[
					2.441416137054588,
					-2.4414161370546172
				],
				[
					2.6633630586049843,
					-2.2194692155042213
				],
				[
					3.1072569017058926,
					-1.7755753724033714
				],
				[
					3.3292038232562886,
					-1.3316815293025213
				],
				[
					3.7730976663570805,
					-0.6658407646512461
				],
				[
					3.7730976663570805,
					-0.22194692155042506
				],
				[
					3.7730976663570805,
					0.22194692155042506
				],
				[
					3.7730976663570805,
					0.6658407646512752
				],
				[
					3.7730976663570805,
					0.8877876862017002
				],
				[
					3.3292038232562886,
					1.3316815293025213
				],
				[
					3.1072569017058926,
					1.3316815293025213
				],
				[
					2.8853099801553803,
					1.3316815293025213
				],
				[
					2.6633630586049843,
					1.3316815293025213
				],
				[
					1.9975222939537964,
					1.1097346077520962
				],
				[
					1.775575372403284,
					0.8877876862017002
				],
				[
					1.3316815293024922,
					0.6658407646512752
				],
				[
					1.1097346077520962,
					0.22194692155042506
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
			"type": "freedraw",
			"version": 437,
			"versionNonce": 381324427,
			"isDeleted": false,
			"id": "qUlLUzbKvJ-tH-ByUShJ6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1263.788802606583,
			"y": 67.71160970025267,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.76814225426479,
			"height": 64.58655417117258,
			"seed": 1594462659,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4438938431009083,
					0.8877876862016857
				],
				[
					0.8877876862017002,
					1.5536284508529463
				],
				[
					1.5536284508530045,
					2.441416137054632
				],
				[
					2.4414161370547047,
					3.5511507448067428
				],
				[
					3.773097666357197,
					5.5486730387605245
				],
				[
					4.438938431008501,
					7.324248411163896
				],
				[
					4.882832274109293,
					7.768142254264746
				],
				[
					5.548673038760597,
					9.543717626668117
				],
				[
					6.214513803411785,
					10.875399155970639
				],
				[
					7.1023014896134855,
					13.98265605767653
				],
				[
					7.3242484111638815,
					15.980178351630327
				],
				[
					7.546195332714394,
					19.08743525333622
				],
				[
					7.76814225426479,
					20.86301062573959
				],
				[
					7.76814225426479,
					23.526373684344648
				],
				[
					7.76814225426479,
					26.855577507600962
				],
				[
					7.76814225426479,
					29.740887487756446
				],
				[
					7.76814225426479,
					31.960356703260654
				],
				[
					7.76814225426479,
					33.95787899721445
				],
				[
					7.76814225426479,
					36.39929513426908
				],
				[
					7.76814225426479,
					37.7309766635716
				],
				[
					7.76814225426479,
					39.50655203597497
				],
				[
					7.76814225426479,
					41.28212740837833
				],
				[
					7.76814225426479,
					42.61380893768088
				],
				[
					7.546195332714394,
					44.38938431008425
				],
				[
					7.3242484111638815,
					46.38690660403802
				],
				[
					7.1023014896134855,
					47.71858813334057
				],
				[
					6.8803545680630895,
					49.05026966264309
				],
				[
					6.658407646512694,
					50.160004270395184
				],
				[
					6.214513803411785,
					51.71363272124813
				],
				[
					5.992566881861389,
					53.26726117210108
				],
				[
					5.770619960310993,
					54.59894270140363
				],
				[
					5.326726117210085,
					55.4867303876053
				],
				[
					4.882832274109293,
					56.81841191690782
				],
				[
					4.660885352558897,
					58.593987289311194
				],
				[
					4.660885352558897,
					59.259828053962465
				],
				[
					4.438938431008501,
					59.925668818613715
				],
				[
					4.216991509458105,
					60.36956266171457
				],
				[
					4.216991509458105,
					60.59150958326499
				],
				[
					3.773097666357197,
					61.479297269466656
				],
				[
					3.551150744806801,
					61.70124419101709
				],
				[
					3.3292038232562886,
					62.36708495566836
				],
				[
					2.8853099801554967,
					63.03292572031964
				],
				[
					2.8853099801554967,
					63.25487264187003
				],
				[
					2.6633630586051007,
					63.476819563420456
				],
				[
					2.6633630586051007,
					63.69876648497088
				],
				[
					2.4414161370547047,
					64.14266032807173
				],
				[
					2.2194692155043088,
					64.36460724962215
				],
				[
					1.9975222939537964,
					64.58655417117258
				],
				[
					1.9975222939537964,
					64.58655417117258
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 289,
			"versionNonce": 829068709,
			"isDeleted": false,
			"id": "qohSgiSB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 464.07563252641705,
			"y": 270.78282102099655,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 279.6651611328125,
			"height": 35,
			"seed": 650398723,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "From Linear Algebra!",
			"rawText": "From Linear Algebra!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "From Linear Algebra!",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 467,
			"versionNonce": 1617871659,
			"isDeleted": false,
			"id": "NpUK2a7g",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 399.1116394224564,
			"y": 546.4603288079838,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 393.8216857910156,
			"height": 175,
			"seed": 614347907,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "dPEQgzYp82NolcKiQ495Q",
					"type": "arrow"
				}
			],
			"updated": 1702760726443,
			"link": "[[Subspaces]]",
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Key notes:\n. Origin is preserved\n. Can be modeled as a 3x3\n  Matrix that describes how\n  each axis is transformed",
			"rawText": "Key notes:\n. Origin is preserved\n. Can be modeled as a 3x3\n  Matrix that describes how\n  each axis is transformed",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Key notes:\n. Origin is preserved\n. Can be modeled as a 3x3\n  Matrix that describes how\n  each axis is transformed",
			"lineHeight": 1.25,
			"baseline": 165
		},
		{
			"type": "arrow",
			"version": 1811,
			"versionNonce": 798292923,
			"isDeleted": false,
			"id": "1qPkV-4anvnRly9SUGNVh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 714.0535553425697,
			"y": 445.9805640390569,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 285.84754944276904,
			"height": 0.313227129749464,
			"seed": 1104915949,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702995800935,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FsIf1pbSBkEiTP0PpjiaC",
				"gap": 1.7972271327679579,
				"focus": 0.1339795291215802
			},
			"endBinding": {
				"elementId": "3eziAxkLea9Nzn_tD8t47",
				"gap": 1,
				"focus": 0.1885916417042957
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
					285.84754944276904,
					-0.313227129749464
				]
			]
		},
		{
			"type": "rectangle",
			"version": 965,
			"versionNonce": 1604527563,
			"isDeleted": false,
			"id": "3eziAxkLea9Nzn_tD8t47",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1000.9011047853386,
			"y": 347.8956090191303,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 404.5647857818254,
			"height": 240.5466400066593,
			"seed": 1313581411,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "1qPkV-4anvnRly9SUGNVh",
					"type": "arrow"
				}
			],
			"updated": 1702760726443,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 504,
			"versionNonce": 1004744805,
			"isDeleted": false,
			"id": "BC8dlz7t",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1167.6718372558573,
			"y": 350.2069169653247,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 82.33869934082031,
			"height": 31.915650483995645,
			"seed": 1853261059,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"fontSize": 25.532520387196517,
			"fontFamily": 1,
			"text": "Scaling",
			"rawText": "Scaling",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Scaling",
			"lineHeight": 1.25,
			"baseline": 22
		},
		{
			"type": "freedraw",
			"version": 397,
			"versionNonce": 1265775723,
			"isDeleted": false,
			"id": "QvV1XfrQvWucumIzcCIWp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1034.6088692061046,
			"y": 416.42996665202315,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffd43b",
			"width": 6.826817354194823,
			"height": 9.216203428162952,
			"seed": 1745153187,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.34134086770973715
				],
				[
					-0.34134086770963634,
					0
				],
				[
					-0.682681735419434,
					0
				],
				[
					-0.682681735419434,
					-0.6826817354194743
				],
				[
					-0.34134086770963634,
					-1.3653634708389586
				],
				[
					0,
					-1.3653634708389586
				],
				[
					0.3413408677097976,
					-1.7067043385486957
				],
				[
					0.6826817354195952,
					-2.0480452062584327
				],
				[
					1.0240226031292317,
					-2.0480452062584327
				],
				[
					2.0480452062584633,
					-2.0480452062584327
				],
				[
					2.730726941677897,
					-1.3653634708389586
				],
				[
					3.4134086770974923,
					-1.0240226031292115
				],
				[
					3.7547495448071286,
					-0.34134086770973715
				],
				[
					4.096090412516927,
					0
				],
				[
					4.096090412516927,
					0.34134086770973715
				],
				[
					4.096090412516927,
					1.0240226031292115
				],
				[
					3.7547495448071286,
					1.7067043385486957
				],
				[
					2.730726941677897,
					1.7067043385486957
				],
				[
					2.0480452062584633,
					1.7067043385486957
				],
				[
					1.3653634708390292,
					2.0480452062584327
				],
				[
					1.0240226031292317,
					2.0480452062584327
				],
				[
					0.3413408677097976,
					2.0480452062584327
				],
				[
					0,
					1.7067043385486957
				],
				[
					-0.682681735419434,
					1.3653634708389586
				],
				[
					-1.0240226031290702,
					0.6826817354194743
				],
				[
					-1.365363470838868,
					0
				],
				[
					-1.365363470838868,
					-1.0240226031292115
				],
				[
					-1.365363470838868,
					-1.7067043385486957
				],
				[
					-1.365363470838868,
					-2.38938607396817
				],
				[
					-1.365363470838868,
					-2.730726941677907
				],
				[
					-0.682681735419434,
					-3.072067809387644
				],
				[
					-0.34134086770963634,
					-3.072067809387644
				],
				[
					0.3413408677097976,
					-3.072067809387644
				],
				[
					1.0240226031292317,
					-3.072067809387644
				],
				[
					2.0480452062584633,
					-3.072067809387644
				],
				[
					2.389386073968261,
					-2.730726941677907
				],
				[
					2.730726941677897,
					-1.7067043385486957
				],
				[
					3.0720678093876947,
					-0.6826817354194743
				],
				[
					3.0720678093876947,
					0.6826817354194743
				],
				[
					2.730726941677897,
					1.7067043385486957
				],
				[
					2.0480452062584633,
					3.4134086770973915
				],
				[
					1.3653634708390292,
					4.437431280226603
				],
				[
					0.3413408677097976,
					5.461453883355825
				],
				[
					-0.34134086770963634,
					5.802794751065561
				],
				[
					-1.0240226031290702,
					5.802794751065561
				],
				[
					-1.365363470838868,
					5.802794751065561
				],
				[
					-1.7067043385486655,
					5.120113015646077
				],
				[
					-2.0480452062583017,
					4.437431280226603
				],
				[
					-2.730726941677897,
					3.072067809387644
				],
				[
					-2.730726941677897,
					2.0480452062584327
				],
				[
					-2.730726941677897,
					1.3653634708389586
				],
				[
					-2.730726941677897,
					0
				],
				[
					-2.3893860739680997,
					-1.3653634708389586
				],
				[
					-2.0480452062583017,
					-2.0480452062584327
				],
				[
					-1.365363470838868,
					-3.072067809387644
				],
				[
					-0.682681735419434,
					-3.4134086770973915
				],
				[
					0,
					-3.4134086770973915
				],
				[
					0.3413408677097976,
					-3.4134086770973915
				],
				[
					1.3653634708390292,
					-3.072067809387644
				],
				[
					2.0480452062584633,
					-2.0480452062584327
				],
				[
					2.0480452062584633,
					-1.3653634708389586
				],
				[
					2.389386073968261,
					-0.34134086770973715
				],
				[
					2.389386073968261,
					0.6826817354194743
				],
				[
					2.389386073968261,
					1.3653634708389586
				],
				[
					2.389386073968261,
					1.7067043385486957
				],
				[
					1.7067043385486655,
					2.0480452062584327
				],
				[
					1.3653634708390292,
					2.0480452062584327
				],
				[
					1.0240226031292317,
					2.0480452062584327
				],
				[
					0.6826817354195952,
					2.0480452062584327
				],
				[
					0.6826817354195952,
					1.7067043385486957
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
			"type": "freedraw",
			"version": 390,
			"versionNonce": 55172037,
			"isDeleted": false,
			"id": "13iBKCBVqE__LI5X_DAZz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1050.9932308561724,
			"y": 415.7472849166037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 60.758674452333494,
			"height": 1.7067043385486957,
			"seed": 1587896387,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.34134086770963634,
					0
				],
				[
					0.682681735419434,
					0
				],
				[
					1.7067043385486655,
					0
				],
				[
					2.730726941677897,
					0
				],
				[
					3.7547495448071286,
					0
				],
				[
					5.461453883355794,
					0
				],
				[
					6.485476486485026,
					0
				],
				[
					8.192180825033692,
					0
				],
				[
					9.55754429587272,
					0
				],
				[
					10.581566899001952,
					0
				],
				[
					11.605589502131021,
					0
				],
				[
					12.970952972970052,
					0
				],
				[
					13.994975576099282,
					0
				],
				[
					15.36033904693815,
					0.34134086770973715
				],
				[
					16.72570251777718,
					0.34134086770973715
				],
				[
					17.74972512090641,
					0.34134086770973715
				],
				[
					19.11508859174528,
					0.34134086770973715
				],
				[
					20.139111194874513,
					0.34134086770973715
				],
				[
					21.16313379800374,
					0.34134086770973715
				],
				[
					22.187156401132974,
					0.34134086770973715
				],
				[
					23.211179004262206,
					0
				],
				[
					24.91788334281087,
					0
				],
				[
					26.2832468136499,
					0
				],
				[
					27.989951152198564,
					-0.6826817354194843
				],
				[
					29.696655490747233,
					-0.6826817354194843
				],
				[
					31.744700697005694,
					-1.0240226031292214
				],
				[
					33.11006416784456,
					-1.0240226031292214
				],
				[
					35.15810937410303,
					-1.3653634708389586
				],
				[
					36.523472844942056,
					-1.3653634708389586
				],
				[
					37.88883631578092,
					-1.3653634708389586
				],
				[
					38.57151805120052,
					-1.3653634708389586
				],
				[
					39.25419978661995,
					-1.3653634708389586
				],
				[
					40.27822238974918,
					-1.3653634708389586
				],
				[
					41.643585860588054,
					-1.3653634708389586
				],
				[
					42.32626759600748,
					-1.3653634708389586
				],
				[
					43.00894933142708,
					-1.3653634708389586
				],
				[
					44.032971934556315,
					-1.3653634708389586
				],
				[
					44.715653669975744,
					-1.3653634708389586
				],
				[
					46.08101714081477,
					-1.3653634708389586
				],
				[
					46.76369887623421,
					-1.3653634708389586
				],
				[
					47.78772147936344,
					-1.3653634708389586
				],
				[
					48.47040321478288,
					-1.3653634708389586
				],
				[
					49.153084950202306,
					-1.3653634708389586
				],
				[
					49.83576668562174,
					-1.3653634708389586
				],
				[
					50.17710755333154,
					-1.3653634708389586
				],
				[
					50.518448421041334,
					-1.0240226031292214
				],
				[
					51.20113015646077,
					-1.0240226031292214
				],
				[
					51.88381189188021,
					-1.0240226031292214
				],
				[
					52.22515275959,
					-1.0240226031292214
				],
				[
					52.5664936272998,
					-0.6826817354194843
				],
				[
					53.249175362719235,
					-0.6826817354194843
				],
				[
					53.93185709813867,
					-0.34134086770973715
				],
				[
					54.27319796584847,
					-0.34134086770973715
				],
				[
					55.2972205689777,
					-0.34134086770973715
				],
				[
					55.97990230439713,
					-0.34134086770973715
				],
				[
					56.662584039816565,
					-0.34134086770973715
				],
				[
					57.00392490752636,
					-0.34134086770973715
				],
				[
					58.02794751065559,
					-0.34134086770973715
				],
				[
					58.36928837836523,
					-0.34134086770973715
				],
				[
					59.051970113784826,
					-0.34134086770973715
				],
				[
					59.393310981494466,
					-0.34134086770973715
				],
				[
					60.07599271691406,
					-0.34134086770973715
				],
				[
					60.41733358462369,
					-0.34134086770973715
				],
				[
					60.758674452333494,
					-0.34134086770973715
				],
				[
					60.758674452333494,
					-0.34134086770973715
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 365,
			"versionNonce": 329674507,
			"isDeleted": false,
			"id": "U41q1IxXiZhAJm_f5lH0L",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1112.0932461762154,
			"y": 404.14169541447257,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 14.677657311518878,
			"height": 19.797770327164844,
			"seed": 2083938275,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.3413408677097472
				],
				[
					0,
					0.6826817354194843
				],
				[
					0,
					1.3653634708389586
				],
				[
					0,
					2.0480452062584327
				],
				[
					0.3413408677097976,
					2.38938607396818
				],
				[
					1.0240226031292317,
					3.4134086770973915
				],
				[
					1.7067043385488267,
					4.437431280226603
				],
				[
					2.730726941677897,
					5.461453883355825
				],
				[
					3.4134086770974923,
					6.485476486485036
				],
				[
					3.7547495448071286,
					6.826817354194783
				],
				[
					4.437431280226724,
					7.850839957323994
				],
				[
					5.461453883355955,
					8.533521692743468
				],
				[
					6.826817354194823,
					9.55754429587269
				],
				[
					7.509499089614419,
					9.898885163582428
				],
				[
					8.192180825033853,
					10.581566899001901
				],
				[
					9.216203428162922,
					11.264248634421385
				],
				[
					9.898885163582518,
					11.94693036984086
				],
				[
					10.922907766711749,
					12.970952972970071
				],
				[
					11.605589502131183,
					13.653634708389555
				],
				[
					11.605589502131183,
					14.33631644380903
				],
				[
					11.946930369840981,
					14.677657311518768
				],
				[
					11.946930369840981,
					15.018998179228504
				],
				[
					11.264248634421385,
					15.360339046938241
				],
				[
					9.898885163582518,
					16.043020782357726
				],
				[
					7.850839957324055,
					16.38436165006746
				],
				[
					5.8027947510655915,
					16.7257025177772
				],
				[
					3.4134086770974923,
					17.408384253196676
				],
				[
					2.0480452062584633,
					17.749725120906422
				],
				[
					0.3413408677097976,
					18.091065988616158
				],
				[
					-0.34134086770963634,
					18.091065988616158
				],
				[
					-1.365363470838868,
					18.432406856325898
				],
				[
					-1.7067043385486655,
					18.432406856325898
				],
				[
					-2.0480452062583017,
					18.773747724035633
				],
				[
					-2.3893860739680997,
					18.773747724035633
				],
				[
					-2.3893860739680997,
					19.11508859174537
				],
				[
					-2.730726941677897,
					19.11508859174537
				],
				[
					-2.730726941677897,
					19.45642945945511
				],
				[
					-2.730726941677897,
					19.797770327164844
				],
				[
					-2.3893860739680997,
					19.797770327164844
				],
				[
					-2.3893860739680997,
					19.797770327164844
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 358,
			"versionNonce": 864295717,
			"isDeleted": false,
			"id": "YfGoANZ63aQ0U33LwDOGP",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1009.0269153806464,
			"y": 434.7214298849673,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.221258438766108,
			"height": 16.41307871180812,
			"seed": 244581155,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.15339325898886252
				],
				[
					-0.15339325898887765,
					0.4601797769665825
				],
				[
					-0.46017977696655227,
					0.7669662949443076
				],
				[
					-0.6135730359554299,
					1.22714607191089
				],
				[
					-0.9203595539331852,
					1.84071910786633
				],
				[
					-1.2271460719108598,
					2.7610786617995
				],
				[
					-1.5339325898886151,
					3.681438215732665
				],
				[
					-1.6873258488774927,
					4.141617992699247
				],
				[
					-1.8407191078663705,
					4.90858428764355
				],
				[
					-2.1475056258440453,
					5.828943841576716
				],
				[
					-2.1475056258440453,
					6.595910136521023
				],
				[
					-2.3008988848329226,
					7.516269690454188
				],
				[
					-2.3008988848329226,
					8.129842726409633
				],
				[
					-2.3008988848329226,
					8.896809021353935
				],
				[
					-2.4542921438218004,
					9.8171685752871
				],
				[
					-2.4542921438218004,
					10.737528129220266
				],
				[
					-2.4542921438218004,
					11.351101165175711
				],
				[
					-2.4542921438218004,
					11.964674201131155
				],
				[
					-2.3008988848329226,
					12.5782472370866
				],
				[
					-2.1475056258440453,
					13.19182027304204
				],
				[
					-1.9941123668551675,
					13.652000050008624
				],
				[
					-1.6873258488774927,
					14.112179826975206
				],
				[
					-1.5339325898886151,
					14.418966344952931
				],
				[
					-1.2271460719108598,
					14.725752862930657
				],
				[
					-0.9203595539331852,
					15.185932639897239
				],
				[
					-0.7669662949443076,
					15.492719157874953
				],
				[
					-0.46017977696655227,
					15.952898934841535
				],
				[
					0,
					16.259685452819262
				],
				[
					0.15339325898887765,
					16.259685452819262
				],
				[
					0.3067865179777553,
					16.41307871180812
				],
				[
					0.46017977696655227,
					16.41307871180812
				],
				[
					0.6135730359554299,
					16.41307871180812
				],
				[
					0.7669662949443076,
					16.41307871180812
				],
				[
					0.7669662949443076,
					16.259685452819262
				],
				[
					0.7669662949443076,
					16.106292193830402
				],
				[
					0.7669662949443076,
					16.106292193830402
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 337,
			"versionNonce": 1253725611,
			"isDeleted": false,
			"id": "Y6UPPaEay2mGGTXTwq_Io",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1015.4694322581787,
			"y": 438.40286810069995,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.8348314747216183,
			"height": 8.743415762365073,
			"seed": 1074636483,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.15339325898886252
				],
				[
					-0.3067865179777553,
					0.30678651797772
				],
				[
					-0.7669662949443882,
					0.920359553933165
				],
				[
					-1.5339325898886151,
					1.53393258988861
				],
				[
					-2.1475056258441256,
					2.454292143821775
				],
				[
					-3.0678651797772303,
					4.601797769665826
				],
				[
					-3.528044956743863,
					5.828943841576716
				],
				[
					-3.681438215732741,
					6.5959101365210175
				],
				[
					-3.8348314747216183,
					7.362876431465326
				],
				[
					-3.8348314747216183,
					7.8230562084319075
				],
				[
					-3.8348314747216183,
					8.436629244387353
				],
				[
					-3.8348314747216183,
					8.590022503376211
				],
				[
					-3.8348314747216183,
					8.283235985398491
				],
				[
					-3.8348314747216183,
					8.129842726409628
				],
				[
					-3.8348314747216183,
					8.129842726409628
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 345,
			"versionNonce": 352284293,
			"isDeleted": false,
			"id": "9GyLYgMyeOQvLxJQeqiZ5",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1012.0947805604237,
			"y": 438.09608158272226,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.994112366855248,
			"height": 8.896809021353935,
			"seed": 1171379811,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.15339325898886252
				],
				[
					0,
					0.30678651797772505
				],
				[
					0,
					0.7669662949443076
				],
				[
					0,
					1.0737528129220275
				],
				[
					0.15339325898887765,
					1.6873258488774725
				],
				[
					0.3067865179777553,
					2.7610786617995
				],
				[
					0.766966294944227,
					3.681438215732665
				],
				[
					0.766966294944227,
					4.755191028654693
				],
				[
					1.0737528129219822,
					5.522157323598996
				],
				[
					1.0737528129219822,
					6.13573035955444
				],
				[
					1.0737528129219822,
					6.44251687753216
				],
				[
					1.2271460719108598,
					6.749303395509886
				],
				[
					1.3805393308997376,
					7.056089913487606
				],
				[
					1.3805393308997376,
					7.209483172476468
				],
				[
					1.5339325898886151,
					7.516269690454188
				],
				[
					1.5339325898886151,
					7.823056208431913
				],
				[
					1.5339325898886151,
					8.129842726409633
				],
				[
					1.6873258488774927,
					8.436629244387353
				],
				[
					1.6873258488774927,
					8.743415762365078
				],
				[
					1.6873258488774927,
					8.896809021353935
				],
				[
					1.8407191078663705,
					8.743415762365078
				],
				[
					1.994112366855248,
					8.590022503376215
				],
				[
					1.994112366855248,
					8.590022503376215
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 331,
			"versionNonce": 1339582539,
			"isDeleted": false,
			"id": "gmw2VHOHLCpdnZwLgKf6t",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1018.0771176609891,
			"y": 444.99877823722096,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.3805393308997376,
			"height": 3.0678651797772254,
			"seed": 1320096259,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.30678651797772505
				],
				[
					-0.3067865179777553,
					1.0737528129220275
				],
				[
					-0.6135730359555106,
					1.53393258988861
				],
				[
					-0.9203595539331045,
					2.147505625844055
				],
				[
					-1.2271460719108598,
					2.7610786617995
				],
				[
					-1.3805393308997376,
					2.914471920788358
				],
				[
					-1.3805393308997376,
					3.0678651797772254
				],
				[
					-1.0737528129219822,
					2.914471920788358
				],
				[
					-1.0737528129219822,
					2.914471920788358
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 404,
			"versionNonce": 108615141,
			"isDeleted": false,
			"id": "f8juO-cKamRJDfI6YYNG9",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1022.6789154306548,
			"y": 436.5621489928336,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.595910136521093,
			"height": 17.333438265741282,
			"seed": 732158371,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.30678651797772505
				],
				[
					0,
					0.7669662949443076
				],
				[
					0,
					1.22714607191089
				],
				[
					0,
					2.7610786617995
				],
				[
					0,
					3.2212584387660828
				],
				[
					0.3067865179777553,
					4.29501125168811
				],
				[
					0.6135730359553493,
					5.061977546632413
				],
				[
					1.2271460719108598,
					5.982337100565577
				],
				[
					1.6873258488774927,
					6.13573035955444
				],
				[
					1.9941123668550869,
					6.13573035955444
				],
				[
					2.4542921438217196,
					5.675550582587858
				],
				[
					2.761078661799475,
					5.061977546632413
				],
				[
					3.0678651797772303,
					4.29501125168811
				],
				[
					3.221258438766108,
					3.374651697754945
				],
				[
					3.3746516977549854,
					2.7610786617995
				],
				[
					3.528044956743702,
					2.147505625844055
				],
				[
					3.6814382157325793,
					1.8407191078663352
				],
				[
					3.988224733710335,
					1.3805393308997527
				],
				[
					4.141617992699213,
					0.92035955393317
				],
				[
					4.448404510676967,
					0.613573035955445
				],
				[
					4.601797769665845,
					0.30678651797772505
				],
				[
					4.755191028654723,
					0.15339325898886252
				],
				[
					4.755191028654723,
					0
				],
				[
					4.755191028654723,
					-0.15339325898885747
				],
				[
					4.755191028654723,
					0
				],
				[
					4.448404510676967,
					0.30678651797772505
				],
				[
					4.2950112516880905,
					1.0737528129220275
				],
				[
					4.141617992699213,
					1.8407191078663352
				],
				[
					3.988224733710335,
					2.7610786617995
				],
				[
					3.988224733710335,
					3.528044956743803
				],
				[
					3.988224733710335,
					4.448404510676967
				],
				[
					3.834831474721457,
					5.368764064610138
				],
				[
					3.6814382157325793,
					6.749303395509886
				],
				[
					3.528044956743702,
					7.66966294944305
				],
				[
					3.3746516977549854,
					9.050202280342798
				],
				[
					3.221258438766108,
					10.277348352253687
				],
				[
					3.0678651797772303,
					11.504494424164578
				],
				[
					2.761078661799475,
					12.5782472370866
				],
				[
					2.4542921438217196,
					13.805393308997491
				],
				[
					2.300898884832842,
					14.418966344952931
				],
				[
					1.9941123668550869,
					15.185932639897239
				],
				[
					1.6873258488774927,
					15.799505675852679
				],
				[
					1.3805393308997376,
					16.259685452819262
				],
				[
					0.766966294944227,
					16.719865229785842
				],
				[
					0.4601797769666329,
					16.87325848877471
				],
				[
					0,
					17.02665174776357
				],
				[
					-0.3067865179777553,
					17.180045006752426
				],
				[
					-1.0737528129219822,
					17.180045006752426
				],
				[
					-1.3805393308997376,
					17.180045006752426
				],
				[
					-1.5339325898886151,
					17.180045006752426
				],
				[
					-1.6873258488774927,
					16.87325848877471
				],
				[
					-1.8407191078663705,
					16.259685452819262
				],
				[
					-1.8407191078663705,
					15.799505675852679
				],
				[
					-1.8407191078663705,
					15.185932639897239
				],
				[
					-1.8407191078663705,
					14.725752862930657
				],
				[
					-1.6873258488774927,
					14.265573085964073
				],
				[
					-1.3805393308997376,
					13.805393308997491
				],
				[
					-1.0737528129219822,
					13.652000050008624
				],
				[
					-0.7669662949443882,
					13.345213532030908
				],
				[
					-0.4601797769666329,
					12.885033755064326
				],
				[
					0,
					12.731640496075459
				],
				[
					0.15339325898887765,
					12.731640496075459
				],
				[
					0.6135730359553493,
					12.731640496075459
				],
				[
					0.9203595539331045,
					13.038427014053184
				],
				[
					1.2271460719108598,
					13.19182027304204
				],
				[
					1.3805393308997376,
					13.498606791019766
				],
				[
					1.8407191078663705,
					13.958786567986348
				],
				[
					1.9941123668550869,
					14.265573085964073
				],
				[
					2.300898884832842,
					14.572359603941788
				],
				[
					2.6076854028105974,
					15.03253938090838
				],
				[
					2.9144719207883525,
					15.185932639897239
				],
				[
					3.221258438766108,
					15.492719157874964
				],
				[
					3.3746516977549854,
					15.952898934841546
				],
				[
					3.6814382157325793,
					16.106292193830402
				],
				[
					3.834831474721457,
					16.106292193830402
				],
				[
					3.988224733710335,
					16.106292193830402
				],
				[
					4.141617992699213,
					16.106292193830402
				],
				[
					4.2950112516880905,
					16.106292193830402
				],
				[
					4.2950112516880905,
					15.952898934841546
				],
				[
					4.448404510676967,
					15.799505675852679
				],
				[
					4.601797769665845,
					15.492719157874964
				],
				[
					4.601797769665845,
					15.185932639897239
				],
				[
					4.601797769665845,
					15.185932639897239
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 329,
			"versionNonce": 953886443,
			"isDeleted": false,
			"id": "hLTrb5LbKl11I45KRxFkM",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1032.1892974879643,
			"y": 445.1521714962098,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.300898884832842,
			"height": 3.37465169775494,
			"seed": 165588291,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.15339325898886252
				],
				[
					0,
					0
				],
				[
					-0.46017977696647167,
					0.7669662949443076
				],
				[
					-1.0737528129219822,
					1.3805393308997476
				],
				[
					-1.6873258488773315,
					1.9941123668551926
				],
				[
					-1.9941123668550869,
					2.6076854028106378
				],
				[
					-2.300898884832842,
					3.221258438766078
				],
				[
					-2.300898884832842,
					3.221258438766078
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 365,
			"versionNonce": 855593285,
			"isDeleted": false,
			"id": "yKPfjsl4AHckm4vOG_Wme",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1035.4105559267302,
			"y": 437.3291152877779,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.056089913487726,
			"height": 11.811280942142293,
			"seed": 1824394467,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.15339325898887765,
					0
				],
				[
					0,
					0
				],
				[
					0.7669662949443882,
					0.15339325898886252
				],
				[
					1.6873258488774927,
					0.30678651797772
				],
				[
					3.0678651797772303,
					0.4601797769665825
				],
				[
					3.681438215732741,
					0.4601797769665825
				],
				[
					4.2950112516880905,
					0.7669662949443026
				],
				[
					4.448404510676967,
					0.7669662949443026
				],
				[
					4.755191028654723,
					0.920359553933165
				],
				[
					4.908584287643601,
					1.0737528129220275
				],
				[
					5.215370805621356,
					1.227146071910885
				],
				[
					5.368764064610233,
					1.3805393308997476
				],
				[
					5.522157323599111,
					1.53393258988861
				],
				[
					5.522157323599111,
					1.6873258488774676
				],
				[
					5.215370805621356,
					1.9941123668551926
				],
				[
					4.908584287643601,
					2.300898884832913
				],
				[
					4.141617992699213,
					2.914471920788358
				],
				[
					3.0678651797772303,
					3.834831474721523
				],
				[
					2.3008988848330034,
					4.90858428764355
				],
				[
					1.2271460719108598,
					6.2891236185432975
				],
				[
					0.6135730359555106,
					7.056089913487606
				],
				[
					0,
					7.97644946742077
				],
				[
					-0.3067865179777553,
					8.743415762365073
				],
				[
					-0.9203595539331045,
					9.51038205730938
				],
				[
					-1.2271460719108598,
					10.277348352253687
				],
				[
					-1.5339325898886151,
					10.584134870231402
				],
				[
					-1.5339325898886151,
					11.197707906186853
				],
				[
					-1.5339325898886151,
					11.504494424164568
				],
				[
					-1.3805393308997376,
					11.811280942142293
				],
				[
					-1.2271460719108598,
					11.811280942142293
				],
				[
					-0.9203595539331045,
					11.811280942142293
				],
				[
					-0.6135730359553493,
					11.811280942142293
				],
				[
					0,
					11.811280942142293
				],
				[
					0.3067865179777553,
					11.657887683153435
				],
				[
					0.9203595539332659,
					11.351101165175711
				],
				[
					1.0737528129221434,
					11.197707906186853
				],
				[
					1.5339325898886151,
					10.890921388209128
				],
				[
					1.8407191078663705,
					10.737528129220271
				],
				[
					2.1475056258441256,
					10.737528129220271
				],
				[
					2.3008988848330034,
					10.584134870231402
				],
				[
					2.4542921438218808,
					10.430741611242546
				],
				[
					2.761078661799475,
					10.430741611242546
				],
				[
					2.761078661799475,
					10.277348352253687
				],
				[
					2.9144719207883525,
					10.277348352253687
				],
				[
					2.9144719207883525,
					10.277348352253687
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 330,
			"versionNonce": 2085425547,
			"isDeleted": false,
			"id": "dUT8QZCf_MPrhkknvGPLd",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1035.7173424447083,
			"y": 442.3910928344103,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.3746516977549854,
			"height": 0,
			"seed": 1741715587,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.15339325898887765,
					0
				],
				[
					0.3067865179777553,
					0
				],
				[
					0.7669662949443882,
					0
				],
				[
					1.3805393308997376,
					0
				],
				[
					1.8407191078663705,
					0
				],
				[
					2.6076854028105974,
					0
				],
				[
					2.9144719207883525,
					0
				],
				[
					3.0678651797772303,
					0
				],
				[
					3.221258438766108,
					0
				],
				[
					3.221258438766108,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 349,
			"versionNonce": 133095589,
			"isDeleted": false,
			"id": "eKRTCzglWP7mh1rdEm2hN",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1043.0802188761734,
			"y": 436.10196921586703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.834831474721457,
			"height": 13.805393308997491,
			"seed": 416575523,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.15339325898887765,
					0
				],
				[
					0.4601797769666329,
					0.30678651797772505
				],
				[
					0.6135730359555106,
					0.4601797769665825
				],
				[
					1.2271460719108598,
					0.920359553933165
				],
				[
					1.6873258488774927,
					1.3805393308997527
				],
				[
					2.1475056258441256,
					1.9941123668551926
				],
				[
					2.4542921438217196,
					2.6076854028106378
				],
				[
					3.0678651797772303,
					4.141617992699247
				],
				[
					3.0678651797772303,
					4.90858428764355
				],
				[
					3.0678651797772303,
					6.13573035955444
				],
				[
					3.0678651797772303,
					6.749303395509886
				],
				[
					2.9144719207883525,
					7.516269690454188
				],
				[
					2.761078661799475,
					8.283235985398495
				],
				[
					2.4542921438217196,
					9.050202280342798
				],
				[
					2.1475056258441256,
					9.663775316298244
				],
				[
					1.994112366855248,
					10.277348352253687
				],
				[
					1.8407191078663705,
					11.044314647197991
				],
				[
					1.6873258488774927,
					11.811280942142293
				],
				[
					1.3805393308997376,
					12.5782472370866
				],
				[
					1.0737528129219822,
					13.038427014053184
				],
				[
					0.7669662949443882,
					13.498606791019766
				],
				[
					0.6135730359555106,
					13.652000050008624
				],
				[
					0.4601797769666329,
					13.805393308997491
				],
				[
					0.3067865179777553,
					13.805393308997491
				],
				[
					0,
					13.805393308997491
				],
				[
					-0.3067865179777553,
					13.805393308997491
				],
				[
					-0.6135730359555106,
					13.805393308997491
				],
				[
					-0.766966294944227,
					13.805393308997491
				],
				[
					-0.766966294944227,
					13.805393308997491
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 355,
			"versionNonce": 1533585451,
			"isDeleted": false,
			"id": "ZgmOjBZtUOvxPGGEyvCvM",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1118.0895225217264,
			"y": 431.19338492822345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.061977546632317,
			"height": 20.247910186529648,
			"seed": 1639478211,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.1533932589887164,
					0
				],
				[
					-0.30678651797759404,
					0.15339325898886255
				],
				[
					-0.766966294944227,
					0.4601797769665826
				],
				[
					-1.2271460719108598,
					1.2271460719108902
				],
				[
					-1.9941123668550869,
					1.8407191078663354
				],
				[
					-2.4542921438217196,
					2.607685402810638
				],
				[
					-3.0678651797772303,
					3.5280449567438033
				],
				[
					-3.374651697754824,
					4.295011251688111
				],
				[
					-4.141617992699213,
					5.061977546632414
				],
				[
					-4.601797769665684,
					6.289123618543304
				],
				[
					-4.755191028654561,
					7.209483172476469
				],
				[
					-4.755191028654561,
					8.283235985398496
				],
				[
					-4.755191028654561,
					9.35698879832052
				],
				[
					-4.755191028654561,
					10.430741611242548
				],
				[
					-4.601797769665684,
					11.504494424164575
				],
				[
					-4.448404510676967,
					12.578247237086602
				],
				[
					-4.2950112516880905,
					13.805393308997488
				],
				[
					-3.834831474721457,
					15.032539380908378
				],
				[
					-3.528044956743702,
					16.259685452819262
				],
				[
					-3.2212584387659464,
					17.02665174776357
				],
				[
					-2.761078661799475,
					18.100404560685593
				],
				[
					-2.6076854028105974,
					18.560584337652177
				],
				[
					-2.300898884832842,
					18.8673708556299
				],
				[
					-2.1475056258439644,
					19.174157373607628
				],
				[
					-1.9941123668550869,
					19.48094389158534
				],
				[
					-1.840719107866209,
					19.634337150574208
				],
				[
					-1.6873258488773315,
					19.787730409563068
				],
				[
					-1.3805393308997376,
					20.09451692754079
				],
				[
					-1.0737528129219822,
					20.09451692754079
				],
				[
					-0.766966294944227,
					20.247910186529648
				],
				[
					-0.46017977696647167,
					20.247910186529648
				],
				[
					0,
					20.247910186529648
				],
				[
					0.15339325898887765,
					20.247910186529648
				],
				[
					0.3067865179777553,
					20.09451692754079
				],
				[
					0.3067865179777553,
					20.09451692754079
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 331,
			"versionNonce": 1794475013,
			"isDeleted": false,
			"id": "XmpSDSjNcDPyWRS37J1AL",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1122.691320291392,
			"y": 438.5562613596888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.988224733710335,
			"height": 9.050202280342804,
			"seed": 1654326115,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726443,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.46017977696647167,
					0.4601797769665825
				],
				[
					-1.0737528129219822,
					1.6873258488774725
				],
				[
					-1.6873258488773315,
					2.7610786617995
				],
				[
					-2.4542921438217196,
					3.8348314747215277
				],
				[
					-3.374651697754824,
					5.82894384157672
				],
				[
					-3.834831474721457,
					7.66966294944305
				],
				[
					-3.834831474721457,
					8.436629244387353
				],
				[
					-3.988224733710335,
					8.896809021353935
				],
				[
					-3.988224733710335,
					9.050202280342804
				],
				[
					-3.988224733710335,
					8.896809021353935
				],
				[
					-3.988224733710335,
					8.896809021353935
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 337,
			"versionNonce": 202926795,
			"isDeleted": false,
			"id": "krthg0m3WnasFfLiWSgRr",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1119.0098820756596,
			"y": 439.47662091362196,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.4542921438217196,
			"height": 6.135730359554436,
			"seed": 868916995,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.30678651797772
				],
				[
					0,
					0.61357303595544
				],
				[
					0.3067865179777553,
					1.3805393308997476
				],
				[
					0.6135730359553493,
					1.84071910786633
				],
				[
					0.9203595539331045,
					2.914471920788358
				],
				[
					1.2271460719108598,
					4.141617992699243
				],
				[
					1.5339325898886151,
					4.90858428764355
				],
				[
					1.5339325898886151,
					5.21537080562127
				],
				[
					1.6873258488774927,
					5.675550582587853
				],
				[
					1.8407191078663705,
					5.982337100565573
				],
				[
					1.8407191078663705,
					6.135730359554436
				],
				[
					1.994112366855248,
					6.135730359554436
				],
				[
					2.1475056258439644,
					6.135730359554436
				],
				[
					2.300898884832842,
					6.135730359554436
				],
				[
					2.300898884832842,
					5.982337100565573
				],
				[
					2.4542921438217196,
					5.675550582587853
				],
				[
					2.4542921438217196,
					5.675550582587853
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 330,
			"versionNonce": 806402917,
			"isDeleted": false,
			"id": "Dfor1pnMTTRpLg1u-qUXP",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1123.4582865863365,
			"y": 434.8748231439561,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.5339325898886151,
			"height": 4.295011251688106,
			"seed": 1606796963,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.15339325898886255
				],
				[
					0.15339325898887765,
					0.7669662949443027
				],
				[
					0.46017977696647167,
					1.2271460719108853
				],
				[
					0.9203595539331045,
					2.1475056258440506
				],
				[
					1.2271460719108598,
					3.0678651797772205
				],
				[
					1.3805393308997376,
					3.5280449567438033
				],
				[
					1.5339325898886151,
					3.988224733710386
				],
				[
					1.5339325898886151,
					4.141617992699243
				],
				[
					1.5339325898886151,
					4.295011251688106
				],
				[
					1.5339325898886151,
					4.295011251688106
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 331,
			"versionNonce": 586602859,
			"isDeleted": false,
			"id": "s53nYPyYTCn3Htov_WA8I",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1128.8270506509466,
			"y": 445.3055647551987,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.9144719207883525,
			"height": 4.60179776966583,
			"seed": 490404419,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.4601797769666329,
					0.30678651797772
				],
				[
					-0.9203595539331045,
					0.920359553933165
				],
				[
					-1.3805393308997376,
					1.53393258988861
				],
				[
					-1.9941123668550869,
					2.454292143821775
				],
				[
					-2.1475056258439644,
					2.7610786617995
				],
				[
					-2.300898884832842,
					3.37465169775494
				],
				[
					-2.6076854028105974,
					3.98822473371038
				],
				[
					-2.761078661799475,
					4.448404510676963
				],
				[
					-2.9144719207883525,
					4.448404510676963
				],
				[
					-2.9144719207883525,
					4.60179776966583
				],
				[
					-2.9144719207883525,
					4.60179776966583
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 404,
			"versionNonce": 1334707909,
			"isDeleted": false,
			"id": "aZL9KDbxJZcS3zogFXLVf",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1131.5881293127459,
			"y": 436.5621489928336,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 9.20359553933169,
			"height": 18.253797819674457,
			"seed": 1225308643,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.46017977696658247
				],
				[
					0,
					1.22714607191089
				],
				[
					0,
					1.6873258488774723
				],
				[
					0,
					2.4542921438217746
				],
				[
					0,
					3.2212584387660823
				],
				[
					0,
					4.141617992699247
				],
				[
					0.3067865179777553,
					4.755191028654692
				],
				[
					0.6135730359555106,
					5.061977546632412
				],
				[
					0.9203595539332659,
					5.061977546632412
				],
				[
					1.5339325898886151,
					4.908584287643555
				],
				[
					1.8407191078663705,
					4.295011251688109
				],
				[
					2.1475056258441256,
					3.6814382157326646
				],
				[
					2.4542921438218808,
					2.6076854028106373
				],
				[
					2.6076854028107586,
					2.1475056258440546
				],
				[
					2.6076854028107586,
					1.5339325898886098
				],
				[
					2.6076854028107586,
					1.22714607191089
				],
				[
					2.6076854028107586,
					1.0737528129220273
				],
				[
					2.6076854028107586,
					1.5339325898886098
				],
				[
					2.6076854028107586,
					2.1475056258440546
				],
				[
					2.6076854028107586,
					2.9144719207883623
				],
				[
					2.6076854028107586,
					3.6814382157326646
				],
				[
					2.6076854028107586,
					4.448404510676967
				],
				[
					2.6076854028107586,
					5.368764064610137
				],
				[
					2.6076854028107586,
					6.135730359554439
				],
				[
					2.6076854028107586,
					6.595910136521022
				],
				[
					2.4542921438218808,
					7.362876431465329
				],
				[
					2.3008988848330034,
					8.283235985398495
				],
				[
					2.1475056258441256,
					9.203595539331658
				],
				[
					1.994112366855248,
					9.817168575287104
				],
				[
					1.8407191078663705,
					10.890921388209126
				],
				[
					1.6873258488774927,
					11.964674201131158
				],
				[
					1.3805393308998988,
					13.191820273042039
				],
				[
					1.3805393308998988,
					13.498606791019764
				],
				[
					1.2271460719108598,
					14.265573085964071
				],
				[
					1.0737528129221434,
					15.032539380908378
				],
				[
					0.9203595539332659,
					15.646112416863819
				],
				[
					0.7669662949443882,
					16.25968545281926
				],
				[
					0.6135730359555106,
					16.87325848877471
				],
				[
					0.15339325898887765,
					17.33343826574129
				],
				[
					-0.15339325898887765,
					17.793618042707873
				],
				[
					-0.6135730359553493,
					18.10040456068559
				],
				[
					-0.9203595539331045,
					18.253797819674457
				],
				[
					-1.2271460719108598,
					18.253797819674457
				],
				[
					-1.6873258488773315,
					18.253797819674457
				],
				[
					-1.9941123668550869,
					18.253797819674457
				],
				[
					-2.300898884832842,
					17.94701130169673
				],
				[
					-2.6076854028105974,
					17.640224783719006
				],
				[
					-2.6076854028105974,
					17.33343826574129
				],
				[
					-2.761078661799475,
					17.026651747763566
				],
				[
					-2.761078661799475,
					16.566471970796982
				],
				[
					-2.761078661799475,
					16.413078711808126
				],
				[
					-2.6076854028105974,
					16.106292193830402
				],
				[
					-2.1475056258439644,
					15.646112416863819
				],
				[
					-1.5339325898886151,
					15.032539380908378
				],
				[
					-1.2271460719108598,
					14.725752862930653
				],
				[
					-0.766966294944227,
					14.418966344952928
				],
				[
					-0.46017977696647167,
					14.265573085964071
				],
				[
					-0.30678651797759404,
					14.112179826975204
				],
				[
					-0.15339325898887765,
					14.112179826975204
				],
				[
					0,
					14.112179826975204
				],
				[
					0.4601797769666329,
					14.112179826975204
				],
				[
					0.6135730359555106,
					14.265573085964071
				],
				[
					0.7669662949443882,
					14.418966344952928
				],
				[
					1.0737528129221434,
					14.572359603941786
				],
				[
					1.6873258488774927,
					14.879146121919511
				],
				[
					2.1475056258441256,
					15.032539380908378
				],
				[
					2.4542921438218808,
					15.339325898886093
				],
				[
					2.9144719207883525,
					15.49271915787496
				],
				[
					3.681438215732741,
					15.799505675852675
				],
				[
					3.988224733710496,
					15.799505675852675
				],
				[
					4.1416179926993735,
					15.952898934841544
				],
				[
					4.601797769665845,
					16.106292193830402
				],
				[
					5.061977546632479,
					16.106292193830402
				],
				[
					5.215370805621356,
					16.106292193830402
				],
				[
					5.522157323599111,
					16.106292193830402
				],
				[
					5.675550582587827,
					16.106292193830402
				],
				[
					5.982337100565583,
					16.106292193830402
				],
				[
					6.1357303595544606,
					16.106292193830402
				],
				[
					6.289123618543338,
					16.106292193830402
				],
				[
					6.289123618543338,
					15.952898934841544
				],
				[
					6.442516877532216,
					15.799505675852675
				],
				[
					6.442516877532216,
					15.49271915787496
				],
				[
					6.442516877532216,
					15.339325898886093
				],
				[
					6.442516877532216,
					15.339325898886093
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 330,
			"versionNonce": 1028551691,
			"isDeleted": false,
			"id": "iFVv-0_b9JmF-0l_qX4TJ",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1138.0306461902785,
			"y": 435.48839617991155,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.6873258488774927,
			"height": 5.52215732359899,
			"seed": 540902787,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.15339325898887765,
					0
				],
				[
					0.3067865179777553,
					0.30678651797772
				],
				[
					0.4601797769666329,
					0.7669662949443026
				],
				[
					0.7669662949443882,
					1.3805393308997476
				],
				[
					1.0737528129219822,
					2.14750562584405
				],
				[
					1.3805393308997376,
					3.37465169775494
				],
				[
					1.3805393308997376,
					4.141617992699243
				],
				[
					1.5339325898886151,
					5.0619775466324075
				],
				[
					1.6873258488774927,
					5.52215732359899
				],
				[
					1.6873258488774927,
					5.52215732359899
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 340,
			"versionNonce": 1544218149,
			"isDeleted": false,
			"id": "Cy_CQn5uxOhRtC1vnjuR6",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1146.313882175677,
			"y": 444.5385984602543,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.528044956743863,
			"height": 5.21537080562127,
			"seed": 974642467,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.1533932589890389,
					0
				],
				[
					-0.3067865179777553,
					0
				],
				[
					-0.4601797769666329,
					0.30678651797772505
				],
				[
					-0.6135730359555106,
					0.613573035955445
				],
				[
					-0.9203595539332659,
					1.3805393308997527
				],
				[
					-1.2271460719110212,
					2.454292143821775
				],
				[
					-1.3805393308998988,
					3.0678651797772254
				],
				[
					-1.5339325898887763,
					3.37465169775494
				],
				[
					-1.6873258488774927,
					3.834831474721523
				],
				[
					-1.8407191078663705,
					3.9882247337103904
				],
				[
					-1.994112366855248,
					4.141617992699247
				],
				[
					-2.3008988848330034,
					4.295011251688106
				],
				[
					-2.6076854028107586,
					4.448404510676973
				],
				[
					-2.9144719207885137,
					4.60179776966583
				],
				[
					-3.0678651797772303,
					4.9085842876435555
				],
				[
					-3.221258438766108,
					5.061977546632413
				],
				[
					-3.3746516977549854,
					5.21537080562127
				],
				[
					-3.528044956743863,
					5.21537080562127
				],
				[
					-3.528044956743863,
					5.061977546632413
				],
				[
					-3.528044956743863,
					5.061977546632413
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 384,
			"versionNonce": 1796848299,
			"isDeleted": false,
			"id": "MiQw3iEex5U0sFf6XRvk_",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1149.6885338734319,
			"y": 437.0223287698002,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.669662949443076,
			"height": 13.498606791019766,
			"seed": 1107706051,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3067865179777553,
					0
				],
				[
					0.4601797769666329,
					0
				],
				[
					0.6135730359555106,
					0
				],
				[
					0.9203595539331045,
					0
				],
				[
					1.3805393308997376,
					0
				],
				[
					1.994112366855248,
					0
				],
				[
					2.761078661799475,
					0
				],
				[
					3.3746516977549854,
					0
				],
				[
					3.988224733710335,
					0
				],
				[
					4.2950112516880905,
					0
				],
				[
					4.755191028654723,
					0
				],
				[
					5.061977546632479,
					0
				],
				[
					5.215370805621356,
					0
				],
				[
					5.3687640646100725,
					0
				],
				[
					5.522157323599111,
					0.15339325898886252
				],
				[
					5.675550582587827,
					0.30678651797772505
				],
				[
					5.828943841576705,
					0.30678651797772505
				],
				[
					5.982337100565583,
					0.4601797769665876
				],
				[
					5.982337100565583,
					0.613573035955445
				],
				[
					5.675550582587827,
					0.7669662949443076
				],
				[
					5.3687640646100725,
					0.92035955393317
				],
				[
					5.061977546632479,
					1.0737528129220275
				],
				[
					4.755191028654723,
					1.22714607191089
				],
				[
					4.448404510676967,
					1.6873258488774725
				],
				[
					4.141617992699213,
					1.9941123668551926
				],
				[
					3.681438215732741,
					2.6076854028106378
				],
				[
					3.3746516977549854,
					3.374651697754945
				],
				[
					3.0678651797772303,
					3.8348314747215277
				],
				[
					2.6076854028105974,
					4.60179776966583
				],
				[
					2.4542921438218808,
					5.2153708056212755
				],
				[
					2.3008988848330034,
					5.675550582587858
				],
				[
					2.1475056258441256,
					6.13573035955444
				],
				[
					1.8407191078663705,
					6.595910136521023
				],
				[
					1.6873258488774927,
					7.209483172476468
				],
				[
					1.5339325898886151,
					7.823056208431913
				],
				[
					1.2271460719108598,
					8.436629244387353
				],
				[
					1.0737528129221434,
					8.89680902135394
				],
				[
					0.7669662949443882,
					9.51038205730938
				],
				[
					0.4601797769666329,
					9.970561834275964
				],
				[
					0.3067865179777553,
					10.277348352253687
				],
				[
					0.15339325898887765,
					10.737528129220271
				],
				[
					-0.15339325898887765,
					11.044314647197996
				],
				[
					-0.3067865179777553,
					11.351101165175711
				],
				[
					-0.4601797769666329,
					11.657887683153435
				],
				[
					-0.766966294944227,
					11.96467420113116
				],
				[
					-1.0737528129219822,
					12.424853978097744
				],
				[
					-1.2271460719108598,
					12.5782472370866
				],
				[
					-1.3805393308997376,
					12.885033755064326
				],
				[
					-1.5339325898886151,
					13.038427014053184
				],
				[
					-1.6873258488774927,
					13.19182027304204
				],
				[
					-1.6873258488774927,
					13.345213532030908
				],
				[
					-1.6873258488774927,
					13.498606791019766
				],
				[
					-1.0737528129219822,
					13.498606791019766
				],
				[
					-0.4601797769666329,
					13.498606791019766
				],
				[
					0.15339325898887765,
					13.498606791019766
				],
				[
					0.7669662949443882,
					13.345213532030908
				],
				[
					1.2271460719108598,
					13.19182027304204
				],
				[
					1.994112366855248,
					13.038427014053184
				],
				[
					2.4542921438218808,
					12.885033755064326
				],
				[
					2.6076854028105974,
					12.885033755064326
				],
				[
					3.0678651797772303,
					12.731640496075459
				],
				[
					3.528044956743863,
					12.731640496075459
				],
				[
					3.8348314747216183,
					12.5782472370866
				],
				[
					4.141617992699213,
					12.424853978097744
				],
				[
					4.755191028654723,
					12.424853978097744
				],
				[
					5.061977546632479,
					12.271460719108875
				],
				[
					5.061977546632479,
					12.271460719108875
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 334,
			"versionNonce": 947181957,
			"isDeleted": false,
			"id": "50II5BgaMAOIwNQNg5XNo",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1149.9953203914092,
			"y": 441.62412653946603,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 4.908584287643601,
			"height": 0.15339325898886252,
			"seed": 1906782307,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.15339325898887765,
					0
				],
				[
					-0.15339325898887765,
					0.15339325898886252
				],
				[
					0,
					0.15339325898886252
				],
				[
					0.7669662949443882,
					0.15339325898886252
				],
				[
					1.3805393308997376,
					0.15339325898886252
				],
				[
					1.8407191078663705,
					0.15339325898886252
				],
				[
					2.4542921438217196,
					0.15339325898886252
				],
				[
					2.9144719207883525,
					0.15339325898886252
				],
				[
					3.0678651797772303,
					0.15339325898886252
				],
				[
					3.528044956743863,
					0.15339325898886252
				],
				[
					3.834831474721457,
					0.15339325898886252
				],
				[
					3.988224733710335,
					0.15339325898886252
				],
				[
					4.141617992699213,
					0.15339325898886252
				],
				[
					4.2950112516880905,
					0.15339325898886252
				],
				[
					4.601797769665845,
					0.15339325898886252
				],
				[
					4.755191028654723,
					0.15339325898886252
				],
				[
					4.755191028654723,
					0.15339325898886252
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 328,
			"versionNonce": 1493380427,
			"isDeleted": false,
			"id": "8tfsk5CkaOI7ifLEJ5mbQ",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1156.284444009953,
			"y": 432.5739242591232,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.6076854028105974,
			"height": 5.982337100565577,
			"seed": 1254697987,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3067865179777553,
					0.4601797769665876
				],
				[
					0.9203595539331045,
					1.3805393308997527
				],
				[
					1.3805393308997376,
					2.147505625844055
				],
				[
					1.6873258488774927,
					2.9144719207883627
				],
				[
					2.1475056258439644,
					4.29501125168811
				],
				[
					2.4542921438217196,
					4.9085842876435555
				],
				[
					2.4542921438217196,
					5.2153708056212755
				],
				[
					2.4542921438217196,
					5.675550582587858
				],
				[
					2.6076854028105974,
					5.82894384157672
				],
				[
					2.6076854028105974,
					5.982337100565577
				],
				[
					2.6076854028105974,
					5.982337100565577
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 344,
			"versionNonce": 235495653,
			"isDeleted": false,
			"id": "4a4_Tt86yPhWml-1keAEO",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1161.9599945925409,
			"y": 433.954463590023,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.8407191078663705,
			"height": 17.486831524730146,
			"seed": 292205475,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.15339325898887765,
					0
				],
				[
					0,
					0.15339325898885747
				],
				[
					0.3067865179777553,
					0.4601797769665825
				],
				[
					0.6135730359553493,
					1.0737528129220275
				],
				[
					0.766966294944227,
					1.6873258488774676
				],
				[
					0.9203595539331045,
					2.454292143821775
				],
				[
					1.2271460719108598,
					3.37465169775494
				],
				[
					1.3805393308997376,
					4.141617992699243
				],
				[
					1.3805393308997376,
					5.21537080562127
				],
				[
					1.3805393308997376,
					6.2891236185432975
				],
				[
					1.3805393308997376,
					7.97644946742077
				],
				[
					1.3805393308997376,
					9.050202280342793
				],
				[
					1.3805393308997376,
					10.430741611242546
				],
				[
					1.2271460719108598,
					11.351101165175711
				],
				[
					1.2271460719108598,
					12.424853978097739
				],
				[
					1.0737528129219822,
					13.345213532030904
				],
				[
					0.9203595539331045,
					14.572359603941793
				],
				[
					0.766966294944227,
					15.339325898886091
				],
				[
					0.6135730359553493,
					15.646112416863815
				],
				[
					0.4601797769666329,
					16.1062921938304
				],
				[
					0.3067865179777553,
					16.413078711808122
				],
				[
					0.3067865179777553,
					16.71986522978584
				],
				[
					0.15339325898887765,
					17.026651747763562
				],
				[
					-0.15339325898887765,
					17.33343826574129
				],
				[
					-0.3067865179777553,
					17.486831524730146
				],
				[
					-0.4601797769666329,
					17.486831524730146
				],
				[
					-0.4601797769666329,
					17.486831524730146
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 250,
			"versionNonce": 979717099,
			"isDeleted": false,
			"id": "1fqWDxzC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 574.5045496321015,
			"y": 747.471182337792,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 114.52049255371094,
			"height": 35,
			"seed": 2122651245,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Reminder",
			"rawText": "Reminder",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Reminder",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "arrow",
			"version": 262,
			"versionNonce": 39189573,
			"isDeleted": false,
			"id": "dPEQgzYp82NolcKiQ495Q",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 561.348379516362,
			"y": 739.9619201578781,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.403555834405779,
			"height": 71.30548975403906,
			"seed": 819431107,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NpUK2a7g",
				"focus": 0.15561378820195587,
				"gap": 18.501591349894284
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
					-2.403555834405779,
					71.30548975403906
				]
			]
		},
		{
			"type": "image",
			"version": 448,
			"versionNonce": 1934268043,
			"isDeleted": false,
			"id": "wJAVwEYK",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 520.4464586103788,
			"y": 852.8295414882931,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 82,
			"height": 63,
			"seed": 65991,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "56e1fbe897520c33ca3187123ef815a8378b6a99",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 294,
			"versionNonce": 758655909,
			"isDeleted": false,
			"id": "Ci__wsNUIfu6bBhM2GzZ8",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 529.0738694725051,
			"y": 847.964283971385,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 14.468354395375627,
			"height": 2.803944650266544,
			"seed": 115431299,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.11215778601069815,
					0
				],
				[
					0.4486311440426789,
					-0.11215778601058446
				],
				[
					0.8972622880853578,
					-0.4486311440425652
				],
				[
					1.5702090041493193,
					-0.785104502074546
				],
				[
					2.1309979342025827,
					-1.1215778601066404
				],
				[
					2.9161024362772423,
					-1.794524576170602
				],
				[
					3.252575794309223,
					-2.0188401481918845
				],
				[
					3.9255225103731846,
					-2.243155720213281
				],
				[
					4.486311440426562,
					-2.4674712922345634
				],
				[
					5.047100370479939,
					-2.691786864255846
				],
				[
					5.383573728511919,
					-2.803944650266544
				],
				[
					5.832204872554485,
					-2.803944650266544
				],
				[
					6.056520444575881,
					-2.803944650266544
				],
				[
					6.50515158861856,
					-2.803944650266544
				],
				[
					6.8416249466505406,
					-2.803944650266544
				],
				[
					7.2902560906932194,
					-2.803944650266544
				],
				[
					7.738887234735785,
					-2.5796290782452616
				],
				[
					8.075360592767765,
					-2.4674712922345634
				],
				[
					8.299676164789162,
					-2.3553135062238653
				],
				[
					8.860465094842425,
					-2.1309979342025827
				],
				[
					9.309096238885104,
					-2.0188401481918845
				],
				[
					9.869885168938481,
					-1.794524576170602
				],
				[
					10.206358526970462,
					-1.6823667901599038
				],
				[
					10.542831885002443,
					-1.5702090041492056
				],
				[
					11.103620815055706,
					-1.4580512181386212
				],
				[
					11.552251959098385,
					-1.345893432127923
				],
				[
					11.776567531119781,
					-1.345893432127923
				],
				[
					12.225198675162346,
					-1.1215778601066404
				],
				[
					12.561672033194327,
					-1.1215778601066404
				],
				[
					12.898145391226308,
					-1.0094200740959423
				],
				[
					13.122460963247704,
					-1.0094200740959423
				],
				[
					13.346776535268987,
					-0.8972622880852441
				],
				[
					13.571092107290383,
					-0.785104502074546
				],
				[
					13.795407679311666,
					-0.6729467160639615
				],
				[
					13.907565465322364,
					-0.5607889300532634
				],
				[
					14.131881037343646,
					-0.4486311440425652
				],
				[
					14.244038823354344,
					-0.33647335803198075
				],
				[
					14.356196609365043,
					-0.2243155720212826
				],
				[
					14.468354395375627,
					-0.2243155720212826
				],
				[
					14.468354395375627,
					-0.2243155720212826
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 267,
			"versionNonce": 40733995,
			"isDeleted": false,
			"id": "okGB-byLwrOW1xyng_vXA",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 539.9531747155395,
			"y": 819.3640485386658,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.402413876703804,
			"height": 12.561672033194327,
			"seed": 28677059,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.11215778601069815,
					0.2243155720212826
				],
				[
					-0.4486311440426789,
					0.6729467160639615
				],
				[
					-1.0094200740959423,
					1.345893432127923
				],
				[
					-1.345893432127923,
					1.9066823621813
				],
				[
					-1.9066823621813,
					2.5796290782452616
				],
				[
					-2.243155720213281,
					3.1404180082986386
				],
				[
					-2.467471292234677,
					3.589049152341204
				],
				[
					-2.803944650266658,
					4.59846922643726
				],
				[
					-2.9161024362772423,
					5.047100370479825
				],
				[
					-3.0282602222879405,
					5.495731514522504
				],
				[
					-3.364733580319921,
					6.168678230586465
				],
				[
					-3.701206938351902,
					6.729467160639842
				],
				[
					-3.8133647243626,
					6.953782732661125
				],
				[
					-3.9255225103732982,
					7.178098304682521
				],
				[
					-4.037680296383883,
					7.6267294487250865
				],
				[
					-4.149838082394581,
					7.851045020746483
				],
				[
					-4.3741536544158635,
					8.187518378778464
				],
				[
					-4.59846922643726,
					8.636149522821142
				],
				[
					-4.822784798458542,
					9.084780666863821
				],
				[
					-5.159258156490523,
					9.869885168938367
				],
				[
					-5.495731514522504,
					10.430674098991744
				],
				[
					-5.607889300533202,
					10.654989671013027
				],
				[
					-5.832204872554485,
					10.879305243034423
				],
				[
					-6.056520444575881,
					11.215778601066404
				],
				[
					-6.2808360165971635,
					11.440094173087687
				],
				[
					-6.392993802607862,
					11.552251959098385
				],
				[
					-6.617309374629144,
					11.888725317130366
				],
				[
					-6.8416249466505406,
					12.000883103141064
				],
				[
					-7.065940518671823,
					12.337356461173044
				],
				[
					-7.178098304682521,
					12.449514247183743
				],
				[
					-7.402413876703804,
					12.561672033194327
				],
				[
					-7.402413876703804,
					12.561672033194327
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 274,
			"versionNonce": 1323134725,
			"isDeleted": false,
			"id": "YkTfLIJ5GCbsPQUk5Jgwe",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 531.7656563367611,
			"y": 821.7193620448897,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 8.972622880853123,
			"height": 9.196938452874406,
			"seed": 682809773,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4486311440426789,
					0.5607889300532634
				],
				[
					1.1215778601066404,
					1.0094200740959423
				],
				[
					1.9066823621813,
					1.6823667901599038
				],
				[
					2.803944650266544,
					2.243155720213281
				],
				[
					3.9255225103731846,
					3.0282602222878268
				],
				[
					4.59846922643726,
					3.8133647243624864
				],
				[
					5.159258156490523,
					4.486311440426562
				],
				[
					6.168678230586465,
					5.383573728511806
				],
				[
					6.617309374629144,
					5.7200470865437865
				],
				[
					7.178098304682521,
					6.168678230586465
				],
				[
					7.514571662714502,
					6.729467160639842
				],
				[
					7.738887234735785,
					7.065940518671823
				],
				[
					7.851045020746483,
					7.402413876703804
				],
				[
					8.299676164789162,
					7.851045020746483
				],
				[
					8.411833950799746,
					7.963202806757067
				],
				[
					8.636149522821142,
					8.411833950799746
				],
				[
					8.748307308831727,
					8.748307308831727
				],
				[
					8.860465094842425,
					8.860465094842425
				],
				[
					8.972622880853123,
					9.084780666863708
				],
				[
					8.972622880853123,
					9.196938452874406
				],
				[
					8.972622880853123,
					9.196938452874406
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 295,
			"versionNonce": 725135307,
			"isDeleted": false,
			"id": "roAMeBGChFmeJWAPUqz7Y",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 553.7485823948512,
			"y": 847.7399683993638,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 11.664409745109083,
			"height": 3.8133647243626,
			"seed": 1035547725,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.11215778601069815,
					-0.11215778601069815
				],
				[
					0.4486311440426789,
					-0.7851045020746596
				],
				[
					0.7851045020746596,
					-1.2337356461173385
				],
				[
					1.5702090041493193,
					-2.243155720213281
				],
				[
					2.0188401481918845,
					-2.9161024362772423
				],
				[
					2.4674712922345634,
					-3.4768913663306193
				],
				[
					2.803944650266544,
					-3.701206938351902
				],
				[
					3.1404180082986386,
					-3.8133647243626
				],
				[
					3.364733580319921,
					-3.8133647243626
				],
				[
					3.701206938351902,
					-3.8133647243626
				],
				[
					4.037680296383883,
					-3.8133647243626
				],
				[
					4.59846922643726,
					-3.701206938351902
				],
				[
					5.047100370479825,
					-3.701206938351902
				],
				[
					5.7200470865439,
					-3.5890491523413175
				],
				[
					6.2808360165971635,
					-3.5890491523413175
				],
				[
					6.617309374629144,
					-3.5890491523413175
				],
				[
					7.290256090693106,
					-3.5890491523413175
				],
				[
					7.851045020746483,
					-3.4768913663306193
				],
				[
					8.187518378778464,
					-3.4768913663306193
				],
				[
					8.748307308831727,
					-3.2525757943093367
				],
				[
					9.196938452874406,
					-3.0282602222879405
				],
				[
					9.421254024895802,
					-2.803944650266658
				],
				[
					9.869885168938367,
					-2.467471292234677
				],
				[
					10.094200740959764,
					-2.355313506223979
				],
				[
					10.318516312981046,
					-2.243155720213281
				],
				[
					10.430674098991744,
					-2.018840148191998
				],
				[
					10.542831885002443,
					-1.9066823621813
				],
				[
					10.654989671013027,
					-1.794524576170602
				],
				[
					10.767147457023725,
					-1.794524576170602
				],
				[
					10.879305243034423,
					-1.6823667901600174
				],
				[
					10.879305243034423,
					-1.5702090041493193
				],
				[
					10.991463029045008,
					-1.4580512181386212
				],
				[
					11.103620815055706,
					-1.2337356461173385
				],
				[
					11.103620815055706,
					-1.1215778601066404
				],
				[
					11.215778601066404,
					-0.8972622880853578
				],
				[
					11.327936387076988,
					-0.7851045020746596
				],
				[
					11.440094173087687,
					-0.7851045020746596
				],
				[
					11.440094173087687,
					-0.6729467160639615
				],
				[
					11.552251959098385,
					-0.6729467160639615
				],
				[
					11.664409745109083,
					-0.6729467160639615
				],
				[
					11.664409745109083,
					-0.7851045020746596
				],
				[
					11.664409745109083,
					-0.7851045020746596
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 300,
			"versionNonce": 1170425445,
			"isDeleted": false,
			"id": "TfusbPfTw1ba06kRU4V4W",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 556.3282114730964,
			"y": 819.8126796827084,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.047100370479939,
			"height": 17.04798347362089,
			"seed": 1530811597,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.2243155720212826
				],
				[
					0,
					0.7851045020746596
				],
				[
					0,
					1.345893432127923
				],
				[
					0,
					2.3553135062238653
				],
				[
					0.33647335803198075,
					3.4768913663305057
				],
				[
					1.1215778601066404,
					4.822784798458542
				],
				[
					1.794524576170602,
					5.495731514522504
				],
				[
					2.243155720213281,
					5.7200470865437865
				],
				[
					2.803944650266658,
					5.7200470865437865
				],
				[
					3.4768913663306193,
					5.159258156490523
				],
				[
					4.037680296383883,
					4.486311440426562
				],
				[
					4.149838082394581,
					3.364733580319921
				],
				[
					4.261995868405165,
					2.3553135062238653
				],
				[
					4.261995868405165,
					1.5702090041492056
				],
				[
					4.261995868405165,
					1.0094200740959423
				],
				[
					4.261995868405165,
					0.5607889300532634
				],
				[
					4.486311440426562,
					0.11215778601058446
				],
				[
					4.59846922643726,
					0
				],
				[
					4.59846922643726,
					-0.11215778601069815
				],
				[
					4.59846922643726,
					0
				],
				[
					4.710627012447844,
					0.5607889300532634
				],
				[
					4.822784798458542,
					1.2337356461172249
				],
				[
					5.047100370479939,
					2.0188401481918845
				],
				[
					5.047100370479939,
					3.0282602222879405
				],
				[
					5.047100370479939,
					4.822784798458542
				],
				[
					5.047100370479939,
					6.841624946650427
				],
				[
					5.047100370479939,
					7.402413876703804
				],
				[
					5.047100370479939,
					9.757727382927783
				],
				[
					5.047100370479939,
					11.103620815055706
				],
				[
					5.047100370479939,
					12.337356461173044
				],
				[
					4.9349425844692405,
					14.131881037343646
				],
				[
					4.822784798458542,
					14.69266996739691
				],
				[
					4.486311440426562,
					14.916985539418306
				],
				[
					4.261995868405165,
					15.141301111439589
				],
				[
					3.9255225103731846,
					15.47777446947157
				],
				[
					3.4768913663306193,
					15.702090041492966
				],
				[
					3.0282602222879405,
					16.038563399524946
				],
				[
					2.5796290782452616,
					16.26287897154623
				],
				[
					2.018840148191998,
					16.59935232957821
				],
				[
					1.794524576170602,
					16.93582568761019
				],
				[
					1.6823667901599038,
					16.93582568761019
				],
				[
					1.4580512181386212,
					16.823667901599606
				],
				[
					1.2337356461173385,
					16.711510115588908
				],
				[
					0.8972622880853578,
					16.375036757556927
				],
				[
					0.4486311440426789,
					15.81424782750355
				],
				[
					0.33647335803198075,
					15.141301111439589
				],
				[
					0.33647335803198075,
					14.580512181386325
				],
				[
					0.33647335803198075,
					14.019723251332948
				],
				[
					0.4486311440426789,
					13.57109210729027
				],
				[
					0.7851045020746596,
					13.346776535268987
				],
				[
					1.0094200740959423,
					13.346776535268987
				],
				[
					1.1215778601066404,
					13.346776535268987
				],
				[
					1.2337356461173385,
					13.234618749258289
				],
				[
					1.345893432127923,
					13.234618749258289
				],
				[
					1.5702090041493193,
					13.346776535268987
				],
				[
					1.794524576170602,
					13.57109210729027
				],
				[
					2.018840148191998,
					13.90756546532225
				],
				[
					2.243155720213281,
					14.244038823354344
				],
				[
					2.5796290782452616,
					14.69266996739691
				],
				[
					2.803944650266658,
					14.916985539418306
				],
				[
					2.9161024362772423,
					15.141301111439589
				],
				[
					3.1404180082986386,
					15.47777446947157
				],
				[
					3.252575794309223,
					15.589932255482267
				],
				[
					3.252575794309223,
					15.702090041492966
				],
				[
					3.364733580319921,
					15.81424782750355
				],
				[
					3.364733580319921,
					15.81424782750355
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 273,
			"versionNonce": 1606844011,
			"isDeleted": false,
			"id": "S8h0cgN0C31I_FiuElMbE",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 562.9455208477257,
			"y": 844.0387614610119,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.1404180082986386,
			"height": 3.589049152341204,
			"seed": 693116493,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.11215778601069815,
					0
				],
				[
					0.4486311440426789,
					0.2243155720212826
				],
				[
					0.7851045020746596,
					0.4486311440425652
				],
				[
					1.009420074096056,
					0.6729467160639615
				],
				[
					1.2337356461173385,
					0.8972622880852441
				],
				[
					1.6823667901600174,
					1.2337356461172249
				],
				[
					1.794524576170602,
					1.345893432127923
				],
				[
					2.018840148191998,
					1.5702090041493193
				],
				[
					2.243155720213281,
					1.794524576170602
				],
				[
					2.467471292234677,
					2.1309979342025827
				],
				[
					2.5796290782452616,
					2.243155720213281
				],
				[
					2.6917868642559597,
					2.5796290782452616
				],
				[
					2.6917868642559597,
					2.691786864255846
				],
				[
					2.803944650266658,
					2.9161024362772423
				],
				[
					2.803944650266658,
					3.140418008298525
				],
				[
					2.9161024362772423,
					3.252575794309223
				],
				[
					3.0282602222879405,
					3.4768913663305057
				],
				[
					3.0282602222879405,
					3.589049152341204
				],
				[
					3.1404180082986386,
					3.589049152341204
				],
				[
					3.1404180082986386,
					3.589049152341204
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 285,
			"versionNonce": 1152856517,
			"isDeleted": false,
			"id": "tj1kWSpVnqyxZkH8Yai75",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 592.6673341405515,
			"y": 843.4779725309585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 11.888725317130366,
			"height": 2.243155720213167,
			"seed": 978433005,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.2243155720212826,
					-0.11215778601058446
				],
				[
					-0.6729467160639615,
					-0.33647335803198075
				],
				[
					-1.2337356461172249,
					-0.5607889300532634
				],
				[
					-1.9066823621813,
					-0.8972622880852441
				],
				[
					-2.3553135062238653,
					-1.0094200740959423
				],
				[
					-3.0282602222878268,
					-1.1215778601066404
				],
				[
					-3.8133647243624864,
					-1.2337356461172249
				],
				[
					-4.598469226437146,
					-1.2337356461172249
				],
				[
					-5.047100370479825,
					-1.2337356461172249
				],
				[
					-5.607889300533088,
					-1.2337356461172249
				],
				[
					-6.392993802607748,
					-1.2337356461172249
				],
				[
					-6.953782732661125,
					-1.2337356461172249
				],
				[
					-7.514571662714388,
					-1.2337356461172249
				],
				[
					-8.18751837877835,
					-1.2337356461172249
				],
				[
					-8.523991736810444,
					-1.2337356461172249
				],
				[
					-8.97262288085301,
					-1.1215778601066404
				],
				[
					-9.421254024895688,
					-1.1215778601066404
				],
				[
					-9.869885168938367,
					-1.0094200740959423
				],
				[
					-10.206358526970348,
					-0.8972622880852441
				],
				[
					-10.43067409899163,
					-0.8972622880852441
				],
				[
					-10.767147457023725,
					-0.7851045020746596
				],
				[
					-11.21577860106629,
					-0.4486311440426789
				],
				[
					-11.21577860106629,
					-0.2243155720212826
				],
				[
					-11.327936387076988,
					-0.2243155720212826
				],
				[
					-11.440094173087687,
					-0.11215778601058446
				],
				[
					-11.440094173087687,
					0
				],
				[
					-11.552251959098385,
					0.2243155720213963
				],
				[
					-11.552251959098385,
					0.33647335803198075
				],
				[
					-11.66440974510897,
					0.4486311440426789
				],
				[
					-11.66440974510897,
					0.560788930053377
				],
				[
					-11.66440974510897,
					0.6729467160639615
				],
				[
					-11.776567531119667,
					0.7851045020746596
				],
				[
					-11.888725317130366,
					0.8972622880853578
				],
				[
					-11.888725317130366,
					1.0094200740959423
				],
				[
					-11.888725317130366,
					1.0094200740959423
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 311,
			"versionNonce": 1793161483,
			"isDeleted": false,
			"id": "PbZKn0-MXspRGe4K8zeac",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 582.6852911856024,
			"y": 824.0746755511136,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 12.00088310314095,
			"height": 11.440094173087687,
			"seed": 901196749,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4486311440426789,
					-0.2243155720212826
				],
				[
					1.9066823621813,
					-0.2243155720212826
				],
				[
					4.037680296383996,
					-0.2243155720212826
				],
				[
					6.8416249466505406,
					-0.2243155720212826
				],
				[
					9.19693845287452,
					-0.2243155720212826
				],
				[
					11.552251959098385,
					-0.2243155720212826
				],
				[
					11.776567531119781,
					-0.2243155720212826
				],
				[
					11.888725317130366,
					-0.11215778601058446
				],
				[
					11.552251959098385,
					0.2243155720213963
				],
				[
					11.10362081505582,
					0.560788930053377
				],
				[
					9.869885168938481,
					1.009420074096056
				],
				[
					8.636149522821142,
					1.5702090041493193
				],
				[
					8.075360592767765,
					2.018840148191998
				],
				[
					7.065940518671823,
					2.803944650266658
				],
				[
					6.280836016597277,
					3.5890491523413175
				],
				[
					5.607889300533202,
					4.261995868405279
				],
				[
					4.59846922643726,
					5.271415942501221
				],
				[
					4.149838082394581,
					5.832204872554598
				],
				[
					3.4768913663306193,
					6.50515158861856
				],
				[
					2.6917868642559597,
					7.2902560906932194
				],
				[
					2.1309979342026963,
					7.851045020746483
				],
				[
					1.3458934321280367,
					8.636149522821142
				],
				[
					0.6729467160639615,
					9.309096238885104
				],
				[
					0.33647335803198075,
					9.869885168938481
				],
				[
					0.11215778601069815,
					10.206358526970462
				],
				[
					0,
					10.767147457023725
				],
				[
					-0.11215778601058446,
					10.991463029045121
				],
				[
					-0.11215778601058446,
					11.103620815055706
				],
				[
					-0.11215778601058446,
					11.215778601066404
				],
				[
					0,
					11.215778601066404
				],
				[
					0.6729467160639615,
					11.215778601066404
				],
				[
					1.4580512181386212,
					11.215778601066404
				],
				[
					2.467471292234677,
					11.215778601066404
				],
				[
					3.4768913663306193,
					10.991463029045121
				],
				[
					4.822784798458542,
					10.991463029045121
				],
				[
					5.383573728511919,
					10.879305243034423
				],
				[
					5.495731514522504,
					10.879305243034423
				],
				[
					5.607889300533202,
					10.879305243034423
				],
				[
					5.832204872554598,
					10.991463029045121
				],
				[
					5.944362658565183,
					10.991463029045121
				],
				[
					6.056520444575881,
					11.103620815055706
				],
				[
					6.168678230586579,
					11.103620815055706
				],
				[
					6.280836016597277,
					11.103620815055706
				],
				[
					6.392993802607862,
					10.991463029045121
				],
				[
					6.50515158861856,
					10.991463029045121
				],
				[
					6.50515158861856,
					10.879305243034423
				],
				[
					6.729467160639842,
					10.879305243034423
				],
				[
					7.178098304682521,
					10.767147457023725
				],
				[
					7.514571662714502,
					10.65498967101314
				],
				[
					7.963202806757181,
					10.65498967101314
				],
				[
					8.299676164789162,
					10.65498967101314
				],
				[
					8.523991736810558,
					10.65498967101314
				],
				[
					8.636149522821142,
					10.65498967101314
				],
				[
					8.74830730883184,
					10.65498967101314
				],
				[
					8.972622880853123,
					10.65498967101314
				],
				[
					9.19693845287452,
					10.65498967101314
				],
				[
					9.309096238885104,
					10.65498967101314
				],
				[
					9.421254024895802,
					10.767147457023725
				],
				[
					9.645569596917085,
					10.879305243034423
				],
				[
					9.757727382927783,
					10.879305243034423
				],
				[
					9.757727382927783,
					10.879305243034423
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 268,
			"versionNonce": 1222029605,
			"isDeleted": false,
			"id": "X_CbGPRRQ5TKvN8QiaOEL",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 583.0217645436344,
			"y": 828.5609869915402,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.738887234735785,
			"height": 0.6729467160639615,
			"seed": 1612183917,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33647335803198075,
					0
				],
				[
					1.009420074096056,
					0
				],
				[
					1.5702090041493193,
					0
				],
				[
					2.467471292234677,
					0
				],
				[
					3.364733580319921,
					0.2243155720213963
				],
				[
					4.261995868405279,
					0.2243155720213963
				],
				[
					4.9349425844692405,
					0.2243155720213963
				],
				[
					5.383573728511919,
					0.4486311440426789
				],
				[
					5.7200470865439,
					0.560788930053377
				],
				[
					6.168678230586579,
					0.6729467160639615
				],
				[
					6.50515158861856,
					0.6729467160639615
				],
				[
					6.729467160639842,
					0.6729467160639615
				],
				[
					7.065940518671823,
					0.6729467160639615
				],
				[
					7.2902560906932194,
					0.6729467160639615
				],
				[
					7.514571662714502,
					0.6729467160639615
				],
				[
					7.6267294487252,
					0.6729467160639615
				],
				[
					7.738887234735785,
					0.6729467160639615
				],
				[
					7.738887234735785,
					0.6729467160639615
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "arrow",
			"version": 250,
			"versionNonce": 1510219691,
			"isDeleted": false,
			"id": "QSt8Ydbrln9awkPmiPnFP",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 608.1854480562017,
			"y": 830.0875392335688,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 21.844215973413384,
			"height": 0.8651174642936894,
			"seed": 379444971,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "tG5oiyN4",
				"focus": 0.317425808050116,
				"gap": 9.341549783710207
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
					21.844215973413384,
					-0.8651174642936894
				]
			]
		},
		{
			"type": "text",
			"version": 395,
			"versionNonce": 1334789253,
			"isDeleted": false,
			"id": "tG5oiyN4",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 639.3712138133253,
			"y": 805.8229140007032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 188.83242797851562,
			"height": 60,
			"seed": 1420933253,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "QSt8Ydbrln9awkPmiPnFP",
					"type": "arrow"
				}
			],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "How the standard basis\nget transformed by this\nmatrix, aka its basis",
			"rawText": "How the standard basis\nget transformed by this\nmatrix, aka its basis",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How the standard basis\nget transformed by this\nmatrix, aka its basis",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "freedraw",
			"version": 308,
			"versionNonce": 660140619,
			"isDeleted": false,
			"id": "iUj_dynoD63BCIpCOzcw6",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1137.520222836971,
			"y": 401.2192467991116,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffd43b",
			"width": 12.591881190739308,
			"height": 12.414530751433194,
			"seed": 2134856267,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5320513179185827,
					0
				],
				[
					1.2414530751433597,
					-0.17735043930619424
				],
				[
					2.128205271674331,
					-0.35470087861238847
				],
				[
					3.1923079075114966,
					-0.35470087861238847
				],
				[
					4.256410543348662,
					-0.5320513179185827
				],
				[
					4.6111114219608895,
					-0.5320513179185827
				],
				[
					4.965812300573278,
					-0.5320513179185827
				],
				[
					5.320513179185666,
					-0.17735043930619424
				],
				[
					5.675214057798055,
					0.17735043930619424
				],
				[
					6.207265375716637,
					1.4188035144495137
				],
				[
					6.73931669363522,
					2.12820527167425
				],
				[
					7.094017572247608,
					3.014957468205181
				],
				[
					7.094017572247608,
					3.724359225429958
				],
				[
					7.094017572247608,
					4.433760982654695
				],
				[
					6.916667132941415,
					5.675214057798014
				],
				[
					6.561966254329026,
					6.561966254328945
				],
				[
					6.207265375716637,
					7.448718450859916
				],
				[
					5.49786361849186,
					8.158120208084654
				],
				[
					5.143162739879472,
					8.86752196530939
				],
				[
					3.9017096647362735,
					9.754274161840321
				],
				[
					3.547008786123885,
					10.286325479758904
				],
				[
					2.8376070288991078,
					10.818376797677447
				],
				[
					2.305555710980525,
					10.99572723698364
				],
				[
					1.7735043930619425,
					11.173077676289834
				],
				[
					1.2414530751433597,
					11.173077676289834
				],
				[
					0.8867521965309713,
					11.173077676289834
				],
				[
					0.5320513179185827,
					10.818376797677447
				],
				[
					0.17735043930619424,
					10.108975040452709
				],
				[
					-0.17735043930619424,
					9.399573283227973
				],
				[
					-0.7094017572246157,
					8.158120208084654
				],
				[
					-0.8867521965308099,
					7.094017572247528
				],
				[
					-0.8867521965308099,
					5.852564497104209
				],
				[
					-0.8867521965308099,
					4.6111114219608895
				],
				[
					1.4188035144495539,
					1.064102635837125
				],
				[
					2.4829061502867193,
					1.064102635837125
				],
				[
					3.369658346817691,
					1.064102635837125
				],
				[
					4.6111114219608895,
					1.064102635837125
				],
				[
					6.561966254329026,
					1.773504393061862
				],
				[
					8.335470647390968,
					2.8376070288990274
				],
				[
					9.044872404615584,
					3.3696583468175696
				],
				[
					10.463675919065137,
					4.433760982654695
				],
				[
					11.173077676289916,
					5.49786361849182
				],
				[
					11.527778554902303,
					6.384615815022751
				],
				[
					11.705128994208497,
					7.626068890166071
				],
				[
					11.705128994208497,
					8.335470647390807
				],
				[
					10.818376797677526,
					9.576923722534167
				],
				[
					9.931624601146556,
					10.641026358371251
				],
				[
					8.512821086697,
					11.527778554902223
				],
				[
					6.207265375716637,
					11.882479433514611
				],
				[
					3.9017096647362735,
					11.882479433514611
				],
				[
					2.128205271674331,
					11.882479433514611
				],
				[
					1.2414530751433597,
					11.882479433514611
				],
				[
					0.7094017572247769,
					11.705128994208417
				],
				[
					0.35470087861238847,
					10.99572723698364
				],
				[
					0.35470087861238847,
					10.286325479758904
				],
				[
					0.17735043930619424,
					9.399573283227973
				],
				[
					0.17735043930619424,
					8.512821086697
				],
				[
					0.17735043930619424,
					7.8034193294722645
				],
				[
					0.17735043930619424,
					7.448718450859916
				],
				[
					0.17735043930619424,
					7.271368011553722
				],
				[
					0.17735043930619424,
					7.271368011553722
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 365,
			"versionNonce": 1285450725,
			"isDeleted": false,
			"id": "-o5Yjluv1VkZtlzbuOoNT",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1144.6142404092186,
			"y": 402.1059989956425,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffd43b",
			"width": 23.764958867029062,
			"height": 21.459403156048737,
			"seed": 1144667269,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.35470087861238847,
					-0.35470087861234817
				],
				[
					1.0641026358371655,
					-0.886752196530931
				],
				[
					1.5961539537555869,
					-1.4188035144495137
				],
				[
					2.482906150286558,
					-1.5961539537556675
				],
				[
					3.547008786123724,
					-1.5961539537556675
				],
				[
					5.320513179185666,
					-0.5320513179185424
				],
				[
					6.739316693635059,
					0.5320513179185827
				],
				[
					7.271368011553641,
					0.886752196530931
				],
				[
					8.158120208084613,
					3.3696583468175696
				],
				[
					8.158120208084613,
					5.143162739879472
				],
				[
					7.8034193294722245,
					6.916667132941334
				],
				[
					6.561966254328865,
					9.044872404615584
				],
				[
					5.143162739879472,
					10.641026358371292
				],
				[
					3.0149574682051408,
					12.591881190739349
				],
				[
					0.8867521965309713,
					13.478633387270278
				],
				[
					-0.17735043930619424,
					14.010684705188861
				],
				[
					-2.8376070288989466,
					11.173077676289834
				],
				[
					-2.8376070288989466,
					10.995727236983681
				],
				[
					-2.8376070288989466,
					10.463675919065098
				],
				[
					-2.8376070288989466,
					8.690171526003235
				],
				[
					-2.305555710980525,
					6.916667132941334
				],
				[
					-1.0641026358371655,
					4.965812300573278
				],
				[
					0,
					3.9017096647361527
				],
				[
					2.305555710980364,
					3.1923079075113754
				],
				[
					4.0790601040423065,
					3.1923079075113754
				],
				[
					7.271368011553641,
					4.433760982654695
				],
				[
					9.75427416184036,
					6.029914936410403
				],
				[
					12.414530751433114,
					7.8034193294722645
				],
				[
					14.010684705188861,
					9.399573283227973
				],
				[
					15.074787341026028,
					10.995727236983681
				],
				[
					15.606838658944449,
					12.591881190739349
				],
				[
					14.897436901719832,
					14.010684705188861
				],
				[
					13.478633387270278,
					15.784189098250723
				],
				[
					10.818376797677365,
					17.025642173394044
				],
				[
					6.916667132941253,
					18.089744809231167
				],
				[
					2.482906150286558,
					18.62179612714975
				],
				[
					-0.8867521965309713,
					18.62179612714975
				],
				[
					-4.2564105433485,
					18.089744809231167
				],
				[
					-6.384615815022832,
					16.670941294781656
				],
				[
					-7.448718450859997,
					15.25213778033218
				],
				[
					-8.158120208084613,
					13.478633387270278
				],
				[
					-8.158120208084613,
					11.350428115596028
				],
				[
					-8.158120208084613,
					9.044872404615584
				],
				[
					-8.158120208084613,
					6.739316693635139
				],
				[
					-7.62606889016603,
					4.433760982654695
				],
				[
					-7.271368011553803,
					3.3696583468175696
				],
				[
					-6.561966254329026,
					2.3055557109804448
				],
				[
					-5.8525644971042485,
					1.596153953755708
				],
				[
					-4.788461861267083,
					1.064102635837125
				],
				[
					-3.9017096647361122,
					0.17735043930619424
				],
				[
					-2.8376070288989466,
					-0.17735043930615393
				],
				[
					-1.9508548323681367,
					-0.7094017572247366
				],
				[
					-0.8867521965309713,
					-1.064102635837125
				],
				[
					0.5320513179185827,
					-1.773504393061862
				],
				[
					2.305555710980364,
					-2.4829061502865986
				],
				[
					4.433760982654695,
					-2.6602565895927928
				],
				[
					6.029914936410443,
					-2.837607028898987
				],
				[
					7.62606889016603,
					-2.837607028898987
				],
				[
					8.335470647390807,
					-2.837607028898987
				],
				[
					9.222222843921779,
					-2.6602565895927928
				],
				[
					9.931624601146556,
					-2.3055557109804448
				],
				[
					10.641026358371171,
					-1.773504393061862
				],
				[
					11.705128994208337,
					-1.064102635837125
				],
				[
					12.237180312126918,
					0.17735043930619424
				],
				[
					12.591881190739308,
					1.4188035144495137
				],
				[
					12.769231630045502,
					2.660256589592833
				],
				[
					12.946582069351695,
					4.256410543348541
				],
				[
					13.301282947964085,
					6.561966254328985
				],
				[
					13.301282947964085,
					9.044872404615584
				],
				[
					13.301282947964085,
					10.995727236983681
				],
				[
					12.946582069351695,
					13.12393250865793
				],
				[
					12.414530751433114,
					15.25213778033218
				],
				[
					11.350428115595948,
					16.49359085547546
				],
				[
					10.286325479758943,
					17.38034305200643
				],
				[
					9.399573283227973,
					18.444445687843558
				],
				[
					7.980769768778418,
					18.62179612714975
				],
				[
					6.916667132941253,
					18.62179612714975
				],
				[
					6.029914936410443,
					18.62179612714975
				],
				[
					5.143162739879472,
					18.267095248537363
				],
				[
					4.433760982654695,
					17.73504393061882
				],
				[
					3.192307907511335,
					16.670941294781656
				],
				[
					2.6602565895927524,
					15.961539537556918
				],
				[
					1.773504393061781,
					14.7200864624136
				],
				[
					0.8867521965309713,
					13.655983826576474
				],
				[
					-0.17735043930619424,
					12.414530751433153
				],
				[
					-0.7094017572247769,
					10.995727236983681
				],
				[
					-1.2414530751433597,
					9.576923722534167
				],
				[
					-1.5961539537557483,
					8.512821086697041
				],
				[
					-1.5961539537557483,
					7.271368011553722
				],
				[
					-1.5961539537557483,
					6.029914936410403
				],
				[
					-1.2414530751433597,
					4.965812300573278
				],
				[
					-0.8867521965309713,
					3.9017096647361527
				],
				[
					-0.35470087861238847,
					3.014957468205181
				],
				[
					0.17735043930619424,
					1.773504393061902
				],
				[
					0.7094017572247769,
					1.064102635837125
				],
				[
					1.2414530751433597,
					0.5320513179185827
				],
				[
					1.9508548323679755,
					0
				],
				[
					2.482906150286558,
					-0.17735043930615393
				],
				[
					3.0149574682051408,
					-0.5320513179185424
				],
				[
					3.547008786123724,
					-0.7094017572247366
				],
				[
					4.0790601040423065,
					-0.886752196530931
				],
				[
					4.6111114219608895,
					-1.064102635837125
				],
				[
					5.320513179185666,
					-1.064102635837125
				],
				[
					5.8525644971042485,
					-1.2414530751433195
				],
				[
					6.384615815022832,
					-1.2414530751433195
				],
				[
					6.916667132941253,
					-1.2414530751433195
				],
				[
					7.448718450859836,
					-1.2414530751433195
				],
				[
					7.8034193294722245,
					-1.064102635837125
				],
				[
					8.690171526003196,
					-0.7094017572247366
				],
				[
					9.222222843921779,
					-0.35470087861234817
				],
				[
					9.576923722534167,
					0.17735043930619424
				],
				[
					10.10897504045275,
					0.886752196530931
				],
				[
					10.463675919064977,
					1.4188035144495137
				],
				[
					10.641026358371171,
					1.773504393061902
				],
				[
					10.818376797677365,
					2.3055557109804448
				],
				[
					10.818376797677365,
					2.482906150286639
				],
				[
					10.818376797677365,
					2.660256589592833
				],
				[
					10.818376797677365,
					2.660256589592833
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 303,
			"versionNonce": 599421163,
			"isDeleted": false,
			"id": "yWGc636LIbcTKOjuLCpPO",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1083.4283388485837,
			"y": 383.8389037471052,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.62606889016603,
			"height": 17.912394369924975,
			"seed": 875956453,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.17735043930615393
				],
				[
					-0.5320513179184215,
					0.5320513179185424
				],
				[
					-1.0641026358370043,
					0.7094017572247366
				],
				[
					-1.773504393061781,
					1.0641026358370849
				],
				[
					-2.482906150286558,
					1.4188035144494733
				],
				[
					-3.3696583468175296,
					1.773504393061862
				],
				[
					-4.2564105433485,
					2.4829061502865986
				],
				[
					-4.611111421960728,
					2.837607028898987
				],
				[
					-4.611111421960728,
					3.014957468205181
				],
				[
					-4.965812300573116,
					3.547008786123724
				],
				[
					-5.320513179185505,
					4.2564105433485
				],
				[
					-5.497863618491699,
					4.6111114219608895
				],
				[
					-5.497863618491699,
					5.143162739879432
				],
				[
					-5.497863618491699,
					5.852564497104169
				],
				[
					-5.497863618491699,
					6.739316693635139
				],
				[
					-5.497863618491699,
					7.271368011553682
				],
				[
					-5.143162739879311,
					8.158120208084613
				],
				[
					-4.7884618612669225,
					8.86752196530939
				],
				[
					-4.2564105433485,
					9.222222843921738
				],
				[
					-3.9017096647361122,
					9.931624601146515
				],
				[
					-3.0149574682051408,
					10.463675919065057
				],
				[
					-2.6602565895927524,
					10.99572723698364
				],
				[
					-2.305555710980364,
					11.350428115596028
				],
				[
					-1.773504393061781,
					11.705128994208376
				],
				[
					-1.4188035144493927,
					11.882479433514572
				],
				[
					-1.0641026358370043,
					12.414530751433114
				],
				[
					-0.7094017572246157,
					12.591881190739308
				],
				[
					-0.17735043930603298,
					13.12393250865789
				],
				[
					0.17735043930619424,
					13.655983826576433
				],
				[
					0.35470087861238847,
					14.188035144495016
				],
				[
					0.5320513179185827,
					14.720086462413558
				],
				[
					0.7094017572247769,
					15.252137780332141
				],
				[
					0.7094017572247769,
					15.606838658944529
				],
				[
					0.7094017572247769,
					16.138889976863073
				],
				[
					0.5320513179185827,
					16.670941294781656
				],
				[
					0.35470087861238847,
					17.025642173394
				],
				[
					-0.17735043930603298,
					17.202992612700196
				],
				[
					-0.8867521965308099,
					17.380343052006392
				],
				[
					-1.4188035144493927,
					17.380343052006392
				],
				[
					-1.9508548323679755,
					17.557693491312584
				],
				[
					-2.482906150286558,
					17.73504393061878
				],
				[
					-2.8376070288989466,
					17.73504393061878
				],
				[
					-3.3696583468175296,
					17.912394369924975
				],
				[
					-3.724359225429918,
					17.912394369924975
				],
				[
					-4.0790601040423065,
					17.912394369924975
				],
				[
					-4.433760982654533,
					17.912394369924975
				],
				[
					-4.7884618612669225,
					17.912394369924975
				],
				[
					-5.143162739879311,
					17.73504393061878
				],
				[
					-5.497863618491699,
					17.557693491312584
				],
				[
					-6.0299149364102815,
					17.380343052006392
				],
				[
					-6.207265375716476,
					17.202992612700196
				],
				[
					-6.561966254328865,
					17.202992612700196
				],
				[
					-6.739316693635059,
					17.202992612700196
				],
				[
					-6.739316693635059,
					17.025642173394
				],
				[
					-6.916667132941253,
					17.025642173394
				],
				[
					-6.916667132941253,
					17.025642173394
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 398,
			"versionNonce": 1611769669,
			"isDeleted": false,
			"id": "9yFS1WCD11R4DPszMU45n",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1082.1868857734405,
			"y": 384.1936046257175,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 8.86752196530939,
			"height": 16.848291734087848,
			"seed": 1456464037,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.17735043930619424
				],
				[
					0.17735043930619424,
					-0.17735043930619424
				],
				[
					0.35470087861238847,
					-0.17735043930619424
				],
				[
					0.5320513179185827,
					-0.17735043930619424
				],
				[
					0.7094017572247769,
					-0.17735043930619424
				],
				[
					0.8867521965309713,
					-0.17735043930619424
				],
				[
					1.2414530751431985,
					0
				],
				[
					1.5961539537555869,
					0.17735043930619424
				],
				[
					1.773504393061781,
					0.35470087861238847
				],
				[
					1.773504393061781,
					0.5320513179185827
				],
				[
					1.9508548323679755,
					0.7094017572247366
				],
				[
					2.1282052716741697,
					0.886752196530931
				],
				[
					2.305555710980364,
					1.2414530751433195
				],
				[
					2.305555710980364,
					1.4188035144495137
				],
				[
					2.482906150286558,
					1.596153953755708
				],
				[
					2.6602565895927524,
					1.9508548323680963
				],
				[
					2.6602565895927524,
					2.3055557109804448
				],
				[
					2.8376070288989466,
					2.660256589592833
				],
				[
					3.0149574682051408,
					2.660256589592833
				],
				[
					3.0149574682051408,
					2.8376070288990274
				],
				[
					3.0149574682051408,
					3.014957468205181
				],
				[
					3.0149574682051408,
					2.8376070288990274
				],
				[
					3.192307907511335,
					2.8376070288990274
				],
				[
					3.192307907511335,
					2.660256589592833
				],
				[
					3.192307907511335,
					2.12820527167425
				],
				[
					3.192307907511335,
					1.773504393061902
				],
				[
					3.192307907511335,
					1.4188035144495137
				],
				[
					3.192307907511335,
					1.064102635837125
				],
				[
					3.192307907511335,
					0.7094017572247366
				],
				[
					3.0149574682051408,
					0.5320513179185827
				],
				[
					2.8376070288989466,
					0.17735043930619424
				],
				[
					2.6602565895927524,
					0
				],
				[
					2.305555710980364,
					-0.35470087861234817
				],
				[
					2.1282052716741697,
					-0.5320513179185424
				],
				[
					1.9508548323679755,
					-0.5320513179185424
				],
				[
					1.9508548323679755,
					-0.7094017572247366
				],
				[
					1.773504393061781,
					-0.7094017572247366
				],
				[
					1.5961539537555869,
					-0.7094017572247366
				],
				[
					1.4188035144493927,
					-0.7094017572247366
				],
				[
					1.2414530751431985,
					-0.7094017572247366
				],
				[
					1.0641026358371655,
					-0.7094017572247366
				],
				[
					0.7094017572247769,
					-0.7094017572247366
				],
				[
					0.35470087861238847,
					-0.5320513179185424
				],
				[
					0.17735043930619424,
					-0.35470087861234817
				],
				[
					0,
					-0.35470087861234817
				],
				[
					-0.17735043930619424,
					-0.17735043930619424
				],
				[
					-0.17735043930619424,
					0
				],
				[
					-0.35470087861238847,
					0.17735043930619424
				],
				[
					-0.5320513179185827,
					0.17735043930619424
				],
				[
					-0.7094017572247769,
					0.17735043930619424
				],
				[
					-0.7094017572247769,
					0.35470087861238847
				],
				[
					-1.0641026358371655,
					0.5320513179185827
				],
				[
					-1.2414530751433597,
					0.7094017572247366
				],
				[
					-1.4188035144495539,
					0.7094017572247366
				],
				[
					-1.5961539537557483,
					0.886752196530931
				],
				[
					-1.5961539537557483,
					1.064102635837125
				],
				[
					-1.7735043930619425,
					1.064102635837125
				],
				[
					-1.7735043930619425,
					1.2414530751433195
				],
				[
					-1.9508548323681367,
					1.4188035144495137
				],
				[
					-2.128205271674331,
					1.596153953755708
				],
				[
					-2.128205271674331,
					1.773504393061902
				],
				[
					-2.305555710980525,
					1.9508548323680963
				],
				[
					-2.4829061502867193,
					2.12820527167425
				],
				[
					-2.4829061502867193,
					2.3055557109804448
				],
				[
					-2.6602565895929136,
					2.482906150286639
				],
				[
					-2.6602565895929136,
					2.8376070288990274
				],
				[
					-2.8376070288991078,
					3.014957468205181
				],
				[
					-2.8376070288991078,
					3.3696583468175696
				],
				[
					-3.014957468205302,
					3.547008786123764
				],
				[
					-3.014957468205302,
					3.724359225429958
				],
				[
					-3.014957468205302,
					3.9017096647361527
				],
				[
					-3.014957468205302,
					4.256410543348541
				],
				[
					-3.014957468205302,
					4.433760982654695
				],
				[
					-3.014957468205302,
					4.6111114219608895
				],
				[
					-3.014957468205302,
					4.788461861267083
				],
				[
					-3.014957468205302,
					4.965812300573278
				],
				[
					-3.014957468205302,
					5.3205131791856255
				],
				[
					-3.014957468205302,
					5.675214057798014
				],
				[
					-3.014957468205302,
					6.029914936410403
				],
				[
					-3.014957468205302,
					6.384615815022792
				],
				[
					-3.014957468205302,
					6.561966254328945
				],
				[
					-3.014957468205302,
					6.916667132941334
				],
				[
					-3.014957468205302,
					7.271368011553722
				],
				[
					-3.014957468205302,
					7.448718450859876
				],
				[
					-2.8376070288991078,
					7.626068890166071
				],
				[
					-2.8376070288991078,
					7.980769768778459
				],
				[
					-2.8376070288991078,
					8.158120208084654
				],
				[
					-2.6602565895929136,
					8.335470647390848
				],
				[
					-2.4829061502867193,
					8.690171526003235
				],
				[
					-2.305555710980525,
					9.222222843921779
				],
				[
					-2.128205271674331,
					9.576923722534167
				],
				[
					-1.9508548323681367,
					9.931624601146515
				],
				[
					-1.7735043930619425,
					10.286325479758904
				],
				[
					-1.5961539537557483,
					10.463675919065098
				],
				[
					-1.2414530751433597,
					10.818376797677486
				],
				[
					-1.0641026358371655,
					10.995727236983681
				],
				[
					-0.7094017572247769,
					11.527778554902223
				],
				[
					-0.35470087861238847,
					11.705128994208417
				],
				[
					-0.17735043930619424,
					12.059829872820766
				],
				[
					0.17735043930619424,
					12.059829872820766
				],
				[
					0.35470087861238847,
					12.23718031212696
				],
				[
					0.7094017572247769,
					12.591881190739349
				],
				[
					0.8867521965309713,
					12.769231630045542
				],
				[
					1.0641026358371655,
					12.946582069351736
				],
				[
					1.2414530751431985,
					13.12393250865793
				],
				[
					1.5961539537555869,
					13.655983826576474
				],
				[
					1.773504393061781,
					14.010684705188861
				],
				[
					1.9508548323679755,
					14.188035144495016
				],
				[
					1.9508548323679755,
					14.542736023107404
				],
				[
					1.9508548323679755,
					14.897436901719793
				],
				[
					1.9508548323679755,
					15.074787341025987
				],
				[
					1.9508548323679755,
					15.25213778033218
				],
				[
					1.773504393061781,
					15.429488219638376
				],
				[
					1.4188035144493927,
					15.606838658944529
				],
				[
					1.0641026358371655,
					15.784189098250723
				],
				[
					0.8867521965309713,
					15.784189098250723
				],
				[
					0.7094017572247769,
					15.961539537556918
				],
				[
					0.5320513179185827,
					16.138889976863112
				],
				[
					0.17735043930619424,
					16.138889976863112
				],
				[
					0,
					16.138889976863112
				],
				[
					-0.17735043930619424,
					16.138889976863112
				],
				[
					-0.35470087861238847,
					16.138889976863112
				],
				[
					-0.5320513179185827,
					16.138889976863112
				],
				[
					-0.8867521965309713,
					16.138889976863112
				],
				[
					-1.2414530751433597,
					16.138889976863112
				],
				[
					-1.4188035144495539,
					16.138889976863112
				],
				[
					-1.5961539537557483,
					16.138889976863112
				],
				[
					-1.7735043930619425,
					16.138889976863112
				],
				[
					-1.9508548323681367,
					16.138889976863112
				],
				[
					-2.128205271674331,
					16.138889976863112
				],
				[
					-2.305555710980525,
					16.138889976863112
				],
				[
					-2.6602565895929136,
					16.138889976863112
				],
				[
					-2.8376070288991078,
					16.138889976863112
				],
				[
					-3.014957468205302,
					15.961539537556918
				],
				[
					-3.192307907511335,
					15.961539537556918
				],
				[
					-3.3696583468175296,
					15.784189098250723
				],
				[
					-3.547008786123724,
					15.606838658944529
				],
				[
					-3.724359225429918,
					15.606838658944529
				],
				[
					-3.9017096647361122,
					15.606838658944529
				],
				[
					-4.0790601040423065,
					15.429488219638376
				],
				[
					-4.2564105433485,
					15.25213778033218
				],
				[
					-4.433760982654695,
					14.897436901719793
				],
				[
					-4.6111114219608895,
					14.897436901719793
				],
				[
					-4.788461861267083,
					14.7200864624136
				],
				[
					-4.965812300573278,
					14.542736023107404
				],
				[
					-5.143162739879472,
					14.36538558380121
				],
				[
					-5.320513179185666,
					14.188035144495016
				],
				[
					-5.49786361849186,
					14.188035144495016
				],
				[
					-5.49786361849186,
					14.010684705188861
				],
				[
					-5.675214057798055,
					13.833334265882668
				],
				[
					-5.675214057798055,
					13.833334265882668
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 390,
			"versionNonce": 548608907,
			"isDeleted": false,
			"id": "aC67aIvL068WgKeBRB7Es",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1039.9812757785983,
			"y": 504.9696599232524,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 16.522622378044446,
			"height": 41.65562543197129,
			"seed": 114928139,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.2327129912401126
				],
				[
					0,
					-0.6981389737201765
				],
				[
					0,
					-1.1635649562003212
				],
				[
					0,
					-1.8617039299204976
				],
				[
					0,
					-2.3271299124006424
				],
				[
					-0.23271299123995134,
					-2.559842903640674
				],
				[
					-0.23271299123995134,
					-3.0252688861208186
				],
				[
					-0.6981389737201765,
					-3.2579818773609315
				],
				[
					-1.1635649562002404,
					-3.723407859840995
				],
				[
					-1.396277947440353,
					-3.9561208510811077
				],
				[
					-1.861703929920417,
					-4.18883384232114
				],
				[
					-2.3271299124004807,
					-4.421546833561171
				],
				[
					-2.5598429036405936,
					-4.421546833561171
				],
				[
					-3.25798187736077,
					-4.654259824801285
				],
				[
					-3.9561208510809465,
					-4.654259824801285
				],
				[
					-4.654259824801285,
					-4.654259824801285
				],
				[
					-5.3523987985214605,
					-4.654259824801285
				],
				[
					-6.050537772241637,
					-4.654259824801285
				],
				[
					-6.515963754721701,
					-4.654259824801285
				],
				[
					-6.9813897372017655,
					-4.654259824801285
				],
				[
					-7.44681571968199,
					-4.421546833561171
				],
				[
					-7.912241702162055,
					-4.18883384232114
				],
				[
					-8.37766768464228,
					-4.18883384232114
				],
				[
					-9.075806658362456,
					-3.490694868600963
				],
				[
					-9.54123264084252,
					-3.2579818773609315
				],
				[
					-9.773945632082633,
					-3.0252688861208186
				],
				[
					-10.239371614562696,
					-2.559842903640674
				],
				[
					-10.704797597042921,
					-2.0944169211605295
				],
				[
					-11.170223579522986,
					-1.8617039299204976
				],
				[
					-11.402936570763098,
					-1.6289909386804657
				],
				[
					-11.402936570763098,
					-1.1635649562003212
				],
				[
					-11.868362553243163,
					-0.6981389737201765
				],
				[
					-12.101075544483274,
					-0.2327129912401126
				],
				[
					-12.101075544483274,
					0.23271299124003197
				],
				[
					-12.333788535723226,
					0.6981389737201765
				],
				[
					-12.56650152696334,
					1.396277947440353
				],
				[
					-12.56650152696334,
					2.0944169211605295
				],
				[
					-12.56650152696334,
					2.792555894880706
				],
				[
					-12.56650152696334,
					3.2579818773609315
				],
				[
					-12.56650152696334,
					3.9561208510811077
				],
				[
					-12.56650152696334,
					4.886972816041316
				],
				[
					-12.56650152696334,
					5.3523987985214605
				],
				[
					-12.333788535723226,
					6.28325076348175
				],
				[
					-12.333788535723226,
					6.748676745961814
				],
				[
					-12.101075544483274,
					7.44681571968199
				],
				[
					-11.868362553243163,
					7.912241702162135
				],
				[
					-11.868362553243163,
					8.843093667122425
				],
				[
					-11.63564956200305,
					9.30851964960257
				],
				[
					-11.402936570763098,
					10.006658623322744
				],
				[
					-11.170223579522986,
					10.47208460580281
				],
				[
					-10.937510588282873,
					10.937510588282954
				],
				[
					-10.47208460580281,
					11.635649562003131
				],
				[
					-10.006658623322584,
					12.333788535723388
				],
				[
					-9.54123264084252,
					12.799214518203451
				],
				[
					-9.075806658362456,
					13.264640500683596
				],
				[
					-8.610380675882231,
					13.730066483163741
				],
				[
					-7.912241702162055,
					14.428205456883918
				],
				[
					-7.44681571968199,
					14.89363143936406
				],
				[
					-6.9813897372017655,
					15.359057421844206
				],
				[
					-6.515963754721701,
					15.82448340432427
				],
				[
					-6.050537772241637,
					16.057196395564382
				],
				[
					-5.3523987985214605,
					16.75533536928456
				],
				[
					-4.886972816041236,
					16.98804836052459
				],
				[
					-4.188833842321059,
					17.453474343004736
				],
				[
					-3.9561208510809465,
					17.91890032548488
				],
				[
					-3.25798187736077,
					18.384326307965026
				],
				[
					-2.792555894880706,
					18.617039299205057
				],
				[
					-2.5598429036405936,
					19.082465281685202
				],
				[
					-2.3271299124004807,
					19.547891264165266
				],
				[
					-1.861703929920417,
					20.01331724664541
				],
				[
					-1.396277947440353,
					20.478743229125556
				],
				[
					-1.1635649562002404,
					20.9441692116057
				],
				[
					-0.9308519649601279,
					21.87502117656591
				],
				[
					-0.9308519649601279,
					22.34044715904605
				],
				[
					-0.6981389737201765,
					23.038586132766227
				],
				[
					-0.46542598248006395,
					23.969438097726517
				],
				[
					-0.23271299123995134,
					24.667577071446694
				],
				[
					-0.23271299123995134,
					25.36571604516687
				],
				[
					0,
					25.831142027647015
				],
				[
					0,
					26.529281001367192
				],
				[
					0,
					27.22741997508737
				],
				[
					0,
					27.925558948807545
				],
				[
					0,
					28.39098493128769
				],
				[
					0,
					28.62369792252772
				],
				[
					-0.23271299123995134,
					29.32183689624798
				],
				[
					-0.23271299123995134,
					29.78726287872812
				],
				[
					-0.46542598248006395,
					30.485401852448298
				],
				[
					-0.6981389737201765,
					31.183540826168475
				],
				[
					-0.9308519649601279,
					31.64896680864854
				],
				[
					-0.9308519649601279,
					32.11439279112869
				],
				[
					-1.1635649562002404,
					32.3471057823688
				],
				[
					-1.1635649562002404,
					32.81253176484894
				],
				[
					-1.396277947440353,
					33.04524475608898
				],
				[
					-1.6289909386803043,
					33.277957747329005
				],
				[
					-1.861703929920417,
					33.74338372980915
				],
				[
					-2.3271299124004807,
					34.208809712289295
				],
				[
					-2.5598429036405936,
					34.67423569476936
				],
				[
					-3.25798187736077,
					35.13966167724951
				],
				[
					-3.723407859840995,
					35.60508765972965
				],
				[
					-3.9561208510809465,
					35.83780065096976
				],
				[
					-4.421546833561171,
					36.303226633449825
				],
				[
					-4.886972816041236,
					36.303226633449825
				],
				[
					-5.119685807281348,
					36.53593962468994
				],
				[
					-5.585111789761412,
					36.768652615929966
				],
				[
					-5.817824781001525,
					37.00136560717
				],
				[
					-6.050537772241637,
					37.00136560717
				],
				[
					-6.283250763481589,
					37.00136560717
				],
				[
					-6.9813897372017655,
					37.00136560717
				],
				[
					-7.214102728441878,
					37.00136560717
				],
				[
					-7.44681571968199,
					37.00136560717
				],
				[
					-7.679528710921942,
					37.00136560717
				],
				[
					-8.144954693402166,
					37.00136560717
				],
				[
					-8.610380675882231,
					37.00136560717
				],
				[
					-8.843093667122343,
					37.00136560717
				],
				[
					-9.308519649602408,
					37.00136560717
				],
				[
					-9.54123264084252,
					37.00136560717
				],
				[
					-10.006658623322584,
					37.00136560717
				],
				[
					-10.239371614562696,
					36.768652615929966
				],
				[
					-10.704797597042921,
					36.768652615929966
				],
				[
					-10.704797597042921,
					36.53593962468994
				],
				[
					-11.170223579522986,
					36.53593962468994
				],
				[
					-11.402936570763098,
					36.303226633449825
				],
				[
					-11.868362553243163,
					35.83780065096976
				],
				[
					-12.799214518203451,
					35.60508765972965
				],
				[
					-13.031927509443403,
					35.37237466848961
				],
				[
					-13.497353491923628,
					35.13966167724951
				],
				[
					-13.962779474403693,
					34.90694868600947
				],
				[
					-14.195492465643804,
					34.67423569476936
				],
				[
					-14.660918448123867,
					34.208809712289295
				],
				[
					-14.89363143936398,
					33.97609672104918
				],
				[
					-15.126344430604094,
					33.74338372980915
				],
				[
					-15.359057421844044,
					33.277957747329005
				],
				[
					-15.591770413084157,
					33.04524475608898
				],
				[
					-15.82448340432427,
					32.57981877360883
				],
				[
					-16.057196395564223,
					32.3471057823688
				],
				[
					-16.057196395564223,
					31.64896680864854
				],
				[
					-16.289909386804332,
					31.416253817408506
				],
				[
					-16.289909386804332,
					31.183540826168475
				],
				[
					-16.289909386804332,
					30.485401852448298
				],
				[
					-16.289909386804332,
					30.25268886120819
				],
				[
					-16.522622378044446,
					29.78726287872812
				],
				[
					-16.522622378044446,
					29.55454988748801
				],
				[
					-16.522622378044446,
					29.32183689624798
				],
				[
					-16.522622378044446,
					28.856410913767835
				],
				[
					-16.522622378044446,
					28.856410913767835
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 259,
			"versionNonce": 1279686309,
			"isDeleted": false,
			"id": "-CZd9fEwZtlWENNFguWtb",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1047.8935174807605,
			"y": 519.6305783713764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.817824781001686,
			"height": 0.9308519649602891,
			"seed": 188210155,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.2327129912401126,
					0
				],
				[
					0.46542598248006395,
					0
				],
				[
					1.1635649562002404,
					0
				],
				[
					1.8617039299205782,
					0.46542598248014455
				],
				[
					2.559842903640755,
					0.46542598248014455
				],
				[
					2.792555894880706,
					0.46542598248014455
				],
				[
					3.4906948686008827,
					0.6981389737202571
				],
				[
					3.9561208510811077,
					0.6981389737202571
				],
				[
					4.421546833561171,
					0.6981389737202571
				],
				[
					5.119685807281348,
					0.9308519649602891
				],
				[
					5.3523987985214605,
					0.9308519649602891
				],
				[
					5.585111789761574,
					0.9308519649602891
				],
				[
					4.886972816041236,
					0.9308519649602891
				],
				[
					4.886972816041236,
					0.9308519649602891
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 270,
			"versionNonce": 1518170667,
			"isDeleted": false,
			"id": "iQc6Ug3mPtMoIn07zZp3l",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1047.1953785070405,
			"y": 519.6305783713764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 9.54123264084252,
			"height": 0,
			"seed": 1267541483,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.23271299123995134,
					0
				],
				[
					0.6981389737201765,
					0
				],
				[
					1.6289909386804657,
					0
				],
				[
					2.0944169211605295,
					0
				],
				[
					3.0252688861208186,
					0
				],
				[
					3.2579818773609315,
					0
				],
				[
					3.723407859840995,
					0
				],
				[
					4.421546833561171,
					0
				],
				[
					5.119685807281348,
					0
				],
				[
					5.3523987985214605,
					0
				],
				[
					5.817824781001525,
					0
				],
				[
					6.28325076348175,
					0
				],
				[
					6.748676745961814,
					0
				],
				[
					6.981389737201926,
					0
				],
				[
					7.214102728441878,
					0
				],
				[
					7.44681571968199,
					0
				],
				[
					7.679528710922103,
					0
				],
				[
					7.912241702162055,
					0
				],
				[
					8.144954693402166,
					0
				],
				[
					8.610380675882393,
					0
				],
				[
					8.843093667122343,
					0
				],
				[
					9.075806658362456,
					0
				],
				[
					9.30851964960257,
					0
				],
				[
					9.54123264084252,
					0
				],
				[
					9.54123264084252,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 271,
			"versionNonce": 736778757,
			"isDeleted": false,
			"id": "KPTVEZSy1LyAGF-Ur8Sr5",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1047.4280914982803,
			"y": 526.6119681085783,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 10.937510588283034,
			"height": 0.23271299124003197,
			"seed": 1395366091,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4654259824802252,
					0
				],
				[
					1.1635649562004018,
					0
				],
				[
					1.6289909386804657,
					0
				],
				[
					2.3271299124008036,
					0
				],
				[
					2.7925558948808673,
					0
				],
				[
					3.490694868601044,
					0
				],
				[
					3.7234078598411564,
					0
				],
				[
					4.654259824801285,
					0
				],
				[
					5.3523987985214605,
					0
				],
				[
					6.050537772241799,
					-0.23271299124003197
				],
				[
					6.515963754721863,
					-0.23271299124003197
				],
				[
					7.214102728442039,
					-0.23271299124003197
				],
				[
					7.446815719682152,
					-0.23271299124003197
				],
				[
					7.679528710922103,
					-0.23271299124003197
				],
				[
					8.144954693402328,
					-0.23271299124003197
				],
				[
					8.377667684642441,
					-0.23271299124003197
				],
				[
					9.075806658362618,
					-0.23271299124003197
				],
				[
					9.30851964960257,
					-0.23271299124003197
				],
				[
					9.541232640842681,
					-0.23271299124003197
				],
				[
					9.773945632082794,
					-0.23271299124003197
				],
				[
					10.006658623322744,
					-0.23271299124003197
				],
				[
					10.239371614562858,
					-0.23271299124003197
				],
				[
					10.472084605802971,
					-0.23271299124003197
				],
				[
					10.704797597042921,
					-0.23271299124003197
				],
				[
					10.937510588283034,
					-0.23271299124003197
				],
				[
					10.937510588283034,
					-0.23271299124003197
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 357,
			"versionNonce": 570684619,
			"isDeleted": false,
			"id": "J0Q50eluKw0_v85_kCAa-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1072.7938075434472,
			"y": 474.9496840532843,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 15.82448340432427,
			"height": 85.63838077634321,
			"seed": 704441067,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.46542598248014455
				],
				[
					-0.2327129912401126,
					1.3962779474403935
				],
				[
					-0.46542598248006395,
					2.3271299124006424
				],
				[
					-0.6981389737201765,
					3.0252688861208186
				],
				[
					-0.6981389737201765,
					4.421546833561212
				],
				[
					-0.9308519649602891,
					5.585111789761533
				],
				[
					-1.396277947440353,
					6.515963754721782
				],
				[
					-1.6289909386804657,
					7.214102728441959
				],
				[
					-1.6289909386804657,
					7.912241702162135
				],
				[
					-1.8617039299205782,
					9.075806658362456
				],
				[
					-2.0944169211605295,
					10.006658623322744
				],
				[
					-2.3271299124006424,
					11.170223579523066
				],
				[
					-2.559842903640755,
					12.101075544483274
				],
				[
					-2.792555894880706,
					13.264640500683596
				],
				[
					-3.0252688861208186,
					13.962779474403773
				],
				[
					-3.2579818773609315,
					15.126344430604094
				],
				[
					-3.4906948686008827,
					16.289909386804414
				],
				[
					-3.723407859840995,
					17.686187334244767
				],
				[
					-3.723407859840995,
					18.84975229044517
				],
				[
					-3.9561208510811077,
					20.01331724664541
				],
				[
					-4.188833842321059,
					21.176882202845732
				],
				[
					-4.188833842321059,
					22.805873141526195
				],
				[
					-4.188833842321059,
					23.736725106486404
				],
				[
					-4.188833842321059,
					25.13300305392684
				],
				[
					-4.188833842321059,
					26.529281001367192
				],
				[
					-4.188833842321059,
					27.692845957567513
				],
				[
					-4.188833842321059,
					28.623697922527803
				],
				[
					-4.188833842321059,
					29.787262878728043
				],
				[
					-4.188833842321059,
					30.950827834928443
				],
				[
					-4.188833842321059,
					31.88167979988865
				],
				[
					-4.188833842321059,
					32.81253176484886
				],
				[
					-4.188833842321059,
					33.74338372980915
				],
				[
					-4.188833842321059,
					34.674235694769436
				],
				[
					-4.188833842321059,
					35.83780065096976
				],
				[
					-4.188833842321059,
					36.3032266334499
				],
				[
					-4.188833842321059,
					37.46679158965014
				],
				[
					-4.188833842321059,
					38.63035654585047
				],
				[
					-4.188833842321059,
					39.32849551957072
				],
				[
					-4.188833842321059,
					40.0266344932909
				],
				[
					-4.188833842321059,
					40.724773467011076
				],
				[
					-4.188833842321059,
					41.65562543197129
				],
				[
					-4.188833842321059,
					42.35376440569154
				],
				[
					-4.188833842321059,
					43.05190337941172
				],
				[
					-3.9561208510811077,
					43.982755344371924
				],
				[
					-3.723407859840995,
					45.14632030057225
				],
				[
					-3.4906948686008827,
					46.07717226553254
				],
				[
					-3.2579818773609315,
					47.24073722173278
				],
				[
					-3.0252688861208186,
					48.17158918669307
				],
				[
					-2.792555894880706,
					49.33515414289339
				],
				[
					-2.559842903640755,
					50.964145081573854
				],
				[
					-2.559842903640755,
					51.894997046534066
				],
				[
					-2.3271299124006424,
					53.058562002734384
				],
				[
					-2.3271299124006424,
					53.75670097645456
				],
				[
					-2.0944169211605295,
					54.454839950174815
				],
				[
					-1.8617039299205782,
					55.38569191513503
				],
				[
					-1.8617039299205782,
					56.0838308888552
				],
				[
					-1.6289909386804657,
					56.78196986257546
				],
				[
					-1.6289909386804657,
					57.480108836295635
				],
				[
					-1.396277947440353,
					58.17824781001581
				],
				[
					-1.1635649562002404,
					58.643673792495875
				],
				[
					-1.1635649562002404,
					59.34181276621614
				],
				[
					-0.9308519649602891,
					59.80723874869628
				],
				[
					-0.6981389737201765,
					60.505377722416455
				],
				[
					-0.46542598248006395,
					61.20351669613663
				],
				[
					0,
					61.90165566985681
				],
				[
					0.2327129912401126,
					62.36708165233695
				],
				[
					0.6981389737201765,
					63.29793361729716
				],
				[
					0.9308519649602891,
					64.22878558225744
				],
				[
					1.1635649562004018,
					64.92692455597762
				],
				[
					1.6289909386804657,
					65.6250635296978
				],
				[
					1.8617039299205782,
					66.32320250341797
				],
				[
					2.0944169211605295,
					67.02134147713815
				],
				[
					2.3271299124006424,
					67.4867674596183
				],
				[
					2.559842903640755,
					67.95219344209845
				],
				[
					2.792555894880706,
					68.41761942457859
				],
				[
					3.0252688861208186,
					68.88304540705873
				],
				[
					3.4906948686008827,
					69.81389737201894
				],
				[
					3.723407859840995,
					70.27932335449908
				],
				[
					4.188833842321221,
					71.2101753194593
				],
				[
					4.421546833561171,
					71.67560130193944
				],
				[
					4.654259824801285,
					72.37374027565961
				],
				[
					4.886972816041397,
					73.07187924937979
				],
				[
					5.3523987985214605,
					73.77001822309997
				],
				[
					5.585111789761574,
					74.23544420558011
				],
				[
					5.817824781001525,
					74.70087018806026
				],
				[
					5.817824781001525,
					75.1662961705404
				],
				[
					6.050537772241637,
					75.63172215302055
				],
				[
					6.515963754721863,
					76.09714813550062
				],
				[
					6.748676745961814,
					76.56257411798076
				],
				[
					6.981389737201926,
					77.0280001004609
				],
				[
					7.214102728442039,
					77.49342608294104
				],
				[
					7.44681571968199,
					77.95885206542118
				],
				[
					7.679528710922103,
					78.65699103914136
				],
				[
					7.912241702162215,
					79.12241702162143
				],
				[
					8.144954693402166,
					79.58784300410157
				],
				[
					8.37766768464228,
					79.8205559953416
				],
				[
					8.843093667122343,
					80.51869496906187
				],
				[
					9.075806658362456,
					80.75140796030189
				],
				[
					9.075806658362456,
					81.21683394278205
				],
				[
					9.30851964960257,
					81.68225992526219
				],
				[
					9.54123264084252,
					82.14768590774224
				],
				[
					10.006658623322744,
					82.6131118902224
				],
				[
					10.239371614562858,
					83.07853787270254
				],
				[
					10.239371614562858,
					83.54396385518268
				],
				[
					10.47208460580281,
					84.00938983766282
				],
				[
					10.704797597042921,
					84.24210282890286
				],
				[
					10.937510588283034,
					84.707528811383
				],
				[
					11.170223579522986,
					84.707528811383
				],
				[
					11.170223579522986,
					84.94024180262304
				],
				[
					11.402936570763098,
					85.17295479386307
				],
				[
					11.635649562003211,
					85.63838077634321
				],
				[
					11.635649562003211,
					85.63838077634321
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 310,
			"versionNonce": 1744490853,
			"isDeleted": false,
			"id": "KZeq9eM-4B1ATQGWuEpK7",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1086.058448044131,
			"y": 479.83665686932557,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.214102728441878,
			"height": 16.289909386804414,
			"seed": 316600875,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.23271299124003197
				],
				[
					0,
					-0.46542598248010425
				],
				[
					-0.2327129912401126,
					-0.46542598248010425
				],
				[
					-0.4654259824802252,
					-0.6981389737201765
				],
				[
					-0.6981389737201765,
					-0.9308519649602085
				],
				[
					-1.1635649562004018,
					-1.1635649562002808
				],
				[
					-1.6289909386804657,
					-1.396277947440353
				],
				[
					-1.8617039299205782,
					-1.396277947440353
				],
				[
					-2.0944169211606907,
					-1.396277947440353
				],
				[
					-2.559842903640755,
					-1.396277947440353
				],
				[
					-2.7925558948808673,
					-1.396277947440353
				],
				[
					-3.2579818773609315,
					-1.1635649562002808
				],
				[
					-3.490694868601044,
					-0.9308519649602085
				],
				[
					-3.7234078598411564,
					-0.6981389737201765
				],
				[
					-3.9561208510811077,
					-0.46542598248010425
				],
				[
					-4.188833842321221,
					-0.23271299124003197
				],
				[
					-4.421546833561333,
					0.46542598248014455
				],
				[
					-4.654259824801285,
					0.6981389737202168
				],
				[
					-4.654259824801285,
					1.3962779474403935
				],
				[
					-4.654259824801285,
					1.6289909386804657
				],
				[
					-4.654259824801285,
					2.3271299124006424
				],
				[
					-4.654259824801285,
					2.792555894880787
				],
				[
					-4.654259824801285,
					3.2579818773609315
				],
				[
					-4.654259824801285,
					3.490694868600963
				],
				[
					-4.654259824801285,
					3.9561208510811077
				],
				[
					-4.421546833561333,
					4.654259824801285
				],
				[
					-4.188833842321221,
					4.886972816041356
				],
				[
					-3.9561208510811077,
					5.585111789761533
				],
				[
					-3.7234078598411564,
					6.050537772241637
				],
				[
					-3.2579818773609315,
					6.748676745961855
				],
				[
					-3.0252688861208186,
					7.214102728441959
				],
				[
					-2.559842903640755,
					7.679528710922103
				],
				[
					-2.0944169211606907,
					8.144954693402248
				],
				[
					-1.6289909386804657,
					8.37766768464228
				],
				[
					-1.1635649562004018,
					8.843093667122425
				],
				[
					-0.6981389737201765,
					9.075806658362456
				],
				[
					-0.4654259824802252,
					9.30851964960257
				],
				[
					-0.2327129912401126,
					9.773945632082674
				],
				[
					0.23271299123995134,
					10.239371614562778
				],
				[
					0.6981389737201765,
					10.937510588282993
				],
				[
					0.9308519649601279,
					12.101075544483274
				],
				[
					0.9308519649601279,
					12.333788535723388
				],
				[
					0.9308519649601279,
					12.799214518203451
				],
				[
					0.9308519649601279,
					13.264640500683596
				],
				[
					0.9308519649601279,
					13.49735349192371
				],
				[
					0.6981389737201765,
					13.49735349192371
				],
				[
					0.46542598248006395,
					13.962779474403852
				],
				[
					0,
					13.962779474403852
				],
				[
					-0.4654259824802252,
					14.195492465643884
				],
				[
					-0.9308519649602891,
					14.195492465643884
				],
				[
					-1.6289909386804657,
					14.66091844812403
				],
				[
					-2.3271299124006424,
					14.89363143936406
				],
				[
					-2.7925558948808673,
					14.89363143936406
				],
				[
					-3.0252688861208186,
					14.89363143936406
				],
				[
					-3.2579818773609315,
					14.89363143936406
				],
				[
					-3.490694868601044,
					14.89363143936406
				],
				[
					-3.9561208510811077,
					14.89363143936406
				],
				[
					-4.421546833561333,
					14.89363143936406
				],
				[
					-4.654259824801285,
					14.66091844812403
				],
				[
					-4.886972816041397,
					14.66091844812403
				],
				[
					-5.3523987985214605,
					14.428205456883918
				],
				[
					-5.585111789761574,
					14.195492465643884
				],
				[
					-5.817824781001686,
					13.962779474403852
				],
				[
					-6.050537772241637,
					13.730066483163741
				],
				[
					-6.28325076348175,
					13.49735349192371
				],
				[
					-6.28325076348175,
					13.49735349192371
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 261,
			"versionNonce": 1189159787,
			"isDeleted": false,
			"id": "jhVhoN-ZCED_Rn0M2aVzZ",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1091.1781338514122,
			"y": 491.2395934400887,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 0,
			"height": 7.214102728441918,
			"seed": 928132267,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.23271299124003197
				],
				[
					0,
					-0.46542598248010425
				],
				[
					0,
					0
				],
				[
					0,
					0.6981389737201765
				],
				[
					0,
					1.1635649562003212
				],
				[
					0,
					1.6289909386804657
				],
				[
					0,
					2.3271299124006424
				],
				[
					0,
					3.0252688861208186
				],
				[
					0,
					3.9561208510811077
				],
				[
					0,
					4.421546833561171
				],
				[
					0,
					4.886972816041316
				],
				[
					0,
					5.585111789761574
				],
				[
					0,
					5.8178247810016055
				],
				[
					0,
					6.050537772241637
				],
				[
					0,
					6.515963754721782
				],
				[
					0,
					6.748676745961814
				],
				[
					0,
					6.748676745961814
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 310,
			"versionNonce": 1841650885,
			"isDeleted": false,
			"id": "wGMvl0Qf9-uFp6AP5spBF",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1083.26589214925,
			"y": 509.6239197480537,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 10.239371614562858,
			"height": 10.47208460580281,
			"seed": 628597931,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.2327129912401126,
					0
				],
				[
					0.4654259824802252,
					0
				],
				[
					0.9308519649602891,
					0
				],
				[
					1.6289909386804657,
					0.6981389737201765
				],
				[
					2.0944169211606907,
					0.9308519649602085
				],
				[
					2.7925558948808673,
					1.6289909386804657
				],
				[
					3.2579818773609315,
					2.0944169211605295
				],
				[
					3.723407859840995,
					2.559842903640674
				],
				[
					3.9561208510811077,
					3.2579818773608507
				],
				[
					4.421546833561171,
					3.9561208510810273
				],
				[
					4.654259824801285,
					4.654259824801285
				],
				[
					4.886972816041397,
					5.3523987985214605
				],
				[
					4.886972816041397,
					5.817824781001525
				],
				[
					4.886972816041397,
					6.515963754721701
				],
				[
					4.886972816041397,
					6.748676745961814
				],
				[
					4.886972816041397,
					7.214102728441959
				],
				[
					4.654259824801285,
					7.679528710922103
				],
				[
					4.188833842321221,
					8.144954693402166
				],
				[
					3.9561208510811077,
					8.610380675882311
				],
				[
					3.490694868601044,
					9.075806658362456
				],
				[
					3.2579818773609315,
					9.308519649602488
				],
				[
					2.7925558948808673,
					9.773945632082633
				],
				[
					2.559842903640755,
					10.006658623322664
				],
				[
					2.3271299124006424,
					10.239371614562778
				],
				[
					2.0944169211606907,
					10.47208460580281
				],
				[
					1.8617039299205782,
					10.47208460580281
				],
				[
					1.3962779474405143,
					10.47208460580281
				],
				[
					0.9308519649602891,
					10.47208460580281
				],
				[
					0.2327129912401126,
					10.006658623322664
				],
				[
					-0.46542598248006395,
					9.773945632082633
				],
				[
					-1.1635649562002404,
					9.54123264084252
				],
				[
					-1.861703929920417,
					9.54123264084252
				],
				[
					-2.5598429036405936,
					9.075806658362456
				],
				[
					-3.0252688861208186,
					8.843093667122343
				],
				[
					-3.4906948686008827,
					8.37766768464228
				],
				[
					-3.9561208510809465,
					8.144954693402166
				],
				[
					-4.421546833561171,
					7.679528710922103
				],
				[
					-4.654259824801285,
					7.214102728441959
				],
				[
					-4.886972816041236,
					6.748676745961814
				],
				[
					-5.119685807281348,
					6.050537772241637
				],
				[
					-5.3523987985214605,
					5.585111789761493
				],
				[
					-5.3523987985214605,
					5.119685807281348
				],
				[
					-5.3523987985214605,
					4.654259824801285
				],
				[
					-5.3523987985214605,
					4.18883384232114
				],
				[
					-5.119685807281348,
					3.723407859840995
				],
				[
					-4.886972816041236,
					3.2579818773608507
				],
				[
					-4.654259824801285,
					2.792555894880706
				],
				[
					-4.421546833561171,
					2.559842903640674
				],
				[
					-3.9561208510809465,
					2.0944169211605295
				],
				[
					-3.4906948686008827,
					1.8617039299204976
				],
				[
					-3.25798187736077,
					1.6289909386804657
				],
				[
					-2.792555894880706,
					1.1635649562003212
				],
				[
					-2.5598429036405936,
					0.9308519649602085
				],
				[
					-2.3271299124006424,
					0.9308519649602085
				],
				[
					-1.861703929920417,
					0.6981389737201765
				],
				[
					-1.6289909386804657,
					0.6981389737201765
				],
				[
					-1.1635649562002404,
					0.46542598248006395
				],
				[
					-0.9308519649602891,
					0.46542598248006395
				],
				[
					-0.46542598248006395,
					0.46542598248006395
				],
				[
					-0.23271299123995134,
					0.46542598248006395
				],
				[
					0,
					0.46542598248006395
				],
				[
					0.2327129912401126,
					0.46542598248006395
				],
				[
					0.4654259824802252,
					0.46542598248006395
				],
				[
					0.6981389737201765,
					0.46542598248006395
				],
				[
					0.9308519649602891,
					0.6981389737201765
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
			"type": "freedraw",
			"version": 314,
			"versionNonce": 1096777227,
			"isDeleted": false,
			"id": "29dBCEjja1pYoEuF5wutv",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1085.5930220616508,
			"y": 537.3167657056213,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 10.239371614562858,
			"height": 12.101075544483274,
			"seed": 912425419,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.2327129912401126
				],
				[
					0.2327129912401126,
					-0.2327129912401126
				],
				[
					0.6981389737201765,
					-0.2327129912401126
				],
				[
					1.6289909386804657,
					-0.2327129912401126
				],
				[
					2.559842903640755,
					-0.2327129912401126
				],
				[
					3.2579818773609315,
					0
				],
				[
					3.490694868601044,
					0.23271299124003197
				],
				[
					3.9561208510811077,
					0.46542598248014455
				],
				[
					4.654259824801285,
					0.9308519649602085
				],
				[
					4.886972816041397,
					1.396277947440353
				],
				[
					5.585111789761574,
					2.0944169211605295
				],
				[
					5.817824781001686,
					2.792555894880706
				],
				[
					6.050537772241637,
					3.490694868600963
				],
				[
					6.28325076348175,
					3.9561208510810273
				],
				[
					6.28325076348175,
					4.654259824801204
				],
				[
					6.515963754721863,
					5.585111789761493
				],
				[
					6.515963754721863,
					6.050537772241637
				],
				[
					6.515963754721863,
					6.748676745961814
				],
				[
					6.515963754721863,
					7.214102728441959
				],
				[
					6.515963754721863,
					7.679528710922022
				],
				[
					6.28325076348175,
					8.3776676846422
				],
				[
					6.050537772241637,
					8.610380675882311
				],
				[
					5.817824781001686,
					9.308519649602488
				],
				[
					5.3523987985214605,
					9.541232640842601
				],
				[
					5.11968580728151,
					10.006658623322664
				],
				[
					4.886972816041397,
					10.239371614562778
				],
				[
					4.421546833561171,
					10.937510588282954
				],
				[
					3.9561208510811077,
					11.170223579522986
				],
				[
					3.723407859840995,
					11.170223579522986
				],
				[
					3.2579818773609315,
					11.402936570763018
				],
				[
					2.792555894880706,
					11.402936570763018
				],
				[
					2.559842903640755,
					11.402936570763018
				],
				[
					2.0944169211605295,
					11.402936570763018
				],
				[
					1.6289909386804657,
					11.402936570763018
				],
				[
					1.1635649562004018,
					11.170223579522986
				],
				[
					0.6981389737201765,
					10.937510588282954
				],
				[
					0.2327129912401126,
					10.704797597042841
				],
				[
					-0.6981389737201765,
					10.47208460580281
				],
				[
					-1.1635649562002404,
					10.239371614562778
				],
				[
					-2.0944169211605295,
					9.773945632082633
				],
				[
					-2.5598429036405936,
					9.308519649602488
				],
				[
					-2.792555894880706,
					8.843093667122343
				],
				[
					-3.2579818773609315,
					8.144954693402166
				],
				[
					-3.4906948686008827,
					7.214102728441959
				],
				[
					-3.723407859840995,
					6.748676745961814
				],
				[
					-3.723407859840995,
					5.817824781001525
				],
				[
					-3.723407859840995,
					5.119685807281348
				],
				[
					-3.723407859840995,
					4.654259824801204
				],
				[
					-3.723407859840995,
					3.9561208510810273
				],
				[
					-3.4906948686008827,
					3.2579818773608507
				],
				[
					-3.4906948686008827,
					2.559842903640674
				],
				[
					-3.2579818773609315,
					2.0944169211605295
				],
				[
					-3.2579818773609315,
					1.628990938680385
				],
				[
					-3.0252688861208186,
					1.1635649562003212
				],
				[
					-2.792555894880706,
					0.46542598248014455
				],
				[
					-2.5598429036405936,
					0
				],
				[
					-2.3271299124006424,
					-0.46542598248014455
				],
				[
					-2.0944169211605295,
					-0.6981389737202571
				],
				[
					-1.861703929920417,
					-0.6981389737202571
				],
				[
					-1.6289909386804657,
					-0.6981389737202571
				],
				[
					-1.396277947440353,
					-0.6981389737202571
				],
				[
					-1.1635649562002404,
					-0.6981389737202571
				],
				[
					-0.6981389737201765,
					-0.6981389737202571
				],
				[
					-0.46542598248006395,
					-0.6981389737202571
				],
				[
					0,
					-0.46542598248014455
				],
				[
					0.2327129912401126,
					-0.46542598248014455
				],
				[
					0.4654259824802252,
					-0.2327129912401126
				],
				[
					0.6981389737201765,
					-0.2327129912401126
				],
				[
					0.9308519649602891,
					0
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
			"type": "freedraw",
			"version": 314,
			"versionNonce": 619150373,
			"isDeleted": false,
			"id": "GHaVCRDorJj6cv9U-7IyB",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1103.5119223871357,
			"y": 491.2395934400887,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 10.704797597042761,
			"height": 10.239371614562778,
			"seed": 614456683,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.23271299124003197
				],
				[
					-0.2327129912401126,
					-0.9308519649602085
				],
				[
					-0.2327129912401126,
					-1.1635649562003212
				],
				[
					-0.4654259824802252,
					-2.0944169211605295
				],
				[
					-0.4654259824802252,
					-2.7925558948807465
				],
				[
					-0.6981389737201765,
					-3.490694868600923
				],
				[
					-0.4654259824802252,
					-3.723407859840995
				],
				[
					-0.4654259824802252,
					-3.9561208510810273
				],
				[
					-0.2327129912401126,
					-4.18883384232114
				],
				[
					0.23271299123995134,
					-4.18883384232114
				],
				[
					0.6981389737201765,
					-4.18883384232114
				],
				[
					1.396277947440353,
					-4.421546833561171
				],
				[
					1.861703929920417,
					-4.421546833561171
				],
				[
					2.5598429036405936,
					-4.421546833561171
				],
				[
					3.0252688861208186,
					-4.421546833561171
				],
				[
					3.4906948686008827,
					-4.421546833561171
				],
				[
					4.188833842321059,
					-4.421546833561171
				],
				[
					4.886972816041236,
					-4.18883384232114
				],
				[
					5.817824781001525,
					-3.9561208510810273
				],
				[
					6.748676745961814,
					-3.723407859840995
				],
				[
					7.214102728441878,
					-3.490694868600923
				],
				[
					7.679528710921942,
					-3.0252688861208186
				],
				[
					8.377667684642118,
					-2.559842903640674
				],
				[
					8.843093667122343,
					-2.3271299124006424
				],
				[
					9.075806658362456,
					-1.8617039299204976
				],
				[
					9.308519649602408,
					-1.396277947440353
				],
				[
					9.773945632082633,
					-0.46542598248010425
				],
				[
					10.006658623322584,
					0.23271299124007228
				],
				[
					10.006658623322584,
					0.9308519649602891
				],
				[
					10.006658623322584,
					1.6289909386804657
				],
				[
					10.006658623322584,
					2.792555894880787
				],
				[
					9.773945632082633,
					3.2579818773609315
				],
				[
					9.773945632082633,
					3.9561208510811077
				],
				[
					9.54123264084252,
					4.654259824801285
				],
				[
					9.075806658362456,
					5.3523987985214605
				],
				[
					8.610380675882231,
					5.3523987985214605
				],
				[
					8.377667684642118,
					5.585111789761574
				],
				[
					7.679528710921942,
					5.8178247810016055
				],
				[
					7.214102728441878,
					5.8178247810016055
				],
				[
					6.748676745961814,
					5.8178247810016055
				],
				[
					6.050537772241637,
					5.8178247810016055
				],
				[
					5.119685807281348,
					5.8178247810016055
				],
				[
					4.654259824801285,
					5.8178247810016055
				],
				[
					4.421546833561171,
					5.8178247810016055
				],
				[
					3.9561208510809465,
					5.585111789761574
				],
				[
					3.25798187736077,
					5.119685807281429
				],
				[
					3.0252688861208186,
					4.886972816041316
				],
				[
					2.5598429036405936,
					4.654259824801285
				],
				[
					2.0944169211605295,
					4.18883384232114
				],
				[
					1.861703929920417,
					3.9561208510811077
				],
				[
					1.396277947440353,
					3.2579818773609315
				],
				[
					1.1635649562002404,
					2.792555894880787
				],
				[
					0.6981389737201765,
					2.3271299124006424
				],
				[
					0.6981389737201765,
					2.0944169211606103
				],
				[
					0.23271299123995134,
					1.396277947440353
				],
				[
					0.23271299123995134,
					0.9308519649602891
				],
				[
					0,
					0.46542598248014455
				],
				[
					0,
					0
				],
				[
					0,
					-0.6981389737201765
				],
				[
					0,
					-0.9308519649602085
				],
				[
					0,
					-1.6289909386804253
				],
				[
					0,
					-1.8617039299204976
				],
				[
					0,
					-2.3271299124006424
				],
				[
					0.46542598248006395,
					-2.7925558948807465
				],
				[
					0.46542598248006395,
					-3.2579818773608507
				],
				[
					0.6981389737201765,
					-3.490694868600923
				],
				[
					0.9308519649601279,
					-3.723407859840995
				],
				[
					1.396277947440353,
					-3.9561208510810273
				],
				[
					1.6289909386803043,
					-4.18883384232114
				],
				[
					1.861703929920417,
					-4.18883384232114
				],
				[
					1.861703929920417,
					-4.18883384232114
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 311,
			"versionNonce": 477725867,
			"isDeleted": false,
			"id": "UzwZr2pyDYg0LXi3UfaZQ",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1112.1223030630179,
			"y": 507.5295028268931,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.748676745961975,
			"height": 15.126344430604094,
			"seed": 143271179,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.2327129912401126,
					0
				],
				[
					-0.9308519649602891,
					-0.23271299124003197
				],
				[
					-1.6289909386804657,
					-0.46542598248014455
				],
				[
					-2.5598429036405936,
					-0.6981389737201765
				],
				[
					-3.25798187736077,
					-0.6981389737201765
				],
				[
					-3.723407859840995,
					-0.6981389737201765
				],
				[
					-3.9561208510809465,
					-0.6981389737201765
				],
				[
					-4.188833842321059,
					-0.6981389737201765
				],
				[
					-4.654259824801285,
					-0.46542598248014455
				],
				[
					-5.119685807281348,
					0
				],
				[
					-5.3523987985214605,
					0.23271299124003197
				],
				[
					-5.585111789761412,
					0.6981389737202571
				],
				[
					-5.817824781001525,
					1.1635649562003212
				],
				[
					-6.050537772241637,
					1.6289909386804657
				],
				[
					-6.050537772241637,
					2.0944169211606103
				],
				[
					-6.050537772241637,
					2.559842903640674
				],
				[
					-6.050537772241637,
					3.0252688861208186
				],
				[
					-6.050537772241637,
					3.2579818773609315
				],
				[
					-6.050537772241637,
					3.723407859841076
				],
				[
					-5.817824781001525,
					4.18883384232114
				],
				[
					-5.585111789761412,
					4.654259824801285
				],
				[
					-5.3523987985214605,
					5.119685807281429
				],
				[
					-5.119685807281348,
					5.585111789761493
				],
				[
					-4.654259824801285,
					6.28325076348175
				],
				[
					-3.9561208510809465,
					6.981389737201926
				],
				[
					-3.723407859840995,
					7.446815719682071
				],
				[
					-3.0252688861208186,
					7.912241702162135
				],
				[
					-2.5598429036405936,
					8.144954693402248
				],
				[
					-1.861703929920417,
					8.37766768464228
				],
				[
					-1.396277947440353,
					8.610380675882311
				],
				[
					-1.1635649562002404,
					8.843093667122425
				],
				[
					-0.9308519649602891,
					9.075806658362456
				],
				[
					-0.2327129912401126,
					9.30851964960257
				],
				[
					0,
					9.541232640842601
				],
				[
					0.2327129912401126,
					9.773945632082713
				],
				[
					0.4654259824802252,
					9.773945632082713
				],
				[
					0.4654259824802252,
					10.47208460580289
				],
				[
					0.4654259824802252,
					10.704797597042921
				],
				[
					0.4654259824802252,
					11.170223579523066
				],
				[
					0.4654259824802252,
					11.635649562003131
				],
				[
					0.2327129912401126,
					11.868362553243243
				],
				[
					0,
					12.101075544483274
				],
				[
					-0.2327129912401126,
					12.101075544483274
				],
				[
					-0.46542598248006395,
					12.56650152696342
				],
				[
					-0.6981389737201765,
					12.799214518203533
				],
				[
					-0.9308519649602891,
					13.031927509443564
				],
				[
					-1.396277947440353,
					13.031927509443564
				],
				[
					-1.6289909386804657,
					13.031927509443564
				],
				[
					-1.861703929920417,
					13.264640500683596
				],
				[
					-2.0944169211605295,
					13.49735349192371
				],
				[
					-2.3271299124006424,
					13.730066483163741
				],
				[
					-2.792555894880706,
					13.730066483163741
				],
				[
					-3.0252688861208186,
					13.730066483163741
				],
				[
					-3.25798187736077,
					13.730066483163741
				],
				[
					-3.4906948686008827,
					13.730066483163741
				],
				[
					-3.723407859840995,
					13.730066483163741
				],
				[
					-3.9561208510809465,
					13.962779474403773
				],
				[
					-4.188833842321059,
					13.962779474403773
				],
				[
					-4.421546833561171,
					13.962779474403773
				],
				[
					-4.654259824801285,
					13.962779474403773
				],
				[
					-4.886972816041236,
					14.195492465643884
				],
				[
					-5.119685807281348,
					14.428205456883918
				],
				[
					-5.3523987985214605,
					14.428205456883918
				],
				[
					-5.585111789761412,
					14.428205456883918
				],
				[
					-5.817824781001525,
					14.428205456883918
				],
				[
					-6.050537772241637,
					14.428205456883918
				],
				[
					-6.28325076348175,
					14.428205456883918
				],
				[
					-6.28325076348175,
					14.428205456883918
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 293,
			"versionNonce": 625913733,
			"isDeleted": false,
			"id": "QpSzrr0jL9X-ae3rfooi4",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1115.8457109228589,
			"y": 516.8380224764957,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.515963754721863,
			"height": 7.214102728441959,
			"seed": 1665255627,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.2327129912401126
				],
				[
					0.2327129912401126,
					-0.2327129912401126
				],
				[
					0.4654259824802252,
					-0.2327129912401126
				],
				[
					0.6981389737201765,
					-0.2327129912401126
				],
				[
					1.1635649562004018,
					-0.2327129912401126
				],
				[
					1.6289909386804657,
					0
				],
				[
					1.8617039299205782,
					0.46542598248014455
				],
				[
					1.8617039299205782,
					0.6981389737201765
				],
				[
					2.0944169211605295,
					1.396277947440353
				],
				[
					2.0944169211605295,
					2.3271299124005616
				],
				[
					2.0944169211605295,
					2.559842903640674
				],
				[
					1.8617039299205782,
					3.490694868600963
				],
				[
					1.6289909386804657,
					3.723407859840995
				],
				[
					1.1635649562004018,
					3.9561208510810273
				],
				[
					0.4654259824802252,
					3.9561208510810273
				],
				[
					0,
					4.18883384232114
				],
				[
					-0.23271299123995134,
					4.421546833561171
				],
				[
					-0.46542598248006395,
					4.654259824801204
				],
				[
					-0.9308519649601279,
					4.654259824801204
				],
				[
					-1.396277947440353,
					4.654259824801204
				],
				[
					-1.6289909386803043,
					4.654259824801204
				],
				[
					-1.861703929920417,
					4.654259824801204
				],
				[
					-2.0944169211605295,
					4.654259824801204
				],
				[
					-2.0944169211605295,
					4.421546833561171
				],
				[
					-2.0944169211605295,
					4.18883384232114
				],
				[
					-1.861703929920417,
					3.9561208510810273
				],
				[
					-1.6289909386803043,
					3.9561208510810273
				],
				[
					-1.396277947440353,
					3.9561208510810273
				],
				[
					-1.1635649562002404,
					3.9561208510810273
				],
				[
					-0.9308519649601279,
					3.9561208510810273
				],
				[
					-0.6981389737201765,
					3.9561208510810273
				],
				[
					-0.23271299123995134,
					3.9561208510810273
				],
				[
					0,
					3.9561208510810273
				],
				[
					0.2327129912401126,
					3.9561208510810273
				],
				[
					0.4654259824802252,
					4.18883384232114
				],
				[
					0.6981389737201765,
					4.421546833561171
				],
				[
					0.9308519649602891,
					4.421546833561171
				],
				[
					1.396277947440353,
					4.886972816041316
				],
				[
					1.6289909386804657,
					5.119685807281348
				],
				[
					1.8617039299205782,
					5.352398798521381
				],
				[
					2.0944169211605295,
					5.352398798521381
				],
				[
					2.3271299124006424,
					5.585111789761493
				],
				[
					2.559842903640755,
					5.817824781001525
				],
				[
					3.0252688861208186,
					6.050537772241637
				],
				[
					3.2579818773609315,
					6.28325076348167
				],
				[
					3.723407859840995,
					6.981389737201846
				],
				[
					3.9561208510811077,
					6.981389737201846
				],
				[
					4.188833842321221,
					6.981389737201846
				],
				[
					4.421546833561333,
					6.981389737201846
				],
				[
					4.421546833561333,
					6.981389737201846
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 301,
			"versionNonce": 534361931,
			"isDeleted": false,
			"id": "N18PURoX2_R5Vcmcec8Zb",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1111.1914510980575,
			"y": 538.4803306618215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 10.239371614562858,
			"height": 8.843093667122425,
			"seed": 1705060683,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6981389737201765,
					-0.2327129912401126
				],
				[
					1.6289909386804657,
					-0.46542598248014455
				],
				[
					2.559842903640755,
					-0.46542598248014455
				],
				[
					3.490694868601044,
					-0.46542598248014455
				],
				[
					4.188833842321221,
					-0.46542598248014455
				],
				[
					4.886972816041397,
					-0.2327129912401126
				],
				[
					5.585111789761574,
					0.23271299124003197
				],
				[
					6.28325076348175,
					0.9308519649602085
				],
				[
					7.214102728442039,
					1.628990938680385
				],
				[
					7.679528710922103,
					2.3271299124006424
				],
				[
					8.144954693402328,
					3.4906948686008827
				],
				[
					8.37766768464228,
					3.723407859840995
				],
				[
					8.843093667122504,
					4.886972816041316
				],
				[
					9.075806658362618,
					5.3523987985214605
				],
				[
					9.075806658362618,
					6.28325076348167
				],
				[
					9.075806658362618,
					6.981389737201846
				],
				[
					8.610380675882393,
					7.912241702162135
				],
				[
					8.144954693402328,
					7.912241702162135
				],
				[
					7.679528710922103,
					8.144954693402166
				],
				[
					6.748676745961814,
					8.37766768464228
				],
				[
					6.050537772241637,
					8.37766768464228
				],
				[
					5.11968580728151,
					8.37766768464228
				],
				[
					4.654259824801285,
					8.37766768464228
				],
				[
					3.9561208510811077,
					8.37766768464228
				],
				[
					3.2579818773609315,
					8.37766768464228
				],
				[
					2.7925558948808673,
					8.37766768464228
				],
				[
					2.3271299124006424,
					8.144954693402166
				],
				[
					2.0944169211606907,
					7.912241702162135
				],
				[
					1.8617039299205782,
					7.679528710922022
				],
				[
					1.1635649562004018,
					7.44681571968199
				],
				[
					0.6981389737201765,
					7.214102728441878
				],
				[
					0.2327129912401126,
					6.981389737201846
				],
				[
					0,
					6.748676745961814
				],
				[
					-0.23271299123995134,
					6.515963754721701
				],
				[
					-0.6981389737201765,
					6.050537772241637
				],
				[
					-0.9308519649601279,
					5.585111789761493
				],
				[
					-0.9308519649601279,
					5.119685807281348
				],
				[
					-1.1635649562002404,
					4.421546833561171
				],
				[
					-1.1635649562002404,
					3.9561208510810273
				],
				[
					-1.1635649562002404,
					3.4906948686008827
				],
				[
					-1.1635649562002404,
					2.792555894880706
				],
				[
					-1.1635649562002404,
					2.0944169211605295
				],
				[
					-0.9308519649601279,
					1.8617039299204976
				],
				[
					-0.6981389737201765,
					1.396277947440353
				],
				[
					-0.46542598248006395,
					0.9308519649602085
				],
				[
					-0.23271299123995134,
					0.46542598248006395
				],
				[
					0,
					0.23271299124003197
				],
				[
					0.2327129912401126,
					0
				],
				[
					0.4654259824802252,
					0
				],
				[
					0.9308519649602891,
					0
				],
				[
					1.1635649562004018,
					0
				],
				[
					1.3962779474405143,
					0
				],
				[
					1.8617039299205782,
					0
				],
				[
					2.3271299124006424,
					0.23271299124003197
				],
				[
					2.559842903640755,
					0.23271299124003197
				],
				[
					2.7925558948808673,
					0.23271299124003197
				],
				[
					3.0252688861209798,
					0.23271299124003197
				],
				[
					3.0252688861209798,
					0.23271299124003197
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 303,
			"versionNonce": 758675173,
			"isDeleted": false,
			"id": "SmjJZuRN85Ubv5_KAmK6O",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1133.764611248344,
			"y": 486.3526206240474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 10.472084605802971,
			"height": 11.402936570763098,
			"seed": 1970789925,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.9308519649601279,
					0
				],
				[
					1.396277947440353,
					0
				],
				[
					2.0944169211605295,
					0.46542598248014455
				],
				[
					2.792555894880706,
					0.6981389737201765
				],
				[
					3.723407859840995,
					1.3962779474403935
				],
				[
					4.188833842321059,
					1.8617039299204976
				],
				[
					4.654259824801285,
					2.559842903640674
				],
				[
					4.886972816041236,
					3.257981877360891
				],
				[
					5.119685807281348,
					3.723407859840995
				],
				[
					5.3523987985214605,
					4.421546833561212
				],
				[
					5.3523987985214605,
					5.3523987985214605
				],
				[
					5.3523987985214605,
					6.515963754721782
				],
				[
					5.3523987985214605,
					7.214102728441959
				],
				[
					5.3523987985214605,
					7.912241702162135
				],
				[
					5.119685807281348,
					8.610380675882311
				],
				[
					4.421546833561171,
					9.308519649602488
				],
				[
					4.188833842321059,
					9.541232640842601
				],
				[
					3.723407859840995,
					9.773945632082633
				],
				[
					3.0252688861208186,
					10.47208460580289
				],
				[
					2.3271299124004807,
					11.170223579523066
				],
				[
					0.9308519649601279,
					11.402936570763098
				],
				[
					0.46542598248006395,
					11.402936570763098
				],
				[
					0,
					11.402936570763098
				],
				[
					-0.4654259824802252,
					11.402936570763098
				],
				[
					-1.396277947440353,
					10.937510588282954
				],
				[
					-2.0944169211605295,
					10.704797597042921
				],
				[
					-2.7925558948808673,
					10.239371614562778
				],
				[
					-3.7234078598411564,
					9.773945632082633
				],
				[
					-4.188833842321221,
					9.308519649602488
				],
				[
					-4.654259824801285,
					8.610380675882311
				],
				[
					-4.886972816041397,
					7.912241702162135
				],
				[
					-5.11968580728151,
					7.446815719682071
				],
				[
					-5.11968580728151,
					6.748676745961814
				],
				[
					-5.11968580728151,
					6.050537772241637
				],
				[
					-4.886972816041397,
					5.3523987985214605
				],
				[
					-4.421546833561333,
					4.886972816041316
				],
				[
					-4.188833842321221,
					4.18883384232114
				],
				[
					-3.7234078598411564,
					3.490694868600963
				],
				[
					-3.490694868601044,
					3.0252688861208186
				],
				[
					-3.0252688861208186,
					2.559842903640674
				],
				[
					-2.7925558948808673,
					2.09441692116057
				],
				[
					-2.3271299124006424,
					1.6289909386804657
				],
				[
					-2.0944169211605295,
					1.3962779474403935
				],
				[
					-1.6289909386804657,
					1.1635649562003212
				],
				[
					-1.1635649562004018,
					0.6981389737201765
				],
				[
					-0.9308519649602891,
					0.6981389737201765
				],
				[
					-0.4654259824802252,
					0.6981389737201765
				],
				[
					-0.2327129912401126,
					0.6981389737201765
				],
				[
					0.23271299123995134,
					0.46542598248014455
				],
				[
					0.46542598248006395,
					0.46542598248014455
				],
				[
					0.6981389737201765,
					0.6981389737201765
				],
				[
					1.1635649562002404,
					0.9308519649602891
				],
				[
					1.396277947440353,
					0.9308519649602891
				],
				[
					1.396277947440353,
					1.1635649562003212
				],
				[
					1.861703929920417,
					1.3962779474403935
				],
				[
					2.0944169211605295,
					1.6289909386804657
				],
				[
					2.0944169211605295,
					1.8617039299204976
				],
				[
					2.3271299124004807,
					1.8617039299204976
				],
				[
					2.3271299124004807,
					2.09441692116057
				],
				[
					2.5598429036405936,
					2.3271299124006424
				],
				[
					2.5598429036405936,
					2.3271299124006424
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 317,
			"versionNonce": 970626539,
			"isDeleted": false,
			"id": "qU4FGqJ3Vp0xF3AMPCd0q",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1133.0664722746237,
			"y": 512.4164756429344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 10.006658623322744,
			"height": 8.843093667122343,
			"seed": 51447019,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.46542598248006384,
					0
				],
				[
					0.6981389737201764,
					0
				],
				[
					1.1635649562002404,
					0
				],
				[
					1.3962779474403528,
					-0.23271299124003197
				],
				[
					1.8617039299204168,
					-0.23271299124003197
				],
				[
					2.3271299124004807,
					-0.46542598248006395
				],
				[
					2.7925558948807057,
					-0.46542598248006395
				],
				[
					3.4906948686008823,
					-0.46542598248006395
				],
				[
					4.421546833561171,
					0.2327129912401126
				],
				[
					4.886972816041235,
					0.46542598248014455
				],
				[
					5.35239879852146,
					1.1635649562003212
				],
				[
					5.817824781001524,
					1.3962779474404337
				],
				[
					6.050537772241636,
					2.0944169211606103
				],
				[
					6.283250763481588,
					2.559842903640755
				],
				[
					6.5159637547217,
					2.792555894880787
				],
				[
					6.5159637547217,
					3.2579818773609315
				],
				[
					6.5159637547217,
					3.9561208510811077
				],
				[
					6.5159637547217,
					4.421546833561252
				],
				[
					6.5159637547217,
					5.119685807281429
				],
				[
					6.5159637547217,
					5.585111789761574
				],
				[
					6.283250763481588,
					6.050537772241637
				],
				[
					5.817824781001524,
					6.28325076348175
				],
				[
					5.35239879852146,
					6.515963754721782
				],
				[
					5.119685807281347,
					6.515963754721782
				],
				[
					4.421546833561171,
					6.981389737201926
				],
				[
					3.9561208510811072,
					7.214102728441959
				],
				[
					3.2579818773607694,
					7.679528710922103
				],
				[
					3.025268886120657,
					7.912241702162215
				],
				[
					2.559842903640593,
					8.37766768464228
				],
				[
					2.3271299124004807,
					8.37766768464228
				],
				[
					2.0944169211605295,
					8.37766768464228
				],
				[
					1.628990938680304,
					8.37766768464228
				],
				[
					1.3962779474403528,
					8.37766768464228
				],
				[
					0.6981389737201764,
					8.37766768464228
				],
				[
					0.2327129912399513,
					8.37766768464228
				],
				[
					-0.4654259824802251,
					8.144954693402248
				],
				[
					-0.930851964960289,
					7.912241702162215
				],
				[
					-1.3962779474403528,
					7.679528710922103
				],
				[
					-2.0944169211606907,
					7.214102728441959
				],
				[
					-2.5598429036407544,
					6.981389737201926
				],
				[
					-3.0252688861209793,
					6.515963754721782
				],
				[
					-3.2579818773609306,
					6.28325076348175
				],
				[
					-3.2579818773609306,
					5.8178247810016055
				],
				[
					-3.4906948686010435,
					5.3523987985214605
				],
				[
					-3.4906948686010435,
					4.886972816041397
				],
				[
					-3.4906948686010435,
					4.654259824801285
				],
				[
					-3.4906948686010435,
					4.18883384232114
				],
				[
					-3.2579818773609306,
					3.490694868600963
				],
				[
					-3.2579818773609306,
					2.792555894880787
				],
				[
					-3.0252688861209793,
					2.3271299124006424
				],
				[
					-3.0252688861209793,
					2.0944169211606103
				],
				[
					-2.792555894880867,
					1.8617039299205782
				],
				[
					-2.5598429036407544,
					1.6289909386804657
				],
				[
					-2.5598429036407544,
					1.3962779474404337
				],
				[
					-2.0944169211606907,
					0.9308519649602891
				],
				[
					-1.861703929920578,
					0.6981389737201765
				],
				[
					-1.6289909386804653,
					0.46542598248014455
				],
				[
					-1.3962779474403528,
					0.46542598248014455
				],
				[
					-1.1635649562004016,
					0.2327129912401126
				],
				[
					-0.930851964960289,
					0
				],
				[
					-0.6981389737201764,
					-0.23271299124003197
				],
				[
					-0.4654259824802251,
					-0.23271299124003197
				],
				[
					-0.23271299124011255,
					-0.23271299124003197
				],
				[
					0,
					-0.23271299124003197
				],
				[
					0.46542598248006384,
					-0.23271299124003197
				],
				[
					0.6981389737201764,
					-0.23271299124003197
				],
				[
					1.1635649562002404,
					-0.23271299124003197
				],
				[
					1.3962779474403528,
					-0.23271299124003197
				],
				[
					1.628990938680304,
					-0.23271299124003197
				],
				[
					1.8617039299204168,
					-0.23271299124003197
				],
				[
					2.0944169211605295,
					0
				],
				[
					2.559842903640593,
					0.2327129912401126
				],
				[
					2.7925558948807057,
					0.46542598248014455
				],
				[
					3.025268886120657,
					0.6981389737201765
				],
				[
					3.025268886120657,
					0.9308519649602891
				],
				[
					3.025268886120657,
					0.9308519649602891
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 314,
			"versionNonce": 1462915653,
			"isDeleted": false,
			"id": "Zm7QpIs5QnlLJP6KB3v0h",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1137.953445090665,
			"y": 530.3353759684193,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.515963754721701,
			"height": 19.08246528168512,
			"seed": 1189914027,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.23271299123995134,
					-0.23271299124003197
				],
				[
					-0.6981389737201765,
					-0.46542598248014455
				],
				[
					-1.1635649562002404,
					-0.6981389737201765
				],
				[
					-1.6289909386804657,
					-0.6981389737201765
				],
				[
					-2.0944169211605295,
					-0.6981389737201765
				],
				[
					-2.3271299124006424,
					-0.6981389737201765
				],
				[
					-2.792555894880706,
					-0.6981389737201765
				],
				[
					-3.4906948686008827,
					-0.23271299124003197
				],
				[
					-3.9561208510811077,
					0
				],
				[
					-4.188833842321059,
					0.23271299124003197
				],
				[
					-4.421546833561171,
					0.46542598248014455
				],
				[
					-4.654259824801285,
					0.6981389737201765
				],
				[
					-4.886972816041236,
					1.1635649562003212
				],
				[
					-5.119685807281348,
					1.3962779474404337
				],
				[
					-5.119685807281348,
					2.0944169211606103
				],
				[
					-5.119685807281348,
					2.792555894880787
				],
				[
					-5.119685807281348,
					3.2579818773608507
				],
				[
					-5.119685807281348,
					3.723407859840995
				],
				[
					-5.119685807281348,
					4.18883384232114
				],
				[
					-4.886972816041236,
					4.654259824801285
				],
				[
					-4.421546833561171,
					5.3523987985214605
				],
				[
					-4.188833842321059,
					5.8178247810016055
				],
				[
					-3.9561208510811077,
					6.28325076348167
				],
				[
					-3.723407859840995,
					6.748676745961814
				],
				[
					-3.2579818773609315,
					7.446815719682071
				],
				[
					-2.792555894880706,
					7.679528710922103
				],
				[
					-2.559842903640755,
					8.144954693402248
				],
				[
					-2.0944169211605295,
					8.610380675882311
				],
				[
					-1.8617039299205782,
					8.843093667122425
				],
				[
					-1.396277947440353,
					9.308519649602488
				],
				[
					-1.1635649562002404,
					9.773945632082633
				],
				[
					-1.1635649562002404,
					10.006658623322744
				],
				[
					-0.9308519649601279,
					10.47208460580289
				],
				[
					-0.6981389737201765,
					10.937510588282954
				],
				[
					-0.46542598248006395,
					11.402936570763098
				],
				[
					-0.23271299123995134,
					12.101075544483274
				],
				[
					-0.23271299123995134,
					12.56650152696342
				],
				[
					-0.23271299123995134,
					13.031927509443564
				],
				[
					-0.23271299123995134,
					13.49735349192371
				],
				[
					-0.23271299123995134,
					13.962779474403773
				],
				[
					-0.23271299123995134,
					14.66091844812395
				],
				[
					-0.46542598248006395,
					14.89363143936406
				],
				[
					-0.46542598248006395,
					15.359057421844126
				],
				[
					-0.9308519649601279,
					15.82448340432427
				],
				[
					-1.1635649562002404,
					16.289909386804414
				],
				[
					-1.396277947440353,
					16.522622378044527
				],
				[
					-1.6289909386804657,
					16.75533536928456
				],
				[
					-2.3271299124006424,
					17.220761351764704
				],
				[
					-2.559842903640755,
					17.453474343004736
				],
				[
					-3.0252688861208186,
					17.686187334244767
				],
				[
					-3.2579818773609315,
					17.686187334244767
				],
				[
					-3.4906948686008827,
					17.91890032548488
				],
				[
					-3.9561208510811077,
					18.151613316724912
				],
				[
					-4.188833842321059,
					18.151613316724912
				],
				[
					-4.421546833561171,
					18.151613316724912
				],
				[
					-4.654259824801285,
					18.151613316724912
				],
				[
					-4.886972816041236,
					18.384326307964944
				],
				[
					-5.119685807281348,
					18.384326307964944
				],
				[
					-5.3523987985214605,
					18.384326307964944
				],
				[
					-5.585111789761412,
					18.384326307964944
				],
				[
					-5.817824781001525,
					18.384326307964944
				],
				[
					-6.050537772241637,
					18.151613316724912
				],
				[
					-6.050537772241637,
					17.91890032548488
				],
				[
					-6.283250763481589,
					17.91890032548488
				],
				[
					-6.515963754721701,
					17.686187334244767
				],
				[
					-6.515963754721701,
					17.453474343004736
				],
				[
					-6.515963754721701,
					16.98804836052459
				],
				[
					-6.515963754721701,
					16.75533536928456
				],
				[
					-6.515963754721701,
					16.522622378044527
				],
				[
					-6.283250763481589,
					16.289909386804414
				],
				[
					-6.283250763481589,
					16.057196395564382
				],
				[
					-6.050537772241637,
					16.057196395564382
				],
				[
					-6.050537772241637,
					16.057196395564382
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 277,
			"versionNonce": 696688779,
			"isDeleted": false,
			"id": "Gyck18xcQyOF_wCnK6qiU",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1140.7460009855456,
			"y": 542.4364515129025,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.7925558948808673,
			"height": 8.144954693402248,
			"seed": 906432139,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.2327129912401126,
					0.23271299124003197
				],
				[
					0.4654259824802252,
					0.23271299124003197
				],
				[
					0.6981389737201765,
					0.23271299124003197
				],
				[
					0.9308519649602891,
					0.23271299124003197
				],
				[
					1.1635649562004018,
					0.23271299124003197
				],
				[
					1.6289909386804657,
					0.6981389737201765
				],
				[
					1.8617039299205782,
					0.9308519649602891
				],
				[
					2.0944169211606907,
					1.6289909386804657
				],
				[
					2.3271299124008036,
					2.0944169211606103
				],
				[
					2.3271299124008036,
					2.559842903640674
				],
				[
					2.3271299124008036,
					3.2579818773608507
				],
				[
					2.3271299124008036,
					3.723407859840995
				],
				[
					2.0944169211606907,
					3.723407859840995
				],
				[
					1.8617039299205782,
					3.9561208510811077
				],
				[
					1.6289909386804657,
					3.9561208510811077
				],
				[
					1.3962779474405143,
					3.9561208510811077
				],
				[
					0.9308519649602891,
					3.9561208510811077
				],
				[
					0.6981389737201765,
					3.9561208510811077
				],
				[
					1.1635649562004018,
					4.18883384232114
				],
				[
					1.3962779474405143,
					4.421546833561252
				],
				[
					1.6289909386804657,
					4.654259824801285
				],
				[
					1.8617039299205782,
					5.119685807281429
				],
				[
					1.8617039299205782,
					5.585111789761493
				],
				[
					1.8617039299205782,
					6.050537772241637
				],
				[
					1.8617039299205782,
					6.28325076348167
				],
				[
					1.6289909386804657,
					6.515963754721782
				],
				[
					1.3962779474405143,
					6.748676745961814
				],
				[
					1.1635649562004018,
					6.981389737201926
				],
				[
					0.9308519649602891,
					7.214102728441959
				],
				[
					0.6981389737201765,
					7.679528710922103
				],
				[
					0.4654259824802252,
					7.912241702162135
				],
				[
					0.2327129912401126,
					7.912241702162135
				],
				[
					0,
					8.144954693402248
				],
				[
					-0.23271299123995134,
					8.144954693402248
				],
				[
					-0.46542598248006395,
					8.144954693402248
				],
				[
					-0.46542598248006395,
					8.144954693402248
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 358,
			"versionNonce": 270123429,
			"isDeleted": false,
			"id": "VSWYL5HyRtwsy45_Dc8w1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1144.9348348278668,
			"y": 484.02549071164674,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 11.402936570763098,
			"height": 75.39900916178044,
			"seed": 293633611,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726444,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.2327129912401126,
					0
				],
				[
					0.46542598248006395,
					0
				],
				[
					0.9308519649602891,
					0.23271299124007228
				],
				[
					1.1635649562002404,
					0.6981389737202168
				],
				[
					1.6289909386804657,
					1.1635649562003212
				],
				[
					2.5598429036405936,
					2.0944169211606103
				],
				[
					2.792555894880706,
					2.5598429036407144
				],
				[
					3.2579818773609315,
					3.0252688861208186
				],
				[
					3.4906948686008827,
					3.490694868600963
				],
				[
					3.9561208510811077,
					4.421546833561212
				],
				[
					4.188833842321221,
					4.886972816041316
				],
				[
					4.654259824801285,
					6.050537772241637
				],
				[
					4.886972816041397,
					6.748676745961855
				],
				[
					5.119685807281348,
					7.679528710922103
				],
				[
					5.3523987985214605,
					8.610380675882311
				],
				[
					5.585111789761574,
					9.30851964960257
				],
				[
					5.817824781001525,
					10.006658623322744
				],
				[
					6.28325076348175,
					10.937510588282954
				],
				[
					6.515963754721701,
					12.333788535723388
				],
				[
					6.981389737201926,
					13.264640500683596
				],
				[
					7.214102728441878,
					14.428205456883918
				],
				[
					7.44681571968199,
					15.591770413084237
				],
				[
					7.679528710922103,
					17.220761351764704
				],
				[
					8.144954693402166,
					18.384326307965026
				],
				[
					8.144954693402166,
					19.547891264165347
				],
				[
					8.37766768464228,
					20.478743229125556
				],
				[
					8.610380675882231,
					21.409595194085842
				],
				[
					8.843093667122343,
					22.573160150286164
				],
				[
					9.075806658362456,
					23.27129912400634
				],
				[
					9.30851964960257,
					24.667577071446694
				],
				[
					9.54123264084252,
					25.598429036406984
				],
				[
					9.773945632082633,
					26.994706983847337
				],
				[
					9.773945632082633,
					28.15827194004766
				],
				[
					10.006658623322744,
					29.089123905007867
				],
				[
					10.239371614562858,
					30.252688861208267
				],
				[
					10.239371614562858,
					30.950827834928443
				],
				[
					10.239371614562858,
					31.88167979988865
				],
				[
					10.239371614562858,
					32.57981877360883
				],
				[
					10.239371614562858,
					33.27795774732908
				],
				[
					10.239371614562858,
					34.208809712289295
				],
				[
					10.239371614562858,
					34.90694868600947
				],
				[
					10.239371614562858,
					35.37237466848961
				],
				[
					10.239371614562858,
					36.07051364220979
				],
				[
					10.239371614562858,
					36.768652615929966
				],
				[
					10.239371614562858,
					37.93221757213029
				],
				[
					10.239371614562858,
					38.39764355461043
				],
				[
					10.239371614562858,
					39.32849551957072
				],
				[
					10.239371614562858,
					39.793921502050786
				],
				[
					10.47208460580281,
					40.724773467011076
				],
				[
					10.47208460580281,
					41.65562543197129
				],
				[
					10.47208460580281,
					42.35376440569154
				],
				[
					10.704797597042921,
					43.05190337941172
				],
				[
					10.704797597042921,
					43.51732936189178
				],
				[
					10.704797597042921,
					44.44818132685207
				],
				[
					10.937510588283034,
					45.14632030057225
				],
				[
					10.937510588283034,
					46.07717226553254
				],
				[
					10.937510588283034,
					46.5425982480126
				],
				[
					10.937510588283034,
					47.24073722173278
				],
				[
					10.937510588283034,
					48.17158918669307
				],
				[
					10.937510588283034,
					48.869728160413246
				],
				[
					10.937510588283034,
					49.800580125373536
				],
				[
					10.937510588283034,
					50.49871909909371
				],
				[
					10.937510588283034,
					51.19685807281389
				],
				[
					10.937510588283034,
					51.894997046534066
				],
				[
					10.937510588283034,
					52.82584901149435
				],
				[
					11.170223579522986,
					53.523987985214525
				],
				[
					11.170223579522986,
					54.68755294141485
				],
				[
					11.170223579522986,
					55.15297892389499
				],
				[
					11.402936570763098,
					56.0838308888552
				],
				[
					11.402936570763098,
					56.549256871335345
				],
				[
					11.402936570763098,
					57.01468285381549
				],
				[
					11.402936570763098,
					57.71282182753567
				],
				[
					11.402936570763098,
					58.643673792495875
				],
				[
					11.402936570763098,
					59.34181276621614
				],
				[
					11.402936570763098,
					60.03995173993631
				],
				[
					11.402936570763098,
					60.505377722416455
				],
				[
					11.402936570763098,
					60.97080370489652
				],
				[
					11.170223579522986,
					61.668942678616695
				],
				[
					11.170223579522986,
					62.36708165233695
				],
				[
					10.937510588283034,
					62.8325076348171
				],
				[
					10.937510588283034,
					63.065220626057126
				],
				[
					10.704797597042921,
					63.7633595997773
				],
				[
					10.47208460580281,
					64.22878558225744
				],
				[
					10.239371614562858,
					64.69421156473751
				],
				[
					10.006658623322744,
					65.39235053845778
				],
				[
					9.773945632082633,
					65.85777652093792
				],
				[
					9.54123264084252,
					66.09048951217795
				],
				[
					9.54123264084252,
					66.5559154946581
				],
				[
					9.30851964960257,
					66.78862848589813
				],
				[
					9.075806658362456,
					67.25405446837827
				],
				[
					8.843093667122343,
					67.95219344209845
				],
				[
					8.843093667122343,
					68.18490643333848
				],
				[
					8.610380675882231,
					68.88304540705873
				],
				[
					8.610380675882231,
					69.11575839829877
				],
				[
					8.144954693402166,
					69.81389737201894
				],
				[
					8.144954693402166,
					70.04661036325898
				],
				[
					7.912241702162055,
					70.51203634573912
				],
				[
					7.912241702162055,
					70.74474933697915
				],
				[
					7.679528710922103,
					70.97746232821926
				],
				[
					7.44681571968199,
					71.4428883106994
				],
				[
					7.214102728441878,
					71.67560130193944
				],
				[
					7.214102728441878,
					72.14102728441958
				],
				[
					6.981389737201926,
					72.37374027565961
				],
				[
					6.748676745961814,
					72.60645326689973
				],
				[
					6.515963754721701,
					73.07187924937979
				],
				[
					6.515963754721701,
					73.30459224061991
				],
				[
					6.28325076348175,
					73.53730523185993
				],
				[
					6.28325076348175,
					73.77001822310005
				],
				[
					6.28325076348175,
					74.00273121434009
				],
				[
					6.050537772241637,
					74.46815719682023
				],
				[
					5.817824781001525,
					74.46815719682023
				],
				[
					5.817824781001525,
					74.70087018806026
				],
				[
					5.817824781001525,
					74.93358317930037
				],
				[
					5.817824781001525,
					75.1662961705404
				],
				[
					5.585111789761574,
					75.39900916178044
				],
				[
					5.585111789761574,
					75.39900916178044
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 377,
			"versionNonce": 1754814251,
			"isDeleted": false,
			"id": "0tBoPkSf",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1216.4296263097922,
			"y": 416.003244066602,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 161.03065490722656,
			"height": 28.369467096885018,
			"seed": 915230731,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"fontSize": 11.347786838754008,
			"fontFamily": 1,
			"text": "If S1=S2=S3  => isotropic\nelse           => anisotropic",
			"rawText": "If S1=S2=S3  => isotropic\nelse           => anisotropic",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If S1=S2=S3  => isotropic\nelse           => anisotropic",
			"lineHeight": 1.25,
			"baseline": 24
		},
		{
			"type": "freedraw",
			"version": 310,
			"versionNonce": 1293698309,
			"isDeleted": false,
			"id": "427Wq5N8VaNQSo5fkM3Hv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1172.7870746159604,
			"y": 489.10488858740086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.230430137257101,
			"height": 64.04095264427723,
			"seed": 794152811,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.3443061970121738,
					0.34430619701225446
				],
				[
					-0.6886123940245089,
					1.032918591036723
				],
				[
					-0.6886123940245089,
					1.7215309850611915
				],
				[
					-1.0329185910366827,
					2.754449576097955
				],
				[
					-1.3772247880490178,
					3.0987557731102093
				],
				[
					-1.3772247880490178,
					3.7873681671347184
				],
				[
					-1.7215309850611915,
					4.4759805611591466
				],
				[
					-2.0658371820733654,
					6.197511546220419
				],
				[
					-2.4101433790857003,
					6.886123940244847
				],
				[
					-2.4101433790857003,
					7.91904253128161
				],
				[
					-2.754449576097874,
					9.296267319330548
				],
				[
					-3.0987557731102093,
					10.673492107379564
				],
				[
					-3.443061970122383,
					11.706410698416247
				],
				[
					-3.443061970122383,
					13.083635486465266
				],
				[
					-3.443061970122383,
					13.772247880489694
				],
				[
					-3.443061970122383,
					15.149472668538712
				],
				[
					-3.443061970122383,
					16.182391259575393
				],
				[
					-3.443061970122383,
					17.215309850612158
				],
				[
					-3.443061970122383,
					17.903922244636668
				],
				[
					-3.443061970122383,
					19.625453229697857
				],
				[
					-3.443061970122383,
					20.658371820734622
				],
				[
					-3.0987557731102093,
					22.035596608783557
				],
				[
					-3.0987557731102093,
					23.06851519982032
				],
				[
					-2.754449576097874,
					24.101433790857005
				],
				[
					-2.754449576097874,
					25.134352381893766
				],
				[
					-2.4101433790857003,
					26.16727097293053
				],
				[
					-2.4101433790857003,
					27.54449576097947
				],
				[
					-2.0658371820733654,
					28.57741435201623
				],
				[
					-2.0658371820733654,
					29.95463914006517
				],
				[
					-2.0658371820733654,
					30.64325153408968
				],
				[
					-1.7215309850611915,
					31.676170125126358
				],
				[
					-1.7215309850611915,
					32.36478251915087
				],
				[
					-1.3772247880490178,
					33.39770111018763
				],
				[
					-1.3772247880490178,
					34.77492589823657
				],
				[
					-1.0329185910366827,
					35.807844489273336
				],
				[
					-1.0329185910366827,
					37.52937547433452
				],
				[
					-1.0329185910366827,
					38.90660026238354
				],
				[
					-1.0329185910366827,
					39.939518853420225
				],
				[
					-1.0329185910366827,
					40.97243744445691
				],
				[
					-1.0329185910366827,
					42.34966223250593
				],
				[
					-1.0329185910366827,
					43.03827462653043
				],
				[
					-1.0329185910366827,
					44.071193217567114
				],
				[
					-1.0329185910366827,
					45.10411180860388
				],
				[
					-1.0329185910366827,
					46.13703039964064
				],
				[
					-1.0329185910366827,
					46.82564279366507
				],
				[
					-1.0329185910366827,
					47.85856138470184
				],
				[
					-1.0329185910366827,
					48.89147997573852
				],
				[
					-0.6886123940245089,
					50.61301096079979
				],
				[
					-0.3443061970121738,
					51.301623354824216
				],
				[
					-0.3443061970121738,
					52.334541945860984
				],
				[
					0,
					53.02315433988549
				],
				[
					0.34430619701233506,
					54.05607293092217
				],
				[
					0.6886123940245089,
					55.43329771897119
				],
				[
					1.0329185910366827,
					56.12191011299562
				],
				[
					1.0329185910366827,
					57.15482870403238
				],
				[
					1.3772247880490178,
					58.187747295069144
				],
				[
					1.7215309850611915,
					58.876359689093654
				],
				[
					2.0658371820735266,
					59.56497208311808
				],
				[
					2.0658371820735266,
					60.25358447714259
				],
				[
					2.4101433790857003,
					60.94219687116702
				],
				[
					2.4101433790857003,
					61.63080926519153
				],
				[
					2.7544495760980356,
					61.97511546220378
				],
				[
					2.7544495760980356,
					62.66372785622829
				],
				[
					3.0987557731102093,
					63.00803405324054
				],
				[
					3.443061970122383,
					63.352340250252716
				],
				[
					3.443061970122383,
					63.69664644726505
				],
				[
					3.7873681671347184,
					64.04095264427723
				],
				[
					3.7873681671347184,
					64.04095264427723
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 264,
			"versionNonce": 1434073547,
			"isDeleted": false,
			"id": "ICp48HU5EgYY2R5cHqzUh",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1186.2150162994378,
			"y": 489.4491947844132,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.574736334269437,
			"height": 11.706410698416247,
			"seed": 194980651,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.34430619701225446
				],
				[
					-0.34430619701233506,
					-0.34430619701225446
				],
				[
					-0.6886123940245089,
					-0.34430619701225446
				],
				[
					-0.6886123940245089,
					0.34430619701225446
				],
				[
					-1.3772247880490178,
					1.032918591036723
				],
				[
					-1.3772247880490178,
					1.377224788048937
				],
				[
					-2.0658371820733654,
					2.754449576097955
				],
				[
					-2.7544495760980356,
					3.7873681671346375
				],
				[
					-3.443061970122383,
					4.820286758171401
				],
				[
					-4.131674364146892,
					5.50889915219591
				],
				[
					-4.820286758171401,
					6.886123940244847
				],
				[
					-5.50889915219591,
					7.574736334269356
				],
				[
					-5.853205349208084,
					8.263348728293865
				],
				[
					-6.541817743232593,
					8.607654925306038
				],
				[
					-6.886123940244928,
					9.640573516342801
				],
				[
					-7.230430137257101,
					9.984879713355056
				],
				[
					-7.230430137257101,
					10.673492107379564
				],
				[
					-7.574736334269437,
					11.01779830439174
				],
				[
					-7.574736334269437,
					11.362104501403993
				],
				[
					-7.574736334269437,
					10.673492107379564
				],
				[
					-7.574736334269437,
					9.296267319330548
				],
				[
					-7.574736334269437,
					8.951961122318293
				],
				[
					-7.574736334269437,
					8.951961122318293
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 28793957,
			"isDeleted": false,
			"id": "jnMJvuSnc4xbrX7CC1Sdc",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1180.0175047532175,
			"y": 486.3504390113029,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.230430137257101,
			"height": 13.772247880489774,
			"seed": 456088779,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.34430619701233506,
					0
				],
				[
					0.6886123940245089,
					0.6886123940245089
				],
				[
					1.0329185910366827,
					1.0329185910367633
				],
				[
					1.3772247880490178,
					2.065837182073446
				],
				[
					1.7215309850613527,
					2.754449576097955
				],
				[
					2.0658371820735266,
					3.443061970122464
				],
				[
					2.4101433790857003,
					4.4759805611591466
				],
				[
					3.0987557731102093,
					5.50889915219591
				],
				[
					3.443061970122383,
					6.197511546220338
				],
				[
					4.131674364147053,
					7.574736334269356
				],
				[
					4.131674364147053,
					7.91904253128161
				],
				[
					4.820286758171401,
					8.951961122318373
				],
				[
					5.1645929551837355,
					9.640573516342801
				],
				[
					5.50889915219591,
					10.329185910367311
				],
				[
					5.853205349208084,
					11.01779830439182
				],
				[
					5.853205349208084,
					11.362104501404074
				],
				[
					6.197511546220419,
					11.706410698416247
				],
				[
					6.197511546220419,
					12.050716895428502
				],
				[
					6.541817743232754,
					12.73932928945301
				],
				[
					6.886123940244928,
					12.73932928945301
				],
				[
					6.886123940244928,
					13.083635486465266
				],
				[
					6.886123940244928,
					13.42794168347752
				],
				[
					7.230430137257101,
					13.42794168347752
				],
				[
					7.230430137257101,
					13.772247880489774
				],
				[
					7.230430137257101,
					13.772247880489774
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 262,
			"versionNonce": 491178091,
			"isDeleted": false,
			"id": "oumGApZehTFXFmmeKBLdK",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1184.4934853143768,
			"y": 491.8593381634988,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 4.131674364146892,
			"height": 5.853205349208164,
			"seed": 963124139,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.34430619701217374,
					-0.34430619701225446
				],
				[
					0.6886123940245088,
					-0.34430619701225446
				],
				[
					1.0329185910366825,
					-0.6886123940245089
				],
				[
					1.0329185910366825,
					-1.3772247880489774
				],
				[
					1.0329185910366825,
					-1.721530985061232
				],
				[
					1.3772247880488562,
					-2.065837182073446
				],
				[
					1.7215309850611913,
					-2.4101433790857003
				],
				[
					1.7215309850611913,
					-2.754449576097955
				],
				[
					2.065837182073526,
					-3.0987557731102093
				],
				[
					2.065837182073526,
					-3.443061970122464
				],
				[
					2.4101433790857,
					-3.443061970122464
				],
				[
					2.754449576097874,
					-3.787368167134678
				],
				[
					2.754449576097874,
					-4.1316743641469325
				],
				[
					2.754449576097874,
					-4.4759805611591466
				],
				[
					3.098755773110209,
					-4.4759805611591466
				],
				[
					3.4430619701223826,
					-4.820286758171401
				],
				[
					3.7873681671345563,
					-5.164592955183656
				],
				[
					3.7873681671345563,
					-5.50889915219591
				],
				[
					3.7873681671345563,
					-5.853205349208164
				],
				[
					4.131674364146892,
					-5.853205349208164
				],
				[
					4.131674364146892,
					-5.853205349208164
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 318,
			"versionNonce": 1438156741,
			"isDeleted": false,
			"id": "WGizQp5NmrFOK7YZ6SQDW",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1181.050423344254,
			"y": 508.38603562008643,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 12.73932928945301,
			"height": 16.182391259575393,
			"seed": 865862667,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.34430619701225446
				],
				[
					0,
					0.6886123940245089
				],
				[
					0,
					1.3772247880490178
				],
				[
					0,
					1.7215309850611915
				],
				[
					0.34430619701233506,
					2.4101433790857003
				],
				[
					0.6886123940246701,
					3.0987557731102093
				],
				[
					1.7215309850613527,
					4.475980561159227
				],
				[
					2.0658371820735266,
					5.164592955183656
				],
				[
					2.7544495760980356,
					5.50889915219591
				],
				[
					3.4430619701225442,
					5.853205349208164
				],
				[
					4.131674364147053,
					5.853205349208164
				],
				[
					4.820286758171401,
					5.50889915219591
				],
				[
					5.508899152196071,
					4.475980561159227
				],
				[
					5.508899152196071,
					3.7873681671347184
				],
				[
					5.8532053492082445,
					2.754449576097955
				],
				[
					5.8532053492082445,
					2.0658371820735266
				],
				[
					6.197511546220419,
					1.3772247880490178
				],
				[
					6.197511546220419,
					0.34430619701225446
				],
				[
					6.541817743232754,
					-0.3443061970121738
				],
				[
					6.541817743232754,
					-0.6886123940245089
				],
				[
					6.541817743232754,
					-1.0329185910366827
				],
				[
					6.541817743232754,
					-0.6886123940245089
				],
				[
					6.541817743232754,
					0
				],
				[
					6.541817743232754,
					0.6886123940245089
				],
				[
					6.541817743232754,
					2.754449576097955
				],
				[
					6.541817743232754,
					3.7873681671347184
				],
				[
					6.541817743232754,
					5.50889915219591
				],
				[
					6.541817743232754,
					6.541817743232673
				],
				[
					6.541817743232754,
					7.230430137257101
				],
				[
					6.541817743232754,
					8.263348728293865
				],
				[
					6.541817743232754,
					8.951961122318373
				],
				[
					6.197511546220419,
					9.984879713355056
				],
				[
					5.508899152196071,
					11.706410698416327
				],
				[
					5.1645929551837355,
					12.73932928945301
				],
				[
					4.475980561159227,
					13.42794168347752
				],
				[
					4.131674364147053,
					13.772247880489774
				],
				[
					3.7873681671347184,
					14.460860274514202
				],
				[
					3.4430619701225442,
					15.149472668538712
				],
				[
					3.0987557731103705,
					15.149472668538712
				],
				[
					2.7544495760980356,
					15.149472668538712
				],
				[
					2.4101433790857003,
					15.149472668538712
				],
				[
					2.0658371820735266,
					14.805166471526457
				],
				[
					1.3772247880490178,
					14.460860274514202
				],
				[
					1.032918591036844,
					14.460860274514202
				],
				[
					0.6886123940246701,
					14.116554077502029
				],
				[
					0.34430619701233506,
					14.116554077502029
				],
				[
					0,
					13.772247880489774
				],
				[
					-0.6886123940243476,
					13.083635486465266
				],
				[
					-1.0329185910366827,
					11.706410698416327
				],
				[
					-1.0329185910366827,
					11.01779830439182
				],
				[
					-1.0329185910366827,
					9.984879713355056
				],
				[
					-0.6886123940243476,
					9.640573516342801
				],
				[
					-0.3443061970121738,
					9.296267319330628
				],
				[
					0,
					8.951961122318373
				],
				[
					0.6886123940246701,
					8.951961122318373
				],
				[
					1.032918591036844,
					8.607654925306118
				],
				[
					1.7215309850613527,
					8.607654925306118
				],
				[
					2.4101433790857003,
					8.607654925306118
				],
				[
					3.4430619701225442,
					8.607654925306118
				],
				[
					4.131674364147053,
					8.951961122318373
				],
				[
					4.475980561159227,
					8.951961122318373
				],
				[
					5.1645929551837355,
					9.296267319330628
				],
				[
					5.8532053492082445,
					9.640573516342801
				],
				[
					6.541817743232754,
					9.984879713355056
				],
				[
					6.886123940244928,
					9.984879713355056
				],
				[
					7.230430137257101,
					10.329185910367311
				],
				[
					8.263348728293945,
					10.673492107379564
				],
				[
					8.607654925306118,
					11.01779830439182
				],
				[
					8.951961122318455,
					11.01779830439182
				],
				[
					9.296267319330628,
					11.362104501404074
				],
				[
					9.640573516342801,
					11.706410698416327
				],
				[
					10.329185910367471,
					12.050716895428502
				],
				[
					10.673492107379646,
					12.395023092440756
				],
				[
					11.01779830439182,
					12.395023092440756
				],
				[
					11.362104501404154,
					12.395023092440756
				],
				[
					11.706410698416327,
					12.395023092440756
				],
				[
					11.706410698416327,
					12.395023092440756
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 287,
			"versionNonce": 1707639563,
			"isDeleted": false,
			"id": "Wdx4iFxC2bqcnLztwR7Gh",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1181.050423344254,
			"y": 534.8976127900293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 12.395023092440837,
			"height": 16.526697456587648,
			"seed": 1096932203,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6886123940246701,
					0
				],
				[
					1.7215309850613527,
					0
				],
				[
					3.4430619701225442,
					0
				],
				[
					4.820286758171401,
					0
				],
				[
					5.8532053492082445,
					0
				],
				[
					6.541817743232754,
					-0.34430619701225446
				],
				[
					7.574736334269437,
					-0.34430619701225446
				],
				[
					8.951961122318455,
					-0.34430619701225446
				],
				[
					9.984879713355136,
					-0.34430619701225446
				],
				[
					9.984879713355136,
					0.34430619701225446
				],
				[
					9.296267319330628,
					1.0329185910366827
				],
				[
					7.574736334269437,
					2.754449576097955
				],
				[
					6.541817743232754,
					4.820286758171401
				],
				[
					5.508899152196071,
					5.853205349208084
				],
				[
					4.475980561159227,
					7.574736334269356
				],
				[
					3.4430619701225442,
					9.640573516342801
				],
				[
					2.7544495760980356,
					11.362104501403993
				],
				[
					2.4101433790857003,
					12.050716895428502
				],
				[
					2.4101433790857003,
					12.73932928945293
				],
				[
					2.4101433790857003,
					13.083635486465266
				],
				[
					2.4101433790857003,
					13.427941683477439
				],
				[
					2.4101433790857003,
					14.116554077501949
				],
				[
					2.4101433790857003,
					14.805166471526457
				],
				[
					2.4101433790857003,
					15.14947266853863
				],
				[
					2.7544495760980356,
					15.83808506256314
				],
				[
					2.7544495760980356,
					16.182391259575393
				],
				[
					3.0987557731103705,
					16.182391259575393
				],
				[
					3.7873681671347184,
					16.182391259575393
				],
				[
					4.131674364147053,
					16.182391259575393
				],
				[
					4.820286758171401,
					16.182391259575393
				],
				[
					5.508899152196071,
					16.182391259575393
				],
				[
					6.541817743232754,
					16.182391259575393
				],
				[
					6.886123940244928,
					16.182391259575393
				],
				[
					7.919042531281772,
					15.83808506256314
				],
				[
					8.607654925306118,
					15.493778865550965
				],
				[
					9.296267319330628,
					15.14947266853863
				],
				[
					9.984879713355136,
					14.460860274514202
				],
				[
					10.673492107379646,
					14.116554077501949
				],
				[
					11.362104501404154,
					13.772247880489694
				],
				[
					11.706410698416327,
					13.427941683477439
				],
				[
					12.050716895428502,
					13.427941683477439
				],
				[
					12.395023092440837,
					13.427941683477439
				],
				[
					12.395023092440837,
					13.083635486465266
				],
				[
					12.395023092440837,
					12.73932928945293
				],
				[
					11.706410698416327,
					12.395023092440756
				],
				[
					11.706410698416327,
					12.395023092440756
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 258,
			"versionNonce": 457000741,
			"isDeleted": false,
			"id": "wI3DNITSJukpI2bomHcvo",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1182.4276481323031,
			"y": 540.7508181392374,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 10.673492107379484,
			"height": 0.34430619701225446,
			"seed": 2128132459,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.34430619701225446
				],
				[
					0.34430619701233506,
					0.34430619701225446
				],
				[
					1.7215309850613527,
					0.34430619701225446
				],
				[
					3.0987557731102093,
					0.34430619701225446
				],
				[
					4.131674364147053,
					0.34430619701225446
				],
				[
					5.1645929551837355,
					0.34430619701225446
				],
				[
					6.886123940244928,
					0.34430619701225446
				],
				[
					7.230430137257101,
					0.34430619701225446
				],
				[
					7.574736334269437,
					0.34430619701225446
				],
				[
					8.263348728293783,
					0.34430619701225446
				],
				[
					8.951961122318455,
					0.34430619701225446
				],
				[
					9.296267319330628,
					0.34430619701225446
				],
				[
					9.640573516342801,
					0.34430619701225446
				],
				[
					9.984879713355136,
					0.34430619701225446
				],
				[
					10.329185910367311,
					0
				],
				[
					10.673492107379484,
					0
				],
				[
					10.673492107379484,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 317,
			"versionNonce": 930736555,
			"isDeleted": false,
			"id": "2ymhFH5H1tW_7wCK3iXr_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1193.445446436695,
			"y": 489.4491947844132,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 8.951961122318293,
			"height": 64.38525884128948,
			"seed": 495532235,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.34430619701233506,
					0
				],
				[
					0.6886123940245089,
					0.34430619701225446
				],
				[
					1.0329185910366827,
					0.6886123940244685
				],
				[
					1.3772247880490178,
					1.032918591036723
				],
				[
					2.0658371820733654,
					1.7215309850611915
				],
				[
					2.4101433790857003,
					2.4101433790857003
				],
				[
					3.0987557731102093,
					2.754449576097955
				],
				[
					3.7873681671347184,
					4.131674364146892
				],
				[
					4.131674364146892,
					5.164592955183656
				],
				[
					4.475980561159227,
					6.541817743232593
				],
				[
					4.820286758171401,
					7.230430137257101
				],
				[
					5.1645929551837355,
					8.607654925306038
				],
				[
					5.853205349208084,
					10.673492107379564
				],
				[
					5.853205349208084,
					11.362104501403993
				],
				[
					6.197511546220419,
					12.73932928945301
				],
				[
					6.541817743232593,
					13.772247880489694
				],
				[
					6.541817743232593,
					14.460860274514202
				],
				[
					6.886123940244928,
					15.83808506256314
				],
				[
					6.886123940244928,
					16.526697456587648
				],
				[
					7.230430137257101,
					17.903922244636668
				],
				[
					7.574736334269437,
					18.592534638661174
				],
				[
					7.91904253128161,
					19.969759426710112
				],
				[
					7.91904253128161,
					21.002678017746874
				],
				[
					7.91904253128161,
					22.035596608783557
				],
				[
					8.263348728293783,
					23.75712759384475
				],
				[
					8.607654925306118,
					25.134352381893766
				],
				[
					8.607654925306118,
					25.822964775918276
				],
				[
					8.951961122318293,
					27.200189563967214
				],
				[
					8.951961122318293,
					28.233108155003976
				],
				[
					8.951961122318293,
					29.26602674604066
				],
				[
					8.951961122318293,
					30.298945337077424
				],
				[
					8.951961122318293,
					31.331863928114107
				],
				[
					8.951961122318293,
					32.70908871616312
				],
				[
					8.951961122318293,
					33.742007307199806
				],
				[
					8.951961122318293,
					34.77492589823657
				],
				[
					8.951961122318293,
					35.80784448927325
				],
				[
					8.951961122318293,
					37.18506927732227
				],
				[
					8.951961122318293,
					38.217987868358954
				],
				[
					8.951961122318293,
					39.250906459395715
				],
				[
					8.951961122318293,
					40.62813124744465
				],
				[
					8.607654925306118,
					41.31674364146916
				],
				[
					8.607654925306118,
					42.69396842951818
				],
				[
					8.607654925306118,
					44.071193217567114
				],
				[
					8.607654925306118,
					45.10411180860388
				],
				[
					8.263348728293783,
					46.48133659665282
				],
				[
					8.263348728293783,
					47.51425518768958
				],
				[
					8.263348728293783,
					48.54717377872626
				],
				[
					8.263348728293783,
					49.58009236976302
				],
				[
					8.263348728293783,
					50.26870476378753
				],
				[
					8.263348728293783,
					51.301623354824216
				],
				[
					8.263348728293783,
					51.645929551836474
				],
				[
					8.263348728293783,
					52.334541945860984
				],
				[
					8.263348728293783,
					52.678848142873235
				],
				[
					8.263348728293783,
					53.71176673390992
				],
				[
					8.263348728293783,
					54.05607293092217
				],
				[
					7.91904253128161,
					55.08899152195894
				],
				[
					7.91904253128161,
					55.43329771897119
				],
				[
					7.574736334269437,
					56.46621631000787
				],
				[
					7.574736334269437,
					56.810522507020124
				],
				[
					7.230430137257101,
					57.499134901044634
				],
				[
					6.886123940244928,
					58.187747295069066
				],
				[
					6.541817743232593,
					58.5320534920814
				],
				[
					6.197511546220419,
					59.22066588610583
				],
				[
					6.197511546220419,
					59.56497208311808
				],
				[
					5.853205349208084,
					60.25358447714259
				],
				[
					5.50889915219591,
					60.9421968711671
				],
				[
					5.50889915219591,
					61.28650306817927
				],
				[
					5.1645929551837355,
					61.97511546220378
				],
				[
					4.820286758171401,
					62.31942165921604
				],
				[
					4.820286758171401,
					62.66372785622829
				],
				[
					4.820286758171401,
					63.008034053240465
				],
				[
					4.475980561159227,
					63.3523402502528
				],
				[
					4.475980561159227,
					63.696646447264975
				],
				[
					4.131674364146892,
					64.04095264427723
				],
				[
					4.131674364146892,
					64.38525884128948
				],
				[
					4.131674364146892,
					64.38525884128948
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 259,
			"versionNonce": 78846597,
			"isDeleted": false,
			"id": "Buxz0xOzgfX7zdnOAPte-",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1213.4152058634052,
			"y": 513.2063223782579,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 12.73932928945301,
			"height": 0.6886123940245089,
			"seed": 1575195019,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3443061970121738,
					0
				],
				[
					1.3772247880490178,
					0
				],
				[
					2.4101433790857003,
					0
				],
				[
					3.0987557731102093,
					0
				],
				[
					3.7873681671347184,
					0
				],
				[
					4.820286758171401,
					0
				],
				[
					5.853205349208084,
					0.34430619701225446
				],
				[
					6.541817743232593,
					0.34430619701225446
				],
				[
					7.91904253128161,
					0.34430619701225446
				],
				[
					8.263348728293945,
					0.34430619701225446
				],
				[
					8.951961122318293,
					0.34430619701225446
				],
				[
					9.640573516342801,
					0.6886123940245089
				],
				[
					10.329185910367311,
					0.6886123940245089
				],
				[
					11.01779830439182,
					0.6886123940245089
				],
				[
					11.706410698416327,
					0.6886123940245089
				],
				[
					12.050716895428502,
					0.6886123940245089
				],
				[
					12.395023092440676,
					0.6886123940245089
				],
				[
					12.73932928945301,
					0.6886123940245089
				],
				[
					12.73932928945301,
					0.6886123940245089
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 257,
			"versionNonce": 663059531,
			"isDeleted": false,
			"id": "U3lty7-eF-4qkCQmTXAqT",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1213.7595120604174,
			"y": 519.4038339244782,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 11.706410698416327,
			"height": 0.34430619701225446,
			"seed": 318768299,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.34430619701233506,
					0
				],
				[
					1.032918591036844,
					0
				],
				[
					2.4101433790857003,
					0
				],
				[
					3.4430619701225442,
					0
				],
				[
					5.1645929551837355,
					0
				],
				[
					5.8532053492082445,
					0
				],
				[
					7.230430137257101,
					0
				],
				[
					7.919042531281772,
					0
				],
				[
					8.607654925306118,
					0.34430619701225446
				],
				[
					9.296267319330628,
					0.34430619701225446
				],
				[
					9.640573516342801,
					0.34430619701225446
				],
				[
					9.984879713355136,
					0.34430619701225446
				],
				[
					10.673492107379646,
					0.34430619701225446
				],
				[
					11.01779830439182,
					0.34430619701225446
				],
				[
					11.362104501404154,
					0.34430619701225446
				],
				[
					11.706410698416327,
					0.34430619701225446
				],
				[
					11.706410698416327,
					0.34430619701225446
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 312,
			"versionNonce": 450331109,
			"isDeleted": false,
			"id": "FQdjqZvzXMDcw06HujT0M",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1258.519317672009,
			"y": 487.38335760233974,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 15.149472668538712,
			"height": 68.51693320543637,
			"seed": 1787112075,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.34430619701233506,
					0
				],
				[
					0.34430619701233506,
					0.3443061970122141
				],
				[
					0.34430619701233506,
					1.377224788048937
				],
				[
					0,
					2.065837182073446
				],
				[
					0,
					2.7544495760979144
				],
				[
					-0.3443061970121738,
					3.7873681671346375
				],
				[
					-0.6886123940243476,
					4.820286758171401
				],
				[
					-0.6886123940243476,
					5.50889915219591
				],
				[
					-1.0329185910366827,
					6.197511546220338
				],
				[
					-1.0329185910366827,
					6.541817743232593
				],
				[
					-1.0329185910366827,
					7.574736334269356
				],
				[
					-1.0329185910366827,
					8.263348728293783
				],
				[
					-1.0329185910366827,
					9.296267319330548
				],
				[
					-1.0329185910366827,
					10.329185910367311
				],
				[
					-1.0329185910366827,
					11.706410698416247
				],
				[
					-1.0329185910366827,
					12.395023092440756
				],
				[
					-1.0329185910366827,
					14.116554077501949
				],
				[
					-1.0329185910366827,
					15.493778865550885
				],
				[
					-1.0329185910366827,
					17.215309850612158
				],
				[
					-1.0329185910366827,
					18.592534638661096
				],
				[
					-1.0329185910366827,
					20.314065623722286
				],
				[
					-1.0329185910366827,
					21.691290411771302
				],
				[
					-1.0329185910366827,
					23.412821396832495
				],
				[
					-1.0329185910366827,
					24.79004618488151
				],
				[
					-1.0329185910366827,
					26.16727097293045
				],
				[
					-1.0329185910366827,
					27.200189563967214
				],
				[
					-1.0329185910366827,
					28.57741435201615
				],
				[
					-1.0329185910366827,
					29.610332943052914
				],
				[
					-1.0329185910366827,
					31.676170125126358
				],
				[
					-1.0329185910366827,
					33.397701110187555
				],
				[
					-0.6886123940243476,
					35.119232095248826
				],
				[
					-0.6886123940243476,
					36.15215068628551
				],
				[
					-0.3443061970121738,
					37.52937547433452
				],
				[
					-0.3443061970121738,
					39.250906459395715
				],
				[
					0,
					40.628131247444735
				],
				[
					0.34430619701233506,
					42.00535603549367
				],
				[
					0.34430619701233506,
					43.382580823542604
				],
				[
					0.6886123940246701,
					44.759805611591624
				],
				[
					1.032918591036844,
					45.79272420262831
				],
				[
					1.7215309850613527,
					47.51425518768958
				],
				[
					2.0658371820735266,
					48.89147997573852
				],
				[
					2.4101433790857003,
					49.92439856677528
				],
				[
					2.7544495760980356,
					50.957317157811964
				],
				[
					3.0987557731103705,
					51.990235748848725
				],
				[
					3.4430619701225442,
					53.36746053689766
				],
				[
					3.7873681671347184,
					54.05607293092217
				],
				[
					4.475980561159227,
					55.08899152195894
				],
				[
					4.820286758171401,
					56.12191011299562
				],
				[
					5.1645929551837355,
					57.499134901044634
				],
				[
					5.508899152196071,
					58.53205349208132
				],
				[
					5.8532053492082445,
					59.56497208311808
				],
				[
					6.197511546220419,
					60.59789067415485
				],
				[
					6.541817743232754,
					61.28650306817927
				],
				[
					6.886123940244928,
					61.63080926519153
				],
				[
					7.230430137257101,
					61.97511546220378
				],
				[
					7.230430137257101,
					62.66372785622821
				],
				[
					7.919042531281772,
					63.00803405324054
				],
				[
					8.607654925306118,
					63.696646447264975
				],
				[
					9.296267319330628,
					64.38525884128948
				],
				[
					9.640573516342801,
					64.72956503830174
				],
				[
					9.984879713355136,
					65.07387123531392
				],
				[
					10.673492107379646,
					65.76248362933842
				],
				[
					11.01779830439182,
					66.10678982635068
				],
				[
					11.706410698416327,
					66.45109602336292
				],
				[
					12.050716895428502,
					66.79540222037518
				],
				[
					12.739329289453172,
					67.4840146143997
				],
				[
					13.083635486465345,
					67.82832081141194
				],
				[
					13.42794168347752,
					67.82832081141194
				],
				[
					14.116554077502029,
					68.17262700842412
				],
				[
					14.116554077502029,
					68.51693320543637
				],
				[
					14.116554077502029,
					68.51693320543637
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 287,
			"versionNonce": 1103477483,
			"isDeleted": false,
			"id": "HWoP5EmbX9sZDD1S2Tpeq",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1272.980177946523,
			"y": 488.76058239038866,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.886123940244928,
			"height": 16.182391259575436,
			"seed": 677162539,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.34430619701233506,
					0
				],
				[
					0.34430619701233506,
					-0.3443061970122545
				],
				[
					0.34430619701233506,
					-0.6886123940244686
				],
				[
					0,
					-0.6886123940244686
				],
				[
					-0.3443061970121738,
					-0.6886123940244686
				],
				[
					-1.0329185910366827,
					-0.6886123940244686
				],
				[
					-1.7215309850610303,
					-0.6886123940244686
				],
				[
					-2.4101433790857003,
					-0.3443061970122545
				],
				[
					-2.754449576097874,
					0
				],
				[
					-3.098755773110048,
					0.688612394024509
				],
				[
					-3.098755773110048,
					1.0329185910367635
				],
				[
					-3.443061970122383,
					1.7215309850612321
				],
				[
					-3.443061970122383,
					2.0658371820734462
				],
				[
					-3.443061970122383,
					3.0987557731102098
				],
				[
					-3.443061970122383,
					3.787368167134638
				],
				[
					-3.443061970122383,
					4.475980561159147
				],
				[
					-3.443061970122383,
					5.5088991521959105
				],
				[
					-3.443061970122383,
					5.853205349208165
				],
				[
					-3.443061970122383,
					6.886123940244848
				],
				[
					-3.098755773110048,
					7.230430137257103
				],
				[
					-2.754449576097874,
					8.263348728293867
				],
				[
					-2.0658371820733654,
					8.951961122318375
				],
				[
					-1.3772247880488564,
					9.640573516342803
				],
				[
					-0.6886123940243476,
					10.673492107379566
				],
				[
					0.34430619701233506,
					11.017798304391821
				],
				[
					0.6886123940246701,
					11.362104501404076
				],
				[
					1.032918591036844,
					11.70641069841625
				],
				[
					1.3772247880490178,
					12.39502309244076
				],
				[
					1.7215309850613527,
					12.739329289453012
				],
				[
					1.7215309850613527,
					13.427941683477522
				],
				[
					1.7215309850613527,
					13.772247880489777
				],
				[
					1.3772247880490178,
					14.460860274514205
				],
				[
					1.032918591036844,
					14.805166471526459
				],
				[
					0.34430619701233506,
					15.149472668538714
				],
				[
					0,
					15.149472668538714
				],
				[
					-0.6886123940243476,
					15.149472668538714
				],
				[
					-1.0329185910366827,
					15.149472668538714
				],
				[
					-1.3772247880488564,
					15.149472668538714
				],
				[
					-2.0658371820733654,
					15.493778865550969
				],
				[
					-2.4101433790857003,
					15.493778865550969
				],
				[
					-3.443061970122383,
					15.493778865550969
				],
				[
					-3.7873681671345567,
					15.493778865550969
				],
				[
					-4.131674364146731,
					15.493778865550969
				],
				[
					-4.475980561159066,
					15.493778865550969
				],
				[
					-4.820286758171401,
					15.493778865550969
				],
				[
					-5.164592955183575,
					15.493778865550969
				],
				[
					-5.164592955183575,
					15.493778865550969
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 260,
			"versionNonce": 1924660549,
			"isDeleted": false,
			"id": "_kx1Xm4BpWA-uoxookD5f",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1277.8004647046946,
			"y": 499.7783806947805,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 1.032918591036844,
			"height": 7.91904253128161,
			"seed": 998133451,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.34430619701225446
				],
				[
					0.34430619701233506,
					-0.34430619701225446
				],
				[
					0.6886123940246701,
					0.34430619701225446
				],
				[
					0.6886123940246701,
					0.6886123940244282
				],
				[
					0.6886123940246701,
					1.377224788048937
				],
				[
					1.032918591036844,
					2.065837182073446
				],
				[
					1.032918591036844,
					2.4101433790857003
				],
				[
					1.032918591036844,
					3.0987557731101285
				],
				[
					1.032918591036844,
					3.7873681671346375
				],
				[
					1.032918591036844,
					4.131674364146892
				],
				[
					1.032918591036844,
					4.4759805611591466
				],
				[
					1.032918591036844,
					5.164592955183656
				],
				[
					1.032918591036844,
					5.508899152195829
				],
				[
					1.032918591036844,
					5.853205349208084
				],
				[
					1.032918591036844,
					6.197511546220338
				],
				[
					1.032918591036844,
					6.541817743232593
				],
				[
					1.032918591036844,
					6.886123940244847
				],
				[
					1.032918591036844,
					7.230430137257101
				],
				[
					1.032918591036844,
					7.574736334269356
				],
				[
					1.032918591036844,
					7.574736334269356
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 241,
			"versionNonce": 851781003,
			"isDeleted": false,
			"id": "vEvtY8duk7FTPenmf6I_W",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1282.6207514628659,
			"y": 495.6467063306335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0.00007092366774221256,
			"height": 0.00007092366774221256,
			"seed": 1340703883,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.00007092366774221256,
					0.00007092366774221256
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 254,
			"versionNonce": 598871205,
			"isDeleted": false,
			"id": "0ka52GP_T8DmZbpvLT2x3",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1295.360080752319,
			"y": 489.7935009814254,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 4.820286758171401,
			"height": 11.362104501403993,
			"seed": 442772587,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.34430619701233506,
					0
				],
				[
					-0.6886123940245089,
					0.6886123940244685
				],
				[
					-1.3772247880490178,
					1.7215309850611915
				],
				[
					-2.0658371820735266,
					2.754449576097874
				],
				[
					-2.7544495760980356,
					3.7873681671346375
				],
				[
					-3.7873681671347184,
					6.541817743232593
				],
				[
					-4.131674364147053,
					7.91904253128161
				],
				[
					-4.475980561159227,
					8.607654925306038
				],
				[
					-4.475980561159227,
					9.296267319330548
				],
				[
					-4.475980561159227,
					10.329185910367311
				],
				[
					-4.820286758171401,
					10.673492107379484
				],
				[
					-4.820286758171401,
					11.01779830439174
				],
				[
					-4.820286758171401,
					11.362104501403993
				],
				[
					-4.820286758171401,
					11.362104501403993
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 256,
			"versionNonce": 834550827,
			"isDeleted": false,
			"id": "SGSC7l35Gh1B9OsZy58O0",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1291.228406388172,
			"y": 489.10488858740086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.8532053492082445,
			"height": 12.050716895428502,
			"seed": 264795755,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6886123940246701,
					0.6886123940245089
				],
				[
					1.3772247880490178,
					2.4101433790857003
				],
				[
					1.7215309850613527,
					3.443061970122383
				],
				[
					2.4101433790857003,
					4.4759805611591466
				],
				[
					3.0987557731103705,
					5.853205349208164
				],
				[
					3.4430619701225442,
					7.230430137257101
				],
				[
					3.7873681671347184,
					7.91904253128161
				],
				[
					4.475980561159227,
					8.951961122318293
				],
				[
					4.820286758171401,
					9.640573516342801
				],
				[
					4.820286758171401,
					9.984879713355056
				],
				[
					5.1645929551837355,
					10.673492107379564
				],
				[
					5.508899152196071,
					11.01779830439182
				],
				[
					5.508899152196071,
					11.706410698416247
				],
				[
					5.8532053492082445,
					11.706410698416247
				],
				[
					5.8532053492082445,
					12.050716895428502
				],
				[
					5.8532053492082445,
					12.050716895428502
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 283,
			"versionNonce": 2104700933,
			"isDeleted": false,
			"id": "dHHLUKEvz6X68tletnfSk",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1277.4561585076824,
			"y": 515.9607719543559,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.541817743232431,
			"height": 11.01779830439182,
			"seed": 376299947,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.34430619701225446
				],
				[
					-0.6886123940245089,
					-0.34430619701225446
				],
				[
					-1.0329185910366827,
					-0.34430619701225446
				],
				[
					-1.7215309850611915,
					-0.34430619701225446
				],
				[
					-2.0658371820735266,
					-0.34430619701225446
				],
				[
					-2.754449576097874,
					-0.34430619701225446
				],
				[
					-3.0987557731102093,
					-0.34430619701225446
				],
				[
					-3.443061970122383,
					0
				],
				[
					-3.7873681671345567,
					0.34430619701225446
				],
				[
					-3.7873681671345567,
					0.6886123940245089
				],
				[
					-3.7873681671345567,
					1.3772247880490178
				],
				[
					-3.7873681671345567,
					1.7215309850612721
				],
				[
					-3.7873681671345567,
					2.754449576097955
				],
				[
					-3.0987557731102093,
					3.0987557731102093
				],
				[
					-2.754449576097874,
					3.7873681671347184
				],
				[
					-2.0658371820735266,
					4.4759805611591466
				],
				[
					-1.7215309850611915,
					4.820286758171401
				],
				[
					-1.0329185910366827,
					5.164592955183656
				],
				[
					-0.3443061970121738,
					5.853205349208164
				],
				[
					0,
					6.197511546220419
				],
				[
					1.032918591036844,
					6.886123940244847
				],
				[
					1.3772247880490178,
					7.230430137257101
				],
				[
					1.7215309850611915,
					7.574736334269356
				],
				[
					2.0658371820735266,
					8.263348728293865
				],
				[
					2.4101433790857003,
					8.951961122318373
				],
				[
					2.754449576097874,
					9.296267319330548
				],
				[
					2.754449576097874,
					9.984879713355056
				],
				[
					2.754449576097874,
					10.329185910367311
				],
				[
					2.4101433790857003,
					10.673492107379564
				],
				[
					2.0658371820735266,
					10.673492107379564
				],
				[
					1.3772247880490178,
					10.673492107379564
				],
				[
					1.032918591036844,
					10.673492107379564
				],
				[
					0.3443061970121738,
					10.673492107379564
				],
				[
					-0.3443061970121738,
					10.673492107379564
				],
				[
					-1.0329185910366827,
					10.673492107379564
				],
				[
					-1.7215309850611915,
					10.673492107379564
				],
				[
					-2.0658371820735266,
					10.673492107379564
				],
				[
					-2.4101433790857003,
					10.673492107379564
				],
				[
					-2.754449576097874,
					10.673492107379564
				],
				[
					-3.0987557731102093,
					10.673492107379564
				],
				[
					-3.443061970122383,
					10.673492107379564
				],
				[
					-3.443061970122383,
					10.329185910367311
				],
				[
					-3.443061970122383,
					10.329185910367311
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 278,
			"versionNonce": 714833611,
			"isDeleted": false,
			"id": "pJMl9-dk75y5mR__5KiBE",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1283.3093638568905,
			"y": 523.8798144856374,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 4.820286758171401,
			"height": 5.50889915219591,
			"seed": 795332555,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3443061970121738,
					0
				],
				[
					0.6886123940243476,
					0
				],
				[
					1.0329185910366827,
					0
				],
				[
					1.3772247880490178,
					0
				],
				[
					2.0658371820733654,
					0
				],
				[
					2.754449576097874,
					0.6886123940245089
				],
				[
					3.098755773110048,
					1.0329185910367633
				],
				[
					3.443061970122383,
					1.7215309850611915
				],
				[
					3.443061970122383,
					2.065837182073446
				],
				[
					3.443061970122383,
					2.754449576097955
				],
				[
					3.443061970122383,
					3.0987557731102093
				],
				[
					3.098755773110048,
					3.443061970122464
				],
				[
					2.4101433790857003,
					3.7873681671346375
				],
				[
					2.0658371820733654,
					3.7873681671346375
				],
				[
					1.3772247880490178,
					3.7873681671346375
				],
				[
					1.0329185910366827,
					4.131674364146972
				],
				[
					0.3443061970121738,
					4.4759805611591466
				],
				[
					0,
					4.4759805611591466
				],
				[
					-0.34430619701233506,
					4.4759805611591466
				],
				[
					-0.6886123940246701,
					4.820286758171401
				],
				[
					-1.032918591036844,
					4.820286758171401
				],
				[
					-1.3772247880490178,
					4.4759805611591466
				],
				[
					-1.3772247880490178,
					4.131674364146972
				],
				[
					-1.3772247880490178,
					3.7873681671346375
				],
				[
					-1.032918591036844,
					3.7873681671346375
				],
				[
					-1.032918591036844,
					3.0987557731102093
				],
				[
					-0.6886123940246701,
					3.0987557731102093
				],
				[
					-0.34430619701233506,
					3.0987557731102093
				],
				[
					0,
					3.0987557731102093
				],
				[
					0.6886123940243476,
					3.443061970122464
				],
				[
					1.0329185910366827,
					3.7873681671346375
				],
				[
					1.3772247880490178,
					4.131674364146972
				],
				[
					1.3772247880490178,
					4.4759805611591466
				],
				[
					1.7215309850610303,
					4.820286758171401
				],
				[
					2.0658371820733654,
					5.164592955183656
				],
				[
					2.4101433790857003,
					5.50889915219591
				],
				[
					2.754449576097874,
					5.50889915219591
				],
				[
					2.754449576097874,
					5.50889915219591
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 241,
			"versionNonce": 2113464165,
			"isDeleted": false,
			"id": "LJnPKyNK3Bwu7NmTHHN2x",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1289.851181600123,
			"y": 521.4696711065518,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0.00007092366774221256,
			"height": 0.00007092366774221256,
			"seed": 879634635,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.00007092366774221256,
					0.00007092366774221256
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 316,
			"versionNonce": 670526827,
			"isDeleted": false,
			"id": "PcxIqepnLjIm2Wb0p1mkt",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1296.3929993433558,
			"y": 512.5177099842334,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 8.951961122318455,
			"height": 18.24822844164892,
			"seed": 2099263659,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.34430619701233506
				],
				[
					0,
					0.6886123940245089
				],
				[
					0,
					1.7215309850612721
				],
				[
					0.3443061970123351,
					2.7544495760980356
				],
				[
					0.688612394024509,
					3.7873681671347184
				],
				[
					1.032918591036683,
					5.50889915219591
				],
				[
					1.032918591036683,
					6.541817743232673
				],
				[
					1.377224788049018,
					6.886123940244928
				],
				[
					1.377224788049018,
					7.230430137257182
				],
				[
					1.7215309850611917,
					7.230430137257182
				],
				[
					2.065837182073366,
					7.230430137257182
				],
				[
					2.4101433790857008,
					6.197511546220419
				],
				[
					2.4101433790857008,
					5.1645929551837355
				],
				[
					2.4101433790857008,
					4.131674364146972
				],
				[
					2.754449576098036,
					3.443061970122464
				],
				[
					3.0987557731102098,
					2.410143379085781
				],
				[
					3.0987557731102098,
					1.7215309850612721
				],
				[
					3.4430619701223835,
					0.6886123940245089
				],
				[
					3.4430619701223835,
					0.34430619701233506
				],
				[
					3.787368167134719,
					-0.6886123940244282
				],
				[
					3.787368167134719,
					-1.0329185910366827
				],
				[
					4.1316743641468925,
					-2.0658371820733654
				],
				[
					4.475980561159067,
					-2.754449576097874
				],
				[
					4.475980561159067,
					-3.0987557731101285
				],
				[
					4.8202867581714015,
					-3.443061970122383
				],
				[
					4.8202867581714015,
					-3.0987557731101285
				],
				[
					4.8202867581714015,
					-2.0658371820733654
				],
				[
					4.8202867581714015,
					-1.377224788048937
				],
				[
					4.8202867581714015,
					-0.3443061970121738
				],
				[
					4.8202867581714015,
					0.34430619701233506
				],
				[
					5.164592955183736,
					1.7215309850612721
				],
				[
					5.164592955183736,
					2.410143379085781
				],
				[
					5.164592955183736,
					3.0987557731102093
				],
				[
					5.164592955183736,
					3.7873681671347184
				],
				[
					5.164592955183736,
					4.8202867581714814
				],
				[
					5.164592955183736,
					6.197511546220419
				],
				[
					5.164592955183736,
					7.574736334269437
				],
				[
					5.164592955183736,
					8.951961122318373
				],
				[
					4.8202867581714015,
					9.640573516342883
				],
				[
					4.475980561159067,
					10.673492107379564
				],
				[
					4.1316743641468925,
					11.01779830439182
				],
				[
					3.787368167134719,
					11.706410698416327
				],
				[
					3.4430619701223835,
					12.050716895428582
				],
				[
					3.4430619701223835,
					12.395023092440837
				],
				[
					2.754449576098036,
					12.73932928945301
				],
				[
					2.4101433790857008,
					13.083635486465266
				],
				[
					2.065837182073366,
					13.083635486465266
				],
				[
					1.7215309850611917,
					13.083635486465266
				],
				[
					1.377224788049018,
					13.083635486465266
				],
				[
					0.688612394024509,
					13.083635486465266
				],
				[
					0.3443061970123351,
					12.73932928945301
				],
				[
					-0.3443061970123351,
					12.395023092440837
				],
				[
					-0.688612394024509,
					12.050716895428582
				],
				[
					-1.377224788049018,
					11.706410698416327
				],
				[
					-1.032918591036683,
					11.706410698416327
				],
				[
					-0.688612394024509,
					11.362104501404074
				],
				[
					-0.3443061970123351,
					11.01779830439182
				],
				[
					0,
					11.01779830439182
				],
				[
					0.688612394024509,
					11.01779830439182
				],
				[
					1.032918591036683,
					11.01779830439182
				],
				[
					1.7215309850611917,
					11.706410698416327
				],
				[
					2.065837182073366,
					12.050716895428582
				],
				[
					2.4101433790857008,
					12.050716895428582
				],
				[
					3.0987557731102098,
					12.73932928945301
				],
				[
					3.4430619701223835,
					13.083635486465266
				],
				[
					3.787368167134719,
					13.083635486465266
				],
				[
					4.475980561159067,
					13.772247880489774
				],
				[
					4.8202867581714015,
					13.772247880489774
				],
				[
					5.164592955183736,
					14.116554077502029
				],
				[
					5.5088991521959105,
					14.116554077502029
				],
				[
					5.853205349208085,
					14.460860274514284
				],
				[
					6.1975115462204196,
					14.460860274514284
				],
				[
					6.886123940244767,
					14.460860274514284
				],
				[
					7.230430137257103,
					14.805166471526537
				],
				[
					7.574736334269438,
					14.805166471526537
				],
				[
					7.574736334269438,
					14.805166471526537
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 277,
			"versionNonce": 126923461,
			"isDeleted": false,
			"id": "R57_t1ONHxA6ErdgJ0EZt",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1284.6865886449395,
			"y": 540.062205745213,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.541817743232593,
			"height": 11.362104501403993,
			"seed": 1199851883,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.3772247880490178,
					-0.34430619701225446
				],
				[
					-2.065837182073688,
					-0.34430619701225446
				],
				[
					-2.7544495760980356,
					-0.34430619701225446
				],
				[
					-3.4430619701225442,
					-0.34430619701225446
				],
				[
					-3.7873681671347184,
					0
				],
				[
					-4.475980561159388,
					0.3443061970121738
				],
				[
					-4.820286758171562,
					1.0329185910366827
				],
				[
					-4.820286758171562,
					1.377224788048937
				],
				[
					-4.820286758171562,
					2.065837182073446
				],
				[
					-4.820286758171562,
					2.4101433790857003
				],
				[
					-4.131674364147053,
					3.0987557731101285
				],
				[
					-3.7873681671347184,
					3.7873681671346375
				],
				[
					-3.0987557731103705,
					4.131674364146892
				],
				[
					-2.7544495760980356,
					4.4759805611591466
				],
				[
					-2.065837182073688,
					5.164592955183575
				],
				[
					-1.032918591036844,
					5.853205349208084
				],
				[
					0,
					6.197511546220338
				],
				[
					0.6886123940243476,
					6.886123940244847
				],
				[
					1.3772247880488564,
					6.886123940244847
				],
				[
					1.7215309850610303,
					7.574736334269275
				],
				[
					1.7215309850610303,
					8.263348728293783
				],
				[
					1.7215309850610303,
					8.607654925306038
				],
				[
					1.7215309850610303,
					8.951961122318293
				],
				[
					1.7215309850610303,
					9.640573516342801
				],
				[
					1.3772247880488564,
					9.984879713354976
				],
				[
					0.6886123940243476,
					10.329185910367311
				],
				[
					-0.34430619701233506,
					10.673492107379484
				],
				[
					-0.6886123940246701,
					11.01779830439174
				],
				[
					-1.7215309850613527,
					11.01779830439174
				],
				[
					-2.065837182073688,
					11.01779830439174
				],
				[
					-2.4101433790858615,
					11.01779830439174
				],
				[
					-2.7544495760980356,
					11.01779830439174
				],
				[
					-3.0987557731103705,
					11.01779830439174
				],
				[
					-3.4430619701225442,
					11.01779830439174
				],
				[
					-3.7873681671347184,
					10.673492107379484
				],
				[
					-4.131674364147053,
					10.673492107379484
				],
				[
					-4.131674364147053,
					10.673492107379484
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 268,
			"versionNonce": 2099021835,
			"isDeleted": false,
			"id": "t81xfTrYOB4vW6smfiNw5",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1289.851181600123,
			"y": 549.3584730645434,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 2.754449576097874,
			"height": 6.197511546220338,
			"seed": 196293579,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.34430619701233506,
					0
				],
				[
					0.6886123940246701,
					0
				],
				[
					1.032918591036844,
					0.34430619701225446
				],
				[
					1.3772247880490178,
					0.6886123940244282
				],
				[
					1.3772247880490178,
					1.377224788048937
				],
				[
					1.3772247880490178,
					1.7215309850611915
				],
				[
					1.3772247880490178,
					2.065837182073446
				],
				[
					1.032918591036844,
					2.065837182073446
				],
				[
					0.34430619701233506,
					2.065837182073446
				],
				[
					0,
					2.4101433790857003
				],
				[
					-0.6886123940243476,
					2.4101433790857003
				],
				[
					-1.0329185910366827,
					2.4101433790857003
				],
				[
					-1.0329185910366827,
					3.0987557731101285
				],
				[
					-1.0329185910366827,
					3.443061970122464
				],
				[
					-0.6886123940243476,
					3.7873681671346375
				],
				[
					0,
					4.131674364146892
				],
				[
					0.34430619701233506,
					4.4759805611591466
				],
				[
					0.6886123940246701,
					4.820286758171401
				],
				[
					1.032918591036844,
					4.820286758171401
				],
				[
					1.032918591036844,
					5.164592955183656
				],
				[
					1.032918591036844,
					5.50889915219591
				],
				[
					0.6886123940246701,
					6.197511546220338
				],
				[
					0,
					6.197511546220338
				],
				[
					-0.34430619701201254,
					6.197511546220338
				],
				[
					-0.6886123940243476,
					6.197511546220338
				],
				[
					-1.0329185910366827,
					6.197511546220338
				],
				[
					-1.3772247880488564,
					6.197511546220338
				],
				[
					-1.3772247880488564,
					6.197511546220338
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 243,
			"versionNonce": 1457000997,
			"isDeleted": false,
			"id": "f0L8RawhY0EKVHD4HESYU",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1296.0486931463433,
			"y": 542.4723491242986,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0.34430619701233506,
			"height": 0,
			"seed": 283782795,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.34430619701233506,
					0
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
			"type": "freedraw",
			"version": 287,
			"versionNonce": 805654187,
			"isDeleted": false,
			"id": "EnU0HwsTt85DV3zV_ugqT",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1302.9348170865883,
			"y": 538.3406747601516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 9.296267319330628,
			"height": 12.395023092440756,
			"seed": 1831772069,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3443061970121738,
					0
				],
				[
					0.6886123940245089,
					0
				],
				[
					1.7215309850611915,
					0
				],
				[
					2.754449576097874,
					0
				],
				[
					3.0987557731102093,
					0
				],
				[
					3.7873681671347184,
					0
				],
				[
					4.475980561159227,
					0
				],
				[
					4.820286758171401,
					0
				],
				[
					5.164592955183575,
					0
				],
				[
					5.50889915219591,
					0.34430619701225446
				],
				[
					5.8532053492082445,
					0.34430619701225446
				],
				[
					5.50889915219591,
					0.6886123940245089
				],
				[
					4.475980561159227,
					1.3772247880490178
				],
				[
					3.4430619701225442,
					2.065837182073446
				],
				[
					2.4101433790857003,
					2.754449576097955
				],
				[
					1.3772247880490178,
					3.443061970122464
				],
				[
					0.6886123940245089,
					4.131674364146972
				],
				[
					0,
					5.164592955183656
				],
				[
					-0.3443061970121738,
					5.50889915219591
				],
				[
					-0.6886123940245089,
					6.541817743232673
				],
				[
					-1.0329185910366827,
					6.886123940244847
				],
				[
					-1.0329185910366827,
					7.91904253128161
				],
				[
					-1.3772247880488564,
					8.263348728293865
				],
				[
					-1.3772247880488564,
					8.951961122318373
				],
				[
					-1.7215309850611915,
					9.640573516342883
				],
				[
					-1.7215309850611915,
					9.984879713355056
				],
				[
					-2.0658371820735266,
					10.329185910367311
				],
				[
					-2.4101433790857003,
					10.673492107379564
				],
				[
					-2.4101433790857003,
					11.01779830439182
				],
				[
					-3.0987557731102093,
					11.362104501404074
				],
				[
					-3.0987557731102093,
					11.706410698416247
				],
				[
					-3.443061970122383,
					12.050716895428582
				],
				[
					-3.443061970122383,
					12.395023092440756
				],
				[
					-3.0987557731102093,
					12.395023092440756
				],
				[
					-2.754449576097874,
					12.395023092440756
				],
				[
					-2.4101433790857003,
					12.395023092440756
				],
				[
					-1.3772247880488564,
					12.395023092440756
				],
				[
					-0.6886123940245089,
					12.395023092440756
				],
				[
					0,
					12.395023092440756
				],
				[
					0.6886123940245089,
					12.395023092440756
				],
				[
					1.032918591036844,
					12.395023092440756
				],
				[
					1.7215309850611915,
					12.395023092440756
				],
				[
					2.0658371820735266,
					12.395023092440756
				],
				[
					2.754449576097874,
					12.395023092440756
				],
				[
					3.0987557731102093,
					12.395023092440756
				],
				[
					3.4430619701225442,
					12.395023092440756
				],
				[
					3.7873681671347184,
					12.395023092440756
				],
				[
					4.131674364146892,
					12.395023092440756
				],
				[
					4.131674364146892,
					12.395023092440756
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 250,
			"versionNonce": 951879045,
			"isDeleted": false,
			"id": "w4bts8xmox-gEEZAeU1_T",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1304.3120418746373,
			"y": 538.3406747601516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.8532053492082445,
			"height": 0,
			"seed": 433727429,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.032918591036844,
					0
				],
				[
					-1.7215309850611915,
					0
				],
				[
					-2.4101433790857003,
					0
				],
				[
					-3.0987557731102093,
					0
				],
				[
					-3.7873681671347184,
					0
				],
				[
					-4.131674364146892,
					0
				],
				[
					-4.475980561159227,
					0
				],
				[
					-4.820286758171401,
					0
				],
				[
					-5.164592955183575,
					0
				],
				[
					-5.50889915219591,
					0
				],
				[
					-5.8532053492082445,
					0
				],
				[
					-5.8532053492082445,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 252,
			"versionNonce": 593248587,
			"isDeleted": false,
			"id": "14DfZNie2Imu6YQ2pFr6r",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1300.1803675104904,
			"y": 543.8495739123475,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.886123940244766,
			"height": 0,
			"seed": 850967301,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6886123940243476,
					0
				],
				[
					1.3772247880490178,
					0
				],
				[
					1.7215309850611915,
					0
				],
				[
					2.754449576097874,
					0
				],
				[
					3.098755773110048,
					0
				],
				[
					3.7873681671347184,
					0
				],
				[
					4.131674364146892,
					0
				],
				[
					4.820286758171401,
					0
				],
				[
					5.164592955183575,
					0
				],
				[
					5.508899152195748,
					0
				],
				[
					5.853205349208084,
					0
				],
				[
					6.541817743232593,
					0
				],
				[
					6.886123940244766,
					0
				],
				[
					6.886123940244766,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 309,
			"versionNonce": 8096997,
			"isDeleted": false,
			"id": "dzoi4jbzTAe9P700IZKWS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1306.7221852537232,
			"y": 490.1378071784376,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.574736334269275,
			"height": 63.00803405324051,
			"seed": 1793036549,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3443061970121738,
					0
				],
				[
					0.6886123940245089,
					0.34430619701225446
				],
				[
					1.0329185910366827,
					1.3772247880489774
				],
				[
					1.7215309850611915,
					2.7544495760979952
				],
				[
					2.0658371820735266,
					3.4430619701224234
				],
				[
					2.4101433790857003,
					4.4759805611591865
				],
				[
					2.754449576097874,
					5.853205349208124
				],
				[
					3.443061970122383,
					8.607654925306079
				],
				[
					3.7873681671345567,
					9.984879713355097
				],
				[
					4.131674364146892,
					11.706410698416288
				],
				[
					4.820286758171401,
					13.42794168347748
				],
				[
					5.164592955183575,
					15.149472668538671
				],
				[
					5.50889915219591,
					17.215309850612197
				],
				[
					5.853205349208084,
					18.592534638661135
				],
				[
					5.853205349208084,
					19.625453229697897
				],
				[
					6.197511546220257,
					21.002678017746835
				],
				[
					6.541817743232593,
					23.068515199820283
				],
				[
					6.886123940244928,
					24.101433790857044
				],
				[
					6.886123940244928,
					25.478658578905982
				],
				[
					6.886123940244928,
					26.855883366955
				],
				[
					7.230430137257101,
					28.233108155003936
				],
				[
					7.230430137257101,
					29.610332943052953
				],
				[
					7.574736334269275,
					30.643251534089636
				],
				[
					7.574736334269275,
					32.020476322138656
				],
				[
					7.574736334269275,
					33.05339491317534
				],
				[
					7.574736334269275,
					34.43061970122435
				],
				[
					7.574736334269275,
					35.80784448927329
				],
				[
					7.574736334269275,
					36.4964568832978
				],
				[
					7.574736334269275,
					37.18506927732231
				],
				[
					7.574736334269275,
					38.56229406537125
				],
				[
					7.574736334269275,
					39.59521265640801
				],
				[
					7.574736334269275,
					40.62813124744469
				],
				[
					7.574736334269275,
					41.66104983848145
				],
				[
					7.574736334269275,
					42.69396842951822
				],
				[
					7.574736334269275,
					44.071193217567156
				],
				[
					7.230430137257101,
					45.10411180860392
				],
				[
					7.230430137257101,
					46.1370303996406
				],
				[
					7.230430137257101,
					47.16994899067737
				],
				[
					6.886123940244928,
					47.858561384701794
				],
				[
					6.886123940244928,
					48.547173778726304
				],
				[
					6.886123940244928,
					49.580092369763065
				],
				[
					6.886123940244928,
					50.2687047637875
				],
				[
					6.886123940244928,
					50.95731715781201
				],
				[
					6.886123940244928,
					51.30162335482426
				],
				[
					6.886123940244928,
					51.64592955183651
				],
				[
					6.886123940244928,
					52.67884814287319
				],
				[
					6.886123940244928,
					53.02315433988545
				],
				[
					6.886123940244928,
					53.71176673390996
				],
				[
					6.541817743232593,
					54.400379127934464
				],
				[
					6.197511546220257,
					55.43329771897115
				],
				[
					6.197511546220257,
					55.777603915983406
				],
				[
					6.197511546220257,
					56.466216310007916
				],
				[
					5.853205349208084,
					56.81052250702017
				],
				[
					5.853205349208084,
					57.15482870403242
				],
				[
					5.164592955183575,
					57.84344109805693
				],
				[
					5.164592955183575,
					58.1877472950691
				],
				[
					4.820286758171401,
					58.87635968909361
				],
				[
					4.820286758171401,
					59.22066588610587
				],
				[
					4.475980561159227,
					59.56497208311812
				],
				[
					4.131674364146892,
					60.25358447714263
				],
				[
					3.7873681671345567,
					60.597890674154804
				],
				[
					3.443061970122383,
					60.942196871167056
				],
				[
					3.443061970122383,
					61.286503068179314
				],
				[
					3.443061970122383,
					61.975115462203824
				],
				[
					3.0987557731102093,
					62.319421659216
				],
				[
					3.0987557731102093,
					62.663727856228334
				],
				[
					2.754449576097874,
					62.663727856228334
				],
				[
					2.754449576097874,
					63.00803405324051
				],
				[
					2.4101433790857003,
					63.00803405324051
				],
				[
					2.4101433790857003,
					63.00803405324051
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "rectangle",
			"version": 1100,
			"versionNonce": 8118251,
			"isDeleted": false,
			"id": "8dU7Dri40eymffhDKBlJh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 994.9533203530472,
			"y": 630.5651320494369,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 421.05296228456814,
			"height": 250.35020076370063,
			"seed": 517728011,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "BeG12LlljrdmLA3OWJfrL",
					"type": "arrow"
				}
			],
			"updated": 1702760726445,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 652,
			"versionNonce": 1034070085,
			"isDeleted": false,
			"id": "uy7KIduA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1168.5208511834421,
			"y": 632.9706381431429,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 104.47015380859375,
			"height": 33.216383758057106,
			"seed": 1082183083,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"fontSize": 26.573107006445685,
			"fontFamily": 1,
			"text": "Shearing",
			"rawText": "Shearing",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Shearing",
			"lineHeight": 1.25,
			"baseline": 23
		},
		{
			"type": "freedraw",
			"version": 530,
			"versionNonce": 1634642571,
			"isDeleted": false,
			"id": "ti74VjswQ5QaLN6KeBx3H",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1030.0348562655868,
			"y": 701.8926309167292,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffd43b",
			"width": 7.105046635249093,
			"height": 9.591812957586214,
			"seed": 907010123,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.3552523317624504
				],
				[
					-0.35525233176234555,
					0
				],
				[
					-0.710504663524859,
					0
				],
				[
					-0.710504663524859,
					-0.7105046635249008
				],
				[
					-0.35525233176234555,
					-1.4210093270498123
				],
				[
					0,
					-1.4210093270498123
				],
				[
					0.3552523317625134,
					-1.7762616588122626
				],
				[
					0.7105046635250268,
					-2.131513990574713
				],
				[
					1.0657569952873722,
					-2.131513990574713
				],
				[
					2.1315139905747444,
					-2.131513990574713
				],
				[
					2.8420186540996037,
					-1.4210093270498123
				],
				[
					3.5525233176246305,
					-1.0657569952873513
				],
				[
					3.907775649386976,
					-0.3552523317624504
				],
				[
					4.263027981149489,
					0
				],
				[
					4.263027981149489,
					0.3552523317624504
				],
				[
					4.263027981149489,
					1.0657569952873513
				],
				[
					3.907775649386976,
					1.7762616588122626
				],
				[
					2.8420186540996037,
					1.7762616588122626
				],
				[
					2.1315139905747444,
					1.7762616588122626
				],
				[
					1.4210093270498858,
					2.131513990574713
				],
				[
					1.0657569952873722,
					2.131513990574713
				],
				[
					0.3552523317625134,
					2.131513990574713
				],
				[
					0,
					1.7762616588122626
				],
				[
					-0.710504663524859,
					1.4210093270498123
				],
				[
					-1.0657569952872046,
					0.7105046635249008
				],
				[
					-1.421009327049718,
					0
				],
				[
					-1.421009327049718,
					-1.0657569952873513
				],
				[
					-1.421009327049718,
					-1.7762616588122626
				],
				[
					-1.421009327049718,
					-2.4867663223371634
				],
				[
					-1.421009327049718,
					-2.842018654099614
				],
				[
					-0.710504663524859,
					-3.1972709858620645
				],
				[
					-0.35525233176234555,
					-3.1972709858620645
				],
				[
					0.3552523317625134,
					-3.1972709858620645
				],
				[
					1.0657569952873722,
					-3.1972709858620645
				],
				[
					2.1315139905747444,
					-3.1972709858620645
				],
				[
					2.486766322337258,
					-2.842018654099614
				],
				[
					2.8420186540996037,
					-1.7762616588122626
				],
				[
					3.1972709858621173,
					-0.7105046635249008
				],
				[
					3.1972709858621173,
					0.7105046635249008
				],
				[
					2.8420186540996037,
					1.7762616588122626
				],
				[
					2.1315139905747444,
					3.5525233176245252
				],
				[
					1.4210093270498858,
					4.618280312911876
				],
				[
					0.3552523317625134,
					5.684037308199238
				],
				[
					-0.35525233176234555,
					6.039289639961689
				],
				[
					-1.0657569952872046,
					6.039289639961689
				],
				[
					-1.421009327049718,
					6.039289639961689
				],
				[
					-1.7762616588122313,
					5.328784976436777
				],
				[
					-2.131513990574577,
					4.618280312911876
				],
				[
					-2.8420186540996037,
					3.1972709858620645
				],
				[
					-2.8420186540996037,
					2.131513990574713
				],
				[
					-2.8420186540996037,
					1.4210093270498123
				],
				[
					-2.8420186540996037,
					0
				],
				[
					-2.4867663223370906,
					-1.4210093270498123
				],
				[
					-2.131513990574577,
					-2.131513990574713
				],
				[
					-1.421009327049718,
					-3.1972709858620645
				],
				[
					-0.710504663524859,
					-3.5525233176245252
				],
				[
					0,
					-3.5525233176245252
				],
				[
					0.3552523317625134,
					-3.5525233176245252
				],
				[
					1.4210093270498858,
					-3.1972709858620645
				],
				[
					2.1315139905747444,
					-2.131513990574713
				],
				[
					2.1315139905747444,
					-1.4210093270498123
				],
				[
					2.486766322337258,
					-0.3552523317624504
				],
				[
					2.486766322337258,
					0.7105046635249008
				],
				[
					2.486766322337258,
					1.4210093270498123
				],
				[
					2.486766322337258,
					1.7762616588122626
				],
				[
					1.7762616588122313,
					2.131513990574713
				],
				[
					1.4210093270498858,
					2.131513990574713
				],
				[
					1.0657569952873722,
					2.131513990574713
				],
				[
					0.7105046635250268,
					2.131513990574713
				],
				[
					0.7105046635250268,
					1.7762616588122626
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
			"type": "freedraw",
			"version": 523,
			"versionNonce": 839866277,
			"isDeleted": false,
			"id": "WfkQ93zsEBX-BQ4XsN6Tc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1047.0869681901845,
			"y": 701.1821262532044,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 63.23491505371647,
			"height": 1.7762616588122626,
			"seed": 1499700971,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3552523317623455,
					0
				],
				[
					0.7105046635248589,
					0
				],
				[
					1.776261658812231,
					0
				],
				[
					2.8420186540996033,
					0
				],
				[
					3.9077756493869757,
					0
				],
				[
					5.684037308199207,
					0
				],
				[
					6.749794303486579,
					0
				],
				[
					8.52605596229881,
					0
				],
				[
					9.947065289348696,
					0
				],
				[
					11.01282228463607,
					0
				],
				[
					12.078579279923272,
					0
				],
				[
					13.499588606973157,
					0
				],
				[
					14.56534560226053,
					0
				],
				[
					15.986354929310247,
					0.35525233176245036
				],
				[
					17.407364256360133,
					0.35525233176245036
				],
				[
					18.473121251647505,
					0.35525233176245036
				],
				[
					19.894130578697226,
					0.35525233176245036
				],
				[
					20.959887573984595,
					0.35525233176245036
				],
				[
					22.02564456927197,
					0.35525233176245036
				],
				[
					23.09140156455934,
					0.35525233176245036
				],
				[
					24.15715855984671,
					0
				],
				[
					25.933420218658945,
					0
				],
				[
					27.35442954570883,
					0
				],
				[
					29.13069120452106,
					-0.7105046635249113
				],
				[
					30.906952863333295,
					-0.7105046635249113
				],
				[
					33.038466853908034,
					-1.0657569952873616
				],
				[
					34.45947618095775,
					-1.0657569952873616
				],
				[
					36.5909901715325,
					-1.421009327049812
				],
				[
					38.011999498582384,
					-1.421009327049812
				],
				[
					39.4330088256321,
					-1.421009327049812
				],
				[
					40.14351348915713,
					-1.421009327049812
				],
				[
					40.85401815268199,
					-1.421009327049812
				],
				[
					41.91977514796936,
					-1.421009327049812
				],
				[
					43.34078447501908,
					-1.421009327049812
				],
				[
					44.05128913854394,
					-1.421009327049812
				],
				[
					44.761793802068965,
					-1.421009327049812
				],
				[
					45.82755079735633,
					-1.421009327049812
				],
				[
					46.538055460881196,
					-1.421009327049812
				],
				[
					47.959064787931084,
					-1.421009327049812
				],
				[
					48.66956945145594,
					-1.421009327049812
				],
				[
					49.735326446743315,
					-1.421009327049812
				],
				[
					50.44583111026817,
					-1.421009327049812
				],
				[
					51.15633577379303,
					-1.421009327049812
				],
				[
					51.86684043731789,
					-1.421009327049812
				],
				[
					52.222092769080405,
					-1.421009327049812
				],
				[
					52.57734510084291,
					-1.0657569952873616
				],
				[
					53.28784976436777,
					-1.0657569952873616
				],
				[
					53.99835442789263,
					-1.0657569952873616
				],
				[
					54.35360675965515,
					-1.0657569952873616
				],
				[
					54.70885909141766,
					-0.7105046635249113
				],
				[
					55.41936375494252,
					-0.7105046635249113
				],
				[
					56.12986841846738,
					-0.35525233176245036
				],
				[
					56.48512075022989,
					-0.35525233176245036
				],
				[
					57.55087774551726,
					-0.35525233176245036
				],
				[
					58.26138240904212,
					-0.35525233176245036
				],
				[
					58.97188707256698,
					-0.35525233176245036
				],
				[
					59.32713940432949,
					-0.35525233176245036
				],
				[
					60.392896399616866,
					-0.35525233176245036
				],
				[
					60.74814873137921,
					-0.35525233176245036
				],
				[
					61.45865339490423,
					-0.35525233176245036
				],
				[
					61.81390572666659,
					-0.35525233176245036
				],
				[
					62.52441039019161,
					-0.35525233176245036
				],
				[
					62.87966272195395,
					-0.35525233176245036
				],
				[
					63.23491505371647,
					-0.35525233176245036
				],
				[
					63.23491505371647,
					-0.35525233176245036
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 497,
			"versionNonce": 988750123,
			"isDeleted": false,
			"id": "P7KZShlsp1WQ1ym72_r-5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1110.6771355756632,
			"y": 689.1035469732811,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 15.275850265785557,
			"height": 20.60463524222222,
			"seed": 1694927243,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.35525233176246096
				],
				[
					0,
					0.7105046635249114
				],
				[
					0,
					1.4210093270498123
				],
				[
					0,
					2.131513990574713
				],
				[
					0.35525233176251336,
					2.486766322337174
				],
				[
					1.0657569952873722,
					3.5525233176245257
				],
				[
					1.776261658812399,
					4.618280312911877
				],
				[
					2.8420186540996033,
					5.684037308199239
				],
				[
					3.55252331762463,
					6.74979430348659
				],
				[
					3.9077756493869757,
					7.105046635249051
				],
				[
					4.6182803129120025,
					8.170803630536403
				],
				[
					5.684037308199375,
					8.881308294061302
				],
				[
					7.105046635249093,
					9.947065289348664
				],
				[
					7.815551298774119,
					10.302317621111115
				],
				[
					8.526055962298978,
					11.012822284636016
				],
				[
					9.591812957586184,
					11.723326948160928
				],
				[
					10.302317621111209,
					12.433831611685829
				],
				[
					11.368074616398582,
					13.49958860697318
				],
				[
					12.07857927992344,
					14.21009327049809
				],
				[
					12.07857927992344,
					14.920597934022991
				],
				[
					12.433831611685953,
					15.275850265785442
				],
				[
					12.433831611685953,
					15.631102597547894
				],
				[
					11.723326948160928,
					15.986354929310345
				],
				[
					10.302317621111209,
					16.696859592835253
				],
				[
					8.170803630536465,
					17.052111924597703
				],
				[
					6.03928963996172,
					17.407364256360154
				],
				[
					3.55252331762463,
					18.11786891988506
				],
				[
					2.1315139905747444,
					18.47312125164752
				],
				[
					0.35525233176251336,
					18.828373583409967
				],
				[
					-0.3552523317623455,
					18.828373583409967
				],
				[
					-1.4210093270497177,
					19.183625915172417
				],
				[
					-1.776261658812231,
					19.183625915172417
				],
				[
					-2.1315139905745766,
					19.538878246934868
				],
				[
					-2.48676632233709,
					19.538878246934868
				],
				[
					-2.48676632233709,
					19.894130578697318
				],
				[
					-2.8420186540996033,
					19.894130578697318
				],
				[
					-2.8420186540996033,
					20.24938291045977
				],
				[
					-2.8420186540996033,
					20.60463524222222
				],
				[
					-2.48676632233709,
					20.60463524222222
				],
				[
					-2.48676632233709,
					20.60463524222222
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 490,
			"versionNonce": 133110533,
			"isDeleted": false,
			"id": "2QEmIgufBDGKsecQJd16g",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1003.4103011441604,
			"y": 720.9295690028428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.352541930473584,
			"height": 17.08199936003192,
			"seed": 1580408875,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.1596448538320757
				],
				[
					-0.1596448538320914,
					0.4789345614962218
				],
				[
					-0.4789345614961903,
					0.7982242691603733
				],
				[
					-0.6385794153282818,
					1.2771588306565949
				],
				[
					-0.9578691229924645,
					1.9157382459848873
				],
				[
					-1.2771588306565635,
					2.8736073689773365
				],
				[
					-1.5964485383207463,
					3.83147649196978
				],
				[
					-1.7560933921528377,
					4.310411053466002
				],
				[
					-1.915738245984929,
					5.10863532262637
				],
				[
					-2.235027953649028,
					6.066504445618813
				],
				[
					-2.235027953649028,
					6.8647287147791864
				],
				[
					-2.394672807481119,
					7.82259783777163
				],
				[
					-2.394672807481119,
					8.461177253099928
				],
				[
					-2.394672807481119,
					9.259401522260296
				],
				[
					-2.554317661313211,
					10.21727064525274
				],
				[
					-2.554317661313211,
					11.175139768245183
				],
				[
					-2.554317661313211,
					11.81371918357348
				],
				[
					-2.554317661313211,
					12.452298598901779
				],
				[
					-2.394672807481119,
					13.090878014230077
				],
				[
					-2.235027953649028,
					13.729457429558368
				],
				[
					-2.0753830998169365,
					14.20839199105459
				],
				[
					-1.7560933921528377,
					14.687326552550811
				],
				[
					-1.5964485383207463,
					15.006616260214964
				],
				[
					-1.2771588306565635,
					15.325905967879114
				],
				[
					-0.9578691229924645,
					15.804840529375335
				],
				[
					-0.7982242691603731,
					16.124130237039477
				],
				[
					-0.4789345614961903,
					16.603064798535698
				],
				[
					0,
					16.92235450619985
				],
				[
					0.1596448538320914,
					16.92235450619985
				],
				[
					0.3192897076641828,
					17.08199936003192
				],
				[
					0.4789345614961903,
					17.08199936003192
				],
				[
					0.6385794153282818,
					17.08199936003192
				],
				[
					0.7982242691603731,
					17.08199936003192
				],
				[
					0.7982242691603731,
					16.92235450619985
				],
				[
					0.7982242691603731,
					16.76270965236778
				],
				[
					0.7982242691603731,
					16.76270965236778
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 469,
			"versionNonce": 107463627,
			"isDeleted": false,
			"id": "jab94Q-MgcXyAtFMYvhAT",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1010.1153850051076,
			"y": 724.7610454948126,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.9911213458019503,
			"height": 9.09975666842822,
			"seed": 1054073547,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.1596448538320757
				],
				[
					-0.31928970766418285,
					0.3192897076641461
				],
				[
					-0.7982242691604572,
					0.9578691229924436
				],
				[
					-1.5964485383207465,
					1.5964485383207412
				],
				[
					-2.2350279536491118,
					2.554317661313185
				],
				[
					-3.192897076641493,
					4.789345614962219
				],
				[
					-3.671831638137767,
					6.066504445618813
				],
				[
					-3.8314764919698585,
					6.864728714779181
				],
				[
					-3.9911213458019503,
					7.6629529839395545
				],
				[
					-3.9911213458019503,
					8.141887545435777
				],
				[
					-3.9911213458019503,
					8.780466960764073
				],
				[
					-3.9911213458019503,
					8.940111814596145
				],
				[
					-3.9911213458019503,
					8.620822106931998
				],
				[
					-3.9911213458019503,
					8.461177253099923
				],
				[
					-3.9911213458019503,
					8.461177253099923
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 477,
			"versionNonce": 1203728997,
			"isDeleted": false,
			"id": "wq8PY4glSyYETIerzUsfL",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1006.6031982208019,
			"y": 724.4417557871484,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.075383099817021,
			"height": 9.259401522260296,
			"seed": 1602441579,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.15964485383207572
				],
				[
					0,
					0.31928970766415143
				],
				[
					0,
					0.7982242691603734
				],
				[
					0,
					1.1175139768245195
				],
				[
					0.15964485383209143,
					1.756093392152817
				],
				[
					0.31928970766418285,
					2.8736073689773365
				],
				[
					0.7982242691602894,
					3.8314764919697804
				],
				[
					0.7982242691602894,
					4.9489904687943005
				],
				[
					1.1175139768244724,
					5.7472147379546685
				],
				[
					1.1175139768244724,
					6.385794153282966
				],
				[
					1.1175139768244724,
					6.705083860947111
				],
				[
					1.2771588306565638,
					7.024373568611264
				],
				[
					1.4368036844886551,
					7.343663276275409
				],
				[
					1.4368036844886551,
					7.503308130107485
				],
				[
					1.5964485383207467,
					7.822597837771631
				],
				[
					1.5964485383207467,
					8.141887545435782
				],
				[
					1.5964485383207467,
					8.46117725309993
				],
				[
					1.756093392152838,
					8.780466960764075
				],
				[
					1.756093392152838,
					9.099756668428226
				],
				[
					1.756093392152838,
					9.259401522260296
				],
				[
					1.9157382459849295,
					9.099756668428226
				],
				[
					2.075383099817021,
					8.94011181459615
				],
				[
					2.075383099817021,
					8.94011181459615
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 463,
			"versionNonce": 737350251,
			"isDeleted": false,
			"id": "Gq__pLd9NOC3FmVGrJye0",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1012.8293475202527,
			"y": 731.6257742095918,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.436803684488655,
			"height": 3.1928970766414877,
			"seed": 562818059,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.3192897076641514
				],
				[
					-0.31928970766418285,
					1.1175139768245195
				],
				[
					-0.6385794153283657,
					1.5964485383207412
				],
				[
					-0.9578691229923807,
					2.235027953649039
				],
				[
					-1.2771588306565638,
					2.8736073689773365
				],
				[
					-1.436803684488655,
					3.0332522228094065
				],
				[
					-1.436803684488655,
					3.1928970766414877
				],
				[
					-1.1175139768244722,
					3.0332522228094065
				],
				[
					-1.1175139768244722,
					3.0332522228094065
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 537,
			"versionNonce": 239984069,
			"isDeleted": false,
			"id": "7vIZu_Rz7BXmZZDSe4PRE",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1017.6186931352147,
			"y": 722.8453072488278,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.864728714779259,
			"height": 18.039868483024364,
			"seed": 1491612331,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.3192897076641514
				],
				[
					0,
					0.7982242691603733
				],
				[
					0,
					1.2771588306565949
				],
				[
					0,
					2.8736073689773365
				],
				[
					0,
					3.352541930473558
				],
				[
					0.31928970766418274,
					4.470055907298078
				],
				[
					0.6385794153281977,
					5.268280176458446
				],
				[
					1.2771588306565633,
					6.226149299450889
				],
				[
					1.7560933921528374,
					6.385794153282965
				],
				[
					2.0753830998168525,
					6.385794153282965
				],
				[
					2.5543176613131267,
					5.906859591786742
				],
				[
					2.8736073689773094,
					5.268280176458446
				],
				[
					3.192897076641492,
					4.470055907298078
				],
				[
					3.3525419304735835,
					3.5121867843056336
				],
				[
					3.512186784305675,
					2.8736073689773365
				],
				[
					3.6718316381375984,
					2.235027953649039
				],
				[
					3.8314764919696898,
					1.9157382459848926
				],
				[
					4.150766199633873,
					1.4368036844886707
				],
				[
					4.310411053465964,
					0.9578691229924489
				],
				[
					4.629700761130146,
					0.6385794153282974
				],
				[
					4.7893456149622375,
					0.3192897076641514
				],
				[
					4.94899046879433,
					0.1596448538320757
				],
				[
					4.94899046879433,
					0
				],
				[
					4.94899046879433,
					-0.15964485383207047
				],
				[
					4.94899046879433,
					0
				],
				[
					4.629700761130146,
					0.3192897076641514
				],
				[
					4.470055907298056,
					1.1175139768245195
				],
				[
					4.310411053465964,
					1.9157382459848926
				],
				[
					4.150766199633873,
					2.8736073689773365
				],
				[
					4.150766199633873,
					3.671831638137704
				],
				[
					4.150766199633873,
					4.629700761130148
				],
				[
					3.9911213458017816,
					5.587569884122597
				],
				[
					3.8314764919696898,
					7.024373568611263
				],
				[
					3.6718316381375984,
					7.982242691603706
				],
				[
					3.512186784305675,
					9.419046376092371
				],
				[
					3.3525419304735835,
					10.696205206748965
				],
				[
					3.192897076641492,
					11.973364037405561
				],
				[
					2.8736073689773094,
					13.090878014230077
				],
				[
					2.5543176613131267,
					14.368036844886669
				],
				[
					2.3946728074810353,
					15.006616260214964
				],
				[
					2.0753830998168525,
					15.804840529375335
				],
				[
					1.7560933921528374,
					16.443419944703628
				],
				[
					1.4368036844886547,
					16.92235450619985
				],
				[
					0.7982242691602891,
					17.401289067696073
				],
				[
					0.47893456149627417,
					17.560933921528154
				],
				[
					0,
					17.720578775360224
				],
				[
					-0.31928970766418274,
					17.880223629192294
				],
				[
					-1.117513976824472,
					17.880223629192294
				],
				[
					-1.4368036844886547,
					17.880223629192294
				],
				[
					-1.596448538320746,
					17.880223629192294
				],
				[
					-1.7560933921528374,
					17.560933921528154
				],
				[
					-1.9157382459849288,
					16.92235450619985
				],
				[
					-1.9157382459849288,
					16.443419944703628
				],
				[
					-1.9157382459849288,
					15.804840529375335
				],
				[
					-1.9157382459849288,
					15.325905967879114
				],
				[
					-1.7560933921528374,
					14.846971406382892
				],
				[
					-1.4368036844886547,
					14.368036844886669
				],
				[
					-1.117513976824472,
					14.20839199105459
				],
				[
					-0.798224269160457,
					13.889102283390448
				],
				[
					-0.47893456149627417,
					13.410167721894227
				],
				[
					0,
					13.250522868062145
				],
				[
					0.15964485383209137,
					13.250522868062145
				],
				[
					0.6385794153281977,
					13.250522868062145
				],
				[
					0.9578691229923805,
					13.569812575726298
				],
				[
					1.2771588306565633,
					13.729457429558368
				],
				[
					1.4368036844886547,
					14.04874713722252
				],
				[
					1.9157382459849288,
					14.527681698718741
				],
				[
					2.0753830998168525,
					14.846971406382892
				],
				[
					2.3946728074810353,
					15.166261114047034
				],
				[
					2.713962515145218,
					15.645195675543265
				],
				[
					3.0332522228094008,
					15.804840529375335
				],
				[
					3.3525419304735835,
					16.124130237039488
				],
				[
					3.512186784305675,
					16.60306479853571
				],
				[
					3.8314764919696898,
					16.76270965236778
				],
				[
					3.9911213458017816,
					16.76270965236778
				],
				[
					4.150766199633873,
					16.76270965236778
				],
				[
					4.310411053465964,
					16.76270965236778
				],
				[
					4.470055907298056,
					16.76270965236778
				],
				[
					4.470055907298056,
					16.60306479853571
				],
				[
					4.629700761130146,
					16.443419944703628
				],
				[
					4.7893456149622375,
					16.124130237039488
				],
				[
					4.7893456149622375,
					15.804840529375335
				],
				[
					4.7893456149622375,
					15.804840529375335
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 462,
			"versionNonce": 744197387,
			"isDeleted": false,
			"id": "-_txRGerE07QBPtgcYaP_",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1027.5166740728032,
			"y": 731.7854190634239,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.3946728074810357,
			"height": 3.5121867843056287,
			"seed": 1984079179,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.15964485383207572
				],
				[
					0,
					0
				],
				[
					-0.47893456149610647,
					0.7982242691603734
				],
				[
					-1.1175139768244722,
					1.4368036844886658
				],
				[
					-1.75609339215267,
					2.075383099816963
				],
				[
					-2.075383099816853,
					2.7139625151452607
				],
				[
					-2.3946728074810357,
					3.352541930473553
				],
				[
					-2.3946728074810357,
					3.352541930473553
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 498,
			"versionNonce": 45604133,
			"isDeleted": false,
			"id": "nefY9zGzC0HXPJS858FK_",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1030.8692160032767,
			"y": 723.6435315179881,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.343663276275534,
			"height": 12.292653745069702,
			"seed": 1895154667,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.15964485383209143,
					0
				],
				[
					0,
					0
				],
				[
					0.7982242691604573,
					0.1596448538320757
				],
				[
					1.756093392152838,
					0.3192897076641461
				],
				[
					3.1928970766414935,
					0.4789345614962218
				],
				[
					3.831476491969859,
					0.4789345614962218
				],
				[
					4.470055907298057,
					0.798224269160368
				],
				[
					4.629700761130148,
					0.798224269160368
				],
				[
					4.948990468794332,
					0.9578691229924436
				],
				[
					5.108635322626423,
					1.1175139768245195
				],
				[
					5.427925030290606,
					1.2771588306565897
				],
				[
					5.587569884122697,
					1.4368036844886656
				],
				[
					5.747214737954788,
					1.5964485383207412
				],
				[
					5.747214737954788,
					1.7560933921528115
				],
				[
					5.427925030290606,
					2.0753830998169627
				],
				[
					5.108635322626423,
					2.3946728074811094
				],
				[
					4.310411053465965,
					3.0332522228094065
				],
				[
					3.1928970766414935,
					3.9911213458018504
				],
				[
					2.394672807481204,
					5.10863532262637
				],
				[
					1.2771588306565638,
					6.545439007115036
				],
				[
					0.6385794153283657,
					7.343663276275408
				],
				[
					0,
					8.30153239926785
				],
				[
					-0.31928970766418285,
					9.09975666842822
				],
				[
					-0.9578691229923808,
					9.897980937588594
				],
				[
					-1.2771588306565638,
					10.696205206748965
				],
				[
					-1.5964485383207467,
					11.015494914413107
				],
				[
					-1.5964485383207467,
					11.65407432974141
				],
				[
					-1.5964485383207467,
					11.973364037405553
				],
				[
					-1.4368036844886551,
					12.292653745069702
				],
				[
					-1.2771588306565638,
					12.292653745069702
				],
				[
					-0.9578691229923808,
					12.292653745069702
				],
				[
					-0.638579415328198,
					12.292653745069702
				],
				[
					0,
					12.292653745069702
				],
				[
					0.31928970766418285,
					12.133008891237631
				],
				[
					0.9578691229925487,
					11.81371918357348
				],
				[
					1.1175139768246403,
					11.65407432974141
				],
				[
					1.5964485383207467,
					11.334784622077258
				],
				[
					1.9157382459849295,
					11.175139768245188
				],
				[
					2.235027953649112,
					11.175139768245188
				],
				[
					2.394672807481204,
					11.015494914413107
				],
				[
					2.5543176613132954,
					10.855850060581036
				],
				[
					2.8736073689773103,
					10.855850060581036
				],
				[
					2.8736073689773103,
					10.696205206748965
				],
				[
					3.033252222809402,
					10.696205206748965
				],
				[
					3.033252222809402,
					10.696205206748965
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 463,
			"versionNonce": 186364843,
			"isDeleted": false,
			"id": "KGLdY2XwyDR2S0XtE-jQd",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1031.1885057109412,
			"y": 728.9118116944466,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.5121867843056758,
			"height": 0,
			"seed": 1896615563,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.15964485383209143,
					0
				],
				[
					0.31928970766418285,
					0
				],
				[
					0.7982242691604573,
					0
				],
				[
					1.4368036844886551,
					0
				],
				[
					1.9157382459849295,
					0
				],
				[
					2.713962515145219,
					0
				],
				[
					3.033252222809402,
					0
				],
				[
					3.1928970766414935,
					0
				],
				[
					3.3525419304735844,
					0
				],
				[
					3.3525419304735844,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 481,
			"versionNonce": 208334981,
			"isDeleted": false,
			"id": "7scwplE66Sb5ks66vbKxT",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1038.8514586948804,
			"y": 722.3663726873316,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.9911213458017825,
			"height": 14.368036844886669,
			"seed": 960496939,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.15964485383209145,
					0
				],
				[
					0.47893456149627434,
					0.3192897076641514
				],
				[
					0.6385794153283658,
					0.4789345614962218
				],
				[
					1.2771588306565638,
					0.9578691229924436
				],
				[
					1.756093392152838,
					1.4368036844886707
				],
				[
					2.235027953649112,
					2.0753830998169627
				],
				[
					2.5543176613131275,
					2.71396251514526
				],
				[
					3.1928970766414935,
					4.310411053466002
				],
				[
					3.1928970766414935,
					5.10863532262637
				],
				[
					3.1928970766414935,
					6.385794153282965
				],
				[
					3.1928970766414935,
					7.024373568611263
				],
				[
					3.033252222809402,
					7.82259783777163
				],
				[
					2.8736073689773103,
					8.620822106932003
				],
				[
					2.5543176613131275,
					9.419046376092371
				],
				[
					2.235027953649112,
					10.05762579142067
				],
				[
					2.0753830998170213,
					10.696205206748965
				],
				[
					1.9157382459849297,
					11.494429475909335
				],
				[
					1.756093392152838,
					12.292653745069702
				],
				[
					1.4368036844886551,
					13.090878014230077
				],
				[
					1.1175139768244724,
					13.569812575726298
				],
				[
					0.7982242691604573,
					14.04874713722252
				],
				[
					0.6385794153283658,
					14.20839199105459
				],
				[
					0.47893456149627434,
					14.368036844886669
				],
				[
					0.3192897076641829,
					14.368036844886669
				],
				[
					0,
					14.368036844886669
				],
				[
					-0.3192897076641829,
					14.368036844886669
				],
				[
					-0.6385794153283658,
					14.368036844886669
				],
				[
					-0.7982242691602894,
					14.368036844886669
				],
				[
					-0.7982242691602894,
					14.368036844886669
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 488,
			"versionNonce": 2019427915,
			"isDeleted": false,
			"id": "tCuQZUAqyrJE1OFgQuoJz",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1116.9177922187648,
			"y": 717.2577373647051,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.268280176458346,
			"height": 21.073120705833777,
			"seed": 1358702539,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.15964485383192362,
					0
				],
				[
					-0.31928970766401504,
					0.15964485383207572
				],
				[
					-0.7982242691602894,
					0.4789345614962219
				],
				[
					-1.2771588306565638,
					1.277158830656595
				],
				[
					-2.0753830998168534,
					1.9157382459848928
				],
				[
					-2.5543176613131275,
					2.7139625151452607
				],
				[
					-3.1928970766414935,
					3.6718316381377045
				],
				[
					-3.5121867843055083,
					4.470055907298078
				],
				[
					-4.310411053465965,
					5.268280176458446
				],
				[
					-4.7893456149620715,
					6.545439007115041
				],
				[
					-4.948990468794163,
					7.503308130107485
				],
				[
					-4.948990468794163,
					8.620822106932005
				],
				[
					-4.948990468794163,
					9.738336083756518
				],
				[
					-4.948990468794163,
					10.855850060581037
				],
				[
					-4.7893456149620715,
					11.973364037405558
				],
				[
					-4.629700761130148,
					13.090878014230077
				],
				[
					-4.470055907298057,
					14.368036844886667
				],
				[
					-3.991121345801783,
					15.645195675543262
				],
				[
					-3.6718316381375997,
					16.922354506199852
				],
				[
					-3.352541930473417,
					17.720578775360224
				],
				[
					-2.8736073689773103,
					18.83809275218474
				],
				[
					-2.713962515145219,
					19.317027313680963
				],
				[
					-2.3946728074810357,
					19.636317021345114
				],
				[
					-2.235027953648945,
					19.955606729009265
				],
				[
					-2.0753830998168534,
					20.274896436673405
				],
				[
					-1.9157382459847616,
					20.434541290505486
				],
				[
					-1.7560933921526702,
					20.594186144337556
				],
				[
					-1.4368036844886551,
					20.913475852001707
				],
				[
					-1.1175139768244724,
					20.913475852001707
				],
				[
					-0.7982242691602894,
					21.073120705833777
				],
				[
					-0.4789345614961065,
					21.073120705833777
				],
				[
					0,
					21.073120705833777
				],
				[
					0.15964485383209143,
					21.073120705833777
				],
				[
					0.31928970766418285,
					20.913475852001707
				],
				[
					0.31928970766418285,
					20.913475852001707
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 463,
			"versionNonce": 1227134949,
			"isDeleted": false,
			"id": "Iig5NgP-z56zaVl6B-y56",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1121.7071378337268,
			"y": 724.9206903486447,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 4.150766199633874,
			"height": 9.419046376092377,
			"seed": 1851455083,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.47893456149610647,
					0.47893456149622177
				],
				[
					-1.1175139768244722,
					1.7560933921528166
				],
				[
					-1.75609339215267,
					2.873607368977336
				],
				[
					-2.5543176613131275,
					3.9911213458018553
				],
				[
					-3.512186784305508,
					6.0665044456188175
				],
				[
					-3.9911213458017825,
					7.982242691603705
				],
				[
					-3.9911213458017825,
					8.780466960764072
				],
				[
					-4.150766199633874,
					9.259401522260294
				],
				[
					-4.150766199633874,
					9.419046376092377
				],
				[
					-4.150766199633874,
					9.259401522260294
				],
				[
					-4.150766199633874,
					9.259401522260294
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 469,
			"versionNonce": 989660395,
			"isDeleted": false,
			"id": "1xJhU8VORrzJPh4il0e0j",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1117.8756613417572,
			"y": 725.878559471637,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.5543176613131275,
			"height": 6.385794153282959,
			"seed": 539422987,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.3192897076641461
				],
				[
					0,
					0.6385794153282922
				],
				[
					0.3192897076641829,
					1.4368036844886656
				],
				[
					0.6385794153281981,
					1.9157382459848873
				],
				[
					0.957869122992381,
					3.0332522228094065
				],
				[
					1.2771588306565638,
					4.310411053465996
				],
				[
					1.5964485383207467,
					5.10863532262637
				],
				[
					1.5964485383207467,
					5.427925030290515
				],
				[
					1.7560933921528383,
					5.906859591786738
				],
				[
					1.91573824598493,
					6.226149299450883
				],
				[
					1.91573824598493,
					6.385794153282959
				],
				[
					2.0753830998170213,
					6.385794153282959
				],
				[
					2.2350279536489452,
					6.385794153282959
				],
				[
					2.394672807481036,
					6.385794153282959
				],
				[
					2.394672807481036,
					6.226149299450883
				],
				[
					2.5543176613131275,
					5.906859591786738
				],
				[
					2.5543176613131275,
					5.906859591786738
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 462,
			"versionNonce": 1123177285,
			"isDeleted": false,
			"id": "VjXD4pvRWVBDgVWdPnMpH",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1122.5053621028874,
			"y": 721.089213856675,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.5964485383207465,
			"height": 4.470055907298073,
			"seed": 937072555,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.15964485383207572
				],
				[
					0.15964485383209143,
					0.7982242691603681
				],
				[
					0.47893456149610647,
					1.27715883065659
				],
				[
					0.9578691229923807,
					2.2350279536490336
				],
				[
					1.2771588306565638,
					3.192897076641483
				],
				[
					1.436803684488655,
					3.6718316381377045
				],
				[
					1.5964485383207465,
					4.150766199633926
				],
				[
					1.5964485383207465,
					4.310411053465997
				],
				[
					1.5964485383207465,
					4.470055907298073
				],
				[
					1.5964485383207465,
					4.470055907298073
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 463,
			"versionNonce": 1518546827,
			"isDeleted": false,
			"id": "jwfWECpdxE-JFNqMa-hm6",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1128.0929319870097,
			"y": 731.9450639172558,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.0332522228094017,
			"height": 4.789345614962223,
			"seed": 1939892811,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.4789345614962743,
					0.3192897076641461
				],
				[
					-0.9578691229923807,
					0.9578691229924436
				],
				[
					-1.436803684488655,
					1.5964485383207412
				],
				[
					-2.075383099816853,
					2.554317661313185
				],
				[
					-2.2350279536489444,
					2.8736073689773365
				],
				[
					-2.3946728074810357,
					3.5121867843056287
				],
				[
					-2.7139625151452185,
					4.150766199633921
				],
				[
					-2.87360736897731,
					4.629700761130143
				],
				[
					-3.0332522228094017,
					4.629700761130143
				],
				[
					-3.0332522228094017,
					4.789345614962223
				],
				[
					-3.0332522228094017,
					4.789345614962223
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 537,
			"versionNonce": 1714528933,
			"isDeleted": false,
			"id": "k8o7OACYOXt98-H1qxIBd",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1130.9665393559872,
			"y": 722.8453072488278,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 9.578691229924479,
			"height": 18.997737606016816,
			"seed": 1750264043,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.47893456149622177
				],
				[
					0,
					1.2771588306565949
				],
				[
					0,
					1.7560933921528166
				],
				[
					0,
					2.5543176613131844
				],
				[
					0,
					3.3525419304735578
				],
				[
					0,
					4.310411053466001
				],
				[
					0.3192897076641829,
					4.948990468794299
				],
				[
					0.6385794153283658,
					5.268280176458445
				],
				[
					0.9578691229925487,
					5.268280176458445
				],
				[
					1.5964485383207465,
					5.108635322626374
				],
				[
					1.9157382459849295,
					4.470055907298077
				],
				[
					2.2350279536491127,
					3.8314764919697795
				],
				[
					2.554317661313295,
					2.71396251514526
				],
				[
					2.7139625151453863,
					2.2350279536490385
				],
				[
					2.7139625151453863,
					1.596448538320741
				],
				[
					2.7139625151453863,
					1.2771588306565949
				],
				[
					2.7139625151453863,
					1.1175139768245193
				],
				[
					2.7139625151453863,
					1.596448538320741
				],
				[
					2.7139625151453863,
					2.2350279536490385
				],
				[
					2.7139625151453863,
					3.0332522228094114
				],
				[
					2.7139625151453863,
					3.8314764919697795
				],
				[
					2.7139625151453863,
					4.629700761130147
				],
				[
					2.7139625151453863,
					5.587569884122596
				],
				[
					2.7139625151453863,
					6.385794153282964
				],
				[
					2.7139625151453863,
					6.864728714779186
				],
				[
					2.554317661313295,
					7.662952983939559
				],
				[
					2.394672807481204,
					8.620822106932001
				],
				[
					2.2350279536491127,
					9.578691229924447
				],
				[
					2.075383099817021,
					10.217270645252743
				],
				[
					1.9157382459849295,
					11.334784622077256
				],
				[
					1.7560933921528379,
					12.452298598901782
				],
				[
					1.436803684488823,
					13.729457429558366
				],
				[
					1.436803684488823,
					14.048747137222518
				],
				[
					1.2771588306565638,
					14.84697140638289
				],
				[
					1.11751397682464,
					15.645195675543263
				],
				[
					0.9578691229925487,
					16.283775090871558
				],
				[
					0.7982242691604572,
					16.92235450619985
				],
				[
					0.6385794153283658,
					17.56093392152815
				],
				[
					0.15964485383209145,
					18.03986848302437
				],
				[
					-0.15964485383209145,
					18.518803044520595
				],
				[
					-0.638579415328198,
					18.838092752184735
				],
				[
					-0.9578691229923808,
					18.997737606016816
				],
				[
					-1.2771588306565638,
					18.997737606016816
				],
				[
					-1.7560933921526702,
					18.997737606016816
				],
				[
					-2.075383099816853,
					18.997737606016816
				],
				[
					-2.3946728074810357,
					18.678447898352665
				],
				[
					-2.713962515145219,
					18.359158190688515
				],
				[
					-2.713962515145219,
					18.03986848302437
				],
				[
					-2.8736073689773103,
					17.72057877536022
				],
				[
					-2.8736073689773103,
					17.241644213864003
				],
				[
					-2.8736073689773103,
					17.08199936003193
				],
				[
					-2.713962515145219,
					16.76270965236778
				],
				[
					-2.2350279536489444,
					16.283775090871558
				],
				[
					-1.5964485383207465,
					15.645195675543263
				],
				[
					-1.2771588306565638,
					15.325905967879113
				],
				[
					-0.7982242691602893,
					15.006616260214962
				],
				[
					-0.47893456149610647,
					14.84697140638289
				],
				[
					-0.31928970766401504,
					14.68732655255081
				],
				[
					-0.15964485383209145,
					14.68732655255081
				],
				[
					0,
					14.68732655255081
				],
				[
					0.47893456149627434,
					14.68732655255081
				],
				[
					0.6385794153283658,
					14.84697140638289
				],
				[
					0.7982242691604572,
					15.006616260214962
				],
				[
					1.11751397682464,
					15.166261114047032
				],
				[
					1.7560933921528379,
					15.485550821711184
				],
				[
					2.2350279536491127,
					15.645195675543263
				],
				[
					2.554317661313295,
					15.964485383207403
				],
				[
					3.033252222809402,
					16.124130237039484
				],
				[
					3.831476491969859,
					16.443419944703628
				],
				[
					4.150766199634042,
					16.443419944703628
				],
				[
					4.310411053466133,
					16.60306479853571
				],
				[
					4.78934561496224,
					16.76270965236778
				],
				[
					5.268280176458514,
					16.76270965236778
				],
				[
					5.427925030290606,
					16.76270965236778
				],
				[
					5.7472147379547875,
					16.76270965236778
				],
				[
					5.906859591786712,
					16.76270965236778
				],
				[
					6.226149299450895,
					16.76270965236778
				],
				[
					6.385794153282986,
					16.76270965236778
				],
				[
					6.545439007115077,
					16.76270965236778
				],
				[
					6.545439007115077,
					16.60306479853571
				],
				[
					6.705083860947169,
					16.443419944703628
				],
				[
					6.705083860947169,
					16.124130237039484
				],
				[
					6.705083860947169,
					15.964485383207403
				],
				[
					6.705083860947169,
					15.964485383207403
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 462,
			"versionNonce": 153814571,
			"isDeleted": false,
			"id": "6OIvXUNyE6_YngIaFDK2J",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1137.6716232169347,
			"y": 721.7277932720032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.7560933921528379,
			"height": 5.747214737954662,
			"seed": 729584523,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.15964485383209143,
					0
				],
				[
					0.31928970766418285,
					0.3192897076641461
				],
				[
					0.4789345614962743,
					0.798224269160368
				],
				[
					0.7982242691604572,
					1.4368036844886656
				],
				[
					1.1175139768244722,
					2.235027953649033
				],
				[
					1.436803684488655,
					3.5121867843056287
				],
				[
					1.436803684488655,
					4.310411053465996
				],
				[
					1.5964485383207465,
					5.268280176458441
				],
				[
					1.7560933921528379,
					5.747214737954662
				],
				[
					1.7560933921528379,
					5.747214737954662
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 472,
			"versionNonce": 932185605,
			"isDeleted": false,
			"id": "hAmUiaiPIFgdsKCBm7fk2",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1146.2924453238666,
			"y": 731.1468396480955,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.671831638137767,
			"height": 5.427925030290515,
			"seed": 1029171755,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.15964485383225926,
					0
				],
				[
					-0.31928970766418285,
					0
				],
				[
					-0.4789345614962743,
					0.3192897076641514
				],
				[
					-0.6385794153283657,
					0.6385794153282974
				],
				[
					-0.9578691229925486,
					1.4368036844886705
				],
				[
					-1.2771588306567314,
					2.5543176613131844
				],
				[
					-1.4368036844888228,
					3.1928970766414873
				],
				[
					-1.5964485383209144,
					3.5121867843056283
				],
				[
					-1.7560933921528379,
					3.99112134580185
				],
				[
					-1.9157382459849293,
					4.150766199633932
				],
				[
					-2.075383099817021,
					4.310411053466001
				],
				[
					-2.3946728074812036,
					4.470055907298072
				],
				[
					-2.7139625151453863,
					4.629700761130152
				],
				[
					-3.033252222809569,
					4.789345614962223
				],
				[
					-3.192897076641493,
					5.108635322626374
				],
				[
					-3.352541930473584,
					5.268280176458445
				],
				[
					-3.5121867843056758,
					5.427925030290515
				],
				[
					-3.671831638137767,
					5.427925030290515
				],
				[
					-3.671831638137767,
					5.268280176458445
				],
				[
					-3.671831638137767,
					5.268280176458445
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 516,
			"versionNonce": 1306462411,
			"isDeleted": false,
			"id": "rYZ-qTLyinLNu3JLC9pxm",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1149.8046321081722,
			"y": 723.3242418103239,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.982242691603732,
			"height": 14.04874713722252,
			"seed": 852454603,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.31928970766418285,
					0
				],
				[
					0.4789345614962743,
					0
				],
				[
					0.6385794153283657,
					0
				],
				[
					0.9578691229923807,
					0
				],
				[
					1.436803684488655,
					0
				],
				[
					2.075383099817021,
					0
				],
				[
					2.87360736897731,
					0
				],
				[
					3.5121867843056758,
					0
				],
				[
					4.150766199633874,
					0
				],
				[
					4.470055907298057,
					0
				],
				[
					4.948990468794331,
					0
				],
				[
					5.268280176458513,
					0
				],
				[
					5.427925030290605,
					0
				],
				[
					5.587569884122528,
					0
				],
				[
					5.7472147379547875,
					0.1596448538320757
				],
				[
					5.906859591786711,
					0.3192897076641514
				],
				[
					6.066504445618803,
					0.3192897076641514
				],
				[
					6.226149299450895,
					0.4789345614962271
				],
				[
					6.226149299450895,
					0.6385794153282974
				],
				[
					5.906859591786711,
					0.7982242691603733
				],
				[
					5.587569884122528,
					0.9578691229924489
				],
				[
					5.268280176458513,
					1.1175139768245195
				],
				[
					4.948990468794331,
					1.2771588306565949
				],
				[
					4.629700761130148,
					1.7560933921528168
				],
				[
					4.310411053465965,
					2.0753830998169627
				],
				[
					3.8314764919698585,
					2.71396251514526
				],
				[
					3.5121867843056758,
					3.5121867843056336
				],
				[
					3.192897076641493,
					3.9911213458018557
				],
				[
					2.7139625151452185,
					4.789345614962223
				],
				[
					2.554317661313295,
					5.42792503029052
				],
				[
					2.3946728074812036,
					5.906859591786742
				],
				[
					2.2350279536491118,
					6.385794153282965
				],
				[
					1.9157382459849293,
					6.8647287147791864
				],
				[
					1.7560933921528379,
					7.503308130107484
				],
				[
					1.5964485383207465,
					8.14188754543578
				],
				[
					1.2771588306565638,
					8.780466960764073
				],
				[
					1.11751397682464,
					9.259401522260301
				],
				[
					0.7982242691604572,
					9.897980937588594
				],
				[
					0.4789345614962743,
					10.376915499084815
				],
				[
					0.31928970766418285,
					10.696205206748965
				],
				[
					0.15964485383209143,
					11.175139768245188
				],
				[
					-0.15964485383209143,
					11.49442947590934
				],
				[
					-0.31928970766418285,
					11.81371918357348
				],
				[
					-0.4789345614962743,
					12.133008891237631
				],
				[
					-0.7982242691602893,
					12.452298598901784
				],
				[
					-1.1175139768244722,
					12.931233160398007
				],
				[
					-1.2771588306565638,
					13.090878014230077
				],
				[
					-1.436803684488655,
					13.410167721894227
				],
				[
					-1.5964485383207465,
					13.569812575726298
				],
				[
					-1.7560933921528379,
					13.729457429558368
				],
				[
					-1.7560933921528379,
					13.889102283390448
				],
				[
					-1.7560933921528379,
					14.04874713722252
				],
				[
					-1.1175139768244722,
					14.04874713722252
				],
				[
					-0.4789345614962743,
					14.04874713722252
				],
				[
					0.15964485383209143,
					14.04874713722252
				],
				[
					0.7982242691604572,
					13.889102283390448
				],
				[
					1.2771588306565638,
					13.729457429558368
				],
				[
					2.075383099817021,
					13.569812575726298
				],
				[
					2.554317661313295,
					13.410167721894227
				],
				[
					2.7139625151452185,
					13.410167721894227
				],
				[
					3.192897076641493,
					13.250522868062145
				],
				[
					3.671831638137767,
					13.250522868062145
				],
				[
					3.9911213458019503,
					13.090878014230077
				],
				[
					4.310411053465965,
					12.931233160398007
				],
				[
					4.948990468794331,
					12.931233160398007
				],
				[
					5.268280176458513,
					12.771588306565924
				],
				[
					5.268280176458513,
					12.771588306565924
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 466,
			"versionNonce": 1242234213,
			"isDeleted": false,
			"id": "6JMeuz4ucr1KBhep-1O5K",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1150.123921815836,
			"y": 728.1135874252861,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.108635322626422,
			"height": 0.1596448538320757,
			"seed": 528325483,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.15964485383209143,
					0
				],
				[
					-0.15964485383209143,
					0.1596448538320757
				],
				[
					0,
					0.1596448538320757
				],
				[
					0.7982242691604572,
					0.1596448538320757
				],
				[
					1.436803684488655,
					0.1596448538320757
				],
				[
					1.9157382459849293,
					0.1596448538320757
				],
				[
					2.5543176613131275,
					0.1596448538320757
				],
				[
					3.0332522228094017,
					0.1596448538320757
				],
				[
					3.192897076641493,
					0.1596448538320757
				],
				[
					3.671831638137767,
					0.1596448538320757
				],
				[
					3.9911213458017825,
					0.1596448538320757
				],
				[
					4.150766199633874,
					0.1596448538320757
				],
				[
					4.310411053465965,
					0.1596448538320757
				],
				[
					4.470055907298057,
					0.1596448538320757
				],
				[
					4.789345614962239,
					0.1596448538320757
				],
				[
					4.948990468794331,
					0.1596448538320757
				],
				[
					4.948990468794331,
					0.1596448538320757
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 460,
			"versionNonce": 1849276267,
			"isDeleted": false,
			"id": "sYhlrPA4XQSvkOkKnnJb3",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1156.6693608229514,
			"y": 718.6945410491937,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.7139625151452185,
			"height": 6.226149299450889,
			"seed": 1068299787,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.31928970766418285,
					0.4789345614962271
				],
				[
					0.9578691229923807,
					1.4368036844886707
				],
				[
					1.436803684488655,
					2.235027953649039
				],
				[
					1.7560933921528379,
					3.033252222809412
				],
				[
					2.2350279536489444,
					4.470055907298078
				],
				[
					2.5543176613131275,
					5.108635322626375
				],
				[
					2.5543176613131275,
					5.42792503029052
				],
				[
					2.5543176613131275,
					5.906859591786742
				],
				[
					2.7139625151452185,
					6.066504445618818
				],
				[
					2.7139625151452185,
					6.226149299450889
				],
				[
					2.7139625151452185,
					6.226149299450889
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 476,
			"versionNonce": 1961887941,
			"isDeleted": false,
			"id": "PpwVd2gWoR2iJqaUF-PIR",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1162.5762204147381,
			"y": 720.1313447336825,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.9157382459849293,
			"height": 18.19951333685644,
			"seed": 1649933483,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.15964485383209143,
					0
				],
				[
					0,
					0.15964485383207047
				],
				[
					0.31928970766418285,
					0.4789345614962218
				],
				[
					0.638579415328198,
					1.1175139768245195
				],
				[
					0.7982242691602893,
					1.7560933921528115
				],
				[
					0.9578691229923807,
					2.554317661313185
				],
				[
					1.2771588306565638,
					3.5121867843056287
				],
				[
					1.436803684488655,
					4.310411053465996
				],
				[
					1.436803684488655,
					5.427925030290515
				],
				[
					1.436803684488655,
					6.545439007115036
				],
				[
					1.436803684488655,
					8.30153239926785
				],
				[
					1.436803684488655,
					9.419046376092368
				],
				[
					1.436803684488655,
					10.855850060581036
				],
				[
					1.2771588306565638,
					11.81371918357348
				],
				[
					1.2771588306565638,
					12.931233160398
				],
				[
					1.1175139768244722,
					13.889102283390443
				],
				[
					0.9578691229923807,
					15.166261114047039
				],
				[
					0.7982242691602893,
					15.964485383207402
				],
				[
					0.638579415328198,
					16.283775090871554
				],
				[
					0.4789345614962743,
					16.76270965236777
				],
				[
					0.31928970766418285,
					17.081999360031926
				],
				[
					0.31928970766418285,
					17.401289067696066
				],
				[
					0.15964485383209143,
					17.720578775360217
				],
				[
					-0.15964485383209143,
					18.03986848302437
				],
				[
					-0.31928970766418285,
					18.19951333685644
				],
				[
					-0.4789345614962743,
					18.19951333685644
				],
				[
					-0.4789345614962743,
					18.19951333685644
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 391,
			"versionNonce": 411406859,
			"isDeleted": false,
			"id": "mwuqVkV-G27W00PvuGmSw",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1043.8609249337796,
			"y": 809.2992189370882,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.054932223919166,
			"height": 0.9687891558270867,
			"seed": 938164331,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.24219728895681364,
					0
				],
				[
					0.4843945779134594,
					0
				],
				[
					1.2109864447837326,
					0
				],
				[
					1.9375783116541734,
					0.48439457791354334
				],
				[
					2.6641701785244463,
					0.48439457791354334
				],
				[
					2.9063674674810924,
					0.48439457791354334
				],
				[
					3.6329593343513653,
					0.726591866870357
				],
				[
					4.117353912264993,
					0.726591866870357
				],
				[
					4.601748490178452,
					0.726591866870357
				],
				[
					5.328340357048725,
					0.9687891558270867
				],
				[
					5.570537646005539,
					0.9687891558270867
				],
				[
					5.812734934962352,
					0.9687891558270867
				],
				[
					5.0861430680919115,
					0.9687891558270867
				],
				[
					5.0861430680919115,
					0.9687891558270867
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 402,
			"versionNonce": 1239197733,
			"isDeleted": false,
			"id": "qKPU9-8ylW2Ef025TAsca",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1043.1343330669094,
			"y": 809.2992189370882,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 9.930088847227177,
			"height": 0,
			"seed": 622721803,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726445,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.24219728895664577,
					0
				],
				[
					0.7265918668702731,
					0
				],
				[
					1.6953810226973596,
					0
				],
				[
					2.179775600610819,
					0
				],
				[
					3.148564756437906,
					0
				],
				[
					3.390762045394719,
					0
				],
				[
					3.8751566233081793,
					0
				],
				[
					4.601748490178452,
					0
				],
				[
					5.328340357048725,
					0
				],
				[
					5.570537646005539,
					0
				],
				[
					6.054932223918998,
					0
				],
				[
					6.539326801832625,
					0
				],
				[
					7.0237213797460845,
					0
				],
				[
					7.2659186687028985,
					0
				],
				[
					7.508115957659544,
					0
				],
				[
					7.750313246616359,
					0
				],
				[
					7.992510535573171,
					0
				],
				[
					8.234707824529817,
					0
				],
				[
					8.476905113486632,
					0
				],
				[
					8.961299691400258,
					0
				],
				[
					9.203496980356904,
					0
				],
				[
					9.445694269313718,
					0
				],
				[
					9.68789155827053,
					0
				],
				[
					9.930088847227177,
					0
				],
				[
					9.930088847227177,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 403,
			"versionNonce": 1304238251,
			"isDeleted": false,
			"id": "EkcXOrQd_YN-soH3j7673",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1043.3765303558664,
			"y": 816.5651376057908,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 11.383272580967892,
			"height": 0.2421972889567297,
			"seed": 1566597547,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4843945779136273,
					0
				],
				[
					1.2109864447839003,
					0
				],
				[
					1.6953810226973596,
					0
				],
				[
					2.4219728895678005,
					0
				],
				[
					2.90636746748126,
					0
				],
				[
					3.632959334351533,
					0
				],
				[
					3.8751566233083468,
					0
				],
				[
					4.843945779135265,
					0
				],
				[
					5.570537646005539,
					0
				],
				[
					6.297129512875979,
					-0.2421972889567297
				],
				[
					6.781524090789438,
					-0.2421972889567297
				],
				[
					7.5081159576597125,
					-0.2421972889567297
				],
				[
					7.750313246616525,
					-0.2421972889567297
				],
				[
					7.992510535573171,
					-0.2421972889567297
				],
				[
					8.476905113486799,
					-0.2421972889567297
				],
				[
					8.719102402443612,
					-0.2421972889567297
				],
				[
					9.445694269313886,
					-0.2421972889567297
				],
				[
					9.68789155827053,
					-0.2421972889567297
				],
				[
					9.930088847227346,
					-0.2421972889567297
				],
				[
					10.172286136184159,
					-0.2421972889567297
				],
				[
					10.414483425140805,
					-0.2421972889567297
				],
				[
					10.656680714097618,
					-0.2421972889567297
				],
				[
					10.898878003054431,
					-0.2421972889567297
				],
				[
					11.141075292011077,
					-0.2421972889567297
				],
				[
					11.383272580967892,
					-0.2421972889567297
				],
				[
					11.383272580967892,
					-0.2421972889567297
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 489,
			"versionNonce": 1253989253,
			"isDeleted": false,
			"id": "BMww9MvPAwszOyjNvFn9V",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1069.7760348521533,
			"y": 762.7973394573896,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 16.469415649059805,
			"height": 89.12860233608845,
			"seed": 970781771,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.4843945779135433
				],
				[
					-0.24219728895681364,
					1.453183733740588
				],
				[
					-0.4843945779134595,
					2.4219728895676327
				],
				[
					-0.7265918668702732,
					3.1485647564379056
				],
				[
					-0.7265918668702732,
					4.601748490178493
				],
				[
					-0.9687891558270869,
					5.81273493496231
				],
				[
					-1.4531837337405464,
					6.781524090789355
				],
				[
					-1.69538102269736,
					7.508115957659627
				],
				[
					-1.69538102269736,
					8.2347078245299
				],
				[
					-1.9375783116541738,
					9.445694269313716
				],
				[
					-2.179775600610819,
					10.414483425140803
				],
				[
					-2.421972889567633,
					11.62546986992462
				],
				[
					-2.6641701785244467,
					12.594259025751622
				],
				[
					-2.906367467481093,
					13.805245470535437
				],
				[
					-3.148564756437906,
					14.531837337405712
				],
				[
					-3.39076204539472,
					15.742823782189525
				],
				[
					-3.6329593343513658,
					16.953810226973342
				],
				[
					-3.8751566233081793,
					18.406993960713887
				],
				[
					-3.8751566233081793,
					19.61798040549779
				],
				[
					-4.117353912264994,
					20.82896685028152
				],
				[
					-4.359551201221638,
					22.039953295065338
				],
				[
					-4.359551201221638,
					23.735334317762696
				],
				[
					-4.359551201221638,
					24.7041234735897
				],
				[
					-4.359551201221638,
					26.15730720733033
				],
				[
					-4.359551201221638,
					27.610490941070875
				],
				[
					-4.359551201221638,
					28.821477385854692
				],
				[
					-4.359551201221638,
					29.79026654168178
				],
				[
					-4.359551201221638,
					31.001252986465513
				],
				[
					-4.359551201221638,
					32.212239431249415
				],
				[
					-4.359551201221638,
					33.18102858707641
				],
				[
					-4.359551201221638,
					34.149817742903416
				],
				[
					-4.359551201221638,
					35.118606898730505
				],
				[
					-4.359551201221638,
					36.087396054557594
				],
				[
					-4.359551201221638,
					37.29838249934141
				],
				[
					-4.359551201221638,
					37.78277707725495
				],
				[
					-4.359551201221638,
					38.993763522038684
				],
				[
					-4.359551201221638,
					40.2047499668225
				],
				[
					-4.359551201221638,
					40.931341833692855
				],
				[
					-4.359551201221638,
					41.65793370056313
				],
				[
					-4.359551201221638,
					42.38452556743341
				],
				[
					-4.359551201221638,
					43.353314723260404
				],
				[
					-4.359551201221638,
					44.07990659013076
				],
				[
					-4.359551201221638,
					44.806498457001034
				],
				[
					-4.117353912264994,
					45.77528761282804
				],
				[
					-3.8751566233081793,
					46.98627405761186
				],
				[
					-3.6329593343513658,
					47.95506321343894
				],
				[
					-3.39076204539472,
					49.166049658222676
				],
				[
					-3.148564756437906,
					50.13483881404976
				],
				[
					-2.906367467481093,
					51.34582525883357
				],
				[
					-2.6641701785244467,
					53.04120628153093
				],
				[
					-2.6641701785244467,
					54.00999543735794
				],
				[
					-2.421972889567633,
					55.22098188214175
				],
				[
					-2.421972889567633,
					55.94757374901202
				],
				[
					-2.179775600610819,
					56.67416561588238
				],
				[
					-1.9375783116541738,
					57.642954771709384
				],
				[
					-1.9375783116541738,
					58.369546638579656
				],
				[
					-1.69538102269736,
					59.096138505450014
				],
				[
					-1.69538102269736,
					59.82273037232029
				],
				[
					-1.4531837337405464,
					60.54932223919056
				],
				[
					-1.2109864447837326,
					61.03371681710402
				],
				[
					-1.2109864447837326,
					61.76030868397437
				],
				[
					-0.9687891558270869,
					62.24470326188792
				],
				[
					-0.7265918668702732,
					62.9712951287582
				],
				[
					-0.4843945779134595,
					63.697886995628465
				],
				[
					0,
					64.42447886249875
				],
				[
					0.24219728895681364,
					64.90887344041228
				],
				[
					0.7265918668702732,
					65.87766259623929
				],
				[
					0.9687891558270869,
					66.84645175206637
				],
				[
					1.2109864447839005,
					67.57304361893665
				],
				[
					1.69538102269736,
					68.29963548580692
				],
				[
					1.9375783116541738,
					69.0262273526772
				],
				[
					2.179775600610819,
					69.75281921954746
				],
				[
					2.421972889567633,
					70.23721379746101
				],
				[
					2.6641701785244467,
					70.72160837537456
				],
				[
					2.906367467481093,
					71.20600295328809
				],
				[
					3.148564756437906,
					71.69039753120164
				],
				[
					3.6329593343513658,
					72.65918668702864
				],
				[
					3.8751566233081793,
					73.14358126494218
				],
				[
					4.359551201221807,
					74.11237042076918
				],
				[
					4.601748490178453,
					74.59676499868273
				],
				[
					4.843945779135266,
					75.32335686555301
				],
				[
					5.08614306809208,
					76.04994873242327
				],
				[
					5.57053764600554,
					76.77654059929355
				],
				[
					5.812734934962353,
					77.26093517720709
				],
				[
					6.054932223918999,
					77.74532975512064
				],
				[
					6.054932223918999,
					78.22972433303418
				],
				[
					6.297129512875812,
					78.71411891094773
				],
				[
					6.78152409078944,
					79.19851348886118
				],
				[
					7.023721379746086,
					79.68290806677473
				],
				[
					7.265918668702899,
					80.16730264468828
				],
				[
					7.508115957659713,
					80.65169722260181
				],
				[
					7.750313246616359,
					81.13609180051536
				],
				[
					7.992510535573173,
					81.86268366738564
				],
				[
					8.234707824529988,
					82.34707824529909
				],
				[
					8.476905113486632,
					82.83147282321264
				],
				[
					8.719102402443445,
					83.07367011216937
				],
				[
					9.203496980356906,
					83.80026197903972
				],
				[
					9.44569426931372,
					84.04245926799645
				],
				[
					9.44569426931372,
					84.52685384591
				],
				[
					9.687891558270532,
					85.01124842382353
				],
				[
					9.930088847227179,
					85.495643001737
				],
				[
					10.414483425140807,
					85.98003757965054
				],
				[
					10.656680714097618,
					86.46443215756409
				],
				[
					10.656680714097618,
					86.94882673547762
				],
				[
					10.898878003054264,
					87.43322131339117
				],
				[
					11.14107529201108,
					87.6754186023479
				],
				[
					11.383272580967894,
					88.15981318026144
				],
				[
					11.625469869924538,
					88.15981318026144
				],
				[
					11.625469869924538,
					88.40201046921817
				],
				[
					11.867667158881352,
					88.6442077581749
				],
				[
					12.109864447838167,
					89.12860233608845
				],
				[
					12.109864447838167,
					89.12860233608845
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 490,
			"versionNonce": 193645387,
			"isDeleted": false,
			"id": "6e0rN5KsrDBZNk-3Y6oCu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1144.8571944287496,
			"y": 772.2430337267035,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 11.86766715888135,
			"height": 78.47192162199093,
			"seed": 849840747,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.24219728895681364,
					0
				],
				[
					0.4843945779134594,
					0
				],
				[
					0.9687891558270867,
					0.2421972889567717
				],
				[
					1.2109864447837326,
					0.7265918668703151
				],
				[
					1.6953810226973596,
					1.2109864447838166
				],
				[
					2.664170178524279,
					2.1797756006109035
				],
				[
					2.9063674674810924,
					2.664170178524405
				],
				[
					3.390762045394719,
					3.148564756437906
				],
				[
					3.6329593343513653,
					3.6329593343514497
				],
				[
					4.117353912264993,
					4.601748490178494
				],
				[
					4.359551201221806,
					5.086143068091996
				],
				[
					4.843945779135265,
					6.297129512875812
				],
				[
					5.086143068092079,
					7.023721379746128
				],
				[
					5.328340357048725,
					7.992510535573172
				],
				[
					5.570537646005539,
					8.961299691400177
				],
				[
					5.812734934962352,
					9.687891558270532
				],
				[
					6.054932223918998,
					10.414483425140805
				],
				[
					6.539326801832625,
					11.383272580967807
				],
				[
					6.781524090789271,
					12.836456314708439
				],
				[
					7.2659186687028985,
					13.805245470535441
				],
				[
					7.508115957659544,
					15.016231915319258
				],
				[
					7.750313246616359,
					16.227218360103073
				],
				[
					7.992510535573171,
					17.922599382800435
				],
				[
					8.476905113486632,
					19.133585827584252
				],
				[
					8.476905113486632,
					20.34457227236807
				],
				[
					8.719102402443443,
					21.31336142819507
				],
				[
					8.96129969140009,
					22.28215058402216
				],
				[
					9.203496980356904,
					23.493137028805975
				],
				[
					9.445694269313718,
					24.219728895676248
				],
				[
					9.68789155827053,
					25.672912629416793
				],
				[
					9.930088847227177,
					26.64170178524388
				],
				[
					10.17228613618399,
					28.094885518984427
				],
				[
					10.17228613618399,
					29.305871963768244
				],
				[
					10.414483425140805,
					30.274661119595244
				],
				[
					10.656680714097618,
					31.485647564379146
				],
				[
					10.656680714097618,
					32.21223943124942
				],
				[
					10.656680714097618,
					33.18102858707642
				],
				[
					10.656680714097618,
					33.90762045394669
				],
				[
					10.656680714097618,
					34.634212320817056
				],
				[
					10.656680714097618,
					35.60300147664405
				],
				[
					10.656680714097618,
					36.329593343514325
				],
				[
					10.656680714097618,
					36.813987921427874
				],
				[
					10.656680714097618,
					37.540579788298146
				],
				[
					10.656680714097618,
					38.26717165516842
				],
				[
					10.656680714097618,
					39.47815809995223
				],
				[
					10.656680714097618,
					39.96255267786578
				],
				[
					10.656680714097618,
					40.93134183369287
				],
				[
					10.656680714097618,
					41.415736411606325
				],
				[
					10.898878003054264,
					42.384525567433414
				],
				[
					10.898878003054264,
					43.35331472326041
				],
				[
					10.898878003054264,
					44.079906590130776
				],
				[
					11.141075292011077,
					44.80649845700105
				],
				[
					11.141075292011077,
					45.290893034914504
				],
				[
					11.141075292011077,
					46.25968219074159
				],
				[
					11.383272580967892,
					46.986274057611865
				],
				[
					11.383272580967892,
					47.955063213438955
				],
				[
					11.383272580967892,
					48.43945779135241
				],
				[
					11.383272580967892,
					49.16604965822268
				],
				[
					11.383272580967892,
					50.13483881404977
				],
				[
					11.383272580967892,
					50.861430680920044
				],
				[
					11.383272580967892,
					51.83021983674713
				],
				[
					11.383272580967892,
					52.556811703617406
				],
				[
					11.383272580967892,
					53.28340357048768
				],
				[
					11.383272580967892,
					54.00999543735795
				],
				[
					11.383272580967892,
					54.97878459318504
				],
				[
					11.625469869924537,
					55.70537646005531
				],
				[
					11.625469869924537,
					56.916362904839126
				],
				[
					11.625469869924537,
					57.40075748275267
				],
				[
					11.86766715888135,
					58.36954663857967
				],
				[
					11.86766715888135,
					58.85394121649321
				],
				[
					11.86766715888135,
					59.33833579440676
				],
				[
					11.86766715888135,
					60.06492766127703
				],
				[
					11.86766715888135,
					61.033716817104036
				],
				[
					11.86766715888135,
					61.76030868397439
				],
				[
					11.86766715888135,
					62.486900550844666
				],
				[
					11.86766715888135,
					62.971295128758214
				],
				[
					11.86766715888135,
					63.45568970667166
				],
				[
					11.625469869924537,
					64.18228157354194
				],
				[
					11.625469869924537,
					64.9088734404123
				],
				[
					11.383272580967892,
					65.39326801832584
				],
				[
					11.383272580967892,
					65.63546530728257
				],
				[
					11.141075292011077,
					66.36205717415284
				],
				[
					10.898878003054264,
					66.84645175206639
				],
				[
					10.656680714097618,
					67.33084632997985
				],
				[
					10.414483425140805,
					68.0574381968502
				],
				[
					10.17228613618399,
					68.54183277476375
				],
				[
					9.930088847227177,
					68.78403006372048
				],
				[
					9.930088847227177,
					69.26842464163403
				],
				[
					9.68789155827053,
					69.51062193059074
				],
				[
					9.445694269313718,
					69.99501650850429
				],
				[
					9.203496980356904,
					70.72160837537457
				],
				[
					9.203496980356904,
					70.96380566433129
				],
				[
					8.96129969140009,
					71.69039753120165
				],
				[
					8.96129969140009,
					71.93259482015839
				],
				[
					8.476905113486632,
					72.65918668702865
				],
				[
					8.476905113486632,
					72.90138397598538
				],
				[
					8.234707824529817,
					73.38577855389893
				],
				[
					8.234707824529817,
					73.62797584285566
				],
				[
					7.992510535573171,
					73.87017313181248
				],
				[
					7.750313246616359,
					74.35456770972601
				],
				[
					7.508115957659544,
					74.59676499868274
				],
				[
					7.508115957659544,
					75.08115957659629
				],
				[
					7.2659186687028985,
					75.32335686555302
				],
				[
					7.0237213797460845,
					75.56555415450984
				],
				[
					6.781524090789271,
					76.04994873242329
				],
				[
					6.781524090789271,
					76.2921460213801
				],
				[
					6.539326801832625,
					76.53434331033684
				],
				[
					6.539326801832625,
					76.77654059929365
				],
				[
					6.539326801832625,
					77.01873788825039
				],
				[
					6.297129512875812,
					77.50313246616392
				],
				[
					6.054932223918998,
					77.50313246616392
				],
				[
					6.054932223918998,
					77.74532975512065
				],
				[
					6.054932223918998,
					77.98752704407747
				],
				[
					6.054932223918998,
					78.2297243330342
				],
				[
					5.812734934962352,
					78.47192162199093
				],
				[
					5.812734934962352,
					78.47192162199093
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 442,
			"versionNonce": 1607639781,
			"isDeleted": false,
			"id": "_R48et8GO4syZ_Mav-Ics",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1173.844561795323,
			"y": 777.5294442037675,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.525108795616994,
			"height": 66.650963618322,
			"seed": 1494363051,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.3583385140769278,
					0.3583385140770117
				],
				[
					-0.7166770281540235,
					1.075015542230993
				],
				[
					-0.7166770281540235,
					1.7916925703849746
				],
				[
					-1.0750155422309513,
					2.86670811261601
				],
				[
					-1.433354056308047,
					3.2250466266930213
				],
				[
					-1.433354056308047,
					3.941723654847045
				],
				[
					-1.7916925703849746,
					4.658400683000984
				],
				[
					-2.1500310844619026,
					6.450093253386043
				],
				[
					-2.508369598538998,
					7.166770281539982
				],
				[
					-2.508369598538998,
					8.241785823771018
				],
				[
					-2.8667081126159255,
					9.67513988007898
				],
				[
					-3.2250466266930213,
					11.108493936387026
				],
				[
					-3.5833851407699493,
					12.183509478617978
				],
				[
					-3.5833851407699493,
					13.616863534926026
				],
				[
					-3.5833851407699493,
					14.333540563079964
				],
				[
					-3.5833851407699493,
					15.76689461938801
				],
				[
					-3.5833851407699493,
					16.841910161618962
				],
				[
					-3.5833851407699493,
					17.916925703849998
				],
				[
					-3.5833851407699493,
					18.63360273200402
				],
				[
					-3.5833851407699493,
					20.425295302388996
				],
				[
					-3.5833851407699493,
					21.50031084462003
				],
				[
					-3.2250466266930213,
					22.933664900927994
				],
				[
					-3.2250466266930213,
					24.008680443159026
				],
				[
					-2.8667081126159255,
					25.08369598538998
				],
				[
					-2.8667081126159255,
					26.158711527621016
				],
				[
					-2.508369598538998,
					27.23372706985205
				],
				[
					-2.508369598538998,
					28.667081126160014
				],
				[
					-2.1500310844619026,
					29.742096668391046
				],
				[
					-2.1500310844619026,
					31.17545072469901
				],
				[
					-2.1500310844619026,
					31.892127752853035
				],
				[
					-1.7916925703849746,
					32.967143295083986
				],
				[
					-1.7916925703849746,
					33.68382032323801
				],
				[
					-1.433354056308047,
					34.758835865469045
				],
				[
					-1.433354056308047,
					36.19218992177701
				],
				[
					-1.0750155422309513,
					37.26720546400804
				],
				[
					-1.0750155422309513,
					39.05889803439302
				],
				[
					-1.0750155422309513,
					40.49225209070106
				],
				[
					-1.0750155422309513,
					41.567267632932015
				],
				[
					-1.0750155422309513,
					42.642283175162966
				],
				[
					-1.0750155422309513,
					44.07563723147101
				],
				[
					-1.0750155422309513,
					44.79231425962504
				],
				[
					-1.0750155422309513,
					45.86732980185599
				],
				[
					-1.0750155422309513,
					46.94234534408702
				],
				[
					-1.0750155422309513,
					48.01736088631805
				],
				[
					-1.0750155422309513,
					48.734037914472
				],
				[
					-1.0750155422309513,
					49.80905345670303
				],
				[
					-1.0750155422309513,
					50.884068998933984
				],
				[
					-0.7166770281540235,
					52.67576156931904
				],
				[
					-0.3583385140769278,
					53.39243859747298
				],
				[
					-0.3583385140769278,
					54.46745413970402
				],
				[
					0,
					55.18413116785804
				],
				[
					0.35833851407709566,
					56.25914671008899
				],
				[
					0.7166770281540235,
					57.69250076639704
				],
				[
					1.0750155422309513,
					58.40917779455098
				],
				[
					1.0750155422309513,
					59.48419333678201
				],
				[
					1.433354056308047,
					60.55920887901305
				],
				[
					1.7916925703849746,
					61.27588590716707
				],
				[
					2.15003108446207,
					61.99256293532101
				],
				[
					2.15003108446207,
					62.70923996347503
				],
				[
					2.508369598538998,
					63.425916991628974
				],
				[
					2.508369598538998,
					64.14259401978299
				],
				[
					2.866708112616094,
					64.50093253386001
				],
				[
					2.866708112616094,
					65.21760956201403
				],
				[
					3.2250466266930213,
					65.57594807609105
				],
				[
					3.5833851407699493,
					65.93428659016797
				],
				[
					3.5833851407699493,
					66.29262510424506
				],
				[
					3.9417236548470447,
					66.650963618322
				],
				[
					3.9417236548470447,
					66.650963618322
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 396,
			"versionNonce": 910764523,
			"isDeleted": false,
			"id": "wMItIjI9EUdQrOsU5NoKt",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1187.8197638443262,
			"y": 777.8877827178446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.883447309694089,
			"height": 12.183509478617978,
			"seed": 818249291,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.3583385140770117
				],
				[
					-0.35833851407709566,
					-0.3583385140770117
				],
				[
					-0.7166770281540235,
					-0.3583385140770117
				],
				[
					-0.7166770281540235,
					0.3583385140770117
				],
				[
					-1.433354056308047,
					1.075015542230993
				],
				[
					-1.433354056308047,
					1.4333540563079628
				],
				[
					-2.1500310844619026,
					2.86670811261601
				],
				[
					-2.866708112616094,
					3.941723654846961
				],
				[
					-3.5833851407699493,
					5.016739197077996
				],
				[
					-4.300062168923972,
					5.73341622523202
				],
				[
					-5.016739197077996,
					7.166770281539983
				],
				[
					-5.73341622523202,
					7.883447309694006
				],
				[
					-6.091754739308947,
					8.60012433784803
				],
				[
					-6.808431767462971,
					8.958462851924958
				],
				[
					-7.1667702815400665,
					10.033478394155992
				],
				[
					-7.525108795616994,
					10.391816908233004
				],
				[
					-7.525108795616994,
					11.108493936387026
				],
				[
					-7.883447309694089,
					11.466832450463954
				],
				[
					-7.883447309694089,
					11.825170964540968
				],
				[
					-7.883447309694089,
					11.108493936387026
				],
				[
					-7.883447309694089,
					9.67513988007898
				],
				[
					-7.883447309694089,
					9.316801366001968
				],
				[
					-7.883447309694089,
					9.316801366001968
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 398,
			"versionNonce": 229047877,
			"isDeleted": false,
			"id": "8KLAYuG-kCIxsHz-6nJCa",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1181.3696705909401,
			"y": 774.6627360911514,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.525108795616994,
			"height": 14.33354056308005,
			"seed": 1739947243,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.35833851407709566,
					0
				],
				[
					0.7166770281540235,
					0.7166770281540235
				],
				[
					1.0750155422309513,
					1.075015542231035
				],
				[
					1.433354056308047,
					2.150031084461986
				],
				[
					1.7916925703851425,
					2.86670811261601
				],
				[
					2.15003108446207,
					3.5833851407700332
				],
				[
					2.508369598538998,
					4.658400683000984
				],
				[
					3.2250466266930213,
					5.73341622523202
				],
				[
					3.5833851407699493,
					6.450093253385958
				],
				[
					4.30006216892414,
					7.883447309694006
				],
				[
					4.30006216892414,
					8.241785823771018
				],
				[
					5.016739197077996,
					9.316801366002052
				],
				[
					5.375077711155092,
					10.033478394155992
				],
				[
					5.73341622523202,
					10.750155422310016
				],
				[
					6.091754739308947,
					11.46683245046404
				],
				[
					6.091754739308947,
					11.825170964541051
				],
				[
					6.450093253386043,
					12.183509478617978
				],
				[
					6.450093253386043,
					12.54184799269499
				],
				[
					6.808431767463138,
					13.258525020849014
				],
				[
					7.1667702815400665,
					13.258525020849014
				],
				[
					7.1667702815400665,
					13.616863534926026
				],
				[
					7.1667702815400665,
					13.975202049003038
				],
				[
					7.525108795616994,
					13.975202049003038
				],
				[
					7.525108795616994,
					14.33354056308005
				],
				[
					7.525108795616994,
					14.33354056308005
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 394,
			"versionNonce": 1124250763,
			"isDeleted": false,
			"id": "HXF393v0DRnWxdQPvALbT",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1186.0280712739414,
			"y": 780.3961523163837,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 4.300062168923972,
			"height": 6.091754739309031,
			"seed": 1231857547,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.35833851407692774,
					-0.3583385140770117
				],
				[
					0.7166770281540233,
					-0.3583385140770117
				],
				[
					1.075015542230951,
					-0.7166770281540235
				],
				[
					1.075015542230951,
					-1.433354056308005
				],
				[
					1.075015542230951,
					-1.7916925703850166
				],
				[
					1.4333540563078788,
					-2.150031084461986
				],
				[
					1.7916925703849744,
					-2.508369598538998
				],
				[
					1.7916925703849744,
					-2.86670811261601
				],
				[
					2.15003108446207,
					-3.2250466266930213
				],
				[
					2.15003108446207,
					-3.5833851407700332
				],
				[
					2.5083695985389975,
					-3.5833851407700332
				],
				[
					2.8667081126159255,
					-3.941723654847003
				],
				[
					2.8667081126159255,
					-4.300062168924015
				],
				[
					2.8667081126159255,
					-4.658400683000984
				],
				[
					3.2250466266930213,
					-4.658400683000984
				],
				[
					3.583385140769949,
					-5.016739197077996
				],
				[
					3.941723654846877,
					-5.375077711155008
				],
				[
					3.941723654846877,
					-5.73341622523202
				],
				[
					3.941723654846877,
					-6.091754739309031
				],
				[
					4.300062168923972,
					-6.091754739309031
				],
				[
					4.300062168923972,
					-6.091754739309031
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 450,
			"versionNonce": 1796795813,
			"isDeleted": false,
			"id": "eWpHbmlJDQ_zADCrKnRKA",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1182.4446861331714,
			"y": 797.5964009920795,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 13.258525020849014,
			"height": 16.841910161618962,
			"seed": 1277525547,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.35833851407701167
				],
				[
					0,
					0.7166770281540233
				],
				[
					0,
					1.4333540563080467
				],
				[
					0,
					1.7916925703849744
				],
				[
					0.35833851407709566,
					2.5083695985389975
				],
				[
					0.7166770281541913,
					3.2250466266930213
				],
				[
					1.7916925703851425,
					4.658400683001068
				],
				[
					2.15003108446207,
					5.375077711155007
				],
				[
					2.866708112616094,
					5.733416225232019
				],
				[
					3.5833851407701167,
					6.09175473930903
				],
				[
					4.30006216892414,
					6.09175473930903
				],
				[
					5.016739197077996,
					5.733416225232019
				],
				[
					5.733416225232188,
					4.658400683001068
				],
				[
					5.733416225232188,
					3.9417236548470442
				],
				[
					6.091754739309115,
					2.8667081126160094
				],
				[
					6.091754739309115,
					2.15003108446207
				],
				[
					6.450093253386043,
					1.4333540563080467
				],
				[
					6.450093253386043,
					0.35833851407701167
				],
				[
					6.808431767463138,
					-0.35833851407692774
				],
				[
					6.808431767463138,
					-0.7166770281540233
				],
				[
					6.808431767463138,
					-1.075015542230951
				],
				[
					6.808431767463138,
					-0.7166770281540233
				],
				[
					6.808431767463138,
					0
				],
				[
					6.808431767463138,
					0.7166770281540233
				],
				[
					6.808431767463138,
					2.8667081126160094
				],
				[
					6.808431767463138,
					3.9417236548470442
				],
				[
					6.808431767463138,
					5.733416225232019
				],
				[
					6.808431767463138,
					6.808431767463055
				],
				[
					6.808431767463138,
					7.525108795616993
				],
				[
					6.808431767463138,
					8.60012433784803
				],
				[
					6.808431767463138,
					9.316801366002052
				],
				[
					6.450093253386043,
					10.391816908233004
				],
				[
					5.733416225232188,
					12.18350947861806
				],
				[
					5.375077711155092,
					13.258525020849012
				],
				[
					4.658400683001068,
					13.975202049003036
				],
				[
					4.30006216892414,
					14.333540563080048
				],
				[
					3.9417236548470447,
					15.050217591233986
				],
				[
					3.5833851407701167,
					15.76689461938801
				],
				[
					3.225046626693189,
					15.76689461938801
				],
				[
					2.866708112616094,
					15.76689461938801
				],
				[
					2.508369598538998,
					15.76689461938801
				],
				[
					2.15003108446207,
					15.408556105311
				],
				[
					1.433354056308047,
					15.050217591233986
				],
				[
					1.0750155422311192,
					15.050217591233986
				],
				[
					0.7166770281541913,
					14.691879077157058
				],
				[
					0.35833851407709566,
					14.691879077157058
				],
				[
					0,
					14.333540563080048
				],
				[
					-0.7166770281538556,
					13.616863534926024
				],
				[
					-1.0750155422309513,
					12.18350947861806
				],
				[
					-1.0750155422309513,
					11.466832450464038
				],
				[
					-1.0750155422309513,
					10.391816908233004
				],
				[
					-0.7166770281538556,
					10.03347839415599
				],
				[
					-0.3583385140769278,
					9.675139880079062
				],
				[
					0,
					9.316801366002052
				],
				[
					0.7166770281541913,
					9.316801366002052
				],
				[
					1.0750155422311192,
					8.95846285192504
				],
				[
					1.7916925703851425,
					8.95846285192504
				],
				[
					2.508369598538998,
					8.95846285192504
				],
				[
					3.5833851407701167,
					8.95846285192504
				],
				[
					4.30006216892414,
					9.316801366002052
				],
				[
					4.658400683001068,
					9.316801366002052
				],
				[
					5.375077711155092,
					9.675139880079062
				],
				[
					6.091754739309115,
					10.03347839415599
				],
				[
					6.808431767463138,
					10.391816908233004
				],
				[
					7.1667702815400665,
					10.391816908233004
				],
				[
					7.525108795616994,
					10.750155422310014
				],
				[
					8.600124337848113,
					11.108493936387026
				],
				[
					8.958462851925042,
					11.466832450464038
				],
				[
					9.316801366002135,
					11.466832450464038
				],
				[
					9.675139880079064,
					11.82517096454105
				],
				[
					10.033478394155992,
					12.18350947861806
				],
				[
					10.750155422310185,
					12.541847992694988
				],
				[
					11.108493936387111,
					12.900186506772002
				],
				[
					11.46683245046404,
					12.900186506772002
				],
				[
					11.825170964541135,
					12.900186506772002
				],
				[
					12.183509478618062,
					12.900186506772002
				],
				[
					12.183509478618062,
					12.900186506772002
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 419,
			"versionNonce": 561113899,
			"isDeleted": false,
			"id": "mpY3eWbnXy9wyRAFoCwi_",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1182.4446861331714,
			"y": 825.1884665760085,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 12.900186506772085,
			"height": 17.200248675695974,
			"seed": 986349771,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.7166770281541913,
					0
				],
				[
					1.7916925703851425,
					0
				],
				[
					3.5833851407701167,
					0
				],
				[
					5.016739197077996,
					0
				],
				[
					6.091754739309115,
					0
				],
				[
					6.808431767463138,
					-0.35833851407701167
				],
				[
					7.883447309694089,
					-0.35833851407701167
				],
				[
					9.316801366002135,
					-0.35833851407701167
				],
				[
					10.391816908233087,
					-0.35833851407701167
				],
				[
					10.391816908233087,
					0.35833851407701167
				],
				[
					9.675139880079064,
					1.075015542230951
				],
				[
					7.883447309694089,
					2.8667081126160094
				],
				[
					6.808431767463138,
					5.016739197077995
				],
				[
					5.733416225232188,
					6.091754739308947
				],
				[
					4.658400683001068,
					7.883447309694005
				],
				[
					3.5833851407701167,
					10.03347839415599
				],
				[
					2.866708112616094,
					11.825170964540966
				],
				[
					2.508369598538998,
					12.541847992694988
				],
				[
					2.508369598538998,
					13.258525020848928
				],
				[
					2.508369598538998,
					13.616863534926024
				],
				[
					2.508369598538998,
					13.97520204900295
				],
				[
					2.508369598538998,
					14.691879077156974
				],
				[
					2.508369598538998,
					15.408556105311
				],
				[
					2.508369598538998,
					15.766894619387925
				],
				[
					2.866708112616094,
					16.48357164754195
				],
				[
					2.866708112616094,
					16.841910161618962
				],
				[
					3.225046626693189,
					16.841910161618962
				],
				[
					3.9417236548470447,
					16.841910161618962
				],
				[
					4.30006216892414,
					16.841910161618962
				],
				[
					5.016739197077996,
					16.841910161618962
				],
				[
					5.733416225232188,
					16.841910161618962
				],
				[
					6.808431767463138,
					16.841910161618962
				],
				[
					7.1667702815400665,
					16.841910161618962
				],
				[
					8.241785823771187,
					16.48357164754195
				],
				[
					8.958462851925042,
					16.12523313346502
				],
				[
					9.675139880079064,
					15.766894619387925
				],
				[
					10.391816908233087,
					15.050217591233986
				],
				[
					11.108493936387111,
					14.691879077156974
				],
				[
					11.825170964541135,
					14.333540563079964
				],
				[
					12.183509478618062,
					13.97520204900295
				],
				[
					12.54184799269499,
					13.97520204900295
				],
				[
					12.900186506772085,
					13.97520204900295
				],
				[
					12.900186506772085,
					13.616863534926024
				],
				[
					12.900186506772085,
					13.258525020848928
				],
				[
					12.183509478618062,
					12.900186506772002
				],
				[
					12.183509478618062,
					12.900186506772002
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 390,
			"versionNonce": 1465250053,
			"isDeleted": false,
			"id": "_xXGbU0YWWr1N_-ZMzHmB",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1183.8780401894792,
			"y": 831.2802213153174,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 11.108493936386942,
			"height": 0.3583385140770117,
			"seed": 519450475,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.3583385140770117
				],
				[
					0.3583385140770956,
					0.3583385140770117
				],
				[
					1.7916925703851423,
					0.3583385140770117
				],
				[
					3.2250466266930213,
					0.3583385140770117
				],
				[
					4.30006216892414,
					0.3583385140770117
				],
				[
					5.375077711155091,
					0.3583385140770117
				],
				[
					7.166770281540066,
					0.3583385140770117
				],
				[
					7.525108795616993,
					0.3583385140770117
				],
				[
					7.8834473096940885,
					0.3583385140770117
				],
				[
					8.600124337847944,
					0.3583385140770117
				],
				[
					9.316801366002135,
					0.3583385140770117
				],
				[
					9.675139880079062,
					0.3583385140770117
				],
				[
					10.03347839415599,
					0.3583385140770117
				],
				[
					10.391816908233087,
					0.3583385140770117
				],
				[
					10.750155422310014,
					0
				],
				[
					11.108493936386942,
					0
				],
				[
					11.108493936386942,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 449,
			"versionNonce": 1711361483,
			"isDeleted": false,
			"id": "xzeW9sYvjMtTFmcvT-qRF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1195.3448726399433,
			"y": 777.8877827178446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 9.316801366001968,
			"height": 67.009302132399,
			"seed": 1794312715,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3583385140770956,
					0
				],
				[
					0.7166770281540233,
					0.35833851407701167
				],
				[
					1.075015542230951,
					0.7166770281539814
				],
				[
					1.4333540563080467,
					1.075015542230993
				],
				[
					2.150031084461902,
					1.7916925703849744
				],
				[
					2.5083695985389975,
					2.5083695985389975
				],
				[
					3.2250466266930213,
					2.8667081126160094
				],
				[
					3.9417236548470442,
					4.300062168923972
				],
				[
					4.300062168923972,
					5.375077711155007
				],
				[
					4.658400683001068,
					6.80843176746297
				],
				[
					5.016739197077995,
					7.525108795616993
				],
				[
					5.375077711155091,
					8.958462851924956
				],
				[
					6.091754739308947,
					11.108493936387026
				],
				[
					6.091754739308947,
					11.825170964540966
				],
				[
					6.450093253386043,
					13.258525020849012
				],
				[
					6.80843176746297,
					14.333540563079964
				],
				[
					6.80843176746297,
					15.050217591233986
				],
				[
					7.166770281540066,
					16.48357164754195
				],
				[
					7.166770281540066,
					17.200248675695974
				],
				[
					7.525108795616993,
					18.633602732004018
				],
				[
					7.8834473096940885,
					19.350279760158042
				],
				[
					8.241785823771016,
					20.783633816466008
				],
				[
					8.241785823771016,
					21.85864935869704
				],
				[
					8.241785823771016,
					22.93366490092799
				],
				[
					8.600124337847944,
					24.725357471312964
				],
				[
					8.95846285192504,
					26.158711527621012
				],
				[
					8.95846285192504,
					26.875388555775036
				],
				[
					9.316801366001968,
					28.308742612082998
				],
				[
					9.316801366001968,
					29.383758154314034
				],
				[
					9.316801366001968,
					30.458773696544984
				],
				[
					9.316801366001968,
					31.53378923877602
				],
				[
					9.316801366001968,
					32.60880478100697
				],
				[
					9.316801366001968,
					34.04215883731502
				],
				[
					9.316801366001968,
					35.11717437954597
				],
				[
					9.316801366001968,
					36.19218992177701
				],
				[
					9.316801366001968,
					37.26720546400795
				],
				[
					9.316801366001968,
					38.700559520316
				],
				[
					9.316801366001968,
					39.775575062546956
				],
				[
					9.316801366001968,
					40.85059060477799
				],
				[
					9.316801366001968,
					42.283944661085954
				],
				[
					8.95846285192504,
					43.00062168923998
				],
				[
					8.95846285192504,
					44.43397574554802
				],
				[
					8.95846285192504,
					45.86732980185598
				],
				[
					8.95846285192504,
					46.942345344087016
				],
				[
					8.600124337847944,
					48.375699400394986
				],
				[
					8.600124337847944,
					49.450714942626014
				],
				[
					8.600124337847944,
					50.525730484856965
				],
				[
					8.600124337847944,
					51.60074602708801
				],
				[
					8.600124337847944,
					52.317423055242024
				],
				[
					8.600124337847944,
					53.392438597472974
				],
				[
					8.600124337847944,
					53.750777111549986
				],
				[
					8.600124337847944,
					54.46745413970401
				],
				[
					8.600124337847944,
					54.82579265378102
				],
				[
					8.600124337847944,
					55.90080819601197
				],
				[
					8.600124337847944,
					56.259146710088984
				],
				[
					8.241785823771016,
					57.33416225232002
				],
				[
					8.241785823771016,
					57.69250076639703
				],
				[
					7.8834473096940885,
					58.76751630862798
				],
				[
					7.8834473096940885,
					59.125854822704994
				],
				[
					7.525108795616993,
					59.84253185085902
				],
				[
					7.166770281540066,
					60.55920887901296
				],
				[
					6.80843176746297,
					60.917547393090054
				],
				[
					6.450093253386043,
					61.634224421244
				],
				[
					6.450093253386043,
					61.99256293532101
				],
				[
					6.091754739308947,
					62.70923996347503
				],
				[
					5.733416225232019,
					63.42591699162906
				],
				[
					5.733416225232019,
					63.78425550570597
				],
				[
					5.375077711155091,
					64.50093253386001
				],
				[
					5.016739197077995,
					64.85927104793701
				],
				[
					5.016739197077995,
					65.21760956201402
				],
				[
					5.016739197077995,
					65.57594807609095
				],
				[
					4.658400683001068,
					65.93428659016804
				],
				[
					4.658400683001068,
					66.29262510424498
				],
				[
					4.300062168923972,
					66.65096361832198
				],
				[
					4.300062168923972,
					67.009302132399
				],
				[
					4.300062168923972,
					67.009302132399
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 391,
			"versionNonce": 1876658277,
			"isDeleted": false,
			"id": "1kt1KXlqcMZihZXE5_K3W",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1216.1285064564092,
			"y": 802.6131401891575,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 13.258525020849014,
			"height": 0.7166770281540235,
			"seed": 1673236651,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3583385140769278,
					0
				],
				[
					1.433354056308047,
					0
				],
				[
					2.508369598538998,
					0
				],
				[
					3.2250466266930213,
					0
				],
				[
					3.9417236548470447,
					0
				],
				[
					5.016739197077996,
					0
				],
				[
					6.091754739308947,
					0.3583385140770117
				],
				[
					6.808431767462971,
					0.3583385140770117
				],
				[
					8.241785823771018,
					0.3583385140770117
				],
				[
					8.600124337848113,
					0.3583385140770117
				],
				[
					9.316801366001968,
					0.3583385140770117
				],
				[
					10.033478394155992,
					0.7166770281540235
				],
				[
					10.750155422310016,
					0.7166770281540235
				],
				[
					11.46683245046404,
					0.7166770281540235
				],
				[
					12.183509478618062,
					0.7166770281540235
				],
				[
					12.54184799269499,
					0.7166770281540235
				],
				[
					12.900186506771917,
					0.7166770281540235
				],
				[
					13.258525020849014,
					0.7166770281540235
				],
				[
					13.258525020849014,
					0.7166770281540235
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 389,
			"versionNonce": 868965483,
			"isDeleted": false,
			"id": "YH1tU07dhAk0Lhd_sx3_F",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1216.486844970486,
			"y": 809.0632334425435,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 12.183509478618062,
			"height": 0.3583385140770117,
			"seed": 1257915211,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.35833851407709566,
					0
				],
				[
					1.0750155422311192,
					0
				],
				[
					2.508369598538998,
					0
				],
				[
					3.5833851407701167,
					0
				],
				[
					5.375077711155092,
					0
				],
				[
					6.091754739309115,
					0
				],
				[
					7.525108795616994,
					0
				],
				[
					8.241785823771187,
					0
				],
				[
					8.958462851925042,
					0.3583385140770117
				],
				[
					9.675139880079064,
					0.3583385140770117
				],
				[
					10.033478394155992,
					0.3583385140770117
				],
				[
					10.391816908233087,
					0.3583385140770117
				],
				[
					11.108493936387111,
					0.3583385140770117
				],
				[
					11.46683245046404,
					0.3583385140770117
				],
				[
					11.825170964541135,
					0.3583385140770117
				],
				[
					12.183509478618062,
					0.3583385140770117
				],
				[
					12.183509478618062,
					0.3583385140770117
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 444,
			"versionNonce": 1182217157,
			"isDeleted": false,
			"id": "MA3gt3r82FUbfNy_9_oKc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1263.0708518004965,
			"y": 775.7377516333825,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 15.766894619388012,
			"height": 71.30936430132297,
			"seed": 1225368043,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.35833851407709566,
					0
				],
				[
					0.35833851407709566,
					0.3583385140769697
				],
				[
					0.35833851407709566,
					1.4333540563079625
				],
				[
					0,
					2.1500310844619857
				],
				[
					0,
					2.8667081126159673
				],
				[
					-0.3583385140769278,
					3.9417236548469603
				],
				[
					-0.7166770281538556,
					5.016739197077996
				],
				[
					-0.7166770281538556,
					5.733416225232019
				],
				[
					-1.0750155422309513,
					6.450093253385958
				],
				[
					-1.0750155422309513,
					6.80843176746297
				],
				[
					-1.0750155422309513,
					7.883447309694004
				],
				[
					-1.0750155422309513,
					8.600124337847943
				],
				[
					-1.0750155422309513,
					9.675139880078978
				],
				[
					-1.0750155422309513,
					10.750155422310014
				],
				[
					-1.0750155422309513,
					12.183509478617976
				],
				[
					-1.0750155422309513,
					12.900186506772
				],
				[
					-1.0750155422309513,
					14.691879077156974
				],
				[
					-1.0750155422309513,
					16.12523313346494
				],
				[
					-1.0750155422309513,
					17.916925703849994
				],
				[
					-1.0750155422309513,
					19.350279760157957
				],
				[
					-1.0750155422309513,
					21.14197233054293
				],
				[
					-1.0750155422309513,
					22.57532638685098
				],
				[
					-1.0750155422309513,
					24.367018957235953
				],
				[
					-1.0750155422309513,
					25.800373013544
				],
				[
					-1.0750155422309513,
					27.233727069851962
				],
				[
					-1.0750155422309513,
					28.308742612082998
				],
				[
					-1.0750155422309513,
					29.74209666839096
				],
				[
					-1.0750155422309513,
					30.817112210621996
				],
				[
					-1.0750155422309513,
					32.96714329508398
				],
				[
					-1.0750155422309513,
					34.75883586546896
				],
				[
					-0.7166770281538556,
					36.55052843585402
				],
				[
					-0.7166770281538556,
					37.62554397808496
				],
				[
					-0.3583385140769278,
					39.05889803439301
				],
				[
					-0.3583385140769278,
					40.850590604777985
				],
				[
					0,
					42.28394466108603
				],
				[
					0.35833851407709566,
					43.717298717393994
				],
				[
					0.35833851407709566,
					45.15065277370196
				],
				[
					0.7166770281541913,
					46.584006830010004
				],
				[
					1.0750155422311192,
					47.65902237224096
				],
				[
					1.7916925703851425,
					49.450714942626014
				],
				[
					2.15003108446207,
					50.88406899893398
				],
				[
					2.508369598538998,
					51.95908454116501
				],
				[
					2.866708112616094,
					53.03410008339596
				],
				[
					3.225046626693189,
					54.109115625627
				],
				[
					3.5833851407701167,
					55.54246968193496
				],
				[
					3.9417236548470447,
					56.259146710088984
				],
				[
					4.658400683001068,
					57.33416225232002
				],
				[
					5.016739197077996,
					58.40917779455097
				],
				[
					5.375077711155092,
					59.84253185085902
				],
				[
					5.733416225232188,
					60.91754739308997
				],
				[
					6.091754739309115,
					61.992562935321004
				],
				[
					6.450093253386043,
					63.06757847755203
				],
				[
					6.808431767463138,
					63.784255505705985
				],
				[
					7.1667702815400665,
					64.14259401978298
				],
				[
					7.525108795616994,
					64.50093253386
				],
				[
					7.525108795616994,
					65.21760956201395
				],
				[
					8.241785823771187,
					65.57594807609104
				],
				[
					8.958462851925042,
					66.29262510424498
				],
				[
					9.675139880079064,
					67.009302132399
				],
				[
					10.033478394155992,
					67.367640646476
				],
				[
					10.391816908233087,
					67.72597916055294
				],
				[
					11.108493936387111,
					68.44265618870696
				],
				[
					11.46683245046404,
					68.80099470278397
				],
				[
					12.183509478618062,
					69.15933321686099
				],
				[
					12.54184799269499,
					69.51767173093799
				],
				[
					13.258525020849182,
					70.23434875909201
				],
				[
					13.616863534926111,
					70.59268727316903
				],
				[
					13.975202049003038,
					70.59268727316903
				],
				[
					14.69187907715706,
					70.95102578724597
				],
				[
					14.69187907715706,
					71.30936430132297
				],
				[
					14.69187907715706,
					71.30936430132297
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 425,
			"versionNonce": 1721407243,
			"isDeleted": false,
			"id": "6gHIpGQ6igjRYEZTIb-7o",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1278.873835667992,
			"y": 779.0180129147552,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.016739197077996,
			"height": 11.825170964540968,
			"seed": 110089323,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.3583385140770956,
					0
				],
				[
					-0.7166770281540233,
					0.7166770281539814
				],
				[
					-1.4333540563080467,
					1.7916925703849746
				],
				[
					-2.15003108446207,
					2.8667081126159255
				],
				[
					-2.8667081126160934,
					3.941723654846961
				],
				[
					-3.9417236548470447,
					6.808431767462971
				],
				[
					-4.30006216892414,
					8.241785823771018
				],
				[
					-4.658400683001068,
					8.958462851924958
				],
				[
					-4.658400683001068,
					9.67513988007898
				],
				[
					-4.658400683001068,
					10.750155422310016
				],
				[
					-5.016739197077996,
					11.108493936386942
				],
				[
					-5.016739197077996,
					11.466832450463954
				],
				[
					-5.016739197077996,
					11.825170964540968
				],
				[
					-5.016739197077996,
					11.825170964540968
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 434,
			"versionNonce": 1464234789,
			"isDeleted": false,
			"id": "22240XD4c4TrEJpnSbs3w",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1273.3387468065337,
			"y": 779.2276059060017,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.091754739309115,
			"height": 12.54184799269499,
			"seed": 1511001867,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.7166770281541913,
					0.7166770281540235
				],
				[
					1.433354056308047,
					2.508369598538998
				],
				[
					1.7916925703851425,
					3.5833851407699493
				],
				[
					2.508369598538998,
					4.658400683000984
				],
				[
					3.225046626693189,
					6.091754739309031
				],
				[
					3.5833851407701167,
					7.525108795616994
				],
				[
					3.9417236548470447,
					8.241785823771018
				],
				[
					4.658400683001068,
					9.316801366001968
				],
				[
					5.016739197077996,
					10.033478394155992
				],
				[
					5.016739197077996,
					10.391816908233004
				],
				[
					5.375077711155092,
					11.108493936387026
				],
				[
					5.733416225232188,
					11.46683245046404
				],
				[
					5.733416225232188,
					12.183509478617978
				],
				[
					6.091754739309115,
					12.183509478617978
				],
				[
					6.091754739309115,
					12.54184799269499
				],
				[
					6.091754739309115,
					12.54184799269499
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 494,
			"versionNonce": 2095676843,
			"isDeleted": false,
			"id": "raYsO10PzCfH_j6kOOwf9",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1276.243771132621,
			"y": 802.8227331804038,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 9.316801366002135,
			"height": 18.991941246081034,
			"seed": 1894166923,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.35833851407709566
				],
				[
					0,
					0.7166770281540236
				],
				[
					0,
					1.7916925703850586
				],
				[
					0.35833851407709555,
					2.8667081126160943
				],
				[
					0.7166770281540232,
					3.941723654847045
				],
				[
					1.0750155422309509,
					5.733416225232021
				],
				[
					1.0750155422309509,
					6.8084317674630555
				],
				[
					1.4333540563080465,
					7.166770281540067
				],
				[
					1.4333540563080465,
					7.525108795617079
				],
				[
					1.7916925703849742,
					7.525108795617079
				],
				[
					2.1500310844619017,
					7.525108795617079
				],
				[
					2.5083695985389975,
					6.450093253386044
				],
				[
					2.5083695985389975,
					5.375077711155092
				],
				[
					2.5083695985389975,
					4.3000621689240575
				],
				[
					2.866708112616093,
					3.5833851407700337
				],
				[
					3.225046626693021,
					2.5083695985390824
				],
				[
					3.225046626693021,
					1.7916925703850586
				],
				[
					3.5833851407699484,
					0.7166770281540236
				],
				[
					3.5833851407699484,
					0.35833851407709566
				],
				[
					3.9417236548470442,
					-0.7166770281539396
				],
				[
					3.9417236548470442,
					-1.0750155422309513
				],
				[
					4.300062168923971,
					-2.1500310844619026
				],
				[
					4.658400683000899,
					-2.866708112615926
				],
				[
					4.658400683000899,
					-3.225046626692938
				],
				[
					5.016739197077995,
					-3.5833851407699497
				],
				[
					5.016739197077995,
					-3.225046626692938
				],
				[
					5.016739197077995,
					-2.1500310844619026
				],
				[
					5.016739197077995,
					-1.433354056307963
				],
				[
					5.016739197077995,
					-0.35833851407692785
				],
				[
					5.016739197077995,
					0.35833851407709566
				],
				[
					5.3750777111550905,
					1.7916925703850586
				],
				[
					5.3750777111550905,
					2.5083695985390824
				],
				[
					5.3750777111550905,
					3.225046626693022
				],
				[
					5.3750777111550905,
					3.941723654847045
				],
				[
					5.3750777111550905,
					5.01673919707808
				],
				[
					5.3750777111550905,
					6.450093253386044
				],
				[
					5.3750777111550905,
					7.88344730969409
				],
				[
					5.3750777111550905,
					9.316801366002053
				],
				[
					5.016739197077995,
					10.033478394156077
				],
				[
					4.658400683000899,
					11.108493936387028
				],
				[
					4.300062168923971,
					11.466832450464041
				],
				[
					3.9417236548470442,
					12.183509478618063
				],
				[
					3.5833851407699484,
					12.541847992695077
				],
				[
					3.5833851407699484,
					12.900186506772087
				],
				[
					2.866708112616093,
					13.258525020849016
				],
				[
					2.5083695985389975,
					13.616863534926026
				],
				[
					2.1500310844619017,
					13.616863534926026
				],
				[
					1.7916925703849742,
					13.616863534926026
				],
				[
					1.4333540563080465,
					13.616863534926026
				],
				[
					0.7166770281540232,
					13.616863534926026
				],
				[
					0.35833851407709555,
					13.258525020849016
				],
				[
					-0.35833851407709555,
					12.900186506772087
				],
				[
					-0.7166770281540232,
					12.541847992695077
				],
				[
					-1.4333540563080465,
					12.183509478618063
				],
				[
					-1.0750155422309509,
					12.183509478618063
				],
				[
					-0.7166770281540232,
					11.825170964541051
				],
				[
					-0.35833851407709555,
					11.466832450464041
				],
				[
					0,
					11.466832450464041
				],
				[
					0.7166770281540232,
					11.466832450464041
				],
				[
					1.0750155422309509,
					11.466832450464041
				],
				[
					1.7916925703849742,
					12.183509478618063
				],
				[
					2.1500310844619017,
					12.541847992695077
				],
				[
					2.5083695985389975,
					12.541847992695077
				],
				[
					3.225046626693021,
					13.258525020849016
				],
				[
					3.5833851407699484,
					13.616863534926026
				],
				[
					3.9417236548470442,
					13.616863534926026
				],
				[
					4.658400683000899,
					14.333540563080051
				],
				[
					5.016739197077995,
					14.333540563080051
				],
				[
					5.3750777111550905,
					14.691879077157061
				],
				[
					5.733416225232018,
					14.691879077157061
				],
				[
					6.091754739308946,
					15.050217591234073
				],
				[
					6.450093253386042,
					15.050217591234073
				],
				[
					7.166770281539897,
					15.050217591234073
				],
				[
					7.525108795616992,
					15.408556105311085
				],
				[
					7.8834473096940885,
					15.408556105311085
				],
				[
					7.8834473096940885,
					15.408556105311085
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 475,
			"versionNonce": 1052165765,
			"isDeleted": false,
			"id": "zOKiy4erHWg4N7qxF-JRX",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1281.1996628612833,
			"y": 826.4561766682774,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 9.675139880079064,
			"height": 12.900186506772002,
			"seed": 1209537547,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.35833851407692774,
					0
				],
				[
					0.7166770281540233,
					0
				],
				[
					1.7916925703849744,
					0
				],
				[
					2.866708112615925,
					0
				],
				[
					3.225046626693021,
					0
				],
				[
					3.9417236548470447,
					0
				],
				[
					4.658400683001068,
					0
				],
				[
					5.016739197077996,
					0
				],
				[
					5.3750777111549235,
					0
				],
				[
					5.733416225232019,
					0.3583385140770117
				],
				[
					6.091754739309114,
					0.3583385140770117
				],
				[
					5.733416225232019,
					0.7166770281540235
				],
				[
					4.658400683001068,
					1.433354056308047
				],
				[
					3.5833851407701167,
					2.150031084461986
				],
				[
					2.508369598538998,
					2.86670811261601
				],
				[
					1.4333540563080467,
					3.5833851407700332
				],
				[
					0.7166770281540233,
					4.300062168924057
				],
				[
					0,
					5.375077711155008
				],
				[
					-0.35833851407692774,
					5.73341622523202
				],
				[
					-0.7166770281540233,
					6.8084317674630555
				],
				[
					-1.075015542230951,
					7.166770281539983
				],
				[
					-1.075015542230951,
					8.241785823771018
				],
				[
					-1.4333540563078788,
					8.60012433784803
				],
				[
					-1.4333540563078788,
					9.316801366002052
				],
				[
					-1.7916925703849744,
					10.033478394156077
				],
				[
					-1.7916925703849744,
					10.391816908233004
				],
				[
					-2.15003108446207,
					10.750155422310016
				],
				[
					-2.508369598538998,
					11.108493936387026
				],
				[
					-2.508369598538998,
					11.46683245046404
				],
				[
					-3.225046626693021,
					11.825170964541051
				],
				[
					-3.225046626693021,
					12.183509478617978
				],
				[
					-3.583385140769949,
					12.541847992695075
				],
				[
					-3.583385140769949,
					12.900186506772002
				],
				[
					-3.225046626693021,
					12.900186506772002
				],
				[
					-2.866708112615925,
					12.900186506772002
				],
				[
					-2.508369598538998,
					12.900186506772002
				],
				[
					-1.4333540563078788,
					12.900186506772002
				],
				[
					-0.7166770281540233,
					12.900186506772002
				],
				[
					0,
					12.900186506772002
				],
				[
					0.7166770281540233,
					12.900186506772002
				],
				[
					1.075015542231119,
					12.900186506772002
				],
				[
					1.7916925703849744,
					12.900186506772002
				],
				[
					2.15003108446207,
					12.900186506772002
				],
				[
					2.866708112615925,
					12.900186506772002
				],
				[
					3.225046626693021,
					12.900186506772002
				],
				[
					3.5833851407701167,
					12.900186506772002
				],
				[
					3.9417236548470447,
					12.900186506772002
				],
				[
					4.300062168923971,
					12.900186506772002
				],
				[
					4.300062168923971,
					12.900186506772002
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 436,
			"versionNonce": 1105367115,
			"isDeleted": false,
			"id": "tK3-kjSCBYVWONtm6XEZs",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1284.176800283259,
			"y": 826.3017983317106,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.091754739309115,
			"height": 0,
			"seed": 732912299,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.0750155422311192,
					0
				],
				[
					-1.7916925703849746,
					0
				],
				[
					-2.508369598538998,
					0
				],
				[
					-3.2250466266930213,
					0
				],
				[
					-3.9417236548470447,
					0
				],
				[
					-4.300062168923972,
					0
				],
				[
					-4.658400683001068,
					0
				],
				[
					-5.016739197077996,
					0
				],
				[
					-5.3750777111549235,
					0
				],
				[
					-5.73341622523202,
					0
				],
				[
					-6.091754739309115,
					0
				],
				[
					-6.091754739309115,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 434,
			"versionNonce": 797289957,
			"isDeleted": false,
			"id": "ECZ8-jUVb_lTlVpeRX7N9",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1277.5610630658337,
			"y": 832.9614845763433,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.166770281539899,
			"height": 0,
			"seed": 904187211,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.7166770281538556,
					0
				],
				[
					1.433354056308047,
					0
				],
				[
					1.7916925703849746,
					0
				],
				[
					2.8667081126159255,
					0
				],
				[
					3.2250466266928535,
					0
				],
				[
					3.9417236548470447,
					0
				],
				[
					4.300062168923972,
					0
				],
				[
					5.016739197077996,
					0
				],
				[
					5.3750777111549235,
					0
				],
				[
					5.733416225231851,
					0
				],
				[
					6.091754739308947,
					0
				],
				[
					6.808431767462971,
					0
				],
				[
					7.166770281539899,
					0
				],
				[
					7.166770281539899,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 531,
			"versionNonce": 929058539,
			"isDeleted": false,
			"id": "8AoPilMdDj5lWj0_QLUgJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1377.3857690862324,
			"y": 778.2989953397367,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.883447309693922,
			"height": 65.575948076091,
			"seed": 1242754027,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.35833851407692785,
					0
				],
				[
					0.7166770281540236,
					0.35833851407701167
				],
				[
					1.0750155422309515,
					1.4333540563080047
				],
				[
					1.7916925703849749,
					2.866708112616051
				],
				[
					2.1500310844620705,
					3.583385140769991
				],
				[
					2.5083695985389984,
					4.658400683001026
				],
				[
					2.866708112615926,
					6.091754739308988
				],
				[
					3.5833851407699497,
					8.958462851924997
				],
				[
					3.9417236548468777,
					10.391816908233045
				],
				[
					4.300062168923973,
					12.183509478618019
				],
				[
					5.016739197077997,
					13.975202049002993
				],
				[
					5.375077711154924,
					15.766894619387969
				],
				[
					5.733416225232021,
					17.916925703850037
				],
				[
					6.091754739308948,
					19.350279760158
				],
				[
					6.091754739308948,
					20.425295302389035
				],
				[
					6.450093253385877,
					21.858649358696997
				],
				[
					6.808431767462972,
					24.008680443158983
				],
				[
					7.166770281540067,
					25.08369598539002
				],
				[
					7.166770281540067,
					26.517050041697985
				],
				[
					7.166770281540067,
					27.95040409800603
				],
				[
					7.525108795616995,
					29.38375815431399
				],
				[
					7.525108795616995,
					30.81711221062204
				],
				[
					7.883447309693922,
					31.892127752852986
				],
				[
					7.883447309693922,
					33.32548180916104
				],
				[
					7.883447309693922,
					34.400497351391984
				],
				[
					7.883447309693922,
					35.83385140770003
				],
				[
					7.883447309693922,
					37.26720546400799
				],
				[
					7.883447309693922,
					37.98388249216202
				],
				[
					7.883447309693922,
					38.70055952031605
				],
				[
					7.883447309693922,
					40.13391357662401
				],
				[
					7.883447309693922,
					41.20892911885504
				],
				[
					7.883447309693922,
					42.283944661086
				],
				[
					7.883447309693922,
					43.358960203317025
				],
				[
					7.883447309693922,
					44.43397574554806
				],
				[
					7.883447309693922,
					45.86732980185602
				],
				[
					7.525108795616995,
					46.94234534408706
				],
				[
					7.525108795616995,
					48.01736088631801
				],
				[
					7.525108795616995,
					49.092376428549045
				],
				[
					7.166770281540067,
					49.80905345670298
				],
				[
					7.166770281540067,
					50.52573048485701
				],
				[
					7.166770281540067,
					51.60074602708804
				],
				[
					7.166770281540067,
					52.31742305524199
				],
				[
					7.166770281540067,
					53.034100083396005
				],
				[
					7.166770281540067,
					53.39243859747302
				],
				[
					7.166770281540067,
					53.75077711155003
				],
				[
					7.166770281540067,
					54.82579265378098
				],
				[
					7.166770281540067,
					55.18413116785799
				],
				[
					7.166770281540067,
					55.900808196012015
				],
				[
					6.808431767462972,
					56.61748522416604
				],
				[
					6.450093253385877,
					57.69250076639699
				],
				[
					6.450093253385877,
					58.050839280474
				],
				[
					6.450093253385877,
					58.767516308628025
				],
				[
					6.091754739308948,
					59.12585482270504
				],
				[
					6.091754739308948,
					59.48419333678205
				],
				[
					5.375077711154924,
					60.20087036493607
				],
				[
					5.375077711154924,
					60.559208879013
				],
				[
					5.016739197077997,
					61.27588590716702
				],
				[
					5.016739197077997,
					61.634224421244035
				],
				[
					4.6584006830010685,
					61.992562935321054
				],
				[
					4.300062168923973,
					62.70923996347507
				],
				[
					3.9417236548468777,
					63.067578477552
				],
				[
					3.5833851407699497,
					63.425916991629016
				],
				[
					3.5833851407699497,
					63.784255505706014
				],
				[
					3.5833851407699497,
					64.50093253386004
				],
				[
					3.225046626693022,
					64.85927104793697
				],
				[
					3.225046626693022,
					65.21760956201408
				],
				[
					2.866708112615926,
					65.21760956201408
				],
				[
					2.866708112615926,
					65.575948076091
				],
				[
					2.5083695985389984,
					65.575948076091
				],
				[
					2.5083695985389984,
					65.575948076091
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "arrow",
			"version": 1053,
			"versionNonce": 2090060891,
			"isDeleted": false,
			"id": "BeG12LlljrdmLA3OWJfrL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 718.3682922665093,
			"y": 442.5512072058053,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 274.2193689159203,
			"height": 303.03166427428084,
			"seed": 994066571,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702995800935,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "FsIf1pbSBkEiTP0PpjiaC",
				"gap": 5.646246235790201,
				"focus": -0.14064099272788663
			},
			"endBinding": {
				"elementId": "8dU7Dri40eymffhDKBlJh",
				"focus": -0.2913210024695778,
				"gap": 2.365659170617562
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
					166.54565619889752,
					35.22042128235165
				],
				[
					184.8720819067878,
					275.5465382330051
				],
				[
					274.2193689159203,
					303.03166427428084
				]
			]
		},
		{
			"type": "freedraw",
			"version": 649,
			"versionNonce": 1072511371,
			"isDeleted": false,
			"id": "-8usYQkyHgIlxJpRS4iQA",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1150.6192587791743,
			"y": 690.1310441487956,
			"strokeColor": "#e03131",
			"backgroundColor": "#deede1",
			"width": 23.71029102309206,
			"height": 25.388895697293112,
			"seed": 36377067,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20982558427508932
				],
				[
					0,
					0.6294767528254359
				],
				[
					-0.20982558427500544,
					1.0491279213756985
				],
				[
					-0.4196511685501787,
					1.4687790899260451
				],
				[
					-0.8393023371005253,
					1.6786046742011342
				],
				[
					-1.4687790899260451,
					2.098255842751481
				],
				[
					-1.8884302584762238,
					2.5179070113017437
				],
				[
					-2.0982558427513975,
					2.7277325955769167
				],
				[
					-2.7277325955769167,
					3.1473837641271794
				],
				[
					-3.147383764127096,
					3.567034932677526
				],
				[
					-3.7768605169526155,
					4.196511685502962
				],
				[
					-4.196511685502962,
					4.616162854053225
				],
				[
					-4.406337269778136,
					4.825988438328397
				],
				[
					-4.825988438328315,
					5.245639606878744
				],
				[
					-5.24563960687866,
					5.8751163597041804
				],
				[
					-5.665290775429007,
					6.294767528254443
				],
				[
					-5.8751163597041804,
					6.714418696804789
				],
				[
					-6.29476752825436,
					7.134069865355052
				],
				[
					-6.924244281079879,
					7.973372202455661
				],
				[
					-7.134069865355053,
					8.393023371005924
				],
				[
					-7.553721033905231,
					8.812674539556271
				],
				[
					-7.973372202455578,
					9.442151292381705
				],
				[
					-8.18319778673075,
					9.65197687665688
				],
				[
					-8.393023371005924,
					10.071628045207142
				],
				[
					-8.602848955281097,
					10.281453629482316
				],
				[
					-9.022500123831275,
					10.281453629482316
				],
				[
					-9.442151292381622,
					10.281453629482316
				],
				[
					-9.651976876656795,
					10.281453629482316
				],
				[
					-10.071628045207142,
					10.281453629482316
				],
				[
					-10.491279213757489,
					10.281453629482316
				],
				[
					-10.910930382307667,
					10.491279213757489
				],
				[
					-11.120755966582841,
					10.701104798032578
				],
				[
					-11.540407135133187,
					10.701104798032578
				],
				[
					-11.750232719408361,
					10.910930382307752
				],
				[
					-11.750232719408361,
					11.120755966582925
				],
				[
					-11.960058303683534,
					11.120755966582925
				],
				[
					-11.960058303683534,
					10.701104798032578
				],
				[
					-11.960058303683534,
					10.071628045207142
				],
				[
					-11.750232719408361,
					9.65197687665688
				],
				[
					-11.540407135133187,
					9.022500123831444
				],
				[
					-11.120755966582841,
					7.973372202455661
				],
				[
					-10.701104798032494,
					6.924244281079878
				],
				[
					-10.281453629482316,
					6.294767528254443
				],
				[
					-9.651976876656795,
					5.035814022603571
				],
				[
					-9.442151292381622,
					4.825988438328397
				],
				[
					-9.022500123831275,
					4.406337269778136
				],
				[
					-8.602848955281097,
					3.567034932677526
				],
				[
					-8.393023371005924,
					2.9375581798520902
				],
				[
					-7.973372202455578,
					2.308081427026654
				],
				[
					-7.763546618180405,
					1.8884302584763075
				],
				[
					-7.134069865355053,
					1.2589535056508718
				],
				[
					-6.924244281079879,
					0.6294767528254359
				],
				[
					-6.504593112529533,
					0.20982558427508932
				],
				[
					-6.084941943979186,
					-0.6294767528255198
				],
				[
					-5.8751163597041804,
					-1.0491279213757825
				],
				[
					-5.24563960687866,
					-1.8884302584763915
				],
				[
					-5.035814022603487,
					-2.5179070113018276
				],
				[
					-4.825988438328315,
					-2.9375581798521737
				],
				[
					-4.196511685502962,
					-3.5670349326776094
				],
				[
					-3.5670349326774424,
					-4.1965116855030455
				],
				[
					-3.357209348402269,
					-4.616162854053308
				],
				[
					-2.7277325955769167,
					-5.035814022603655
				],
				[
					-2.3080814270265706,
					-5.455465191153918
				],
				[
					-1.8884302584762238,
					-5.875116359704264
				],
				[
					-1.2589535056508718,
					-6.5045931125297
				],
				[
					-0.8393023371005253,
					-6.714418696804789
				],
				[
					-0.20982558427500544,
					-7.134069865355135
				],
				[
					0.20982558427517328,
					-7.553721033905398
				],
				[
					0.6294767528255198,
					-7.763546618180571
				],
				[
					1.2589535056510397,
					-8.60284895528118
				],
				[
					1.8884302584763917,
					-8.812674539556355
				],
				[
					2.5179070113019115,
					-9.022500123831444
				],
				[
					2.9375581798520902,
					-9.022500123831444
				],
				[
					3.1473837641272633,
					-9.022500123831444
				],
				[
					3.357209348402437,
					-9.022500123831444
				],
				[
					3.56703493267761,
					-9.022500123831444
				],
				[
					3.7768605169527834,
					-9.022500123831444
				],
				[
					3.9866861012279564,
					-8.812674539556355
				],
				[
					4.406337269778136,
					-8.393023371006008
				],
				[
					4.616162854053308,
					-8.183197786730835
				],
				[
					4.825988438328482,
					-7.973372202455745
				],
				[
					5.035814022603655,
					-7.553721033905398
				],
				[
					5.035814022603655,
					-7.134069865355135
				],
				[
					5.245639606878829,
					-6.714418696804789
				],
				[
					5.245639606878829,
					-6.294767528254527
				],
				[
					5.245639606878829,
					-5.875116359704264
				],
				[
					5.245639606878829,
					-5.455465191153918
				],
				[
					5.035814022603655,
					-5.035814022603655
				],
				[
					4.825988438328482,
					-4.616162854053308
				],
				[
					4.616162854053308,
					-3.9866861012278725
				],
				[
					3.9866861012279564,
					-3.1473837641272633
				],
				[
					3.357209348402437,
					-2.5179070113018276
				],
				[
					2.9375581798520902,
					-1.8884302584763915
				],
				[
					2.3080814270267385,
					-1.2589535056509555
				],
				[
					1.6786046742012184,
					-0.4196511685503465
				],
				[
					1.0491279213758664,
					0
				],
				[
					0.6294767528255198,
					0.4196511685502626
				],
				[
					0,
					1.2589535056508718
				],
				[
					-0.629476752825352,
					1.6786046742011342
				],
				[
					-1.4687790899260451,
					2.098255842751481
				],
				[
					-2.3080814270265706,
					2.5179070113017437
				],
				[
					-2.9375581798520902,
					3.1473837641271794
				],
				[
					-3.5670349326774424,
					3.776860516952699
				],
				[
					-4.406337269778136,
					4.616162854053225
				],
				[
					-5.035814022603487,
					5.035814022603571
				],
				[
					-5.665290775429007,
					5.665290775429007
				],
				[
					-6.084941943979186,
					6.08494194397927
				],
				[
					-6.714418696804707,
					6.504593112529616
				],
				[
					-7.134069865355053,
					6.714418696804789
				],
				[
					-8.18319778673075,
					7.134069865355052
				],
				[
					-8.602848955281097,
					7.134069865355052
				],
				[
					-9.23232570810645,
					7.343895449630225
				],
				[
					-9.861802460931969,
					7.343895449630225
				],
				[
					-10.491279213757489,
					7.5537210339053145
				],
				[
					-10.910930382307667,
					7.5537210339053145
				],
				[
					-11.120755966582841,
					7.5537210339053145
				],
				[
					-11.330581550858014,
					7.5537210339053145
				],
				[
					-11.330581550858014,
					7.343895449630225
				],
				[
					-11.540407135133187,
					6.924244281079878
				],
				[
					-11.750232719408361,
					6.504593112529616
				],
				[
					-11.960058303683534,
					5.8751163597041804
				],
				[
					-12.169883887958708,
					5.455465191153833
				],
				[
					-12.799360640784059,
					4.616162854053225
				],
				[
					-12.799360640784059,
					3.776860516952699
				],
				[
					-12.799360640784059,
					3.1473837641271794
				],
				[
					-12.379709472233714,
					1.8884302584763075
				],
				[
					-11.960058303683534,
					1.0491279213756985
				],
				[
					-11.120755966582841,
					0.20982558427508932
				],
				[
					-10.491279213757489,
					-0.4196511685503465
				],
				[
					-9.442151292381622,
					-1.4687790899261288
				],
				[
					-7.973372202455578,
					-2.308081427026654
				],
				[
					-6.504593112529533,
					-3.3572093484024363
				],
				[
					-5.665290775429007,
					-4.1965116855030455
				],
				[
					-4.616162854053141,
					-5.245639606878744
				],
				[
					-3.986686101227789,
					-5.665290775429091
				],
				[
					-3.147383764127096,
					-6.294767528254527
				],
				[
					-2.7277325955769167,
					-7.134069865355135
				],
				[
					-2.0982558427513975,
					-7.553721033905398
				],
				[
					-1.4687790899260451,
					-8.183197786730835
				],
				[
					-1.0491279213756988,
					-8.393023371006008
				],
				[
					-0.629476752825352,
					-9.022500123831444
				],
				[
					-0.20982558427500544,
					-9.44215129238179
				],
				[
					0.41965116855034656,
					-10.071628045207227
				],
				[
					0.8393023371006931,
					-10.491279213757572
				],
				[
					1.0491279213758664,
					-10.910930382307836
				],
				[
					1.4687790899260451,
					-11.330581550858097
				],
				[
					1.8884302584763917,
					-11.750232719408444
				],
				[
					2.3080814270267385,
					-12.169883887958708
				],
				[
					2.9375581798520902,
					-12.799360640784142
				],
				[
					3.357209348402437,
					-13.21901180933449
				],
				[
					3.9866861012279564,
					-13.428837393609662
				],
				[
					4.825988438328482,
					-13.848488562159925
				],
				[
					5.245639606878829,
					-14.058314146435098
				],
				[
					6.084941943979354,
					-14.268139730710187
				],
				[
					6.714418696804874,
					-14.268139730710187
				],
				[
					7.343895449630393,
					-14.268139730710187
				],
				[
					7.7635466181805715,
					-14.268139730710187
				],
				[
					8.183197786730918,
					-14.268139730710187
				],
				[
					8.812674539556438,
					-13.848488562159925
				],
				[
					9.232325708106616,
					-13.638662977884753
				],
				[
					9.44215129238179,
					-13.009186225059317
				],
				[
					9.861802460932136,
					-12.589535056509053
				],
				[
					10.281453629482483,
					-11.960058303683617
				],
				[
					10.281453629482483,
					-11.330581550858097
				],
				[
					10.281453629482483,
					-10.910930382307836
				],
				[
					10.281453629482483,
					-10.071628045207227
				],
				[
					10.281453629482483,
					-9.44215129238179
				],
				[
					10.07162804520731,
					-8.812674539556355
				],
				[
					9.861802460932136,
					-7.973372202455745
				],
				[
					9.44215129238179,
					-7.343895449630309
				],
				[
					9.232325708106616,
					-6.714418696804789
				],
				[
					8.393023371006091,
					-5.875116359704264
				],
				[
					7.553721033905399,
					-5.245639606878744
				],
				[
					6.924244281080047,
					-4.616162854053308
				],
				[
					6.294767528254527,
					-3.776860516952699
				],
				[
					5.455465191154001,
					-2.9375581798521737
				],
				[
					4.825988438328482,
					-2.098255842751565
				],
				[
					3.9866861012279564,
					-1.4687790899261288
				],
				[
					3.357209348402437,
					-0.8393023371006091
				],
				[
					2.3080814270267385,
					0.20982558427508932
				],
				[
					1.4687790899260451,
					0.8393023371006091
				],
				[
					0.8393023371006931,
					1.4687790899260451
				],
				[
					0,
					2.098255842751481
				],
				[
					-0.8393023371005253,
					2.7277325955769167
				],
				[
					-1.4687790899260451,
					3.1473837641271794
				],
				[
					-2.3080814270265706,
					3.776860516952699
				],
				[
					-2.7277325955769167,
					4.196511685502962
				],
				[
					-3.357209348402269,
					4.406337269778136
				],
				[
					-3.7768605169526155,
					4.616162854053225
				],
				[
					-3.986686101227789,
					4.825988438328397
				],
				[
					-4.616162854053141,
					5.035814022603571
				],
				[
					-4.825988438328315,
					5.035814022603571
				],
				[
					-5.455465191153833,
					5.245639606878744
				],
				[
					-5.8751163597041804,
					5.455465191153833
				],
				[
					-6.29476752825436,
					5.455465191153833
				],
				[
					-6.714418696804707,
					5.455465191153833
				],
				[
					-6.924244281079879,
					5.455465191153833
				],
				[
					-7.134069865355053,
					5.455465191153833
				],
				[
					-7.553721033905231,
					5.455465191153833
				],
				[
					-7.973372202455578,
					5.455465191153833
				],
				[
					-8.18319778673075,
					5.455465191153833
				],
				[
					-8.602848955281097,
					5.245639606878744
				],
				[
					-9.022500123831275,
					5.245639606878744
				],
				[
					-9.442151292381622,
					5.245639606878744
				],
				[
					-9.651976876656795,
					5.035814022603571
				],
				[
					-10.071628045207142,
					5.035814022603571
				],
				[
					-10.281453629482316,
					4.825988438328397
				],
				[
					-10.701104798032494,
					4.616162854053225
				],
				[
					-10.910930382307667,
					4.616162854053225
				],
				[
					-11.120755966582841,
					4.616162854053225
				],
				[
					-11.330581550858014,
					4.406337269778136
				],
				[
					-11.540407135133187,
					4.196511685502962
				],
				[
					-11.750232719408361,
					4.196511685502962
				],
				[
					-11.960058303683534,
					3.9866861012277885
				],
				[
					-12.169883887958708,
					3.9866861012277885
				],
				[
					-12.379709472233714,
					3.9866861012277885
				],
				[
					-12.379709472233714,
					3.776860516952699
				],
				[
					-12.589535056508886,
					3.776860516952699
				],
				[
					-12.799360640784059,
					3.776860516952699
				],
				[
					-12.799360640784059,
					3.567034932677526
				],
				[
					-13.009186225059231,
					3.567034932677526
				],
				[
					-13.009186225059231,
					3.776860516952699
				],
				[
					-13.009186225059231,
					4.196511685502962
				],
				[
					-13.009186225059231,
					4.616162854053225
				],
				[
					-13.009186225059231,
					4.825988438328397
				],
				[
					-13.219011809334406,
					5.245639606878744
				],
				[
					-13.219011809334406,
					5.665290775429007
				],
				[
					-13.428837393609578,
					5.8751163597041804
				],
				[
					-13.428837393609578,
					6.294767528254443
				],
				[
					-13.428837393609578,
					6.504593112529616
				],
				[
					-13.428837393609578,
					6.714418696804789
				],
				[
					-13.428837393609578,
					6.924244281079878
				],
				[
					-13.428837393609578,
					7.134069865355052
				],
				[
					-13.428837393609578,
					7.343895449630225
				],
				[
					-13.428837393609578,
					7.5537210339053145
				],
				[
					-13.428837393609578,
					7.763546618180488
				],
				[
					-13.219011809334406,
					7.763546618180488
				],
				[
					-13.009186225059231,
					7.763546618180488
				],
				[
					-12.799360640784059,
					7.763546618180488
				],
				[
					-12.379709472233714,
					7.973372202455661
				],
				[
					-12.169883887958708,
					7.973372202455661
				],
				[
					-11.960058303683534,
					7.973372202455661
				],
				[
					-11.540407135133187,
					7.973372202455661
				],
				[
					-11.120755966582841,
					7.973372202455661
				],
				[
					-10.910930382307667,
					7.973372202455661
				],
				[
					-10.701104798032494,
					7.973372202455661
				],
				[
					-10.491279213757489,
					7.973372202455661
				],
				[
					-10.281453629482316,
					7.973372202455661
				],
				[
					-10.071628045207142,
					7.973372202455661
				],
				[
					-9.861802460931969,
					7.973372202455661
				],
				[
					-9.442151292381622,
					7.763546618180488
				],
				[
					-9.23232570810645,
					7.763546618180488
				],
				[
					-9.022500123831275,
					7.5537210339053145
				],
				[
					-8.602848955281097,
					7.343895449630225
				],
				[
					-8.393023371005924,
					7.343895449630225
				],
				[
					-8.18319778673075,
					7.343895449630225
				],
				[
					-7.973372202455578,
					7.134069865355052
				],
				[
					-7.553721033905231,
					6.924244281079878
				],
				[
					-7.343895449630226,
					6.714418696804789
				],
				[
					-7.343895449630226,
					6.504593112529616
				],
				[
					-7.343895449630226,
					6.294767528254443
				],
				[
					-7.343895449630226,
					6.08494194397927
				],
				[
					-6.924244281079879,
					5.455465191153833
				],
				[
					-6.504593112529533,
					5.035814022603571
				],
				[
					-6.084941943979186,
					4.825988438328397
				],
				[
					-5.665290775429007,
					4.616162854053225
				],
				[
					-5.035814022603487,
					3.776860516952699
				],
				[
					-4.406337269778136,
					3.1473837641271794
				],
				[
					-3.7768605169526155,
					2.5179070113017437
				],
				[
					-3.357209348402269,
					1.8884302584763075
				],
				[
					-3.147383764127096,
					1.4687790899260451
				],
				[
					-2.7277325955769167,
					1.2589535056508718
				],
				[
					-2.3080814270265706,
					0.6294767528254359
				],
				[
					-1.8884302584762238,
					0.20982558427508932
				],
				[
					-1.6786046742010505,
					-0.20982558427517325
				],
				[
					-1.2589535056508718,
					-0.6294767528255198
				],
				[
					-1.0491279213756988,
					-1.0491279213757825
				],
				[
					-0.8393023371005253,
					-1.4687790899261288
				],
				[
					-0.629476752825352,
					-1.8884302584763915
				],
				[
					-0.20982558427500544,
					-2.098255842751565
				],
				[
					0,
					-2.308081427026654
				],
				[
					0.20982558427517328,
					-2.7277325955770007
				],
				[
					0.41965116855034656,
					-2.9375581798521737
				],
				[
					0.41965116855034656,
					-3.1473837641272633
				],
				[
					0.6294767528255198,
					-3.3572093484024363
				],
				[
					0.8393023371006931,
					-3.5670349326776094
				],
				[
					1.0491279213758664,
					-3.5670349326776094
				],
				[
					1.0491279213758664,
					-3.776860516952699
				],
				[
					1.0491279213758664,
					-3.9866861012278725
				],
				[
					1.0491279213758664,
					-3.9866861012278725
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 399,
			"versionNonce": 1808087205,
			"isDeleted": false,
			"id": "kNC8eUIC1V48K_aSWoUuq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1063.5973207340844,
			"y": 662.6811161794616,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 4.276501687663637,
			"height": 24.13168809467389,
			"seed": 1520445189,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.30546440626165233
				],
				[
					0,
					0.6109288125233886
				],
				[
					0.30546440626156846,
					1.2218576250467772
				],
				[
					0.6109288125233048,
					1.8327864375701657
				],
				[
					0.916393218785041,
					2.4437152500935544
				],
				[
					1.2218576250466096,
					2.7491796563552064
				],
				[
					1.5273220313083458,
					3.3601084688786793
				],
				[
					2.443715250093555,
					4.887430500187109
				],
				[
					2.443715250093555,
					5.19289490644876
				],
				[
					2.749179656355123,
					6.109288125233886
				],
				[
					3.360108468878596,
					7.331145750280663
				],
				[
					3.360108468878596,
					8.553003375327439
				],
				[
					3.9710372814019,
					9.469396594112565
				],
				[
					3.9710372814019,
					10.080325406635954
				],
				[
					3.9710372814019,
					11.30218303168273
				],
				[
					4.276501687663637,
					11.913111844206119
				],
				[
					4.276501687663637,
					12.524040656729508
				],
				[
					4.276501687663637,
					13.440433875514548
				],
				[
					4.276501687663637,
					14.356827094299675
				],
				[
					4.276501687663637,
					14.967755906823063
				],
				[
					4.276501687663637,
					15.57868471934645
				],
				[
					4.276501687663637,
					16.49507793813149
				],
				[
					4.276501687663637,
					17.106006750654963
				],
				[
					4.276501687663637,
					17.411471156916615
				],
				[
					4.276501687663637,
					18.022399969440006
				],
				[
					4.276501687663637,
					18.938793188225045
				],
				[
					4.276501687663637,
					19.244257594486783
				],
				[
					3.9710372814019,
					19.549722000748517
				],
				[
					3.9710372814019,
					19.85518640701017
				],
				[
					3.9710372814019,
					20.46611521953356
				],
				[
					3.9710372814019,
					21.077044032056946
				],
				[
					3.665572875140164,
					21.3825084383186
				],
				[
					3.665572875140164,
					21.687972844580337
				],
				[
					3.665572875140164,
					21.99343725084207
				],
				[
					3.360108468878596,
					22.604366063365376
				],
				[
					3.360108468878596,
					22.909830469627114
				],
				[
					3.0546440626168594,
					23.21529487588885
				],
				[
					3.0546440626168594,
					23.520759282150504
				],
				[
					2.749179656355123,
					23.520759282150504
				],
				[
					2.749179656355123,
					23.826223688412238
				],
				[
					2.443715250093555,
					24.13168809467389
				],
				[
					2.443715250093555,
					24.13168809467389
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 388,
			"versionNonce": 147050539,
			"isDeleted": false,
			"id": "ctEAwLyNp0DHXjQZ8d61Y",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1085.896222391188,
			"y": 662.3756517731998,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 3.054644062617027,
			"height": 22.29890165710381,
			"seed": 105714565,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.30546440626173627,
					0.6109288125233886
				],
				[
					-0.30546440626173627,
					1.5273220313085134
				],
				[
					-0.6109288125234725,
					2.138250843831902
				],
				[
					-0.9163932187852087,
					3.6655728751404157
				],
				[
					-1.221857625046945,
					4.887430500187192
				],
				[
					-1.5273220313085134,
					5.803823718972233
				],
				[
					-1.8327864375702496,
					7.6366101565424
				],
				[
					-1.8327864375702496,
					8.858467781589177
				],
				[
					-2.138250843831986,
					9.774861000374301
				],
				[
					-2.138250843831986,
					10.996718625421078
				],
				[
					-2.138250843831986,
					11.607647437944467
				],
				[
					-2.4437152500935544,
					12.524040656729508
				],
				[
					-2.4437152500935544,
					13.440433875514634
				],
				[
					-2.4437152500935544,
					14.356827094299675
				],
				[
					-2.7491796563552904,
					15.2732203130848
				],
				[
					-3.054644062617027,
					16.18961353186984
				],
				[
					-3.054644062617027,
					17.106006750654963
				],
				[
					-3.054644062617027,
					17.716935563178353
				],
				[
					-3.054644062617027,
					18.32786437570174
				],
				[
					-3.054644062617027,
					18.93879318822513
				],
				[
					-3.054644062617027,
					19.549722000748517
				],
				[
					-3.054644062617027,
					19.855186407010255
				],
				[
					-3.054644062617027,
					20.46611521953356
				],
				[
					-2.7491796563552904,
					20.771579625795294
				],
				[
					-2.7491796563552904,
					21.07704403205703
				],
				[
					-2.7491796563552904,
					21.382508438318684
				],
				[
					-2.4437152500935544,
					21.687972844580337
				],
				[
					-2.4437152500935544,
					21.99343725084207
				],
				[
					-2.4437152500935544,
					22.29890165710381
				],
				[
					-2.138250843831986,
					22.29890165710381
				],
				[
					-2.138250843831986,
					22.29890165710381
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 385,
			"versionNonce": 843111429,
			"isDeleted": false,
			"id": "V9I2n--oQP6katHm1Ea7J",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1082.2306495160476,
			"y": 673.6778348048825,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 15.27322031308463,
			"height": 0.9163932187851248,
			"seed": 1188333285,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.3054644062615684,
					0
				],
				[
					-2.1382508438318184,
					0
				],
				[
					-3.054644062616859,
					0
				],
				[
					-4.581966093925372,
					0
				],
				[
					-5.80382371897215,
					0
				],
				[
					-6.414752531495454,
					0
				],
				[
					-7.025681344018927,
					0
				],
				[
					-7.331145750280663,
					0
				],
				[
					-7.942074562803968,
					0
				],
				[
					-8.553003375327439,
					0
				],
				[
					-8.858467781589008,
					0
				],
				[
					-9.163932187850744,
					0
				],
				[
					-9.46939659411248,
					0
				],
				[
					-10.080325406635785,
					0
				],
				[
					-10.691254219159259,
					0
				],
				[
					-11.302183031682562,
					0
				],
				[
					-11.6076474379443,
					0
				],
				[
					-12.218576250467772,
					0
				],
				[
					-12.524040656729508,
					0
				],
				[
					-12.829505062991077,
					0
				],
				[
					-13.134969469252813,
					0.30546440626173627
				],
				[
					-13.440433875514548,
					0.6109288125233886
				],
				[
					-13.745898281776117,
					0.6109288125233886
				],
				[
					-14.051362688037853,
					0.6109288125233886
				],
				[
					-14.35682709429959,
					0.6109288125233886
				],
				[
					-14.967755906823063,
					0.9163932187851248
				],
				[
					-15.27322031308463,
					0.9163932187851248
				],
				[
					-15.27322031308463,
					0.9163932187851248
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 408,
			"versionNonce": 869176011,
			"isDeleted": false,
			"id": "W6MnM0Fzz0Y-G9taq6St1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1010.4465140445493,
			"y": 794.0308108719903,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.192894906448845,
			"height": 35.128406720094965,
			"seed": 1006417957,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.30546440626173627
				],
				[
					0,
					0.6109288125233886
				],
				[
					0.30546440626173627,
					2.138250843831902
				],
				[
					0.9163932187851248,
					3.0546440626169424
				],
				[
					0.9163932187851248,
					3.971037281402068
				],
				[
					1.2218576250467772,
					4.276501687663719
				],
				[
					1.5273220313085134,
					5.498359312710497
				],
				[
					1.5273220313085134,
					6.720216937757358
				],
				[
					1.5273220313085134,
					8.247538969065788
				],
				[
					1.5273220313085134,
					9.469396594112565
				],
				[
					1.5273220313085134,
					10.691254219159342
				],
				[
					1.5273220313085134,
					11.913111844206117
				],
				[
					1.5273220313085134,
					13.134969469252894
				],
				[
					1.5273220313085134,
					13.745898281776283
				],
				[
					1.5273220313085134,
					14.662291500561409
				],
				[
					1.2218576250467772,
					15.578684719346448
				],
				[
					1.2218576250467772,
					16.18961353186984
				],
				[
					0.9163932187851248,
					17.106006750654963
				],
				[
					0.9163932187851248,
					17.716935563178353
				],
				[
					0.6109288125233886,
					18.022399969440006
				],
				[
					0.6109288125233886,
					18.633328781963478
				],
				[
					0.6109288125233886,
					19.549722000748517
				],
				[
					0.30546440626173627,
					20.160650813271907
				],
				[
					0.30546440626173627,
					20.771579625795294
				],
				[
					0.30546440626173627,
					21.07704403205703
				],
				[
					0,
					21.993437250842067
				],
				[
					0,
					22.604366063365458
				],
				[
					0,
					23.215294875888848
				],
				[
					-0.30546440626165233,
					23.826223688412234
				],
				[
					-0.30546440626165233,
					24.437152500935625
				],
				[
					-0.9163932187850409,
					25.35354571972075
				],
				[
					-1.2218576250467772,
					25.964474532244136
				],
				[
					-1.2218576250467772,
					26.88086775102918
				],
				[
					-1.5273220313084295,
					27.491796563552565
				],
				[
					-1.8327864375701657,
					28.102725376075956
				],
				[
					-1.8327864375701657,
					28.713654188599346
				],
				[
					-2.1382508438318184,
					29.01911859486108
				],
				[
					-2.1382508438318184,
					29.63004740738447
				],
				[
					-2.4437152500935544,
					30.240976219907857
				],
				[
					-2.7491796563552064,
					31.157369438692896
				],
				[
					-2.7491796563552064,
					31.462833844954638
				],
				[
					-2.7491796563552064,
					32.07376265747802
				],
				[
					-3.054644062616943,
					32.379227063739755
				],
				[
					-3.054644062616943,
					32.68469147000141
				],
				[
					-3.3601084688785954,
					33.601084688786536
				],
				[
					-3.3601084688785954,
					33.90654909504819
				],
				[
					-3.6655728751403314,
					34.21201350130984
				],
				[
					-3.6655728751403314,
					34.517477907571575
				],
				[
					-3.6655728751403314,
					34.82294231383331
				],
				[
					-3.6655728751403314,
					35.128406720094965
				],
				[
					-3.6655728751403314,
					35.128406720094965
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 386,
			"versionNonce": 607196005,
			"isDeleted": false,
			"id": "-4Mr4TG0YIATdouo908gI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1013.806622513428,
			"y": 810.5258888101218,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 13.440433875514634,
			"height": 2.7491796563552064,
			"seed": 707189739,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.30546440626165233
				],
				[
					0.6109288125233886,
					0.6109288125233886
				],
				[
					1.5273220313084295,
					0.6109288125233886
				],
				[
					2.4437152500934705,
					0.9163932187850409
				],
				[
					3.054644062616943,
					0.9163932187850409
				],
				[
					3.6655728751402474,
					0.9163932187850409
				],
				[
					4.887430500187024,
					0.9163932187850409
				],
				[
					5.803823718972233,
					0.9163932187850409
				],
				[
					6.414752531495538,
					0.9163932187850409
				],
				[
					6.720216937757274,
					0.9163932187850409
				],
				[
					7.331145750280747,
					0.9163932187850409
				],
				[
					7.636610156542315,
					0.9163932187850409
				],
				[
					7.942074562804051,
					0.9163932187850409
				],
				[
					8.247538969065788,
					0.9163932187850409
				],
				[
					8.858467781589091,
					0.9163932187850409
				],
				[
					9.469396594112565,
					0.6109288125233886
				],
				[
					9.774861000374301,
					0.6109288125233886
				],
				[
					10.385789812897606,
					0.30546440626165233
				],
				[
					10.691254219159342,
					0.30546440626165233
				],
				[
					10.996718625421078,
					0.30546440626165233
				],
				[
					11.607647437944383,
					-0.30546440626173627
				],
				[
					11.913111844206119,
					-0.30546440626173627
				],
				[
					12.218576250467855,
					-0.6109288125233886
				],
				[
					12.524040656729424,
					-0.6109288125233886
				],
				[
					12.524040656729424,
					-0.9163932187851248
				],
				[
					12.82950506299116,
					-0.9163932187851248
				],
				[
					12.82950506299116,
					-1.2218576250467772
				],
				[
					13.134969469252896,
					-1.5273220313085132
				],
				[
					13.440433875514634,
					-1.8327864375701655
				],
				[
					13.440433875514634,
					-1.8327864375701655
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 388,
			"versionNonce": 1101529451,
			"isDeleted": false,
			"id": "6CojSA2L_CdDkyDpqqhRM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1028.1634496077277,
			"y": 793.419882059467,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 2.1382508438318184,
			"height": 28.10272537607596,
			"seed": 905801707,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.30546440626173627
				],
				[
					0.3054644062617363,
					1.2218576250467772
				],
				[
					0.6109288125233048,
					1.8327864375701657
				],
				[
					0.6109288125233048,
					2.7491796563552904
				],
				[
					0.6109288125233048,
					3.9710372814020682
				],
				[
					0.6109288125233048,
					5.192894906448845
				],
				[
					0.6109288125233048,
					6.414752531495622
				],
				[
					0.6109288125233048,
					8.858467781589177
				],
				[
					0.6109288125233048,
					9.774861000374301
				],
				[
					0.6109288125233048,
					11.30218303168273
				],
				[
					0.3054644062617363,
					13.440433875514634
				],
				[
					0.3054644062617363,
					14.967755906823063
				],
				[
					0.3054644062617363,
					16.18961353186984
				],
				[
					0.3054644062617363,
					17.106006750654963
				],
				[
					0.3054644062617363,
					18.93879318822513
				],
				[
					0.3054644062617363,
					19.549722000748517
				],
				[
					0.3054644062617363,
					20.160650813271907
				],
				[
					0.3054644062617363,
					21.382508438318684
				],
				[
					0.3054644062617363,
					22.298901657103723
				],
				[
					0.3054644062617363,
					23.21529487588885
				],
				[
					0.3054644062617363,
					23.826223688412238
				],
				[
					0.3054644062617363,
					24.43715250093563
				],
				[
					0.3054644062617363,
					25.048081313459015
				],
				[
					0.6109288125233048,
					25.96447453224414
				],
				[
					0.6109288125233048,
					26.57540334476753
				],
				[
					0.916393218785041,
					26.880867751029182
				],
				[
					1.2218576250467774,
					27.18633215729092
				],
				[
					1.5273220313085136,
					27.49179656355257
				],
				[
					1.832786437570082,
					27.797260969814307
				],
				[
					2.1382508438318184,
					27.797260969814307
				],
				[
					2.1382508438318184,
					28.10272537607596
				],
				[
					2.1382508438318184,
					28.10272537607596
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 387,
			"versionNonce": 233004741,
			"isDeleted": false,
			"id": "3xC29x_VM7fgyxkb0jASA",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1080.5011190623818,
			"y": 783.346487799883,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 3.072808917311961,
			"height": 10.475484945381274,
			"seed": 980419307,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.13967313260512726,
					-0.27934626521017064
				],
				[
					0.2793462652102545,
					-0.5586925304203413
				],
				[
					0.4190193978153818,
					-1.1173850608406826
				],
				[
					0.6983656630254685,
					-1.6760775912610237
				],
				[
					0.8380387956305957,
					-2.93313578470675
				],
				[
					0.9777119282355553,
					-3.7711745803372616
				],
				[
					1.1173850608406823,
					-4.050520845547433
				],
				[
					1.2570581934458098,
					-4.888559641177944
				],
				[
					1.2570581934458098,
					-5.586925304203329
				],
				[
					1.2570581934458098,
					-6.14561783462367
				],
				[
					1.2570581934458098,
					-6.7043103650440115
				],
				[
					1.2570581934458098,
					-7.123329762859226
				],
				[
					1.2570581934458098,
					-7.542349160674523
				],
				[
					1.2570581934458098,
					-7.961368558489738
				],
				[
					1.2570581934458098,
					-8.520061088910078
				],
				[
					1.2570581934458098,
					-8.939080486725294
				],
				[
					1.2570581934458098,
					-9.218426751935464
				],
				[
					1.2570581934458098,
					-9.497773017145633
				],
				[
					1.2570581934458098,
					-9.777119282355805
				],
				[
					1.2570581934458098,
					-10.056465547565976
				],
				[
					1.396731326050937,
					-10.335811812776146
				],
				[
					1.396731326050937,
					-10.475484945381274
				],
				[
					1.2570581934458098,
					-10.475484945381274
				],
				[
					0.8380387956305957,
					-10.335811812776146
				],
				[
					0.6983656630254685,
					-10.196138680171103
				],
				[
					0.13967313260512726,
					-10.056465547565976
				],
				[
					-0.2793462652100867,
					-9.777119282355805
				],
				[
					-0.8380387956304279,
					-9.637446149750762
				],
				[
					-1.1173850608406823,
					-9.497773017145633
				],
				[
					-1.3967313260507692,
					-9.35809988454059
				],
				[
					-1.5364044586558965,
					-9.218426751935464
				],
				[
					-1.5364044586558965,
					-9.07875361933042
				],
				[
					-1.6760775912610235,
					-9.07875361933042
				],
				[
					-1.6760775912610235,
					-8.939080486725294
				],
				[
					-1.6760775912610235,
					-8.939080486725294
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 407,
			"versionNonce": 999988235,
			"isDeleted": false,
			"id": "72Ell4Yd6UVncW5Kp7FYn",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1084.132620510114,
			"y": 796.0567428669456,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.542349160674523,
			"height": 14.665678923533749,
			"seed": 699917323,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.838038795630428,
					0
				],
				[
					-1.5364044586558967,
					0
				],
				[
					-2.2347701216811973,
					0.419019397815214
				],
				[
					-2.5141163868914522,
					0.5586925304203413
				],
				[
					-2.6537895194965793,
					0.9777119282355554
				],
				[
					-2.933135784706666,
					1.3967313260508532
				],
				[
					-3.0728089173117934,
					1.8157507238660673
				],
				[
					-3.0728089173117934,
					2.095096989076238
				],
				[
					-3.0728089173117934,
					2.6537895194965793
				],
				[
					-3.0728089173117934,
					2.93313578470675
				],
				[
					-3.0728089173117934,
					3.3521551825220475
				],
				[
					-2.933135784706666,
					3.910847712942305
				],
				[
					-2.793462652101539,
					4.329867110757603
				],
				[
					-2.6537895194965793,
					4.888559641177944
				],
				[
					-2.5141163868914522,
					5.167905906388115
				],
				[
					-2.3744432542863247,
					5.586925304203329
				],
				[
					-2.2347701216811973,
					5.8662715694135
				],
				[
					-1.9554238564711108,
					6.424964099833841
				],
				[
					-1.5364044586558967,
					6.843983497649055
				],
				[
					-1.1173850608405147,
					7.402676028069396
				],
				[
					-0.838038795630428,
					7.682022293279567
				],
				[
					-0.419019397815214,
					8.101041691094865
				],
				[
					0,
					8.380387956305036
				],
				[
					0.2793462652102546,
					8.79940735412025
				],
				[
					0.5586925304203413,
					9.218426751935548
				],
				[
					0.6983656630254687,
					9.637446149750762
				],
				[
					0.9777119282357231,
					10.056465547565976
				],
				[
					0.9777119282357231,
					10.335811812776146
				],
				[
					0.9777119282357231,
					10.894504343196488
				],
				[
					0.9777119282357231,
					11.313523741011785
				],
				[
					0.9777119282357231,
					11.732543138827
				],
				[
					0.8380387956305958,
					12.01188940403717
				],
				[
					0.5586925304203413,
					12.570581934457511
				],
				[
					0.2793462652102546,
					12.849928199667682
				],
				[
					0,
					13.129274464877852
				],
				[
					-0.419019397815214,
					13.268947597482898
				],
				[
					-0.838038795630428,
					13.548293862693066
				],
				[
					-1.3967313260507694,
					13.827640127903237
				],
				[
					-1.676077591260856,
					14.10698639311341
				],
				[
					-2.2347701216811973,
					14.386332658323578
				],
				[
					-2.6537895194965793,
					14.526005790928705
				],
				[
					-3.0728089173117934,
					14.526005790928705
				],
				[
					-3.35215518252188,
					14.665678923533749
				],
				[
					-3.771174580337094,
					14.665678923533749
				],
				[
					-4.190193978152476,
					14.665678923533749
				],
				[
					-4.60921337596769,
					14.665678923533749
				],
				[
					-4.8885596411777765,
					14.665678923533749
				],
				[
					-5.167905906388031,
					14.665678923533749
				],
				[
					-5.586925304203245,
					14.665678923533749
				],
				[
					-5.866271569413332,
					14.665678923533749
				],
				[
					-6.145617834623587,
					14.665678923533749
				],
				[
					-6.285290967228714,
					14.665678923533749
				],
				[
					-6.424964099833673,
					14.665678923533749
				],
				[
					-6.564637232438801,
					14.665678923533749
				],
				[
					-6.564637232438801,
					14.665678923533749
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 365,
			"versionNonce": 1442135589,
			"isDeleted": false,
			"id": "PZ99Nhh6Pr63J-c9G3QFA",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1088.0434682230564,
			"y": 809.7447098622438,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0.1396731326051273,
			"height": 3.4918283151270915,
			"seed": 2106912171,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.13967313260504338
				],
				[
					0,
					0.5586925304202573
				],
				[
					0,
					0.8380387956305119
				],
				[
					0,
					1.3967313260507694
				],
				[
					0,
					1.67607759126094
				],
				[
					0,
					2.234770121681281
				],
				[
					0,
					2.6537895194965793
				],
				[
					0,
					2.7934626521016224
				],
				[
					0.1396731326051273,
					3.0728089173117934
				],
				[
					0.1396731326051273,
					3.2124820499169204
				],
				[
					0.1396731326051273,
					3.352155182521964
				],
				[
					0.1396731326051273,
					3.4918283151270915
				],
				[
					0.1396731326051273,
					3.4918283151270915
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 402,
			"versionNonce": 497083051,
			"isDeleted": false,
			"id": "k6F-v4a6olCg-tXY1frIk",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1091.6749696707884,
			"y": 825.5277738466182,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.285290967228714,
			"height": 13.687966995298193,
			"seed": 822022411,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.5586925304203413,
					0
				],
				[
					-1.2570581934456422,
					0
				],
				[
					-2.095096989076238,
					0
				],
				[
					-2.6537895194965797,
					0
				],
				[
					-3.3521551825218805,
					0
				],
				[
					-4.190193978152476,
					0.27934626521017064
				],
				[
					-4.469540243362563,
					0.4190193978152979
				],
				[
					-5.0282327737829045,
					0.5586925304203413
				],
				[
					-5.307579038993159,
					0.6983656630254687
				],
				[
					-5.7265984368083735,
					0.9777119282356392
				],
				[
					-5.866271569413501,
					1.2570581934458098
				],
				[
					-6.00594470201846,
					1.5364044586559804
				],
				[
					-6.00594470201846,
					1.8157507238660673
				],
				[
					-6.00594470201846,
					2.095096989076238
				],
				[
					-6.00594470201846,
					2.3744432542864082
				],
				[
					-6.00594470201846,
					3.2124820499169204
				],
				[
					-5.7265984368083735,
					4.050520845547433
				],
				[
					-5.307579038993159,
					4.609213375967774
				],
				[
					-4.60921337596769,
					5.167905906388115
				],
				[
					-3.910847712942222,
					5.8662715694135
				],
				[
					-3.4918283151270075,
					6.424964099833841
				],
				[
					-3.072808917311794,
					6.7043103650440115
				],
				[
					-2.6537895194965797,
					7.263002895464353
				],
				[
					-2.3744432542863247,
					7.542349160674523
				],
				[
					-1.8157507238659836,
					8.101041691094865
				],
				[
					-1.3967313260507694,
					8.520061088910078
				],
				[
					-1.1173850608406826,
					8.79940735412025
				],
				[
					-0.8380387956304282,
					9.07875361933042
				],
				[
					-0.5586925304203413,
					9.35809988454059
				],
				[
					-0.13967313260495945,
					9.777119282355805
				],
				[
					0.1396731326051273,
					10.056465547566061
				],
				[
					0.2793462652102546,
					10.475484945381274
				],
				[
					0.2793462652102546,
					10.754831210591444
				],
				[
					0.2793462652102546,
					11.313523741011785
				],
				[
					0.1396731326051273,
					11.592870006221956
				],
				[
					0,
					12.01188940403717
				],
				[
					-0.27934626521008676,
					12.29123566924734
				],
				[
					-0.5586925304203413,
					12.430908801852384
				],
				[
					-0.9777119282355555,
					12.849928199667682
				],
				[
					-1.3967313260507694,
					12.989601332272725
				],
				[
					-1.8157507238659836,
					13.129274464877852
				],
				[
					-2.3744432542863247,
					13.129274464877852
				],
				[
					-2.793462652101539,
					13.268947597482981
				],
				[
					-3.212482049916921,
					13.548293862693066
				],
				[
					-3.631501447732135,
					13.548293862693066
				],
				[
					-3.910847712942222,
					13.548293862693066
				],
				[
					-4.190193978152476,
					13.687966995298193
				],
				[
					-4.329867110757604,
					13.687966995298193
				],
				[
					-4.469540243362563,
					13.687966995298193
				],
				[
					-4.469540243362563,
					13.687966995298193
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 397,
			"versionNonce": 861155717,
			"isDeleted": false,
			"id": "QH2PwU__UUMFgZoKfJhuY",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1094.0494129250749,
			"y": 839.6347602397315,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 4.469540243362562,
			"height": 5.447252171598202,
			"seed": 1475269003,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.5586925304203412,
					-0.13967313260504338
				],
				[
					0.6983656630253006,
					-0.13967313260504338
				],
				[
					0.8380387956304279,
					-0.13967313260504338
				],
				[
					1.2570581934458096,
					-0.13967313260504338
				],
				[
					1.6760775912610235,
					-0.13967313260504338
				],
				[
					1.815750723865983,
					-0.13967313260504338
				],
				[
					2.0950969890762376,
					-0.13967313260504338
				],
				[
					2.374443254286324,
					0.1396731326051273
				],
				[
					2.5141163868914513,
					0.5586925304203413
				],
				[
					2.5141163868914513,
					0.838038795630512
				],
				[
					2.5141163868914513,
					1.25705819344581
				],
				[
					2.5141163868914513,
					1.536404458655897
				],
				[
					2.374443254286324,
					1.8157507238661514
				],
				[
					2.0950969890762376,
					2.095096989076238
				],
				[
					1.815750723865983,
					2.234770121681365
				],
				[
					1.1173850608406823,
					2.514116386891536
				],
				[
					0.8380387956304279,
					2.6537895194965797
				],
				[
					0.2793462652100867,
					2.7934626521017067
				],
				[
					-0.2793462652102545,
					2.7934626521017067
				],
				[
					-0.8380387956305957,
					2.7934626521017067
				],
				[
					-1.3967313260509369,
					2.7934626521017067
				],
				[
					-1.6760775912610235,
					2.7934626521017067
				],
				[
					-1.8157507238661508,
					2.7934626521017067
				],
				[
					-1.9554238564711104,
					2.7934626521017067
				],
				[
					-1.6760775912610235,
					2.7934626521017067
				],
				[
					-1.2570581934458096,
					2.7934626521017067
				],
				[
					-1.1173850608406823,
					2.6537895194965797
				],
				[
					-0.9777119282355552,
					2.6537895194965797
				],
				[
					-0.8380387956305957,
					2.6537895194965797
				],
				[
					-0.5586925304203412,
					2.9331357847067503
				],
				[
					-0.41901939781521397,
					3.212482049916921
				],
				[
					-0.13967313260512726,
					3.352155182522048
				],
				[
					0,
					3.631501447732135
				],
				[
					0.2793462652100867,
					3.91084771294239
				],
				[
					0.41901939781521397,
					4.050520845547433
				],
				[
					0.5586925304203412,
					4.329867110757604
				],
				[
					0.6983656630253006,
					4.46954024336273
				],
				[
					0.9777119282355552,
					4.609213375967774
				],
				[
					0.9777119282355552,
					4.748886508572817
				],
				[
					1.1173850608406823,
					4.888559641177945
				],
				[
					1.1173850608406823,
					5.028232773782988
				],
				[
					1.2570581934458096,
					5.167905906388116
				],
				[
					1.2570581934458096,
					5.307579038993159
				],
				[
					1.2570581934458096,
					5.307579038993159
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 397,
			"versionNonce": 6640971,
			"isDeleted": false,
			"id": "bDAMol6AsCXdNDEGzBRul",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1102.2901277487747,
			"y": 774.5470804457627,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.8662715694135,
			"height": 11.034177475801615,
			"seed": 1794098763,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.13967313260512726,
					0
				],
				[
					0,
					-0.13967313260504338
				],
				[
					-0.5586925304203412,
					-0.27934626521017064
				],
				[
					-1.3967313260507692,
					-0.5586925304203413
				],
				[
					-1.9554238564711106,
					-0.5586925304203413
				],
				[
					-2.653789519496579,
					-0.5586925304203413
				],
				[
					-3.072808917311793,
					-0.419019397815214
				],
				[
					-3.4918283151270066,
					0
				],
				[
					-3.910847712942221,
					0.419019397815214
				],
				[
					-4.190193978152475,
					0.6983656630253847
				],
				[
					-4.190193978152475,
					1.2570581934457261
				],
				[
					-4.329867110757603,
					1.3967313260508532
				],
				[
					-4.329867110757603,
					1.8157507238660673
				],
				[
					-4.329867110757603,
					2.5141163868915357
				],
				[
					-4.329867110757603,
					3.0728089173118773
				],
				[
					-4.329867110757603,
					3.6315014477321346
				],
				[
					-4.190193978152475,
					4.190193978152476
				],
				[
					-3.4918283151270066,
					5.028232773782988
				],
				[
					-2.9331357847066655,
					5.447252171598286
				],
				[
					-2.2347701216811973,
					5.8662715694135
				],
				[
					-1.8157507238659831,
					6.005944702018543
				],
				[
					-1.257058193445642,
					6.14561783462367
				],
				[
					-0.8380387956304279,
					6.424964099833841
				],
				[
					-0.5586925304203412,
					6.564637232438884
				],
				[
					-0.41901939781521397,
					6.7043103650440115
				],
				[
					-0.2793462652100867,
					7.123329762859226
				],
				[
					-0.13967313260495942,
					7.402676028069396
				],
				[
					-0.13967313260495942,
					7.682022293279567
				],
				[
					-0.13967313260495942,
					8.101041691094865
				],
				[
					-0.13967313260495942,
					8.659734221515121
				],
				[
					-0.6983656630253007,
					9.497773017145633
				],
				[
					-1.257058193445642,
					9.916792414960932
				],
				[
					-1.6760775912608559,
					10.056465547565976
				],
				[
					-2.0950969890762376,
					10.335811812776146
				],
				[
					-2.514116386891452,
					10.335811812776146
				],
				[
					-3.072808917311793,
					10.475484945381274
				],
				[
					-3.3521551825218796,
					10.475484945381274
				],
				[
					-3.631501447732134,
					10.475484945381274
				],
				[
					-3.910847712942221,
					10.475484945381274
				],
				[
					-4.190193978152475,
					10.475484945381274
				],
				[
					-4.609213375967689,
					10.335811812776146
				],
				[
					-5.167905906388031,
					10.196138680171103
				],
				[
					-5.586925304203245,
					10.196138680171103
				],
				[
					-5.726598436808372,
					10.196138680171103
				],
				[
					-5.726598436808372,
					10.196138680171103
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 392,
			"versionNonce": 591247589,
			"isDeleted": false,
			"id": "SXnWepyJqJxzNujFGXSmA",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1103.8265322074308,
			"y": 784.882892258539,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 2.7934626521017063,
			"height": 7.123329762859309,
			"seed": 710070699,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.1396731326051273,
					-0.13967313260504335
				],
				[
					0.2793462652102546,
					-0.13967313260504335
				],
				[
					0.2793462652102546,
					-0.2793462652101706
				],
				[
					0.5586925304203413,
					-0.2793462652101706
				],
				[
					0.8380387956305958,
					-0.41901939781521397
				],
				[
					0.9777119282357231,
					-0.5586925304203412
				],
				[
					1.5364044586560646,
					-0.41901939781521397
				],
				[
					1.8157507238661512,
					-0.13967313260504335
				],
				[
					1.8157507238661512,
					0.13967313260512726
				],
				[
					2.0950969890764055,
					0.5586925304203412
				],
				[
					2.0950969890764055,
					0.9777119282355553
				],
				[
					2.0950969890764055,
					1.257058193445726
				],
				[
					1.8157507238661512,
					1.5364044586558965
				],
				[
					1.6760775912610237,
					1.6760775912610235
				],
				[
					1.3967313260509373,
					1.9554238564711943
				],
				[
					1.1173850608406826,
					1.9554238564711943
				],
				[
					0.9777119282357231,
					2.0950969890762376
				],
				[
					0.8380387956305958,
					2.0950969890762376
				],
				[
					0.6983656630254687,
					2.2347701216813647
				],
				[
					0.6983656630254687,
					2.3744432542864082
				],
				[
					0.8380387956305958,
					2.653789519496579
				],
				[
					1.2570581934458098,
					2.93313578470675
				],
				[
					1.5364044586560646,
					3.352155182522047
				],
				[
					1.8157507238661512,
					3.491828315127091
				],
				[
					2.0950969890764055,
					4.050520845547432
				],
				[
					2.3744432542864926,
					4.609213375967773
				],
				[
					2.5141163868916196,
					5.028232773782987
				],
				[
					2.5141163868916196,
					5.447252171598286
				],
				[
					2.3744432542864926,
					5.8662715694135
				],
				[
					2.0950969890764055,
					6.005944702018626
				],
				[
					1.9554238564712785,
					6.145617834623669
				],
				[
					1.6760775912610237,
					6.285290967228713
				],
				[
					1.3967313260509373,
					6.285290967228713
				],
				[
					1.1173850608406826,
					6.285290967228713
				],
				[
					0.6983656630254687,
					6.285290967228713
				],
				[
					0.1396731326051273,
					6.42496409983384
				],
				[
					-0.13967313260495945,
					6.42496409983384
				],
				[
					-0.27934626521008676,
					6.564637232438968
				],
				[
					-0.27934626521008676,
					6.564637232438968
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 394,
			"versionNonce": 54686699,
			"isDeleted": false,
			"id": "wXdVtNrk856bSRXQlrvLm",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1104.8042441356663,
			"y": 809.3256904644285,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.0282327737829045,
			"height": 12.01188940403717,
			"seed": 1037647179,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.13967313260495948,
					0
				],
				[
					0.2793462652100868,
					-0.13967313260504338
				],
				[
					0.2793462652100868,
					-0.9777119282355554
				],
				[
					0.2793462652100868,
					-1.3967313260507694
				],
				[
					0.13967313260495948,
					-2.5141163868914522
				],
				[
					-0.13967313260512731,
					-4.469540243362647
				],
				[
					-0.41901939781538194,
					-5.3075790389931585
				],
				[
					-0.41901939781538194,
					-5.586925304203329
				],
				[
					-0.5586925304203414,
					-6.564637232438884
				],
				[
					-0.6983656630254688,
					-7.123329762859226
				],
				[
					-0.9777119282357233,
					-7.682022293279567
				],
				[
					-1.1173850608406828,
					-8.240714823699909
				],
				[
					-1.1173850608406828,
					-8.659734221515121
				],
				[
					-1.2570581934458103,
					-9.218426751935464
				],
				[
					-1.3967313260509375,
					-9.497773017145633
				],
				[
					-1.536404458656065,
					-10.056465547565976
				],
				[
					-1.6760775912610242,
					-10.47548494538119
				],
				[
					-1.6760775912610242,
					-10.75483121059136
				],
				[
					-1.8157507238661517,
					-11.313523741011702
				],
				[
					-1.955423856471279,
					-11.592870006221872
				],
				[
					-1.955423856471279,
					-11.732543138827
				],
				[
					-1.955423856471279,
					-11.872216271432043
				],
				[
					-1.955423856471279,
					-12.01188940403717
				],
				[
					-2.0950969890762385,
					-12.01188940403717
				],
				[
					-2.374443254286493,
					-12.01188940403717
				],
				[
					-2.6537895194965797,
					-11.732543138827
				],
				[
					-3.2124820499169213,
					-11.592870006221872
				],
				[
					-3.6315014477323033,
					-11.313523741011702
				],
				[
					-3.9108477129423904,
					-11.03417747580153
				],
				[
					-4.190193978152477,
					-10.615158077986317
				],
				[
					-4.190193978152477,
					-10.335811812776146
				],
				[
					-4.190193978152477,
					-10.056465547565976
				],
				[
					-4.190193978152477,
					-9.777119282355805
				],
				[
					-4.190193978152477,
					-9.35809988454059
				],
				[
					-4.190193978152477,
					-9.07875361933042
				],
				[
					-4.329867110757604,
					-8.659734221515121
				],
				[
					-4.469540243362731,
					-8.520061088910078
				],
				[
					-4.609213375967859,
					-8.101041691094782
				],
				[
					-4.609213375967859,
					-7.961368558489738
				],
				[
					-4.748886508572818,
					-7.82169542588461
				],
				[
					-4.748886508572818,
					-7.82169542588461
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 392,
			"versionNonce": 524244037,
			"isDeleted": false,
			"id": "MvK5rm84DVYC7EXJHAtMk",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1108.994438113819,
			"y": 825.8071201118283,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.3075790389931585,
			"height": 13.827640127903237,
			"seed": 1839928875,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.1396731326051273,
					-0.13967313260504338
				],
				[
					-0.41901939781538183,
					-0.13967313260504338
				],
				[
					-1.2570581934458098,
					-0.419019397815214
				],
				[
					-1.8157507238661512,
					-0.419019397815214
				],
				[
					-2.234770121681365,
					-0.419019397815214
				],
				[
					-2.6537895194965793,
					-0.27934626521017064
				],
				[
					-3.0728089173117934,
					0
				],
				[
					-3.491828315127175,
					0.5586925304203413
				],
				[
					-4.050520845547516,
					0.9777119282356392
				],
				[
					-4.329867110757603,
					1.3967313260508532
				],
				[
					-4.329867110757603,
					1.6760775912610237
				],
				[
					-4.329867110757603,
					2.095096989076238
				],
				[
					-4.329867110757603,
					2.6537895194965793
				],
				[
					-4.329867110757603,
					3.4918283151270915
				],
				[
					-4.050520845547516,
					4.050520845547433
				],
				[
					-3.910847712942389,
					4.46954024336273
				],
				[
					-3.491828315127175,
					5.167905906388115
				],
				[
					-2.7934626521017063,
					5.8662715694135
				],
				[
					-2.5141163868916196,
					6.285290967228714
				],
				[
					-1.8157507238661512,
					6.843983497649055
				],
				[
					-1.1173850608406826,
					7.263002895464353
				],
				[
					-0.41901939781538183,
					7.821695425884694
				],
				[
					-0.1396731326051273,
					8.101041691094865
				],
				[
					0.27934626521008676,
					8.659734221515206
				],
				[
					0.6983656630253008,
					9.07875361933042
				],
				[
					0.838038795630428,
					9.218426751935548
				],
				[
					0.9777119282355554,
					9.777119282355889
				],
				[
					0.9777119282355554,
					10.196138680171103
				],
				[
					0.9777119282355554,
					10.615158077986317
				],
				[
					0.838038795630428,
					11.313523741011785
				],
				[
					0.419019397815214,
					11.732543138827
				],
				[
					-0.1396731326051273,
					12.43090880185247
				],
				[
					-0.5586925304203413,
					12.710255067062555
				],
				[
					-0.9777119282355554,
					13.129274464877852
				],
				[
					-1.2570581934458098,
					13.268947597482898
				],
				[
					-1.3967313260509373,
					13.408620730088023
				],
				[
					-1.5364044586558967,
					13.408620730088023
				],
				[
					-1.8157507238661512,
					13.408620730088023
				],
				[
					-1.9554238564712785,
					13.408620730088023
				],
				[
					-1.9554238564712785,
					13.408620730088023
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 389,
			"versionNonce": 1984085643,
			"isDeleted": false,
			"id": "E_aWQqwo2mRG6CLY0JVrt",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1114.0226708876016,
			"y": 836.7016244550248,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 3.3521551825220475,
			"height": 6.005944702018627,
			"seed": 1902903403,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.1396731326051273
				],
				[
					0,
					0.4190193978152979
				],
				[
					0,
					0.9777119282356392
				],
				[
					0.1396731326051273,
					1.3967313260508532
				],
				[
					0.41901939781538183,
					1.6760775912610237
				],
				[
					0.5586925304203413,
					2.234770121681365
				],
				[
					0.6983656630254687,
					2.3744432542864082
				],
				[
					0.9777119282355554,
					2.3744432542864082
				],
				[
					1.2570581934458098,
					2.3744432542864082
				],
				[
					1.3967313260509373,
					2.3744432542864082
				],
				[
					1.9554238564712785,
					2.3744432542864082
				],
				[
					2.234770121681365,
					2.234770121681365
				],
				[
					2.5141163868916196,
					1.9554238564711945
				],
				[
					2.7934626521017063,
					1.6760775912610237
				],
				[
					2.933135784706834,
					1.3967313260508532
				],
				[
					3.0728089173117934,
					1.1173850608406826
				],
				[
					3.2124820499169204,
					0.8380387956305119
				],
				[
					3.3521551825220475,
					0.5586925304203413
				],
				[
					3.3521551825220475,
					0.4190193978152979
				],
				[
					3.3521551825220475,
					0.27934626521017064
				],
				[
					3.3521551825220475,
					0.4190193978152979
				],
				[
					3.3521551825220475,
					0.9777119282356392
				],
				[
					3.3521551825220475,
					1.3967313260508532
				],
				[
					3.3521551825220475,
					1.6760775912610237
				],
				[
					3.3521551825220475,
					2.0950969890763216
				],
				[
					3.3521551825220475,
					2.6537895194965793
				],
				[
					3.3521551825220475,
					3.0728089173118773
				],
				[
					3.2124820499169204,
					3.7711745803372616
				],
				[
					3.0728089173117934,
					4.050520845547433
				],
				[
					3.0728089173117934,
					4.609213375967774
				],
				[
					3.0728089173117934,
					4.888559641177944
				],
				[
					3.0728089173117934,
					5.167905906388115
				],
				[
					3.0728089173117934,
					5.447252171598286
				],
				[
					3.2124820499169204,
					5.586925304203329
				],
				[
					3.2124820499169204,
					5.8662715694135
				],
				[
					3.3521551825220475,
					6.005944702018627
				],
				[
					3.3521551825220475,
					6.005944702018627
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 397,
			"versionNonce": 322339749,
			"isDeleted": false,
			"id": "5rrLPV-Pof-k5w2xQrrij",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1133.7165825849186,
			"y": 778.8769475565203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.285290967228714,
			"height": 12.849928199667682,
			"seed": 564316875,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.13967313260495945,
					0
				],
				[
					-0.4190193978152141,
					-0.2793462652101706
				],
				[
					-0.8380387956304282,
					-0.41901939781529784
				],
				[
					-1.676077591261024,
					-0.6983656630254685
				],
				[
					-2.7934626521017067,
					-0.8380387956305118
				],
				[
					-3.771174580337262,
					-1.1173850608406823
				],
				[
					-4.329867110757604,
					-1.1173850608406823
				],
				[
					-4.888559641177945,
					-0.8380387956305118
				],
				[
					-5.1679059063880315,
					-0.5586925304203412
				],
				[
					-5.586925304203246,
					0
				],
				[
					-5.866271569413501,
					0.5586925304203412
				],
				[
					-5.866271569413501,
					1.396731326050853
				],
				[
					-5.7265984368083735,
					1.815750723866067
				],
				[
					-5.447252171598118,
					2.514116386891452
				],
				[
					-4.748886508572817,
					3.072808917311793
				],
				[
					-4.329867110757604,
					3.631501447732134
				],
				[
					-3.771174580337262,
					4.190193978152475
				],
				[
					-2.7934626521017067,
					5.028232773782987
				],
				[
					-2.234770121681365,
					5.586925304203328
				],
				[
					-1.676077591261024,
					6.285290967228713
				],
				[
					-1.2570581934456422,
					6.983656630254098
				],
				[
					-1.1173850608406826,
					7.402676028069395
				],
				[
					-0.6983656630253008,
					7.961368558489737
				],
				[
					-0.5586925304203413,
					8.38038795630495
				],
				[
					-0.5586925304203413,
					8.79940735412025
				],
				[
					-0.5586925304203413,
					9.078753619330419
				],
				[
					-0.5586925304203413,
					9.497773017145633
				],
				[
					-0.5586925304203413,
					9.637446149750676
				],
				[
					-0.6983656630253008,
					10.196138680171018
				],
				[
					-1.3967313260507694,
					10.754831210591359
				],
				[
					-1.8157507238659836,
					11.03417747580153
				],
				[
					-2.234770121681365,
					11.173850608406656
				],
				[
					-2.7934626521017067,
					11.3135237410117
				],
				[
					-3.3521551825218805,
					11.59287000622187
				],
				[
					-3.910847712942222,
					11.59287000622187
				],
				[
					-4.329867110757604,
					11.59287000622187
				],
				[
					-4.748886508572817,
					11.732543138827
				],
				[
					-5.1679059063880315,
					11.732543138827
				],
				[
					-5.307579038993159,
					11.732543138827
				],
				[
					-5.586925304203246,
					11.453196873616827
				],
				[
					-5.7265984368083735,
					11.453196873616827
				],
				[
					-6.145617834623588,
					11.173850608406656
				],
				[
					-6.285290967228714,
					11.03417747580153
				],
				[
					-6.285290967228714,
					11.03417747580153
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 382,
			"versionNonce": 1142994219,
			"isDeleted": false,
			"id": "uBlPzubhcHzO_zcYKiQ8T",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1139.1638347565167,
			"y": 787.1176623802203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 2.5141163868914522,
			"height": 6.843983497649055,
			"seed": 1793429387,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.27934626521008676,
					-0.1396731326051273
				],
				[
					-0.419019397815214,
					-0.1396731326051273
				],
				[
					-0.6983656630254687,
					-0.1396731326051273
				],
				[
					-0.9777119282355554,
					-0.1396731326051273
				],
				[
					-1.3967313260507694,
					-0.1396731326051273
				],
				[
					-1.6760775912610237,
					0
				],
				[
					-1.9554238564711108,
					0.6983656630253847
				],
				[
					-1.9554238564711108,
					1.1173850608406826
				],
				[
					-1.9554238564711108,
					1.3967313260507694
				],
				[
					-1.8157507238661512,
					1.6760775912610237
				],
				[
					-1.8157507238661512,
					2.3744432542864082
				],
				[
					-1.6760775912610237,
					2.7934626521016224
				],
				[
					-1.5364044586558967,
					3.2124820499169204
				],
				[
					-1.5364044586558967,
					3.352155182521964
				],
				[
					-1.5364044586558967,
					3.4918283151270915
				],
				[
					-1.3967313260507694,
					3.4918283151270915
				],
				[
					-1.1173850608406826,
					3.910847712942305
				],
				[
					-0.9777119282355554,
					4.190193978152476
				],
				[
					-0.6983656630254687,
					4.469540243362647
				],
				[
					-0.27934626521008676,
					5.028232773782988
				],
				[
					-0.1396731326051273,
					5.447252171598202
				],
				[
					-0.1396731326051273,
					6.005944702018543
				],
				[
					-0.419019397815214,
					6.005944702018543
				],
				[
					-0.6983656630254687,
					6.285290967228714
				],
				[
					-1.1173850608406826,
					6.285290967228714
				],
				[
					-1.3967313260507694,
					6.285290967228714
				],
				[
					-1.6760775912610237,
					6.424964099833841
				],
				[
					-2.095096989076238,
					6.564637232438884
				],
				[
					-2.5141163868914522,
					6.704310365043928
				],
				[
					-2.5141163868914522,
					6.704310365043928
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 395,
			"versionNonce": 324060933,
			"isDeleted": false,
			"id": "O7lEnk6U2EZbI2rEpFuSw",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1133.4372363197085,
			"y": 803.1800726298048,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.726598436808373,
			"height": 13.548293862693066,
			"seed": 434480011,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.1396731326051273,
					0
				],
				[
					-0.419019397815214,
					0
				],
				[
					-0.9777119282355554,
					0
				],
				[
					-1.8157507238661512,
					0.1396731326051273
				],
				[
					-2.3744432542864926,
					0.4190193978152979
				],
				[
					-2.6537895194965793,
					0.5586925304203413
				],
				[
					-3.0728089173117934,
					0.9777119282356392
				],
				[
					-3.3521551825220475,
					1.3967313260508532
				],
				[
					-3.491828315127175,
					1.6760775912610237
				],
				[
					-3.491828315127175,
					2.234770121681365
				],
				[
					-3.6315014477321346,
					2.93313578470675
				],
				[
					-3.6315014477321346,
					3.6315014477322185
				],
				[
					-3.3521551825220475,
					4.329867110757603
				],
				[
					-3.0728089173117934,
					5.028232773782988
				],
				[
					-2.6537895194965793,
					5.8662715694135
				],
				[
					-2.095096989076238,
					6.424964099833841
				],
				[
					-1.5364044586558967,
					6.843983497649139
				],
				[
					-0.8380387956305958,
					7.4026760280694806
				],
				[
					-0.2793462652102546,
					7.682022293279567
				],
				[
					0.27934626521008676,
					8.101041691094865
				],
				[
					0.5586925304203413,
					8.520061088910078
				],
				[
					1.1173850608406826,
					9.07875361933042
				],
				[
					1.257058193445642,
					9.218426751935548
				],
				[
					1.6760775912610237,
					9.777119282355889
				],
				[
					1.8157507238659834,
					10.056465547566061
				],
				[
					1.9554238564711108,
					10.475484945381274
				],
				[
					2.095096989076238,
					10.894504343196488
				],
				[
					2.095096989076238,
					11.173850608406658
				],
				[
					1.9554238564711108,
					11.592870006221956
				],
				[
					1.8157507238659834,
					11.872216271432126
				],
				[
					1.5364044586558967,
					12.151562536642297
				],
				[
					0.9777119282355554,
					12.570581934457511
				],
				[
					0.5586925304203413,
					12.710255067062638
				],
				[
					0.1396731326051273,
					12.849928199667682
				],
				[
					-0.2793462652102546,
					12.989601332272725
				],
				[
					-0.6983656630254687,
					12.989601332272725
				],
				[
					-1.1173850608406826,
					13.129274464877852
				],
				[
					-1.3967313260509373,
					13.129274464877852
				],
				[
					-1.6760775912610237,
					13.268947597482981
				],
				[
					-1.9554238564712785,
					13.408620730088023
				],
				[
					-2.095096989076238,
					13.408620730088023
				],
				[
					-2.3744432542864926,
					13.548293862693066
				],
				[
					-2.3744432542864926,
					13.548293862693066
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 387,
			"versionNonce": 474404811,
			"isDeleted": false,
			"id": "CE6dYqwGcRKuL2ngR9QhO",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1141.2589317455931,
			"y": 813.515884442581,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 3.771174580337094,
			"height": 5.3075790389931585,
			"seed": 23004587,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.27934626521008676,
					0.27934626521017064
				],
				[
					-0.9777119282355554,
					0.6983656630254687
				],
				[
					-1.6760775912610237,
					1.2570581934458098
				],
				[
					-2.095096989076238,
					2.0950969890763216
				],
				[
					-2.3744432542863247,
					3.0728089173118773
				],
				[
					-2.3744432542863247,
					3.6315014477322185
				],
				[
					-2.3744432542863247,
					3.7711745803372616
				],
				[
					-2.3744432542863247,
					4.329867110757603
				],
				[
					-2.095096989076238,
					4.748886508572901
				],
				[
					-1.8157507238661512,
					4.888559641177944
				],
				[
					-1.5364044586558967,
					5.028232773783071
				],
				[
					-0.9777119282355554,
					5.3075790389931585
				],
				[
					-0.5586925304203413,
					5.3075790389931585
				],
				[
					-0.1396731326051273,
					5.3075790389931585
				],
				[
					0.27934626521008676,
					5.3075790389931585
				],
				[
					0.6983656630254687,
					5.3075790389931585
				],
				[
					0.9777119282355554,
					5.167905906388115
				],
				[
					1.1173850608406826,
					5.028232773783071
				],
				[
					1.3967313260507694,
					4.748886508572901
				],
				[
					1.3967313260507694,
					4.329867110757603
				],
				[
					1.3967313260507694,
					4.050520845547433
				],
				[
					1.3967313260507694,
					3.6315014477322185
				],
				[
					1.3967313260507694,
					3.4918283151270915
				],
				[
					1.1173850608406826,
					3.2124820499169204
				],
				[
					0.8380387956305958,
					3.0728089173118773
				],
				[
					0.419019397815214,
					2.7934626521017063
				],
				[
					0,
					2.7934626521017063
				],
				[
					-0.27934626521008676,
					2.7934626521017063
				],
				[
					-0.6983656630254687,
					2.7934626521017063
				],
				[
					-0.9777119282355554,
					2.933135784706834
				],
				[
					-1.1173850608406826,
					2.933135784706834
				],
				[
					-1.2570581934458098,
					3.0728089173118773
				],
				[
					-1.3967313260507694,
					3.2124820499169204
				],
				[
					-1.5364044586558967,
					3.2124820499169204
				],
				[
					-1.5364044586558967,
					3.2124820499169204
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 382,
			"versionNonce": 1376493157,
			"isDeleted": false,
			"id": "2CBDrw2U4F5uPdhmnVUaK",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1135.5323333087847,
			"y": 840.6124721679671,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 4.050520845547348,
			"height": 10.47548494538119,
			"seed": 1032990411,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.27934626521008676,
					0
				],
				[
					0.419019397815214,
					-0.419019397815214
				],
				[
					0.419019397815214,
					-0.6983656630253847
				],
				[
					0.419019397815214,
					-1.5364044586558967
				],
				[
					0.419019397815214,
					-2.6537895194965793
				],
				[
					0,
					-3.2124820499168365
				],
				[
					-0.1396731326051273,
					-4.469540243362562
				],
				[
					-0.2793462652102546,
					-5.447252171598202
				],
				[
					-0.2793462652102546,
					-6.4249640998337565
				],
				[
					-0.419019397815214,
					-7.54234916067444
				],
				[
					-0.419019397815214,
					-8.240714823699825
				],
				[
					-0.5586925304203413,
					-8.799407354120165
				],
				[
					-0.8380387956305958,
					-9.497773017145633
				],
				[
					-0.9777119282355554,
					-9.916792414960849
				],
				[
					-0.9777119282355554,
					-10.056465547565976
				],
				[
					-1.1173850608406826,
					-10.196138680171018
				],
				[
					-1.1173850608406826,
					-10.335811812776061
				],
				[
					-1.2570581934458098,
					-10.47548494538119
				],
				[
					-1.3967313260509373,
					-10.47548494538119
				],
				[
					-1.5364044586558967,
					-10.47548494538119
				],
				[
					-1.9554238564711108,
					-10.335811812776061
				],
				[
					-2.095096989076238,
					-10.196138680171018
				],
				[
					-2.5141163868914522,
					-9.916792414960849
				],
				[
					-2.6537895194965793,
					-9.777119282355805
				],
				[
					-2.933135784706834,
					-9.497773017145633
				],
				[
					-3.0728089173117934,
					-9.358099884540506
				],
				[
					-3.2124820499169204,
					-9.078753619330337
				],
				[
					-3.491828315127175,
					-8.659734221515121
				],
				[
					-3.6315014477321346,
					-8.380387956304952
				],
				[
					-3.6315014477321346,
					-8.380387956304952
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 372,
			"versionNonce": 1557112427,
			"isDeleted": false,
			"id": "YEODcWuUEyPzev1b1nH48",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1286.4121628746866,
			"y": 785.5059670824469,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.2411597169398805,
			"height": 0,
			"seed": 113329701,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3914140387534526,
					0
				],
				[
					0.9785350968837995,
					0
				],
				[
					1.7613631743907048,
					0
				],
				[
					2.3484842325210513,
					0
				],
				[
					2.93560529065123,
					0
				],
				[
					3.7184333681583035,
					0
				],
				[
					4.109847406911756,
					0
				],
				[
					4.3055544262886505,
					0
				],
				[
					4.696968465042103,
					0
				],
				[
					5.088382503795556,
					0
				],
				[
					5.284089523172449,
					0
				],
				[
					5.675503561925902,
					0
				],
				[
					5.871210581302629,
					0
				],
				[
					6.458331639432807,
					0
				],
				[
					6.654038658809702,
					0
				],
				[
					6.849745678186428,
					0
				],
				[
					7.045452697563154,
					0
				],
				[
					7.2411597169398805,
					0
				],
				[
					7.045452697563154,
					0
				],
				[
					7.045452697563154,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 373,
			"versionNonce": 1446283717,
			"isDeleted": false,
			"id": "sarZrH1gbmM382mpRPXxJ",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1288.7606471072077,
			"y": 781.9832407336652,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0.39141403875362046,
			"height": 8.219694813823763,
			"seed": 795196517,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.7828280775070728
				],
				[
					0,
					1.1742421162606094
				],
				[
					0,
					1.9570701937675983
				],
				[
					0,
					2.544191251897861
				],
				[
					0,
					3.131312310028124
				],
				[
					0,
					3.9141403875351966
				],
				[
					0,
					4.501261445665459
				],
				[
					0,
					4.892675484418912
				],
				[
					0,
					5.284089523172448
				],
				[
					0,
					5.675503561925984
				],
				[
					0,
					5.8712105813027105
				],
				[
					0,
					6.066917600679521
				],
				[
					0,
					6.262624620056248
				],
				[
					-0.1957070193767263,
					6.4583316394329735
				],
				[
					-0.39141403875362046,
					6.849745678186511
				],
				[
					-0.39141403875362046,
					7.241159716940047
				],
				[
					-0.39141403875362046,
					7.436866736316773
				],
				[
					-0.39141403875362046,
					7.82828077507031
				],
				[
					-0.39141403875362046,
					8.023987794447036
				],
				[
					-0.39141403875362046,
					8.219694813823763
				],
				[
					-0.39141403875362046,
					8.219694813823763
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 389,
			"versionNonce": 1015390475,
			"isDeleted": false,
			"id": "X_GYtXSp1IjfOBSAu3fJi",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1303.8300875992177,
			"y": 781.7875337142885,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.871210581302629,
			"height": 10.372472026968007,
			"seed": 2053793285,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.7828280775069052,
					0
				],
				[
					-1.7613631743907048,
					-0.19570701937672633
				],
				[
					-2.544191251897778,
					-0.19570701937672633
				],
				[
					-3.327019329404851,
					-0.19570701937672633
				],
				[
					-3.7184333681583035,
					-0.19570701937672633
				],
				[
					-3.91414038753503,
					0
				],
				[
					-4.109847406911756,
					0.19570701937672633
				],
				[
					-4.109847406911756,
					0.9785350968837996
				],
				[
					-4.109847406911756,
					1.1742421162605259
				],
				[
					-3.91414038753503,
					1.7613631743907887
				],
				[
					-3.327019329404851,
					2.3484842325210518
				],
				[
					-2.7398982712745044,
					2.9356052906513987
				],
				[
					-2.1527772131443252,
					3.718433368158388
				],
				[
					-1.3699491356372522,
					4.305554426288651
				],
				[
					-0.5871210581301789,
					4.696968465042187
				],
				[
					0,
					5.28408952317245
				],
				[
					0.39141403875362046,
					5.675503561925903
				],
				[
					0.5871210581303468,
					5.871210581302713
				],
				[
					1.1742421162605257,
					6.2626246200562505
				],
				[
					1.36994913563742,
					6.654038658809702
				],
				[
					1.5656561550141461,
					7.045452697563239
				],
				[
					1.5656561550141461,
					7.241159716939965
				],
				[
					1.7613631743908724,
					7.632573755693502
				],
				[
					1.7613631743908724,
					8.02398779444704
				],
				[
					1.5656561550141461,
					8.415401833200491
				],
				[
					1.36994913563742,
					8.611108852577303
				],
				[
					0.7828280775070731,
					9.198229910707566
				],
				[
					0.39141403875362046,
					9.39393693008429
				],
				[
					-0.1957070193767263,
					9.785350968837827
				],
				[
					-0.9785350968836316,
					9.981057988214554
				],
				[
					-1.3699491356372522,
					10.17676500759128
				],
				[
					-2.1527772131443252,
					10.17676500759128
				],
				[
					-2.7398982712745044,
					10.17676500759128
				],
				[
					-3.327019329404851,
					10.17676500759128
				],
				[
					-3.522726348781577,
					10.17676500759128
				],
				[
					-3.7184333681583035,
					10.17676500759128
				],
				[
					-3.7184333681583035,
					10.17676500759128
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 388,
			"versionNonce": 1894320421,
			"isDeleted": false,
			"id": "-g5JrldYmFNi4Pmaj2gOB",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1310.5139194324126,
			"y": 789.6150821264199,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.539045559739055,
			"height": 7.79569375074388,
			"seed": 1127119269,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.2051498355458474,
					0
				],
				[
					0.6154495066375422,
					0
				],
				[
					1.0257491777294048,
					0.20514983554584743
				],
				[
					1.4360488488212675,
					0.20514983554584743
				],
				[
					1.8463485199129623,
					0.6154495066376262
				],
				[
					2.0514983554588095,
					0.8205993421835575
				],
				[
					2.2566481910048246,
					1.025749177729405
				],
				[
					2.2566481910048246,
					1.2308990132753364
				],
				[
					2.4617980265506723,
					1.8463485199129626
				],
				[
					2.4617980265506723,
					2.051498355458894
				],
				[
					2.2566481910048246,
					2.256648191004825
				],
				[
					1.6411986843671147,
					2.8720976976424515
				],
				[
					1.0257491777294048,
					3.0772475331883826
				],
				[
					0.4102996710916948,
					3.28239736873423
				],
				[
					-0.2051498355458474,
					3.4875472042801614
				],
				[
					0,
					3.4875472042801614
				],
				[
					0.4102996710916948,
					3.692697039826009
				],
				[
					1.2308990132752522,
					4.102996710917788
				],
				[
					1.8463485199129623,
					4.308146546463719
				],
				[
					1.8463485199129623,
					4.718446217555498
				],
				[
					2.0514983554588095,
					4.923596053101345
				],
				[
					2.0514983554588095,
					5.333895724193208
				],
				[
					2.0514983554588095,
					5.539045559739055
				],
				[
					1.8463485199129623,
					5.744195395284903
				],
				[
					1.2308990132752522,
					6.154495066376765
				],
				[
					0.8205993421835573,
					6.3596449019226124
				],
				[
					0,
					6.769944573014391
				],
				[
					-0.8205993421835573,
					6.975094408560323
				],
				[
					-1.4360488488212675,
					7.59054391519795
				],
				[
					-2.0514983554589774,
					7.79569375074388
				],
				[
					-2.2566481910048246,
					7.79569375074388
				],
				[
					-2.46179802655084,
					7.79569375074388
				],
				[
					-2.872097697642535,
					7.79569375074388
				],
				[
					-3.077247533188382,
					7.59054391519795
				],
				[
					-3.077247533188382,
					7.3853940796521025
				],
				[
					-3.077247533188382,
					7.3853940796521025
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 411,
			"versionNonce": 887310251,
			"isDeleted": false,
			"id": "ryjiwKDCYsryIXX9OmSlR",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1316.8735643343352,
			"y": 783.6657368955891,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.3596449019226124,
			"height": 18.258335363584447,
			"seed": 953181669,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.41029967109177873
				],
				[
					0.2051498355458474,
					1.2308990132754203
				],
				[
					0.4102996710916948,
					1.8463485199130463
				],
				[
					0.61544950663771,
					2.666947862096604
				],
				[
					0.8205993421835573,
					3.4875472042801614
				],
				[
					1.0257491777294048,
					4.102996710917871
				],
				[
					1.23089901327542,
					4.718446217555498
				],
				[
					1.6411986843671147,
					5.1287458886473605
				],
				[
					1.8463485199129623,
					5.333895724193208
				],
				[
					2.0514983554588095,
					5.333895724193208
				],
				[
					2.2566481910048246,
					5.333895724193208
				],
				[
					2.4617980265506723,
					5.333895724193208
				],
				[
					2.872097697642535,
					4.923596053101429
				],
				[
					3.077247533188382,
					4.51329638200965
				],
				[
					3.2823973687342294,
					4.102996710917871
				],
				[
					3.4875472042800775,
					3.6926970398260925
				],
				[
					3.692697039826092,
					3.0772475331883826
				],
				[
					4.102996710917787,
					2.4617980265507566
				],
				[
					4.308146546463802,
					1.8463485199130463
				],
				[
					4.308146546463802,
					1.641198684367199
				],
				[
					4.513296382009649,
					1.2308990132754203
				],
				[
					4.513296382009649,
					1.0257491777294887
				],
				[
					4.718446217555497,
					1.0257491777294887
				],
				[
					4.718446217555497,
					1.2308990132754203
				],
				[
					4.718446217555497,
					2.0514983554589774
				],
				[
					4.718446217555497,
					2.872097697642535
				],
				[
					4.718446217555497,
					3.89784687537194
				],
				[
					4.718446217555497,
					4.923596053101429
				],
				[
					4.718446217555497,
					6.154495066376765
				],
				[
					4.718446217555497,
					7.1802442441062535
				],
				[
					4.718446217555497,
					7.3853940796521025
				],
				[
					4.308146546463802,
					8.41114325738159
				],
				[
					4.102996710917787,
					9.43689243511108
				],
				[
					3.8978468753719397,
					10.667791448386415
				],
				[
					3.692697039826092,
					11.693540626115821
				],
				[
					3.2823973687342294,
					12.71928980384531
				],
				[
					2.872097697642535,
					13.950188817120646
				],
				[
					2.4617980265506723,
					15.181087830396066
				],
				[
					2.2566481910048246,
					16.001687172579622
				],
				[
					1.6411986843671147,
					16.82228651476318
				],
				[
					1.23089901327542,
					17.23258618585496
				],
				[
					0.61544950663771,
					17.848035692492584
				],
				[
					0,
					18.05318552803852
				],
				[
					-0.2051498355458474,
					18.258335363584447
				],
				[
					-0.4102996710918626,
					18.258335363584447
				],
				[
					-0.61544950663771,
					18.05318552803852
				],
				[
					-1.0257491777294048,
					17.437736021400806
				],
				[
					-1.23089901327542,
					17.027436350309028
				],
				[
					-1.4360488488212675,
					16.411986843671404
				],
				[
					-1.6411986843671147,
					15.796537337033694
				],
				[
					-1.6411986843671147,
					15.386237665941913
				],
				[
					-1.6411986843671147,
					15.181087830396066
				],
				[
					-1.4360488488212675,
					15.181087830396066
				],
				[
					-1.23089901327542,
					15.181087830396066
				],
				[
					-1.0257491777294048,
					15.181087830396066
				],
				[
					-0.61544950663771,
					15.181087830396066
				],
				[
					-0.4102996710918626,
					15.181087830396066
				],
				[
					-0.4102996710918626,
					15.181087830396066
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 363,
			"versionNonce": 1939250309,
			"isDeleted": false,
			"id": "HS-phyUiC-E0OI5bZdFYf",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1328.3619551249053,
			"y": 789.409932290874,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.975094408560323,
			"height": 1.0257491777294887,
			"seed": 1908054117,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20514983554584743,
					0.20514983554593128
				],
				[
					1.025749177729405,
					0.4102996710917786
				],
				[
					2.0514983554589774,
					0.6154495066377099
				],
				[
					3.0772475331883826,
					0.6154495066377099
				],
				[
					4.102996710917788,
					0.8205993421835572
				],
				[
					5.128745888647193,
					0.8205993421835572
				],
				[
					5.539045559739055,
					1.0257491777294887
				],
				[
					6.154495066376765,
					1.0257491777294887
				],
				[
					6.769944573014476,
					1.0257491777294887
				],
				[
					6.975094408560323,
					1.0257491777294887
				],
				[
					6.975094408560323,
					1.0257491777294887
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 378,
			"versionNonce": 739449419,
			"isDeleted": false,
			"id": "AlO0sCH6SiULoG2ldfTH7",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1332.670101671369,
			"y": 785.512085415502,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0.6154495066377101,
			"height": 9.231742599565065,
			"seed": 832857157,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20514983554584745,
					-0.20514983554584743
				],
				[
					0.4102996710918627,
					-0.20514983554584743
				],
				[
					0.4102996710918627,
					0
				],
				[
					0.4102996710918627,
					0.8205993421835575
				],
				[
					0.4102996710918627,
					1.2308990132753364
				],
				[
					0.4102996710918627,
					2.051498355458894
				],
				[
					0.4102996710918627,
					2.8720976976424515
				],
				[
					0.4102996710918627,
					3.89784687537194
				],
				[
					0.4102996710918627,
					4.718446217555498
				],
				[
					0.4102996710918627,
					5.7441953952849865
				],
				[
					0.4102996710918627,
					6.154495066376765
				],
				[
					0.4102996710918627,
					6.564794737468544
				],
				[
					0.4102996710918627,
					6.769944573014476
				],
				[
					0.4102996710918627,
					6.975094408560323
				],
				[
					0.4102996710918627,
					7.1802442441062535
				],
				[
					0.4102996710918627,
					7.3853940796521025
				],
				[
					0.4102996710918627,
					7.590543915198033
				],
				[
					0.4102996710918627,
					7.79569375074388
				],
				[
					0.4102996710918627,
					8.000843586289811
				],
				[
					0.4102996710918627,
					8.20599342183566
				],
				[
					0.4102996710918627,
					8.41114325738159
				],
				[
					0.4102996710918627,
					8.616293092927439
				],
				[
					0.4102996710918627,
					8.82144292847337
				],
				[
					0.4102996710918627,
					9.026592764019217
				],
				[
					0.6154495066377101,
					9.026592764019217
				],
				[
					0.6154495066377101,
					9.026592764019217
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 388,
			"versionNonce": 637191141,
			"isDeleted": false,
			"id": "twiDPQnxCEX2osuDQxRui",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1346.662603474379,
			"y": 780.5186047896642,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.471842460548744,
			"height": 14.88523765926226,
			"seed": 1404246725,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.21572808201830823
				],
				[
					-1.0786404100913733,
					0.21572808201830823
				],
				[
					-2.3730089022012226,
					0.43145616403661646
				],
				[
					-3.667377394310904,
					0.862912328073149
				],
				[
					-4.746017804402445,
					1.2943684921097653
				],
				[
					-4.961745886420753,
					1.5100965741280736
				],
				[
					-5.39320205045737,
					1.9415527381646063
				],
				[
					-5.824658214493819,
					2.5887369842195307
				],
				[
					-6.040386296512127,
					3.45164931229268
				],
				[
					-6.040386296512127,
					4.314561640365828
				],
				[
					-5.6089301324755105,
					4.961745886420753
				],
				[
					-4.530289722384137,
					5.824658214493903
				],
				[
					-3.451649312292596,
					6.687570542567052
				],
				[
					-2.3730089022012226,
					7.119026706603668
				],
				[
					-1.2943684921096816,
					7.766210952658509
				],
				[
					-0.6471842460549247,
					7.9819390346768175
				],
				[
					0,
					8.413395198713433
				],
				[
					0.21572808201830823,
					8.844851362749965
				],
				[
					0.21572808201830823,
					9.276307526786582
				],
				[
					0.43145616403661646,
					9.923491772841507
				],
				[
					0.43145616403661646,
					10.35494793687804
				],
				[
					0.43145616403661646,
					11.217860264951188
				],
				[
					0,
					11.865044511006113
				],
				[
					-0.21572808201830823,
					12.29650067504273
				],
				[
					-0.6471842460549247,
					12.94368492109757
				],
				[
					-1.2943684921096816,
					13.375141085134187
				],
				[
					-2.157280820182914,
					14.238053413207336
				],
				[
					-2.8044650662376713,
					14.453781495225645
				],
				[
					-3.451649312292596,
					14.669509577243954
				],
				[
					-3.8831054763292125,
					14.669509577243954
				],
				[
					-4.314561640365828,
					14.88523765926226
				],
				[
					-4.530289722384137,
					14.88523765926226
				],
				[
					-4.746017804402445,
					14.88523765926226
				],
				[
					-4.961745886420753,
					14.88523765926226
				],
				[
					-4.530289722384137,
					14.88523765926226
				],
				[
					-4.530289722384137,
					14.88523765926226
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 395,
			"versionNonce": 1592760555,
			"isDeleted": false,
			"id": "OmxVO4pU56xia9SzAKBFo",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1352.2715336068547,
			"y": 791.9521931366337,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 3.8831054763292125,
			"height": 7.119026706603668,
			"seed": 1491414789,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.21572808201830823
				],
				[
					-0.21572808201830823,
					-0.21572808201830823
				],
				[
					-0.6471842460549247,
					-0.43145616403653253
				],
				[
					-1.0786404100915412,
					-0.6471842460548408
				],
				[
					-1.2943684921098495,
					-0.6471842460548408
				],
				[
					-1.725824656146298,
					-0.6471842460548408
				],
				[
					-2.157280820182914,
					-0.6471842460548408
				],
				[
					-2.3730089022012226,
					-0.6471842460548408
				],
				[
					-2.5887369842195307,
					-0.6471842460548408
				],
				[
					-3.0201931482561473,
					-0.6471842460548408
				],
				[
					-3.451649312292596,
					-0.21572808201830823
				],
				[
					-3.667377394310904,
					0
				],
				[
					-3.667377394310904,
					0.21572808201830823
				],
				[
					-3.667377394310904,
					0.43145616403661646
				],
				[
					-3.667377394310904,
					0.6471842460549247
				],
				[
					-3.667377394310904,
					1.078640410091457
				],
				[
					-3.667377394310904,
					1.2943684921097653
				],
				[
					-3.667377394310904,
					1.5100965741280736
				],
				[
					-3.667377394310904,
					1.725824656146382
				],
				[
					-3.667377394310904,
					2.3730089022012226
				],
				[
					-3.667377394310904,
					2.5887369842195307
				],
				[
					-3.667377394310904,
					2.804465066237839
				],
				[
					-2.804465066237839,
					2.804465066237839
				],
				[
					-2.157280820182914,
					2.804465066237839
				],
				[
					-1.725824656146298,
					3.0201931482561473
				],
				[
					-1.5100965741281576,
					3.2359212302744558
				],
				[
					-1.2943684921098495,
					3.6673773943109884
				],
				[
					-1.0786404100915412,
					4.0988335583476045
				],
				[
					-1.0786404100915412,
					4.530289722384137
				],
				[
					-0.8629123280732329,
					4.746017804402445
				],
				[
					-0.8629123280732329,
					5.177473968439061
				],
				[
					-1.0786404100915412,
					5.39320205045737
				],
				[
					-1.2943684921098495,
					5.8246582144939865
				],
				[
					-1.725824656146298,
					6.040386296512211
				],
				[
					-1.9415527381646063,
					6.256114378530519
				],
				[
					-2.3730089022012226,
					6.256114378530519
				],
				[
					-2.5887369842195307,
					6.471842460548827
				],
				[
					-3.0201931482561473,
					6.471842460548827
				],
				[
					-3.2359212302744558,
					6.471842460548827
				],
				[
					-3.451649312292596,
					6.471842460548827
				],
				[
					-3.667377394310904,
					6.471842460548827
				],
				[
					-3.8831054763292125,
					6.471842460548827
				],
				[
					-3.8831054763292125,
					6.471842460548827
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 395,
			"versionNonce": 2082668357,
			"isDeleted": false,
			"id": "PDFZ21Tb2u7G_8RYYFlYZ",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1356.3703671652022,
			"y": 783.3230698559021,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 10.354947936878123,
			"height": 13.375141085134103,
			"seed": 37905125,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.2943684921098493,
					0
				],
				[
					2.5887369842195307,
					0
				],
				[
					3.4516493122927634,
					0
				],
				[
					4.09883355834752,
					0
				],
				[
					4.961745886420752,
					0
				],
				[
					6.040386296512294,
					0
				],
				[
					6.256114378530603,
					0
				],
				[
					7.334754788621975,
					0
				],
				[
					7.981939034676901,
					0.2157280820182243
				],
				[
					8.413395198713516,
					0.43145616403653253
				],
				[
					9.060579444768273,
					0.6471842460548408
				],
				[
					9.276307526786582,
					0.862912328073149
				],
				[
					9.492035608804889,
					1.2943684921096816
				],
				[
					9.707763690823198,
					1.9415527381646063
				],
				[
					9.276307526786582,
					2.8044650662377553
				],
				[
					8.629123280731656,
					3.667377394310904
				],
				[
					7.766210952658592,
					4.530289722384137
				],
				[
					6.687570542567219,
					6.040386296512127
				],
				[
					6.040386296512294,
					6.90329862458536
				],
				[
					4.961745886420752,
					8.41339519871335
				],
				[
					4.314561640365828,
					9.923491772841423
				],
				[
					3.8831054763292117,
					11.00213218293288
				],
				[
					3.4516493122927634,
					11.865044511006113
				],
				[
					3.2359212302744553,
					12.080772593024422
				],
				[
					3.2359212302744553,
					12.296500675042646
				],
				[
					3.2359212302744553,
					12.512228757060955
				],
				[
					3.020193148256147,
					12.727956839079262
				],
				[
					3.020193148256147,
					12.94368492109757
				],
				[
					3.020193148256147,
					13.159413003115795
				],
				[
					3.4516493122927634,
					13.375141085134103
				],
				[
					4.530289722384136,
					13.375141085134103
				],
				[
					5.824658214493986,
					13.375141085134103
				],
				[
					6.687570542567219,
					13.159413003115795
				],
				[
					7.550482870640284,
					12.94368492109757
				],
				[
					8.197667116695207,
					12.512228757060955
				],
				[
					8.629123280731656,
					12.296500675042646
				],
				[
					9.060579444768273,
					12.296500675042646
				],
				[
					9.276307526786582,
					12.296500675042646
				],
				[
					9.492035608804889,
					12.296500675042646
				],
				[
					9.707763690823198,
					12.296500675042646
				],
				[
					10.139219854859814,
					12.080772593024422
				],
				[
					10.354947936878123,
					12.080772593024422
				],
				[
					10.354947936878123,
					12.080772593024422
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 372,
			"versionNonce": 184763275,
			"isDeleted": false,
			"id": "bqZFimJqM12qid9rBYe3S",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1357.6647356573121,
			"y": 789.3634561524142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 8.844851362749965,
			"height": 0.6471842460549247,
			"seed": 341691077,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6471842460549246,
					0
				],
				[
					1.2943684921096814,
					0.21572808201830826
				],
				[
					1.941552738164606,
					0.21572808201830826
				],
				[
					3.0201931482559794,
					0.21572808201830826
				],
				[
					4.314561640365828,
					0.21572808201830826
				],
				[
					4.746017804402445,
					0.21572808201830826
				],
				[
					5.3932020504573694,
					0.21572808201830826
				],
				[
					6.256114378530434,
					0.21572808201830826
				],
				[
					6.687570542567051,
					0.21572808201830826
				],
				[
					7.119026706603667,
					0.21572808201830826
				],
				[
					7.334754788621807,
					0.21572808201830826
				],
				[
					7.550482870640116,
					0.21572808201830826
				],
				[
					7.981939034676733,
					0.21572808201830826
				],
				[
					8.19766711669504,
					0.21572808201830826
				],
				[
					8.41339519871335,
					0.21572808201830826
				],
				[
					8.629123280731656,
					0.21572808201830826
				],
				[
					8.844851362749965,
					0.21572808201830826
				],
				[
					8.41339519871335,
					0.4314561640366165
				],
				[
					7.766210952658424,
					0.6471842460549247
				],
				[
					7.766210952658424,
					0.6471842460549247
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 365,
			"versionNonce": 208457381,
			"isDeleted": false,
			"id": "y-c8jHpNvrFWaNVW0NOFi",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1289.063205575495,
			"y": 810.7205362722252,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.119026706603668,
			"height": 0,
			"seed": 2017528069,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.2157280820181404,
					0
				],
				[
					1.0786404100913733,
					0
				],
				[
					1.9415527381646063,
					0
				],
				[
					2.804465066237839,
					0
				],
				[
					4.09883355834752,
					0
				],
				[
					4.9617458864205854,
					0
				],
				[
					6.040386296512127,
					0
				],
				[
					6.256114378530435,
					0
				],
				[
					6.471842460548744,
					0
				],
				[
					6.687570542567052,
					0
				],
				[
					6.90329862458536,
					0
				],
				[
					7.119026706603668,
					0
				],
				[
					7.119026706603668,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 369,
			"versionNonce": 1485347371,
			"isDeleted": false,
			"id": "Ka-iZr7f0xxdzz9IhplLC",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1292.5148548877876,
			"y": 807.2688869599325,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0.6471842460549247,
			"height": 9.276307526786667,
			"seed": 1316264869,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.21572808201830826,
					0.21572808201830823
				],
				[
					0.21572808201830826,
					0.8629123280732329
				],
				[
					0.21572808201830826,
					1.2943684921097653
				],
				[
					0.21572808201830826,
					1.725824656146382
				],
				[
					0.21572808201830826,
					2.3730089022012226
				],
				[
					0.21572808201830826,
					2.804465066237839
				],
				[
					0.21572808201830826,
					3.6673773943109884
				],
				[
					0.21572808201830826,
					4.530289722384221
				],
				[
					0.21572808201830826,
					5.608930132475594
				],
				[
					0.21572808201830826,
					6.040386296512211
				],
				[
					0.21572808201830826,
					6.687570542567136
				],
				[
					0.21572808201830826,
					7.334754788621977
				],
				[
					0.21572808201830826,
					7.9819390346768175
				],
				[
					0.4314561640366165,
					8.413395198713433
				],
				[
					0.4314561640366165,
					8.844851362750049
				],
				[
					0.6471842460549247,
					9.276307526786667
				],
				[
					0.6471842460549247,
					9.276307526786667
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 392,
			"versionNonce": 1166389765,
			"isDeleted": false,
			"id": "QyieNEU18pxK0T26JTz8m",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1307.1115205850833,
			"y": 807.9826084668435,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.210553990560521,
			"height": 8.733591549225721,
			"seed": 103479237,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.5822394366149755,
					-0.3881596244100115
				],
				[
					-1.164478873229951,
					-0.3881596244100115
				],
				[
					-1.746718309845094,
					-0.3881596244100115
				],
				[
					-2.5230375586651173,
					-0.1940798122049638
				],
				[
					-2.9111971830752124,
					0.19407981220504772
				],
				[
					-3.1052769952800925,
					0.38815962441009544
				],
				[
					-3.1052769952800925,
					0.7763192488201069
				],
				[
					-3.1052769952800925,
					1.1644788732301186
				],
				[
					-2.9111971830752124,
					1.55263849764013
				],
				[
					-2.3289577464600693,
					2.134877934255189
				],
				[
					-1.9407981220501418,
					2.5230375586652847
				],
				[
					-1.5526384976400462,
					2.9111971830752124
				],
				[
					-1.164478873229951,
					3.299356807485308
				],
				[
					-0.5822394366149755,
					3.881596244100367
				],
				[
					-0.1940798122048799,
					4.075676056305331
				],
				[
					0,
					4.269755868510378
				],
				[
					0.3881596244100955,
					4.463835680715426
				],
				[
					0.9703990610250709,
					5.0460751173304015
				],
				[
					1.3585586854351663,
					5.240154929535449
				],
				[
					1.9407981220501418,
					5.628314553945461
				],
				[
					2.3289577464602376,
					5.822394366150508
				],
				[
					2.5230375586652847,
					5.822394366150508
				],
				[
					2.7171173708703327,
					6.21055399056052
				],
				[
					2.7171173708703327,
					6.404633802765567
				],
				[
					2.5230375586652847,
					6.792793427175579
				],
				[
					1.9407981220501418,
					7.180953051585591
				],
				[
					1.552638497640214,
					7.569112675995602
				],
				[
					0.5822394366151432,
					7.763192488200651
				],
				[
					0,
					7.957272300405613
				],
				[
					-0.5822394366149755,
					8.151352112610661
				],
				[
					-0.9703990610250709,
					8.345431924815708
				],
				[
					-1.5526384976400462,
					8.345431924815708
				],
				[
					-1.746718309845094,
					8.345431924815708
				],
				[
					-2.1348779342550217,
					8.345431924815708
				],
				[
					-2.3289577464600693,
					8.345431924815708
				],
				[
					-2.5230375586651173,
					8.151352112610661
				],
				[
					-3.1052769952800925,
					7.957272300405613
				],
				[
					-3.2993568074851405,
					7.763192488200651
				],
				[
					-3.493436619690188,
					7.763192488200651
				],
				[
					-3.493436619690188,
					7.763192488200651
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 366,
			"versionNonce": 74063051,
			"isDeleted": false,
			"id": "9-ZWMjKQ_PBt4w5Vyo6yn",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1313.904314012259,
			"y": 813.999082645199,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0.19407981220504775,
			"height": 5.24015492953545,
			"seed": 649765253,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.3881596244100955
				],
				[
					-0.19407981220504775,
					0.9703990610250709
				],
				[
					-0.19407981220504775,
					1.5526384976401302
				],
				[
					-0.19407981220504775,
					2.1348779342551896
				],
				[
					-0.19407981220504775,
					2.3289577464602376
				],
				[
					-0.19407981220504775,
					2.9111971830752124
				],
				[
					-0.19407981220504775,
					3.493436619690356
				],
				[
					-0.19407981220504775,
					3.881596244100368
				],
				[
					-0.19407981220504775,
					4.269755868510379
				],
				[
					-0.19407981220504775,
					4.657915492920391
				],
				[
					-0.19407981220504775,
					4.851995305125438
				],
				[
					-0.19407981220504775,
					5.046075117330402
				],
				[
					-0.19407981220504775,
					5.24015492953545
				],
				[
					-0.19407981220504775,
					5.24015492953545
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 367,
			"versionNonce": 1684744549,
			"isDeleted": false,
			"id": "wt_yudB28j79zy3FECoyF",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1323.0260651858946,
			"y": 808.5648479034585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 2.9111971830752124,
			"height": 9.315830985840782,
			"seed": 1795454853,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.38815962441001156
				],
				[
					0,
					1.1644788732301188
				],
				[
					-0.19407981220487988,
					1.746718309845178
				],
				[
					-0.3881596244099276,
					2.9111971830752967
				],
				[
					-0.9703990610250707,
					4.075676056305332
				],
				[
					-1.552638497640046,
					5.24015492953545
				],
				[
					-1.9407981220501413,
					6.016474178355473
				],
				[
					-2.1348779342550217,
					6.986873239380544
				],
				[
					-2.523037558665117,
					7.763192488200651
				],
				[
					-2.717117370870165,
					8.345431924815626
				],
				[
					-2.9111971830752124,
					8.92767136143077
				],
				[
					-2.9111971830752124,
					9.315830985840782
				],
				[
					-2.9111971830752124,
					9.121751173635733
				],
				[
					-2.9111971830752124,
					8.733591549225721
				],
				[
					-2.9111971830752124,
					8.733591549225721
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 379,
			"versionNonce": 1245858667,
			"isDeleted": false,
			"id": "VOkKQw6zrYNfyWmaTFBwZ",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1318.9503891295894,
			"y": 809.1470873400737,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 6.016474178355305,
			"height": 7.957272300405615,
			"seed": 631788773,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.19407981220504775
				],
				[
					0.38815962440992763,
					0.7763192488200231
				],
				[
					0.9703990610250709,
					1.1644788732301188
				],
				[
					1.164478873229951,
					1.746718309845094
				],
				[
					1.9407981220501418,
					2.523037558665201
				],
				[
					2.1348779342550217,
					2.9111971830752124
				],
				[
					2.3289577464600693,
					3.493436619690272
				],
				[
					2.7171173708701652,
					4.075676056305332
				],
				[
					2.9111971830752124,
					4.269755868510379
				],
				[
					3.1052769952800925,
					4.657915492920391
				],
				[
					3.2993568074851405,
					5.24015492953545
				],
				[
					3.2993568074851405,
					5.434234741740413
				],
				[
					3.493436619690188,
					5.822394366150425
				],
				[
					3.6875164318952356,
					6.210553990560521
				],
				[
					3.6875164318952356,
					6.404633802765485
				],
				[
					3.8815962441002836,
					6.598713614970532
				],
				[
					4.075676056305164,
					6.986873239380544
				],
				[
					4.075676056305164,
					7.180953051585592
				],
				[
					4.269755868510211,
					7.375032863790556
				],
				[
					4.463835680715259,
					7.375032863790556
				],
				[
					4.657915492920306,
					7.569112675995603
				],
				[
					5.0460751173302345,
					7.569112675995603
				],
				[
					5.240154929535282,
					7.763192488200567
				],
				[
					5.4342347417403305,
					7.763192488200567
				],
				[
					5.628314553945378,
					7.957272300405615
				],
				[
					6.016474178355305,
					7.957272300405615
				],
				[
					6.016474178355305,
					7.957272300405615
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 364,
			"versionNonce": 711636165,
			"isDeleted": false,
			"id": "_HsSFXyAhvco0s23j9zLb",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1329.8188586130702,
			"y": 812.6405239597639,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 9.315830985840613,
			"height": 0.5822394366150594,
			"seed": 1195058885,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.38815962440992763,
					0
				],
				[
					0.9703990610250709,
					0
				],
				[
					1.746718309845094,
					-0.19407981220496384
				],
				[
					2.5230375586651173,
					-0.3881596244100116
				],
				[
					3.493436619690188,
					-0.3881596244100116
				],
				[
					4.851995305125354,
					-0.5822394366150594
				],
				[
					5.240154929535282,
					-0.5822394366150594
				],
				[
					6.210553990560353,
					-0.5822394366150594
				],
				[
					7.56911267599552,
					-0.5822394366150594
				],
				[
					8.53951173702059,
					-0.5822394366150594
				],
				[
					9.315830985840613,
					-0.5822394366150594
				],
				[
					9.315830985840613,
					-0.5822394366150594
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 362,
			"versionNonce": 240887307,
			"isDeleted": false,
			"id": "msTsyv5IrCZ667eDEwxx6",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1335.6412529792206,
			"y": 808.9530075278685,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0,
			"height": 5.4342347417404975,
			"seed": 136280581,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.5822394366150594
				],
				[
					0,
					1.552638497640214
				],
				[
					0,
					2.5230375586652847
				],
				[
					0,
					3.299356807485308
				],
				[
					0,
					3.881596244100368
				],
				[
					0,
					4.657915492920391
				],
				[
					0,
					4.851995305125438
				],
				[
					0,
					5.24015492953545
				],
				[
					0,
					5.4342347417404975
				],
				[
					0,
					5.4342347417404975
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 386,
			"versionNonce": 1394725925,
			"isDeleted": false,
			"id": "r1JqLNJT9LpASQSnTGUk9",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1351.2387886573101,
			"y": 808.0720739099836,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.896667713275449,
			"height": 8.74333488520159,
			"seed": 1043872389,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726446,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.20333336942333766,
					0
				],
				[
					-0.4066667388466753,
					0
				],
				[
					-1.6266669553863655,
					0
				],
				[
					-2.2366670636562107,
					0
				],
				[
					-2.846667171926056,
					0
				],
				[
					-3.253333910772731,
					0.20333336942333766
				],
				[
					-3.660000649619239,
					0.4066667388466753
				],
				[
					-4.066667388465746,
					0.8133334776931828
				],
				[
					-4.066667388465746,
					1.4233335859631118
				],
				[
					-4.066667388465746,
					1.830000324809703
				],
				[
					-3.863334019042576,
					2.440000433079548
				],
				[
					-3.253333910772731,
					3.253333910772731
				],
				[
					-2.4400004330795486,
					3.8633340190425756
				],
				[
					-1.8300003248097032,
					4.4733341273124205
				],
				[
					-1.423333585963028,
					5.083334235582351
				],
				[
					-1.0166668471163527,
					5.286667605005603
				],
				[
					-0.8133334776931828,
					5.896667713275449
				],
				[
					-0.6100001082698451,
					6.303334452122124
				],
				[
					-0.6100001082698451,
					6.506667821545379
				],
				[
					-0.6100001082698451,
					6.91333456039197
				],
				[
					-0.6100001082698451,
					7.320001299238561
				],
				[
					-1.0166668471163527,
					7.726668038085151
				],
				[
					-1.2200002165396902,
					7.726668038085151
				],
				[
					-2.033333694232873,
					8.336668146354997
				],
				[
					-2.643333802502718,
					8.336668146354997
				],
				[
					-3.253333910772731,
					8.540001515778334
				],
				[
					-3.660000649619239,
					8.540001515778334
				],
				[
					-4.270000757889084,
					8.74333488520159
				],
				[
					-4.473334127312421,
					8.74333488520159
				],
				[
					-4.880000866159097,
					8.74333488520159
				],
				[
					-5.286667605005604,
					8.74333488520159
				],
				[
					-5.693334343852112,
					8.74333488520159
				],
				[
					-5.896667713275449,
					8.74333488520159
				],
				[
					-5.896667713275449,
					8.74333488520159
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 385,
			"versionNonce": 1202760875,
			"isDeleted": false,
			"id": "Upc4P2oMz7wtVTjAgMQ3m",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1355.508789415199,
			"y": 812.1387412984495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 4.473334127312421,
			"height": 6.710001190968632,
			"seed": 867564549,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20333336942325372
				],
				[
					-0.20333336942333766,
					0.6100001082698451
				],
				[
					-0.6100001082698451,
					1.2200002165396902
				],
				[
					-1.2200002165396902,
					2.033333694232873
				],
				[
					-1.423333585963028,
					2.4400004330794647
				],
				[
					-1.6266669553863655,
					3.2533339107726476
				],
				[
					-1.8300003248095356,
					4.066667388465746
				],
				[
					-2.033333694232873,
					5.490000974428858
				],
				[
					-2.033333694232873,
					6.100001082698704
				],
				[
					-1.6266669553863655,
					6.506667821545295
				],
				[
					-1.423333585963028,
					6.710001190968632
				],
				[
					-1.0166668471163527,
					6.710001190968632
				],
				[
					-0.6100001082698451,
					6.710001190968632
				],
				[
					-0.20333336942333766,
					6.710001190968632
				],
				[
					0.20333336942333766,
					6.710001190968632
				],
				[
					0.8133334776931828,
					6.506667821545295
				],
				[
					1.423333585963028,
					6.100001082698704
				],
				[
					1.8300003248097032,
					5.693334343852112
				],
				[
					2.033333694233041,
					5.286667605005521
				],
				[
					2.4400004330795486,
					4.473334127312421
				],
				[
					2.4400004330795486,
					3.863334019042493
				],
				[
					2.4400004330795486,
					3.456667280195901
				],
				[
					2.2366670636562107,
					3.0500005413493096
				],
				[
					1.8300003248097032,
					2.846667171926056
				],
				[
					1.423333585963028,
					2.643333802502718
				],
				[
					1.0166668471165206,
					2.643333802502718
				],
				[
					0.6100001082700129,
					2.643333802502718
				],
				[
					0,
					2.643333802502718
				],
				[
					-0.6100001082698451,
					2.643333802502718
				],
				[
					-1.0166668471163527,
					2.643333802502718
				],
				[
					-1.0166668471163527,
					2.846667171926056
				],
				[
					-1.0166668471163527,
					3.0500005413493096
				],
				[
					-1.0166668471163527,
					3.0500005413493096
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 388,
			"versionNonce": 1249773445,
			"isDeleted": false,
			"id": "SjGsqxrH7FZ1vo8sSEFig",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1361.8121238673214,
			"y": 809.0887407571,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.896667713275449,
			"height": 10.166668471164533,
			"seed": 954960421,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.6100001082698451,
					0
				],
				[
					1.0166668471163527,
					0
				],
				[
					1.423333585963028,
					0
				],
				[
					2.033333694232873,
					0
				],
				[
					2.643333802502718,
					0
				],
				[
					3.253333910772731,
					0.20333336942325372
				],
				[
					3.660000649619239,
					0.20333336942325372
				],
				[
					4.270000757889084,
					0.4066667388465914
				],
				[
					4.473334127312421,
					0.6100001082698451
				],
				[
					4.676667496735759,
					0.8133334776931828
				],
				[
					4.676667496735759,
					1.0166668471164364
				],
				[
					4.270000757889084,
					2.033333694232873
				],
				[
					3.8633340190424086,
					2.8466671719260557
				],
				[
					3.253333910772731,
					3.253333910772647
				],
				[
					2.643333802502718,
					4.2700007578890835
				],
				[
					1.423333585963028,
					5.286667605005603
				],
				[
					0.6100001082698451,
					6.506667821545294
				],
				[
					0.20333336942333766,
					7.320001299238477
				],
				[
					0,
					7.726668038085068
				],
				[
					-0.20333336942333766,
					8.54000151577825
				],
				[
					-0.20333336942333766,
					8.946668254624841
				],
				[
					-0.20333336942333766,
					9.150001624048096
				],
				[
					-0.4066667388466753,
					9.556668362894689
				],
				[
					-0.4066667388466753,
					9.760001732318024
				],
				[
					-0.4066667388466753,
					9.96333510174128
				],
				[
					-0.20333336942333766,
					10.166668471164533
				],
				[
					0.8133334776931828,
					10.166668471164533
				],
				[
					2.033333694232873,
					10.166668471164533
				],
				[
					2.846667171926056,
					10.166668471164533
				],
				[
					3.253333910772731,
					9.96333510174128
				],
				[
					3.8633340190424086,
					9.760001732318024
				],
				[
					4.473334127312421,
					9.35333499347135
				],
				[
					4.880000866158929,
					8.946668254624841
				],
				[
					5.286667605005604,
					8.54000151577825
				],
				[
					5.490000974428774,
					8.54000151577825
				],
				[
					5.490000974428774,
					8.54000151577825
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 360,
			"versionNonce": 703323979,
			"isDeleted": false,
			"id": "bxMcmmOy-YOoMMjd3TmgG",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1361.2021237590513,
			"y": 813.968741623259,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 4.066667388465914,
			"height": 0,
			"seed": 1095046757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.20333336942333766,
					0
				],
				[
					1.0166668471165206,
					0
				],
				[
					1.8300003248097032,
					0
				],
				[
					2.8466671719262235,
					0
				],
				[
					3.456667280196069,
					0
				],
				[
					3.8633340190427448,
					0
				],
				[
					4.066667388465914,
					0
				],
				[
					4.066667388465914,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 359,
			"versionNonce": 582799077,
			"isDeleted": false,
			"id": "15M7WPFk_zHsm19eTAnhU",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1292.4754448939789,
			"y": 833.6920784573184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 8.13333477693166,
			"height": 0.20333336942325372,
			"seed": 1600474149,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8133334776931828,
					0
				],
				[
					2.033333694232873,
					0.20333336942325372
				],
				[
					3.863334019042576,
					0.20333336942325372
				],
				[
					5.490000974428942,
					0.20333336942325372
				],
				[
					7.523334668661815,
					0.20333336942325372
				],
				[
					8.13333477693166,
					0.20333336942325372
				],
				[
					8.13333477693166,
					0.20333336942325372
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 368,
			"versionNonce": 258457067,
			"isDeleted": false,
			"id": "Z8xqEfFfECVl_BPDPxwap",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1296.1354455435978,
			"y": 828.8120775911594,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0.4066667388466753,
			"height": 7.726668038085152,
			"seed": 1915153029,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.20333336942333763
				],
				[
					0,
					0.6100001082699289
				],
				[
					0,
					1.220000216539774
				],
				[
					0,
					1.830000324809703
				],
				[
					0,
					2.2366670636562103
				],
				[
					0,
					2.8466671719261396
				],
				[
					0,
					3.4566672801959846
				],
				[
					0,
					4.0666673884659135
				],
				[
					0,
					5.08333423558235
				],
				[
					0,
					5.490000974428941
				],
				[
					0.20333336942333766,
					6.100001082698786
				],
				[
					0.20333336942333766,
					6.506667821545378
				],
				[
					0.20333336942333766,
					6.913334560391969
				],
				[
					0.4066667388466753,
					7.523334668661814
				],
				[
					0.4066667388466753,
					7.726668038085152
				],
				[
					0.4066667388466753,
					7.726668038085152
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 383,
			"versionNonce": 1248569925,
			"isDeleted": false,
			"id": "PWQmwjUZrY9DpzHEwRd5I",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1309.2739631842092,
			"y": 828.137581460864,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.375257901966276,
			"height": 11.864545320554292,
			"seed": 1074930501,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.961990161126087,
					0
				],
				[
					-1.6033169352100891,
					0
				],
				[
					-2.5653070963360083,
					0
				],
				[
					-3.2066338704201782,
					0
				],
				[
					-4.489287418588183,
					0.6413267740840022
				],
				[
					-4.8099508056301,
					0.9619901611260033
				],
				[
					-5.451277579714102,
					1.9239803222520906
				],
				[
					-5.771940966756187,
					2.5653070963360927
				],
				[
					-5.771940966756187,
					3.2066338704200947
				],
				[
					-5.451277579714102,
					4.1686240315460985
				],
				[
					-4.489287418588183,
					4.489287418588099
				],
				[
					-3.5272972574620955,
					5.451277579714186
				],
				[
					-2.2446437092940914,
					6.092604353798189
				],
				[
					-0.961990161126087,
					6.733931127882191
				],
				[
					0,
					7.375257901966194
				],
				[
					0.961990161126087,
					8.016584676050195
				],
				[
					1.2826535481680041,
					8.337248063092197
				],
				[
					1.6033169352100891,
					8.657911450134282
				],
				[
					1.6033169352100891,
					8.978574837176282
				],
				[
					1.6033169352100891,
					9.619901611260284
				],
				[
					1.2826535481680041,
					9.940564998302285
				],
				[
					0.961990161126087,
					9.940564998302285
				],
				[
					-0.3206633870419171,
					11.22321854647029
				],
				[
					-1.2826535481680041,
					11.543881933512376
				],
				[
					-1.6033169352100891,
					11.864545320554292
				],
				[
					-1.9239803222520064,
					11.864545320554292
				],
				[
					-2.2446437092940914,
					11.864545320554292
				],
				[
					-2.8859704833780935,
					11.864545320554292
				],
				[
					-3.2066338704201782,
					11.543881933512376
				],
				[
					-3.2066338704201782,
					11.543881933512376
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 395,
			"versionNonce": 590268555,
			"isDeleted": false,
			"id": "P4CnC8qTaOIpj6uVEed8P",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1314.4045773768814,
			"y": 837.4368196850822,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.771940966756188,
			"height": 6.733931127882191,
			"seed": 876639365,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.32066338704191716,
					0
				],
				[
					0.9619901611259194,
					0
				],
				[
					1.6033169352100893,
					0
				],
				[
					1.9239803222520067,
					0
				],
				[
					2.244643709293924,
					0
				],
				[
					2.5653070963360087,
					0.3206633870420011
				],
				[
					2.885970483378094,
					0.6413267740840022
				],
				[
					2.885970483378094,
					1.2826535481680044
				],
				[
					2.885970483378094,
					1.6033169352100056
				],
				[
					2.885970483378094,
					1.9239803222520067
				],
				[
					2.885970483378094,
					2.5653070963360087
				],
				[
					2.5653070963360087,
					2.885970483378094
				],
				[
					1.9239803222520067,
					3.2066338704200947
				],
				[
					1.2826535481680044,
					3.2066338704200947
				],
				[
					0.32066338704191716,
					3.527297257462096
				],
				[
					0,
					3.847960644504097
				],
				[
					-0.320663387042085,
					4.1686240315460985
				],
				[
					-0.9619901611260872,
					4.489287418588099
				],
				[
					-1.2826535481681722,
					4.8099508056301
				],
				[
					-1.6033169352100893,
					5.130614192672102
				],
				[
					-1.9239803222520067,
					5.130614192672102
				],
				[
					-2.2446437092940914,
					5.130614192672102
				],
				[
					-2.5653070963361766,
					5.130614192672102
				],
				[
					-2.885970483378094,
					5.130614192672102
				],
				[
					-2.885970483378094,
					4.8099508056301
				],
				[
					-2.2446437092940914,
					4.489287418588099
				],
				[
					-1.9239803222520067,
					4.1686240315460985
				],
				[
					-1.6033169352100893,
					4.1686240315460985
				],
				[
					-1.2826535481681722,
					4.1686240315460985
				],
				[
					-0.9619901611260872,
					4.1686240315460985
				],
				[
					-0.6413267740840022,
					4.1686240315460985
				],
				[
					-0.320663387042085,
					4.489287418588099
				],
				[
					0,
					4.489287418588099
				],
				[
					0.32066338704191716,
					4.489287418588099
				],
				[
					0.6413267740840022,
					4.8099508056301
				],
				[
					0.9619901611259194,
					5.130614192672102
				],
				[
					1.2826535481680044,
					5.451277579714103
				],
				[
					1.6033169352100893,
					5.451277579714103
				],
				[
					1.9239803222520067,
					6.092604353798105
				],
				[
					1.9239803222520067,
					6.4132677408401895
				],
				[
					2.244643709293924,
					6.733931127882191
				],
				[
					2.5653070963360087,
					6.733931127882191
				],
				[
					2.885970483378094,
					6.733931127882191
				],
				[
					2.885970483378094,
					6.733931127882191
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 368,
			"versionNonce": 40376741,
			"isDeleted": false,
			"id": "-1CgMIwZy-CY_pebxOpN8",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1325.6277959233516,
			"y": 829.09957162199,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.054594514924192,
			"height": 9.940564998302285,
			"seed": 611472133,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.320663387042085,
					0
				],
				[
					-0.9619901611260872,
					0.3206633870420011
				],
				[
					-1.6033169352100893,
					0.6413267740840861
				],
				[
					-1.9239803222521743,
					1.2826535481680883
				],
				[
					-2.5653070963360087,
					1.9239803222520906
				],
				[
					-3.2066338704201787,
					2.885970483378094
				],
				[
					-3.527297257462096,
					3.527297257462096
				],
				[
					-3.847960644504181,
					4.168624031546182
				],
				[
					-4.8099508056301,
					5.130614192672185
				],
				[
					-5.130614192672185,
					6.092604353798189
				],
				[
					-5.4512775797142705,
					6.733931127882191
				],
				[
					-5.771940966756188,
					7.375257901966194
				],
				[
					-6.092604353798105,
					8.016584676050279
				],
				[
					-6.4132677408401895,
					8.657911450134282
				],
				[
					-6.733931127882275,
					9.299238224218284
				],
				[
					-6.733931127882275,
					9.619901611260284
				],
				[
					-7.054594514924192,
					9.940564998302285
				],
				[
					-7.054594514924192,
					9.940564998302285
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 368,
			"versionNonce": 1257996075,
			"isDeleted": false,
			"id": "i8_DsX3Dlu0MoBwOzJUnQ",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1319.5351915695535,
			"y": 829.09957162199,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.771940966756019,
			"height": 9.940564998302285,
			"seed": 1919811205,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.3206633870419171,
					0.3206633870420011
				],
				[
					0.9619901611259192,
					0.9619901611260872
				],
				[
					1.6033169352099212,
					1.9239803222520906
				],
				[
					1.9239803222520064,
					3.2066338704200947
				],
				[
					2.5653070963360083,
					4.168624031546182
				],
				[
					2.8859704833779256,
					4.489287418588183
				],
				[
					3.206633870420011,
					5.451277579714186
				],
				[
					3.206633870420011,
					5.771940966756188
				],
				[
					3.5272972574620955,
					6.733931127882191
				],
				[
					3.847960644504013,
					7.375257901966194
				],
				[
					4.16862403154593,
					8.016584676050279
				],
				[
					4.489287418588015,
					8.657911450134282
				],
				[
					4.8099508056301,
					9.299238224218284
				],
				[
					5.130614192672017,
					9.619901611260284
				],
				[
					5.451277579714102,
					9.619901611260284
				],
				[
					5.451277579714102,
					9.940564998302285
				],
				[
					5.771940966756019,
					9.940564998302285
				],
				[
					5.771940966756019,
					9.940564998302285
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 365,
			"versionNonce": 333421829,
			"isDeleted": false,
			"id": "uS2qXGvjdv65_bRJFvGpL",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1332.3617270512339,
			"y": 834.8715125887462,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 7.375257901966276,
			"height": 0,
			"seed": 1852893701,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.320663387042085,
					0
				],
				[
					0.9619901611260872,
					0
				],
				[
					1.9239803222521743,
					0
				],
				[
					2.5653070963361766,
					0
				],
				[
					2.885970483378094,
					0
				],
				[
					3.527297257462096,
					0
				],
				[
					4.1686240315460985,
					0
				],
				[
					4.809950805630268,
					0
				],
				[
					5.4512775797142705,
					0
				],
				[
					6.092604353798273,
					0
				],
				[
					6.4132677408401895,
					0
				],
				[
					6.733931127882275,
					0
				],
				[
					7.054594514924192,
					0
				],
				[
					7.375257901966276,
					0
				],
				[
					7.375257901966276,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 363,
			"versionNonce": 1362649547,
			"isDeleted": false,
			"id": "P8tGt1nMr2Aqhf3MPeqiQ",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1335.8890243086958,
			"y": 831.3442153312842,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0,
			"height": 8.33724806309228,
			"seed": 235763557,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.6413267740840022
				],
				[
					0,
					1.6033169352100056
				],
				[
					0,
					2.2446437092940914
				],
				[
					0,
					2.5653070963360927
				],
				[
					0,
					3.847960644504097
				],
				[
					0,
					4.8099508056301
				],
				[
					0,
					6.092604353798189
				],
				[
					0,
					7.054594514924192
				],
				[
					0,
					7.375257901966194
				],
				[
					0,
					7.695921289008194
				],
				[
					0,
					8.016584676050195
				],
				[
					0,
					8.33724806309228
				],
				[
					0,
					8.33724806309228
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 395,
			"versionNonce": 1179628645,
			"isDeleted": false,
			"id": "eBVn-l2uYwV-EY0GFDH1u",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1348.7155597903761,
			"y": 828.137581460864,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 5.771940966756188,
			"height": 14.429852416890386,
			"seed": 383137227,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.3206633870419172,
					0
				],
				[
					-0.6413267740840023,
					0
				],
				[
					-0.9619901611259195,
					0
				],
				[
					-1.9239803222520069,
					0
				],
				[
					-2.565307096336009,
					0
				],
				[
					-3.5272972574620964,
					0.3206633870420011
				],
				[
					-4.1686240315460985,
					0.6413267740840022
				],
				[
					-4.489287418588016,
					0.9619901611260033
				],
				[
					-4.809950805630101,
					1.6033169352100893
				],
				[
					-4.809950805630101,
					2.2446437092940914
				],
				[
					-4.809950805630101,
					2.885970483378094
				],
				[
					-4.489287418588016,
					3.527297257462096
				],
				[
					-4.1686240315460985,
					3.847960644504097
				],
				[
					-3.8479606445040138,
					4.489287418588099
				],
				[
					-3.2066338704200117,
					5.130614192672185
				],
				[
					-2.8859704833780944,
					5.451277579714186
				],
				[
					-2.565307096336009,
					6.092604353798189
				],
				[
					-2.244643709294092,
					6.733931127882191
				],
				[
					-1.9239803222520069,
					7.375257901966194
				],
				[
					-1.6033169352100896,
					8.016584676050195
				],
				[
					-1.2826535481680046,
					8.657911450134282
				],
				[
					-0.6413267740840023,
					9.299238224218284
				],
				[
					-0.6413267740840023,
					9.619901611260284
				],
				[
					-0.3206633870419172,
					9.940564998302285
				],
				[
					0,
					10.261228385344287
				],
				[
					0.3206633870420851,
					10.902555159428289
				],
				[
					0.3206633870420851,
					11.22321854647029
				],
				[
					0.3206633870420851,
					11.543881933512376
				],
				[
					0.3206633870420851,
					12.185208707596377
				],
				[
					0.3206633870420851,
					12.826535481680379
				],
				[
					-0.3206633870419172,
					13.14719886872238
				],
				[
					-0.9619901611259195,
					13.467862255764382
				],
				[
					-1.2826535481680046,
					14.109189029848384
				],
				[
					-1.6033169352100896,
					14.109189029848384
				],
				[
					-1.9239803222520069,
					14.429852416890386
				],
				[
					-2.565307096336009,
					14.429852416890386
				],
				[
					-2.8859704833780944,
					14.429852416890386
				],
				[
					-3.5272972574620964,
					14.429852416890386
				],
				[
					-3.8479606445040138,
					14.429852416890386
				],
				[
					-4.1686240315460985,
					14.429852416890386
				],
				[
					-4.489287418588016,
					14.429852416890386
				],
				[
					-4.809950805630101,
					14.429852416890386
				],
				[
					-5.130614192672185,
					14.109189029848384
				],
				[
					-5.451277579714103,
					13.467862255764382
				],
				[
					-5.451277579714103,
					13.467862255764382
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 387,
			"versionNonce": 1325396075,
			"isDeleted": false,
			"id": "2a534W7wcDmr7g4P9LGPe",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1350.3188767255863,
			"y": 836.4748295239561,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 3.8479606445040133,
			"height": 13.467862255764382,
			"seed": 1309190853,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.320663387042085
				],
				[
					0.3206633870419172,
					0.6413267740840861
				],
				[
					0.3206633870419172,
					0.9619901611260872
				],
				[
					0.6413267740840023,
					0.9619901611260872
				],
				[
					0.9619901611260874,
					0.9619901611260872
				],
				[
					1.2826535481680046,
					1.2826535481680883
				],
				[
					1.6033169352100896,
					1.6033169352100893
				],
				[
					1.9239803222520067,
					1.9239803222520906
				],
				[
					2.244643709294092,
					1.9239803222520906
				],
				[
					2.8859704833780944,
					1.6033169352100893
				],
				[
					3.206633870420179,
					1.2826535481680883
				],
				[
					3.206633870420179,
					0.9619901611260872
				],
				[
					3.5272972574620964,
					0.6413267740840861
				],
				[
					3.8479606445040133,
					0
				],
				[
					3.8479606445040133,
					-1.2826535481680044
				],
				[
					3.8479606445040133,
					-1.6033169352100056
				],
				[
					3.8479606445040133,
					-1.9239803222520067
				],
				[
					3.8479606445040133,
					-1.6033169352100056
				],
				[
					3.8479606445040133,
					-1.2826535481680044
				],
				[
					3.5272972574620964,
					-0.3206633870420011
				],
				[
					3.5272972574620964,
					0.6413267740840861
				],
				[
					3.206633870420179,
					1.2826535481680883
				],
				[
					3.206633870420179,
					2.2446437092940914
				],
				[
					2.8859704833780944,
					3.527297257462096
				],
				[
					2.8859704833780944,
					3.847960644504181
				],
				[
					2.8859704833780944,
					5.130614192672185
				],
				[
					2.8859704833780944,
					5.771940966756188
				],
				[
					2.8859704833780944,
					6.4132677408401895
				],
				[
					2.8859704833780944,
					7.054594514924192
				],
				[
					2.8859704833780944,
					7.375257901966276
				],
				[
					2.8859704833780944,
					8.33724806309228
				],
				[
					2.8859704833780944,
					8.657911450134282
				],
				[
					2.8859704833780944,
					9.299238224218284
				],
				[
					2.8859704833780944,
					9.619901611260284
				],
				[
					2.8859704833780944,
					10.26122838534437
				],
				[
					2.8859704833780944,
					10.902555159428372
				],
				[
					2.8859704833780944,
					11.223218546470374
				],
				[
					2.8859704833780944,
					11.543881933512376
				],
				[
					2.8859704833780944,
					11.543881933512376
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 411,
			"versionNonce": 361095109,
			"isDeleted": false,
			"id": "yMTfxHZi4ikVTPCTLS40g",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1361.2214318850145,
			"y": 828.778908234948,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 9.299238224218284,
			"height": 17.31582290026848,
			"seed": 961151269,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.32066338704200115
				],
				[
					0,
					0.6413267740840023
				],
				[
					0,
					1.2826535481680885
				],
				[
					0,
					1.9239803222520908
				],
				[
					0.3206633870420851,
					2.5653070963360927
				],
				[
					0.6413267740841702,
					2.8859704833780944
				],
				[
					0.9619901611260873,
					3.5272972574620964
				],
				[
					1.2826535481681725,
					3.8479606445040972
				],
				[
					1.6033169352100896,
					4.1686240315460985
				],
				[
					1.9239803222521745,
					4.1686240315460985
				],
				[
					2.565307096336177,
					4.1686240315460985
				],
				[
					2.885970483378262,
					4.1686240315460985
				],
				[
					3.206633870420179,
					4.1686240315460985
				],
				[
					3.5272972574620964,
					3.8479606445040972
				],
				[
					3.8479606445041816,
					3.5272972574620964
				],
				[
					4.168624031546266,
					3.206633870420095
				],
				[
					4.489287418588184,
					2.8859704833780944
				],
				[
					5.130614192672185,
					2.244643709294092
				],
				[
					5.451277579714271,
					1.9239803222520908
				],
				[
					5.451277579714271,
					1.6033169352100896
				],
				[
					5.451277579714271,
					1.9239803222520908
				],
				[
					5.451277579714271,
					2.5653070963360927
				],
				[
					5.451277579714271,
					3.206633870420095
				],
				[
					5.130614192672185,
					4.1686240315460985
				],
				[
					5.130614192672185,
					5.130614192672185
				],
				[
					5.130614192672185,
					7.054594514924193
				],
				[
					4.809950805630269,
					9.299238224218286
				],
				[
					4.489287418588184,
					11.543881933512377
				],
				[
					4.168624031546266,
					12.82653548168038
				],
				[
					3.5272972574620964,
					14.429852416890471
				],
				[
					3.206633870420179,
					15.712505965058476
				],
				[
					2.885970483378262,
					16.35383273914248
				],
				[
					2.244643709294092,
					16.67449612618448
				],
				[
					1.6033169352100896,
					16.99515951322648
				],
				[
					1.2826535481681725,
					17.31582290026848
				],
				[
					0.6413267740841702,
					17.31582290026848
				],
				[
					0.3206633870420851,
					17.31582290026848
				],
				[
					0,
					16.67449612618448
				],
				[
					-0.3206633870419172,
					15.712505965058476
				],
				[
					-0.9619901611259195,
					15.071179190974473
				],
				[
					-1.2826535481680046,
					14.429852416890471
				],
				[
					-1.2826535481680046,
					14.109189029848386
				],
				[
					-1.2826535481680046,
					13.788525642806384
				],
				[
					-0.9619901611259195,
					13.467862255764384
				],
				[
					-0.6413267740838344,
					13.147198868722382
				],
				[
					0,
					12.82653548168038
				],
				[
					0.6413267740841702,
					12.82653548168038
				],
				[
					0.9619901611260873,
					12.82653548168038
				],
				[
					2.244643709294092,
					13.147198868722382
				],
				[
					2.885970483378262,
					13.467862255764384
				],
				[
					3.5272972574620964,
					13.788525642806384
				],
				[
					3.8479606445041816,
					13.788525642806384
				],
				[
					4.489287418588184,
					14.109189029848386
				],
				[
					5.451277579714271,
					14.429852416890471
				],
				[
					5.771940966756189,
					14.750515803932387
				],
				[
					6.092604353798273,
					14.750515803932387
				],
				[
					6.7339311278822755,
					14.750515803932387
				],
				[
					7.054594514924193,
					14.750515803932387
				],
				[
					7.695921289008363,
					14.750515803932387
				],
				[
					7.695921289008363,
					14.429852416890471
				],
				[
					8.016584676050279,
					14.429852416890471
				],
				[
					8.016584676050279,
					14.429852416890471
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "rectangle",
			"version": 1505,
			"versionNonce": 1444719371,
			"isDeleted": false,
			"id": "QH_8bU4lZchwCsZOrzyCb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 639.2149258205399,
			"y": 944.3858141724478,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 570.4228202809587,
			"height": 339.1627191094773,
			"seed": 11142629,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "2yCi7qKzOZaXKm_t6nJzt",
					"type": "arrow"
				},
				{
					"id": "NTE9jU8a1FXfUcf0W_smS",
					"type": "arrow"
				},
				{
					"id": "gikkH85SeWSmp-qFanqqT",
					"type": "arrow"
				}
			],
			"updated": 1702760726447,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 907,
			"versionNonce": 664772389,
			"isDeleted": false,
			"id": "7QnKs3Y6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 876.1903203386153,
			"y": 951.0516309932187,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 151.77606201171875,
			"height": 45,
			"seed": 60424517,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Rotating",
			"rawText": "Rotating",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Rotating",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "freedraw",
			"version": 761,
			"versionNonce": 1527321003,
			"isDeleted": false,
			"id": "yveGiRY5vNSm4KNo7q8yG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 711.6773867664558,
			"y": 1043.4613582925735,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 85.667699354148,
			"height": 2.4063960492738232,
			"seed": 2024027141,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4812792098546197,
					0
				],
				[
					0.9625584197094668,
					0
				],
				[
					2.4063960492737806,
					0
				],
				[
					3.8502336788380944,
					0
				],
				[
					5.294071308402408,
					0
				],
				[
					7.700467357676189,
					0
				],
				[
					9.144304987240503,
					0
				],
				[
					11.550701036514283,
					0
				],
				[
					13.475817875933444,
					0
				],
				[
					14.919655505497758,
					0
				],
				[
					16.363493135061844,
					0
				],
				[
					18.288609974481005,
					0
				],
				[
					19.73244760404532,
					0
				],
				[
					21.657564443464253,
					0.4812792098547618
				],
				[
					23.582681282883414,
					0.4812792098547618
				],
				[
					25.026518912447727,
					0.4812792098547618
				],
				[
					26.95163575186666,
					0.4812792098547618
				],
				[
					28.395473381430975,
					0.4812792098547618
				],
				[
					29.83931101099529,
					0.4812792098547618
				],
				[
					31.283148640559602,
					0.4812792098547618
				],
				[
					32.726986270123916,
					0
				],
				[
					35.1333823193977,
					0
				],
				[
					37.05849915881686,
					0
				],
				[
					39.46489520809064,
					-0.9625584197095378
				],
				[
					41.87129125736442,
					-0.9625584197095378
				],
				[
					44.75896651649305,
					-1.4438376295642996
				],
				[
					46.68408335591198,
					-1.4438376295642996
				],
				[
					49.57175861504061,
					-1.9251168394190614
				],
				[
					51.49687545445977,
					-1.9251168394190614
				],
				[
					53.4219922938787,
					-1.9251168394190614
				],
				[
					54.384550713588396,
					-1.9251168394190614
				],
				[
					55.34710913329786,
					-1.9251168394190614
				],
				[
					56.79094676286218,
					-1.9251168394190614
				],
				[
					58.71606360228111,
					-1.9251168394190614
				],
				[
					59.67862202199058,
					-1.9251168394190614
				],
				[
					60.64118044170027,
					-1.9251168394190614
				],
				[
					62.085018071264585,
					-1.9251168394190614
				],
				[
					63.04757649097405,
					-1.9251168394190614
				],
				[
					64.97269333039321,
					-1.9251168394190614
				],
				[
					65.93525175010268,
					-1.9251168394190614
				],
				[
					67.379089379667,
					-1.9251168394190614
				],
				[
					68.34164779937646,
					-1.9251168394190614
				],
				[
					69.30420621908593,
					-1.9251168394190614
				],
				[
					70.2667646387954,
					-1.9251168394190614
				],
				[
					70.74804384865024,
					-1.9251168394190614
				],
				[
					71.22932305850509,
					-1.4438376295642996
				],
				[
					72.19188147821455,
					-1.4438376295642996
				],
				[
					73.15443989792402,
					-1.4438376295642996
				],
				[
					73.63571910777887,
					-1.4438376295642996
				],
				[
					74.11699831763372,
					-0.9625584197095378
				],
				[
					75.07955673734318,
					-0.9625584197095378
				],
				[
					76.04211515705265,
					-0.4812792098547618
				],
				[
					76.5233943669075,
					-0.4812792098547618
				],
				[
					77.96723199647181,
					-0.4812792098547618
				],
				[
					78.92979041618128,
					-0.4812792098547618
				],
				[
					79.89234883589074,
					-0.4812792098547618
				],
				[
					80.37362804574559,
					-0.4812792098547618
				],
				[
					81.8174656753099,
					-0.4812792098547618
				],
				[
					82.29874488516452,
					-0.4812792098547618
				],
				[
					83.26130330487422,
					-0.4812792098547618
				],
				[
					83.74258251472884,
					-0.4812792098547618
				],
				[
					84.70514093443853,
					-0.4812792098547618
				],
				[
					85.18642014429315,
					-0.4812792098547618
				],
				[
					85.667699354148,
					-0.4812792098547618
				],
				[
					85.667699354148,
					-0.4812792098547618
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 736,
			"versionNonce": 51016325,
			"isDeleted": false,
			"id": "aA0l72uzNDiZnpEdcvDsc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 797.8263653304582,
			"y": 1027.0978651575115,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 20.695006023755013,
			"height": 27.914194171576312,
			"seed": 1953065829,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.481279209854776
				],
				[
					0,
					0.9625584197095378
				],
				[
					0,
					1.9251168394190614
				],
				[
					0,
					2.887675259128585
				],
				[
					0.48127920985484707,
					3.368954468983361
				],
				[
					1.4438376295643138,
					4.8127920985476464
				],
				[
					2.406396049274008,
					6.256629728111932
				],
				[
					3.8502336788380944,
					7.7004673576762315
				],
				[
					4.8127920985477886,
					9.144304987240517
				],
				[
					5.294071308402408,
					9.625584197095293
				],
				[
					6.256629728112102,
					11.069421826659578
				],
				[
					7.700467357676416,
					12.031980246369102
				],
				[
					9.62558419709535,
					13.475817875933402
				],
				[
					10.588142616805044,
					13.957097085788163
				],
				[
					11.55070103651451,
					14.919655505497687
				],
				[
					12.994538666078597,
					15.882213925207225
				],
				[
					13.957097085788291,
					16.84477234491675
				],
				[
					15.400934715352605,
					18.288609974481034
				],
				[
					16.363493135062072,
					19.25116839419057
				],
				[
					16.363493135062072,
					20.213726813900095
				],
				[
					16.84477234491692,
					20.695006023754857
				],
				[
					16.84477234491692,
					21.17628523360962
				],
				[
					15.882213925207225,
					21.65756444346438
				],
				[
					13.957097085788291,
					22.62012286317392
				],
				[
					11.069421826659664,
					23.10140207302868
				],
				[
					8.181746567531036,
					23.582681282883442
				],
				[
					4.8127920985477886,
					24.545239702592966
				],
				[
					2.8876752591286277,
					25.02651891244774
				],
				[
					0.48127920985484707,
					25.507798122302503
				],
				[
					-0.4812792098546197,
					25.507798122302503
				],
				[
					-1.9251168394189335,
					25.989077332157265
				],
				[
					-2.4063960492737806,
					25.989077332157265
				],
				[
					-2.8876752591284003,
					26.470356542012027
				],
				[
					-3.3689544689832474,
					26.470356542012027
				],
				[
					-3.3689544689832474,
					26.95163575186679
				],
				[
					-3.8502336788380944,
					26.95163575186679
				],
				[
					-3.8502336788380944,
					27.43291496172155
				],
				[
					-3.8502336788380944,
					27.914194171576312
				],
				[
					-3.3689544689832474,
					27.914194171576312
				],
				[
					-3.3689544689832474,
					27.914194171576312
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 729,
			"versionNonce": 1592763467,
			"isDeleted": false,
			"id": "OYPmFZUf5fsinC8-TCloh",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 652.5062851984131,
			"y": 1070.2142682482868,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 4.541866687541415,
			"height": 23.14189216985367,
			"seed": 1699788485,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.21627936607340104
				],
				[
					-0.21627936607342235,
					0.648838098220196
				],
				[
					-0.6488380982201534,
					1.081396830366998
				],
				[
					-0.8651174642935757,
					1.730234928587194
				],
				[
					-1.2976761964404204,
					2.595352392880784
				],
				[
					-1.7302349285871514,
					3.893028589321183
				],
				[
					-2.162793660733996,
					5.190704785761575
				],
				[
					-2.3790730268074185,
					5.839542883981771
				],
				[
					-2.595352392880841,
					6.920939714348762
				],
				[
					-3.027911125027572,
					8.218615910789154
				],
				[
					-3.027911125027572,
					9.300012741156152
				],
				[
					-3.2441904911009942,
					10.597688937596544
				],
				[
					-3.2441904911009942,
					11.462806401890141
				],
				[
					-3.2441904911009942,
					12.544203232257132
				],
				[
					-3.4604698571744166,
					13.841879428697524
				],
				[
					-3.4604698571744166,
					15.139555625137916
				],
				[
					-3.4604698571744166,
					16.004673089431513
				],
				[
					-3.4604698571744166,
					16.86979055372511
				],
				[
					-3.2441904911009942,
					17.734908018018707
				],
				[
					-3.027911125027572,
					18.600025482312297
				],
				[
					-2.8116317589541495,
					19.248863580532493
				],
				[
					-2.3790730268074185,
					19.89770167875269
				],
				[
					-2.162793660733996,
					20.33026041089949
				],
				[
					-1.7302349285871514,
					20.762819143046293
				],
				[
					-1.2976761964404204,
					21.41165724126649
				],
				[
					-1.081396830366998,
					21.844215973413277
				],
				[
					-0.6488380982201534,
					22.493054071633473
				],
				[
					0,
					22.925612803780275
				],
				[
					0.21627936607342235,
					22.925612803780275
				],
				[
					0.4325587321468447,
					23.14189216985367
				],
				[
					0.6488380982201534,
					23.14189216985367
				],
				[
					0.8651174642935757,
					23.14189216985367
				],
				[
					1.081396830366998,
					23.14189216985367
				],
				[
					1.081396830366998,
					22.925612803780275
				],
				[
					1.081396830366998,
					22.70933343770688
				],
				[
					1.081396830366998,
					22.70933343770688
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 708,
			"versionNonce": 75749861,
			"isDeleted": false,
			"id": "SwIzz_6o15iPzREH_9XiU",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 661.590018573496,
			"y": 1075.4049730340485,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.406984151835104,
			"height": 12.327923866183731,
			"seed": 100111909,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.21627936607340104
				],
				[
					-0.4325587321468447,
					0.43255873214679497
				],
				[
					-1.0813968303671118,
					1.297676196440392
				],
				[
					-2.162793660733996,
					2.162793660733989
				],
				[
					-3.0279111250276856,
					3.460469857174381
				],
				[
					-4.325587321467992,
					6.48838098220196
				],
				[
					-4.974425419688259,
					8.218615910789154
				],
				[
					-5.190704785761682,
					9.300012741156145
				],
				[
					-5.406984151835104,
					10.381409571523143
				],
				[
					-5.406984151835104,
					11.03024766974334
				],
				[
					-5.406984151835104,
					11.895365134036936
				],
				[
					-5.406984151835104,
					12.11164450011033
				],
				[
					-5.406984151835104,
					11.679085767963535
				],
				[
					-5.406984151835104,
					11.462806401890134
				],
				[
					-5.406984151835104,
					11.462806401890134
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 716,
			"versionNonce": 1504371435,
			"isDeleted": false,
			"id": "e5TxtcYpjBEilxivDN7pf",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 656.8318725198811,
			"y": 1074.9724143019016,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.811631758954263,
			"height": 12.544203232257132,
			"seed": 1632340357,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.21627936607340104
				],
				[
					0,
					0.43255873214680207
				],
				[
					0,
					1.081396830366998
				],
				[
					0,
					1.513955562513793
				],
				[
					0.21627936607342235,
					2.37907302680739
				],
				[
					0.4325587321468447,
					3.893028589321183
				],
				[
					1.0813968303668844,
					5.190704785761575
				],
				[
					1.0813968303668844,
					6.704660348275368
				],
				[
					1.513955562513729,
					7.786057178642359
				],
				[
					1.513955562513729,
					8.651174642935956
				],
				[
					1.513955562513729,
					9.083733375082751
				],
				[
					1.7302349285871514,
					9.516292107229553
				],
				[
					1.9465142946605738,
					9.948850839376348
				],
				[
					1.9465142946605738,
					10.16513020544975
				],
				[
					2.162793660733996,
					10.597688937596544
				],
				[
					2.162793660733996,
					11.030247669743346
				],
				[
					2.162793660733996,
					11.462806401890141
				],
				[
					2.3790730268074185,
					11.895365134036936
				],
				[
					2.3790730268074185,
					12.327923866183738
				],
				[
					2.3790730268074185,
					12.544203232257132
				],
				[
					2.595352392880841,
					12.327923866183738
				],
				[
					2.811631758954263,
					12.111644500110337
				],
				[
					2.811631758954263,
					12.111644500110337
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 702,
			"versionNonce": 353981765,
			"isDeleted": false,
			"id": "SWGQXvzidaonz1yrHQFTl",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 665.2667677967434,
			"y": 1084.704985775205,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 1.9465142946605738,
			"height": 4.325587321467985,
			"seed": 1217007845,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.43255873214680207
				],
				[
					-0.4325587321468447,
					1.513955562513793
				],
				[
					-0.8651174642936894,
					2.162793660733989
				],
				[
					-1.2976761964403067,
					3.027911125027586
				],
				[
					-1.7302349285871514,
					3.893028589321183
				],
				[
					-1.9465142946605738,
					4.109307955394577
				],
				[
					-1.9465142946605738,
					4.325587321467985
				],
				[
					-1.513955562513729,
					4.109307955394577
				],
				[
					-1.513955562513729,
					4.109307955394577
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 775,
			"versionNonce": 1673874827,
			"isDeleted": false,
			"id": "yc4n0HRCGBHA0lS8-rRq8",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 671.7551487789451,
			"y": 1072.8096206411678,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 9.300012741156252,
			"height": 24.43956836629406,
			"seed": 155233349,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.43255873214680207
				],
				[
					0,
					1.081396830366998
				],
				[
					0,
					1.730234928587194
				],
				[
					0,
					3.893028589321183
				],
				[
					0,
					4.541866687541379
				],
				[
					0.4325587321468447,
					6.055822250055172
				],
				[
					0.865117464293462,
					7.137219080422163
				],
				[
					1.7302349285871514,
					8.434895276862555
				],
				[
					2.3790730268074185,
					8.651174642935956
				],
				[
					2.811631758954036,
					8.651174642935956
				],
				[
					3.460469857174303,
					8.00233654471576
				],
				[
					3.8930285893211476,
					7.137219080422163
				],
				[
					4.325587321467992,
					6.055822250055172
				],
				[
					4.541866687541415,
					4.75814605361478
				],
				[
					4.758146053614837,
					3.893028589321183
				],
				[
					4.974425419688032,
					3.027911125027586
				],
				[
					5.190704785761454,
					2.595352392880791
				],
				[
					5.623263517908299,
					1.9465142946605951
				],
				[
					5.839542883981721,
					1.297676196440399
				],
				[
					6.272101616128566,
					0.865117464293597
				],
				[
					6.4883809822019884,
					0.43255873214680207
				],
				[
					6.704660348275411,
					0.21627936607340104
				],
				[
					6.704660348275411,
					0
				],
				[
					6.704660348275411,
					-0.21627936607339393
				],
				[
					6.704660348275411,
					0
				],
				[
					6.272101616128566,
					0.43255873214680207
				],
				[
					6.055822250055144,
					1.513955562513793
				],
				[
					5.839542883981721,
					2.595352392880791
				],
				[
					5.623263517908299,
					3.893028589321183
				],
				[
					5.623263517908299,
					4.974425419688174
				],
				[
					5.623263517908299,
					6.272101616128566
				],
				[
					5.406984151834877,
					7.569777812568965
				],
				[
					5.190704785761454,
					9.516292107229553
				],
				[
					4.974425419688032,
					10.813968303669945
				],
				[
					4.758146053614837,
					12.760482598330533
				],
				[
					4.541866687541415,
					14.490717526917727
				],
				[
					4.325587321467992,
					16.22095245550492
				],
				[
					3.8930285893211476,
					17.734908018018707
				],
				[
					3.460469857174303,
					19.4651429466059
				],
				[
					3.2441904911008805,
					20.33026041089949
				],
				[
					2.811631758954036,
					21.41165724126649
				],
				[
					2.3790730268074185,
					22.27677470556008
				],
				[
					1.9465142946605738,
					22.925612803780275
				],
				[
					1.0813968303668844,
					23.57445090200047
				],
				[
					0.6488380982202671,
					23.79073026807388
				],
				[
					0,
					24.007009634147273
				],
				[
					-0.4325587321468447,
					24.223289000220667
				],
				[
					-1.513955562513729,
					24.223289000220667
				],
				[
					-1.9465142946605738,
					24.223289000220667
				],
				[
					-2.162793660733996,
					24.223289000220667
				],
				[
					-2.3790730268074185,
					23.79073026807388
				],
				[
					-2.595352392880841,
					22.925612803780275
				],
				[
					-2.595352392880841,
					22.27677470556008
				],
				[
					-2.595352392880841,
					21.41165724126649
				],
				[
					-2.595352392880841,
					20.762819143046293
				],
				[
					-2.3790730268074185,
					20.113981044826097
				],
				[
					-1.9465142946605738,
					19.4651429466059
				],
				[
					-1.513955562513729,
					19.248863580532493
				],
				[
					-1.0813968303671118,
					18.816304848385705
				],
				[
					-0.6488380982202671,
					18.16746675016551
				],
				[
					0,
					17.9511873840921
				],
				[
					0.21627936607342235,
					17.9511873840921
				],
				[
					0.865117464293462,
					17.9511873840921
				],
				[
					1.2976761964403067,
					18.383746116238903
				],
				[
					1.7302349285871514,
					18.600025482312297
				],
				[
					1.9465142946605738,
					19.0325842144591
				],
				[
					2.595352392880841,
					19.681422312679295
				],
				[
					2.811631758954036,
					20.113981044826097
				],
				[
					3.2441904911008805,
					20.546539776972885
				],
				[
					3.6767492232477252,
					21.195377875193095
				],
				[
					4.10930795539457,
					21.41165724126649
				],
				[
					4.541866687541415,
					21.84421597341329
				],
				[
					4.758146053614837,
					22.493054071633487
				],
				[
					5.190704785761454,
					22.70933343770688
				],
				[
					5.406984151834877,
					22.70933343770688
				],
				[
					5.623263517908299,
					22.70933343770688
				],
				[
					5.839542883981721,
					22.70933343770688
				],
				[
					6.055822250055144,
					22.70933343770688
				],
				[
					6.055822250055144,
					22.493054071633487
				],
				[
					6.272101616128566,
					22.27677470556008
				],
				[
					6.4883809822019884,
					21.84421597341329
				],
				[
					6.4883809822019884,
					21.41165724126649
				],
				[
					6.4883809822019884,
					21.41165724126649
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 700,
			"versionNonce": 539518117,
			"isDeleted": false,
			"id": "uQryJtbtdX_El9a1ZMM8i",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 685.1644694754957,
			"y": 1084.9212651412781,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.2441904911008805,
			"height": 4.758146053614773,
			"seed": 1665981349,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.21627936607340104
				],
				[
					0,
					0
				],
				[
					-0.6488380982200397,
					1.081396830366998
				],
				[
					-1.513955562513729,
					1.946514294660588
				],
				[
					-2.379073026807191,
					2.811631758954185
				],
				[
					-2.811631758954036,
					3.676749223247782
				],
				[
					-3.2441904911008805,
					4.541866687541372
				],
				[
					-3.2441904911008805,
					4.541866687541372
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 736,
			"versionNonce": 544826411,
			"isDeleted": false,
			"id": "JqlrtiDinV0n_wFoJdAFH",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 689.7063361630369,
			"y": 1073.8910174715347,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 9.948850839376519,
			"height": 16.65351118765171,
			"seed": 1054613253,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.21627936607342235,
					0
				],
				[
					0,
					0
				],
				[
					1.0813968303671118,
					0.21627936607340104
				],
				[
					2.3790730268074185,
					0.43255873214679497
				],
				[
					4.325587321467992,
					0.648838098220196
				],
				[
					5.190704785761682,
					0.648838098220196
				],
				[
					6.055822250055144,
					1.081396830366991
				],
				[
					6.272101616128566,
					1.081396830366991
				],
				[
					6.704660348275411,
					1.297676196440392
				],
				[
					6.920939714348833,
					1.513955562513793
				],
				[
					7.353498446495678,
					1.730234928587187
				],
				[
					7.5697778125691,
					1.946514294660588
				],
				[
					7.786057178642523,
					2.162793660733989
				],
				[
					7.786057178642523,
					2.379073026807383
				],
				[
					7.353498446495678,
					2.811631758954185
				],
				[
					6.920939714348833,
					3.24419049110098
				],
				[
					5.839542883981721,
					4.109307955394577
				],
				[
					4.325587321467992,
					5.406984151834969
				],
				[
					3.244190491101108,
					6.920939714348762
				],
				[
					1.7302349285871514,
					8.86745400900935
				],
				[
					0.8651174642936894,
					9.948850839376348
				],
				[
					0,
					11.24652703581674
				],
				[
					-0.4325587321468447,
					12.327923866183731
				],
				[
					-1.2976761964403067,
					13.40932069655073
				],
				[
					-1.7302349285871514,
					14.490717526917727
				],
				[
					-2.162793660733996,
					14.923276259064515
				],
				[
					-2.162793660733996,
					15.78839372335812
				],
				[
					-2.162793660733996,
					16.220952455504907
				],
				[
					-1.9465142946605738,
					16.65351118765171
				],
				[
					-1.7302349285871514,
					16.65351118765171
				],
				[
					-1.2976761964403067,
					16.65351118765171
				],
				[
					-0.865117464293462,
					16.65351118765171
				],
				[
					0,
					16.65351118765171
				],
				[
					0.4325587321468447,
					16.437231821578315
				],
				[
					1.2976761964405341,
					16.004673089431513
				],
				[
					1.5139555625139565,
					15.78839372335812
				],
				[
					2.162793660733996,
					15.355834991211317
				],
				[
					2.595352392880841,
					15.139555625137923
				],
				[
					3.0279111250276856,
					15.139555625137923
				],
				[
					3.244190491101108,
					14.923276259064515
				],
				[
					3.4604698571745303,
					14.706996892991121
				],
				[
					3.8930285893211476,
					14.706996892991121
				],
				[
					3.8930285893211476,
					14.490717526917727
				],
				[
					4.10930795539457,
					14.490717526917727
				],
				[
					4.10930795539457,
					14.490717526917727
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 701,
			"versionNonce": 1230931973,
			"isDeleted": false,
			"id": "VtbJirczXzToA5FIqFKf3",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 690.1388948951842,
			"y": 1081.028236551957,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 4.758146053614837,
			"height": 0,
			"seed": 577500773,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.21627936607342235,
					0
				],
				[
					0.4325587321468447,
					0
				],
				[
					1.0813968303671118,
					0
				],
				[
					1.9465142946605738,
					0
				],
				[
					2.595352392880841,
					0
				],
				[
					3.6767492232477252,
					0
				],
				[
					4.10930795539457,
					0
				],
				[
					4.325587321467992,
					0
				],
				[
					4.541866687541415,
					0
				],
				[
					4.541866687541415,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 720,
			"versionNonce": 1739695819,
			"isDeleted": false,
			"id": "zBx32Qu8QLaw9P-IH136U",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 700.5203044667071,
			"y": 1072.1607825429478,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.406984151834877,
			"height": 19.4651429466059,
			"seed": 1758060997,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.21627936607342235,
					0
				],
				[
					0.6488380982202671,
					0.43255873214680207
				],
				[
					0.8651174642936894,
					0.648838098220196
				],
				[
					1.7302349285871514,
					1.297676196440392
				],
				[
					2.3790730268074185,
					1.9465142946605951
				],
				[
					3.0279111250276856,
					2.811631758954185
				],
				[
					3.460469857174303,
					3.676749223247782
				],
				[
					4.325587321467992,
					5.839542883981771
				],
				[
					4.325587321467992,
					6.920939714348762
				],
				[
					4.325587321467992,
					8.651174642935956
				],
				[
					4.325587321467992,
					9.516292107229553
				],
				[
					4.10930795539457,
					10.597688937596544
				],
				[
					3.8930285893211476,
					11.679085767963542
				],
				[
					3.460469857174303,
					12.760482598330533
				],
				[
					3.0279111250276856,
					13.62560006262413
				],
				[
					2.811631758954263,
					14.490717526917727
				],
				[
					2.595352392880841,
					15.572114357284718
				],
				[
					2.3790730268074185,
					16.65351118765171
				],
				[
					1.9465142946605738,
					17.734908018018707
				],
				[
					1.513955562513729,
					18.383746116238903
				],
				[
					1.0813968303671118,
					19.0325842144591
				],
				[
					0.8651174642936894,
					19.248863580532493
				],
				[
					0.6488380982202671,
					19.4651429466059
				],
				[
					0.4325587321468447,
					19.4651429466059
				],
				[
					0,
					19.4651429466059
				],
				[
					-0.4325587321468447,
					19.4651429466059
				],
				[
					-0.8651174642936894,
					19.4651429466059
				],
				[
					-1.0813968303668844,
					19.4651429466059
				],
				[
					-1.0813968303668844,
					19.4651429466059
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 726,
			"versionNonce": 1656307557,
			"isDeleted": false,
			"id": "IhzBUfNdE0hOO8w2H7DvX",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 806.2809144765995,
			"y": 1065.2398428285987,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 7.137219080422028,
			"height": 28.548876321688645,
			"seed": 924016933,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.21627936607319498,
					0
				],
				[
					-0.43255873214661733,
					0.21627936607340104
				],
				[
					-1.0813968303668844,
					0.648838098220196
				],
				[
					-1.7302349285871514,
					1.730234928587194
				],
				[
					-2.811631758954036,
					2.595352392880791
				],
				[
					-3.460469857174303,
					3.676749223247782
				],
				[
					-4.325587321467992,
					4.974425419688174
				],
				[
					-4.75814605361461,
					6.055822250055172
				],
				[
					-5.839542883981721,
					7.137219080422163
				],
				[
					-6.488380982201761,
					8.867454009009357
				],
				[
					-6.704660348275183,
					10.16513020544975
				],
				[
					-6.704660348275183,
					11.679085767963542
				],
				[
					-6.704660348275183,
					13.193041330477328
				],
				[
					-6.704660348275183,
					14.706996892991121
				],
				[
					-6.488380982201761,
					16.220952455504914
				],
				[
					-6.272101616128566,
					17.734908018018707
				],
				[
					-6.055822250055144,
					19.465142946605894
				],
				[
					-5.406984151834877,
					21.19537787519309
				],
				[
					-4.974425419688032,
					22.925612803780275
				],
				[
					-4.541866687541187,
					24.007009634147273
				],
				[
					-3.8930285893211476,
					25.52096519666106
				],
				[
					-3.6767492232477252,
					26.169803294881255
				],
				[
					-3.2441904911008805,
					26.602362027028057
				],
				[
					-3.027911125027458,
					27.03492075917486
				],
				[
					-2.811631758954036,
					27.467479491321647
				],
				[
					-2.5953523928806135,
					27.683758857395055
				],
				[
					-2.379073026807191,
					27.90003822346845
				],
				[
					-1.9465142946605738,
					28.33259695561525
				],
				[
					-1.513955562513729,
					28.33259695561525
				],
				[
					-1.0813968303668844,
					28.548876321688645
				],
				[
					-0.6488380982200397,
					28.548876321688645
				],
				[
					0,
					28.548876321688645
				],
				[
					0.21627936607342235,
					28.548876321688645
				],
				[
					0.4325587321468447,
					28.33259695561525
				],
				[
					0.4325587321468447,
					28.33259695561525
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 702,
			"versionNonce": 805868907,
			"isDeleted": false,
			"id": "T6l7_m2xWZwItgY7hLcQb",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 812.7692954588008,
			"y": 1075.621252400122,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 5.623263517908299,
			"height": 12.76048259833054,
			"seed": 850785413,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6488380982200397,
					0.648838098220196
				],
				[
					-1.513955562513729,
					2.37907302680739
				],
				[
					-2.379073026807191,
					3.893028589321183
				],
				[
					-3.460469857174303,
					5.406984151834976
				],
				[
					-4.75814605361461,
					8.218615910789161
				],
				[
					-5.406984151834877,
					10.813968303669945
				],
				[
					-5.406984151834877,
					11.895365134036936
				],
				[
					-5.623263517908299,
					12.544203232257132
				],
				[
					-5.623263517908299,
					12.76048259833054
				],
				[
					-5.623263517908299,
					12.544203232257132
				],
				[
					-5.623263517908299,
					12.544203232257132
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 708,
			"versionNonce": 579209925,
			"isDeleted": false,
			"id": "C0kKJv07jykurTvvWtVen",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 807.5785906730396,
			"y": 1076.9189285965622,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.460469857174303,
			"height": 8.651174642935949,
			"seed": 2003770341,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.43255873214679497
				],
				[
					0,
					0.8651174642935899
				],
				[
					0.4325587321468447,
					1.946514294660588
				],
				[
					0.865117464293462,
					2.595352392880784
				],
				[
					1.2976761964403067,
					4.109307955394577
				],
				[
					1.7302349285871514,
					5.839542883981764
				],
				[
					2.162793660733996,
					6.920939714348762
				],
				[
					2.162793660733996,
					7.353498446495557
				],
				[
					2.3790730268074185,
					8.002336544715753
				],
				[
					2.595352392880841,
					8.434895276862548
				],
				[
					2.595352392880841,
					8.651174642935949
				],
				[
					2.811631758954263,
					8.651174642935949
				],
				[
					3.027911125027458,
					8.651174642935949
				],
				[
					3.2441904911008805,
					8.651174642935949
				],
				[
					3.2441904911008805,
					8.434895276862548
				],
				[
					3.460469857174303,
					8.002336544715753
				],
				[
					3.460469857174303,
					8.002336544715753
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 701,
			"versionNonce": 952676363,
			"isDeleted": false,
			"id": "93rA_Vzk4lresbIL9pID6",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 813.8506922891681,
			"y": 1070.4305476143604,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.162793660733996,
			"height": 6.055822250055165,
			"seed": 1296848709,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.21627936607340104
				],
				[
					0.21627936607342235,
					1.081396830366991
				],
				[
					0.6488380982200397,
					1.730234928587187
				],
				[
					1.2976761964403067,
					3.027911125027579
				],
				[
					1.7302349285871514,
					4.325587321467978
				],
				[
					1.9465142946605738,
					4.974425419688174
				],
				[
					2.162793660733996,
					5.62326351790837
				],
				[
					2.162793660733996,
					5.839542883981764
				],
				[
					2.162793660733996,
					6.055822250055165
				],
				[
					2.162793660733996,
					6.055822250055165
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 702,
			"versionNonce": 425880101,
			"isDeleted": false,
			"id": "lvzwMMP7NDOl4YKLOo6X1",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 821.4204701017368,
			"y": 1085.1375445073513,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 4.10930795539457,
			"height": 6.488380982201967,
			"seed": 514533029,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6488380982202671,
					0.43255873214679497
				],
				[
					-1.2976761964403067,
					1.297676196440392
				],
				[
					-1.9465142946605738,
					2.162793660733989
				],
				[
					-2.811631758954036,
					3.460469857174381
				],
				[
					-3.027911125027458,
					3.893028589321183
				],
				[
					-3.2441904911008805,
					4.758146053614773
				],
				[
					-3.6767492232477252,
					5.623263517908363
				],
				[
					-3.8930285893211476,
					6.272101616128559
				],
				[
					-4.10930795539457,
					6.272101616128559
				],
				[
					-4.10930795539457,
					6.488380982201967
				],
				[
					-4.10930795539457,
					6.488380982201967
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 775,
			"versionNonce": 1944876715,
			"isDeleted": false,
			"id": "rL37I0UaDThaeunvDlpus",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 825.3134986910579,
			"y": 1072.8096206411678,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 12.976761964403977,
			"height": 25.737244562734467,
			"seed": 775490053,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.648838098220196
				],
				[
					0,
					1.730234928587194
				],
				[
					0,
					2.37907302680739
				],
				[
					0,
					3.460469857174381
				],
				[
					0,
					4.541866687541379
				],
				[
					0,
					5.839542883981771
				],
				[
					0.4325587321468447,
					6.704660348275368
				],
				[
					0.8651174642936894,
					7.137219080422163
				],
				[
					1.2976761964405341,
					7.137219080422163
				],
				[
					2.162793660733996,
					6.920939714348769
				],
				[
					2.595352392880841,
					6.055822250055172
				],
				[
					3.0279111250276856,
					5.190704785761575
				],
				[
					3.4604698571745303,
					3.676749223247782
				],
				[
					3.6767492232479526,
					3.027911125027586
				],
				[
					3.6767492232479526,
					2.162793660733989
				],
				[
					3.6767492232479526,
					1.730234928587194
				],
				[
					3.6767492232479526,
					1.513955562513793
				],
				[
					3.6767492232479526,
					2.162793660733989
				],
				[
					3.6767492232479526,
					3.027911125027586
				],
				[
					3.6767492232479526,
					4.109307955394584
				],
				[
					3.6767492232479526,
					5.190704785761575
				],
				[
					3.6767492232479526,
					6.272101616128566
				],
				[
					3.6767492232479526,
					7.569777812568965
				],
				[
					3.6767492232479526,
					8.651174642935956
				],
				[
					3.6767492232479526,
					9.300012741156152
				],
				[
					3.4604698571745303,
					10.38140957152315
				],
				[
					3.244190491101108,
					11.679085767963542
				],
				[
					3.0279111250276856,
					12.976761964403934
				],
				[
					2.811631758954263,
					13.841879428697531
				],
				[
					2.595352392880841,
					15.355834991211317
				],
				[
					2.3790730268074185,
					16.869790553725117
				],
				[
					1.9465142946608012,
					18.600025482312297
				],
				[
					1.9465142946608012,
					19.0325842144591
				],
				[
					1.7302349285871514,
					20.113981044826097
				],
				[
					1.5139555625139565,
					21.195377875193095
				],
				[
					1.2976761964405341,
					22.060495339486685
				],
				[
					1.0813968303671118,
					22.925612803780275
				],
				[
					0.8651174642936894,
					23.79073026807388
				],
				[
					0.21627936607342235,
					24.439568366294075
				],
				[
					-0.21627936607342235,
					25.08840646451427
				],
				[
					-0.865117464293462,
					25.52096519666106
				],
				[
					-1.2976761964403067,
					25.737244562734467
				],
				[
					-1.7302349285871514,
					25.737244562734467
				],
				[
					-2.379073026807191,
					25.737244562734467
				],
				[
					-2.811631758954036,
					25.737244562734467
				],
				[
					-3.2441904911008805,
					25.304685830587665
				],
				[
					-3.6767492232477252,
					24.872127098440863
				],
				[
					-3.6767492232477252,
					24.439568366294075
				],
				[
					-3.8930285893211476,
					24.007009634147273
				],
				[
					-3.8930285893211476,
					23.358171535927077
				],
				[
					-3.8930285893211476,
					23.141892169853683
				],
				[
					-3.6767492232477252,
					22.70933343770688
				],
				[
					-3.027911125027458,
					22.060495339486685
				],
				[
					-2.162793660733996,
					21.195377875193095
				],
				[
					-1.7302349285871514,
					20.762819143046293
				],
				[
					-1.0813968303668844,
					20.33026041089949
				],
				[
					-0.6488380982200397,
					20.113981044826097
				],
				[
					-0.43255873214661733,
					19.89770167875269
				],
				[
					-0.21627936607342235,
					19.89770167875269
				],
				[
					0,
					19.89770167875269
				],
				[
					0.6488380982202671,
					19.89770167875269
				],
				[
					0.8651174642936894,
					20.113981044826097
				],
				[
					1.0813968303671118,
					20.33026041089949
				],
				[
					1.5139555625139565,
					20.546539776972885
				],
				[
					2.3790730268074185,
					20.979098509119687
				],
				[
					3.0279111250276856,
					21.195377875193095
				],
				[
					3.4604698571745303,
					21.627936607339883
				],
				[
					4.10930795539457,
					21.84421597341329
				],
				[
					5.190704785761682,
					22.27677470556008
				],
				[
					5.623263517908526,
					22.27677470556008
				],
				[
					5.839542883981949,
					22.493054071633487
				],
				[
					6.4883809822019884,
					22.70933343770688
				],
				[
					7.1372190804222555,
					22.70933343770688
				],
				[
					7.353498446495678,
					22.70933343770688
				],
				[
					7.786057178642523,
					22.70933343770688
				],
				[
					8.002336544715718,
					22.70933343770688
				],
				[
					8.434895276862562,
					22.70933343770688
				],
				[
					8.651174642935985,
					22.70933343770688
				],
				[
					8.867454009009407,
					22.70933343770688
				],
				[
					8.867454009009407,
					22.493054071633487
				],
				[
					9.08373337508283,
					22.27677470556008
				],
				[
					9.08373337508283,
					21.84421597341329
				],
				[
					9.08373337508283,
					21.627936607339883
				],
				[
					9.08373337508283,
					21.627936607339883
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 701,
			"versionNonce": 1748753797,
			"isDeleted": false,
			"id": "-JO42kyU1K5jIFneP1x71",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 834.3972320661412,
			"y": 1071.295665078654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.3790730268074185,
			"height": 7.786057178642352,
			"seed": 217284965,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.21627936607342235,
					0
				],
				[
					0.4325587321468447,
					0.43255873214679497
				],
				[
					0.6488380982202671,
					1.081396830366991
				],
				[
					1.0813968303671118,
					1.946514294660588
				],
				[
					1.513955562513729,
					3.027911125027579
				],
				[
					1.9465142946605738,
					4.758146053614773
				],
				[
					1.9465142946605738,
					5.839542883981764
				],
				[
					2.162793660733996,
					7.137219080422156
				],
				[
					2.3790730268074185,
					7.786057178642352
				],
				[
					2.3790730268074185,
					7.786057178642352
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 711,
			"versionNonce": 807299403,
			"isDeleted": false,
			"id": "DZSkNK8bs15_5wXKcZJFR",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 846.0763178341047,
			"y": 1084.0561476769844,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 4.974425419688259,
			"height": 7.353498446495557,
			"seed": 1344801989,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.21627936607364973,
					0
				],
				[
					-0.4325587321468447,
					0
				],
				[
					-0.6488380982202671,
					0.43255873214680207
				],
				[
					-0.8651174642936894,
					0.865117464293597
				],
				[
					-1.2976761964405341,
					1.9465142946605951
				],
				[
					-1.7302349285873788,
					3.460469857174381
				],
				[
					-1.9465142946608012,
					4.325587321467985
				],
				[
					-2.1627936607342235,
					4.758146053614773
				],
				[
					-2.3790730268074185,
					5.406984151834969
				],
				[
					-2.595352392880841,
					5.623263517908377
				],
				[
					-2.811631758954263,
					5.839542883981771
				],
				[
					-3.244190491101108,
					6.055822250055165
				],
				[
					-3.6767492232479526,
					6.272101616128573
				],
				[
					-4.109307955394797,
					6.488380982201967
				],
				[
					-4.325587321467992,
					6.920939714348769
				],
				[
					-4.541866687541415,
					7.137219080422163
				],
				[
					-4.758146053614837,
					7.353498446495557
				],
				[
					-4.974425419688259,
					7.353498446495557
				],
				[
					-4.974425419688259,
					7.137219080422163
				],
				[
					-4.974425419688259,
					7.137219080422163
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 755,
			"versionNonce": 911205605,
			"isDeleted": false,
			"id": "93Fl54bBPqScBPU2PwTUF",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 850.8344638877195,
			"y": 1073.4584587393879,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 10.81396830366998,
			"height": 19.0325842144591,
			"seed": 125053989,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4325587321468447,
					0
				],
				[
					0.6488380982202671,
					0
				],
				[
					0.8651174642936894,
					0
				],
				[
					1.2976761964403067,
					0
				],
				[
					1.9465142946605738,
					0
				],
				[
					2.811631758954263,
					0
				],
				[
					3.8930285893211476,
					0
				],
				[
					4.758146053614837,
					0
				],
				[
					5.623263517908299,
					0
				],
				[
					6.055822250055144,
					0
				],
				[
					6.704660348275411,
					0
				],
				[
					7.1372190804222555,
					0
				],
				[
					7.353498446495678,
					0
				],
				[
					7.569777812568873,
					0
				],
				[
					7.786057178642523,
					0.21627936607340104
				],
				[
					8.002336544715718,
					0.43255873214680207
				],
				[
					8.21861591078914,
					0.43255873214680207
				],
				[
					8.434895276862562,
					0.6488380982202031
				],
				[
					8.434895276862562,
					0.865117464293597
				],
				[
					8.002336544715718,
					1.081396830366998
				],
				[
					7.569777812568873,
					1.297676196440399
				],
				[
					7.1372190804222555,
					1.513955562513793
				],
				[
					6.704660348275411,
					1.730234928587194
				],
				[
					6.272101616128566,
					2.37907302680739
				],
				[
					5.839542883981721,
					2.811631758954185
				],
				[
					5.190704785761682,
					3.676749223247782
				],
				[
					4.758146053614837,
					4.75814605361478
				],
				[
					4.325587321467992,
					5.406984151834976
				],
				[
					3.6767492232477252,
					6.488380982201967
				],
				[
					3.4604698571745303,
					7.353498446495564
				],
				[
					3.244190491101108,
					8.00233654471576
				],
				[
					3.0279111250276856,
					8.651174642935956
				],
				[
					2.595352392880841,
					9.300012741156152
				],
				[
					2.3790730268074185,
					10.16513020544975
				],
				[
					2.162793660733996,
					11.030247669743346
				],
				[
					1.7302349285871514,
					11.895365134036936
				],
				[
					1.5139555625139565,
					12.54420323225714
				],
				[
					1.0813968303671118,
					13.40932069655073
				],
				[
					0.6488380982202671,
					14.058158794770925
				],
				[
					0.4325587321468447,
					14.490717526917727
				],
				[
					0.21627936607342235,
					15.139555625137923
				],
				[
					-0.21627936607342235,
					15.572114357284725
				],
				[
					-0.4325587321468447,
					16.004673089431513
				],
				[
					-0.6488380982202671,
					16.437231821578315
				],
				[
					-1.0813968303668844,
					16.869790553725117
				],
				[
					-1.513955562513729,
					17.518628651945313
				],
				[
					-1.7302349285871514,
					17.734908018018707
				],
				[
					-1.9465142946605738,
					18.16746675016551
				],
				[
					-2.162793660733996,
					18.383746116238903
				],
				[
					-2.3790730268074185,
					18.600025482312297
				],
				[
					-2.3790730268074185,
					18.816304848385705
				],
				[
					-2.3790730268074185,
					19.0325842144591
				],
				[
					-1.513955562513729,
					19.0325842144591
				],
				[
					-0.6488380982202671,
					19.0325842144591
				],
				[
					0.21627936607342235,
					19.0325842144591
				],
				[
					1.0813968303671118,
					18.816304848385705
				],
				[
					1.7302349285871514,
					18.600025482312297
				],
				[
					2.811631758954263,
					18.383746116238903
				],
				[
					3.4604698571745303,
					18.16746675016551
				],
				[
					3.6767492232477252,
					18.16746675016551
				],
				[
					4.325587321467992,
					17.9511873840921
				],
				[
					4.974425419688259,
					17.9511873840921
				],
				[
					5.406984151835104,
					17.734908018018707
				],
				[
					5.839542883981721,
					17.518628651945313
				],
				[
					6.704660348275411,
					17.518628651945313
				],
				[
					7.1372190804222555,
					17.302349285871905
				],
				[
					7.1372190804222555,
					17.302349285871905
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 705,
			"versionNonce": 45680619,
			"isDeleted": false,
			"id": "AkUsqFdaP7SsSHrK-YxrO",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 851.2670226198659,
			"y": 1079.94683972159,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 6.920939714348833,
			"height": 0.21627936607340104,
			"seed": 1925537669,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.21627936607342235,
					0
				],
				[
					-0.21627936607342235,
					0.21627936607340104
				],
				[
					0,
					0.21627936607340104
				],
				[
					1.0813968303671118,
					0.21627936607340104
				],
				[
					1.9465142946605738,
					0.21627936607340104
				],
				[
					2.595352392880841,
					0.21627936607340104
				],
				[
					3.460469857174303,
					0.21627936607340104
				],
				[
					4.10930795539457,
					0.21627936607340104
				],
				[
					4.325587321467992,
					0.21627936607340104
				],
				[
					4.974425419688259,
					0.21627936607340104
				],
				[
					5.406984151834877,
					0.21627936607340104
				],
				[
					5.623263517908299,
					0.21627936607340104
				],
				[
					5.839542883981721,
					0.21627936607340104
				],
				[
					6.055822250055144,
					0.21627936607340104
				],
				[
					6.4883809822019884,
					0.21627936607340104
				],
				[
					6.704660348275411,
					0.21627936607340104
				],
				[
					6.704660348275411,
					0.21627936607340104
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 699,
			"versionNonce": 1730936901,
			"isDeleted": false,
			"id": "aEPz0XwawsyOdV7pMHMPi",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 860.1344766288755,
			"y": 1067.1863571232593,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 3.6767492232477252,
			"height": 8.434895276862555,
			"seed": 2019108581,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4325587321468447,
					0.6488380982202031
				],
				[
					1.2976761964403067,
					1.9465142946605951
				],
				[
					1.9465142946605738,
					3.027911125027586
				],
				[
					2.3790730268074185,
					4.109307955394584
				],
				[
					3.027911125027458,
					6.055822250055172
				],
				[
					3.460469857174303,
					6.920939714348769
				],
				[
					3.460469857174303,
					7.353498446495564
				],
				[
					3.460469857174303,
					8.00233654471576
				],
				[
					3.6767492232477252,
					8.218615910789161
				],
				[
					3.6767492232477252,
					8.434895276862555
				],
				[
					3.6767492232477252,
					8.434895276862555
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 715,
			"versionNonce": 1908855435,
			"isDeleted": false,
			"id": "sDXZzUgIBmjyYEYZ_TILu",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 868.1368131735915,
			"y": 1069.13287141792,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffd43b",
			"width": 2.595352392880841,
			"height": 24.655847732367462,
			"seed": 1522336325,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.21627936607342235,
					0
				],
				[
					0,
					0.21627936607339393
				],
				[
					0.4325587321468447,
					0.648838098220196
				],
				[
					0.865117464293462,
					1.513955562513793
				],
				[
					1.0813968303668844,
					2.379073026807383
				],
				[
					1.2976761964403067,
					3.460469857174381
				],
				[
					1.7302349285871514,
					4.758146053614773
				],
				[
					1.9465142946605738,
					5.839542883981764
				],
				[
					1.9465142946605738,
					7.353498446495557
				],
				[
					1.9465142946605738,
					8.86745400900935
				],
				[
					1.9465142946605738,
					11.24652703581674
				],
				[
					1.9465142946605738,
					12.760482598330526
				],
				[
					1.9465142946605738,
					14.706996892991121
				],
				[
					1.7302349285871514,
					16.004673089431513
				],
				[
					1.7302349285871514,
					17.518628651945306
				],
				[
					1.513955562513729,
					18.8163048483857
				],
				[
					1.2976761964403067,
					20.546539776972892
				],
				[
					1.0813968303668844,
					21.627936607339876
				],
				[
					0.865117464293462,
					22.06049533948668
				],
				[
					0.6488380982202671,
					22.709333437706874
				],
				[
					0.4325587321468447,
					23.141892169853676
				],
				[
					0.4325587321468447,
					23.574450902000464
				],
				[
					0.21627936607342235,
					24.007009634147266
				],
				[
					-0.21627936607342235,
					24.43956836629407
				],
				[
					-0.4325587321468447,
					24.655847732367462
				],
				[
					-0.6488380982202671,
					24.655847732367462
				],
				[
					-0.6488380982202671,
					24.655847732367462
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 836,
			"versionNonce": 279818149,
			"isDeleted": false,
			"id": "Tn3sYRVU8W1A_QCSW_H8x",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 677.1114306603499,
			"y": 1046.0420278177312,
			"strokeColor": "#e03131",
			"backgroundColor": "#deede1",
			"width": 42.252971451198846,
			"height": 47.69464201688379,
			"seed": 1712404971,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.320098268569609,
					-0.320098268569609
				],
				[
					0.9602948057090543,
					-0.6401965371394454
				],
				[
					1.2803930742786633,
					-0.9602948057090543
				],
				[
					1.6004913428484997,
					-0.9602948057090543
				],
				[
					2.2406878799877177,
					-1.9205896114181087
				],
				[
					2.880884417127163,
					-2.2406878799877177
				],
				[
					4.481375759975663,
					-4.161277491406054
				],
				[
					5.121572297115108,
					-5.441670565684717
				],
				[
					6.401965371393771,
					-7.042161908533217
				],
				[
					7.682358445672435,
					-8.642653251381716
				],
				[
					8.642653251381489,
					-10.243144594229989
				],
				[
					9.602948057090543,
					-11.843635937078488
				],
				[
					10.563242862799598,
					-13.124029011357152
				],
				[
					11.203439399939043,
					-14.404422085636043
				],
				[
					12.163734205648097,
					-15.364716891345097
				],
				[
					12.803930742787543,
					-16.64510996562376
				],
				[
					14.084323817066206,
					-17.92550303990265
				],
				[
					14.724520354205652,
					-19.205896114181314
				],
				[
					15.364716891345097,
					-19.84609265132076
				],
				[
					16.004913428484542,
					-20.806387457029814
				],
				[
					16.64510996562376,
					-21.76668226273887
				],
				[
					16.965208234193597,
					-22.406878799878314
				],
				[
					17.605404771332815,
					-23.367173605587368
				],
				[
					18.24560130847226,
					-24.007370142726586
				],
				[
					18.885797845611705,
					-24.327468411296422
				],
				[
					19.205896114181314,
					-24.96766494843564
				],
				[
					19.84609265132076,
					-25.287763217005477
				],
				[
					20.16619091989037,
					-25.927959754144922
				],
				[
					20.486289188459978,
					-26.24805802271453
				],
				[
					21.126485725599423,
					-26.888254559853976
				],
				[
					21.446583994169032,
					-27.84854936556303
				],
				[
					22.086780531308477,
					-28.16864763413264
				],
				[
					22.406878799878314,
					-28.48874590270225
				],
				[
					23.04707533701753,
					-28.808844171272085
				],
				[
					23.367173605587368,
					-29.128942439841694
				],
				[
					23.687271874156977,
					-29.44904070841153
				],
				[
					24.007370142726586,
					-29.76913897698114
				],
				[
					24.327468411296422,
					-30.08923724555075
				],
				[
					24.64756667986603,
					-30.409335514120585
				],
				[
					24.96766494843564,
					-30.729433782690194
				],
				[
					25.287763217005477,
					-31.049532051259803
				],
				[
					25.607861485575086,
					-31.36963031982964
				],
				[
					25.927959754144695,
					-31.36963031982964
				],
				[
					26.24805802271453,
					-31.689728588399248
				],
				[
					26.888254559853976,
					-32.32992512553869
				],
				[
					27.208352828423585,
					-32.6500233941083
				],
				[
					27.528451096993194,
					-32.6500233941083
				],
				[
					27.528451096993194,
					-32.97012166267791
				],
				[
					27.84854936556303,
					-33.29021993124775
				],
				[
					28.16864763413264,
					-33.29021993124775
				],
				[
					28.48874590270225,
					-32.97012166267791
				],
				[
					28.808844171272085,
					-32.97012166267791
				],
				[
					29.128942439841694,
					-32.6500233941083
				],
				[
					29.449040708411303,
					-32.32992512553869
				],
				[
					29.76913897698114,
					-32.32992512553869
				],
				[
					30.08923724555075,
					-32.32992512553869
				],
				[
					30.409335514120357,
					-32.32992512553869
				],
				[
					30.729433782690194,
					-32.00982685696886
				],
				[
					31.36963031982941,
					-32.00982685696886
				],
				[
					32.00982685696886,
					-31.689728588399248
				],
				[
					32.329925125538466,
					-31.689728588399248
				],
				[
					32.6500233941083,
					-31.689728588399248
				],
				[
					33.29021993124752,
					-31.689728588399248
				],
				[
					33.61031819981736,
					-31.689728588399248
				],
				[
					34.2505147369568,
					-31.689728588399248
				],
				[
					34.57061300552641,
					-31.36963031982964
				],
				[
					34.89071127409602,
					-31.36963031982964
				],
				[
					35.21080954266586,
					-31.36963031982964
				],
				[
					35.530907811235465,
					-31.36963031982964
				],
				[
					35.851006079805074,
					-31.36963031982964
				],
				[
					35.851006079805074,
					-31.049532051259803
				],
				[
					36.17110434837491,
					-31.049532051259803
				],
				[
					36.49120261694452,
					-31.049532051259803
				],
				[
					36.81130088551413,
					-31.049532051259803
				],
				[
					37.131399154083965,
					-31.049532051259803
				],
				[
					37.451497422653574,
					-31.049532051259803
				],
				[
					37.451497422653574,
					-31.36963031982964
				],
				[
					37.451497422653574,
					-32.00982685696886
				],
				[
					37.451497422653574,
					-32.97012166267791
				],
				[
					37.451497422653574,
					-33.930416468386966
				],
				[
					37.451497422653574,
					-34.2505147369568
				],
				[
					37.451497422653574,
					-35.530907811235465
				],
				[
					37.131399154083965,
					-35.530907811235465
				],
				[
					37.131399154083965,
					-36.17110434837491
				],
				[
					37.131399154083965,
					-37.131399154083965
				],
				[
					37.131399154083965,
					-37.77159569122341
				],
				[
					37.131399154083965,
					-38.41179222836263
				],
				[
					37.131399154083965,
					-39.051988765502074
				],
				[
					37.451497422653574,
					-39.69218530264152
				],
				[
					37.451497422653574,
					-40.33238183978074
				],
				[
					37.77159569122341,
					-40.97257837692018
				],
				[
					37.77159569122341,
					-41.61277491405963
				],
				[
					38.09169395979302,
					-42.25297145119907
				],
				[
					38.41179222836263,
					-42.89316798833829
				],
				[
					38.731890496932465,
					-43.53336452547774
				],
				[
					39.051988765502074,
					-43.853462794047346
				],
				[
					39.37208703407168,
					-44.49365933118679
				],
				[
					39.69218530264152,
					-45.133855868326236
				],
				[
					40.01228357121113,
					-45.453954136895845
				],
				[
					40.01228357121113,
					-46.09415067403529
				],
				[
					40.33238183978074,
					-46.4142489426049
				],
				[
					40.652480108350574,
					-46.73434721117451
				],
				[
					40.97257837692018,
					-47.374543748313954
				],
				[
					41.29267664548979,
					-47.69464201688379
				],
				[
					40.97257837692018,
					-47.69464201688379
				],
				[
					40.33238183978074,
					-47.054445479744345
				],
				[
					39.69218530264152,
					-47.054445479744345
				],
				[
					39.051988765502074,
					-46.73434721117451
				],
				[
					38.09169395979302,
					-46.4142489426049
				],
				[
					37.131399154083965,
					-45.774052405465454
				],
				[
					36.17110434837491,
					-45.453954136895845
				],
				[
					34.57061300552641,
					-44.8137575997564
				],
				[
					33.61031819981736,
					-44.49365933118679
				],
				[
					32.329925125538466,
					-44.49365933118679
				],
				[
					31.36963031982941,
					-44.17356106261718
				],
				[
					30.08923724555075,
					-43.53336452547774
				],
				[
					29.128942439841694,
					-43.53336452547774
				],
				[
					27.84854936556303,
					-43.21326625690813
				],
				[
					26.888254559853976,
					-43.21326625690813
				],
				[
					25.927959754144695,
					-42.57306971976868
				],
				[
					24.96766494843564,
					-42.25297145119907
				],
				[
					24.007370142726586,
					-41.93287318262924
				],
				[
					23.04707533701753,
					-41.29267664549002
				],
				[
					22.406878799878314,
					-40.97257837692018
				],
				[
					21.446583994169032,
					-40.33238183978074
				],
				[
					20.486289188459978,
					-39.69218530264152
				],
				[
					19.525994382750923,
					-39.37208703407168
				],
				[
					19.205896114181314,
					-39.051988765502074
				],
				[
					18.24560130847226,
					-38.41179222836263
				],
				[
					17.92550303990265,
					-38.09169395979302
				],
				[
					17.605404771332815,
					-38.09169395979302
				],
				[
					16.965208234193597,
					-37.77159569122341
				],
				[
					16.64510996562376,
					-37.77159569122341
				],
				[
					16.32501169705415,
					-37.451497422653574
				],
				[
					16.004913428484542,
					-37.451497422653574
				],
				[
					16.32501169705415,
					-37.451497422653574
				],
				[
					16.965208234193597,
					-37.451497422653574
				],
				[
					17.605404771332815,
					-37.451497422653574
				],
				[
					18.885797845611705,
					-37.451497422653574
				],
				[
					19.525994382750923,
					-37.451497422653574
				],
				[
					21.446583994169032,
					-37.451497422653574
				],
				[
					22.406878799878314,
					-37.451497422653574
				],
				[
					23.367173605587368,
					-37.451497422653574
				],
				[
					24.96766494843564,
					-37.451497422653574
				],
				[
					26.24805802271453,
					-37.451497422653574
				],
				[
					27.528451096993194,
					-37.451497422653574
				],
				[
					28.16864763413264,
					-37.451497422653574
				],
				[
					29.128942439841694,
					-37.451497422653574
				],
				[
					29.76913897698114,
					-37.131399154083965
				],
				[
					30.409335514120357,
					-37.131399154083965
				],
				[
					31.049532051259803,
					-36.811300885514356
				],
				[
					32.00982685696886,
					-36.811300885514356
				],
				[
					32.6500233941083,
					-36.811300885514356
				],
				[
					32.97012166267791,
					-36.811300885514356
				],
				[
					33.61031819981736,
					-36.49120261694452
				],
				[
					33.930416468386966,
					-36.49120261694452
				],
				[
					34.57061300552641,
					-36.49120261694452
				],
				[
					35.21080954266586,
					-36.49120261694452
				],
				[
					35.530907811235465,
					-36.49120261694452
				],
				[
					35.21080954266586,
					-36.811300885514356
				],
				[
					34.89071127409602,
					-37.131399154083965
				],
				[
					34.89071127409602,
					-37.77159569122341
				],
				[
					34.89071127409602,
					-38.731890496932465
				],
				[
					34.89071127409602,
					-39.69218530264152
				],
				[
					34.89071127409602,
					-40.33238183978074
				],
				[
					34.89071127409602,
					-41.29267664549002
				],
				[
					34.89071127409602,
					-41.61277491405963
				],
				[
					35.21080954266586,
					-41.93287318262924
				],
				[
					35.530907811235465,
					-42.57306971976868
				],
				[
					35.851006079805074,
					-42.89316798833829
				],
				[
					36.17110434837491,
					-43.21326625690813
				],
				[
					36.49120261694452,
					-43.21326625690813
				],
				[
					36.49120261694452,
					-43.53336452547774
				],
				[
					36.49120261694452,
					-43.21326625690813
				],
				[
					36.17110434837491,
					-42.89316798833829
				],
				[
					36.17110434837491,
					-42.57306971976868
				],
				[
					35.851006079805074,
					-41.93287318262924
				],
				[
					35.530907811235465,
					-41.29267664549002
				],
				[
					35.530907811235465,
					-40.652480108350574
				],
				[
					35.21080954266586,
					-40.33238183978074
				],
				[
					34.89071127409602,
					-40.01228357121113
				],
				[
					34.57061300552641,
					-39.69218530264152
				],
				[
					34.2505147369568,
					-39.37208703407168
				],
				[
					33.61031819981736,
					-39.051988765502074
				],
				[
					32.97012166267791,
					-38.731890496932465
				],
				[
					32.329925125538466,
					-38.41179222836263
				],
				[
					31.36963031982941,
					-38.09169395979302
				],
				[
					30.729433782690194,
					-37.77159569122341
				],
				[
					29.76913897698114,
					-37.131399154083965
				],
				[
					28.808844171272085,
					-36.811300885514356
				],
				[
					28.16864763413264,
					-36.49120261694452
				],
				[
					27.528451096993194,
					-36.17110434837491
				],
				[
					26.888254559853976,
					-35.530907811235465
				],
				[
					26.24805802271453,
					-35.21080954266586
				],
				[
					25.607861485575086,
					-34.57061300552641
				],
				[
					24.96766494843564,
					-33.930416468386966
				],
				[
					24.327468411296422,
					-33.29021993124775
				],
				[
					23.687271874156977,
					-32.97012166267791
				],
				[
					23.367173605587368,
					-32.00982685696886
				],
				[
					23.04707533701753,
					-31.36963031982964
				],
				[
					22.406878799878314,
					-30.729433782690194
				],
				[
					22.086780531308477,
					-30.08923724555075
				],
				[
					21.76668226273887,
					-29.44904070841153
				],
				[
					21.126485725599423,
					-28.48874590270225
				],
				[
					20.806387457029814,
					-28.16864763413264
				],
				[
					20.486289188459978,
					-27.528451096993194
				],
				[
					20.486289188459978,
					-26.888254559853976
				],
				[
					20.16619091989037,
					-26.24805802271453
				],
				[
					19.84609265132076,
					-25.607861485575086
				],
				[
					19.525994382750923,
					-24.96766494843564
				],
				[
					19.525994382750923,
					-24.64756667986603
				],
				[
					19.205896114181314,
					-24.007370142726586
				],
				[
					18.885797845611705,
					-23.367173605587368
				],
				[
					18.56569957704187,
					-23.04707533701753
				],
				[
					18.24560130847226,
					-22.406878799878314
				],
				[
					18.24560130847226,
					-22.086780531308477
				],
				[
					17.92550303990265,
					-21.76668226273887
				],
				[
					17.605404771332815,
					-20.806387457029814
				],
				[
					17.285306502763206,
					-20.16619091989037
				],
				[
					16.64510996562376,
					-19.52599438275115
				],
				[
					16.32501169705415,
					-18.885797845611705
				],
				[
					15.684815159914706,
					-17.92550303990265
				],
				[
					15.04461862277526,
					-17.285306502763206
				],
				[
					14.404422085636043,
					-16.32501169705415
				],
				[
					13.764225548496597,
					-15.684815159914706
				],
				[
					13.124029011357152,
					-15.044618622775488
				],
				[
					12.483832474217934,
					-14.404422085636043
				],
				[
					11.52353766850888,
					-13.444127279926988
				],
				[
					10.883341131369434,
					-12.803930742787543
				],
				[
					10.243144594229989,
					-12.163734205648097
				],
				[
					8.962751519951325,
					-10.883341131369434
				],
				[
					8.32255498281188,
					-10.243144594229989
				],
				[
					7.362260177102826,
					-9.60294805709077
				],
				[
					6.72206363996338,
					-8.962751519951325
				],
				[
					5.761768834254326,
					-8.002456714242271
				],
				[
					5.121572297115108,
					-7.362260177102826
				],
				[
					4.161277491406054,
					-6.722063639963608
				],
				[
					3.200982685696772,
					-5.761768834254326
				],
				[
					2.560786148557554,
					-5.121572297115108
				],
				[
					1.9205896114181087,
					-4.801474028545272
				],
				[
					1.6004913428484997,
					-4.481375759975663
				],
				[
					0.9602948057090543,
					-3.8411792228362174
				],
				[
					0.320098268569609,
					-3.5210809542666084
				],
				[
					0,
					-3.2009826856969994
				],
				[
					-0.320098268569609,
					-2.560786148557554
				],
				[
					-0.6401965371394454,
					-2.2406878799877177
				],
				[
					-0.9602948057090543,
					-2.2406878799877177
				],
				[
					-0.320098268569609,
					-2.2406878799877177
				],
				[
					0.320098268569609,
					-3.2009826856969994
				],
				[
					1.2803930742786633,
					-3.5210809542666084
				],
				[
					2.2406878799877177,
					-4.481375759975663
				],
				[
					3.5210809542666084,
					-5.441670565684717
				],
				[
					4.801474028545272,
					-6.401965371393771
				],
				[
					5.441670565684717,
					-7.042161908533217
				],
				[
					6.72206363996338,
					-8.002456714242271
				],
				[
					7.682358445672435,
					-8.962751519951325
				],
				[
					8.962751519951325,
					-9.92304632566038
				],
				[
					9.92304632566038,
					-11.203439399939043
				],
				[
					10.563242862799598,
					-12.163734205648097
				],
				[
					11.843635937078488,
					-13.444127279926988
				],
				[
					12.163734205648097,
					-14.404422085636043
				],
				[
					12.803930742787543,
					-15.364716891345097
				],
				[
					13.444127279926988,
					-16.32501169705415
				],
				[
					14.084323817066206,
					-16.965208234193597
				],
				[
					14.404422085636043,
					-17.92550303990265
				],
				[
					15.04461862277526,
					-18.885797845611705
				],
				[
					15.684815159914706,
					-19.84609265132076
				],
				[
					16.004913428484542,
					-20.486289188460205
				],
				[
					16.64510996562376,
					-21.44658399416926
				],
				[
					16.965208234193597,
					-22.406878799878314
				],
				[
					17.605404771332815,
					-22.726977068447923
				],
				[
					18.24560130847226,
					-24.007370142726586
				],
				[
					18.56569957704187,
					-24.64756667986603
				],
				[
					19.205896114181314,
					-25.287763217005477
				],
				[
					19.525994382750923,
					-25.927959754144922
				],
				[
					20.16619091989037,
					-26.56815629128414
				],
				[
					20.806387457029814,
					-27.208352828423585
				],
				[
					21.126485725599423,
					-27.84854936556303
				],
				[
					21.76668226273887,
					-28.48874590270225
				],
				[
					22.086780531308477,
					-29.128942439841694
				],
				[
					22.726977068447923,
					-30.08923724555075
				],
				[
					23.367173605587368,
					-30.409335514120585
				],
				[
					23.687271874156977,
					-31.049532051259803
				],
				[
					24.007370142726586,
					-31.689728588399248
				],
				[
					24.64756667986603,
					-32.00982685696886
				],
				[
					25.287763217005477,
					-32.6500233941083
				],
				[
					25.607861485575086,
					-32.97012166267791
				],
				[
					25.927959754144695,
					-33.29021993124775
				],
				[
					26.24805802271453,
					-33.61031819981736
				],
				[
					26.56815629128414,
					-33.930416468386966
				],
				[
					26.888254559853976,
					-34.2505147369568
				],
				[
					27.208352828423585,
					-34.57061300552641
				],
				[
					26.888254559853976,
					-34.57061300552641
				],
				[
					26.888254559853976,
					-34.57061300552641
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 943,
			"versionNonce": 1577208107,
			"isDeleted": false,
			"id": "gqbDHe3HarXB1qizgVCa_",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 826.5973220823946,
			"y": 1006.6699407836594,
			"strokeColor": "#e03131",
			"backgroundColor": "#deede1",
			"width": 47.054445479744345,
			"height": 45.13385586832601,
			"seed": 959943403,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.32009826856983636,
					0
				],
				[
					0.6401965371394454,
					0
				],
				[
					0.9602948057090543,
					0
				],
				[
					1.6004913428484997,
					0
				],
				[
					2.560786148557554,
					0.640196537139218
				],
				[
					2.8808844171273904,
					0.9602948057090543
				],
				[
					3.2009826856969994,
					1.2803930742786633
				],
				[
					3.5210809542666084,
					1.6004913428482723
				],
				[
					3.5210809542666084,
					1.9205896114181087
				],
				[
					3.8411792228364448,
					2.2406878799877177
				],
				[
					4.481375759975663,
					2.880884417127163
				],
				[
					5.121572297115108,
					3.200982685696772
				],
				[
					5.761768834254553,
					3.8411792228362174
				],
				[
					6.401965371393771,
					4.481375759975663
				],
				[
					6.722063639963608,
					4.801474028545272
				],
				[
					7.362260177102826,
					5.121572297114881
				],
				[
					7.682358445672662,
					5.441670565684717
				],
				[
					8.002456714242271,
					5.761768834254326
				],
				[
					8.642653251381716,
					6.401965371393771
				],
				[
					9.282849788520934,
					6.72206363996338
				],
				[
					9.60294805709077,
					7.042161908532989
				],
				[
					10.243144594230216,
					7.682358445672435
				],
				[
					10.563242862799825,
					8.002456714242044
				],
				[
					10.883341131369434,
					8.32255498281188
				],
				[
					11.20343939993927,
					8.962751519951098
				],
				[
					11.52353766850888,
					9.282849788520934
				],
				[
					11.52353766850888,
					9.602948057090543
				],
				[
					11.843635937078716,
					9.923046325660152
				],
				[
					12.163734205648325,
					10.243144594229989
				],
				[
					12.483832474217934,
					10.883341131369434
				],
				[
					12.80393074278777,
					11.203439399939043
				],
				[
					13.12402901135738,
					11.523537668508652
				],
				[
					13.12402901135738,
					11.843635937078488
				],
				[
					13.444127279926988,
					12.163734205648097
				],
				[
					13.764225548496825,
					12.483832474217706
				],
				[
					14.084323817066434,
					13.124029011357152
				],
				[
					14.724520354205879,
					13.44412727992676
				],
				[
					14.724520354205879,
					13.764225548496597
				],
				[
					15.044618622775488,
					14.404422085636043
				],
				[
					15.364716891345097,
					14.724520354205652
				],
				[
					15.684815159914933,
					15.364716891345097
				],
				[
					16.004913428484542,
					15.684815159914706
				],
				[
					16.32501169705415,
					16.004913428484315
				],
				[
					16.645109965623988,
					16.32501169705415
				],
				[
					16.645109965623988,
					16.64510996562376
				],
				[
					17.285306502763206,
					17.285306502763206
				],
				[
					17.285306502763206,
					17.605404771332815
				],
				[
					17.605404771333042,
					17.925503039902424
				],
				[
					18.24560130847226,
					18.885797845611478
				],
				[
					18.565699577042096,
					19.205896114181314
				],
				[
					19.205896114181314,
					19.846092651320532
				],
				[
					19.52599438275115,
					20.16619091989037
				],
				[
					19.84609265132076,
					20.486289188459978
				],
				[
					20.486289188460205,
					21.126485725599423
				],
				[
					20.806387457029814,
					21.446583994169032
				],
				[
					21.126485725599423,
					21.76668226273887
				],
				[
					21.44658399416926,
					22.406878799878086
				],
				[
					22.086780531308705,
					22.726977068447923
				],
				[
					22.72697706844815,
					23.04707533701753
				],
				[
					23.04707533701776,
					23.687271874156977
				],
				[
					23.687271874157204,
					24.007370142726586
				],
				[
					24.007370142726813,
					24.327468411296195
				],
				[
					24.327468411296422,
					24.96766494843564
				],
				[
					24.64756667986626,
					25.287763217005477
				],
				[
					24.967664948435868,
					25.607861485575086
				],
				[
					25.607861485575313,
					25.927959754144695
				],
				[
					25.927959754144922,
					26.24805802271453
				],
				[
					26.24805802271453,
					26.56815629128414
				],
				[
					26.888254559853976,
					26.88825455985375
				],
				[
					27.208352828423585,
					27.208352828423585
				],
				[
					27.52845109699342,
					27.208352828423585
				],
				[
					27.84854936556303,
					27.528451096993194
				],
				[
					28.488745902702476,
					27.848549365562803
				],
				[
					28.808844171272085,
					28.16864763413264
				],
				[
					29.128942439841694,
					28.16864763413264
				],
				[
					29.44904070841153,
					28.48874590270225
				],
				[
					29.76913897698114,
					28.48874590270225
				],
				[
					30.409335514120585,
					29.128942439841694
				],
				[
					30.729433782690194,
					29.128942439841694
				],
				[
					31.36963031982964,
					29.449040708411303
				],
				[
					31.689728588399248,
					29.449040708411303
				],
				[
					32.00982685696886,
					29.769138976980912
				],
				[
					32.32992512553869,
					30.08923724555075
				],
				[
					32.6500233941083,
					30.08923724555075
				],
				[
					32.97012166267814,
					30.409335514120357
				],
				[
					33.29021993124775,
					30.409335514120357
				],
				[
					33.61031819981736,
					30.409335514120357
				],
				[
					32.97012166267814,
					31.049532051259803
				],
				[
					32.6500233941083,
					31.36963031982941
				],
				[
					32.00982685696886,
					32.00982685696886
				],
				[
					31.689728588399248,
					32.329925125538466
				],
				[
					31.049532051259803,
					32.97012166267791
				],
				[
					30.409335514120585,
					33.29021993124752
				],
				[
					30.08923724555075,
					33.61031819981736
				],
				[
					29.76913897698114,
					33.930416468386966
				],
				[
					28.808844171272085,
					34.57061300552641
				],
				[
					28.488745902702476,
					34.89071127409602
				],
				[
					27.52845109699342,
					35.851006079805074
				],
				[
					26.888254559853976,
					36.17110434837468
				],
				[
					26.24805802271453,
					37.131399154083965
				],
				[
					25.607861485575313,
					37.451497422653574
				],
				[
					24.967664948435868,
					38.41179222836263
				],
				[
					24.64756667986626,
					38.73189049693224
				],
				[
					24.327468411296422,
					39.37208703407168
				],
				[
					24.007370142726813,
					39.69218530264129
				],
				[
					23.687271874157204,
					40.33238183978074
				],
				[
					23.04707533701776,
					40.97257837692018
				],
				[
					22.72697706844815,
					41.29267664548979
				],
				[
					22.406878799878314,
					41.93287318262924
				],
				[
					22.086780531308705,
					42.252971451198846
				],
				[
					21.76668226273887,
					42.89316798833829
				],
				[
					21.126485725599423,
					43.2132662569079
				],
				[
					20.806387457029814,
					43.53336452547751
				],
				[
					20.806387457029814,
					43.853462794047346
				],
				[
					20.486289188460205,
					44.173561062616955
				],
				[
					20.16619091989037,
					44.49365933118679
				],
				[
					20.16619091989037,
					44.8137575997564
				],
				[
					19.84609265132076,
					44.8137575997564
				],
				[
					19.84609265132076,
					45.13385586832601
				],
				[
					20.16619091989037,
					45.13385586832601
				],
				[
					20.806387457029814,
					45.13385586832601
				],
				[
					21.76668226273887,
					45.13385586832601
				],
				[
					22.406878799878314,
					45.13385586832601
				],
				[
					23.04707533701776,
					45.13385586832601
				],
				[
					23.687271874157204,
					45.13385586832601
				],
				[
					24.64756667986626,
					45.13385586832601
				],
				[
					24.967664948435868,
					45.13385586832601
				],
				[
					25.927959754144922,
					45.13385586832601
				],
				[
					26.888254559853976,
					45.13385586832601
				],
				[
					27.52845109699342,
					45.13385586832601
				],
				[
					28.16864763413264,
					45.13385586832601
				],
				[
					28.488745902702476,
					45.13385586832601
				],
				[
					29.128942439841694,
					44.8137575997564
				],
				[
					30.08923724555075,
					44.8137575997564
				],
				[
					30.729433782690194,
					44.8137575997564
				],
				[
					31.36963031982964,
					44.8137575997564
				],
				[
					32.00982685696886,
					44.8137575997564
				],
				[
					32.97012166267814,
					44.8137575997564
				],
				[
					33.29021993124775,
					44.8137575997564
				],
				[
					33.93041646838719,
					44.8137575997564
				],
				[
					34.89071127409625,
					44.8137575997564
				],
				[
					35.53090781123569,
					44.8137575997564
				],
				[
					36.17110434837491,
					44.8137575997564
				],
				[
					36.811300885514356,
					44.8137575997564
				],
				[
					37.131399154083965,
					44.8137575997564
				],
				[
					37.4514974226538,
					44.8137575997564
				],
				[
					38.09169395979302,
					44.8137575997564
				],
				[
					38.731890496932465,
					44.8137575997564
				],
				[
					39.051988765502074,
					44.8137575997564
				],
				[
					39.37208703407191,
					44.8137575997564
				],
				[
					39.69218530264152,
					44.8137575997564
				],
				[
					40.332381839780965,
					44.8137575997564
				],
				[
					40.652480108350574,
					44.8137575997564
				],
				[
					40.97257837692018,
					44.8137575997564
				],
				[
					41.29267664549002,
					44.8137575997564
				],
				[
					41.61277491405963,
					44.8137575997564
				],
				[
					41.93287318262924,
					44.8137575997564
				],
				[
					42.57306971976868,
					44.8137575997564
				],
				[
					42.89316798833829,
					44.8137575997564
				],
				[
					43.21326625690813,
					45.13385586832601
				],
				[
					43.53336452547774,
					45.13385586832601
				],
				[
					43.85346279404757,
					45.13385586832601
				],
				[
					44.17356106261718,
					45.13385586832601
				],
				[
					44.49365933118679,
					45.13385586832601
				],
				[
					44.81375759975663,
					45.13385586832601
				],
				[
					44.81375759975663,
					44.49365933118679
				],
				[
					44.81375759975663,
					43.53336452547751
				],
				[
					44.81375759975663,
					42.573069719768455
				],
				[
					44.81375759975663,
					41.29267664548979
				],
				[
					44.81375759975663,
					40.01228357121113
				],
				[
					44.81375759975663,
					38.41179222836263
				],
				[
					44.49365933118679,
					36.17110434837468
				],
				[
					44.49365933118679,
					35.21080954266563
				],
				[
					44.17356106261718,
					33.61031819981736
				],
				[
					43.85346279404757,
					32.329925125538466
				],
				[
					43.85346279404757,
					31.68972858839902
				],
				[
					43.85346279404757,
					30.409335514120357
				],
				[
					43.85346279404757,
					29.128942439841694
				],
				[
					43.53336452547774,
					28.48874590270225
				],
				[
					43.53336452547774,
					27.528451096993194
				],
				[
					43.53336452547774,
					26.24805802271453
				],
				[
					43.53336452547774,
					25.927959754144695
				],
				[
					43.53336452547774,
					24.64756667986603
				],
				[
					43.53336452547774,
					23.687271874156977
				],
				[
					43.53336452547774,
					23.04707533701753
				],
				[
					43.53336452547774,
					22.086780531308477
				],
				[
					43.53336452547774,
					21.446583994169032
				],
				[
					43.53336452547774,
					20.806387457029587
				],
				[
					43.53336452547774,
					20.486289188459978
				],
				[
					43.53336452547774,
					20.16619091989037
				],
				[
					43.53336452547774,
					19.525994382750923
				],
				[
					43.53336452547774,
					19.205896114181314
				],
				[
					43.53336452547774,
					18.885797845611478
				],
				[
					43.21326625690813,
					18.885797845611478
				],
				[
					42.89316798833829,
					19.205896114181314
				],
				[
					42.25297145119907,
					19.846092651320532
				],
				[
					41.93287318262924,
					20.16619091989037
				],
				[
					41.61277491405963,
					21.126485725599423
				],
				[
					40.97257837692018,
					22.086780531308477
				],
				[
					40.332381839780965,
					22.406878799878086
				],
				[
					40.01228357121113,
					23.04707533701753
				],
				[
					39.37208703407191,
					23.687271874156977
				],
				[
					38.731890496932465,
					24.64756667986603
				],
				[
					38.411792228362856,
					25.287763217005477
				],
				[
					37.77159569122341,
					25.927959754144695
				],
				[
					37.131399154083965,
					26.88825455985375
				],
				[
					36.811300885514356,
					27.528451096993194
				],
				[
					36.17110434837491,
					28.48874590270225
				],
				[
					35.8510060798053,
					28.808844171271858
				],
				[
					35.21080954266586,
					29.769138976980912
				],
				[
					34.89071127409625,
					30.08923724555075
				],
				[
					34.2505147369568,
					31.049532051259803
				],
				[
					33.93041646838719,
					31.68972858839902
				],
				[
					33.61031819981736,
					32.329925125538466
				],
				[
					33.29021993124775,
					32.650023394108075
				],
				[
					32.97012166267814,
					33.29021993124752
				],
				[
					32.6500233941083,
					33.61031819981736
				],
				[
					32.32992512553869,
					34.250514736956575
				],
				[
					32.00982685696886,
					34.57061300552641
				],
				[
					32.00982685696886,
					35.21080954266563
				],
				[
					31.36963031982964,
					35.530907811235465
				],
				[
					31.049532051259803,
					36.17110434837468
				],
				[
					30.729433782690194,
					36.81130088551413
				],
				[
					30.08923724555075,
					37.451497422653574
				],
				[
					29.76913897698114,
					38.09169395979302
				],
				[
					29.44904070841153,
					38.73189049693224
				],
				[
					29.44904070841153,
					39.051988765502074
				],
				[
					30.729433782690194,
					39.051988765502074
				],
				[
					32.00982685696886,
					39.051988765502074
				],
				[
					32.97012166267814,
					39.051988765502074
				],
				[
					33.61031819981736,
					39.051988765502074
				],
				[
					34.89071127409625,
					39.051988765502074
				],
				[
					35.8510060798053,
					39.051988765502074
				],
				[
					36.17110434837491,
					39.051988765502074
				],
				[
					36.49120261694475,
					39.051988765502074
				],
				[
					36.811300885514356,
					39.051988765502074
				],
				[
					37.4514974226538,
					39.051988765502074
				],
				[
					38.09169395979302,
					39.051988765502074
				],
				[
					38.411792228362856,
					39.051988765502074
				],
				[
					38.731890496932465,
					38.73189049693224
				],
				[
					39.37208703407191,
					38.09169395979302
				],
				[
					39.69218530264152,
					37.77159569122318
				],
				[
					40.01228357121113,
					37.131399154083965
				],
				[
					40.332381839780965,
					36.49120261694452
				],
				[
					40.332381839780965,
					35.530907811235465
				],
				[
					40.332381839780965,
					33.61031819981736
				],
				[
					40.332381839780965,
					32.650023394108075
				],
				[
					40.332381839780965,
					31.68972858839902
				],
				[
					40.332381839780965,
					31.049532051259803
				],
				[
					40.332381839780965,
					30.409335514120357
				],
				[
					40.332381839780965,
					30.729433782689966
				],
				[
					40.01228357121113,
					31.049532051259803
				],
				[
					39.37208703407191,
					31.68972858839902
				],
				[
					39.051988765502074,
					32.329925125538466
				],
				[
					39.051988765502074,
					32.97012166267791
				],
				[
					39.051988765502074,
					33.29021993124752
				],
				[
					39.051988765502074,
					33.61031819981736
				],
				[
					38.731890496932465,
					33.61031819981736
				],
				[
					38.411792228362856,
					33.61031819981736
				],
				[
					38.09169395979302,
					33.61031819981736
				],
				[
					37.77159569122341,
					33.61031819981736
				],
				[
					37.131399154083965,
					32.97012166267791
				],
				[
					36.49120261694475,
					32.650023394108075
				],
				[
					36.17110434837491,
					32.329925125538466
				],
				[
					34.89071127409625,
					31.68972858839902
				],
				[
					33.93041646838719,
					31.049532051259803
				],
				[
					32.32992512553869,
					30.08923724555075
				],
				[
					31.049532051259803,
					29.769138976980912
				],
				[
					30.08923724555075,
					29.128942439841694
				],
				[
					28.808844171272085,
					28.808844171271858
				],
				[
					27.52845109699342,
					27.848549365562803
				],
				[
					26.888254559853976,
					27.528451096993194
				],
				[
					25.927959754144922,
					27.208352828423585
				],
				[
					24.967664948435868,
					26.88825455985375
				],
				[
					24.007370142726813,
					26.24805802271453
				],
				[
					23.04707533701776,
					25.927959754144695
				],
				[
					22.086780531308705,
					25.287763217005477
				],
				[
					21.126485725599423,
					24.64756667986603
				],
				[
					20.486289188460205,
					24.327468411296195
				],
				[
					19.205896114181314,
					23.36717360558714
				],
				[
					18.565699577042096,
					23.04707533701753
				],
				[
					17.285306502763206,
					22.086780531308477
				],
				[
					16.645109965623988,
					21.446583994169032
				],
				[
					15.684815159914933,
					20.806387457029587
				],
				[
					15.044618622775488,
					20.16619091989037
				],
				[
					14.724520354205879,
					19.846092651320532
				],
				[
					14.084323817066434,
					19.525994382750923
				],
				[
					13.764225548496825,
					19.205896114181314
				],
				[
					13.12402901135738,
					18.56569957704187
				],
				[
					12.80393074278777,
					18.24560130847226
				],
				[
					12.483832474217934,
					17.925503039902424
				],
				[
					12.163734205648325,
					17.605404771332815
				],
				[
					11.843635937078716,
					17.285306502763206
				],
				[
					11.20343939993927,
					16.64510996562376
				],
				[
					10.883341131369434,
					16.004913428484315
				],
				[
					10.563242862799825,
					15.684815159914706
				],
				[
					10.563242862799825,
					15.364716891345097
				],
				[
					9.92304632566038,
					14.724520354205652
				],
				[
					9.60294805709077,
					14.404422085636043
				],
				[
					9.282849788520934,
					13.764225548496597
				],
				[
					8.962751519951325,
					13.44412727992676
				],
				[
					8.32255498281188,
					12.803930742787543
				],
				[
					8.002456714242271,
					12.163734205648097
				],
				[
					7.682358445672662,
					11.843635937078488
				],
				[
					7.362260177102826,
					11.203439399939043
				],
				[
					7.042161908533217,
					10.883341131369434
				],
				[
					6.401965371393771,
					10.243144594229989
				],
				[
					6.081867102824162,
					9.923046325660152
				],
				[
					5.441670565684717,
					9.602948057090543
				],
				[
					5.121572297115108,
					9.282849788520934
				],
				[
					4.801474028545499,
					8.642653251381489
				],
				[
					4.161277491406054,
					8.002456714242044
				],
				[
					3.5210809542666084,
					7.682358445672435
				],
				[
					2.8808844171273904,
					7.362260177102826
				],
				[
					2.240687879987945,
					7.042161908532989
				],
				[
					1.920589611418336,
					6.72206363996338
				],
				[
					1.6004913428484997,
					6.401965371393771
				],
				[
					1.2803930742788907,
					6.081867102823935
				],
				[
					0.6401965371394454,
					5.761768834254326
				],
				[
					0,
					5.441670565684717
				],
				[
					-0.320098268569609,
					5.121572297114881
				],
				[
					-0.640196537139218,
					4.801474028545272
				],
				[
					-1.6004913428482723,
					4.481375759975663
				],
				[
					-1.6004913428482723,
					4.161277491405826
				],
				[
					-1.9205896114181087,
					4.161277491405826
				],
				[
					-1.9205896114181087,
					3.8411792228362174
				],
				[
					-2.2406878799877177,
					3.8411792228362174
				],
				[
					-2.2406878799877177,
					3.5210809542666084
				],
				[
					-1.9205896114181087,
					3.8411792228362174
				],
				[
					-0.320098268569609,
					4.801474028545272
				],
				[
					0.9602948057090543,
					5.441670565684717
				],
				[
					1.920589611418336,
					5.761768834254326
				],
				[
					3.2009826856969994,
					6.401965371393771
				],
				[
					3.8411792228364448,
					6.72206363996338
				],
				[
					4.481375759975663,
					7.042161908532989
				],
				[
					5.121572297115108,
					8.002456714242044
				],
				[
					5.441670565684717,
					8.002456714242044
				],
				[
					6.401965371393771,
					8.962751519951098
				],
				[
					7.042161908533217,
					9.602948057090543
				],
				[
					7.682358445672662,
					10.243144594229989
				],
				[
					8.32255498281188,
					10.883341131369434
				],
				[
					8.642653251381716,
					11.523537668508652
				],
				[
					9.282849788520934,
					11.843635937078488
				],
				[
					9.60294805709077,
					12.163734205648097
				],
				[
					10.243144594230216,
					12.483832474217706
				],
				[
					10.883341131369434,
					13.124029011357152
				],
				[
					11.20343939993927,
					13.44412727992676
				],
				[
					12.163734205648325,
					13.764225548496597
				],
				[
					12.80393074278777,
					14.404422085636043
				],
				[
					13.444127279926988,
					15.04461862277526
				],
				[
					14.084323817066434,
					15.364716891345097
				],
				[
					14.724520354205879,
					16.004913428484315
				],
				[
					15.364716891345097,
					16.32501169705415
				],
				[
					16.004913428484542,
					16.96520823419337
				],
				[
					16.32501169705415,
					17.285306502763206
				],
				[
					16.965208234193597,
					17.925503039902424
				],
				[
					17.605404771333042,
					17.925503039902424
				],
				[
					17.92550303990265,
					17.925503039902424
				],
				[
					18.565699577042096,
					17.925503039902424
				],
				[
					18.885797845611705,
					18.24560130847226
				],
				[
					19.52599438275115,
					18.885797845611478
				],
				[
					19.84609265132076,
					18.885797845611478
				],
				[
					20.486289188460205,
					19.525994382750923
				],
				[
					20.806387457029814,
					19.525994382750923
				],
				[
					21.126485725599423,
					19.846092651320532
				],
				[
					21.44658399416926,
					20.16619091989037
				],
				[
					22.086780531308705,
					20.16619091989037
				],
				[
					22.406878799878314,
					20.486289188459978
				],
				[
					23.04707533701776,
					20.806387457029587
				],
				[
					23.367173605587368,
					20.806387457029587
				],
				[
					23.687271874157204,
					21.126485725599423
				],
				[
					24.327468411296422,
					21.446583994169032
				],
				[
					24.967664948435868,
					21.76668226273887
				],
				[
					25.287763217005477,
					21.76668226273887
				],
				[
					25.607861485575313,
					22.086780531308477
				],
				[
					26.24805802271453,
					22.086780531308477
				],
				[
					26.568156291284367,
					22.406878799878086
				],
				[
					27.52845109699342,
					22.726977068447923
				],
				[
					27.84854936556303,
					22.726977068447923
				],
				[
					28.16864763413264,
					23.04707533701753
				],
				[
					28.488745902702476,
					23.04707533701753
				],
				[
					28.808844171272085,
					23.36717360558714
				],
				[
					29.76913897698114,
					23.687271874156977
				],
				[
					30.08923724555075,
					23.687271874156977
				],
				[
					30.409335514120585,
					23.687271874156977
				],
				[
					30.729433782690194,
					23.687271874156977
				],
				[
					31.36963031982964,
					24.007370142726586
				],
				[
					31.689728588399248,
					24.007370142726586
				],
				[
					32.00982685696886,
					24.007370142726586
				],
				[
					32.32992512553869,
					24.007370142726586
				],
				[
					32.97012166267814,
					24.327468411296195
				],
				[
					33.29021993124775,
					24.64756667986603
				],
				[
					33.61031819981736,
					24.64756667986603
				],
				[
					33.93041646838719,
					24.96766494843564
				],
				[
					34.2505147369568,
					24.96766494843564
				],
				[
					34.89071127409625,
					25.607861485575086
				],
				[
					35.21080954266586,
					25.927959754144695
				],
				[
					35.53090781123569,
					25.927959754144695
				],
				[
					35.53090781123569,
					26.24805802271453
				],
				[
					35.8510060798053,
					26.56815629128414
				],
				[
					35.8510060798053,
					26.56815629128414
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 625,
			"versionNonce": 822244101,
			"isDeleted": false,
			"id": "5ZUD5n1chEVz4qrXAzYgd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 745.7424426962837,
			"y": 1020.9217140433672,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 17.143856479754504,
			"height": 31.49685260233946,
			"seed": 592904235,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.398694336738572
				],
				[
					0.398694336738572,
					-1.5947773469540607
				],
				[
					0.398694336738572,
					-3.189554693907894
				],
				[
					0.398694336738572,
					-4.385637704123383
				],
				[
					0.398694336738572,
					-7.575192398031049
				],
				[
					0.398694336738572,
					-9.16996974498511
				],
				[
					0.398694336738572,
					-10.366052755200371
				],
				[
					0.398694336738572,
					-11.56213576541586
				],
				[
					0.398694336738572,
					-13.954301785846837
				],
				[
					0.398694336738572,
					-15.150384796062099
				],
				[
					0.398694336738572,
					-16.346467806277587
				],
				[
					0.398694336738572,
					-16.745162143015932
				],
				[
					0.398694336738572,
					-17.94124515323142
				],
				[
					0.398694336738572,
					-18.339939489969993
				],
				[
					0.7973886734769167,
					-19.13732816344691
				],
				[
					0.7973886734769167,
					-20.333411173662398
				],
				[
					1.1960830102154887,
					-21.130799847139315
				],
				[
					1.1960830102154887,
					-21.52949418387766
				],
				[
					1.1960830102154887,
					-21.92818852061623
				],
				[
					1.5947773469540607,
					-22.725577194093148
				],
				[
					1.5947773469540607,
					-23.12427153083172
				],
				[
					1.5947773469540607,
					-23.522965867570065
				],
				[
					1.9934716836924053,
					-23.522965867570065
				],
				[
					1.9934716836924053,
					-23.921660204308637
				],
				[
					1.9934716836924053,
					-24.32035454104698
				],
				[
					1.9934716836924053,
					-24.719048877785553
				],
				[
					2.3921660204309774,
					-24.719048877785553
				],
				[
					2.3921660204309774,
					-25.117743214524126
				],
				[
					2.790860357169322,
					-25.51643755126247
				],
				[
					2.790860357169322,
					-25.915131888001042
				],
				[
					3.189554693907894,
					-25.915131888001042
				],
				[
					3.189554693907894,
					-26.313826224739387
				],
				[
					3.588249030646466,
					-26.313826224739387
				],
				[
					3.9869433673848107,
					-26.313826224739387
				],
				[
					4.385637704123383,
					-26.313826224739387
				],
				[
					4.784332040861727,
					-26.313826224739387
				],
				[
					5.581720714338871,
					-25.915131888001042
				],
				[
					7.176498061292705,
					-25.51643755126247
				],
				[
					8.372581071507966,
					-25.117743214524126
				],
				[
					9.967358418462027,
					-24.32035454104698
				],
				[
					11.163441428677515,
					-23.522965867570065
				],
				[
					11.960830102154205,
					-23.12427153083172
				],
				[
					13.156913112369693,
					-21.92818852061623
				],
				[
					13.95430178584661,
					-21.52949418387766
				],
				[
					15.150384796062099,
					-20.732105510400743
				],
				[
					15.54907913280067,
					-19.934716836923826
				],
				[
					16.74516214301616,
					-18.738633826708337
				],
				[
					17.143856479754504,
					-17.94124515323142
				],
				[
					17.143856479754504,
					-17.542550816493076
				],
				[
					17.143856479754504,
					-16.745162143015932
				],
				[
					17.143856479754504,
					-15.947773469539015
				],
				[
					15.947773469539015,
					-13.555607449108265
				],
				[
					14.751690459323754,
					-13.156913112369693
				],
				[
					13.95430178584661,
					-12.359524438892777
				],
				[
					12.758218775631349,
					-11.960830102154432
				],
				[
					11.163441428677515,
					-11.56213576541586
				],
				[
					9.967358418462027,
					-11.56213576541586
				],
				[
					8.771275408246538,
					-11.163441428677288
				],
				[
					7.575192398031049,
					-11.163441428677288
				],
				[
					5.980415051077216,
					-11.163441428677288
				],
				[
					4.784332040861727,
					-10.764747091938943
				],
				[
					3.9869433673848107,
					-10.764747091938943
				],
				[
					3.189554693907894,
					-10.764747091938943
				],
				[
					2.790860357169322,
					-10.764747091938943
				],
				[
					3.9869433673848107,
					-10.366052755200371
				],
				[
					5.183026377600299,
					-9.967358418462027
				],
				[
					6.777803724554133,
					-9.568664081723455
				],
				[
					7.973886734769621,
					-8.771275408246538
				],
				[
					8.771275408246538,
					-7.973886734769621
				],
				[
					10.366052755200371,
					-6.777803724554133
				],
				[
					11.163441428677515,
					-5.581720714338644
				],
				[
					11.960830102154205,
					-4.784332040861727
				],
				[
					12.359524438892777,
					-3.189554693907894
				],
				[
					13.156913112369693,
					-1.9934716836924053
				],
				[
					13.555607449108265,
					-0.797388673477144
				],
				[
					13.95430178584661,
					0.39869433673834465
				],
				[
					14.352996122585182,
					0.7973886734769167
				],
				[
					14.751690459323754,
					1.9934716836924053
				],
				[
					14.751690459323754,
					2.39216602043075
				],
				[
					14.751690459323754,
					2.790860357169322
				],
				[
					14.751690459323754,
					3.5882490306462387
				],
				[
					14.751690459323754,
					3.9869433673845833
				],
				[
					14.751690459323754,
					4.385637704123155
				],
				[
					14.751690459323754,
					5.183026377600072
				],
				[
					14.751690459323754,
					5.183026377600072
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 565,
			"versionNonce": 752217035,
			"isDeleted": false,
			"id": "MW4kan_wZarOapw1kd2nM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 744.9450540228067,
			"y": 1014.94129899229,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 1.1960830102154887,
			"height": 15.549079132800443,
			"seed": 784343179,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.398694336738572,
					0.7973886734769167
				],
				[
					0.398694336738572,
					1.1960830102154887
				],
				[
					0.398694336738572,
					1.9934716836924053
				],
				[
					0.7973886734769167,
					2.790860357169322
				],
				[
					1.1960830102154887,
					3.9869433673848107
				],
				[
					1.1960830102154887,
					4.784332040861727
				],
				[
					1.1960830102154887,
					6.379109387815561
				],
				[
					1.1960830102154887,
					6.777803724554133
				],
				[
					1.1960830102154887,
					7.575192398031049
				],
				[
					1.1960830102154887,
					7.973886734769621
				],
				[
					1.1960830102154887,
					8.372581071507966
				],
				[
					1.1960830102154887,
					9.169969744984883
				],
				[
					1.1960830102154887,
					9.568664081723455
				],
				[
					1.1960830102154887,
					9.9673584184618
				],
				[
					1.1960830102154887,
					10.366052755200371
				],
				[
					1.1960830102154887,
					10.764747091938716
				],
				[
					1.1960830102154887,
					11.56213576541586
				],
				[
					1.1960830102154887,
					11.960830102154205
				],
				[
					1.1960830102154887,
					12.758218775631121
				],
				[
					1.1960830102154887,
					13.156913112369693
				],
				[
					1.1960830102154887,
					13.95430178584661
				],
				[
					1.1960830102154887,
					14.352996122585182
				],
				[
					1.1960830102154887,
					15.150384796062099
				],
				[
					1.1960830102154887,
					15.549079132800443
				],
				[
					1.1960830102154887,
					15.549079132800443
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 541,
			"versionNonce": 614976101,
			"isDeleted": false,
			"id": "Iq1wwCc-B4sTIiE9vKuiX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 973.4555228347633,
			"y": 975.1651982025265,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 392378219,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
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
			"type": "text",
			"version": 663,
			"versionNonce": 844905067,
			"isDeleted": false,
			"id": "cUUmOXRG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 917.1573772064735,
			"y": 1012.4126767780459,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 238.9925079345703,
			"height": 40,
			"seed": 2094091691,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We want to rotate around an\naxis x/y/z by an angle a",
			"rawText": "We want to rotate around an\naxis x/y/z by an angle a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We want to rotate around an\naxis x/y/z by an angle a",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 729,
			"versionNonce": 1550529989,
			"isDeleted": false,
			"id": "rmOddWat",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 927.8797864126243,
			"y": 1106.4024088839788,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 232,
			"height": 63,
			"seed": 44427,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b0f289b6a6940e6c74e91025eddcab2517b18f90",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 650,
			"versionNonce": 1532998923,
			"isDeleted": false,
			"id": "bu87mDQR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 929.7432988476112,
			"y": 1189.689395142038,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 231,
			"height": 63,
			"seed": 61568,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "01d52910c5c0f8ff24dcaf4ff2bcc516fefbc10f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 639,
			"versionNonce": 1399469349,
			"isDeleted": false,
			"id": "IFcQervT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 667.6343319727107,
			"y": 1194.788598382327,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 230,
			"height": 63,
			"seed": 73703,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "024eefd71a9227fa8e33bf6e93c24df21f8575ba",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 666,
			"versionNonce": 391830443,
			"isDeleted": false,
			"id": "XEnBLgpo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 100.39751844423873,
			"y": 399.6092390907985,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 254.43507385253906,
			"height": 105.06739359777504,
			"seed": 494616299,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"fontSize": 14.008985813036672,
			"fontFamily": 1,
			"text": "We want to combine linear\nand non-linear transformations\ninto one transformation that \nway we can composite them using\nmatrix multiplication to make it more\ncompact!",
			"rawText": "We want to combine linear\nand non-linear transformations\ninto one transformation that \nway we can composite them using\nmatrix multiplication to make it more\ncompact!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We want to combine linear\nand non-linear transformations\ninto one transformation that \nway we can composite them using\nmatrix multiplication to make it more\ncompact!",
			"lineHeight": 1.25,
			"baseline": 100
		},
		{
			"type": "arrow",
			"version": 839,
			"versionNonce": 992648699,
			"isDeleted": false,
			"id": "ty8Yo_-5S_oMuYzl7q6Ea",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 61.86910653253768,
			"y": 393.21007183238646,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.483145680950237,
			"height": 169.3555702334187,
			"seed": 2084621323,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702995800937,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "N5kfUjMxrLrOI-DuLdj9K",
				"gap": 3.4964494948933122,
				"focus": -0.0292895463415269
			},
			"endBinding": {
				"elementId": "XXqDLL9d",
				"gap": 1.0617802730318573,
				"focus": -0.01705477665395594
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
					1.483145680950237,
					169.3555702334187
				]
			]
		},
		{
			"type": "ellipse",
			"version": 489,
			"versionNonce": 41430603,
			"isDeleted": false,
			"id": "XXqDLL9d",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -79.30557262446064,
			"y": 563.6109314967001,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 291.5640342264489,
			"height": 143.58644557725165,
			"seed": 1569927627,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "ty8Yo_-5S_oMuYzl7q6Ea",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "uc4txuvp"
				},
				{
					"id": "WKvV5NchnfD0fO2xeb5_6",
					"type": "arrow"
				}
			],
			"updated": 1702760726447,
			"link": "[[Subspaces]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 258,
			"versionNonce": 589361125,
			"isDeleted": false,
			"id": "uc4txuvp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2.175146509609121,
			"y": 615.638679608252,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 137.1362762451172,
			"height": 40,
			"seed": 353581419,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Using\nAffine subspaces!",
			"rawText": "Using\nAffine subspaces!",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "XXqDLL9d",
			"originalText": "Using\nAffine subspaces!",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 569,
			"versionNonce": 1938442363,
			"isDeleted": false,
			"id": "1K5pdzJR8SBMFFQCsADaO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -557.9684873969918,
			"y": 464.8011802468759,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0.13473555264090464,
			"height": 98.67047916414754,
			"seed": 1653555275,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702995800938,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Mb19cauT1lXSa87jjqcHz",
				"gap": 2.4347063554684496,
				"focus": -0.00468479258896047
			},
			"endBinding": {
				"elementId": "5qzql3zp",
				"gap": 5.795831057964875,
				"focus": -0.0059571758410655404
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
					-0.13473555264090464,
					98.67047916414754
				]
			]
		},
		{
			"type": "ellipse",
			"version": 582,
			"versionNonce": 1269017413,
			"isDeleted": false,
			"id": "5qzql3zp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -703.1227380654116,
			"y": 569.266508757882,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 291.5640342264489,
			"height": 143.58644557725165,
			"seed": 294405925,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "BESVIZlk"
				},
				{
					"id": "1K5pdzJR8SBMFFQCsADaO",
					"type": "arrow"
				},
				{
					"id": "iX6BfBPTLwqImJ3bYLKgA",
					"type": "arrow"
				},
				{
					"id": "Y8We6sbL_V8wIlpCzbcm4",
					"type": "arrow"
				}
			],
			"updated": 1702760726447,
			"link": "[[Subspaces]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 360,
			"versionNonce": 1915967371,
			"isDeleted": false,
			"id": "BESVIZlk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -642.1123452147202,
			"y": 621.2942568694339,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#deede1",
			"width": 169.3763427734375,
			"height": 40,
			"seed": 1495407237,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Using\nProjective subspaces!",
			"rawText": "Using\nProjective subspaces!",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "5qzql3zp",
			"originalText": "Using\nProjective subspaces!",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 841,
			"versionNonce": 300069083,
			"isDeleted": false,
			"id": "iX6BfBPTLwqImJ3bYLKgA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -409.3653357062954,
			"y": 643.173189677834,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 82.132082059715,
			"height": 0.600548272536571,
			"seed": 60104197,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702995800939,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "5qzql3zp",
				"gap": 2.2536793982304744,
				"focus": 0.014365578293464347
			},
			"endBinding": {
				"elementId": "Q9UofkTN",
				"gap": 4.462232242401797,
				"focus": 0.01830902162201722
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
					82.132082059715,
					0.600548272536571
				]
			]
		},
		{
			"type": "rectangle",
			"version": 512,
			"versionNonce": 2007834026,
			"isDeleted": false,
			"id": "Q9UofkTN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -322.77102140417855,
			"y": 572.1187642955032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 187.43066958721715,
			"height": 147.47083140111,
			"seed": 1504526693,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "FZ5mjH8J"
				},
				{
					"id": "_mJx42VVx5762e0vd2fy6",
					"type": "arrow"
				},
				{
					"id": "iX6BfBPTLwqImJ3bYLKgA",
					"type": "arrow"
				},
				{
					"id": "kRXxgchF7_0tSG5dvTZvu",
					"type": "arrow"
				}
			],
			"updated": 1702813780271,
			"link": "[[Subspaces]]",
			"locked": false
		},
		{
			"type": "text",
			"version": 471,
			"versionNonce": 365649413,
			"isDeleted": false,
			"id": "FZ5mjH8J",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -277.20777859055045,
			"y": 625.8541799960582,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 96.30418395996094,
			"height": 40,
			"seed": 588188805,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Homogeneous\nCoordinates",
			"rawText": "Homogeneous\nCoordinates",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Q9UofkTN",
			"originalText": "Homogeneous\nCoordinates",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 1307,
			"versionNonce": 40999739,
			"isDeleted": false,
			"id": "WKvV5NchnfD0fO2xeb5_6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 61.48000788444694,
			"y": 710.6475067465001,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 1.6631419527216877,
			"height": 107.11199561330614,
			"seed": 1295606411,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702995800937,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XXqDLL9d",
				"gap": 3.4923142537030714,
				"focus": 0.026258460291645455
			},
			"endBinding": {
				"elementId": "iDfXTaAH",
				"gap": 3.009629659829102,
				"focus": -0.03273625669943879
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
					-1.6631419527216877,
					107.11199561330614
				]
			]
		},
		{
			"type": "arrow",
			"version": 1345,
			"versionNonce": 411474843,
			"isDeleted": false,
			"id": "_mJx42VVx5762e0vd2fy6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -229.45391496833457,
			"y": 726.2903606816947,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 97.23830545714861,
			"height": 206.37777287702886,
			"seed": 1526644325,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702995800939,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Q9UofkTN",
				"gap": 6.700764985081491,
				"focus": 0.02691900410614742
			},
			"endBinding": {
				"elementId": "iDfXTaAH",
				"focus": -0.38405425041260016,
				"gap": 3.2841297115055568
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
					5.169376606037304,
					190.88972874930835
				],
				[
					97.23830545714861,
					206.37777287702886
				]
			]
		},
		{
			"type": "text",
			"version": 230,
			"versionNonce": 452648811,
			"isDeleted": false,
			"id": "MFBs87UN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -23.208699960432227,
			"y": 825.4205599591218,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 178.41639709472656,
			"height": 20,
			"seed": 1187300869,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Affine transformations",
			"rawText": "Affine transformations",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Affine transformations",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 551,
			"versionNonce": 1312121029,
			"isDeleted": false,
			"id": "EM7IOfRV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -87.40421682694648,
			"y": 851.1867591357334,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 322.19049072265625,
			"height": 84.0712190399936,
			"seed": 604788261,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"fontSize": 11.209495871999145,
			"fontFamily": 1,
			"text": "We can now do both transformations all within one matrix!\n\nWe define out coordinates in\nhomogeneous coordinates first.\n\n",
			"rawText": "We can now do both transformations all within one matrix!\n\nWe define out coordinates in\nhomogeneous coordinates first.\n\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can now do both transformations all within one matrix!\n\nWe define out coordinates in\nhomogeneous coordinates first.\n\n",
			"lineHeight": 1.25,
			"baseline": 80
		},
		{
			"type": "freedraw",
			"version": 360,
			"versionNonce": 1658960395,
			"isDeleted": false,
			"id": "SsFYhVjIievyld5isq6Z0",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 95.79096140823282,
			"y": 874.3136205656918,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 6.785804242267604,
			"height": 38.79218091829648,
			"seed": 1719761669,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.11309673737113148
				],
				[
					0,
					0.33929021211339444
				],
				[
					-0.11309673737113148,
					0.6785804242267889
				],
				[
					-0.3392902121133852,
					1.1309673737113148
				],
				[
					-0.3392902121133852,
					1.2440641110824462
				],
				[
					-0.6785804242267613,
					1.9226445353091617
				],
				[
					-1.0178706363401466,
					2.6012249595359505
				],
				[
					-1.470257585824654,
					3.732192333247192
				],
				[
					-1.6964510605669079,
					4.297676020102849
				],
				[
					-2.1488380100514153,
					5.089353181700696
				],
				[
					-2.4881282221647916,
					5.881030343298616
				],
				[
					-2.7143216969070454,
					6.559610767525405
				],
				[
					-2.940515171649299,
					7.464384666494384
				],
				[
					-3.0536119090204306,
					7.916771615978909
				],
				[
					-3.1667086463915526,
					8.708448777576756
				],
				[
					-3.3929021211338064,
					9.273932464432415
				],
				[
					-3.3929021211338064,
					9.952512888659202
				],
				[
					-3.3929021211338064,
					10.517996575514786
				],
				[
					-3.3929021211338064,
					11.309673737112707
				],
				[
					-3.3929021211338064,
					11.988254161339423
				],
				[
					-3.3929021211338064,
					12.66683458556621
				],
				[
					-3.3929021211338064,
					13.458511747164131
				],
				[
					-3.3929021211338064,
					14.137092171390847
				],
				[
					-3.3929021211338064,
					14.815672595617636
				],
				[
					-3.3929021211338064,
					15.833543231957746
				],
				[
					-3.3929021211338064,
					16.625220393555665
				],
				[
					-3.3929021211338064,
					17.529994292524645
				],
				[
					-3.3929021211338064,
					18.321671454122566
				],
				[
					-3.3929021211338064,
					19.11334861572041
				],
				[
					-3.3929021211338064,
					20.131219252060596
				],
				[
					-3.3929021211338064,
					20.69670293891618
				],
				[
					-3.3929021211338064,
					21.60147683788523
				],
				[
					-3.3929021211338064,
					22.393153999483076
				],
				[
					-3.3929021211338064,
					23.524121373194394
				],
				[
					-3.3929021211338064,
					24.089605060049976
				],
				[
					-3.505998858504929,
					25.22057243376129
				],
				[
					-3.505998858504929,
					26.12534633273027
				],
				[
					-3.505998858504929,
					26.91702349432819
				],
				[
					-3.3929021211338064,
					27.59560391855498
				],
				[
					-3.279805383762675,
					28.16108760541056
				],
				[
					-3.0536119090204306,
					28.83966802963735
				],
				[
					-2.8274184342781767,
					29.178958241750745
				],
				[
					-2.601224959535923,
					30.083732140719725
				],
				[
					-2.375031484793669,
					30.53611909020425
				],
				[
					-2.2619347474225378,
					30.875409302317646
				],
				[
					-2.035741272680284,
					31.3277962518021
				],
				[
					-1.9226445353091617,
					31.667086463915492
				],
				[
					-1.6964510605669079,
					32.006376676028886
				],
				[
					-1.470257585824654,
					32.34566688814228
				],
				[
					-1.3571608484535227,
					32.68495710025567
				],
				[
					-1.2440641110824002,
					32.91115057499794
				],
				[
					-0.7916771615978928,
					33.47663426185352
				],
				[
					-0.565483686855639,
					34.042117948709176
				],
				[
					-0.11309673737113148,
					34.38140816082257
				],
				[
					0.11309673737112229,
					34.60760163556483
				],
				[
					0.33929021211337607,
					35.05998858504929
				],
				[
					0.5654836868556299,
					35.28618205979155
				],
				[
					0.7916771615978836,
					35.51237553453382
				],
				[
					1.0178706363401373,
					35.85166574664721
				],
				[
					1.2440641110823911,
					36.077859221389474
				],
				[
					1.470257585824645,
					36.304052696131734
				],
				[
					1.5833543231957672,
					36.530246170874
				],
				[
					1.9226445353091524,
					36.75643964561619
				],
				[
					2.0357412726802746,
					36.86953638298732
				],
				[
					2.1488380100514064,
					37.09572985772958
				],
				[
					2.37503148479366,
					37.32192333247185
				],
				[
					2.4881282221647822,
					37.43502006984298
				],
				[
					2.6012249595359136,
					37.66121354458524
				],
				[
					2.714321696907036,
					37.887407019327505
				],
				[
					2.94051517164929,
					38.000503756698635
				],
				[
					3.0536119090204212,
					38.226697231440895
				],
				[
					3.1667086463915437,
					38.452890706183084
				],
				[
					3.1667086463915437,
					38.56598744355422
				],
				[
					3.279805383762675,
					38.67908418092535
				],
				[
					3.279805383762675,
					38.79218091829648
				],
				[
					3.279805383762675,
					38.79218091829648
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 299,
			"versionNonce": 11993125,
			"isDeleted": false,
			"id": "FS7tJE_GqWBvrh6ZXE0Wz",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 116.05756091738323,
			"y": 874.0541255672042,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 3.732192333247192,
			"height": 36.41714943350279,
			"seed": 1033848293,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.11309673737111312,
					0.2261934747421895
				],
				[
					0.33929021211337607,
					0.6785804242267154
				],
				[
					0.6785804242267521,
					1.2440641110823727
				],
				[
					1.0178706363401282,
					2.1488380100513513
				],
				[
					1.1309673737112598,
					2.4881282221647454
				],
				[
					1.6964510605668988,
					3.6190955958760602
				],
				[
					2.0357412726802746,
					4.523869494845039
				],
				[
					2.2619347474225378,
					5.428643393814017
				],
				[
					2.375031484793651,
					6.672707504896463
				],
				[
					2.6012249595359136,
					8.934642252318946
				],
				[
					2.6012249595359136,
					10.404899838143654
				],
				[
					2.6012249595359136,
					12.440641110823874
				],
				[
					2.6012249595359136,
					13.910898696648584
				],
				[
					2.6012249595359136,
					15.041866070359825
				],
				[
					2.6012249595359136,
					16.39902691881333
				],
				[
					2.6012249595359136,
					17.41689755515351
				],
				[
					2.6012249595359136,
					18.774058403607018
				],
				[
					2.375031484793651,
					20.01812251468939
				],
				[
					2.2619347474225378,
					21.035993151029572
				],
				[
					2.1488380100514064,
					22.053863787369682
				],
				[
					2.1488380100514064,
					22.84554094896753
				],
				[
					2.0357412726802746,
					23.63721811056545
				],
				[
					1.9226445353091433,
					24.54199200953443
				],
				[
					1.8095477979380301,
					25.44676590850348
				],
				[
					1.6964510605668988,
					26.12534633273027
				],
				[
					1.5833543231957672,
					26.690830019585853
				],
				[
					1.3571608484535227,
					27.25631370644151
				],
				[
					1.2440641110823911,
					27.9348941306683
				],
				[
					1.1309673737112598,
					28.726571292266147
				],
				[
					1.0178706363401282,
					29.292054979121804
				],
				[
					0.9047738989690151,
					29.857538665977387
				],
				[
					0.7916771615978836,
					30.309925615461914
				],
				[
					0.5654836868556207,
					30.87540930231757
				],
				[
					0.45238694948450753,
					31.553989726544287
				],
				[
					0.22619347474224458,
					32.006376676028815
				],
				[
					0.11309673737111312,
					32.458763625513335
				],
				[
					0,
					32.91115057499786
				],
				[
					-0.11309673737113148,
					33.25044078711126
				],
				[
					-0.22619347474226295,
					33.58973099922458
				],
				[
					-0.22619347474226295,
					33.815924473966845
				],
				[
					-0.22619347474226295,
					34.042117948709105
				],
				[
					-0.22619347474226295,
					34.3814081608225
				],
				[
					-0.22619347474226295,
					34.49450489819363
				],
				[
					-0.22619347474226295,
					34.72069837293589
				],
				[
					-0.22619347474226295,
					34.94689184767816
				],
				[
					-0.22619347474226295,
					35.05998858504929
				],
				[
					-0.22619347474226295,
					35.28618205979148
				],
				[
					-0.22619347474226295,
					35.39927879716261
				],
				[
					-0.22619347474226295,
					35.51237553453374
				],
				[
					-0.33929021211339444,
					35.625472271904876
				],
				[
					-0.33929021211339444,
					35.738569009276006
				],
				[
					-0.45238694948450753,
					35.738569009276006
				],
				[
					-0.45238694948450753,
					35.851665746647136
				],
				[
					-0.565483686855639,
					35.964762484018266
				],
				[
					-0.6785804242267705,
					36.077859221389396
				],
				[
					-0.6785804242267705,
					36.19095595876053
				],
				[
					-0.7916771615978836,
					36.30405269613166
				],
				[
					-0.9047738989690151,
					36.30405269613166
				],
				[
					-1.0178706363401466,
					36.41714943350279
				],
				[
					-1.130967373711278,
					36.41714943350279
				],
				[
					-1.130967373711278,
					36.41714943350279
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 266,
			"versionNonce": 1247035563,
			"isDeleted": false,
			"id": "2cikVyTPJBdnkPlGS1Rfe",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 123.6350423212487,
			"y": 890.3400557486465,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 6.107223818040861,
			"height": 0.6785804242267889,
			"seed": 1750775429,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.22619347474226295,
					0
				],
				[
					0.565483686855639,
					0.22619347474226295
				],
				[
					1.130967373711278,
					0.33929021211339444
				],
				[
					1.470257585824654,
					0.4523869494845259
				],
				[
					2.375031484793669,
					0.6785804242267889
				],
				[
					2.7143216969070454,
					0.6785804242267889
				],
				[
					3.1667086463915526,
					0.6785804242267889
				],
				[
					3.732192333247192,
					0.6785804242267889
				],
				[
					3.8452890706183234,
					0.6785804242267889
				],
				[
					4.071482545360568,
					0.6785804242267889
				],
				[
					4.1845792827317,
					0.6785804242267889
				],
				[
					4.410772757473944,
					0.6785804242267889
				],
				[
					4.5238694948450755,
					0.6785804242267889
				],
				[
					4.636966232216207,
					0.6785804242267889
				],
				[
					4.750062969587338,
					0.6785804242267889
				],
				[
					4.863159706958451,
					0.6785804242267889
				],
				[
					4.976256444329583,
					0.6785804242267889
				],
				[
					5.089353181700714,
					0.6785804242267889
				],
				[
					5.202449919071846,
					0.6785804242267889
				],
				[
					5.315546656442959,
					0.6785804242267889
				],
				[
					5.428643393814091,
					0.6785804242267889
				],
				[
					5.541740131185222,
					0.6785804242267889
				],
				[
					5.6548368685563535,
					0.6785804242267889
				],
				[
					5.767933605927467,
					0.6785804242267889
				],
				[
					5.881030343298598,
					0.6785804242267889
				],
				[
					5.994127080669729,
					0.6785804242267889
				],
				[
					6.107223818040861,
					0.5654836868556574
				],
				[
					6.107223818040861,
					0.5654836868556574
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 265,
			"versionNonce": 1687008133,
			"isDeleted": false,
			"id": "466GbSeYQzvv93t5PWHGn",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 123.6350423212487,
			"y": 894.5246350313781,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 7.2381911917521204,
			"height": 0.5654836868556574,
			"seed": 916836293,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.11309673737113148,
					0
				],
				[
					0.22619347474226295,
					0
				],
				[
					0.45238694948450753,
					0
				],
				[
					0.791677161597902,
					0
				],
				[
					1.2440641110824096,
					0.11309673737113148
				],
				[
					1.8095477979380301,
					0.22619347474226295
				],
				[
					2.2619347474225378,
					0.22619347474226295
				],
				[
					2.7143216969070454,
					0.33929021211339444
				],
				[
					3.0536119090204212,
					0.33929021211339444
				],
				[
					3.6190955958760602,
					0.4523869494845259
				],
				[
					4.071482545360568,
					0.4523869494845259
				],
				[
					4.410772757473944,
					0.5654836868556574
				],
				[
					4.750062969587338,
					0.5654836868556574
				],
				[
					4.976256444329583,
					0.5654836868556574
				],
				[
					5.428643393814091,
					0.5654836868556574
				],
				[
					5.6548368685563535,
					0.5654836868556574
				],
				[
					5.881030343298598,
					0.5654836868556574
				],
				[
					6.107223818040861,
					0.5654836868556574
				],
				[
					6.333417292783105,
					0.5654836868556574
				],
				[
					6.55961076752535,
					0.5654836868556574
				],
				[
					6.672707504896482,
					0.5654836868556574
				],
				[
					6.785804242267613,
					0.5654836868556574
				],
				[
					6.898900979638745,
					0.5654836868556574
				],
				[
					7.011997717009858,
					0.5654836868556574
				],
				[
					7.1250944543809895,
					0.5654836868556574
				],
				[
					7.2381911917521204,
					0.5654836868556574
				],
				[
					7.2381911917521204,
					0.5654836868556574
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 418,
			"versionNonce": 989655883,
			"isDeleted": false,
			"id": "YUqpEDrqXy6qjsC1P5q0z",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 140.40398709779814,
			"y": 873.4886418803486,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 7.2381911917521204,
			"height": 51.23282202912043,
			"seed": 1851864485,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.5654836868556207,
					-0.11309673737113148
				],
				[
					-0.9047738989690151,
					-0.11309673737113148
				],
				[
					-1.2440641110823911,
					-0.11309673737113148
				],
				[
					-1.809547797938012,
					-0.11309673737113148
				],
				[
					-2.1488380100514064,
					-0.22619347474226295
				],
				[
					-2.7143216969070267,
					-0.33929021211339444
				],
				[
					-3.0536119090204212,
					-0.33929021211339444
				],
				[
					-3.2798053837626657,
					-0.33929021211339444
				],
				[
					-3.619095595876042,
					-0.33929021211339444
				],
				[
					-3.7321923332471734,
					-0.33929021211339444
				],
				[
					-3.8452890706183047,
					-0.33929021211339444
				],
				[
					-3.9583858079894365,
					-0.33929021211339444
				],
				[
					-4.184579282731681,
					-0.22619347474226295
				],
				[
					-4.297676020102813,
					-0.22619347474226295
				],
				[
					-4.410772757473944,
					-0.11309673737113148
				],
				[
					-4.523869494845057,
					0
				],
				[
					-4.636966232216189,
					0
				],
				[
					-4.75006296958732,
					0.11309673737113148
				],
				[
					-4.863159706958451,
					0.11309673737113148
				],
				[
					-4.9762564443295645,
					0.22619347474226295
				],
				[
					-4.9762564443295645,
					0.33929021211339444
				],
				[
					-5.089353181700696,
					0.33929021211339444
				],
				[
					-5.089353181700696,
					0.4523869494845259
				],
				[
					-5.089353181700696,
					0.5654836868556574
				],
				[
					-5.089353181700696,
					0.7916771615978468
				],
				[
					-5.089353181700696,
					1.1309673737112413
				],
				[
					-5.089353181700696,
					1.4702575858246358
				],
				[
					-5.089353181700696,
					1.8095477979380301
				],
				[
					-5.089353181700696,
					2.261934747422556
				],
				[
					-5.089353181700696,
					2.601224959535877
				],
				[
					-4.9762564443295645,
					3.1667086463915344
				],
				[
					-4.863159706958451,
					3.6190955958760602
				],
				[
					-4.75006296958732,
					4.0714825453605865
				],
				[
					-4.75006296958732,
					4.63696623221617
				],
				[
					-4.636966232216189,
					5.202449919071827
				],
				[
					-4.636966232216189,
					5.767933605927485
				],
				[
					-4.523869494845057,
					6.5596107675253315
				],
				[
					-4.523869494845057,
					7.2381911917521204
				],
				[
					-4.523869494845057,
					7.916771615978836
				],
				[
					-4.523869494845057,
					8.482255302834494
				],
				[
					-4.523869494845057,
					9.273932464432415
				],
				[
					-4.523869494845057,
					10.06560962603026
				],
				[
					-4.636966232216189,
					10.857286787628182
				],
				[
					-4.863159706958451,
					11.648963949226028
				],
				[
					-4.9762564443295645,
					12.327544373452817
				],
				[
					-5.089353181700696,
					13.119221535050663
				],
				[
					-5.315546656442959,
					13.797801959277452
				],
				[
					-5.428643393814072,
					14.589479120875373
				],
				[
					-5.541740131185204,
					15.154962807730957
				],
				[
					-5.654836868556335,
					15.946639969328878
				],
				[
					-5.654836868556335,
					16.39902691881333
				],
				[
					-5.654836868556335,
					17.077607343040118
				],
				[
					-5.767933605927448,
					17.75618776726691
				],
				[
					-5.767933605927448,
					18.32167145412249
				],
				[
					-5.767933605927448,
					18.887155140978148
				],
				[
					-5.767933605927448,
					19.56573556520494
				],
				[
					-5.88103034329858,
					20.01812251468939
				],
				[
					-5.88103034329858,
					20.470509464173915
				],
				[
					-5.88103034329858,
					21.035993151029572
				],
				[
					-5.88103034329858,
					21.82767031262742
				],
				[
					-5.88103034329858,
					22.280057262111946
				],
				[
					-5.88103034329858,
					22.845540948967603
				],
				[
					-5.88103034329858,
					23.411024635823185
				],
				[
					-5.88103034329858,
					23.976508322678846
				],
				[
					-5.88103034329858,
					24.42889527216337
				],
				[
					-5.88103034329858,
					24.994378959019027
				],
				[
					-5.88103034329858,
					25.559862645874613
				],
				[
					-5.88103034329858,
					26.12534633273027
				],
				[
					-5.88103034329858,
					26.690830019585928
				],
				[
					-5.88103034329858,
					27.030120231699247
				],
				[
					-5.994127080669712,
					27.482507181183774
				],
				[
					-5.994127080669712,
					27.821797393297167
				],
				[
					-5.994127080669712,
					28.04799086803943
				],
				[
					-5.994127080669712,
					28.387281080152825
				],
				[
					-5.994127080669712,
					28.613474554895088
				],
				[
					-5.994127080669712,
					29.06586150437954
				],
				[
					-5.994127080669712,
					29.405151716492934
				],
				[
					-5.994127080669712,
					29.744441928606328
				],
				[
					-5.994127080669712,
					30.083732140719725
				],
				[
					-5.994127080669712,
					30.423022352833044
				],
				[
					-5.994127080669712,
					30.87540930231757
				],
				[
					-5.994127080669712,
					31.214699514430965
				],
				[
					-5.994127080669712,
					31.55398972654436
				],
				[
					-5.88103034329858,
					32.006376676028886
				],
				[
					-5.88103034329858,
					32.458763625513335
				],
				[
					-5.88103034329858,
					32.91115057499786
				],
				[
					-5.88103034329858,
					33.36353752448239
				],
				[
					-5.767933605927448,
					33.702827736595786
				],
				[
					-5.767933605927448,
					34.268311423451365
				],
				[
					-5.654836868556335,
					34.72069837293589
				],
				[
					-5.654836868556335,
					35.17308532242042
				],
				[
					-5.654836868556335,
					35.62547227190495
				],
				[
					-5.654836868556335,
					36.077859221389396
				],
				[
					-5.654836868556335,
					36.41714943350279
				],
				[
					-5.654836868556335,
					36.98263312035845
				],
				[
					-5.541740131185204,
					37.4350200698429
				],
				[
					-5.541740131185204,
					38.00050375669856
				],
				[
					-5.541740131185204,
					38.56598744355422
				],
				[
					-5.541740131185204,
					39.4707613425232
				],
				[
					-5.541740131185204,
					40.149341766749984
				],
				[
					-5.541740131185204,
					40.82792219097677
				],
				[
					-5.541740131185204,
					41.61959935257462
				],
				[
					-5.541740131185204,
					42.41127651417254
				],
				[
					-5.541740131185204,
					43.08985693839926
				],
				[
					-5.541740131185204,
					43.768437362626045
				],
				[
					-5.541740131185204,
					44.67321126159502
				],
				[
					-5.541740131185204,
					45.23869494845068
				],
				[
					-5.541740131185204,
					45.91727537267747
				],
				[
					-5.541740131185204,
					46.48275905953305
				],
				[
					-5.654836868556335,
					47.04824274638871
				],
				[
					-5.654836868556335,
					47.726823170615496
				],
				[
					-5.654836868556335,
					48.06611338272882
				],
				[
					-5.654836868556335,
					48.40540359484221
				],
				[
					-5.767933605927448,
					48.74469380695561
				],
				[
					-5.767933605927448,
					48.97088728169787
				],
				[
					-5.767933605927448,
					49.31017749381127
				],
				[
					-5.767933605927448,
					49.53637096855353
				],
				[
					-5.767933605927448,
					49.762564443295716
				],
				[
					-5.767933605927448,
					49.98875791803798
				],
				[
					-5.767933605927448,
					50.21495139278024
				],
				[
					-5.767933605927448,
					50.32804813015138
				],
				[
					-5.767933605927448,
					50.44114486752251
				],
				[
					-5.767933605927448,
					50.66733834226477
				],
				[
					-5.315546656442959,
					50.89353181700704
				],
				[
					-4.9762564443295645,
					50.89353181700704
				],
				[
					-4.75006296958732,
					50.7804350796359
				],
				[
					-4.410772757473944,
					50.7804350796359
				],
				[
					-4.071482545360549,
					50.66733834226477
				],
				[
					-3.7321923332471734,
					50.55424160489364
				],
				[
					-3.2798053837626657,
					50.55424160489364
				],
				[
					-3.1667086463915344,
					50.55424160489364
				],
				[
					-2.6012249595359136,
					50.55424160489364
				],
				[
					-2.1488380100514064,
					50.55424160489364
				],
				[
					-1.809547797938012,
					50.55424160489364
				],
				[
					-1.3571608484535227,
					50.55424160489364
				],
				[
					-1.0178706363401282,
					50.55424160489364
				],
				[
					-0.6785804242267521,
					50.55424160489364
				],
				[
					-0.5654836868556207,
					50.55424160489364
				],
				[
					-0.33929021211337607,
					50.55424160489364
				],
				[
					-0.22619347474224458,
					50.44114486752251
				],
				[
					0,
					50.44114486752251
				],
				[
					0.11309673737113148,
					50.44114486752251
				],
				[
					0.33929021211339444,
					50.32804813015138
				],
				[
					0.45238694948450753,
					50.32804813015138
				],
				[
					0.6785804242267705,
					50.32804813015138
				],
				[
					0.9047738989690151,
					50.21495139278024
				],
				[
					1.0178706363401466,
					50.21495139278024
				],
				[
					1.130967373711278,
					50.21495139278024
				],
				[
					1.130967373711278,
					50.10185465540911
				],
				[
					1.2440641110824096,
					50.10185465540911
				],
				[
					1.2440641110824096,
					49.87566118066685
				],
				[
					1.2440641110824096,
					49.87566118066685
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 358,
			"versionNonce": 905378533,
			"isDeleted": false,
			"id": "q2pn2Iim8BCFxvcfJT7J4",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 148.5163245428966,
			"y": 872.2445777692662,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 7.125094454380971,
			"height": 52.25069266546054,
			"seed": 1620815205,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.22619347474224458,
					0
				],
				[
					0.45238694948450753,
					0
				],
				[
					0.9047738989690151,
					0.2261934747421895
				],
				[
					1.4702575858246358,
					0.339290212113321
				],
				[
					1.8095477979380301,
					0.5654836868555839
				],
				[
					2.4881282221647822,
					0.7916771615978468
				],
				[
					2.94051517164929,
					1.0178706363401098
				],
				[
					3.1667086463915344,
					1.1309673737112413
				],
				[
					3.619095595876042,
					1.2440641110823727
				],
				[
					4.184579282731681,
					1.4702575858246358
				],
				[
					4.523869494845057,
					1.4702575858246358
				],
				[
					4.75006296958732,
					1.4702575858246358
				],
				[
					5.089353181700696,
					1.4702575858246358
				],
				[
					5.428643393814072,
					1.4702575858246358
				],
				[
					5.654836868556335,
					1.5833543231957672
				],
				[
					5.994127080669712,
					1.5833543231957672
				],
				[
					6.220320555411974,
					1.5833543231957672
				],
				[
					6.446514030154218,
					1.6964510605668988
				],
				[
					6.672707504896463,
					1.6964510605668988
				],
				[
					6.785804242267595,
					1.6964510605668988
				],
				[
					6.898900979638726,
					1.6964510605668988
				],
				[
					7.011997717009858,
					1.6964510605668988
				],
				[
					7.125094454380971,
					1.6964510605668988
				],
				[
					7.125094454380971,
					1.8095477979380301
				],
				[
					7.011997717009858,
					1.9226445353090882
				],
				[
					6.785804242267595,
					2.375031484793614
				],
				[
					6.672707504896463,
					2.82741843427814
				],
				[
					6.55961076752535,
					3.3929021211337975
				],
				[
					6.446514030154218,
					4.071482545360513
				],
				[
					6.333417292783087,
					4.523869494845039
				],
				[
					6.333417292783087,
					4.863159706958433
				],
				[
					6.1072238180408425,
					5.541740131185149
				],
				[
					6.1072238180408425,
					6.220320555411937
				],
				[
					5.994127080669712,
					7.238191191752048
				],
				[
					5.994127080669712,
					8.25606182809223
				],
				[
					5.994127080669712,
					10.291803100772524
				],
				[
					6.1072238180408425,
					12.893028060308401
				],
				[
					6.55961076752535,
					14.476382383504168
				],
				[
					6.672707504896463,
					16.39902691881333
				],
				[
					6.672707504896463,
					18.32167145412249
				],
				[
					6.672707504896463,
					19.791929039947128
				],
				[
					6.672707504896463,
					21.149089888400706
				],
				[
					6.672707504896463,
					22.61934747422534
				],
				[
					6.672707504896463,
					23.63721811056545
				],
				[
					6.672707504896463,
					24.541992009534503
				],
				[
					6.672707504896463,
					24.994378959018956
				],
				[
					6.672707504896463,
					25.786056120616873
				],
				[
					6.672707504896463,
					26.577733282214723
				],
				[
					6.672707504896463,
					27.482507181183774
				],
				[
					6.785804242267595,
					28.27418434278162
				],
				[
					6.785804242267595,
					29.292054979121804
				],
				[
					6.785804242267595,
					30.19682887809078
				],
				[
					6.785804242267595,
					30.87540930231757
				],
				[
					6.785804242267595,
					31.780183201286622
				],
				[
					6.672707504896463,
					32.6849571002556
				],
				[
					6.672707504896463,
					33.58973099922458
				],
				[
					6.55961076752535,
					34.60760163556476
				],
				[
					6.446514030154218,
					35.738569009276006
				],
				[
					6.446514030154218,
					36.75643964561619
				],
				[
					6.446514030154218,
					37.548116807214036
				],
				[
					6.446514030154218,
					38.339793968811954
				],
				[
					6.446514030154218,
					39.01837439303867
				],
				[
					6.446514030154218,
					39.81005155463659
				],
				[
					6.446514030154218,
					40.37553524149217
				],
				[
					6.446514030154218,
					40.71482545360557
				],
				[
					6.446514030154218,
					41.28030914046123
				],
				[
					6.446514030154218,
					41.61959935257462
				],
				[
					6.446514030154218,
					42.071986302059145
				],
				[
					6.446514030154218,
					42.411276514172464
				],
				[
					6.446514030154218,
					42.75056672628586
				],
				[
					6.446514030154218,
					43.08985693839926
				],
				[
					6.446514030154218,
					43.542243887883785
				],
				[
					6.446514030154218,
					43.994630837368234
				],
				[
					6.446514030154218,
					44.44701778685276
				],
				[
					6.446514030154218,
					44.78630799896615
				],
				[
					6.446514030154218,
					45.12559821107955
				],
				[
					6.446514030154218,
					45.464888423192946
				],
				[
					6.446514030154218,
					45.804178635306336
				],
				[
					6.446514030154218,
					46.25656558479079
				],
				[
					6.446514030154218,
					46.59585579690418
				],
				[
					6.446514030154218,
					46.93514600901758
				],
				[
					6.446514030154218,
					47.387532958502035
				],
				[
					6.446514030154218,
					47.726823170615425
				],
				[
					6.446514030154218,
					47.95301664535769
				],
				[
					6.446514030154218,
					48.29230685747108
				],
				[
					6.446514030154218,
					48.74469380695561
				],
				[
					6.446514030154218,
					48.97088728169787
				],
				[
					6.446514030154218,
					49.19708075644014
				],
				[
					6.446514030154218,
					49.536370968553456
				],
				[
					6.446514030154218,
					49.762564443295716
				],
				[
					6.446514030154218,
					49.98875791803798
				],
				[
					6.446514030154218,
					50.10185465540911
				],
				[
					6.446514030154218,
					50.21495139278024
				],
				[
					6.446514030154218,
					50.44114486752251
				],
				[
					6.446514030154218,
					50.66733834226477
				],
				[
					6.446514030154218,
					50.89353181700704
				],
				[
					6.446514030154218,
					51.119725291749226
				],
				[
					6.446514030154218,
					51.232822029120356
				],
				[
					6.446514030154218,
					51.45901550386262
				],
				[
					6.446514030154218,
					51.685208978604884
				],
				[
					6.446514030154218,
					51.911402453347144
				],
				[
					6.446514030154218,
					52.024499190718274
				],
				[
					6.446514030154218,
					52.137595928089404
				],
				[
					6.333417292783087,
					52.25069266546054
				],
				[
					6.1072238180408425,
					52.25069266546054
				],
				[
					5.88103034329858,
					52.25069266546054
				],
				[
					5.654836868556335,
					52.25069266546054
				],
				[
					5.202449919071827,
					52.25069266546054
				],
				[
					4.863159706958451,
					52.25069266546054
				],
				[
					4.636966232216189,
					52.25069266546054
				],
				[
					4.184579282731681,
					52.25069266546054
				],
				[
					3.8452890706183047,
					52.25069266546054
				],
				[
					3.505998858504929,
					52.25069266546054
				],
				[
					3.2798053837626657,
					52.25069266546054
				],
				[
					2.8274184342781585,
					52.25069266546054
				],
				[
					2.6012249595359136,
					52.25069266546054
				],
				[
					2.2619347474225378,
					52.25069266546054
				],
				[
					2.1488380100514064,
					52.25069266546054
				],
				[
					2.0357412726802746,
					52.25069266546054
				],
				[
					2.0357412726802746,
					52.25069266546054
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 188,
			"versionNonce": 87445995,
			"isDeleted": false,
			"id": "xLUJ5q4ttwRUsXYdg4so4",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 110.076097296456,
			"y": 875.7021895319333,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 4.742431086231065,
			"height": 7.074774243393904,
			"seed": 1250417099,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.07774477190542939,
					0
				],
				[
					-0.15548954381084457,
					0.07774477190548623
				],
				[
					-0.38872385952713273,
					0.3887238595272038
				],
				[
					-0.5442134033379773,
					0.6219581752434351
				],
				[
					-0.7774477190542655,
					0.8551924909597801
				],
				[
					-1.1661715785814124,
					1.2439163504868702
				],
				[
					-1.3994058942976864,
					1.5548954381085878
				],
				[
					-1.7103849819193897,
					1.8658745257303053
				],
				[
					-1.9436192976356779,
					2.0991088414465366
				],
				[
					-2.2545983852573954,
					2.4878327009737404
				],
				[
					-2.41008792906824,
					2.7210670166899718
				],
				[
					-2.643322244784528,
					3.0320461043116893
				],
				[
					-2.7988117885953727,
					3.2652804200279206
				],
				[
					-3.032046104311661,
					3.576259507649638
				],
				[
					-3.1097908762170903,
					3.809493823365983
				],
				[
					-3.1875356481225197,
					4.0427281390822145
				],
				[
					-3.265280420027949,
					4.2759624547985595
				],
				[
					-3.265280420027949,
					4.431451998609418
				],
				[
					-3.3430251919333784,
					4.742431086231136
				],
				[
					-3.3430251919333784,
					4.820175858136508
				],
				[
					-3.3430251919333784,
					4.897920630041995
				],
				[
					-3.3430251919333784,
					5.053410173852853
				],
				[
					-3.420769963838808,
					5.208899717663712
				],
				[
					-3.420769963838808,
					5.286644489569085
				],
				[
					-3.498514735744237,
					5.4421340333799435
				],
				[
					-3.5762595076496524,
					5.597623577190802
				],
				[
					-3.731749051460511,
					5.830857892907034
				],
				[
					-3.8094938233659406,
					5.986347436717892
				],
				[
					-3.8872385952713557,
					6.064092208623379
				],
				[
					-4.0427281390822145,
					6.29732652433961
				],
				[
					-4.120472910987644,
					6.375071296245096
				],
				[
					-4.198217682893073,
					6.530560840055955
				],
				[
					-4.275962454798503,
					6.6083056119613275
				],
				[
					-4.353707226703932,
					6.686050383866814
				],
				[
					-4.4314519986093615,
					6.763795155772186
				],
				[
					-4.4314519986093615,
					6.919284699583045
				],
				[
					-4.509196770514791,
					6.919284699583045
				],
				[
					-4.58694154242022,
					6.997029471488531
				],
				[
					-4.66468631432565,
					7.074774243393904
				],
				[
					-4.742431086231065,
					7.074774243393904
				],
				[
					-4.742431086231065,
					7.074774243393904
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 173,
			"versionNonce": 1300256325,
			"isDeleted": false,
			"id": "pbr2GQhuVXMmShMY0zvNz",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 104.08974985973809,
			"y": 875.5466999881224,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 6.141836980528765,
			"height": 7.15251901529939,
			"seed": 2079490731,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.15548954381085878,
					0.31097908762171755
				],
				[
					0.23323431571627395,
					0.3887238595272038
				],
				[
					0.6219581752434209,
					0.6997029471489213
				],
				[
					1.088426806675983,
					1.0884268066760114
				],
				[
					1.4771506662031157,
					1.4771506662031015
				],
				[
					1.710384981919404,
					1.7103849819194465
				],
				[
					2.099108841446551,
					2.176853613352023
				],
				[
					2.5655774728790988,
					2.565577472879113
				],
				[
					2.8765565605008163,
					3.0320461043116893
				],
				[
					3.2652804200279633,
					3.4985147357442656
				],
				[
					3.654004279555082,
					4.0427281390822145
				],
				[
					4.042728139082229,
					4.431451998609418
				],
				[
					4.353707226703946,
					4.897920630041995
				],
				[
					4.742431086231065,
					5.208899717663712
				],
				[
					4.897920630041924,
					5.51987880528543
				],
				[
					5.208899717663641,
					5.830857892907034
				],
				[
					5.442134033379929,
					6.219581752434237
				],
				[
					5.675368349096203,
					6.452816068150469
				],
				[
					5.830857892907062,
					6.6083056119613275
				],
				[
					5.908602664812477,
					6.686050383866814
				],
				[
					5.986347436717907,
					6.8415399276776725
				],
				[
					6.064092208623336,
					6.919284699583045
				],
				[
					6.064092208623336,
					6.997029471488531
				],
				[
					6.141836980528765,
					7.074774243393904
				],
				[
					6.141836980528765,
					7.15251901529939
				],
				[
					6.141836980528765,
					7.15251901529939
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 227,
			"versionNonce": 168483979,
			"isDeleted": false,
			"id": "B0_U9YMXSAKjE0ee-N-Sa",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 104.9449423506978,
			"y": 888.2968425806125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 4.820175858136508,
			"height": 11.428481470097836,
			"seed": 1578828843,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.15548954381085878
				],
				[
					0.07774477190542939,
					0.3887238595272038
				],
				[
					0.23323431571627395,
					0.6997029471489213
				],
				[
					0.38872385952713273,
					0.9329372628651527
				],
				[
					0.6997029471488361,
					1.2439163504868702
				],
				[
					0.8551924909596949,
					1.4771506662032152
				],
				[
					1.1661715785814124,
					1.5548954381085878
				],
				[
					1.5548954381085451,
					1.7103849819194465
				],
				[
					1.788129753824819,
					1.7103849819194465
				],
				[
					2.0991088414465366,
					1.7103849819194465
				],
				[
					2.4878327009736694,
					1.7103849819194465
				],
				[
					2.7988117885953727,
					1.632640210014074
				],
				[
					3.1875356481225197,
					1.4771506662032152
				],
				[
					3.420769963838808,
					1.2439163504868702
				],
				[
					3.654004279555082,
					1.0884268066760114
				],
				[
					3.8872385952713557,
					0.7774477190542939
				],
				[
					3.964983367176785,
					0.6997029471489213
				],
				[
					4.120472910987644,
					0.46646863143257633
				],
				[
					4.198217682893073,
					0.31097908762171755
				],
				[
					4.353707226703932,
					-0.07774477190537255
				],
				[
					4.353707226703932,
					-0.23323431571623132
				],
				[
					4.4314519986093615,
					-0.46646863143246264
				],
				[
					4.4314519986093615,
					-0.6219581752433214
				],
				[
					4.509196770514791,
					-0.7774477190541802
				],
				[
					4.509196770514791,
					-0.8551924909596664
				],
				[
					4.509196770514791,
					-0.932937262865039
				],
				[
					4.509196770514791,
					-0.8551924909596664
				],
				[
					4.58694154242022,
					-0.5442134033379489
				],
				[
					4.58694154242022,
					-0.23323431571623132
				],
				[
					4.58694154242022,
					0.15548954381085878
				],
				[
					4.66468631432565,
					0.6997029471489213
				],
				[
					4.66468631432565,
					1.2439163504868702
				],
				[
					4.66468631432565,
					1.7103849819194465
				],
				[
					4.66468631432565,
					2.7210670166899718
				],
				[
					4.66468631432565,
					3.187535648122548
				],
				[
					4.66468631432565,
					3.6540042795551244
				],
				[
					4.66468631432565,
					4.431451998609418
				],
				[
					4.66468631432565,
					5.208899717663712
				],
				[
					4.66468631432565,
					5.90860266481252
				],
				[
					4.66468631432565,
					6.530560840055955
				],
				[
					4.58694154242022,
					6.919284699583045
				],
				[
					4.509196770514791,
					7.385753331015621
				],
				[
					4.4314519986093615,
					7.774477190542825
				],
				[
					4.353707226703932,
					8.085456278164543
				],
				[
					4.120472910987644,
					8.474180137691633
				],
				[
					3.964983367176785,
					8.707414453407864
				],
				[
					3.731749051460511,
					9.018393541029582
				],
				[
					3.5762595076496666,
					9.251627856745927
				],
				[
					3.3430251919333784,
					9.640351716273017
				],
				[
					3.1097908762170903,
					9.951330803894734
				],
				[
					2.9543013324062315,
					10.106820347705593
				],
				[
					2.643322244784528,
					10.340054663421938
				],
				[
					2.410087929068254,
					10.41779943532731
				],
				[
					2.2545983852573954,
					10.495544207232797
				],
				[
					2.0213640695411073,
					10.495544207232797
				],
				[
					1.8658745257302485,
					10.495544207232797
				],
				[
					1.7103849819193897,
					10.495544207232797
				],
				[
					1.5548954381085451,
					10.495544207232797
				],
				[
					1.321661122392257,
					10.340054663421938
				],
				[
					1.1661715785814124,
					10.262309891516452
				],
				[
					0.9329372628651242,
					10.106820347705593
				],
				[
					0.8551924909596949,
					10.02907557580022
				],
				[
					0.6219581752434067,
					9.795841260083876
				],
				[
					0.4664686314325479,
					9.640351716273017
				],
				[
					0.23323431571627395,
					9.407117400556785
				],
				[
					0.15548954381085878,
					9.251627856745927
				],
				[
					0,
					9.096138312935068
				],
				[
					-0.15548954381085878,
					8.862903997218723
				],
				[
					-0.15548954381085878,
					8.707414453407864
				],
				[
					-0.15548954381085878,
					8.629669681502492
				],
				[
					-0.15548954381085878,
					8.474180137691633
				],
				[
					-0.15548954381085878,
					8.240945821975401
				],
				[
					-0.07774477190542939,
					8.163201050069915
				],
				[
					0,
					7.929966734353684
				],
				[
					0,
					7.852221962448198
				],
				[
					0.07774477190542939,
					7.774477190542825
				],
				[
					0.23323431571627395,
					7.696732418637339
				],
				[
					0.31097908762170334,
					7.618987646731966
				],
				[
					0.38872385952713273,
					7.54124287482648
				],
				[
					0.38872385952713273,
					7.54124287482648
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 216,
			"versionNonce": 369575333,
			"isDeleted": false,
			"id": "MY0S3tXWhC0Ld2EXTuZdx",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 103.68836169035347,
			"y": 903.9606349831801,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 6.751218284893582,
			"height": 10.7055032803313,
			"seed": 707472709,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726447,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.38578390199390356,
					0
				],
				[
					0.7715678039878355,
					0
				],
				[
					1.1573517059817533,
					0
				],
				[
					1.446689632477188,
					0
				],
				[
					1.639581583474154,
					0
				],
				[
					1.9289195099695888,
					0
				],
				[
					2.2182574364650236,
					0
				],
				[
					2.7004873139574244,
					0
				],
				[
					3.182717191449825,
					0.09644597549845457
				],
				[
					3.568501093443743,
					0.09644597549845457
				],
				[
					3.9542849954376607,
					0.19289195099702283
				],
				[
					4.24362292193311,
					0.2893379264954774
				],
				[
					4.725852799425496,
					0.2893379264954774
				],
				[
					4.918744750422462,
					0.2893379264954774
				],
				[
					5.30452865241638,
					0.2893379264954774
				],
				[
					5.690312554410298,
					0.2893379264954774
				],
				[
					6.0760964564042155,
					0.2893379264954774
				],
				[
					6.2689884074011815,
					0.2893379264954774
				],
				[
					6.461880358398133,
					0.2893379264954774
				],
				[
					6.558326333896616,
					0.2893379264954774
				],
				[
					6.654772309395099,
					0.2893379264954774
				],
				[
					6.751218284893582,
					0.385783901993932
				],
				[
					6.751218284893582,
					0.5786758529908411
				],
				[
					6.654772309395099,
					0.771567803987864
				],
				[
					6.558326333896616,
					0.9644597549847731
				],
				[
					6.1725424319026985,
					1.157351705981796
				],
				[
					5.593866578911815,
					1.736027558972637
				],
				[
					5.015190725920945,
					2.121811460966569
				],
				[
					4.24362292193311,
					2.7969332894559784
				],
				[
					3.664947068942226,
					3.279163166948365
				],
				[
					3.375609142446791,
					3.664947068942297
				],
				[
					3.086271215951342,
					4.1471769464346835
				],
				[
					2.893379264954376,
					4.436514872930047
				],
				[
					2.7004873139574244,
					4.822298774923979
				],
				[
					2.4111493874619896,
					5.208082676917911
				],
				[
					2.1218114609665406,
					5.497420603413389
				],
				[
					1.9289195099695888,
					5.8832045054073205
				],
				[
					1.736027558972637,
					6.172542431902684
				],
				[
					1.639581583474154,
					6.461880358398162
				],
				[
					1.446689632477188,
					6.847664260392094
				],
				[
					1.253797681480222,
					7.137002186887571
				],
				[
					0.9644597549847873,
					7.715678039878412
				],
				[
					0.7715678039878355,
					8.101461941872344
				],
				[
					0.6751218284893525,
					8.487245843866276
				],
				[
					0.5786758529908695,
					8.873029745860208
				],
				[
					0.48222987749238655,
					9.162367672355572
				],
				[
					0.38578390199390356,
					9.548151574349504
				],
				[
					0.28933792649543477,
					9.741043525346527
				],
				[
					0.28933792649543477,
					10.03038145184189
				],
				[
					0.28933792649543477,
					10.223273402838913
				],
				[
					0.28933792649543477,
					10.319719378337368
				],
				[
					0.28933792649543477,
					10.416165353835822
				],
				[
					0.28933792649543477,
					10.512611329334277
				],
				[
					0.38578390199390356,
					10.609057304832845
				],
				[
					0.6751218284893525,
					10.7055032803313
				],
				[
					1.0609057304832703,
					10.7055032803313
				],
				[
					1.639581583474154,
					10.7055032803313
				],
				[
					2.2182574364650236,
					10.7055032803313
				],
				[
					2.893379264954376,
					10.7055032803313
				],
				[
					3.472055117945274,
					10.512611329334277
				],
				[
					3.664947068942226,
					10.512611329334277
				],
				[
					4.050730970936144,
					10.416165353835822
				],
				[
					4.340068897431593,
					10.223273402838913
				],
				[
					4.532960848428544,
					10.223273402838913
				],
				[
					4.822298774923979,
					10.126827427340345
				],
				[
					5.111636701419428,
					10.03038145184189
				],
				[
					5.208082676917911,
					9.933935476343436
				],
				[
					5.400974627914863,
					9.933935476343436
				],
				[
					5.497420603413332,
					9.933935476343436
				],
				[
					5.593866578911815,
					9.933935476343436
				],
				[
					5.786758529908781,
					9.933935476343436
				],
				[
					5.786758529908781,
					9.933935476343436
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 167,
			"versionNonce": 624235307,
			"isDeleted": false,
			"id": "QPfXXLBeR2BZtsIH6F2WT",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 102.62745595987019,
			"y": 907.6255820521224,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 6.558326333896616,
			"height": 0.09644597549845457,
			"seed": 968467205,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726448,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.38578390199391777,
					0
				],
				[
					0.48222987749240076,
					0
				],
				[
					0.8680137794863185,
					0
				],
				[
					1.3502436569787193,
					0
				],
				[
					2.121811460966555,
					0
				],
				[
					2.7004873139574386,
					0
				],
				[
					2.9898252404528733,
					0
				],
				[
					3.568501093443757,
					0
				],
				[
					3.9542849954376607,
					0
				],
				[
					4.24362292193311,
					0
				],
				[
					4.629406823927027,
					0
				],
				[
					4.918744750422462,
					0
				],
				[
					5.208082676917911,
					0
				],
				[
					5.497420603413346,
					0
				],
				[
					5.593866578911829,
					0
				],
				[
					5.786758529908781,
					0
				],
				[
					5.979650480905747,
					0
				],
				[
					6.07609645640423,
					0
				],
				[
					6.172542431902713,
					0
				],
				[
					6.3654343828996645,
					0.09644597549845457
				],
				[
					6.4618803583981475,
					0.09644597549845457
				],
				[
					6.558326333896616,
					0.09644597549845457
				],
				[
					6.558326333896616,
					0.09644597549845457
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 186,
			"versionNonce": 1119439109,
			"isDeleted": false,
			"id": "7J9G7dZnrLD-FxiaSXQDU",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 147.99721067926654,
			"y": 876.9794360576989,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 4.601629412379651,
			"height": 7.596340617261717,
			"seed": 2069011301,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726448,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.07304173670442538,
					0
				],
				[
					-0.14608347340887917,
					0.0730417367044538
				],
				[
					-0.3652086835221837,
					0.2191252101133614
				],
				[
					-0.6573756303399421,
					0.5112921569310629
				],
				[
					-0.8765008404532466,
					0.7304173670444243
				],
				[
					-1.0956260505665796,
					1.0225843138621258
				],
				[
					-1.387792997384338,
					1.314751260679941
				],
				[
					-1.6799599442020963,
					1.75300168090655
				],
				[
					-1.7530016809065216,
					2.0451686277243653
				],
				[
					-1.9721268910198546,
					2.4103773112465205
				],
				[
					-2.118210364428734,
					2.629502521359882
				],
				[
					-2.264293837837613,
					3.067752941586491
				],
				[
					-2.4834190479509175,
					3.3599198884041925
				],
				[
					-2.556460784655343,
					3.579045098517554
				],
				[
					-2.775585994768676,
					3.8712120453352554
				],
				[
					-2.994711204882009,
					4.163378992153071
				],
				[
					-3.067752941586434,
					4.382504202266318
				],
				[
					-3.2138364149953134,
					4.60162941237968
				],
				[
					-3.3599198884041925,
					4.820754622493041
				],
				[
					-3.5060033618130717,
					5.039879832606289
				],
				[
					-3.5790450985175255,
					5.185963306015196
				],
				[
					-3.652086835221951,
					5.405088516128558
				],
				[
					-3.652086835221951,
					5.478130252833012
				],
				[
					-3.7251285719263763,
					5.697255462946259
				],
				[
					-3.79817030863083,
					5.843338936355167
				],
				[
					-3.944253782039709,
					6.062464146468528
				],
				[
					-4.017295518744135,
					6.281589356581776
				],
				[
					-4.017295518744135,
					6.35463109328623
				],
				[
					-4.090337255448588,
					6.500714566695137
				],
				[
					-4.163378992153042,
					6.646798040103931
				],
				[
					-4.236420728857468,
					6.719839776808385
				],
				[
					-4.309462465561893,
					6.865923250217293
				],
				[
					-4.382504202266347,
					7.0120067236262
				],
				[
					-4.455545938970772,
					7.085048460330654
				],
				[
					-4.455545938970772,
					7.158090197035108
				],
				[
					-4.455545938970772,
					7.231131933739448
				],
				[
					-4.455545938970772,
					7.3772154071483556
				],
				[
					-4.528587675675226,
					7.450257143852809
				],
				[
					-4.528587675675226,
					7.523298880557263
				],
				[
					-4.601629412379651,
					7.523298880557263
				],
				[
					-4.601629412379651,
					7.596340617261717
				],
				[
					-4.601629412379651,
					7.596340617261717
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 185,
			"versionNonce": 1461679563,
			"isDeleted": false,
			"id": "l7Gq7M0m088cVkfcseFSn",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 142.81124737325138,
			"y": 876.9063943209944,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 6.792881513512839,
			"height": 7.085048460330654,
			"seed": 1933220965,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726448,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.14608347340887917,
					0.2921669468178152
				],
				[
					0.5112921569310629,
					0.6573756303399705
				],
				[
					0.876500840453275,
					0.9495425771577857
				],
				[
					1.3147512606798841,
					1.3877929973843948
				],
				[
					1.8260434176109754,
					1.6069182074976425
				],
				[
					2.0451686277243084,
					1.8990851543154577
				],
				[
					2.4834190479509175,
					2.118210364428819
				],
				[
					2.921669468177555,
					2.4834190479509743
				],
				[
					3.140794678290888,
					2.7025442580643357
				],
				[
					3.5060033618130717,
					2.9947112048820372
				],
				[
					3.79817030863083,
					3.2868781516998524
				],
				[
					4.090337255448588,
					3.579045098517554
				],
				[
					4.309462465561921,
					3.7981703086309153
				],
				[
					4.455545938970772,
					3.871212045335369
				],
				[
					4.674671149084105,
					4.090337255448617
				],
				[
					4.893796359197438,
					4.382504202266432
				],
				[
					5.039879832606289,
					4.528587675675226
				],
				[
					5.112921569310743,
					4.6746711490841335
				],
				[
					5.259005042719593,
					4.820754622493041
				],
				[
					5.405088516128501,
					5.039879832606289
				],
				[
					5.551171989537352,
					5.185963306015196
				],
				[
					5.6242137262418055,
					5.332046779424104
				],
				[
					5.697255462946259,
					5.478130252833012
				],
				[
					5.770297199650685,
					5.6242137262418055
				],
				[
					5.84333893635511,
					5.770297199650713
				],
				[
					5.916380673059564,
					5.916380673059621
				],
				[
					5.916380673059564,
					5.9894224097640745
				],
				[
					5.989422409764018,
					6.062464146468528
				],
				[
					5.989422409764018,
					6.135505883172982
				],
				[
					6.062464146468443,
					6.208547619877322
				],
				[
					6.062464146468443,
					6.281589356581776
				],
				[
					6.135505883172868,
					6.281589356581776
				],
				[
					6.135505883172868,
					6.427672829990684
				],
				[
					6.208547619877322,
					6.500714566695137
				],
				[
					6.281589356581776,
					6.573756303399591
				],
				[
					6.427672829990627,
					6.719839776808385
				],
				[
					6.5007145666950805,
					6.792881513512839
				],
				[
					6.573756303399534,
					6.865923250217293
				],
				[
					6.64679804010396,
					6.9389649869217465
				],
				[
					6.719839776808385,
					7.0120067236262
				],
				[
					6.792881513512839,
					7.085048460330654
				],
				[
					6.792881513512839,
					7.085048460330654
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 341,
			"versionNonce": 1158930533,
			"isDeleted": false,
			"id": "7jK5Romzn3v8NzcTTm9A4",
			"fillStyle": "hachure",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 143.61470647700017,
			"y": 888.154821773478,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 3.9442537820397376,
			"height": 10.371926612030393,
			"seed": 1611440197,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702760726448,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					-0.11199732961347947
				],
				[
					0,
					-0.049137168328434344
				],
				[
					0,
					0.01372299295661078
				],
				[
					0.049303172275506554,
					0.2023034768116484
				],
				[
					0.14790951682650047,
					0.4537441219518289
				],
				[
					0.29581903365298173,
					0.7680449283769568
				],
				[
					0.44372855047948223,
					1.0823457348020846
				],
				[
					0.5423348950304762,
					1.27092621865722
				],
				[
					0.7888507564079513,
					1.7109473476524382
				],
				[
					0.9860634455099392,
					2.1509684766476562
				],
				[
					1.183276134611927,
					2.465269283072882
				],
				[
					1.3804888237139148,
					2.77957008949801
				],
				[
					1.6270046850914093,
					3.0310107346380923
				],
				[
					1.7749142019178905,
					3.1567310572081824
				],
				[
					1.9721268910198784,
					3.282451379778273
				],
				[
					2.2186427523973538,
					3.3453115410633183
				],
				[
					2.4158554414993416,
					3.3453115410633183
				],
				[
					2.662371302876817,
					3.3453115410633183
				],
				[
					2.810280819703317,
					3.3453115410633183
				],
				[
					3.056796681080792,
					3.282451379778273
				],
				[
					3.2047061979072926,
					3.1567310572081824
				],
				[
					3.352615714733793,
					3.0310107346380923
				],
				[
					3.4512220592847678,
					2.9052904120681
				],
				[
					3.5005252315602746,
					2.7167099282129645
				],
				[
					3.5991315761112492,
					2.590989605642874
				],
				[
					3.6977379206622625,
					2.3395489605027917
				],
				[
					3.796344265213237,
					2.2138286379327017
				],
				[
					3.8456474374887435,
					2.025248154077566
				],
				[
					3.8456474374887435,
					1.7738075089374834
				],
				[
					3.8949506097642503,
					1.5223668637974006
				],
				[
					3.9442537820397376,
					1.3966465412273104
				],
				[
					3.9442537820397376,
					1.1452058960871296
				],
				[
					3.9442537820397376,
					0.9566254122320922
				],
				[
					3.9442537820397376,
					0.7680449283769568
				],
				[
					3.9442537820397376,
					0.5794644445218213
				],
				[
					3.9442537820397376,
					0.4537441219518289
				],
				[
					3.9442537820397376,
					0.2651636380966935
				],
				[
					3.9442537820397376,
					0.13944331552660322
				],
				[
					3.9442537820397376,
					0.0765831542415581
				],
				[
					3.9442537820397376,
					-0.11199732961347947
				],
				[
					3.9442537820397376,
					-0.17485749089852465
				],
				[
					3.9442537820397376,
					-0.23771765218356966
				],
				[
					3.9442537820397376,
					-0.3005778134686148
				],
				[
					3.9442537820397376,
					-0.42629813603860733
				],
				[
					3.9442537820397376,
					-0.5520184586086977
				],
				[
					3.9442537820397376,
					-0.6148786198937428
				],
				[
					3.9442537820397376,
					-0.6777387811787878
				],
				[
					3.9442537820397376,
					-0.7405989424638331
				],
				[
					3.9442537820397376,
					-0.8034591037488781
				],
				[
					3.9442537820397376,
					-0.6777387811787878
				],
				[
					3.9442537820397376,
					-0.42629813603860733
				],
				[
					3.9442537820397376,
					-0.17485749089852465
				],
				[
					3.9442537820397376,
					0.0765831542415581
				],
				[
					3.9442537820397376,
					0.2651636380966935
				],
				[
					3.9442537820397376,
					0.5794644445218213
				],
				[
					3.9442537820397376,
}