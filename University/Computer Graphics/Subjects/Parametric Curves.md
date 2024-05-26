---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
P ^5YwjuiWH

a ^noqCvc54

r ^GpjbApZV

a ^HvaptkyZ

m ^5nYUI97E

e ^8ElM2M6t

t ^io9juNly

r ^vDzIK69P

i ^jcrnEVxn

c ^So8jcN3b

C ^F9LmUaje

u ^tpPpKWsG

r ^8gxy3kls

v ^Ek9wKRuT

e ^JL8YURhm

s ^rv62rBHM

Parametric surfaces and curves can be represented in
two ways ^fT0xLd5O

Explicit Representations ^2Qi3LCtI

Implicit Representations ^eAjFL0E2

p: R -> R ^VYLgJdd1

d ^3mjZudZx

t ->  ^0gnGDzMM

p(t) = [ x(t) , y(t), z(t) ] ^JurLOYvT

example ^XaB3Z6k7

t = [0,2Pi]
p(t) = r( cos(t), sin(t), 0)  ^yP55BnEk

f: R -> R ^Gxg57rWL

d ^gIZahTtu

p -> f( p(x,y) ) = x^2 + y^2 - r^2 ^ExhaaYjA

if f(p) = 0 then p is on the surface ^X0My576R

Properties
of Curves ^dLJhlHL8

Lets take the curve segment [a,b]
This curve segment can be parameterized differently even if its modelling
the exact same line ^UrGZMCK7

p(t) = t a + (1-t) b

p(t) = t a + (1-t ) b ^mRyZeIfy

2 ^cMLN87L1

2 ^BuFGq633

a ^DiMLqNps

b ^F4S9Xw1K

a ^Z3gWGyo1

b ^jltDQjux

1) A parametric curve is n times continuously differentiable if the mapping is n times continuously differentiable.

2) A curve is regular if the first derivative of p exists and p'(t) != 0 for all t.
This regularity describes smoothness of a curve, and a curve is only regular if
it has no kinks (im not gonna judge if it does)

3) Arclength of a curve




Which calculates the length of the curve via an integral of its derivative
which is not very analytically easy to compute 


4) Curvature is the magnitude of the curve vector ^7x6Nbo3U

The derivative p'(t) of p at t is a vector, which provides the
tangential direction of the curve at that position. 
and the magnitude can be seen the as the strength
of the steps in that direction ^dmdoNNVC

example of an irregular continuously differential curve!
derivative at 0 is 0 ^eYqXMJUf

a curve is parameteried by its arclength if the length
of its derivative is 1 everywhere
which only happens if the curve is regular! ^p3aBNQZX

Generation of Parametric Curves ^F4p3zkju

We want to find a way to be able to Generate a parametric curve and be able to control it
to our liking with predictable changes
We also think it is convenient to Generate the curve in the following form: 




The first idea is to mess with polynomials
Theyre continuously differentiable and regular, can we understand how to
tune their coefficients such that we get a surface that we want? ^WL7iow8O

A polynomial such as this of degree n forms a n+1 dimensional vector space
such that the monomial (the variables not the coefficients) are its basis.

We control the coefficients c0... cn, what do those coefficients mean when it comes to the curve? ^L3wix8xo

Coefficients determine the derivative of the curve at t.
Modeling of curves with the help of these coefficients is virtually impossible. ^Fnf0zcGK

Interpolation ^iQ20T3z4

What if we can choose certain points at certain inputs such that our curve has to go through
and we interpolate the rest that is inbetween? ^JUdtfMWz

Lets consider the following Lagrange polynomial ^6ciUprAy

missing (t-ti) ^SJ1YoYtw

missing (ti-ti) ^4TLuzFm5

substituting any point that is not ti will result in 0
and substituting ti will result in 1 ^0MoIKmbw

Which will result that our interpolation problem becomes ^VZKWq5LM

such that at point k no other point other than k contributes to pk so we will get pk * 1
and anything in between is an interpolation of such through the various points ^BlEFRsiz

This implementation is not perfect but its nice because it offers us
affine invariance

Affine invariance is the following homoginity of an affine transformation T ^toxyK91L

We may generate the curve from the points and then transform the curve
or first transform the points and the generate the curve from the transformed points.
Which is quite useful in order to get the same curve for different devices that may have
different resolutions and thus different coordinate systems. ^a4q1959v

With higher polynomial degree the interpolation shows undesired oscillation. ^xvjD5laV

The form of the curve depends not only on the points (pi )
but also on the choice of ti, i.e. the parametrization. ^u1pq2Ksh

Hermite interpolation ^9iVN8bLX

Hermite Interpolation interpolates not only the geometric positions (points) but also their derivatives
The cubic version allows interpolation of two points, this method consists of 4 basis functions over
the [0,1] interval: ^WVg2Pzaq

point 1 ^9BQyNeKa

point 2 ^s1bBSbDi

derivative
at point 1 ^sidP6yIP

derivative
at point 2 ^IYaDGjeg

p0 ^MGJ2EpX6

p1 ^0vlKI2dQ

m0 ^fxkB2Pal

m1 ^gJJao4Un

Approximation ^Xed7LOOX

Sometimes interpolation is hard to control and not the best method.
We can also settle down for Approximation methods that try to build a polynomial such that
it has the least distance to all points ^C0Tixxfh

Which leads us to a linear system of equations ^fwQFXiek

Evaluation at point i ^RXZabbUT

variables ^FDo9nhCq

control
points ^OPnSWu5u

Basis function i
of degree n ^w4tqloLM

Control point i ^SQmsyPnq

General Properties we like our curve to function to have: ^29pY9Uhp

1) Our control points are used as coefficients for modelling
2) moving the points we want the curve to follow smoothly and predictably
3) moving a control point should only have local effects, not global
4) no unwanted oscillation between two control points
5) Affine invariant (explained later)
6) Linearly precise
7) Efficient processing and rendering ^PdC6Qj7n

How do we Generate such curves? ^W9mJhXor

Bezier Curves ^WiPqFSI7

Bezier curves are curved defined by a control polygon

A control polygon is a polygon that encodes all control points and their sequence ^Cu0PUJyu

p1 ^rIXpfPYI

p2 ^SXe2TZcE

p3 ^I96Eg3aC

p4 ^fkDr1FSF

p5 ^G7xE6X2J

t=0 ^jiSfxI8P

t=1 ^d7FwKUdl

The points are encoded on a fixed interval t between 0 and 1 ^HsRhh985

Bezier curves only interpolate the first and the last point from the control
polygon but it will smoothly follow the shape of the polygon
 and is defined as follows: ^Bp3QdpeZ

control
points ^e4vB4DXR

Bernstein Polynomial ^Zl9RK3Oi

But what is a
Bernstein Polynom? ^cjEivlWs

Bernstein Polynomial
Basis function ^ViBjq3pk

from n
pick i ^9VFjZL3S

n basis ^4Hezhcny

related to
ith point ^ssbbNijC

interval [0,1] ^cGjeVaTp

Polynomial of degree n forms the basis of a
n+1 dimensional vector space of polynomials (n+1 points)

These polynomials provide the following properties:

1) partition of unity:


The sum of all Bernstein basis polynomials of n degree over the
same interval is always equal to 1


2) non-negativity:


Bernstein basis polynomials never produce negative results


3) Recursion:


Bernstein polynomials are a linear combination of the recursive
matching Bernstein polynomial of the previous degree


4) Symmetry:


Bernstein polynomials are symmetric
meaning if we go at the start and end of the interval
where the point is at the start and end too, the result will
be the same ^CefuugeV

p1 ^tTPVxMGu

p2 ^2OHywLhy

p3 ^2pnSyVrM

p4 ^iNp2KzTH

p5 ^YMY7ejdd

t=0 ^U5hmycIe

t=1 ^N0e16aU7

every point on the curve
is a linear/affine combination of the
control points ^dWzbF0kx

p1 ^MIceWtMR

p2 ^mCpgMQvi

p3 ^nzpdOwqO

p4 ^n3582KJ3

p5 ^byyVXPlp

t=0 ^AF7VOhkK

t=1 ^tLFNXSqh

The curvature will always follow
the control polygon and be in its convex
hull (convex combination) ^euicolFB

p1 ^9clCu7so

p2 ^2QrRON8M

p3 ^xtda7RH8

p4 ^FA3hwA7u

p5 ^ZNmWhd7P

t=0 ^8SItrKD9

t=1 ^FfzneDt5

at any two symmetric points on the curve
the opposing points will have the same influence ^H2RZOc0K

Constant ^OSnvKeze

Linear ^zicdZf3w

Quadratic ^rX6LZLK7

If we start with a constant polynomial we can
interpolate it in both ways which results in 2 linear
functions which can also be interpolated and linearly added
to form three quadratic functions ^piVxvZNV

Which makes it affine invariant!!! ^DTVbdYqm

The derivative of a Bézier Curve is a polynomial and can be expressed in Bézier form: ^YDtBvzTG

Which means that the first derivative of it is ^rLW6xbEJ

Segments of the
control polygon ^uATe1kBu

If we calculate the derivatives at each end of the curve we find that ^DsJLRWlj

p1 ^vmsVi9VU

p2 ^iFQix1vm

p3 ^Z0M08dRW

p4 ^ldsNNovG

p5 ^u6MQDboL

t=0 ^lF1F8IYG

t=1 ^hxoW0jUF

The curve Tangents at these points are the derivatives
of the curve at each point which are also the first and last
segment ^c1K5spgW

Variation Diminishing Property ^hMNxzD6k

THis property holds for Bezier curves and tells us that the curve does not oscillate more
than the polygon itself, meaning for any line, the number of intersections it has with the control
polygon is always bigger than the number of intersections it has with the curve ^VT3sxm3A

De casteljau Algorithm ^srG2ebDZ

Given a Bezier Curve, in order to find a point and tangent at a
certain interval on the point we consider the following recursion:



Down until


We can generate the point ^BvUHEgNV

an interpolation between two
points in a segment according to
our interval in a Control polygon
that is one dimension lower! ^fOl3k1Iv

p1 ^9bOOOhXs

p2 ^zyELiHaP

p3 ^D0srU6GL

p4 ^njS7Qc2j

p5 ^79qMFiDn

t=0 ^T5SyMDDc

t=1 ^1W1auF1T

We want to evaluate the point at 1/3 ^p56Ft8DB

Recursion 1 ^NDhyeQ4z

Recursion 2 ^PT5y0OCc

Recursion 3 ^0WJGRvyL

We can also use this algorithm to evaluate the derivatives on a certain interval





Furthermore if you have noticed, we can subdivide our control polygon into 2 control polygons that
describe the same curve in the same Bezier representation ^3hn2B78B

This method of subdivision really helps with intersection calculation since we can ignore the halves that
their control polygon does not get intersected according to the variation diminishing property ^GBIaJgEn

De Casteljau can also be used to
create more control points! ^zkTV340z

Say you have n degree control polynomial and you want to create an n+1
Control polynomial that describes the same curve.

Why you might ask? well the more control points you have the
more control you have on little variations in the curve.

Rule:
Every N degree control polynomial has an N+i equivalent control
polynomial that describes the same curve, whereas the opposite is not
guaranteed.


So whats the algorithm to add more control points?




Or if you want piece-wise (per segment) linear interpolation of points ^BsPApitm

Note that the interpolation is not the same for every segment unlike
the previous algorithm ^Gx3kUnFQ

And this result is much better than subdividing the curve into two control
polygons because of a simple caveat ^bAsU4HPQ

Moving the top three points (the tangent points) around will destroy the equivalence
of the two control polygons because the middle point is always supposed to be tangental
to the curve alongside the fact that the distance to the left and right point must be equal ^UiUyBtuY

Splines ^s4deMXZO

Bezier Curves are great, they offer nice control and good algorithms, one issue arises that leads us
to splines though.

Lets say we have a curve that we re-parameterized into a high degree because we want more control and
want it to be intricate. at extreme degrees of control polynomials, the control points start having small to
little effect on the curve, and it would require change in a lot of control points to get a desired shape.


Okay well we cant use low degree Bezier curves in order to get intricate shapes, and using high degree polynomials
is hard, the Idea behind splines is to split the entire curve into segments each of which are Bezier curves of low
degree on their own, that way we also offer locality to the change of control points, a few rules need to be put in 
place first to achieve this.

We define the spline over segments u0....un, where ui is the point that connects the two bezier segments.
We need to offer a smooth transition from one curve into another in order to simulate regularity and not
be so obvious about the segmentation.

1) Every Bezier segment must be regular and continuously differentiable on its own.

2) at ui, both the positions and the derivatives of the connected segments must match
for this we define the following terms:







So for a Bezier spline to be Parametrically continuous it would require 



so for C0 only the locations have to match, for C1  it would have to C0 continuous and the first derivatives have to
match meaning the length of the connecting segments in the control polygon have to be the same








And for C2 which dictates that the transition has the same curvature on both ends we need
 ^ve79aYX4

Parametric continuity / C - Continuous
is when all the segments in the spline match their derivative up to degree n on the segment connection points ^sGhbmdEM

Geometric continuity / G - Continuous
is when all the segments in the spline can be reparameterized such that the connection such that the connection with be C continuous ^sgxv37Sx

n ^QJSPNmvi

n ^o0SSi9Aw

n ^wGhOv0hb

And to be clear, these smoothness conditions are necessary to make a spline smooth but theyre not sufficient as there can always
be examples of non-smooth splines that apply these conditions using intersections to create cusps ^eRi3gZ3d

B - Splines ^te4cV73j

Two issues arise when talking about Bezier Splines

The first issue is regarding the formulation, because we are concatenating
different Bezier splines we have now lost the formulation of C_point * Basis_function
Which is a convenient formulation that we want

The second issue is regarding our claim of Local control
even though we defined our segments as different Bezier curves, our smoothness terms still
force us to change connecting segments accordingly which removes the whole idea of local control
(although it decays exponentially the further you go along the curve) ^qjAEw5vQ

Lets define the following t as a sequence of weakly increasing knots



such that


Then we recursively define the following functions








Which another convex affine combination interpolation using the intervals we have over the lower
degree polynomial and the reason we have identical elements at the start and the end of the sequence is because
we want to define our function in those end points (One that touches that point).
We can also denote the following which provides us with local support



B-splines also have some useful properties

1) Partition of unity
(The sum of all Basis functions =1)


2) Smoothness
if a knot consists of mu points on top of each other then the B-spline
of degree n is C^(n-mu) continuous




more over if we have n control points that are the same
the curve would interpolate that point
and if n+1 points are on a line, the curve interpolates a segment of
that line ^E7VVCdKO

Knots vs Control Points ^0qMUmgpE

Knots live in parameter space and they define the
intervals that we see ^iLbEOHyG

Control points live in the space of the basis function
and help define it.

Depending on the degree of our spline we have a different
amount of control points

k points
k-1 intervals
n degree
k-1-n Control points ^heMf8AGy

2 Control
Points Per
Basis function ^4uchgi0v

Knots tie the
function's different
segments together ^vRbek3Z9

This is a trad between Interpolation of the end points
and continuity, the more points the closer it is to
the point and less continuous it is and vice versa  ^1zYAZEWW

Which can be written with control points
called de Boor points in order to describe the curve ^cn8Eo2it

the i-th de Boor point only has influence in the
parameter interval of [ti, ti+1+n] ^D6BwhjWE

What about 3D? ^UMBqHzAk

(Read after getting a good
grasp on 2d) ^3NomcNbZ

Parametric Surfaces ^fXSjKSW4

Mapping 2d intervals


Into 3D coordinates ^mAw1pQiw

An example for this would be the Unit sphere









such that each 2d part of the overall surface (u,v)
defined its own parametric curve which can be seen when
we fix one of their values to a constant ^h3A1swZx

Properties ^elZeqkH2

We previously talked about how we attempt to define smoothness in a curve
some necessary but no sufficient properties were:

1) Continuously differentiable:
a surface is n-continuously differentiable if its mapping is continuously differentiable

2) Regularity
For a surface to be regular, both its curve domains need to be regular themselves
as a kink in the subcurve would result in an obvious kink in the surface.
But this is not enough so we look for a new way to define it.
Each component curve generates tangent lines along its curve, for a surface to be
regular, these tangent lines have to be linearly independent at all times!
(If one of them vanishes, it technically is linear dependency with the other
line therefore they cant vanish either) ^5ecWrftq

First tangent ^MEVS1DxU

second tangent ^lYBQ4Ng6

plane defined
by those tangents ^Vw5zWdG3

In other words, the tangent plane cannot vanish
(Tangent planes are independent of parameterization! it is constant
w.r.t a single point on a surface) ^oXZ4ioLe

How so? ^eHpIYeDV

3d Cross product ofc ^vymePnse

Normal vector of the tangent plane
and thus the normal to that point
(its sign depends on the
parameterization though) ^WOaU0lFP

Definition ^iH8hvAIc

Similarly to parametric curves we want to use the formulation of
control point * Basis function in 3d





So do we need to redefine all the Basis functions in 3d?
No we can use Tensor products of function spaces ^uIlSsSHG

Tensor Products
of Function spaces ^K1xFKWex

Given the basis functions 


of two linear real univariate function spaces R1 and R2
with dimensions m+1 and n+1


The tensor product space R1xR2  is the linear subspace of bivariate
real functions spanned by the basis functions 



Which has (m+1) * (n+1) dimensions ^4OJKKVp4

This parameterization has its limitations though, due to the nature of cij
The control points lie on a grid-like structure, they can be moved around
but they still remain in grid-like structure
We can write the following in Matrix notation ^uoLEwAUn

Polynomials ^LkeQn1KH

We can choose polynomials for our univariate basis functions and use
the Tensor products to make a multivariate polynomial function





for example a quadratic univariate basis function would result in this basis ^LMqZUKnY

Lagrange ^RbcHbhOz

Given control points pij and parameter values u,v
we need to interpolate the curve such that



and the desired surface is simply given by ^fEYCi5Cx

Bezier ^aFgKAOWY

We use Bernstein polynomials over [0,1] as polynomial basis 




and the control points turn into a control mesh!
The parameter curves (one variable is constant and the other
is changing) are Bezier curves of their own








Bezier surfaces still have the Bezier properties:

1) Partition of Unity


2) Non-negativity


3) The surface is inside the convex hull
4) all 4 points at the corners of the control net are interpolated ^DOHkWiM4

new transformed
control points ^g6dGF4H5

Does De Casteljau algorithm still work
in 3d?
Fuck yeah, except we have to do an extra step
in the other parameter's direction ^kwdm904F

De Casteljau ^xaxgofS1

1) Apply de casteljau algorithm in one direction alongside
all parallel line on the grid of control points

2) take all the end points from each parallel line in that grid
and perform de casteljau on it ^Iivkyo2T

But how do we pick the direction?
The results are the same, but the efficient is different!
Pick the direction with the shortest interval distance, that way you do many evaluations
on a short distance and then few evaluations on long distance! ^ou8Y5NzF

i hate limitations, this is so not realistic omg give me something else pls ^DcmA6viE

Parametric Surfaces
of
Irregular Data ^NlJowQFk

Maybe we can try modelling parametric surfaces as height frields.
What this means is that the parameters u and v are already and x and y
coordinates, but we try to model the height z ^SK3ofbrk

Radial Basis Function ^Hfplp5h5

examples ^cvXjdBrp

RBFs are independent of the dimension of the parameter values ^q2DkrnTN

Weighted sum of radial functions one for
each point ^xBQbRJUY

Distance is computed in parameter space ^ft0qnsfc

Least Squared Fitting ^RmDvQ4Nu

Like before we try to Minimize the sum of squared residuals for a fixed class of functions 




such that we find the mesh polynomial that makes the least mistakes when it comes to
the points
for example using a quadratic Polynomial



Which we can represent as a linear system of equations









Resulting in the following ^E4o7ODbR

But you quickly notice a big issue when it comes to this approach
we try to find the best basis function that describes these evaluations
but then we lose all local control, because any error in one end of the parametric curve
will influence the solution in all the others. ^XN4meIyp

Weighted Least Squared Fitting ^oM2dnDM8

Idea:
how about we introduce weight to the equation such that we
only care about the nearby points to influence our current result

How do we choose our weighing function?
The surface is n-times continuously differentiable if and only if the weighting function is too.
thus we need a smooth weighing function.
also we want something that gradually goes down the further you are away
but also goes to zero after a certain distance ^7VpCleDo

Smooth
Doesnt go to zero! ^jwco2VW8

Smooth
Doesnt go to zero! ^j4mHPXEy

Goes to zero
C2 continuous ^cPt5BAyz

Lets build the model: ^xUsmnCN4

# Embedded files
84f5043bc8b2e6f6f6100557a3100a449c566f80: [[Pasted Image 20240426205646_219.png]]
4fccf32be8d4dded4599ec8370ee42b2f5de00ac: [[Pasted Image 20240426210045_260.png]]
bd9529c00bc9bb753fa119f0c9f5ecf9a5872fa6: [[Pasted Image 20240426210618_283.png]]
95873c963abc1b6434c1d39e0d65497e384743a6: [[Pasted Image 20240426210933_323.png]]
4740e964faf6320bbc6d24ddbac89b4841dd069b: [[Pasted Image 20240426211159_382.png]]
baf0f4e50b25832241d46f8e5c25e6fbf797d43e: [[Pasted Image 20240426211159_386.png]]
585d53ddaf37b9f5b94d2ee05776f0693be59fe1: [[Pasted Image 20240426211659_392.png]]
e0223f752c9e55652c97e392afbfcad487075bd1: [[Pasted Image 20240426211842_457.png]]
eed74e29793ce688138123862c8a1193b2d48011: [[Pasted Image 20240426211912_458.png]]
411ce47537d702e3ab73ac185f3b20e7592e4a0d: [[Pasted Image 20240426212359_526.png]]
d4853f377fd013788ffa6b195da9032a32ad05f7: [[Pasted Image 20240426213319_582.png]]
c96063f14e6665777a6d580b5979af2cb91e91d5: [[Pasted Image 20240426213408_587.png]]
ea40523ed8775ec5233b0d3274ea599aa34f4bbf: [[Pasted Image 20240426214137_713.png]]
0ecdabb68a99291d5cf45a698f921a294d9a510d: [[Pasted Image 20240426214207_721.png]]
c296f6eea3a9dde15fb22cdd43fffe363588a9b7: [[Pasted Image 20240426214222_722.png]]
774dfe8f6eb923f14502100a689a0f944cd36d9d: [[Pasted Image 20240426214328_728.png]]
77b1c3c70c6458584bd863ab782235e94ab71ac3: [[Pasted Image 20240426214430_735.png]]
7f234b59f5553c96682e63bea2fb004b9b87eabd: [[Pasted Image 20240426214502_737.png]]
79c4f96b7a009aaee96f869d859e50a82647755e: [[Pasted Image 20240426214522_741.png]]
54e97ce09c31f6742905c5e2d703805b3da685ee: [[Pasted Image 20240426214552_745.png]]
1745cdeb2ccf2cf43873a0dbc9545ede4ee37640: [[Pasted Image 20240426214624_749.png]]
6a9720baef0c2f58b4b49b13d01237fd3461fdc9: [[Pasted Image 20240426214639_750.png]]
b2d5a7fb6edae3eac7e2a1445e886bbe0d493e8c: [[Pasted Image 20240505191748_732.png]]
f55953bdfad301ead4bd294454c9ca9f290df54f: [[Pasted Image 20240505193959_872.png]]
7800ee7ba438d7d9e36e1aaed832b1b5b174522d: [[Pasted Image 20240505194323_904.png]]
5b581acc5a19aebf99e583d4094e70ddfa52215c: [[Pasted Image 20240505195126_030.png]]
f2ac1ba755a55f5e6cafb9544c02fccb4a6e5b12: [[Pasted Image 20240505195214_063.png]]
9db3ccae2d5867d8a77469d67327dcfb40e1aa07: [[Pasted Image 20240505195359_129.png]]
ef06e4f8274e1f2a67dd3f2265c51e85242bb4b0: [[Pasted Image 20240505195744_152.png]]
6528d8b732d36cd55d418bf5afec180fe6cf3f79: [[Pasted Image 20240505202451_425.png]]
e8be897c5c06f49328fc8c05870c30d7a929b52f: [[Pasted Image 20240505202507_435.png]]
c8486e02547241b6d2f0d5923f8b76bb356c207e: [[Pasted Image 20240505202637_445.png]]
6e3ba353ab32371d6c06f3bdd4550d48bf5ab567: [[Pasted Image 20240505202837_489.png]]
3886a838b45484a7ff32beaa5206b6e2f209d1ab: [[Pasted Image 20240505205429_627.png]]
a8554fd4e53a79ec12cc91c520ed111094c44582: [[Pasted Image 20240506190603_223.png]]
5d9eb0f8b9a5e237a04d6e54f0fd89cf1a188f7c: [[Pasted Image 20240506190648_238.png]]
a859458e226e087ceb5b60ddb0fb7ea6cbf89078: [[Pasted Image 20240506190825_280.png]]
c743c8dc4d9e6969c005d7026b4415b37d61b32d: [[Pasted Image 20240506192635_105.png]]
6044722cac12995d29b39c2dc2dddcb98b00727f: [[Pasted Image 20240506192750_116.png]]
ce86d18e727c4dc772f91a727a73c14bf356b675: [[Pasted Image 20240506194629_355.png]]
a62e5411e0a92ca5c4ac4441371d28020d0e239b: [[Pasted Image 20240506194729_365.png]]
7f0c87bb06ca8a4604e1bc8b59eb0fd80dd826c1: [[Pasted Image 20240506194829_371.png]]
2051be5b548c025a89af9335f5c4b968751c0583: [[Pasted Image 20240506195015_412.png]]
f73a276784a880ffcf516c0cf1597cbe9413317d: [[Pasted Image 20240506200816_873.png]]
c39949c5fda3ffd6877fb2d26b814559cb0bd0d5: [[Pasted Image 20240506201812_991.png]]
a2de4e34f1bf91111d4aa9c1a056860b4943c123: [[Pasted Image 20240506201943_010.png]]
559f3a8430eb1fe05c281e187e8c66271bf23074: [[Pasted Image 20240506202058_028.png]]
5f0d0c2fc2aa7db33e1a4c9fa358f881836c2004: [[Pasted Image 20240506202843_069.png]]
a893d0602ec69fff13c86306edddd75f8f955e94: [[Pasted Image 20240506210139_218.png]]
654475de15875789ddc830bc83830d06e64ffc6d: [[Pasted Image 20240506210229_235.png]]
b5e88439ee2264f116b1db93f8f122af32cab3ef: [[Pasted Image 20240506210545_258.png]]
b01ea08c25d66c649c5f4692cc8b9d37ea266711: [[Pasted Image 20240510141400_825.png]]
ee1c1c78dc92d17803633bf673f965a956eb02c1: [[Pasted Image 20240510142125_900.png]]
f8644b730f93b1536978ae6a05cd9a5d96ec3d6b: [[Pasted Image 20240512191623_856.png]]
27d81010cce038f0d3deec61a2c228f84f75e8a9: [[Pasted Image 20240512191843_555.png]]
7de1906c842673977844b07a0ffccfb2a85ee143: [[Pasted Image 20240512191913_563.png]]
f4fd33f0d902a7a109bbc14089df4d14f27031c2: [[Pasted Image 20240512192019_600.png]]
cb28b693cd70c1347d9ac086a579cf9de11e5e50: [[Pasted Image 20240512192034_602.png]]
9575241c5f1323a06c53ec5bec974844714111be: [[Pasted Image 20240512192105_604.png]]
2d98be3d150c4587e78f5db6eed0d111979125b6: [[Pasted Image 20240512192254_637.png]]
ad0e346915cd4bea3b30b3f84eaae19adbf23223: [[Pasted Image 20240512192906_909.png]]
0e628a0503e697924c6e163f3f26f312f98a3b55: [[Pasted Image 20240512192922_926.png]]
860e20fbb566e07529ac9d0f86dba342bc5d67b6: [[Pasted Image 20240512193009_935.png]]
a15a420a15e689a2e4e10d5fcb20235810ef2397: [[Pasted Image 20240512193322_019.png]]
dc6c361e912582a77d1f1b09e7ec15e6dc1c15a1: [[Pasted Image 20240512194931_128.png]]
133b8f571062ba985f1fe7df4ce5f8affa26a8ee: [[Pasted Image 20240512195136_163.png]]
67af7863c29a3caec28f7c4ef45711f6b8cbcd70: [[Pasted Image 20240512195306_192.png]]
e03708358f627113a4816ace6d4964a4c0e868fa: [[Pasted Image 20240512195506_210.png]]
60cfd2f1fb408b0a0ee940f5bbc7b7e808e3b9fa: [[Pasted Image 20240512195707_239.png]]
56e222b9f871e806cd159f3cbdb6634c376a7a53: [[Pasted Image 20240512204817_404.png]]
99b922a2f75f96015c6b98b6e846e929d57cd840: [[Pasted Image 20240512204834_427.png]]
88dc1661372a46ea7749cb05565fb996f47669a7: [[Pasted Image 20240512205018_475.png]]
51633ffc1e5aebfb86adf0645bf68220421c581d: [[Pasted Image 20240512205153_518.png]]
78bb1d2affc61c00948d7c215371908d949e3762: [[Pasted Image 20240512205223_529.png]]
7cc8974534cb0e253ec0c6b749c8791ad8364bcb: [[Pasted Image 20240512205338_549.png]]
2a743352c26e52c14124754fb8326b722921251b: [[Pasted Image 20240512205528_603.png]]
722952b95e8e50ed794c7c934087e2faaf97c4d6: [[Pasted Image 20240512205707_641.png]]
cc8b0f5d67acc0678f8be5cf3df584a13ddce52c: [[Pasted Image 20240512205722_646.png]]
7ff0c2a264427fed4b2fb2d414ca1650ebbb3672: [[Pasted Image 20240512211721_851.png]]
baffbd8054c8c98e4fc47fb9fe4c5aeb6c711db4: [[Pasted Image 20240512212027_907.png]]
818d60d5f592c896250c82be48fc7185bed23feb: [[Pasted Image 20240512212133_924.png]]
f7fd5e6b9125c966d8509897a9215bcb97032cd0: [[Pasted Image 20240512212335_965.png]]
bbb7c4aad8d733fe0437932289624c167d32518d: [[Pasted Image 20240512212435_978.png]]
a8919df9e561344551c5f338aa454211cdbcb1cb: [[Pasted Image 20240512212720_995.png]]
f9e859db0079a1a510eec317f28cb6acd0a4ce81: [[Pasted Image 20240512212737_004.png]]
d97a5bc59d1fa1cdd2ec8913b5d30c2c640d7037: [[Pasted Image 20240512212852_017.png]]
7c5f5f52983d266fad9a971b71692d73e4d01b7a: [[Pasted Image 20240512213304_105.png]]
30d6e30b6f442aa9be14353f1cf64378c9adb9bf: [[Pasted Image 20240512213341_118.png]]
0dbd0e385cd29db3dc16542bf84442b33840e7c5: [[Pasted Image 20240512213412_123.png]]
87b3ea6147160b353d2453160c4711221929c322: [[Pasted Image 20240512213727_171.png]]
a05f99e6edf76d383d73b9bc33a3defba3028701: [[Pasted Image 20240512213743_187.png]]

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
			"version": 267,
			"versionNonce": 348792779,
			"isDeleted": false,
			"id": "k8dUbD1pYPNHX4CKGJGAy",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1407.612274466727,
			"y": 534.4829942340093,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 295.9349703867156,
			"height": 80.57919251808826,
			"seed": 85722673,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					295.9349703867156,
					8.02924338258535
				],
				[
					253.49468393590752,
					-45.59463206539512
				],
				[
					162.30541980511725,
					-72.54994913550291
				],
				[
					63.947188368447314,
					-66.81477529079916
				],
				[
					0.28675869223525297,
					2.294069537881512
				]
			]
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 304434789,
			"isDeleted": false,
			"id": "5YwjuiWH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.786556584035055,
			"x": 1630.546363119461,
			"y": -2253.6701357275115,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.868927001953125,
			"height": 56.48807091654578,
			"seed": 45620,
			"groupIds": [
				"LWRzflmA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "P",
			"rawText": "P",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "P",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 141096555,
			"isDeleted": false,
			"id": "noqCvc54",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.909943730031149,
			"x": 1657.619120406926,
			"y": -2266.248349893443,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 30.140045166015625,
			"height": 56.48807091654578,
			"seed": 36784,
			"groupIds": [
				"LWRzflmA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 1201158597,
			"isDeleted": false,
			"id": "GpjbApZV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.03445087114443,
			"x": 1686.2968705446365,
			"y": -2275.4658730767997,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 19.430618286132812,
			"height": 56.48807091654578,
			"seed": 74226,
			"groupIds": [
				"LWRzflmA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "r",
			"rawText": "r",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 1215623435,
			"isDeleted": false,
			"id": "HvaptkyZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.114717899953024,
			"x": 1705.302497449818,
			"y": -2279.4889887676654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 30.140045166015625,
			"height": 56.48807091654578,
			"seed": 65314,
			"groupIds": [
				"LWRzflmA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 1515632933,
			"isDeleted": false,
			"id": "5nYUI97E",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.239225041066305,
			"x": 1735.2554283396923,
			"y": -2282.682422296498,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 28.603668212890625,
			"height": 56.48807091654578,
			"seed": 58801,
			"groupIds": [
				"LWRzflmA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "m",
			"rawText": "m",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "m",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 644388779,
			"isDeleted": false,
			"id": "8ElM2M6t",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.07420023600260416,
			"x": 1763.841202808755,
			"y": -2282.250172876977,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.717544555664062,
			"height": 56.48807091654578,
			"seed": 35954,
			"groupIds": [
				"LWRzflmA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "e",
			"rawText": "e",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "e",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 1137593477,
			"isDeleted": false,
			"id": "io9juNly",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.176307373046875,
			"x": 1788.3561925541417,
			"y": -2279.1634180346273,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 25.530929565429688,
			"height": 56.48807091654578,
			"seed": 89044,
			"groupIds": [
				"LWRzflmA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "t",
			"rawText": "t",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 1617848907,
			"isDeleted": false,
			"id": "vDzIK69P",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.28177449544270833,
			"x": 1813.2105905532205,
			"y": -2273.3690639012743,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 19.430618286132812,
			"height": 56.48807091654578,
			"seed": 62053,
			"groupIds": [
				"LWRzflmA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "r",
			"rawText": "r",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 1941730277,
			"isDeleted": false,
			"id": "jcrnEVxn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.3620415242513021,
			"x": 1831.6394733434745,
			"y": -2267.222878659669,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.89605712890625,
			"height": 56.48807091654578,
			"seed": 97932,
			"groupIds": [
				"LWRzflmA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "i",
			"rawText": "i",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 190900459,
			"isDeleted": false,
			"id": "So8jcN3b",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.4029216512044271,
			"x": 1840.820449206541,
			"y": -2263.5294357950565,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 22.684112548828125,
			"height": 56.48807091654578,
			"seed": 56713,
			"groupIds": [
				"LWRzflmA"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "c",
			"rawText": "c",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "c",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 433,
			"versionNonce": 103722821,
			"isDeleted": false,
			"id": "F9LmUaje",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.30380126953125,
			"x": 1882.6601906438918,
			"y": -2236.2257599841123,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.100738525390625,
			"height": 56.48807091654578,
			"seed": 88497,
			"groupIds": [
				"H6HMueph"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "C",
			"rawText": "C",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "C",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 433,
			"versionNonce": 1019909003,
			"isDeleted": false,
			"id": "tpPpKWsG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.18358744303385416,
			"x": 1910.886066954355,
			"y": -2229.2077949189406,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 25.666488647460938,
			"height": 56.48807091654578,
			"seed": 32830,
			"groupIds": [
				"H6HMueph"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "u",
			"rawText": "u",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "u",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 433,
			"versionNonce": 964853413,
			"isDeleted": false,
			"id": "8gxy3kls",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.07756032307942708,
			"x": 1936.323931421821,
			"y": -2225.8672677488134,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 19.430618286132812,
			"height": 56.48807091654578,
			"seed": 82011,
			"groupIds": [
				"H6HMueph"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "r",
			"rawText": "r",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "r",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 433,
			"versionNonce": 1961224747,
			"isDeleted": false,
			"id": "Ek9wKRuT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.28047860145042,
			"x": 1955.7370948060345,
			"y": -2225.140355554056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.633041381835938,
			"height": 56.48807091654578,
			"seed": 34117,
			"groupIds": [
				"H6HMueph"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "v",
			"rawText": "v",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "v",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 433,
			"versionNonce": 610624005,
			"isDeleted": false,
			"id": "JL8YURhm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.182851546600159,
			"x": 1979.331064986617,
			"y": -2226.356999048899,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.717544555664062,
			"height": 56.48807091654578,
			"seed": 16693,
			"groupIds": [
				"H6HMueph"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "e",
			"rawText": "e",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "e",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 433,
			"versionNonce": 1218276555,
			"isDeleted": false,
			"id": "rv62rBHM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 6.080744409555888,
			"x": 2003.7570252144837,
			"y": -2230.0832900493265,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 24.53680419921875,
			"height": 56.48807091654578,
			"seed": 58509,
			"groupIds": [
				"H6HMueph"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 45.19045673323662,
			"fontFamily": 1,
			"text": "s",
			"rawText": "s",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "s",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 623,
			"versionNonce": 735369573,
			"isDeleted": false,
			"id": "n1aw92QJJNz00_yJzc1g2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1606.789700420586,
			"y": -2175.0379754540963,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 494.01816317401983,
			"height": 63.6941656922478,
			"seed": 1927475175,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					68.35471440143678,
					-39.61466402810537
				],
				[
					151.46783304863817,
					-56.70334262846454
				],
				[
					225.2598542774619,
					-44.275212737294254
				],
				[
					279.63292255133206,
					-14.758404245764753
				],
				[
					346.4341207163724,
					6.99082306378326
				],
				[
					425.66344877258314,
					-3.883790590990746
				],
				[
					494.01816317401983,
					-50.489277682879425
				]
			]
		},
		{
			"type": "text",
			"version": 347,
			"versionNonce": 1267440491,
			"isDeleted": false,
			"id": "fT0xLd5O",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1565.9929301160682,
			"y": -2146.7635738715926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 539.699462890625,
			"height": 50,
			"seed": 1578795175,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Parametric surfaces and curves can be represented in\ntwo ways",
			"rawText": "Parametric surfaces and curves can be represented in\ntwo ways",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Parametric surfaces and curves can be represented in\ntwo ways",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 819,
			"versionNonce": 958293189,
			"isDeleted": false,
			"id": "UG9BSyn_9bljt2jJIa4yi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1982.0130305528774,
			"y": -2104.2120568047717,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 116.33096856086027,
			"height": 128.21348500681245,
			"seed": 2141408265,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "2Qi3LCtI",
				"focus": -0.002025665513525155,
				"gap": 4.261647671251694
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
					99.32661573800911,
					7.509058873668266
				],
				[
					116.33096856086027,
					128.21348500681245
				]
			]
		},
		{
			"type": "arrow",
			"version": 844,
			"versionNonce": 972748299,
			"isDeleted": false,
			"id": "Ka2DEXHQ0LZMy1XJpcQnW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1683.1545152194178,
			"y": -2102.245164659305,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 113.72304227620575,
			"height": 127.41661614734232,
			"seed": 410407369,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "eAjFL0E2",
				"focus": -0.0024693614497535927,
				"gap": 3.0916241444751904
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
					-99.32661573800911,
					7.509058873668266
				],
				[
					-113.72304227620575,
					127.41661614734232
				]
			]
		},
		{
			"type": "text",
			"version": 295,
			"versionNonce": 803177509,
			"isDeleted": false,
			"id": "2Qi3LCtI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1936.143460524909,
			"y": -1971.7369241267077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 331.21337890625,
			"height": 35,
			"seed": 775164871,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "UG9BSyn_9bljt2jJIa4yi",
					"type": "arrow"
				}
			],
			"updated": 1715542501114,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Explicit Representations",
			"rawText": "Explicit Representations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Explicit Representations",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 343,
			"versionNonce": 1659239595,
			"isDeleted": false,
			"id": "eAjFL0E2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1402.576619737972,
			"y": -1971.7369243674875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 329.5893859863281,
			"height": 35,
			"seed": 1928410727,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ka2DEXHQ0LZMy1XJpcQnW",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Implicit Representations",
			"rawText": "Implicit Representations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Implicit Representations",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 272,
			"versionNonce": 604354437,
			"isDeleted": false,
			"id": "VYLgJdd1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1960.6196589039582,
			"y": -1918.4277748406153,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 89.73988342285156,
			"height": 25,
			"seed": 130698249,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p: R -> R",
			"rawText": "p: R -> R",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p: R -> R",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 295,
			"versionNonce": 1375153995,
			"isDeleted": false,
			"id": "3mjZudZx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2051.528877743753,
			"y": -1925.0692679618462,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.104019165039062,
			"height": 20,
			"seed": 2005232519,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "d",
			"rawText": "d",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "d",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 316,
			"versionNonce": 1338932965,
			"isDeleted": false,
			"id": "0gnGDzMM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1987.8616316036848,
			"y": -1891.7301021831574,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 49.219940185546875,
			"height": 25,
			"seed": 279826281,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "t -> ",
			"rawText": "t -> ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t -> ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 393,
			"versionNonce": 965283307,
			"isDeleted": false,
			"id": "JurLOYvT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2035.4908765403316,
			"y": -1892.6749555261692,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 259.7996826171875,
			"height": 25,
			"seed": 238450823,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p(t) = [ x(t) , y(t), z(t) ]",
			"rawText": "p(t) = [ x(t) , y(t), z(t) ]",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p(t) = [ x(t) , y(t), z(t) ]",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 260,
			"versionNonce": 1237801541,
			"isDeleted": false,
			"id": "XaB3Z6k7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2094.134398044204,
			"y": -1855.9591729980436,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 74.23991394042969,
			"height": 25,
			"seed": 131267977,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "example",
			"rawText": "example",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "example",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 328,
			"versionNonce": 480647307,
			"isDeleted": false,
			"id": "yP55BnEk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1983.1693509411994,
			"y": -1820.2882319808566,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 265.5396728515625,
			"height": 50,
			"seed": 1147851751,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "t = [0,2Pi]\np(t) = r( cos(t), sin(t), 0) ",
			"rawText": "t = [0,2Pi]\np(t) = r( cos(t), sin(t), 0) ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t = [0,2Pi]\np(t) = r( cos(t), sin(t), 0) ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 284,
			"versionNonce": 2060306853,
			"isDeleted": false,
			"id": "Gxg57rWL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1416.472617107552,
			"y": -1911.120126161806,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 89.59988403320312,
			"height": 25,
			"seed": 911693735,
			"groupIds": [
				"RotgcUUMXSgR6rb6nfcRh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "f: R -> R",
			"rawText": "f: R -> R",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f: R -> R",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 386,
			"versionNonce": 956878635,
			"isDeleted": false,
			"id": "gIZahTtu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1455.2342350794677,
			"y": -1917.8511731388298,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.104019165039062,
			"height": 20,
			"seed": 1512692935,
			"groupIds": [
				"RotgcUUMXSgR6rb6nfcRh"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "d",
			"rawText": "d",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "d",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 274,
			"versionNonce": 1410288901,
			"isDeleted": false,
			"id": "ExhaaYjA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1441.7081193410954,
			"y": -1883.0950088358295,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 340.87957763671875,
			"height": 25,
			"seed": 874350407,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p -> f( p(x,y) ) = x^2 + y^2 - r^2",
			"rawText": "p -> f( p(x,y) ) = x^2 + y^2 - r^2",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p -> f( p(x,y) ) = x^2 + y^2 - r^2",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 292,
			"versionNonce": 823898571,
			"isDeleted": false,
			"id": "X0My576R",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1445.3742185671858,
			"y": -1845.2119834995638,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 358.799560546875,
			"height": 25,
			"seed": 1796688135,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "if f(p) = 0 then p is on the surface",
			"rawText": "if f(p) = 0 then p is on the surface",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "if f(p) = 0 then p is on the surface",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 314,
			"versionNonce": 1158243429,
			"isDeleted": false,
			"id": "ZiqxbSr1HRo1YnoGCcy5a",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1578.202727357113,
			"y": -1792.888122437941,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 161.60719628017597,
			"height": 172.71769102443807,
			"seed": 1230698631,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
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
					3.0301349302533254,
					160.59715130342488
				],
				[
					161.60719628017597,
					172.71769102443807
				]
			]
		},
		{
			"type": "arrow",
			"version": 546,
			"versionNonce": 1979269227,
			"isDeleted": false,
			"id": "E8c8nWBNZ4anxVI-Z_e6n",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2130.6973296399647,
			"y": -1741.3758286236352,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 207.05922023397557,
			"height": 120.71061905875172,
			"seed": 1883211911,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "dLJhlHL8",
				"focus": -0.33634111258727806,
				"gap": 15.854329984122614
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
					-6.060269860506651,
					114.13508237287442
				],
				[
					-207.05922023397557,
					120.71061905875172
				]
			]
		},
		{
			"type": "text",
			"version": 248,
			"versionNonce": 1904840645,
			"isDeleted": false,
			"id": "dLJhlHL8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1768.0911829863196,
			"y": -1640.3211060647695,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 139.69259643554688,
			"height": 70,
			"seed": 363551625,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "E8c8nWBNZ4anxVI-Z_e6n",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Properties\nof Curves",
			"rawText": "Properties\nof Curves",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Properties\nof Curves",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 352,
			"versionNonce": 1902902027,
			"isDeleted": false,
			"id": "UrGZMCK7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1473.0061068844607,
			"y": -1555.7025451327368,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 723.7991943359375,
			"height": 75,
			"seed": 1496661063,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets take the curve segment [a,b]\nThis curve segment can be parameterized differently even if its modelling\nthe exact same line",
			"rawText": "Lets take the curve segment [a,b]\nThis curve segment can be parameterized differently even if its modelling\nthe exact same line",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets take the curve segment [a,b]\nThis curve segment can be parameterized differently even if its modelling\nthe exact same line",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 365,
			"versionNonce": 665669413,
			"isDeleted": false,
			"id": "mRyZeIfy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1640.3658507134446,
			"y": -1471.5103740534498,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 205.85972595214844,
			"height": 75,
			"seed": 222435335,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p(t) = t a + (1-t) b\n\np(t) = t a + (1-t ) b",
			"rawText": "p(t) = t a + (1-t) b\n\np(t) = t a + (1-t ) b",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p(t) = t a + (1-t) b\n\np(t) = t a + (1-t ) b",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 362,
			"versionNonce": 1877893547,
			"isDeleted": false,
			"id": "cMLN87L1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1719.7745658383521,
			"y": -1425.2072225762615,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.39202880859375,
			"height": 20,
			"seed": 1085117671,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
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
			"type": "text",
			"version": 356,
			"versionNonce": 367141509,
			"isDeleted": false,
			"id": "BuFGq633",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1808.5943779871068,
			"y": -1428.1477626133305,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.39202880859375,
			"height": 20,
			"seed": 11106119,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
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
			"type": "line",
			"version": 308,
			"versionNonce": 1252717643,
			"isDeleted": false,
			"id": "BaJm9vakK9qd2ChSyahdo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1883.5403798388402,
			"y": -1454.9231340016372,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 226.1377169992606,
			"height": 1.183967104708188,
			"seed": 1151146535,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					226.1377169992606,
					-1.183967104708188
				]
			]
		},
		{
			"type": "ellipse",
			"version": 304,
			"versionNonce": 1088784869,
			"isDeleted": false,
			"id": "6igxbhZRweXurzRAiZwaq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1871.7007087917584,
			"y": -1463.2109037345945,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.207605256498084,
			"height": 15.391572361206158,
			"seed": 437775209,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 326,
			"versionNonce": 1367093995,
			"isDeleted": false,
			"id": "Xy8DA1qix5TfT8OC4ZFQW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2111.4540474951627,
			"y": -1463.8028872869486,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.207605256498084,
			"height": 15.391572361206158,
			"seed": 2147302343,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 289,
			"versionNonce": 969213253,
			"isDeleted": false,
			"id": "DiMLqNps",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1871.692546969,
			"y": -1483.9303280669874,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.672027587890625,
			"height": 20,
			"seed": 2022251817,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "3XxdqxCr1LgRNFrjHwuxi",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 273,
			"versionNonce": 1961663883,
			"isDeleted": false,
			"id": "F4S9Xw1K",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2115.677806608003,
			"y": -1482.7463609622794,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.128021240234375,
			"height": 20,
			"seed": 1269641351,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "K80gaqYW0UB-ellML10Xs",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "b",
			"rawText": "b",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "b",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 323,
			"versionNonce": 333321381,
			"isDeleted": false,
			"id": "djC68i7WqNC-ClrLHJjW4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1884.4324360787505,
			"y": -1406.6764744847796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 226.1377169992606,
			"height": 1.183967104708188,
			"seed": 946282761,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					226.1377169992606,
					-1.183967104708188
				]
			]
		},
		{
			"type": "ellipse",
			"version": 320,
			"versionNonce": 808891435,
			"isDeleted": false,
			"id": "HYcqwdHUQYYyw7W8p1bID",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1872.5927650316687,
			"y": -1414.9642442177365,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.207605256498084,
			"height": 15.391572361206158,
			"seed": 584062953,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "j40EC-nKnBARVZNNL5RW2",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 341,
			"versionNonce": 450770949,
			"isDeleted": false,
			"id": "pmmA1uvkZacYp1A-BL96I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2112.3461037350735,
			"y": -1415.5562277700908,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.207605256498084,
			"height": 15.391572361206158,
			"seed": 112669385,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 305,
			"versionNonce": 860157643,
			"isDeleted": false,
			"id": "Z3gWGyo1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1872.5846032089103,
			"y": -1435.6836685501298,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 10.672027587890625,
			"height": 20,
			"seed": 1488449961,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 288,
			"versionNonce": 1220734821,
			"isDeleted": false,
			"id": "jltDQjux",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2116.569862847913,
			"y": -1434.4997014454216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.128021240234375,
			"height": 20,
			"seed": 1845351561,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "FREL9qYnAlHrmBfLWGWhi",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "b",
			"rawText": "b",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "b",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 419,
			"versionNonce": 1286727019,
			"isDeleted": false,
			"id": "K80gaqYW0UB-ellML10Xs",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2109.878986249683,
			"y": -1456.1363462794616,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 30.28430297175896,
			"height": 0.7866052719937215,
			"seed": 972978217,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "F4S9Xw1K",
				"focus": -1.6183011461443377,
				"gap": 6.610014682817791
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
					-30.28430297175896,
					0.7866052719937215
				]
			]
		},
		{
			"type": "arrow",
			"version": 229,
			"versionNonce": 2077866693,
			"isDeleted": false,
			"id": "aR7YFvc2SBKb-61Qy5bTJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2089.8205518138425,
			"y": -1456.5296489154584,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 35.39723723971821,
			"height": 0.7866052719937215,
			"seed": 1931980423,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
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
					-35.39723723971821,
					0.7866052719937215
				]
			]
		},
		{
			"type": "arrow",
			"version": 292,
			"versionNonce": 331874315,
			"isDeleted": false,
			"id": "4080ryw0z7eKmZpBfSJza",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2063.0759725660555,
			"y": -1456.1363462794616,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 35.39723723971821,
			"height": 0.39330263599686077,
			"seed": 1543019913,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
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
					-35.39723723971821,
					0.39330263599686077
				]
			]
		},
		{
			"type": "arrow",
			"version": 230,
			"versionNonce": 1824528933,
			"isDeleted": false,
			"id": "bEtSSEGSt2tXS_8zSjFHj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2037.117998590262,
			"y": -1456.1363462794616,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 36.97044778370571,
			"height": 0.39330263599686077,
			"seed": 151811655,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
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
					-36.97044778370571,
					-0.39330263599686077
				]
			]
		},
		{
			"type": "arrow",
			"version": 258,
			"versionNonce": 1384236715,
			"isDeleted": false,
			"id": "El34aNnPNYXvaBDDkvXPs",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2009.586814070481,
			"y": -1456.9229515514553,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 35.39723723971821,
			"height": 1.573210543987443,
			"seed": 986798249,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
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
					-35.39723723971821,
					1.573210543987443
				]
			]
		},
		{
			"type": "arrow",
			"version": 230,
			"versionNonce": 1684245893,
			"isDeleted": false,
			"id": "Naq1eCDrAJr8bzrYevGr5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1983.6288400946878,
			"y": -1455.3497410074679,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 36.57714514770885,
			"height": 0,
			"seed": 321912551,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
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
					-36.57714514770885,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 231,
			"versionNonce": 797555019,
			"isDeleted": false,
			"id": "T7GqLKCG3j9uiu6ONq-Gh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1957.2775634828977,
			"y": -1456.1363462794616,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 37.36375041970257,
			"height": 0.39330263599686077,
			"seed": 1477659145,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
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
					-37.36375041970257,
					0.39330263599686077
				]
			]
		},
		{
			"type": "arrow",
			"version": 430,
			"versionNonce": 838964453,
			"isDeleted": false,
			"id": "3XxdqxCr1LgRNFrjHwuxi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1927.7798657831324,
			"y": -1455.7430436434647,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 34.61063196772449,
			"height": 0,
			"seed": 213863207,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "DiMLqNps",
				"focus": 1.818728442352267,
				"gap": 10.804659258517404
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
					-34.61063196772449,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 454,
			"versionNonce": 406476779,
			"isDeleted": false,
			"id": "FREL9qYnAlHrmBfLWGWhi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2105.9459598897142,
			"y": -1408.9400299598371,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 35.39723723971821,
			"height": 0.7866052719937215,
			"seed": 889587913,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jltDQjux",
				"focus": -1.5096930988580162,
				"gap": 10.623902958198869
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
					-35.39723723971821,
					0.7866052719937215
				]
			]
		},
		{
			"type": "arrow",
			"version": 248,
			"versionNonce": 1629990981,
			"isDeleted": false,
			"id": "jHGQnjbaPSFB4i0FWyECM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2080.3812885499174,
			"y": -1409.3333325958342,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 53.4891584955742,
			"height": 1.5732105439875,
			"seed": 1398051943,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
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
					-53.4891584955742,
					1.5732105439875
				]
			]
		},
		{
			"type": "arrow",
			"version": 271,
			"versionNonce": 1788748427,
			"isDeleted": false,
			"id": "I-CD2dgQEExOATv_M-I6W",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2042.2309328582214,
			"y": -1407.7601220518466,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 73.94089556741136,
			"height": 0.7866052719937215,
			"seed": 1506364489,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
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
					-73.94089556741136,
					0.7866052719937215
				]
			]
		},
		{
			"type": "arrow",
			"version": 491,
			"versionNonce": 800284581,
			"isDeleted": false,
			"id": "j40EC-nKnBARVZNNL5RW2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1992.281498086619,
			"y": -1407.7601220518466,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 90.85290891527677,
			"height": 1.5732105439875,
			"seed": 1683595751,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "HYcqwdHUQYYyw7W8p1bID",
				"focus": 0.18941175837019114,
				"gap": 14.65367325799529
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
					-90.85290891527677,
					1.5732105439875
				]
			]
		},
		{
			"type": "text",
			"version": 638,
			"versionNonce": 1601149227,
			"isDeleted": false,
			"id": "7x6Nbo3U",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1295.8661408280338,
			"y": -1349.7119009684607,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1100.7188720703125,
			"height": 400,
			"seed": 655646377,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) A parametric curve is n times continuously differentiable if the mapping is n times continuously differentiable.\n\n2) A curve is regular if the first derivative of p exists and p'(t) != 0 for all t.\nThis regularity describes smoothness of a curve, and a curve is only regular if\nit has no kinks (im not gonna judge if it does)\n\n3) Arclength of a curve\n\n\n\n\nWhich calculates the length of the curve via an integral of its derivative\nwhich is not very analytically easy to compute \n\n\n4) Curvature is the magnitude of the curve vector",
			"rawText": "1) A parametric curve is n times continuously differentiable if the mapping is n times continuously differentiable.\n\n2) A curve is regular if the first derivative of p exists and p'(t) != 0 for all t.\nThis regularity describes smoothness of a curve, and a curve is only regular if\nit has no kinks (im not gonna judge if it does)\n\n3) Arclength of a curve\n\n\n\n\nWhich calculates the length of the curve via an integral of its derivative\nwhich is not very analytically easy to compute \n\n\n4) Curvature is the magnitude of the curve vector",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) A parametric curve is n times continuously differentiable if the mapping is n times continuously differentiable.\n\n2) A curve is regular if the first derivative of p exists and p'(t) != 0 for all t.\nThis regularity describes smoothness of a curve, and a curve is only regular if\nit has no kinks (im not gonna judge if it does)\n\n3) Arclength of a curve\n\n\n\n\nWhich calculates the length of the curve via an integral of its derivative\nwhich is not very analytically easy to compute \n\n\n4) Curvature is the magnitude of the curve vector",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 560,
			"versionNonce": 1137844997,
			"isDeleted": false,
			"id": "dJ-ZPyjzRd38v-6J6yZvA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2080.225615983217,
			"y": -1450.7088136762159,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 215.1533603317548,
			"height": 62.01111731627583,
			"seed": 1241998089,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					154.35375940681695,
					62.01111731627583
				],
				[
					215.1533603317548,
					55.17611485879638
				]
			]
		},
		{
			"type": "text",
			"version": 394,
			"versionNonce": 874068939,
			"isDeleted": false,
			"id": "dmdoNNVC",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2198.6795980759757,
			"y": -1464.1828807794825,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 490.72100830078125,
			"height": 80,
			"seed": 961562471,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The derivative p'(t) of p at t is a vector, which provides the\ntangential direction of the curve at that position. \nand the magnitude can be seen the as the strength\nof the steps in that direction",
			"rawText": "The derivative p'(t) of p at t is a vector, which provides the\ntangential direction of the curve at that position. \nand the magnitude can be seen the as the strength\nof the steps in that direction",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The derivative p'(t) of p at t is a vector, which provides the\ntangential direction of the curve at that position. \nand the magnitude can be seen the as the strength\nof the steps in that direction",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 311,
			"versionNonce": 570522213,
			"isDeleted": false,
			"id": "1f9sTp2ZQ7xC7SYegxPn5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1449.0571766158582,
			"y": -1256.291461238788,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 291.48862427686674,
			"height": 38.54395031760225,
			"seed": 526380649,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					-167.02378470960957,
					36.937952387702126
				],
				[
					-291.48862427686674,
					38.54395031760225
				]
			]
		},
		{
			"type": "arrow",
			"version": 361,
			"versionNonce": 347441771,
			"isDeleted": false,
			"id": "ZCKP88jZdu9gkIWpQNO_R",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 892.5335023828322,
			"y": -1170.770057953578,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 254.6473184294652,
			"height": 1.5783924696041205,
			"seed": 872437193,
			"groupIds": [
				"tw0NicmD3WSauwGJpLwxT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					254.6473184294652,
					1.5783924696041205
				]
			]
		},
		{
			"type": "arrow",
			"version": 346,
			"versionNonce": 1661920709,
			"isDeleted": false,
			"id": "BuK1NUZ242oLrNzlsnR6g",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1019.3310307743634,
			"y": -1169.7177963071754,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.5783924696041205,
			"height": 203.0864977557305,
			"seed": 1052563655,
			"groupIds": [
				"tw0NicmD3WSauwGJpLwxT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					1.5783924696041205,
					-203.0864977557305
				]
			]
		},
		{
			"type": "line",
			"version": 766,
			"versionNonce": 1175389451,
			"isDeleted": false,
			"id": "hl21olOAHWvl-63RYM_eD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 897.794810614846,
			"y": -1338.079659731615,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 244.65083278863898,
			"height": 166.2573401316343,
			"seed": 1329632905,
			"groupIds": [
				"tw0NicmD3WSauwGJpLwxT"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					48.93016655772774,
					28.937195276075595
				],
				[
					83.12867006581712,
					92.59902488344187
				],
				[
					108.90908040268432,
					143.63371473397518
				],
				[
					115.74878110430222,
					157.31311613721093
				],
				[
					122.58848180592013,
					166.2573401316343
				],
				[
					128.9020516843366,
					157.83924696041228
				],
				[
					136.2678832091558,
					145.2121072035793
				],
				[
					155.2085928444053,
					95.75580982265008
				],
				[
					192.56388129170293,
					30.515587745679714
				],
				[
					244.65083278863898,
					8.944223994423375
				]
			]
		},
		{
			"type": "text",
			"version": 370,
			"versionNonce": 706209061,
			"isDeleted": false,
			"id": "eYqXMJUf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 786.5013121622269,
			"y": -1144.6746051107318,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 432.1768798828125,
			"height": 40,
			"seed": 1675520679,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "example of an irregular continuously differential curve!\nderivative at 0 is 0",
			"rawText": "example of an irregular continuously differential curve!\nderivative at 0 is 0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "example of an irregular continuously differential curve!\nderivative at 0 is 0",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 264,
			"versionNonce": 262155179,
			"isDeleted": false,
			"id": "oEwi3o6RUl6QXpov9AmiB",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1714.3859146840186,
			"y": -1171.7321098105858,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 287.6606544889087,
			"height": 82.48089856198567,
			"seed": 1042773961,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "84f5043bc8b2e6f6f6100557a3100a449c566f80",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 577,
			"versionNonce": 1518991493,
			"isDeleted": false,
			"id": "NDXfIkxGhRuOTJnncKzvC",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2035.1279152423756,
			"y": -1153.5354181644057,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 158.4228869047529,
			"height": 47.302586447567364,
			"seed": 515706375,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "p3aBNQZX",
				"focus": 0.19456120040707262,
				"gap": 14.190775934270278
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
					77.57624177401055,
					-47.302586447567364
				],
				[
					158.4228869047529,
					-30.273655326443077
				]
			]
		},
		{
			"type": "text",
			"version": 419,
			"versionNonce": 1704164939,
			"isDeleted": false,
			"id": "p3aBNQZX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2120.4718326359234,
			"y": -1169.6182975565785,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 427.21685791015625,
			"height": 60,
			"seed": 143545767,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "NDXfIkxGhRuOTJnncKzvC",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "a curve is parameteried by its arclength if the length\nof its derivative is 1 everywhere\nwhich only happens if the curve is regular!",
			"rawText": "a curve is parameteried by its arclength if the length\nof its derivative is 1 everywhere\nwhich only happens if the curve is regular!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a curve is parameteried by its arclength if the length\nof its derivative is 1 everywhere\nwhich only happens if the curve is regular!",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 275,
			"versionNonce": 237150181,
			"isDeleted": false,
			"id": "oS-AeU4xmvSOI83xFmNKl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1747.1017077682136,
			"y": -940.0109296885516,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 222.22906832051936,
			"height": 58.58187474351799,
			"seed": 1605154057,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4fccf32be8d4dded4599ec8370ee42b2f5de00ac",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 406,
			"versionNonce": 1388543211,
			"isDeleted": false,
			"id": "CjpfveVGj8OaGtJpwi_ze",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1700.229630956345,
			"y": 599.671417291386,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 366.3733828609658,
			"height": 206.51941364520565,
			"seed": 296102567,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "baf0f4e50b25832241d46f8e5c25e6fbf797d43e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 322,
			"versionNonce": 1257200453,
			"isDeleted": false,
			"id": "iQ20T3z4",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1791.4990608567157,
			"y": 470.8566040487076,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 177.40875244140625,
			"height": 35,
			"seed": 1297819719,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YSzNfACrkTkixSms4FYcU",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Interpolation",
			"rawText": "Interpolation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Interpolation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 444,
			"versionNonce": 582657931,
			"isDeleted": false,
			"id": "JUdtfMWz",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1406.3138795298883,
			"y": 507.24969433577576,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 947.7791137695312,
			"height": 50,
			"seed": 1432795881,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "What if we can choose certain points at certain inputs such that our curve has to go through\nand we interpolate the rest that is inbetween?",
			"rawText": "What if we can choose certain points at certain inputs such that our curve has to go through\nand we interpolate the rest that is inbetween?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What if we can choose certain points at certain inputs such that our curve has to go through\nand we interpolate the rest that is inbetween?",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 366,
			"versionNonce": 2035133093,
			"isDeleted": false,
			"id": "-G1s8QKDyVWOyhJRko9TW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1763.9713235523348,
			"y": 568.1509343474818,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 232.4642266953729,
			"height": 35.91721957525075,
			"seed": 576212937,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4740e964faf6320bbc6d24ddbac89b4841dd069b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 343,
			"versionNonce": 1270054443,
			"isDeleted": false,
			"id": "6ciUprAy",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1652.7365736768984,
			"y": 788.5834424869979,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 461.3594970703125,
			"height": 25,
			"seed": 703793063,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets consider the following Lagrange polynomial",
			"rawText": "Lets consider the following Lagrange polynomial",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets consider the following Lagrange polynomial",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 386,
			"versionNonce": 434834949,
			"isDeleted": false,
			"id": "tsm9_LA7e7B2oUVPYowmL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1559.0335514908638,
			"y": 848.6219366256234,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 694.3612260415277,
			"height": 77.44798290463194,
			"seed": 1874172841,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "585d53ddaf37b9f5b94d2ee05776f0693be59fe1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 656,
			"versionNonce": 412647627,
			"isDeleted": false,
			"id": "2fsVH7mcZfRQgB-Sp5XdM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2209.820261273053,
			"y": 861.1595952600819,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 114.28277766008159,
			"height": 54.312607204791334,
			"seed": 553387177,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "SJ1YoYtw",
				"focus": -0.20215799263175524,
				"gap": 10.495631466124905
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
					46.957774979142414,
					-54.312607204791334
				],
				[
					114.28277766008159,
					-49.78655660439199
				]
			]
		},
		{
			"type": "text",
			"version": 301,
			"versionNonce": 1002767717,
			"isDeleted": false,
			"id": "SJ1YoYtw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2334.5986703992594,
			"y": 800.3438527102492,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 122.75984191894531,
			"height": 25,
			"seed": 1110443497,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "2fsVH7mcZfRQgB-Sp5XdM",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "missing (t-ti)",
			"rawText": "missing (t-ti)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "missing (t-ti)",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 616,
			"versionNonce": 319041387,
			"isDeleted": false,
			"id": "z87DSOaCOx4lecU0332Er",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2246.0286660762476,
			"y": 909.8146392143742,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.80882826048128,
			"height": 40.16869907854357,
			"seed": 601976743,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "4TLuzFm5",
				"focus": 0.3852689402293708,
				"gap": 5.55084155269526
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
					80.33739815708714,
					1.6972689751497683
				],
				[
					118.80882826048128,
					-38.4714301033938
				]
			]
		},
		{
			"type": "text",
			"version": 306,
			"versionNonce": 841552069,
			"isDeleted": false,
			"id": "4TLuzFm5",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2347.6595972193363,
			"y": 840.7923675582852,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 127.13983154296875,
			"height": 25,
			"seed": 246392233,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "z87DSOaCOx4lecU0332Er",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "missing (ti-ti)",
			"rawText": "missing (ti-ti)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "missing (ti-ti)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 400,
			"versionNonce": 759237131,
			"isDeleted": false,
			"id": "8UG1dRwGnRonvx_gzH6WD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1734.597388892462,
			"y": 940.391093536562,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 291.2120946588038,
			"height": 63.095953842740826,
			"seed": 1905983593,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0223f752c9e55652c97e392afbfcad487075bd1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 392,
			"versionNonce": 179613733,
			"isDeleted": false,
			"id": "0MoIKmbw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1636.637540722174,
			"y": 1008.6297469949443,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 515.9794921875,
			"height": 50,
			"seed": 672217223,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "substituting any point that is not ti will result in 0\nand substituting ti will result in 1",
			"rawText": "substituting any point that is not ti will result in 0\nand substituting ti will result in 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "substituting any point that is not ti will result in 0\nand substituting ti will result in 1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 378,
			"versionNonce": 743018667,
			"isDeleted": false,
			"id": "VZKWq5LM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1624.8265214591845,
			"y": 1073.5803014074056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 546.7993774414062,
			"height": 25,
			"seed": 1519460489,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Which will result that our interpolation problem becomes",
			"rawText": "Which will result that our interpolation problem becomes",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which will result that our interpolation problem becomes",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 374,
			"versionNonce": 1129669509,
			"isDeleted": false,
			"id": "Y_jJAF9kGWKWYCD1qIJ_P",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1707.948469877499,
			"y": 1100.369136455399,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 402.5871111223844,
			"height": 63.288803495222,
			"seed": 1151537351,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "eed74e29793ce688138123862c8a1193b2d48011",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 584,
			"versionNonce": 1372078923,
			"isDeleted": false,
			"id": "BlEFRsiz",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1483.36108480921,
			"y": 1141.1895751338268,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 882.9590454101562,
			"height": 50,
			"seed": 329213065,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "such that at point k no other point other than k contributes to pk so we will get pk * 1\nand anything in between is an interpolation of such through the various points",
			"rawText": "such that at point k no other point other than k contributes to pk so we will get pk * 1\nand anything in between is an interpolation of such through the various points",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "such that at point k no other point other than k contributes to pk so we will get pk * 1\nand anything in between is an interpolation of such through the various points",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 829,
			"versionNonce": 1078504165,
			"isDeleted": false,
			"id": "kSxTvt0UtgSWhZTuouPsy",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1588.1737637720828,
			"y": 1114.0020953193773,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 266.5818541066735,
			"height": 226.03705924917517,
			"seed": 481580329,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "toxyK91L",
				"focus": -0.10949780125646469,
				"gap": 19.567064838778833
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
					-266.5818541066735,
					13.563775426035136
				],
				[
					-255.07903019565742,
					226.03705924917517
				]
			]
		},
		{
			"type": "text",
			"version": 676,
			"versionNonce": 1175953899,
			"isDeleted": false,
			"id": "toxyK91L",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1011.011231423501,
			"y": 1359.6062194073313,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 732.499267578125,
			"height": 100,
			"seed": 355437255,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "kSxTvt0UtgSWhZTuouPsy",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This implementation is not perfect but its nice because it offers us\naffine invariance\n\nAffine invariance is the following homoginity of an affine transformation T",
			"rawText": "This implementation is not perfect but its nice because it offers us\naffine invariance\n\nAffine invariance is the following homoginity of an affine transformation T",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This implementation is not perfect but its nice because it offers us\naffine invariance\n\nAffine invariance is the following homoginity of an affine transformation T",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 529,
			"versionNonce": 35391045,
			"isDeleted": false,
			"id": "SJvFJU1t7RKJY47oSkuAv",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1182.7704692680504,
			"y": 1479.1242990484448,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 440.79046042343634,
			"height": 98.91511033344996,
			"seed": 1450790535,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "411ce47537d702e3ab73ac185f3b20e7592e4a0d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 649,
			"versionNonce": 1111633035,
			"isDeleted": false,
			"id": "a4q1959v",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 949.2561822334953,
			"y": 1587.4998539013222,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 893.5589599609375,
			"height": 100,
			"seed": 650598729,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We may generate the curve from the points and then transform the curve\nor first transform the points and the generate the curve from the transformed points.\nWhich is quite useful in order to get the same curve for different devices that may have\ndifferent resolutions and thus different coordinate systems.",
			"rawText": "We may generate the curve from the points and then transform the curve\nor first transform the points and the generate the curve from the transformed points.\nWhich is quite useful in order to get the same curve for different devices that may have\ndifferent resolutions and thus different coordinate systems.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We may generate the curve from the points and then transform the curve\nor first transform the points and the generate the curve from the transformed points.\nWhich is quite useful in order to get the same curve for different devices that may have\ndifferent resolutions and thus different coordinate systems.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 252,
			"versionNonce": 464319909,
			"isDeleted": false,
			"id": "xvjD5laV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1614.3459337570976,
			"y": 1235.3061311103113,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 581.4412841796875,
			"height": 20,
			"seed": 1873270249,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "With higher polynomial degree the interpolation shows undesired oscillation.",
			"rawText": "With higher polynomial degree the interpolation shows undesired oscillation.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "With higher polynomial degree the interpolation shows undesired oscillation.",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 239,
			"versionNonce": 2046976811,
			"isDeleted": false,
			"id": "u1pq2Ksh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1653.8718386045919,
			"y": 1193.4006291150931,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 466.73687744140625,
			"height": 40,
			"seed": 442592841,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The form of the curve depends not only on the points (pi )\nbut also on the choice of ti, i.e. the parametrization.",
			"rawText": "The form of the curve depends not only on the points (pi )\nbut also on the choice of ti, i.e. the parametrization.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The form of the curve depends not only on the points (pi )\nbut also on the choice of ti, i.e. the parametrization.",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 342,
			"versionNonce": 1747515653,
			"isDeleted": false,
			"id": "bIXu-szYjwMVJwB-kpcQ2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2495.105914103309,
			"y": 1113.8957715933948,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 134.9275063934574,
			"height": 1.827021904172625,
			"seed": 1233214023,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					134.9275063934574,
					1.827021904172625
				]
			]
		},
		{
			"type": "text",
			"version": 282,
			"versionNonce": 1170392523,
			"isDeleted": false,
			"id": "9iVN8bLX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3015.120031496135,
			"y": 866.8862323393503,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 280.05718994140625,
			"height": 35,
			"seed": 1896864615,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Hermite interpolation",
			"rawText": "Hermite interpolation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hermite interpolation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 378,
			"versionNonce": 17666149,
			"isDeleted": false,
			"id": "WVg2Pzaq",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2674.1558709095552,
			"y": 907.040909037833,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1003.1388549804688,
			"height": 75,
			"seed": 1732797351,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Hermite Interpolation interpolates not only the geometric positions (points) but also their derivatives\nThe cubic version allows interpolation of two points, this method consists of 4 basis functions over\nthe [0,1] interval:",
			"rawText": "Hermite Interpolation interpolates not only the geometric positions (points) but also their derivatives\nThe cubic version allows interpolation of two points, this method consists of 4 basis functions over\nthe [0,1] interval:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hermite Interpolation interpolates not only the geometric positions (points) but also their derivatives\nThe cubic version allows interpolation of two points, this method consists of 4 basis functions over\nthe [0,1] interval:",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 306,
			"versionNonce": 211670123,
			"isDeleted": false,
			"id": "djzF3Vp7TE6fx3KGQf7Mv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3002.3228224005707,
			"y": 988.0984194885384,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 318.6565087290209,
			"height": 160.15094758842358,
			"seed": 2039021961,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d4853f377fd013788ffa6b195da9032a32ad05f7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 358,
			"versionNonce": 1948793797,
			"isDeleted": false,
			"id": "0h7VU22scaELucLQPCdIv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2856.405342708922,
			"y": 1149.2292743590544,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 575.5873984582371,
			"height": 39.7698109112134,
			"seed": 120349159,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c96063f14e6665777a6d580b5979af2cb91e91d5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 264,
			"versionNonce": 1851657995,
			"isDeleted": false,
			"id": "ouUn7QwVO3IbnQDsBE287",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2960.651800285047,
			"y": 1191.9547472366671,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 15.084925850107993,
			"height": 33.186836870237585,
			"seed": 1421476425,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-15.084925850107993,
					33.186836870237585
				]
			]
		},
		{
			"type": "text",
			"version": 243,
			"versionNonce": 966163237,
			"isDeleted": false,
			"id": "9BQyNeKa",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2914.876910140506,
			"y": 1225.1415841069047,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 61.37992858886719,
			"height": 25,
			"seed": 1399959529,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "point 1",
			"rawText": "point 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "point 1",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 278,
			"versionNonce": 763229611,
			"isDeleted": false,
			"id": "YgqWCoBh6ifoz2jnFF3NV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3347.5801483403147,
			"y": 1192.7089935291726,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 18.856157312634423,
			"height": 52.04299418287246,
			"seed": 210025639,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					14.330679557602707,
					35.44957574775344
				],
				[
					18.856157312634423,
					52.04299418287246
				]
			]
		},
		{
			"type": "text",
			"version": 249,
			"versionNonce": 1774571141,
			"isDeleted": false,
			"id": "s1bBSbDi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3333.599084203317,
			"y": 1246.2604802970554,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 70.19992065429688,
			"height": 25,
			"seed": 1192456009,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "point 2",
			"rawText": "point 2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "point 2",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 271,
			"versionNonce": 1495795787,
			"isDeleted": false,
			"id": "sidP6yIP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3043.0464659563513,
			"y": 1221.3703526443774,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 96.17988586425781,
			"height": 50,
			"seed": 1494727017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "derivative\nat point 1",
			"rawText": "derivative\nat point 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "derivative\nat point 1",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 270,
			"versionNonce": 863221221,
			"isDeleted": false,
			"id": "odlxtyOHQ2RiYRTpLBbvb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3087.3651774259533,
			"y": 1185.1665306041186,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1.508492585010572,
			"height": 34.69532945524816,
			"seed": 388347273,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.508492585010572,
					34.69532945524816
				]
			]
		},
		{
			"type": "text",
			"version": 289,
			"versionNonce": 926336747,
			"isDeleted": false,
			"id": "IYaDGjeg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3188.0572376707596,
			"y": 1222.8788452293886,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 104.83987426757812,
			"height": 50,
			"seed": 1963333033,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "FOCio1UjVm6J0wZMdHRsL",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "derivative\nat point 2",
			"rawText": "derivative\nat point 2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "derivative\nat point 2",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 269,
			"versionNonce": 296595781,
			"isDeleted": false,
			"id": "LTOSSU92B0wOwD3zP32Si",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3219.358278614398,
			"y": 1185.1665306041186,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.822186972591226,
			"height": 34.69532945524816,
			"seed": 1081178567,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					12.822186972591226,
					34.69532945524816
				]
			]
		},
		{
			"type": "text",
			"version": 410,
			"versionNonce": 1848947083,
			"isDeleted": false,
			"id": "MGJ2EpX6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2950.042789666966,
			"y": 1348.141080461166,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 23.619979858398438,
			"height": 25,
			"seed": 459429961,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p0",
			"rawText": "p0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p0",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 417,
			"versionNonce": 1104232613,
			"isDeleted": false,
			"id": "0vlKI2dQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3325.01876253767,
			"y": 1326.3962856484086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 15.279983520507812,
			"height": 25,
			"seed": 788753353,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p1",
			"rawText": "p1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p1",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 487,
			"versionNonce": 1868318763,
			"isDeleted": false,
			"id": "samYnM-OX97dJbkScSNp7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2996.8022217028565,
			"y": 1373.1833365738496,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1e1e1e",
			"width": 53.23849851465138,
			"height": 78.12922509293026,
			"seed": 91652905,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					53.23849851465138,
					78.12922509293026
				]
			]
		},
		{
			"type": "text",
			"version": 434,
			"versionNonce": 2039211013,
			"isDeleted": false,
			"id": "fxkB2Pal",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2984.9750483910166,
			"y": 1427.804653231739,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 26.41998291015625,
			"height": 25,
			"seed": 281625383,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "m0",
			"rawText": "m0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "m0",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 727,
			"versionNonce": 546835147,
			"isDeleted": false,
			"id": "FOCio1UjVm6J0wZMdHRsL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3307.9363039313394,
			"y": 1337.2300648496694,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1e1e1e",
			"width": 15.902408647233642,
			"height": 60.15258923084002,
			"seed": 1705476103,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "gJJao4Un",
				"focus": 1.7696404008875293,
				"gap": 15.210999575614778
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
					15.902408647233642,
					-60.15258923084002
				]
			]
		},
		{
			"type": "text",
			"version": 410,
			"versionNonce": 1557863269,
			"isDeleted": false,
			"id": "gJJao4Un",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3329.3183097964366,
			"y": 1292.2884751944441,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 18.079986572265625,
			"height": 25,
			"seed": 1371022185,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "FOCio1UjVm6J0wZMdHRsL",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "m1",
			"rawText": "m1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "m1",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 712,
			"versionNonce": 1182955883,
			"isDeleted": false,
			"id": "2BeU4AqoAWhi7dpvqPiTd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2995.4194035596183,
			"y": 1369.0348821441364,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 311.8254913001024,
			"height": 177.00072233442597,
			"seed": 1669748775,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					36.644680795799104,
					44.94158965522547
				],
				[
					108.55122424415958,
					80.20345230778685
				],
				[
					206.7313124140369,
					64.9924527321723
				],
				[
					268.9581288597333,
					22.125090291803417
				],
				[
					309.05985501362693,
					-35.261862652561376
				],
				[
					311.8254913001024,
					-96.79727002663913
				]
			]
		},
		{
			"type": "ellipse",
			"version": 529,
			"versionNonce": 873227973,
			"isDeleted": false,
			"id": "vIbh72SYpAanuz68mhL2Z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2982.4531115240407,
			"y": 1364.1635608495137,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 21.744794812757846,
			"height": 17.166943273229435,
			"seed": 121278441,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 512,
			"versionNonce": 778441739,
			"isDeleted": false,
			"id": "E53F4YHj-sGclP5dpcEQV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3288.5969332299674,
			"y": 1325.824054205968,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 21.744794812757846,
			"height": 17.166943273229435,
			"seed": 1700795015,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 515,
			"versionNonce": 1639794213,
			"isDeleted": false,
			"id": "F4p3zkju",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1664.757295770709,
			"y": -355.64054586544506,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 458.305908203125,
			"height": 35,
			"seed": 1591194569,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Generation of Parametric Curves",
			"rawText": "Generation of Parametric Curves",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Generation of Parametric Curves",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 749,
			"versionNonce": 406674091,
			"isDeleted": false,
			"id": "WL7iow8O",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1424.0480765605287,
			"y": -311.80555949898013,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 931.6190795898438,
			"height": 250,
			"seed": 1920672775,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We want to find a way to be able to Generate a parametric curve and be able to control it\nto our liking with predictable changes\nWe also think it is convenient to Generate the curve in the following form: \n\n\n\n\nThe first idea is to mess with polynomials\nTheyre continuously differentiable and regular, can we understand how to\ntune their coefficients such that we get a surface that we want?",
			"rawText": "We want to find a way to be able to Generate a parametric curve and be able to control it\nto our liking with predictable changes\nWe also think it is convenient to Generate the curve in the following form: \n\n\n\n\nThe first idea is to mess with polynomials\nTheyre continuously differentiable and regular, can we understand how to\ntune their coefficients such that we get a surface that we want?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We want to find a way to be able to Generate a parametric curve and be able to control it\nto our liking with predictable changes\nWe also think it is convenient to Generate the curve in the following form: \n\n\n\n\nThe first idea is to mess with polynomials\nTheyre continuously differentiable and regular, can we understand how to\ntune their coefficients such that we get a surface that we want?",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 470,
			"versionNonce": 417020293,
			"isDeleted": false,
			"id": "8I3Oz_68-yehExr9vviZ_",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1660.1975892393727,
			"y": -52.97057408439582,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 471.42532089569517,
			"height": 46.12352400117154,
			"seed": 538431687,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bd9529c00bc9bb753fa119f0c9f5ecf9a5872fa6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 666,
			"versionNonce": 1622330699,
			"isDeleted": false,
			"id": "L3wix8xo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1412.3822956620243,
			"y": -3.039319111933594,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 973.2391357421875,
			"height": 100,
			"seed": 1880181543,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "A polynomial such as this of degree n forms a n+1 dimensional vector space\nsuch that the monomial (the variables not the coefficients) are its basis.\n\nWe control the coefficients c0... cn, what do those coefficients mean when it comes to the curve?",
			"rawText": "A polynomial such as this of degree n forms a n+1 dimensional vector space\nsuch that the monomial (the variables not the coefficients) are its basis.\n\nWe control the coefficients c0... cn, what do those coefficients mean when it comes to the curve?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A polynomial such as this of degree n forms a n+1 dimensional vector space\nsuch that the monomial (the variables not the coefficients) are its basis.\n\nWe control the coefficients c0... cn, what do those coefficients mean when it comes to the curve?",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 443,
			"versionNonce": 1386463461,
			"isDeleted": false,
			"id": "MpC8_iUPNd1TJfNH2d75P",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1605.5730776323703,
			"y": 100.76841159631687,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 638.6179699739818,
			"height": 68.63107509738602,
			"seed": 1855615209,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "95873c963abc1b6434c1d39e0d65497e384743a6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 372,
			"versionNonce": 1797319659,
			"isDeleted": false,
			"id": "Fnf0zcGK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1521.2696372883108,
			"y": 169.5281882459529,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 754.5391845703125,
			"height": 50,
			"seed": 1670081575,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YSzNfACrkTkixSms4FYcU",
					"type": "arrow"
				}
			],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Coefficients determine the derivative of the curve at t.\nModeling of curves with the help of these coefficients is virtually impossible.",
			"rawText": "Coefficients determine the derivative of the curve at t.\nModeling of curves with the help of these coefficients is virtually impossible.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Coefficients determine the derivative of the curve at t.\nModeling of curves with the help of these coefficients is virtually impossible.",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 573,
			"versionNonce": 77880389,
			"isDeleted": false,
			"id": "YSzNfACrkTkixSms4FYcU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1874.4271346004862,
			"y": 230.6457872505494,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.5995041710114037,
			"height": 227.55050603627615,
			"seed": 839711335,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Fnf0zcGK",
				"focus": 0.064153129191724,
				"gap": 11.117599004596514
			},
			"endBinding": {
				"elementId": "iQ20T3z4",
				"focus": -0.05743448267631953,
				"gap": 12.660310761882045
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
					0.5995041710114037,
					227.55050603627615
				]
			]
		},
		{
			"type": "arrow",
			"version": 189,
			"versionNonce": 1267873419,
			"isDeleted": false,
			"id": "Hgywz-QbWKpyJnPLQ4A0E",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2422.3522881379386,
			"y": -107.9870799749346,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 295.36027459329944,
			"height": 1.4210854715202004e-14,
			"seed": 365906023,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501115,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					295.36027459329944,
					-1.4210854715202004e-14
				]
			]
		},
		{
			"type": "text",
			"version": 228,
			"versionNonce": 381324197,
			"isDeleted": false,
			"id": "Xed7LOOX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3110.690560920566,
			"y": -355.6405459666397,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 182.33676147460938,
			"height": 35,
			"seed": 1330269577,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Approximation",
			"rawText": "Approximation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Approximation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 415,
			"versionNonce": 817966379,
			"isDeleted": false,
			"id": "C0Tixxfh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2744.9102971086777,
			"y": -315.6464770154438,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 924.3989868164062,
			"height": 75,
			"seed": 191560839,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Sometimes interpolation is hard to control and not the best method.\nWe can also settle down for Approximation methods that try to build a polynomial such that\nit has the least distance to all points",
			"rawText": "Sometimes interpolation is hard to control and not the best method.\nWe can also settle down for Approximation methods that try to build a polynomial such that\nit has the least distance to all points",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sometimes interpolation is hard to control and not the best method.\nWe can also settle down for Approximation methods that try to build a polynomial such that\nit has the least distance to all points",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 223,
			"versionNonce": 420728581,
			"isDeleted": false,
			"id": "B54b36al7pI13WMfxUMOP",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3094.0030510280976,
			"y": -233.4687012119088,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 285.28553389622675,
			"height": 79.52649838700125,
			"seed": 185213191,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ea40523ed8775ec5233b0d3274ea599aa34f4bbf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 279,
			"versionNonce": 236474315,
			"isDeleted": false,
			"id": "OLBDGCBdPY18Zjihh6lRf",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3125.7207897319477,
			"y": -151.71986621081487,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 205.32431733971592,
			"height": 48.089116429565046,
			"seed": 1945298087,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0ecdabb68a99291d5cf45a698f921a294d9a510d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 404,
			"versionNonce": 976070245,
			"isDeleted": false,
			"id": "DF3W0ZArA9J7cwyDnzlVJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2760.9836246013265,
			"y": -227.51016737933935,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 309.4597036771395,
			"height": 77.60643973589033,
			"seed": 2084093319,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c296f6eea3a9dde15fb22cdd43fffe363588a9b7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 206,
			"versionNonce": 95559275,
			"isDeleted": false,
			"id": "fwQFXiek",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3009.4773823951573,
			"y": -102.71507228957597,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 470.99951171875,
			"height": 25,
			"seed": 541246279,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Which leads us to a linear system of equations",
			"rawText": "Which leads us to a linear system of equations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which leads us to a linear system of equations",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 340,
			"versionNonce": 2094371269,
			"isDeleted": false,
			"id": "PaPfuRzLthts5M86_jz7A",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2997.776337152327,
			"y": -48.33007094455911,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 532.830252389673,
			"height": 164.198710430287,
			"seed": 1428657031,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "774dfe8f6eb923f14502100a689a0f944cd36d9d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 199,
			"versionNonce": 307829003,
			"isDeleted": false,
			"id": "stiTFCO6rpobYwujkP36J",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3018.6412944474605,
			"y": -46.880879016856284,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 207.28491348755688,
			"height": 46.9629882120247,
			"seed": 1142531847,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 201,
			"versionNonce": 774443301,
			"isDeleted": false,
			"id": "RXZabbUT",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2894.2879692845586,
			"y": -66.51286196735055,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 166.6563720703125,
			"height": 20,
			"seed": 1092611785,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Evaluation at point i",
			"rawText": "Evaluation at point i",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Evaluation at point i",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 208,
			"versionNonce": 1904721835,
			"isDeleted": false,
			"id": "BY1vSyt5Fwff8W-bVyjWl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3228.085425783847,
			"y": -47.960487941270685,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 52.90083729630396,
			"height": 125.77443969427293,
			"seed": 1329729159,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 190,
			"versionNonce": 462791813,
			"isDeleted": false,
			"id": "FDo9nhCq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3219.0599590371744,
			"y": -70.6322753539722,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 69.87216186523438,
			"height": 20,
			"seed": 1480837383,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "variables",
			"rawText": "variables",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "variables",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 207,
			"versionNonce": 1298698827,
			"isDeleted": false,
			"id": "N61wAC6aiPTfG2TSxi9Lm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3322.5512066701035,
			"y": -43.64205224361319,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 59.37849084278969,
			"height": 116.05795937454366,
			"seed": 2017803207,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 148425701,
			"isDeleted": false,
			"id": "OPnSWu5u",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3325.560398380561,
			"y": -81.42836459811588,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 53.360107421875,
			"height": 40,
			"seed": 389403431,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "control\npoints",
			"rawText": "control\npoints",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "control\npoints",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 379,
			"versionNonce": 651563243,
			"isDeleted": false,
			"id": "WqtdS7AG3kbQlUlgj3JDx",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2866.402068042962,
			"y": 117.78249122627665,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 157.91377635875367,
			"height": 50.67015253879012,
			"seed": 921496423,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "77b1c3c70c6458584bd863ab782235e94ab71ac3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 333,
			"versionNonce": 1711277893,
			"isDeleted": false,
			"id": "aexTbEbzW0e2SXqc49TBG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3025.704122887279,
			"y": 124.99118052035385,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 263.5279984035983,
			"height": 36.551981881483435,
			"seed": 67593383,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7f234b59f5553c96682e63bea2fb004b9b87eabd",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 332,
			"versionNonce": 2136652683,
			"isDeleted": false,
			"id": "kr8G3jLOwQ8U1eJOs6c2l",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3289.137035558626,
			"y": 125.45911323591656,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 296.78569116208905,
			"height": 34.113297834722886,
			"seed": 1964907881,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "79c4f96b7a009aaee96f869d859e50a82647755e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 365,
			"versionNonce": 1164498597,
			"isDeleted": false,
			"id": "M5LHvAv84a1pCMaIQ-mLH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2859.0943433354246,
			"y": 165.92278020940955,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 527.3895085779513,
			"height": 45.81569089962898,
			"seed": 1274803495,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "54e97ce09c31f6742905c5e2d703805b3da685ee",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 273,
			"versionNonce": 1127289387,
			"isDeleted": false,
			"id": "goHWrqB5GMJXoDY58sZP1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3070.3583007021966,
			"y": 209.46771225232487,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 291.0418070105484,
			"height": 85.8546332368779,
			"seed": 1874258311,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1745cdeb2ccf2cf43873a0dbc9545ede4ee37640",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 271,
			"versionNonce": 297843205,
			"isDeleted": false,
			"id": "i3DL1LgB9cKAZmIWErGY0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3465.913970680148,
			"y": 172.9229761172778,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 112.08666475737994,
			"height": 110.18689077844131,
			"seed": 61797735,
			"groupIds": [
				"mu7ZZn4xCjNf7IH26yoRi"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6a9720baef0c2f58b4b49b13d01237fd3461fdc9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 81,
			"versionNonce": 1933808843,
			"isDeleted": false,
			"id": "gZ_0rX7zJM5wwOSthTZ5k",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1751.4807601689806,
			"y": -228.47894656588014,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 243.7500000000002,
			"height": 41.67338709677423,
			"seed": 421399647,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "kITpkWQeXyxgpsI7e1PwM",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b2d5a7fb6edae3eac7e2a1445e886bbe0d493e8c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 189,
			"versionNonce": 67449189,
			"isDeleted": false,
			"id": "kITpkWQeXyxgpsI7e1PwM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1961.9697593092928,
			"y": -184.37347558415217,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 162.17966280148948,
			"height": 12.983807044481921,
			"seed": 33091007,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "gZ_0rX7zJM5wwOSthTZ5k",
				"focus": 0.22659262152236279,
				"gap": 2.432083884953741
			},
			"endBinding": {
				"elementId": "w4tqloLM",
				"focus": 0.19581757289400684,
				"gap": 4.378093672475643
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
					76.99438537040419,
					12.286338091021946
				],
				[
					162.17966280148948,
					12.983807044481921
				]
			]
		},
		{
			"type": "text",
			"version": 84,
			"versionNonce": 254591851,
			"isDeleted": false,
			"id": "w4tqloLM",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2128.527515783258,
			"y": -186.83074320235653,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 123.93626403808594,
			"height": 40,
			"seed": 563345279,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "kITpkWQeXyxgpsI7e1PwM",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Basis function i\nof degree n",
			"rawText": "Basis function i\nof degree n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Basis function i\nof degree n",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 82,
			"versionNonce": 1501805765,
			"isDeleted": false,
			"id": "Jdadsd-fvSjjJcEog_kfc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1917.7389421816138,
			"y": -193.3834568509016,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 212.14410437164543,
			"height": 33.58265744879333,
			"seed": 1906587551,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "SQmsyPnq",
				"focus": -0.16715480450268033,
				"gap": 10.39410777159651
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
					-94.19525869783479,
					33.58265744879333
				],
				[
					-212.14410437164543,
					25.39176538811205
				]
			]
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 1060576779,
			"isDeleted": false,
			"id": "SQmsyPnq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1583.296494198528,
			"y": -180.27802955381156,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 111.90423583984375,
			"height": 20,
			"seed": 2021665055,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Jdadsd-fvSjjJcEog_kfc",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Control point i",
			"rawText": "Control point i",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Control point i",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 110,
			"versionNonce": 1239014437,
			"isDeleted": false,
			"id": "29pY9Uhp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1458.7665353951836,
			"y": -871.7280839482283,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffc9c9",
			"width": 798.8994140625,
			"height": 35,
			"seed": 1143366271,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "General Properties we like our curve to function to have:",
			"rawText": "General Properties we like our curve to function to have:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "General Properties we like our curve to function to have:",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 447,
			"versionNonce": 1046291627,
			"isDeleted": false,
			"id": "PdC6Qj7n",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1490.368209727215,
			"y": -811.4050149482283,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffc9c9",
			"width": 737.8392333984375,
			"height": 175,
			"seed": 1150682705,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "38AX_e8F4V9SAe3Br7Cmv",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Our control points are used as coefficients for modelling\n2) moving the points we want the curve to follow smoothly and predictably\n3) moving a control point should only have local effects, not global\n4) no unwanted oscillation between two control points\n5) Affine invariant (explained later)\n6) Linearly precise\n7) Efficient processing and rendering",
			"rawText": "1) Our control points are used as coefficients for modelling\n2) moving the points we want the curve to follow smoothly and predictably\n3) moving a control point should only have local effects, not global\n4) no unwanted oscillation between two control points\n5) Affine invariant (explained later)\n6) Linearly precise\n7) Efficient processing and rendering",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Our control points are used as coefficients for modelling\n2) moving the points we want the curve to follow smoothly and predictably\n3) moving a control point should only have local effects, not global\n4) no unwanted oscillation between two control points\n5) Affine invariant (explained later)\n6) Linearly precise\n7) Efficient processing and rendering",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 133,
			"versionNonce": 1022693253,
			"isDeleted": false,
			"id": "W9mJhXor",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1630.7714680807371,
			"y": -456.2280945174375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 468.666015625,
			"height": 35,
			"seed": 1533668191,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "How do we Generate such curves?",
			"rawText": "How do we Generate such curves?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we Generate such curves?",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 70,
			"versionNonce": 71915339,
			"isDeleted": false,
			"id": "38AX_e8F4V9SAe3Br7Cmv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1859.965157007788,
			"y": -617.0098282635674,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 1.052631578947512,
			"height": 163.15789473684208,
			"seed": 1209528561,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "PdC6Qj7n",
				"focus": 0.00003333237684351264,
				"gap": 19.39518668466087
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
					1.052631578947512,
					163.15789473684208
				]
			]
		},
		{
			"type": "arrow",
			"version": 72,
			"versionNonce": 1091753701,
			"isDeleted": false,
			"id": "iOnFL35tN-yV2R4AFRNM_",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1328.7746808173129,
			"y": -114.82311147158725,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 328.88888888888914,
			"height": 4.444444444444343,
			"seed": 911386993,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					-328.88888888888914,
					-4.444444444444343
				]
			]
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 794179051,
			"isDeleted": false,
			"id": "WiPqFSI7",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 355.9239713280547,
			"y": -301.79439218098895,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 190.31680297851562,
			"height": 35,
			"seed": 223038079,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Bezier Curves",
			"rawText": "Bezier Curves",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bezier Curves",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 223,
			"versionNonce": 1086370373,
			"isDeleted": false,
			"id": "Cu0PUJyu",
			"fillStyle": "hachure",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 49.722784657025,
			"y": -266.79439183544554,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 802.7191772460938,
			"height": 75,
			"seed": 139741535,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Bezier curves are curved defined by a control polygon\n\nA control polygon is a polygon that encodes all control points and their sequence",
			"rawText": "Bezier curves are curved defined by a control polygon\n\nA control polygon is a polygon that encodes all control points and their sequence",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bezier curves are curved defined by a control polygon\n\nA control polygon is a polygon that encodes all control points and their sequence",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 285,
			"versionNonce": 781074571,
			"isDeleted": false,
			"id": "TD4wbHl98uLnxWKfcHWeI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 170.69246385648643,
			"y": -31.960080660351707,
			"strokeColor": "#e03131",
			"backgroundColor": "#1971c2",
			"width": 547.368774998788,
			"height": 100.00865057074105,
			"seed": 1584198367,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					127.68961635371403,
					-70.54181602757626
				],
				[
					305.38355799279856,
					-91.07930676978202
				],
				[
					445.5742556678552,
					-51.790194045562316
				],
				[
					547.368774998788,
					8.929343800959032
				]
			]
		},
		{
			"type": "line",
			"version": 279,
			"versionNonce": 2027692453,
			"isDeleted": false,
			"id": "7TVePqChQMfLfzOSs0SO1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 176.590670646724,
			"y": -37.80562094570314,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 547.9706788595789,
			"height": 153.16968153474028,
			"seed": 1287894737,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					115.49157805560628,
					-125.32064852842387
				],
				[
					307.97754148161687,
					-134.3306297951733
				],
				[
					469.3381150770384,
					-86.82345584322178
				],
				[
					547.9706788595789,
					18.83905173956697
				]
			]
		},
		{
			"type": "ellipse",
			"version": 293,
			"versionNonce": 732690219,
			"isDeleted": false,
			"id": "igDXeER0OnLvfi5wgz0GW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 165.12342176177012,
			"y": -47.634691418520674,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 18.83905173956697,
			"height": 19.65814094563513,
			"seed": 1790346239,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 292,
			"versionNonce": 781362437,
			"isDeleted": false,
			"id": "etQ90GeGB9s0qFq2ys4xh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 282.6627228325468,
			"y": -172.13625074087645,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 18.83905173956697,
			"height": 19.65814094563513,
			"seed": 679117873,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 292,
			"versionNonce": 890886603,
			"isDeleted": false,
			"id": "NMeu-UXLjuAvzA38MPmYR",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 471.05324022821674,
			"y": -181.14623200762594,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 18.83905173956697,
			"height": 19.65814094563513,
			"seed": 1725557745,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 292,
			"versionNonce": 627162213,
			"isDeleted": false,
			"id": "WwoEXJKcaIlTlH4JHz8LQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 635.6901706479108,
			"y": -133.63905805567435,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 18.83905173956697,
			"height": 19.65814094563513,
			"seed": 1993499569,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 291,
			"versionNonce": 670197867,
			"isDeleted": false,
			"id": "jBXfnvgL3acLqNlbhbZuq",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 713.5036452243831,
			"y": -32.891085709294344,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 18.83905173956697,
			"height": 19.65814094563513,
			"seed": 1902111601,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 1427564485,
			"isDeleted": false,
			"id": "rIXpfPYI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 138.64437826194927,
			"y": -44.35833459424816,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 15.279983520507812,
			"height": 25,
			"seed": 529011793,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p1",
			"rawText": "p1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 108,
			"versionNonce": 1509958411,
			"isDeleted": false,
			"id": "SXe2TZcE",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 253.00231710911328,
			"y": -177.05078597728522,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 24.0999755859375,
			"height": 25,
			"seed": 296912959,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p2",
			"rawText": "p2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p2",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 1607444261,
			"isDeleted": false,
			"id": "I96Eg3aC",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 440.06466128063505,
			"y": -191.79439168651152,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 23.479965209960938,
			"height": 25,
			"seed": 667452657,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p3",
			"rawText": "p3",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p3",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 62753195,
			"isDeleted": false,
			"id": "fkDr1FSF",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 658.3523861274725,
			"y": -152.47810979524132,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 22.65997314453125,
			"height": 25,
			"seed": 1760943057,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p4",
			"rawText": "p4",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p4",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 108,
			"versionNonce": 1207532165,
			"isDeleted": false,
			"id": "G7xE6X2J",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 741.3003971610568,
			"y": -37.8056209457032,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 22.219970703125,
			"height": 25,
			"seed": 428650591,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "p5",
			"rawText": "p5",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p5",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 1783962699,
			"isDeleted": false,
			"id": "jiSfxI8P",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 190.6542571999961,
			"y": -48.45378062458883,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 37.39996337890625,
			"height": 25,
			"seed": 856202961,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "t=0",
			"rawText": "t=0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=0",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 1716642277,
			"isDeleted": false,
			"id": "d7FwKUdl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 673.1723517127292,
			"y": -35.34835332749873,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 29.059967041015625,
			"height": 25,
			"seed": 448739889,
			"groupIds": [
				"wPoUkpgc7-Vgu4JXyw0QG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "t=1",
			"rawText": "t=1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 197,
			"versionNonce": 1235311339,
			"isDeleted": false,
			"id": "HsRhh985",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 201.69579804767113,
			"y": -4.180231115114225,
			"strokeColor": "#e03131",
			"backgroundColor": "#1971c2",
			"width": 493.66497802734375,
			"height": 20,
			"seed": 2112540767,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The points are encoded on a fixed interval t between 0 and 1",
			"rawText": "The points are encoded on a fixed interval t between 0 and 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The points are encoded on a fixed interval t between 0 and 1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 239,
			"versionNonce": 535190853,
			"isDeleted": false,
			"id": "Bp3QdpeZ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 74.17506662788489,
			"y": 30.606107011919356,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 755.2591552734375,
			"height": 75,
			"seed": 1531716049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Bezier curves only interpolate the first and the last point from the control\npolygon but it will smoothly follow the shape of the polygon\n and is defined as follows:",
			"rawText": "Bezier curves only interpolate the first and the last point from the control\npolygon but it will smoothly follow the shape of the polygon\n and is defined as follows:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bezier curves only interpolate the first and the last point from the control\npolygon but it will smoothly follow the shape of the polygon\n and is defined as follows:",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 185,
			"versionNonce": 2116863371,
			"isDeleted": false,
			"id": "YIEyeKmEA9QSNPUQW3wKG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 368.366996135402,
			"y": 120.39244457820075,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 187.48715017418664,
			"height": 66.29155201386642,
			"seed": 2097001791,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f55953bdfad301ead4bd294454c9ca9f290df54f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 180,
			"versionNonce": 1544842405,
			"isDeleted": false,
			"id": "-QR9NG7IemAc7s3HLTNwN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 487.92403330613746,
			"y": 171.8206362111099,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 60.963707491295736,
			"height": 42.29013943089882,
			"seed": 1266628191,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "e4vB4DXR",
				"focus": -0.358134719696184,
				"gap": 1
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
					9.88600662021014,
					28.559574680607
				],
				[
					60.963707491295736,
					42.29013943089882
				]
			]
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 1865538603,
			"isDeleted": false,
			"id": "e4vB4DXR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 549.589573421614,
			"y": 186.10042355141337,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 66.69993591308594,
			"height": 50,
			"seed": 992861215,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-QR9NG7IemAc7s3HLTNwN",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "control\npoints",
			"rawText": "control\npoints",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "control\npoints",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 186,
			"versionNonce": 982093829,
			"isDeleted": false,
			"id": "bWRsy5LXVcvtpv0h2afcm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 512.334704431212,
			"y": 134.4762108627201,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 258.5256062176928,
			"height": 33.22417429303681,
			"seed": 2010007135,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "Zl9RK3Oi",
				"focus": 0.6338581812516546,
				"gap": 7.243904177338891
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
					-116.28461002562892,
					-19.726853486490597
				],
				[
					-258.5256062176928,
					13.497320806546213
				]
			]
		},
		{
			"type": "text",
			"version": 116,
			"versionNonce": 949690059,
			"isDeleted": false,
			"id": "Zl9RK3Oi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 51.3254021660631,
			"y": 137.59097720269227,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 195.2397918701172,
			"height": 25,
			"seed": 477232881,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "bWRsy5LXVcvtpv0h2afcm",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Bernstein Polynomial",
			"rawText": "Bernstein Polynomial",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bernstein Polynomial",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 565,
			"versionNonce": 155404133,
			"isDeleted": false,
			"id": "gIfCsIJzc3NEkoCx1nVl3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -53.890171081788964,
			"y": 132.72797799643467,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 190.34608327978378,
			"height": 93.36157685782507,
			"seed": 704819345,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.4420157824226436,
					30.2438910947884
				],
				[
					-144.20157824226038,
					21.915863112165525
				],
				[
					-145.643594024683,
					57.419561353873654
				],
				[
					-188.90406749736113,
					7.013076195892978
				],
				[
					-141.3175466774152,
					-35.942015503951424
				],
				[
					-142.75956245983778,
					3.944855360189784
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 138,
			"versionNonce": 352521579,
			"isDeleted": false,
			"id": "cjEivlWs",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -191.93135065181252,
			"y": 87.94925116999437,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 145.2642822265625,
			"height": 40,
			"seed": 1688559953,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "But what is a\nBernstein Polynom?",
			"rawText": "But what is a\nBernstein Polynom?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But what is a\nBernstein Polynom?",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 135,
			"versionNonce": 2056196805,
			"isDeleted": false,
			"id": "ViBjq3pk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -743.4469372881035,
			"y": -87.33914325912605,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 273.33709716796875,
			"height": 70,
			"seed": 1822578911,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Bernstein Polynomial\nBasis function",
			"rawText": "Bernstein Polynomial\nBasis function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bernstein Polynomial\nBasis function",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 183,
			"versionNonce": 129247243,
			"isDeleted": false,
			"id": "E7jB0DtCZF64q0_EwCIg8",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -763.1391171730946,
			"y": 51.71857727859545,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 301.8796257951996,
			"height": 67.3887367927578,
			"seed": 1556132831,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7800ee7ba438d7d9e36e1aaed832b1b5b174522d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 138,
			"versionNonce": 453669413,
			"isDeleted": false,
			"id": "2WQJpop_Z12DBnFD9-5EL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -645.8672877142974,
			"y": 55.84558768954406,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 49.57356962917413,
			"height": 37.868699022285796,
			"seed": 1028308305,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-15.14747960891441,
					-30.294959217828648
				],
				[
					-49.57356962917413,
					-37.868699022285796
				]
			]
		},
		{
			"type": "text",
			"version": 136,
			"versionNonce": 1185476267,
			"isDeleted": false,
			"id": "9VFjZL3S",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -752.3614329268713,
			"y": -3.514766754217078,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 49.12010192871094,
			"height": 40,
			"seed": 253825183,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "from n\npick i",
			"rawText": "from n\npick i",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "from n\npick i",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 137,
			"versionNonce": 128116101,
			"isDeleted": false,
			"id": "-BQBHOzm1D1uFL26xJq2x",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -731.2439909645416,
			"y": 66.17341469562194,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 67.47513643970922,
			"height": 16.52452320972469,
			"seed": 89891391,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-29.60643741742342,
					-12.393392407293504
				],
				[
					-67.47513643970922,
					-16.52452320972469
				]
			]
		},
		{
			"type": "text",
			"version": 126,
			"versionNonce": 1686888779,
			"isDeleted": false,
			"id": "4Hezhcny",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -862.0983260887976,
			"y": 37.25549907860375,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 55.152130126953125,
			"height": 20,
			"seed": 1830138385,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "n basis",
			"rawText": "n basis",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n basis",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 162,
			"versionNonce": 1670769893,
			"isDeleted": false,
			"id": "Nt-1ADP5ucaH7kYrADL_u",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -728.9702053930434,
			"y": 104.33419399764304,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 76.12449707662859,
			"height": 7.040415914601482,
			"seed": 695942865,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-33.88200158901964,
					7.040415914601482
				],
				[
					-76.12449707662859,
					0.8800519893251817
				]
			]
		},
		{
			"type": "text",
			"version": 136,
			"versionNonce": 985104363,
			"isDeleted": false,
			"id": "ssbbNijC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -895.5936776599347,
			"y": 78.81268630721266,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 83.31217956542969,
			"height": 40,
			"seed": 1841805055,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "related to\nith point",
			"rawText": "related to\nith point",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "related to\nith point",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 139,
			"versionNonce": 242288709,
			"isDeleted": false,
			"id": "Yaj0YZVsDA631fuLnJQqJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -524.4038695986567,
			"y": 78.8242797615876,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 25.240380643994627,
			"height": 51.127950535271,
			"seed": 22230897,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.413460214664838,
					-36.24259784778701
				],
				[
					16.82692042932979,
					-51.127950535271
				]
			]
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 322325131,
			"isDeleted": false,
			"id": "cGjeVaTp",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -537.9710116034737,
			"y": 7.633462560577414,
			"strokeColor": "#e03131",
			"backgroundColor": "#e9ecef",
			"width": 102.20823669433594,
			"height": 20,
			"seed": 1292953983,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "interval [0,1]",
			"rawText": "interval [0,1]",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "interval [0,1]",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 964,
			"versionNonce": 437368741,
			"isDeleted": false,
			"id": "CefuugeV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -937.803187707251,
			"y": 133.31477137950947,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 634.9393310546875,
			"height": 800,
			"seed": 1348984063,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rt4jVI1oTyhqZ6XPo-jO3",
					"type": "arrow"
				},
				{
					"id": "87uFvVA8gKF092SzvmmZY",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Polynomial of degree n forms the basis of a\nn+1 dimensional vector space of polynomials (n+1 points)\n\nThese polynomials provide the following properties:\n\n1) partition of unity:\n\n\nThe sum of all Bernstein basis polynomials of n degree over the\nsame interval is always equal to 1\n\n\n2) non-negativity:\n\n\nBernstein basis polynomials never produce negative results\n\n\n3) Recursion:\n\n\nBernstein polynomials are a linear combination of the recursive\nmatching Bernstein polynomial of the previous degree\n\n\n4) Symmetry:\n\n\nBernstein polynomials are symmetric\nmeaning if we go at the start and end of the interval\nwhere the point is at the start and end too, the result will\nbe the same",
			"rawText": "Polynomial of degree n forms the basis of a\nn+1 dimensional vector space of polynomials (n+1 points)\n\nThese polynomials provide the following properties:\n\n1) partition of unity:\n\n\nThe sum of all Bernstein basis polynomials of n degree over the\nsame interval is always equal to 1\n\n\n2) non-negativity:\n\n\nBernstein basis polynomials never produce negative results\n\n\n3) Recursion:\n\n\nBernstein polynomials are a linear combination of the recursive\nmatching Bernstein polynomial of the previous degree\n\n\n4) Symmetry:\n\n\nBernstein polynomials are symmetric\nmeaning if we go at the start and end of the interval\nwhere the point is at the start and end too, the result will\nbe the same",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Polynomial of degree n forms the basis of a\nn+1 dimensional vector space of polynomials (n+1 points)\n\nThese polynomials provide the following properties:\n\n1) partition of unity:\n\n\nThe sum of all Bernstein basis polynomials of n degree over the\nsame interval is always equal to 1\n\n\n2) non-negativity:\n\n\nBernstein basis polynomials never produce negative results\n\n\n3) Recursion:\n\n\nBernstein polynomials are a linear combination of the recursive\nmatching Bernstein polynomial of the previous degree\n\n\n4) Symmetry:\n\n\nBernstein polynomials are symmetric\nmeaning if we go at the start and end of the interval\nwhere the point is at the start and end too, the result will\nbe the same",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 124,
			"versionNonce": 314753323,
			"isDeleted": false,
			"id": "7h8f1Xwi1YIgL7c2tMuaJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -693.3699503465697,
			"y": 293.8176055037303,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 153.1460886491974,
			"height": 36.727342526730595,
			"seed": 103258353,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5b581acc5a19aebf99e583d4094e70ddfa52215c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 127,
			"versionNonce": 10844933,
			"isDeleted": false,
			"id": "Nl9-tZzvN_Qm9YK6jsfGS",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -667.5590659808215,
			"y": 467.61323176414135,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 105.18174093678819,
			"height": 30.76744802912852,
			"seed": 1806014527,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f2ac1ba755a55f5e6cafb9544c02fccb4a6e5b12",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 138,
			"versionNonce": 1657234379,
			"isDeleted": false,
			"id": "MyXgG_gioAwptjCO4IVT_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -898.0887747505885,
			"y": 615.1025856396926,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 616.404712101624,
			"height": 36.36787801399581,
			"seed": 1230642609,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9db3ccae2d5867d8a77469d67327dcfb40e1aa07",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 132,
			"versionNonce": 447337061,
			"isDeleted": false,
			"id": "M4kzjLy9phmSc75kJ6k4w",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -719.6000483002263,
			"y": 791.4269705434758,
			"strokeColor": "transparent",
			"backgroundColor": "#e9ecef",
			"width": 198.5330523644588,
			"height": 31.27575482453803,
			"seed": 696845681,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ef06e4f8274e1f2a67dd3f2265c51e85242bb4b0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 669,
			"versionNonce": 459190891,
			"isDeleted": false,
			"id": "2mlqQrQ5GXZFpZ5O_ggyD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1408.550279375063,
			"y": 342.35443734210736,
			"strokeColor": "#e03131",
			"backgroundColor": "#1971c2",
			"width": 293.3902151565806,
			"height": 53.60473751637363,
			"seed": 391425887,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					68.44176307894134,
					-37.810484498156384
				],
				[
					163.68589491606943,
					-48.81860023812598
				],
				[
					238.8282501845575,
					-27.759596213836332
				],
				[
					293.3902151565806,
					4.78613727824765
				]
			]
		},
		{
			"type": "line",
			"version": 663,
			"versionNonce": 1424768453,
			"isDeleted": false,
			"id": "luryr99nnOsSEdx7P2_GA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1405.3888345900007,
			"y": 339.2212218567528,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 293.7128362326941,
			"height": 82.09910370031957,
			"seed": 1357212543,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					61.903602255321154,
					-67.17199393662511
				],
				[
					165.07627268085648,
					-72.00135297782039
				],
				[
					251.56570278226263,
					-46.53745985151805
				],
				[
					293.7128362326941,
					10.09775072249919
				]
			]
		},
		{
			"type": "ellipse",
			"version": 677,
			"versionNonce": 1834167563,
			"isDeleted": false,
			"id": "33yUmRLxpOe_SOSWIM8F6",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1411.535291551522,
			"y": 333.95283017544887,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 1833542559,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 676,
			"versionNonce": 646593829,
			"isDeleted": false,
			"id": "nUtswEm22fmoOmvpMT22u",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1348.5341076959292,
			"y": 267.21986887893246,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 1018288063,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 676,
			"versionNonce": 203379627,
			"isDeleted": false,
			"id": "hQ9l_9SoIjOGEohJlybrx",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1247.5566004709372,
			"y": 262.3905098377371,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 893290463,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 676,
			"versionNonce": 1190219909,
			"isDeleted": false,
			"id": "rn8SqKE3JIOWE4RZvicOQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1159.3110398090964,
			"y": 287.8544029640395,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 889205759,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 675,
			"versionNonce": 1475192395,
			"isDeleted": false,
			"id": "ZN6NCcMxL1hQGT_kj2bEh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1117.6029389987734,
			"y": 341.85541769740473,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 66542623,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 502,
			"versionNonce": 601815013,
			"isDeleted": false,
			"id": "tTPVxMGu",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1425.7280855587617,
			"y": 335.7089607358835,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 8.189178466796875,
			"height": 13.400025200434126,
			"seed": 370442303,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p1",
			"rawText": "p1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 492,
			"versionNonce": 1201186027,
			"isDeleted": false,
			"id": "2OHywLhy",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1364.4321150618937,
			"y": 264.58567303828045,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 12.916183471679688,
			"height": 13.400025200434126,
			"seed": 221782111,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p2",
			"rawText": "p2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p2",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 503,
			"versionNonce": 392213317,
			"isDeleted": false,
			"id": "2pnSyVrM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1264.1665100238665,
			"y": 256.6830855163246,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 12.583892822265625,
			"height": 13.400025200434126,
			"seed": 2066922623,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p3",
			"rawText": "p3",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p3",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 495,
			"versionNonce": 313184139,
			"isDeleted": false,
			"id": "iNp2KzTH",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1147.1640694681446,
			"y": 277.7566522415403,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 12.144424438476562,
			"height": 13.400025200434126,
			"seed": 1673843871,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p4",
			"rawText": "p4",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p4",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 492,
			"versionNonce": 1574175397,
			"isDeleted": false,
			"id": "YMY7ejdd",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1102.7038519411078,
			"y": 339.2212218567528,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 11.908615112304688,
			"height": 13.400025200434126,
			"seed": 2124343487,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p5",
			"rawText": "p5",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p5",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 495,
			"versionNonce": 459187755,
			"isDeleted": false,
			"id": "U5hmycIe",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1397.8507380211074,
			"y": 333.51379753534013,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 20.044204711914062,
			"height": 13.400025200434126,
			"seed": 962689247,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "t=0",
			"rawText": "t=0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=0",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 495,
			"versionNonce": 1273390597,
			"isDeleted": false,
			"id": "N0e16aU7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1139.2205529756645,
			"y": 340.5383197770788,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 15.574447631835938,
			"height": 13.400025200434126,
			"seed": 2040333567,
			"groupIds": [
				"F6bPVEdyarGFV0uLOIS_-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "t=1",
			"rawText": "t=1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=1",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 221,
			"versionNonce": 413051083,
			"isDeleted": false,
			"id": "rt4jVI1oTyhqZ6XPo-jO3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -956.216969992646,
			"y": 349.480968067738,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 117.21154298762099,
			"height": 0,
			"seed": 483082129,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "CefuugeV",
				"focus": 0.45958450827942876,
				"gap": 18.413782285394973
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
					-117.21154298762099,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 92,
			"versionNonce": 1150639461,
			"isDeleted": false,
			"id": "919SQrNDjgJ2PRUzf5zLz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1310.616399485542,
			"y": 292.8904083611216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.558379605816526,
			"height": 11.860691849937893,
			"seed": 197882655,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "1WnnYZWE0TMn1LfSwrjLn",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 315,
			"versionNonce": 350059,
			"isDeleted": false,
			"id": "1WnnYZWE0TMn1LfSwrjLn",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1298.0580198797254,
			"y": 304.05341245518076,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 27.21483213169722,
			"height": 52.426928527666746,
			"seed": 1886508319,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "919SQrNDjgJ2PRUzf5zLz",
				"focus": -0.4432250618342279,
				"gap": 2.0422890796170607
			},
			"endBinding": {
				"elementId": "dWzbF0kx",
				"focus": -0.13916419875950703,
				"gap": 13.953755117574019
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
					18.139881652846043,
					30.698261258662683
				],
				[
					-9.074950478851179,
					52.426928527666746
				]
			]
		},
		{
			"type": "text",
			"version": 192,
			"versionNonce": 1865312453,
			"isDeleted": false,
			"id": "dWzbF0kx",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1480.192880580766,
			"y": 370.4340961004215,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 286.32061767578125,
			"height": 60,
			"seed": 1322989777,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "1WnnYZWE0TMn1LfSwrjLn",
					"type": "arrow"
				},
				{
					"id": "cCkaK1w0mZjb2xEAV7HLI",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "every point on the curve\nis a linear/affine combination of the\ncontrol points",
			"rawText": "every point on the curve\nis a linear/affine combination of the\ncontrol points",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "every point on the curve\nis a linear/affine combination of the\ncontrol points",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 201,
			"versionNonce": 803025419,
			"isDeleted": false,
			"id": "7dKSDkCrANJLZ5Wr9Oi1r",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -930.524856288801,
			"y": 525.1200249670346,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 117.21154298762099,
			"height": 0,
			"seed": 1332734801,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					-117.21154298762099,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 719,
			"versionNonce": 760154149,
			"isDeleted": false,
			"id": "sD4rxXa8SJiucLK4pSJaJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1408.5502795636933,
			"y": 536.5866024235322,
			"strokeColor": "#e03131",
			"backgroundColor": "#1971c2",
			"width": 293.3902151565806,
			"height": 53.60473751637363,
			"seed": 1535687665,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					68.44176307894134,
					-37.810484498156384
				],
				[
					163.68589491606943,
					-48.81860023812598
				],
				[
					238.8282501845575,
					-27.759596213836332
				],
				[
					293.3902151565806,
					4.78613727824765
				]
			]
		},
		{
			"type": "line",
			"version": 713,
			"versionNonce": 1495316651,
			"isDeleted": false,
			"id": "GaoFCpCYWe-D02ovvfyUt",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1405.3888347786308,
			"y": 533.4533869381776,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 293.7128362326941,
			"height": 82.09910370031957,
			"seed": 1070470609,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					61.903602255321154,
					-67.17199393662511
				],
				[
					165.07627268085648,
					-72.00135297782039
				],
				[
					251.56570278226263,
					-46.53745985151805
				],
				[
					293.7128362326941,
					10.09775072249919
				]
			]
		},
		{
			"type": "ellipse",
			"version": 727,
			"versionNonce": 1357167493,
			"isDeleted": false,
			"id": "SEyKFaCnzRfOba-_IRaN5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1411.5352917401526,
			"y": 528.1849952568737,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 168637361,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 726,
			"versionNonce": 695888715,
			"isDeleted": false,
			"id": "If0etn6pBhhI-wP6Mlbqd",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1348.5341078845597,
			"y": 461.45203396035737,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 1584240017,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 726,
			"versionNonce": 304939749,
			"isDeleted": false,
			"id": "WgTQVO5wqgiD-J6xHVCjU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1247.5566006595675,
			"y": 456.62267491916197,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 1881586545,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 726,
			"versionNonce": 893700587,
			"isDeleted": false,
			"id": "5qEVGmuYdUjwkXk-gedeH",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1159.311039997727,
			"y": 482.0865680454643,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 528491857,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 725,
			"versionNonce": 1169514053,
			"isDeleted": false,
			"id": "126_GeSqTWPI-tvaDBHaX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1117.6029391874038,
			"y": 536.0875827788295,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 1473336113,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 552,
			"versionNonce": 562713739,
			"isDeleted": false,
			"id": "MIceWtMR",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1425.7280857473918,
			"y": 529.9411258173084,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 8.189178466796875,
			"height": 13.400025200434126,
			"seed": 763479313,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p1",
			"rawText": "p1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 542,
			"versionNonce": 1381715365,
			"isDeleted": false,
			"id": "mCpgMQvi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1364.4321152505238,
			"y": 458.8178381197053,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 12.916183471679688,
			"height": 13.400025200434126,
			"seed": 1007221489,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p2",
			"rawText": "p2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p2",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 553,
			"versionNonce": 235244331,
			"isDeleted": false,
			"id": "nzpdOwqO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1264.1665102124969,
			"y": 450.91525059774943,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 12.583892822265625,
			"height": 13.400025200434126,
			"seed": 1139700945,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p3",
			"rawText": "p3",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p3",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 545,
			"versionNonce": 1733054725,
			"isDeleted": false,
			"id": "n3582KJ3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1147.164069656775,
			"y": 471.9888173229652,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 12.144424438476562,
			"height": 13.400025200434126,
			"seed": 147436209,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p4",
			"rawText": "p4",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p4",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 542,
			"versionNonce": 1059122635,
			"isDeleted": false,
			"id": "byyVXPlp",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1102.7038521297384,
			"y": 533.4533869381776,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 11.908615112304688,
			"height": 13.400025200434126,
			"seed": 1866609809,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p5",
			"rawText": "p5",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p5",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 545,
			"versionNonce": 1912989797,
			"isDeleted": false,
			"id": "AF7VOhkK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1397.850738209738,
			"y": 527.7459626167649,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 20.044204711914062,
			"height": 13.400025200434126,
			"seed": 1527741041,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "t=0",
			"rawText": "t=0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=0",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 545,
			"versionNonce": 133626987,
			"isDeleted": false,
			"id": "tLFNXSqh",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1139.220553164295,
			"y": 534.7704848585036,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 15.574447631835938,
			"height": 13.400025200434126,
			"seed": 1291387985,
			"groupIds": [
				"fXMc4-QXS83u07a7F1uzI"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "t=1",
			"rawText": "t=1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=1",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 265,
			"versionNonce": 1414894533,
			"isDeleted": false,
			"id": "RX4PaL2SkQJz9H5NFsiOI",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1269.4569748016606,
			"y": 490.84462652585813,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 19.564396760958743,
			"height": 65.28283190202916,
			"seed": 1114659825,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "euicolFB",
				"focus": 0.037353526361697365,
				"gap": 2.23809199569223
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
					19.564396760958743,
					31.635819161255142
				],
				[
					10.048809821705618,
					65.28283190202916
				]
			]
		},
		{
			"type": "text",
			"version": 218,
			"versionNonce": 1951545099,
			"isDeleted": false,
			"id": "euicolFB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1432.0639100421258,
			"y": 558.3655504235795,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 314.68865966796875,
			"height": 60,
			"seed": 1035331359,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "RX4PaL2SkQJz9H5NFsiOI",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The curvature will always follow\nthe control polygon and be in its convex\nhull (convex combination)",
			"rawText": "The curvature will always follow\nthe control polygon and be in its convex\nhull (convex combination)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The curvature will always follow\nthe control polygon and be in its convex\nhull (convex combination)",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 841,
			"versionNonce": 1515770661,
			"isDeleted": false,
			"id": "9xcctFAMoPvkEH0R_LRaR",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1381.490921169248,
			"y": 898.0199726041034,
			"strokeColor": "#e03131",
			"backgroundColor": "#1971c2",
			"width": 293.3902151565806,
			"height": 53.60473751637363,
			"seed": 1569777489,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					68.44176307894134,
					-37.810484498156384
				],
				[
					163.68589491606943,
					-48.81860023812598
				],
				[
					238.8282501845575,
					-27.759596213836332
				],
				[
					293.3902151565806,
					4.78613727824765
				]
			]
		},
		{
			"type": "line",
			"version": 835,
			"versionNonce": 850206123,
			"isDeleted": false,
			"id": "k3zK_4_F0ReuZ09Efzi_u",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1378.3294763841855,
			"y": 894.8867571187487,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 293.7128362326941,
			"height": 82.09910370031957,
			"seed": 1517933873,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					61.903602255321154,
					-67.17199393662511
				],
				[
					165.07627268085648,
					-72.00135297782039
				],
				[
					251.56570278226263,
					-46.53745985151805
				],
				[
					293.7128362326941,
					10.09775072249919
				]
			]
		},
		{
			"type": "ellipse",
			"version": 849,
			"versionNonce": 1887250053,
			"isDeleted": false,
			"id": "SjsewbaaqVgBvKbjKLz8Y",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1384.4759333457073,
			"y": 889.6183654374448,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 197789457,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 848,
			"versionNonce": 1043476555,
			"isDeleted": false,
			"id": "VXpD2FP19srqPNEsUQeK3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1321.4747494901144,
			"y": 822.8854041409285,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 1811479793,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 848,
			"versionNonce": 427822565,
			"isDeleted": false,
			"id": "uCxC9CThH2IWoqC9VqSDI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1220.4972422651222,
			"y": 818.0560450997331,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 982398673,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 848,
			"versionNonce": 1220275947,
			"isDeleted": false,
			"id": "hc_xqu3KBgyhNnxeTtqeL",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1132.2516816032817,
			"y": 843.5199382260354,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 1512125617,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 847,
			"versionNonce": 611256645,
			"isDeleted": false,
			"id": "vAZHk9iFUVZhvUqatBZWq",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1090.5435807929584,
			"y": 897.5209529594007,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 10.097750722499187,
			"height": 10.536783362607864,
			"seed": 1851356817,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 674,
			"versionNonce": 1691670923,
			"isDeleted": false,
			"id": "9clCu7so",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1398.6687273529465,
			"y": 891.3744959978795,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 8.189178466796875,
			"height": 13.400025200434126,
			"seed": 971930737,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p1",
			"rawText": "p1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 664,
			"versionNonce": 581408933,
			"isDeleted": false,
			"id": "2QrRON8M",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1337.3727568560785,
			"y": 820.2512083002765,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 12.916183471679688,
			"height": 13.400025200434126,
			"seed": 1017628241,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p2",
			"rawText": "p2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p2",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 675,
			"versionNonce": 1874292779,
			"isDeleted": false,
			"id": "xtda7RH8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1237.107151818051,
			"y": 812.3486207783207,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 12.583892822265625,
			"height": 13.400025200434126,
			"seed": 291296305,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p3",
			"rawText": "p3",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p3",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 667,
			"versionNonce": 500644869,
			"isDeleted": false,
			"id": "FA3hwA7u",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1120.1047112623296,
			"y": 833.4221875035363,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 12.144424438476562,
			"height": 13.400025200434126,
			"seed": 200615441,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p4",
			"rawText": "p4",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p4",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 664,
			"versionNonce": 994980555,
			"isDeleted": false,
			"id": "ZNmWhd7P",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1075.644493735293,
			"y": 894.8867571187487,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 11.908615112304688,
			"height": 13.400025200434126,
			"seed": 392707057,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "p5",
			"rawText": "p5",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p5",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 667,
			"versionNonce": 234582885,
			"isDeleted": false,
			"id": "8SItrKD9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1370.7913798152927,
			"y": 889.1793327973361,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 20.044204711914062,
			"height": 13.400025200434126,
			"seed": 1404933585,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "t=0",
			"rawText": "t=0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=0",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 667,
			"versionNonce": 2016649579,
			"isDeleted": false,
			"id": "FfzneDt5",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1112.1611947698498,
			"y": 896.2038550390747,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 15.574447631835938,
			"height": 13.400025200434126,
			"seed": 1946989489,
			"groupIds": [
				"D4oYHbkCxhbaEKkTmk902"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 10.7200201603473,
			"fontFamily": 1,
			"text": "t=1",
			"rawText": "t=1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=1",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 230,
			"versionNonce": 258064069,
			"isDeleted": false,
			"id": "YYRmDv1AV4u4yUdgkW5ll",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -921.7644581011934,
			"y": 879.6785930493863,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 117.21154298762099,
			"height": 0,
			"seed": 598299871,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					-117.21154298762099,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 70,
			"versionNonce": 1605516299,
			"isDeleted": false,
			"id": "zM3u-ZFFAQ6tkHksxKr1J",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1335.2855120481736,
			"y": 860.268085763012,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 17.901412847445727,
			"height": 13.426059635584238,
			"seed": 1149700671,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "m-BLbDtq0b0is60zXGaHM",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 110,
			"versionNonce": 1487380005,
			"isDeleted": false,
			"id": "ghAN0XOXm_yg20CzqDa9E",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1151.2987688938708,
			"y": 861.2626086989814,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 20.387720187368586,
			"height": 18.39867431543007,
			"seed": 59452479,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "2zCOGDmdOW7uswJWTtmYP",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 241,
			"versionNonce": 499417771,
			"isDeleted": false,
			"id": "2zCOGDmdOW7uswJWTtmYP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1147.817938617979,
			"y": 879.6612830144114,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 73.59469726172074,
			"height": 75.58374313365937,
			"seed": 1954258815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ghAN0XOXm_yg20CzqDa9E",
				"focus": -0.6417582269541107,
				"gap": 1.8700730404129242
			},
			"endBinding": {
				"elementId": "H2RZOc0K",
				"focus": -0.025297896401229578,
				"gap": 4.97261467984606
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
					-66.1357752419517,
					26.852119271168363
				],
				[
					-73.59469726172074,
					75.58374313365937
				]
			]
		},
		{
			"type": "arrow",
			"version": 290,
			"versionNonce": 1891275141,
			"isDeleted": false,
			"id": "m-BLbDtq0b0is60zXGaHM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1317.3840992007279,
			"y": 871.2078380586731,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 94.47967891707412,
			"height": 84.53444955738223,
			"seed": 1726335409,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zM3u-ZFFAQ6tkHksxKr1J",
				"focus": -0.018044747732732187,
				"gap": 1.481158023170055
			},
			"endBinding": {
				"elementId": "H2RZOc0K",
				"focus": 0.013765127009370784,
				"gap": 4.4753532118614885
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
					85.52897249335138,
					41.769963310706544
				],
				[
					94.47967891707412,
					84.53444955738223
				]
			]
		},
		{
			"type": "text",
			"version": 175,
			"versionNonce": 2064971083,
			"isDeleted": false,
			"id": "H2RZOc0K",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1407.7625190716606,
			"y": 960.2176408279169,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 374.6888122558594,
			"height": 40,
			"seed": 480575729,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "2zCOGDmdOW7uswJWTtmYP",
					"type": "arrow"
				},
				{
					"id": "m-BLbDtq0b0is60zXGaHM",
					"type": "arrow"
				}
			],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "at any two symmetric points on the curve\nthe opposing points will have the same influence",
			"rawText": "at any two symmetric points on the curve\nthe opposing points will have the same influence",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "at any two symmetric points on the curve\nthe opposing points will have the same influence",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 398,
			"versionNonce": 618141925,
			"isDeleted": false,
			"id": "87uFvVA8gKF092SzvmmZY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -940.9651292228286,
			"y": 671.0181745180214,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e9ecef",
			"width": 138.50610094515196,
			"height": 0.10057610050159838,
			"seed": 1705255089,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "CefuugeV",
				"focus": -0.34464194776529405,
				"gap": 3.1619415155776096
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
					-138.50610094515196,
					-0.10057610050159838
				]
			]
		},
		{
			"type": "arrow",
			"version": 303,
			"versionNonce": 1191056363,
			"isDeleted": false,
			"id": "PUSTlcnb8e923slkSpIMR",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1427.2204551201382,
			"y": 745.430378786281,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 326.00591123327285,
			"height": 1.3306363723806953,
			"seed": 771582001,
			"groupIds": [
				"7hbWpIykMgBCPk4IC2qRF"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					326.00591123327285,
					1.3306363723806953
				]
			]
		},
		{
			"type": "line",
			"version": 220,
			"versionNonce": 1049474117,
			"isDeleted": false,
			"id": "M42d16orncxLsoLGUAvc7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1389.9626366934783,
			"y": 738.7771969243776,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 17.9635910271395,
			"seed": 260838865,
			"groupIds": [
				"7hbWpIykMgBCPk4IC2qRF"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					17.9635910271395
				]
			]
		},
		{
			"type": "line",
			"version": 226,
			"versionNonce": 25845387,
			"isDeleted": false,
			"id": "bGMKvY4yKOx30Lg0Xys8a",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1350.043545963486,
			"y": 738.777196645092,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 17.9635910271395,
			"seed": 466899505,
			"groupIds": [
				"7hbWpIykMgBCPk4IC2qRF"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					17.9635910271395
				]
			]
		},
		{
			"type": "line",
			"version": 233,
			"versionNonce": 2042160037,
			"isDeleted": false,
			"id": "kdedKofZfBxoFTyAzo__D",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1310.1244551434916,
			"y": 738.7771974589015,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 17.9635910271395,
			"seed": 555803473,
			"groupIds": [
				"7hbWpIykMgBCPk4IC2qRF"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					17.9635910271395
				]
			]
		},
		{
			"type": "line",
			"version": 236,
			"versionNonce": 1165251883,
			"isDeleted": false,
			"id": "mF1ZZF0GQ1F6rjy3-zdiz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1270.2053632754025,
			"y": 738.7771980865211,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 17.9635910271395,
			"seed": 2065961361,
			"groupIds": [
				"7hbWpIykMgBCPk4IC2qRF"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501116,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					17.9635910271395
				]
			]
		},
		{
			"type": "line",
			"version": 322,
			"versionNonce": 981935877,
			"isDeleted": false,
			"id": "2Al9ymOrVjnPYtzVeqYac",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1230.286271124936,
			"y": 737.7792190865213,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 17.9635910271395,
			"seed": 2067082673,
			"groupIds": [
				"7hbWpIykMgBCPk4IC2qRF"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					17.9635910271395
				]
			]
		},
		{
			"type": "line",
			"version": 272,
			"versionNonce": 1915123659,
			"isDeleted": false,
			"id": "MSnNRwguT9Zk1yr-pGY1i",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1190.367179484946,
			"y": 737.113901645092,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 17.9635910271395,
			"seed": 2133712095,
			"groupIds": [
				"7hbWpIykMgBCPk4IC2qRF"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					17.9635910271395
				]
			]
		},
		{
			"type": "line",
			"version": 250,
			"versionNonce": 58064485,
			"isDeleted": false,
			"id": "cW7qYIS7Z028y1zm8m2jt",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1150.4480876168577,
			"y": 737.1139010174728,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 17.9635910271395,
			"seed": 675650207,
			"groupIds": [
				"7hbWpIykMgBCPk4IC2qRF"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					17.9635910271395
				]
			]
		},
		{
			"type": "line",
			"version": 229,
			"versionNonce": 364594795,
			"isDeleted": false,
			"id": "zzBRNl7bw5ZxQ-Ue7FZE-",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1394.1399067625266,
			"y": 645.1474156715378,
			"strokeColor": "#ffec99",
			"backgroundColor": "transparent",
			"width": 242.8411379594786,
			"height": 0,
			"seed": 1310560145,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					242.8411379594786,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 144,
			"versionNonce": 726854085,
			"isDeleted": false,
			"id": "OSnvKeze",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1501.7923222826798,
			"y": 664.8993109324784,
			"strokeColor": "#ffec99",
			"backgroundColor": "transparent",
			"width": 71.55215454101562,
			"height": 20,
			"seed": 805333265,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Constant",
			"rawText": "Constant",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Constant",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 128,
			"versionNonce": 385696011,
			"isDeleted": false,
			"id": "1_66LbU_1_P1u5z3VBXub",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1392.6239094382386,
			"y": 644.967332671538,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 241.51050158709813,
			"height": 99.79772792855272,
			"seed": 10186975,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					241.51050158709813,
					99.79772792855272
				]
			]
		},
		{
			"type": "line",
			"version": 79,
			"versionNonce": 1396402469,
			"isDeleted": false,
			"id": "5mdz776ygyQe9WRHXhNPk",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1390.6279548796674,
			"y": 744.7650606000907,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 238.18391065614628,
			"height": 98.46709155617214,
			"seed": 1569678641,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					238.18391065614628,
					-98.46709155617214
				]
			]
		},
		{
			"type": "text",
			"version": 110,
			"versionNonce": 526837675,
			"isDeleted": false,
			"id": "zicdZf3w",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1501.7923223630519,
			"y": 684.8993111186687,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 46.864105224609375,
			"height": 20,
			"seed": 512881681,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Linear",
			"rawText": "Linear",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Linear",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 480050309,
			"isDeleted": false,
			"id": "rX6LZLK7",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1501.792321611787,
			"y": 704.8993113537076,
			"strokeColor": "#e64980",
			"backgroundColor": "transparent",
			"width": 78.27218627929688,
			"height": 20,
			"seed": 1027852703,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Quadratic",
			"rawText": "Quadratic",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Quadratic",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 388,
			"versionNonce": 1159903819,
			"isDeleted": false,
			"id": "piVxvZNV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1986.1199089475494,
			"y": 656.4595197870935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 467.8729248046875,
			"height": 80,
			"seed": 1684156081,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "If we start with a constant polynomial we can\ninterpolate it in both ways which results in 2 linear\nfunctions which can also be interpolated and linearly added\nto form three quadratic functions",
			"rawText": "If we start with a constant polynomial we can\ninterpolate it in both ways which results in 2 linear\nfunctions which can also be interpolated and linearly added\nto form three quadratic functions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If we start with a constant polynomial we can\ninterpolate it in both ways which results in 2 linear\nfunctions which can also be interpolated and linearly added\nto form three quadratic functions",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 379,
			"versionNonce": 523576293,
			"isDeleted": false,
			"id": "EtRP19x2p6ohTjs2wroeY",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1392.0327447597278,
			"y": 745.5125085218205,
			"strokeColor": "#c2255c",
			"backgroundColor": "transparent",
			"width": 241.79648691288753,
			"height": 66.43753939475607,
			"seed": 920409343,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					77.73644065236749,
					-50.16712158379528
				],
				[
					121.57617753190038,
					-64.62971519353812
				],
				[
					162.2522220593023,
					-48.81125343288181
				],
				[
					241.79648691288753,
					1.8078242012179544
				]
			]
		},
		{
			"type": "line",
			"version": 357,
			"versionNonce": 1963669739,
			"isDeleted": false,
			"id": "ukmGioeCec9D4-ej_-qJO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1151.140169947449,
			"y": 747.772288773343,
			"strokeColor": "#c2255c",
			"backgroundColor": "transparent",
			"width": 240.44061876197406,
			"height": 102.14206736880863,
			"seed": 628477105,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-106.20967182154891,
					-11.298901257611533
				],
				[
					-171.29134306539117,
					-32.08887957161687
				],
				[
					-240.44061876197406,
					-102.14206736880863
				]
			]
		},
		{
			"type": "line",
			"version": 390,
			"versionNonce": 521232197,
			"isDeleted": false,
			"id": "q-Xp3jD_3rL1VAr-FQK0e",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1391.5807887094227,
			"y": 746.8683766727341,
			"strokeColor": "#c2255c",
			"backgroundColor": "transparent",
			"width": 240.44061876197384,
			"height": 102.14206736880853,
			"seed": 383451327,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					87.22751770876152,
					-9.491077056393692
				],
				[
					178.97459592056703,
					-30.73301142070352
				],
				[
					240.44061876197384,
					-102.14206736880853
				]
			]
		},
		{
			"type": "text",
			"version": 143,
			"versionNonce": 480961419,
			"isDeleted": false,
			"id": "DTVbdYqm",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1873.667846338403,
			"y": 390.0919823072302,
			"strokeColor": "#e03131",
			"backgroundColor": "#f783ac",
			"width": 321.9996337890625,
			"height": 25,
			"seed": 1381267793,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "cCkaK1w0mZjb2xEAV7HLI",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Which makes it affine invariant!!!",
			"rawText": "Which makes it affine invariant!!!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which makes it affine invariant!!!",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 278,
			"versionNonce": 42938021,
			"isDeleted": false,
			"id": "cCkaK1w0mZjb2xEAV7HLI",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1493.8431283039686,
			"y": 398.9029546715232,
			"strokeColor": "#e03131",
			"backgroundColor": "#f783ac",
			"width": 49.521366633705156,
			"height": 0.09029587273846573,
			"seed": 1964080817,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "dWzbF0kx",
				"focus": 0.041149203036402425,
				"gap": 13.650247723202483
			},
			"endBinding": {
				"elementId": "DTVbdYqm",
				"focus": -0.3195377997959703,
				"gap": 8.303717611666798
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
					-49.521366633705156,
					-0.09029587273846573
				]
			]
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 339491371,
			"isDeleted": false,
			"id": "YDtBvzTG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 22.296108270397752,
			"y": 254.76709063777875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 860.2391967773438,
			"height": 25,
			"seed": 867447583,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The derivative of a Bézier Curve is a polynomial and can be expressed in Bézier form:",
			"rawText": "The derivative of a Bézier Curve is a polynomial and can be expressed in Bézier form:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The derivative of a Bézier Curve is a polynomial and can be expressed in Bézier form:",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 214,
			"versionNonce": 140251653,
			"isDeleted": false,
			"id": "7OOyjBZwfLqVsJ7XsFxdM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 230.7266050210179,
			"y": 281.5315979204687,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 435.6033632743404,
			"height": 82.20063466747195,
			"seed": 852687711,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6528d8b732d36cd55d418bf5afec180fe6cf3f79",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 161,
			"versionNonce": 1219083467,
			"isDeleted": false,
			"id": "dYrxngsi4R23b_WbK4gZT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 698.8020952625931,
			"y": 292.7728144295078,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 276.9222139681026,
			"height": 62.2610346841036,
			"seed": 232496383,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e8be897c5c06f49328fc8c05870c30d7a929b52f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 181,
			"versionNonce": 1031113061,
			"isDeleted": false,
			"id": "rLW6xbEJ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 195.83549142636917,
			"y": 369.8077040251601,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 456.93951416015625,
			"height": 25,
			"seed": 662139263,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Which means that the first derivative of it is",
			"rawText": "Which means that the first derivative of it is",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which means that the first derivative of it is",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 196,
			"versionNonce": 630057835,
			"isDeleted": false,
			"id": "AhNw3gpSjhO3jwHAmZ1L_",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 260.03868990492185,
			"y": 406.5128203871351,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 328.5331187419778,
			"height": 45.6023582731402,
			"seed": 823450257,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c8486e02547241b6d2f0d5923f8b76bb356c207e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 229,
			"versionNonce": 858330309,
			"isDeleted": false,
			"id": "-MidnwL6Q1PzPEvu9L3Rc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 463.01569529292857,
			"y": 449.2669664178741,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 66.69100213211328,
			"height": 40.77921149479539,
			"seed": 1146019601,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "uATe1kBu",
				"focus": 0.5519476123582616,
				"gap": 6.907481505052033
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
					-7.221318702203348,
					31.009192074167345
				],
				[
					-66.69100213211328,
					40.77921149479539
				]
			]
		},
		{
			"type": "text",
			"version": 162,
			"versionNonce": 1060324875,
			"isDeleted": false,
			"id": "uATe1kBu",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 260.50493443408357,
			"y": 464.8865527446437,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 128.9122772216797,
			"height": 40,
			"seed": 535668017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-MidnwL6Q1PzPEvu9L3Rc",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Segments of the\ncontrol polygon",
			"rawText": "Segments of the\ncontrol polygon",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Segments of the\ncontrol polygon",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 193,
			"versionNonce": 1964258341,
			"isDeleted": false,
			"id": "DsJLRWlj",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 92.34863015904192,
			"y": 517.6579264566628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 712.3593139648438,
			"height": 25,
			"seed": 917807057,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "If we calculate the derivatives at each end of the curve we find that",
			"rawText": "If we calculate the derivatives at each end of the curve we find that",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If we calculate the derivatives at each end of the curve we find that",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 182,
			"versionNonce": 1016351915,
			"isDeleted": false,
			"id": "yPkQcS5Lg_HTFRUPAjANe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 299.5047905400237,
			"y": 547.8818300378778,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 304.8100951830437,
			"height": 77.11331093276206,
			"seed": 914854193,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "SS8Knnvw2oVthaLCkuTix",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6e3ba353ab32371d6c06f3bdd4550d48bf5ab567",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 446,
			"versionNonce": 1059350405,
			"isDeleted": false,
			"id": "4wIUyIapucRbuFVZQgOhG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 236.07007935499865,
			"y": 748.1894330997857,
			"strokeColor": "#e03131",
			"backgroundColor": "#1971c2",
			"width": 407.59214289277156,
			"height": 74.47034258399742,
			"seed": 1203375999,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					95.082669549211,
					-52.52818807264103
				],
				[
					227.4005103904207,
					-67.82120485328336
				],
				[
					331.79197276263136,
					-38.56499883814151
				],
				[
					407.59214289277156,
					6.649137730714062
				]
			]
		},
		{
			"type": "line",
			"version": 439,
			"versionNonce": 22773579,
			"isDeleted": false,
			"id": "MckcMGxj0MPDIpLQUH_DA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 240.46211422191803,
			"y": 743.8366157669416,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 408.04034398797603,
			"height": 114.05612006838791,
			"seed": 1776928671,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					85.999534383116,
					-93.3186436923174
				],
				[
					229.33209168830942,
					-100.02782722575198
				],
				[
					349.4874695143651,
					-64.65213223127873
				],
				[
					408.04034398797603,
					14.028292842635933
				]
			]
		},
		{
			"type": "ellipse",
			"version": 455,
			"versionNonce": 1939287781,
			"isDeleted": false,
			"id": "uVvWVJwbqOB7l_wSuACb0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 231.92315336118307,
			"y": 736.5175064577402,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 14.028292842635933,
			"height": 14.638218618402735,
			"seed": 2041412543,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "SS8Knnvw2oVthaLCkuTix",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 436,
			"versionNonce": 400776683,
			"isDeleted": false,
			"id": "POJKjWXJmI9Vls0tKzS5W",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 319.4475021837161,
			"y": 643.8087885411895,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 14.028292842635933,
			"height": 14.638218618402735,
			"seed": 455453663,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 432,
			"versionNonce": 1358563909,
			"isDeleted": false,
			"id": "WTYXssXFjBmclWv4a4j6h",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 459.73043061007564,
			"y": 637.0996050077549,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 14.028292842635933,
			"height": 14.638218618402735,
			"seed": 442685439,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 433,
			"versionNonce": 1530292363,
			"isDeleted": false,
			"id": "IazZ2AZY-ft-9mNdee16v",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 582.3255115391985,
			"y": 672.4753000022282,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 14.028292842635933,
			"height": 14.638218618402735,
			"seed": 1835368479,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "ku0_GNl5cNBkjfXioIiso",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 431,
			"versionNonce": 1747614117,
			"isDeleted": false,
			"id": "xKEcGLIwRBnImlV0gtn4C",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 640.2684602370425,
			"y": 747.4961704215423,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 14.028292842635933,
			"height": 14.638218618402735,
			"seed": 1981686847,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "ku0_GNl5cNBkjfXioIiso",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 282,
			"versionNonce": 1628380971,
			"isDeleted": false,
			"id": "vmsVi9VU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 212.20582461537217,
			"y": 738.9572095608073,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 11.364456176757812,
			"height": 18.615975257890536,
			"seed": 74269791,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "SS8Knnvw2oVthaLCkuTix",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 14.892780206312429,
			"fontFamily": 1,
			"text": "p1",
			"rawText": "p1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 255,
			"versionNonce": 1381367045,
			"isDeleted": false,
			"id": "iFQix1vm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 297.3612070202587,
			"y": 640.1492338865888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 17.924301147460938,
			"height": 18.615975257890536,
			"seed": 404971647,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "SS8Knnvw2oVthaLCkuTix",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 14.892780206312429,
			"fontFamily": 1,
			"text": "p2",
			"rawText": "p2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p2",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 258,
			"versionNonce": 601358795,
			"isDeleted": false,
			"id": "Z0M08dRW",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 436.65512585146087,
			"y": 629.1705699227869,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 17.463180541992188,
			"height": 18.615975257890533,
			"seed": 1661008031,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 14.892780206312427,
			"fontFamily": 1,
			"text": "p3",
			"rawText": "p3",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p3",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 246,
			"versionNonce": 653923429,
			"isDeleted": false,
			"id": "ldsNNovG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 599.2006812454587,
			"y": 658.4470071595923,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 16.853302001953125,
			"height": 18.615975257890536,
			"seed": 179735743,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ku0_GNl5cNBkjfXioIiso",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 14.892780206312429,
			"fontFamily": 1,
			"text": "p4",
			"rawText": "p4",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p4",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 254,
			"versionNonce": 1823182955,
			"isDeleted": false,
			"id": "u6MQDboL",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 660.967006089156,
			"y": 743.8366157669415,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 16.526046752929688,
			"height": 18.61597525789054,
			"seed": 719625439,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ku0_GNl5cNBkjfXioIiso",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 14.89278020631243,
			"fontFamily": 1,
			"text": "p5",
			"rawText": "p5",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p5",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 273,
			"versionNonce": 837042117,
			"isDeleted": false,
			"id": "lF1F8IYG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 250.93440939443465,
			"y": 735.9075806819734,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 27.816146850585938,
			"height": 18.615975257890536,
			"seed": 387688703,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 14.892780206312429,
			"fontFamily": 1,
			"text": "t=0",
			"rawText": "t=0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=0",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 251,
			"versionNonce": 2102676235,
			"isDeleted": false,
			"id": "hxoW0jUF",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 610.2362057517757,
			"y": 745.6663930942418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 21.613296508789062,
			"height": 18.615975257890536,
			"seed": 1557934367,
			"groupIds": [
				"uIV15wPlr5wf-rmRTU5ea"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 14.892780206312429,
			"fontFamily": 1,
			"text": "t=1",
			"rawText": "t=1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=1",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 709,
			"versionNonce": 1764884261,
			"isDeleted": false,
			"id": "ku0_GNl5cNBkjfXioIiso",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 595.9891683679482,
			"y": 687.4308548732348,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ced4da",
			"width": 59.394163187407685,
			"height": 81.00112901960892,
			"seed": 729493439,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ldsNNovG",
				"focus": 1.7085492350468054,
				"gap": 10.367872455751922
			},
			"endBinding": {
				"elementId": "u6MQDboL",
				"focus": -1.6602236916224637,
				"gap": 5.979392868011701
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
					59.394163187407685,
					81.00112901960892
				]
			]
		},
		{
			"type": "arrow",
			"version": 545,
			"versionNonce": 2051846571,
			"isDeleted": false,
			"id": "SS8Knnvw2oVthaLCkuTix",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 224.0100301053914,
			"y": 760.8401267145574,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ced4da",
			"width": 100.21126310369903,
			"height": 107.75404634806353,
			"seed": 1502508305,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "vmsVi9VU",
				"focus": 1.2414972112913214,
				"gap": 3.2669418958595315
			},
			"endBinding": {
				"elementId": "iFQix1vm",
				"focus": -1.206060957747622,
				"gap": 8.91430421988855
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
					100.21126310369903,
					-107.75404634806353
				]
			]
		},
		{
			"type": "text",
			"version": 313,
			"versionNonce": 592499333,
			"isDeleted": false,
			"id": "c1K5spgW",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 157.81923000722725,
			"y": 791.3570848155504,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 610.6992797851562,
			"height": 75,
			"seed": 285317553,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ku0_GNl5cNBkjfXioIiso",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The curve Tangents at these points are the derivatives\nof the curve at each point which are also the first and last\nsegment",
			"rawText": "The curve Tangents at these points are the derivatives\nof the curve at each point which are also the first and last\nsegment",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The curve Tangents at these points are the derivatives\nof the curve at each point which are also the first and last\nsegment",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 106,
			"versionNonce": 348079179,
			"isDeleted": false,
			"id": "YECaMRWmhB5hdPy6nW3Yq",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 87.23547208319724,
			"y": 239.88565691893723,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 697.3333333333331,
			"height": 2.6666666666666288,
			"seed": 766627921,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					697.3333333333331,
					2.6666666666666288
				]
			]
		},
		{
			"type": "line",
			"version": 141,
			"versionNonce": 217987557,
			"isDeleted": false,
			"id": "TrOw4BoO-LNj-hSj32364",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 81.08011574986391,
			"y": 873.6318569189373,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 697.3333333333331,
			"height": 2.6666666666666288,
			"seed": 2010578801,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					697.3333333333331,
					2.6666666666666288
				]
			]
		},
		{
			"type": "text",
			"version": 83,
			"versionNonce": 1954972395,
			"isDeleted": false,
			"id": "hMNxzD6k",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 299.70589939487195,
			"y": 888.3618473951278,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 284.2996826171875,
			"height": 25,
			"seed": 1029382431,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Variation Diminishing Property",
			"rawText": "Variation Diminishing Property",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Variation Diminishing Property",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 398,
			"versionNonce": 1598534981,
			"isDeleted": false,
			"id": "VT3sxm3A",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -23.989698429346845,
			"y": 925.4251713951279,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 951.799072265625,
			"height": 75,
			"seed": 885224817,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "THis property holds for Bezier curves and tells us that the curve does not oscillate more\nthan the polygon itself, meaning for any line, the number of intersections it has with the control\npolygon is always bigger than the number of intersections it has with the curve",
			"rawText": "THis property holds for Bezier curves and tells us that the curve does not oscillate more\nthan the polygon itself, meaning for any line, the number of intersections it has with the control\npolygon is always bigger than the number of intersections it has with the curve",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "THis property holds for Bezier curves and tells us that the curve does not oscillate more\nthan the polygon itself, meaning for any line, the number of intersections it has with the control\npolygon is always bigger than the number of intersections it has with the curve",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 112,
			"versionNonce": 1647111563,
			"isDeleted": false,
			"id": "9e8EJB9012LgF-8v4OA_D",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 273.8557407034657,
			"y": 1008.8618473951278,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 360,
			"height": 163,
			"seed": 817632017,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "MbDOWgfXSuix_1b-r5yBH",
					"type": "arrow"
				},
				{
					"id": "1dqa29BqBPCAcdMbXzIhp",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3886a838b45484a7ff32beaa5206b6e2f209d1ab",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 207,
			"versionNonce": 1435157669,
			"isDeleted": false,
			"id": "srG2ebDZ",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -472.2533393252437,
			"y": 1274.3618470627405,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 316.17730712890625,
			"height": 35,
			"seed": 519645582,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "De casteljau Algorithm",
			"rawText": "De casteljau Algorithm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "De casteljau Algorithm",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 314,
			"versionNonce": 820839467,
			"isDeleted": false,
			"id": "BvUHEgNV",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -635.6143012393062,
			"y": 1319.6081040627405,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 642.8992309570312,
			"height": 225,
			"seed": 2006275090,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Given a Bezier Curve, in order to find a point and tangent at a\ncertain interval on the point we consider the following recursion:\n\n\n\nDown until\n\n\nWe can generate the point",
			"rawText": "Given a Bezier Curve, in order to find a point and tangent at a\ncertain interval on the point we consider the following recursion:\n\n\n\nDown until\n\n\nWe can generate the point",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given a Bezier Curve, in order to find a point and tangent at a\ncertain interval on the point we consider the following recursion:\n\n\n\nDown until\n\n\nWe can generate the point",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 198,
			"versionNonce": 1668605957,
			"isDeleted": false,
			"id": "XwawXuQ-VPFWHxV-jzHhe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -534.9146857607907,
			"y": 1376.5992899601763,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 450.25,
			"height": 50.5088141025641,
			"seed": 662895374,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rbsQO7cwK58l_UWNUnHG0",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a8554fd4e53a79ec12cc91c520ed111094c44582",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 196,
			"versionNonce": 1756448459,
			"isDeleted": false,
			"id": "z_EyWUugKm62C7zHhaRZG",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -371.6646857607907,
			"y": 1471.8324630370994,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 125.00000000000001,
			"height": 41.02564102564103,
			"seed": 2090596750,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5d9eb0f8b9a5e237a04d6e54f0fd89cf1a188f7c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 210,
			"versionNonce": 721657701,
			"isDeleted": false,
			"id": "NWJmAc6r3xP5uJsRNTsIT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -384.6646857607907,
			"y": 1544.608103811818,
			"strokeColor": "transparent",
			"backgroundColor": "#ffec99",
			"width": 140.99999999999994,
			"height": 44.22509225092249,
			"seed": 430229330,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a859458e226e087ceb5b60ddb0fb7ea6cbf89078",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 341,
			"versionNonce": 806630763,
			"isDeleted": false,
			"id": "rbsQO7cwK58l_UWNUnHG0",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -190.4146857607907,
			"y": 1429.6081040627405,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 145,
			"height": 38.75,
			"seed": 2071713742,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XwawXuQ-VPFWHxV-jzHhe",
				"focus": -0.2680708552505472,
				"gap": 2.5000000000001137
			},
			"endBinding": {
				"elementId": "fOl3k1Iv",
				"focus": 1,
				"gap": 1
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
					66.25,
					38.75
				],
				[
					145,
					38.75
				]
			]
		},
		{
			"type": "text",
			"version": 269,
			"versionNonce": 847538885,
			"isDeleted": false,
			"id": "fOl3k1Iv",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -106.93450692778288,
			"y": 1468.3581040627405,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 320.5396423339844,
			"height": 100,
			"seed": 1687758290,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rbsQO7cwK58l_UWNUnHG0",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "an interpolation between two\npoints in a segment according to\nour interval in a Control polygon\nthat is one dimension lower!",
			"rawText": "an interpolation between two\npoints in a segment according to\nour interval in a Control polygon\nthat is one dimension lower!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "an interpolation between two\npoints in a segment according to\nour interval in a Control polygon\nthat is one dimension lower!",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 803,
			"versionNonce": 1986023435,
			"isDeleted": false,
			"id": "NU1LZO5kc6dgYnbILj4Kz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -676.5218239478597,
			"y": 1800.859691516662,
			"strokeColor": "#e03131",
			"backgroundColor": "#1971c2",
			"width": 739.5730608353222,
			"height": 143.19089280815123,
			"seed": 1247005650,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					236.24019587992223,
					-129.18495369155175
				],
				[
					460.20001668016323,
					-131.1260794176892
				],
				[
					618.1641538540084,
					-77.23440221615874
				],
				[
					739.5730608353222,
					12.06481339046204
				]
			]
		},
		{
			"type": "line",
			"version": 575,
			"versionNonce": 1519700517,
			"isDeleted": false,
			"id": "1LEDxKzL0WIBupahhFrHK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -668.5525077417876,
			"y": 1792.9615352488274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 740.3863185529455,
			"height": 206.9540232726469,
			"seed": 1900970386,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					156.04554695958933,
					-169.32601904125656
				],
				[
					416.1214585589051,
					-181.49978511611815
				],
				[
					634.142541899608,
					-117.31083672139346
				],
				[
					740.3863185529455,
					25.45423815652874
				]
			]
		},
		{
			"type": "ellipse",
			"version": 589,
			"versionNonce": 1569724075,
			"isDeleted": false,
			"id": "EfHictxa7nxehfd93oFxc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -684.0463918370663,
			"y": 1779.6810631671601,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 25.45423815652874,
			"height": 26.56094416333438,
			"seed": 1525448530,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 588,
			"versionNonce": 337788293,
			"isDeleted": false,
			"id": "okzwz19ZFw76APISOdpA6",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -525.2340798604628,
			"y": 1611.4617501327093,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 25.45423815652874,
			"height": 26.56094416333438,
			"seed": 1669645586,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 588,
			"versionNonce": 1682835787,
			"isDeleted": false,
			"id": "dWOxnaYxdSTtA_-anoZst",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -270.6916982951749,
			"y": 1599.2879840578476,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 25.45423815652874,
			"height": 26.56094416333438,
			"seed": 1150178002,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 588,
			"versionNonce": 1449805029,
			"isDeleted": false,
			"id": "NJF6rL7LkYTqGRkVi9Xnz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -48.24379092724985,
			"y": 1663.4769324525726,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 25.45423815652874,
			"height": 26.56094416333438,
			"seed": 1889544338,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 588,
			"versionNonce": 1341433835,
			"isDeleted": false,
			"id": "YA8Qd1k0pCXyU7MDbgRXV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 56.89327971928208,
			"y": 1799.601771289661,
			"strokeColor": "transparent",
			"backgroundColor": "#1971c2",
			"width": 25.45423815652874,
			"height": 26.56094416333438,
			"seed": 1869694546,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 414,
			"versionNonce": 1425694789,
			"isDeleted": false,
			"id": "9bOOOhXs",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -719.8233454077142,
			"y": 1784.1078871943826,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 20.639999389648438,
			"height": 33.778555455458694,
			"seed": 970501138,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 27.022844364366957,
			"fontFamily": 1,
			"text": "p1",
			"rawText": "p1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 404,
			"versionNonce": 1452176011,
			"isDeleted": false,
			"id": "zyELiHaP",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -565.3095062428789,
			"y": 1604.8215140918758,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 32.55390930175781,
			"height": 33.778555455458694,
			"seed": 365779410,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 27.022844364366957,
			"fontFamily": 1,
			"text": "p2",
			"rawText": "p2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p2",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 415,
			"versionNonce": 1974472613,
			"isDeleted": false,
			"id": "D0srU6GL",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -312.56167559384494,
			"y": 1584.900805969375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 31.7164306640625,
			"height": 33.778555455458694,
			"seed": 1919307666,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 27.022844364366957,
			"fontFamily": 1,
			"text": "p3",
			"rawText": "p3",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p3",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 407,
			"versionNonce": 148236587,
			"isDeleted": false,
			"id": "njS7Qc2j",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -17.62391483445242,
			"y": 1638.0226942960435,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 30.608779907226562,
			"height": 33.778555455458694,
			"seed": 1138396498,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 27.022844364366957,
			"fontFamily": 1,
			"text": "p4",
			"rawText": "p4",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p4",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 405,
			"versionNonce": 112775941,
			"isDeleted": false,
			"id": "79qMFiDn",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 94.4506447902645,
			"y": 1792.9615352488274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 30.014434814453125,
			"height": 33.778555455458694,
			"seed": 1602294546,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 27.022844364366957,
			"fontFamily": 1,
			"text": "p5",
			"rawText": "p5",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p5",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 407,
			"versionNonce": 2083883979,
			"isDeleted": false,
			"id": "T5SyMDDc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -649.550602210094,
			"y": 1778.5743571603548,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 50.51934814453125,
			"height": 33.778555455458694,
			"seed": 1473306834,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 27.022844364366957,
			"fontFamily": 1,
			"text": "t=0",
			"rawText": "t=0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=0",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 408,
			"versionNonce": 881994341,
			"isDeleted": false,
			"id": "1W1auF1T",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2.3999663403307068,
			"y": 1796.2816532692443,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1971c2",
			"width": 39.253814697265625,
			"height": 33.778555455458694,
			"seed": 1482749586,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 27.022844364366957,
			"fontFamily": 1,
			"text": "t=1",
			"rawText": "t=1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t=1",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 319,
			"versionNonce": 885512811,
			"isDeleted": false,
			"id": "p56Ft8DB",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -510.6488708397827,
			"y": 1808.636293178717,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 383.09954833984375,
			"height": 25,
			"seed": 1485765074,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We want to evaluate the point at 1/3",
			"rawText": "We want to evaluate the point at 1/3",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We want to evaluate the point at 1/3",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 229,
			"versionNonce": 1074369989,
			"isDeleted": false,
			"id": "OX0VI8aogItUM9ioLEl7f",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -629.314219227095,
			"y": 1728.0785088146313,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 17.742962236948642,
			"height": 16.93646395345081,
			"seed": 1999571666,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					17.742962236948642,
					16.93646395345081
				]
			]
		},
		{
			"type": "line",
			"version": 209,
			"versionNonce": 1331123467,
			"isDeleted": false,
			"id": "X_YpTy1woL7mHflM8pBqe",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -438.9806243216469,
			"y": 1607.103766289982,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 2.419494850493038,
			"height": 25.00144678842753,
			"seed": 1551654610,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.419494850493038,
					25.00144678842753
				]
			]
		},
		{
			"type": "line",
			"version": 203,
			"versionNonce": 1950127397,
			"isDeleted": false,
			"id": "AGiMWKaG2t_xIu2_ZhOhm",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -176.06218390140918,
			"y": 1623.2337319599353,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 8.871481118474321,
			"height": 19.35595880394385,
			"seed": 1857298962,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.871481118474321,
					19.35595880394385
				]
			]
		},
		{
			"type": "line",
			"version": 217,
			"versionNonce": 1801354155,
			"isDeleted": false,
			"id": "Afr2GtT-XfNaahTRhjmRM",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7.819424736057499,
			"y": 1715.1745362786687,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 18.549460520446246,
			"height": 12.097474252464963,
			"seed": 1482288398,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-18.549460520446246,
					12.097474252464963
				]
			]
		},
		{
			"type": "line",
			"version": 328,
			"versionNonce": 1553508485,
			"isDeleted": false,
			"id": "JX0fbqPHPelOMLPSPqyoO",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -621.2492363921184,
			"y": 1739.3694847835986,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 620.1971800097018,
			"height": 120.1682442411518,
			"seed": 469430738,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					182.26861207047148,
					-120.1682442411518
				],
				[
					440.34806278972326,
					-106.4577734216914
				],
				[
					620.1971800097018,
					-17.742962236948642
				]
			]
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 1426574923,
			"isDeleted": false,
			"id": "NDhyeQ4z",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -372.3653031365361,
			"y": 1698.006863613029,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 105.57987976074219,
			"height": 25,
			"seed": 123473426,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Recursion 1",
			"rawText": "Recursion 1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Recursion 1",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 216,
			"versionNonce": 987451365,
			"isDeleted": false,
			"id": "W1HDKpO7aSupcEHMGJGjT",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -572.8593393822582,
			"y": 1696.6250757582227,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 11.29097596896736,
			"height": 14.516969102958,
			"seed": 1025400594,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					11.29097596896736,
					14.516969102958
				]
			]
		},
		{
			"type": "line",
			"version": 196,
			"versionNonce": 1865272555,
			"isDeleted": false,
			"id": "FPvrAFLllJRowaUL_l63l",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -357.5242976883826,
			"y": 1613.5557525579636,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.6129965669953208,
			"height": 17.742962236948415,
			"seed": 1161300302,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.6129965669953208,
					17.742962236948415
				]
			]
		},
		{
			"type": "line",
			"version": 238,
			"versionNonce": 1024592709,
			"isDeleted": false,
			"id": "7xKrSaJ_gKmZyMCFPE623",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -117.18780920607946,
			"y": 1651.4611718823535,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 8.871481118474208,
			"height": 16.129965669953435,
			"seed": 813149522,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-8.871481118474208,
					16.129965669953435
				]
			]
		},
		{
			"type": "line",
			"version": 297,
			"versionNonce": 1566242699,
			"isDeleted": false,
			"id": "xfsWCxw-PK-r9Hah9CO62",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -566.4073531142769,
			"y": 1703.8835603097016,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 442.7675576402162,
			"height": 81.45632663326364,
			"seed": 1383617810,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					209.68955370939204,
					-81.45632663326364
				],
				[
					442.7675576402162,
					-42.744409025375944
				]
			]
		},
		{
			"type": "text",
			"version": 303,
			"versionNonce": 1939495589,
			"isDeleted": false,
			"id": "PT5y0OCc",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -374.35580431875815,
			"y": 1723.0083104014568,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 114.39987182617188,
			"height": 25,
			"seed": 1417585810,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Recursion 2",
			"rawText": "Recursion 2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Recursion 2",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 199,
			"versionNonce": 1841942059,
			"isDeleted": false,
			"id": "y6Ftytvo4RJkQ78gTu5vb",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -509.145974985943,
			"y": 1670.8171306862976,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 7.258484551479,
			"height": 16.93646395345081,
			"seed": 885240590,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					7.258484551479,
					16.93646395345081
				]
			]
		},
		{
			"type": "line",
			"version": 218,
			"versionNonce": 119651845,
			"isDeleted": false,
			"id": "nNusM00Zmemsr6E1T7Ubx",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -286.5524487405884,
			"y": 1624.0402302434331,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 6.451986267981283,
			"height": 19.355958803944077,
			"seed": 53635282,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.451986267981283,
					19.355958803944077
				]
			]
		},
		{
			"type": "line",
			"version": 225,
			"versionNonce": 1130680523,
			"isDeleted": false,
			"id": "eud0OwPiG_RIlrDXhvOQ3",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -504.306985284957,
			"y": 1677.2691169542788,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 214.528543410378,
			"height": 42.74440902537617,
			"seed": 965368658,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					214.528543410378,
					-42.74440902537617
				]
			]
		},
		{
			"type": "line",
			"version": 201,
			"versionNonce": 782611813,
			"isDeleted": false,
			"id": "-uHtahmFRAP8cxVzdX0K5",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -431.7221397701675,
			"y": 1658.7196564338326,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 8.064982834976604,
			"height": 20.162457087441453,
			"seed": 852350990,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.064982834976604,
					20.162457087441453
				]
			]
		},
		{
			"type": "text",
			"version": 281,
			"versionNonce": 1069973355,
			"isDeleted": false,
			"id": "0WJGRvyL",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -372.3653030687044,
			"y": 1752.0422487258468,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 113.77986145019531,
			"height": 25,
			"seed": 82382098,
			"groupIds": [
				"BGxqMD6hJ-lQ2g3W4XivB"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Recursion 3",
			"rawText": "Recursion 3",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Recursion 3",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 510,
			"versionNonce": 1702084805,
			"isDeleted": false,
			"id": "3hn2B78B",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -788.7098474916038,
			"y": 1840.23472667881,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 974.2191162109375,
			"height": 200,
			"seed": 936372430,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can also use this algorithm to evaluate the derivatives on a certain interval\n\n\n\n\n\nFurthermore if you have noticed, we can subdivide our control polygon into 2 control polygons that\ndescribe the same curve in the same Bezier representation",
			"rawText": "We can also use this algorithm to evaluate the derivatives on a certain interval\n\n\n\n\n\nFurthermore if you have noticed, we can subdivide our control polygon into 2 control polygons that\ndescribe the same curve in the same Bezier representation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can also use this algorithm to evaluate the derivatives on a certain interval\n\n\n\n\n\nFurthermore if you have noticed, we can subdivide our control polygon into 2 control polygons that\ndescribe the same curve in the same Bezier representation",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 220,
			"versionNonce": 758733323,
			"isDeleted": false,
			"id": "QEDplxNubR9s9dGIfOo-M",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -530.59395932871,
			"y": 1873.9289952552692,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 432.8585483716212,
			"height": 100.28401357073022,
			"seed": 139677454,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c743c8dc4d9e6969c005d7026b4415b37d61b32d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 220,
			"versionNonce": 1630101541,
			"isDeleted": false,
			"id": "zgE0APwefuDOV69lAVTGn",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -432.67930103805884,
			"y": 2050.779036425579,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 315.3102139436014,
			"height": 179.83653654574545,
			"seed": 26491598,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6044722cac12995d29b39c2dc2dddcb98b00727f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "rectangle",
			"version": 359,
			"versionNonce": 683139243,
			"isDeleted": false,
			"id": "Xxcvytd7UH0aW5dxe4g9z",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.4688924817105713,
			"x": -432.0423934427588,
			"y": 2108.349350990071,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 302.57358552311916,
			"height": 48.059311720035794,
			"seed": 703860174,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 332,
			"versionNonce": 1202983813,
			"isDeleted": false,
			"id": "GBIaJgEn",
			"fillStyle": "cross-hatch",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -801.9539803056541,
			"y": 2256.274611162362,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1026.87890625,
			"height": 50,
			"seed": 984908174,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This method of subdivision really helps with intersection calculation since we can ignore the halves that\ntheir control polygon does not get intersected according to the variation diminishing property",
			"rawText": "This method of subdivision really helps with intersection calculation since we can ignore the halves that\ntheir control polygon does not get intersected according to the variation diminishing property",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This method of subdivision really helps with intersection calculation since we can ignore the halves that\ntheir control polygon does not get intersected according to the variation diminishing property",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 239,
			"versionNonce": 1273795403,
			"isDeleted": false,
			"id": "MbDOWgfXSuix_1b-r5yBH",
			"fillStyle": "cross-hatch",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 422.2441308191021,
			"y": 1193.5928065401647,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 520,
			"height": 93.33333333333326,
			"seed": 459878418,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9e8EJB9012LgF-8v4OA_D",
				"focus": -0.281955006343326,
				"gap": 21.730959145036877
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
					-86.66666666666652,
					84.44444444444457
				],
				[
					-520,
					93.33333333333326
				]
			]
		},
		{
			"type": "line",
			"version": 741,
			"versionNonce": 626088677,
			"isDeleted": false,
			"id": "Gj2LsR_jFvdrc_wIVRR3i",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -611.0194530755896,
			"y": 1459.709458168077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 290.6780723366096,
			"height": 161.96784171044507,
			"seed": 1993615314,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.9666239458151864,
					76.15522715250181
				],
				[
					-247.6602219565018,
					63.15711945195079
				],
				[
					-246.8713608847986,
					122.82648543925163
				],
				[
					-289.71144839079443,
					44.34739546620601
				],
				[
					-246.95819058713167,
					-39.141356271193416
				],
				[
					-246.83874124575482,
					24.87164854757725
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 125,
			"versionNonce": 389149163,
			"isDeleted": false,
			"id": "zkTV340z",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1559.7474807219676,
			"y": 1351.2958769752988,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 481.1259765625,
			"height": 70,
			"seed": 1003960782,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "De Casteljau can also be used to\ncreate more control points!",
			"rawText": "De Casteljau can also be used to\ncreate more control points!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "De Casteljau can also be used to\ncreate more control points!",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 664,
			"versionNonce": 579778117,
			"isDeleted": false,
			"id": "BsPApitm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1689.9649247741263,
			"y": 1433.7567223536603,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 721.3392333984375,
			"height": 450,
			"seed": 614736914,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Say you have n degree control polynomial and you want to create an n+1\nControl polynomial that describes the same curve.\n\nWhy you might ask? well the more control points you have the\nmore control you have on little variations in the curve.\n\nRule:\nEvery N degree control polynomial has an N+i equivalent control\npolynomial that describes the same curve, whereas the opposite is not\nguaranteed.\n\n\nSo whats the algorithm to add more control points?\n\n\n\n\nOr if you want piece-wise (per segment) linear interpolation of points",
			"rawText": "Say you have n degree control polynomial and you want to create an n+1\nControl polynomial that describes the same curve.\n\nWhy you might ask? well the more control points you have the\nmore control you have on little variations in the curve.\n\nRule:\nEvery N degree control polynomial has an N+i equivalent control\npolynomial that describes the same curve, whereas the opposite is not\nguaranteed.\n\n\nSo whats the algorithm to add more control points?\n\n\n\n\nOr if you want piece-wise (per segment) linear interpolation of points",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Say you have n degree control polynomial and you want to create an n+1\nControl polynomial that describes the same curve.\n\nWhy you might ask? well the more control points you have the\nmore control you have on little variations in the curve.\n\nRule:\nEvery N degree control polynomial has an N+i equivalent control\npolynomial that describes the same curve, whereas the opposite is not\nguaranteed.\n\n\nSo whats the algorithm to add more control points?\n\n\n\n\nOr if you want piece-wise (per segment) linear interpolation of points",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 156,
			"versionNonce": 462584971,
			"isDeleted": false,
			"id": "2sMHQme-rZc5Ku7AHKf0O",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1597.2425456981264,
			"y": 1768.477052643236,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 529.3317680792861,
			"height": 75.13096063060836,
			"seed": 330626386,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ce86d18e727c4dc772f91a727a73c14bf356b675",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 95,
			"versionNonce": 2051646885,
			"isDeleted": false,
			"id": "AL2YVBMcniue9Wl858lB9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1495.5285615604244,
			"y": 1891.3644590302015,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 332.46650668934075,
			"height": 65.41308525115188,
			"seed": 177804046,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a62e5411e0a92ca5c4ac4441371d28020d0e239b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 1690874667,
			"isDeleted": false,
			"id": "Gx3kUnFQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1614.1450625100588,
			"y": 1961.7427518838988,
			"strokeColor": "#e03131",
			"backgroundColor": "#ced4da",
			"width": 550.4171752929688,
			"height": 40,
			"seed": 1605919246,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Note that the interpolation is not the same for every segment unlike\nthe previous algorithm",
			"rawText": "Note that the interpolation is not the same for every segment unlike\nthe previous algorithm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note that the interpolation is not the same for every segment unlike\nthe previous algorithm",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 144,
			"versionNonce": 800041221,
			"isDeleted": false,
			"id": "DzZEYRAGG2rexWZUXwgbC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1450.5829806348067,
			"y": 2009.6690385978873,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 227.38217895649373,
			"height": 185.12200424911907,
			"seed": 1597534738,
			"groupIds": [
				"svKJIoRKBqKmIua2V_Pjb"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7f0c87bb06ca8a4604e1bc8b59eb0fd80dd826c1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 225,
			"versionNonce": 591336907,
			"isDeleted": false,
			"id": "yuTvhWyd5dTysvdRbWayr",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 70,
			"angle": 0,
			"x": -1433.9589466478442,
			"y": 2178.3080562951845,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 199.7436477977783,
			"height": 160.97276775840623,
			"seed": 1101929682,
			"groupIds": [
				"svKJIoRKBqKmIua2V_Pjb"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.49077063340973837,
					-122.20188771903395
				],
				[
					99.62643858218416,
					-160.97276775840623
				],
				[
					199.25287716436856,
					-119.25726391857552
				],
				[
					199.7436477977783,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 147,
			"versionNonce": 71188581,
			"isDeleted": false,
			"id": "bAsU4HPQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1685.0566938623563,
			"y": 2211.634312534098,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 733.8392333984375,
			"height": 50,
			"seed": 1736652110,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "And this result is much better than subdividing the curve into two control\npolygons because of a simple caveat",
			"rawText": "And this result is much better than subdividing the curve into two control\npolygons because of a simple caveat",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "And this result is much better than subdividing the curve into two control\npolygons because of a simple caveat",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 234,
			"versionNonce": 370156651,
			"isDeleted": false,
			"id": "zW__v_-7ALjRfHGb739h0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1450.5829811351434,
			"y": 2270.2783578065023,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 222.83569085594618,
			"height": 181.42050489094305,
			"seed": 117208850,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2051be5b548c025a89af9335f5c4b968751c0583",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 233,
			"versionNonce": 767749061,
			"isDeleted": false,
			"id": "WIUxgA-eub4EIy3m2Y__q",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1336.1356094357798,
			"y": 2316.502820465008,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 99.36554861799459,
			"height": 120.42314832511966,
			"seed": 1095490258,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-67.77914905730745,
					3.9482999450860916
				],
				[
					-91.46894872782286,
					37.50884947831628
				],
				[
					-99.36554861799459,
					120.42314832511966
				]
			]
		},
		{
			"type": "line",
			"version": 153,
			"versionNonce": 889609995,
			"isDeleted": false,
			"id": "i1uA8uPLXNfybNsNArkwA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1336.1356094357798,
			"y": 2316.502820465008,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 96.07529866375626,
			"height": 116.47484838003356,
			"seed": 1470080590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					61.19864914883101,
					1.3160999816955155
				],
				[
					91.46894872782286,
					44.08934938679249
				],
				[
					96.07529866375626,
					116.47484838003356
				]
			]
		},
		{
			"type": "ellipse",
			"version": 106,
			"versionNonce": 1281043237,
			"isDeleted": false,
			"id": "jqKW_6QxViNN86qVY4LtE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1440.7655579805557,
			"y": 2425.739118945717,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 14.477099798648162,
			"height": 14.4770997986484,
			"seed": 1621998670,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 108,
			"versionNonce": 446449067,
			"isDeleted": false,
			"id": "_jCdi1N1DfgM2gPHzN2tC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1436.1592080446217,
			"y": 2348.089220025695,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 14.477099798648162,
			"height": 14.4770997986484,
			"seed": 143598674,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 108,
			"versionNonce": 544505477,
			"isDeleted": false,
			"id": "uRuDBA3SUR9gWV8V6tqf8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1411.8113583832592,
			"y": 2315.1867204833125,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 14.477099798648162,
			"height": 14.4770997986484,
			"seed": 1267447762,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 133,
			"versionNonce": 771512395,
			"isDeleted": false,
			"id": "vzjmU4EDISzzZrm31KzH8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1347.9805092710374,
			"y": 2307.2901205931403,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 14.477099798648162,
			"height": 14.4770997986484,
			"seed": 1209625426,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 114,
			"versionNonce": 13395429,
			"isDeleted": false,
			"id": "1goiF6CH4cYEo-GvXIZ4i",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1285.4657601405113,
			"y": 2309.2642705656835,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 14.477099798648162,
			"height": 14.4770997986484,
			"seed": 1647891410,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 114,
			"versionNonce": 218175211,
			"isDeleted": false,
			"id": "fUjurMihqOlFvlitkzS6x",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1249.931060634738,
			"y": 2355.327769925019,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 14.477099798648162,
			"height": 14.4770997986484,
			"seed": 232937362,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 109,
			"versionNonce": 275800389,
			"isDeleted": false,
			"id": "aZNINRY4zKUKtNgXfTRGa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1247.2988606713475,
			"y": 2424.423018964022,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 14.477099798648162,
			"height": 14.4770997986484,
			"seed": 546153298,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 347,
			"versionNonce": 909443467,
			"isDeleted": false,
			"id": "UiUyBtuY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "dashed",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1802.915150378186,
			"y": 2451.698863314205,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 933.55908203125,
			"height": 75,
			"seed": 204433554,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Moving the top three points (the tangent points) around will destroy the equivalence\nof the two control polygons because the middle point is always supposed to be tangental\nto the curve alongside the fact that the distance to the left and right point must be equal",
			"rawText": "Moving the top three points (the tangent points) around will destroy the equivalence\nof the two control polygons because the middle point is always supposed to be tangental\nto the curve alongside the fact that the distance to the left and right point must be equal",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Moving the top three points (the tangent points) around will destroy the equivalence\nof the two control polygons because the middle point is always supposed to be tangental\nto the curve alongside the fact that the distance to the left and right point must be equal",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 487,
			"versionNonce": 884863141,
			"isDeleted": false,
			"id": "qO5qlHfUyASYJkygpum-v",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1318.2334808604219,
			"y": 2565.4373363588,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 2049.4900375569637,
			"height": 558.951828424626,
			"seed": 82930898,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					196.38848025730113,
					239.19109774927665
				],
				[
					1178.3308815438065,
					186.31727614154215
				],
				[
					1604.1747395139455,
					-280.2290283688544
				],
				[
					2049.4900375569637,
					-319.76073067534935
				]
			]
		},
		{
			"type": "text",
			"version": 40,
			"versionNonce": 1926404139,
			"isDeleted": false,
			"id": "s4deMXZO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 785.0525088407144,
			"y": 2230.6410036255716,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 113.0400390625,
			"height": 45,
			"seed": 1098374862,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Splines",
			"rawText": "Splines",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Splines",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 195,
			"versionNonce": 1264751621,
			"isDeleted": false,
			"id": "1dqa29BqBPCAcdMbXzIhp",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 431.17096065478404,
			"y": 1190.717974557692,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 438.7460856727539,
			"height": 1016.8424406126921,
			"seed": 1090419598,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9e8EJB9012LgF-8v4OA_D",
				"focus": 0.10801348223447892,
				"gap": 18.856127162564235
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
					-15.10680617363846,
					508.59580784583136
				],
				[
					390.2591594856626,
					679.8062778137348
				],
				[
					423.63927949911545,
					1016.8424406126921
				]
			]
		},
		{
			"type": "text",
			"version": 1974,
			"versionNonce": 12868299,
			"isDeleted": false,
			"id": "ve79aYX4",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 252.69028957218018,
			"y": 2281.422874340168,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 1184.6988525390625,
			"height": 1100,
			"seed": 1913461390,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Bezier Curves are great, they offer nice control and good algorithms, one issue arises that leads us\nto splines though.\n\nLets say we have a curve that we re-parameterized into a high degree because we want more control and\nwant it to be intricate. at extreme degrees of control polynomials, the control points start having small to\nlittle effect on the curve, and it would require change in a lot of control points to get a desired shape.\n\n\nOkay well we cant use low degree Bezier curves in order to get intricate shapes, and using high degree polynomials\nis hard, the Idea behind splines is to split the entire curve into segments each of which are Bezier curves of low\ndegree on their own, that way we also offer locality to the change of control points, a few rules need to be put in \nplace first to achieve this.\n\nWe define the spline over segments u0....un, where ui is the point that connects the two bezier segments.\nWe need to offer a smooth transition from one curve into another in order to simulate regularity and not\nbe so obvious about the segmentation.\n\n1) Every Bezier segment must be regular and continuously differentiable on its own.\n\n2) at ui, both the positions and the derivatives of the connected segments must match\nfor this we define the following terms:\n\n\n\n\n\n\n\nSo for a Bezier spline to be Parametrically continuous it would require \n\n\n\nso for C0 only the locations have to match, for C1  it would have to C0 continuous and the first derivatives have to\nmatch meaning the length of the connecting segments in the control polygon have to be the same\n\n\n\n\n\n\n\n\nAnd for C2 which dictates that the transition has the same curvature on both ends we need\n",
			"rawText": "Bezier Curves are great, they offer nice control and good algorithms, one issue arises that leads us\nto splines though.\n\nLets say we have a curve that we re-parameterized into a high degree because we want more control and\nwant it to be intricate. at extreme degrees of control polynomials, the control points start having small to\nlittle effect on the curve, and it would require change in a lot of control points to get a desired shape.\n\n\nOkay well we cant use low degree Bezier curves in order to get intricate shapes, and using high degree polynomials\nis hard, the Idea behind splines is to split the entire curve into segments each of which are Bezier curves of low\ndegree on their own, that way we also offer locality to the change of control points, a few rules need to be put in \nplace first to achieve this.\n\nWe define the spline over segments u0....un, where ui is the point that connects the two bezier segments.\nWe need to offer a smooth transition from one curve into another in order to simulate regularity and not\nbe so obvious about the segmentation.\n\n1) Every Bezier segment must be regular and continuously differentiable on its own.\n\n2) at ui, both the positions and the derivatives of the connected segments must match\nfor this we define the following terms:\n\n\n\n\n\n\n\nSo for a Bezier spline to be Parametrically continuous it would require \n\n\n\nso for C0 only the locations have to match, for C1  it would have to C0 continuous and the first derivatives have to\nmatch meaning the length of the connecting segments in the control polygon have to be the same\n\n\n\n\n\n\n\n\nAnd for C2 which dictates that the transition has the same curvature on both ends we need\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bezier Curves are great, they offer nice control and good algorithms, one issue arises that leads us\nto splines though.\n\nLets say we have a curve that we re-parameterized into a high degree because we want more control and\nwant it to be intricate. at extreme degrees of control polynomials, the control points start having small to\nlittle effect on the curve, and it would require change in a lot of control points to get a desired shape.\n\n\nOkay well we cant use low degree Bezier curves in order to get intricate shapes, and using high degree polynomials\nis hard, the Idea behind splines is to split the entire curve into segments each of which are Bezier curves of low\ndegree on their own, that way we also offer locality to the change of control points, a few rules need to be put in \nplace first to achieve this.\n\nWe define the spline over segments u0....un, where ui is the point that connects the two bezier segments.\nWe need to offer a smooth transition from one curve into another in order to simulate regularity and not\nbe so obvious about the segmentation.\n\n1) Every Bezier segment must be regular and continuously differentiable on its own.\n\n2) at ui, both the positions and the derivatives of the connected segments must match\nfor this we define the following terms:\n\n\n\n\n\n\n\nSo for a Bezier spline to be Parametrically continuous it would require \n\n\n\nso for C0 only the locations have to match, for C1  it would have to C0 continuous and the first derivatives have to\nmatch meaning the length of the connecting segments in the control polygon have to be the same\n\n\n\n\n\n\n\n\nAnd for C2 which dictates that the transition has the same curvature on both ends we need\n",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 54,
			"versionNonce": 542886757,
			"isDeleted": false,
			"id": "F3eJpzilQnaCK8KkF1pS_",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1427.5752034284087,
			"y": 2276.2579232336307,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 543,
			"height": 287,
			"seed": 1241482574,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f73a276784a880ffcf516c0cf1597cbe9413317d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 264,
			"versionNonce": 2091174251,
			"isDeleted": false,
			"id": "sGhbmdEM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 327.57709423433937,
			"y": 2821.852141833067,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 1083.518798828125,
			"height": 50,
			"seed": 1254232530,
			"groupIds": [
				"7ncOfIF3CpEmxIVN8hWbV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Parametric continuity / C - Continuous\nis when all the segments in the spline match their derivative up to degree n on the segment connection points",
			"rawText": "Parametric continuity / C - Continuous\nis when all the segments in the spline match their derivative up to degree n on the segment connection points",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Parametric continuity / C - Continuous\nis when all the segments in the spline match their derivative up to degree n on the segment connection points",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 408,
			"versionNonce": 603395781,
			"isDeleted": false,
			"id": "sgxv37Sx",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 202.4271302650959,
			"y": 2901.2710142291567,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#e03131",
			"width": 1333.8187255859375,
			"height": 50,
			"seed": 1319591890,
			"groupIds": [
				"7ncOfIF3CpEmxIVN8hWbV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Geometric continuity / G - Continuous\nis when all the segments in the spline can be reparameterized such that the connection such that the connection with be C continuous",
			"rawText": "Geometric continuity / G - Continuous\nis when all the segments in the spline can be reparameterized such that the connection such that the connection with be C continuous",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Geometric continuity / G - Continuous\nis when all the segments in the spline can be reparameterized such that the connection such that the connection with be C continuous",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 64,
			"versionNonce": 197026827,
			"isDeleted": false,
			"id": "QJSPNmvi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1425.533566473121,
			"y": 2920.4265288406446,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#e03131",
			"width": 9.339996337890625,
			"height": 25,
			"seed": 1314308558,
			"groupIds": [
				"7ncOfIF3CpEmxIVN8hWbV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 62,
			"versionNonce": 1624372773,
			"isDeleted": false,
			"id": "o0SSi9Aw",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 923.3247733872663,
			"y": 2894.612058168007,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#e03131",
			"width": 9.339996337890625,
			"height": 25,
			"seed": 1829063950,
			"groupIds": [
				"7ncOfIF3CpEmxIVN8hWbV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 83,
			"versionNonce": 1175169707,
			"isDeleted": false,
			"id": "wGhOv0hb",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 928.0183135095641,
			"y": 2815.229111425265,
			"strokeColor": "#1971c2",
			"backgroundColor": "#e03131",
			"width": 9.339996337890625,
			"height": 25,
			"seed": 1279760978,
			"groupIds": [
				"7ncOfIF3CpEmxIVN8hWbV"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 161,
			"versionNonce": 836364677,
			"isDeleted": false,
			"id": "xGbNRsVMdTW3Qvs5f1rMT",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 626.3542267235279,
			"y": 3006.4228740863173,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 437.3709785019726,
			"height": 69.33139955512752,
			"seed": 690753166,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c39949c5fda3ffd6877fb2d26b814559cb0bd0d5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 127,
			"versionNonce": 1614224715,
			"isDeleted": false,
			"id": "n-jtrBtxu51CTThYIBUo1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 607.8648798445406,
			"y": 3147.8868449553333,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 455.34762199209365,
			"height": 129.57892328689294,
			"seed": 1152187218,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a2de4e34f1bf91111d4aa9c1a056860b4943c123",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 135,
			"versionNonce": 944533733,
			"isDeleted": false,
			"id": "78GCXjWFtZfMkIDd_hB1F",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 730.8945634827714,
			"y": 3272.0012174733224,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 215.15153583192864,
			"height": 22.79147625338227,
			"seed": 1813920914,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "559f3a8430eb1fe05c281e187e8c66271bf23074",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 91,
			"versionNonce": 362494955,
			"isDeleted": false,
			"id": "1p86HeEpjss1Ka4i2lxQk",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 604.9013660155617,
			"y": 3370.7592895222174,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 484.1515227823126,
			"height": 225.599400668198,
			"seed": 1693155346,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5f0d0c2fc2aa7db33e1a4c9fa358f881836c2004",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 245,
			"versionNonce": 297208901,
			"isDeleted": false,
			"id": "eRi3gZ3d",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 189.85786471140568,
			"y": 3616.3315586977274,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 1314.238525390625,
			"height": 50,
			"seed": 1845349266,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "And to be clear, these smoothness conditions are necessary to make a spline smooth but theyre not sufficient as there can always\nbe examples of non-smooth splines that apply these conditions using intersections to create cusps",
			"rawText": "And to be clear, these smoothness conditions are necessary to make a spline smooth but theyre not sufficient as there can always\nbe examples of non-smooth splines that apply these conditions using intersections to create cusps",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "And to be clear, these smoothness conditions are necessary to make a spline smooth but theyre not sufficient as there can always\nbe examples of non-smooth splines that apply these conditions using intersections to create cusps",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 539,
			"versionNonce": 1380091531,
			"isDeleted": false,
			"id": "jC1uX7uFx72ij8P-9aeo-",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1655.4916700956396,
			"y": 2857.947551401456,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 697.777777777778,
			"height": 295.00000000000034,
			"seed": 639774030,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.30727023319605,
					176.66666666666652
				],
				[
					428.57338820301777,
					123.3333333333332
				],
				[
					430.727023319616,
					226.66666666666646
				],
				[
					697.777777777778,
					71.66666666666652
				],
				[
					433.223593964335,
					-68.33333333333391
				],
				[
					430.727023319616,
					45
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 102,
			"versionNonce": 1308048293,
			"isDeleted": false,
			"id": "te4cV73j",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2949.408890438366,
			"y": 2246.042789496695,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 147.78460693359375,
			"height": 35,
			"seed": 1644727058,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "B - Splines",
			"rawText": "B - Splines",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "B - Splines",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 859,
			"versionNonce": 484932907,
			"isDeleted": false,
			"id": "qjAEw5vQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1491.933304012849,
			"y": 3107.2526381877674,
			"strokeColor": "#e03131",
			"backgroundColor": "#ced4da",
			"width": 960.01904296875,
			"height": 250,
			"seed": 1742908626,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Two issues arise when talking about Bezier Splines\n\nThe first issue is regarding the formulation, because we are concatenating\ndifferent Bezier splines we have now lost the formulation of C_point * Basis_function\nWhich is a convenient formulation that we want\n\nThe second issue is regarding our claim of Local control\neven though we defined our segments as different Bezier curves, our smoothness terms still\nforce us to change connecting segments accordingly which removes the whole idea of local control\n(although it decays exponentially the further you go along the curve)",
			"rawText": "Two issues arise when talking about Bezier Splines\n\nThe first issue is regarding the formulation, because we are concatenating\ndifferent Bezier splines we have now lost the formulation of C_point * Basis_function\nWhich is a convenient formulation that we want\n\nThe second issue is regarding our claim of Local control\neven though we defined our segments as different Bezier curves, our smoothness terms still\nforce us to change connecting segments accordingly which removes the whole idea of local control\n(although it decays exponentially the further you go along the curve)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Two issues arise when talking about Bezier Splines\n\nThe first issue is regarding the formulation, because we are concatenating\ndifferent Bezier splines we have now lost the formulation of C_point * Basis_function\nWhich is a convenient formulation that we want\n\nThe second issue is regarding our claim of Local control\neven though we defined our segments as different Bezier curves, our smoothness terms still\nforce us to change connecting segments accordingly which removes the whole idea of local control\n(although it decays exponentially the further you go along the curve)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 156,
			"versionNonce": 624590597,
			"isDeleted": false,
			"id": "L_qEPvRTKNh8VZOX56wXM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2600.301194156899,
			"y": 2346.2683571145517,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 846,
			"height": 46,
			"seed": 1911801998,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a893d0602ec69fff13c86306edddd75f8f955e94",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 1226,
			"versionNonce": 1089773515,
			"isDeleted": false,
			"id": "E7VVCdKO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2453.473881429619,
			"y": 2317.9736011399586,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 1146.27880859375,
			"height": 1000,
			"seed": 1533862862,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets define the following t as a sequence of weakly increasing knots\n\n\n\nsuch that\n\n\nThen we recursively define the following functions\n\n\n\n\n\n\n\n\nWhich another convex affine combination interpolation using the intervals we have over the lower\ndegree polynomial and the reason we have identical elements at the start and the end of the sequence is because\nwe want to define our function in those end points (One that touches that point).\nWe can also denote the following which provides us with local support\n\n\n\nB-splines also have some useful properties\n\n1) Partition of unity\n(The sum of all Basis functions =1)\n\n\n2) Smoothness\nif a knot consists of mu points on top of each other then the B-spline\nof degree n is C^(n-mu) continuous\n\n\n\n\nmore over if we have n control points that are the same\nthe curve would interpolate that point\nand if n+1 points are on a line, the curve interpolates a segment of\nthat line",
			"rawText": "Lets define the following t as a sequence of weakly increasing knots\n\n\n\nsuch that\n\n\nThen we recursively define the following functions\n\n\n\n\n\n\n\n\nWhich another convex affine combination interpolation using the intervals we have over the lower\ndegree polynomial and the reason we have identical elements at the start and the end of the sequence is because\nwe want to define our function in those end points (One that touches that point).\nWe can also denote the following which provides us with local support\n\n\n\nB-splines also have some useful properties\n\n1) Partition of unity\n(The sum of all Basis functions =1)\n\n\n2) Smoothness\nif a knot consists of mu points on top of each other then the B-spline\nof degree n is C^(n-mu) continuous\n\n\n\n\nmore over if we have n control points that are the same\nthe curve would interpolate that point\nand if n+1 points are on a line, the curve interpolates a segment of\nthat line",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets define the following t as a sequence of weakly increasing knots\n\n\n\nsuch that\n\n\nThen we recursively define the following functions\n\n\n\n\n\n\n\n\nWhich another convex affine combination interpolation using the intervals we have over the lower\ndegree polynomial and the reason we have identical elements at the start and the end of the sequence is because\nwe want to define our function in those end points (One that touches that point).\nWe can also denote the following which provides us with local support\n\n\n\nB-splines also have some useful properties\n\n1) Partition of unity\n(The sum of all Basis functions =1)\n\n\n2) Smoothness\nif a knot consists of mu points on top of each other then the B-spline\nof degree n is C^(n-mu) continuous\n\n\n\n\nmore over if we have n control points that are the same\nthe curve would interpolate that point\nand if n+1 points are on a line, the curve interpolates a segment of\nthat line",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 131,
			"versionNonce": 1845384805,
			"isDeleted": false,
			"id": "szx8hAWC2QnOPOEcJABB2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2894.4251112929282,
			"y": 2446.268357045405,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 257.75216607169114,
			"height": 39.161240701500034,
			"seed": 1983810066,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "654475de15875789ddc830bc83830d06e64ffc6d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 148,
			"versionNonce": 948203115,
			"isDeleted": false,
			"id": "KoxD0J7NUsTrlWQfJe8GI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2745.489679215435,
			"y": 2541.5124811886126,
			"strokeColor": "transparent",
			"backgroundColor": "#ced4da",
			"width": 596.6824255311785,
			"height": 151.20896249485764,
			"seed": 340609358,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "MV6T23AFIhsapd8Zl2m-i",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b5e88439ee2264f116b1db93f8f122af32cab3ef",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 135,
			"versionNonce": 1393574341,
			"isDeleted": false,
			"id": "l_vOHVzLoz7mTq4amffZc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3366.2699481537798,
			"y": 2319.0636390006234,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 289.77629089013135,
			"height": 87.87540344577928,
			"seed": 887072427,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					147.61904761904725,
					-80.95238095238074
				],
				[
					289.77629089013135,
					-87.87540344577928
				]
			]
		},
		{
			"type": "text",
			"version": 110,
			"versionNonce": 1449224459,
			"isDeleted": false,
			"id": "0qMUmgpE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3826.4253135073236,
			"y": 2140.9684009053854,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 235.87974548339844,
			"height": 25,
			"seed": 1175203301,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Knots vs Control Points",
			"rawText": "Knots vs Control Points",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Knots vs Control Points",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 120,
			"versionNonce": 1234026789,
			"isDeleted": false,
			"id": "iLbEOHyG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3688.7528513041816,
			"y": 2171.619684209061,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 498.5994567871094,
			"height": 50,
			"seed": 534076683,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Knots live in parameter space and they define the\nintervals that we see",
			"rawText": "Knots live in parameter space and they define the\nintervals that we see",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Knots live in parameter space and they define the\nintervals that we see",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 134,
			"versionNonce": 805703595,
			"isDeleted": false,
			"id": "IWys09TbJOMFX6ufzMqZy",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3720.342323049344,
			"y": 2348.470982945959,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 446.01602883194073,
			"height": 2.834699558035936,
			"seed": 934634379,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "2Eu-p23QIAN-hZ2POiXN8",
				"focus": -0.37385092202190434,
				"gap": 9.67490083878241
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
					446.01602883194073,
					2.834699558035936
				]
			]
		},
		{
			"type": "line",
			"version": 742,
			"versionNonce": 1189368965,
			"isDeleted": false,
			"id": "u0SdUzUit0FSOedx_wieq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3744.5401426078206,
			"y": 2339.5230509600433,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 397.1571754648212,
			"height": 96.61757866040216,
			"seed": 66074437,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					77.7653681900797,
					-12.56814031354861
				],
				[
					135.89301714024077,
					-96.61757866040216
				],
				[
					175.953964389676,
					-96.61757866040216
				],
				[
					226.22652564386908,
					-7.069578926370923
				],
				[
					285.9251921332234,
					-7.855087695967086
				],
				[
					328.34266569144893,
					-70.69578926370923
				],
				[
					397.1571754648212,
					-30.38636617701468
				]
			]
		},
		{
			"type": "line",
			"version": 56,
			"versionNonce": 1201463883,
			"isDeleted": false,
			"id": "cVJcxYGlVccBB-5K6BurV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3743.07851641405,
			"y": 2338.9704050765195,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0,
			"height": 20.082405846862457,
			"seed": 1251864523,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					20.082405846862457
				]
			]
		},
		{
			"type": "line",
			"version": 68,
			"versionNonce": 919698405,
			"isDeleted": false,
			"id": "1TSUFU4yQYORQvrlZU9zs",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4146.804123611313,
			"y": 2337.5854115698394,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0,
			"height": 20.082405846862457,
			"seed": 1891096043,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					20.082405846862457
				]
			]
		},
		{
			"type": "line",
			"version": 66,
			"versionNonce": 1979736299,
			"isDeleted": false,
			"id": "yG3YbyARoNjblOrvTER7r",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4050.547075130343,
			"y": 2341.7050320898793,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0,
			"height": 20.082405846862457,
			"seed": 2037456715,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					20.082405846862457
				]
			]
		},
		{
			"type": "line",
			"version": 51,
			"versionNonce": 828553029,
			"isDeleted": false,
			"id": "IF4DOhPdcfimgvyqRR_vj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3954.2900261827726,
			"y": 2340.3553985832,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0,
			"height": 20.082405846862457,
			"seed": 757311819,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					20.082405846862457
				]
			]
		},
		{
			"type": "line",
			"version": 81,
			"versionNonce": 347802507,
			"isDeleted": false,
			"id": "NMqX4RvBaM1PbytBSPNir",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3848.6842706750817,
			"y": 2338.1224437897777,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 0,
			"height": 20.082405846862457,
			"seed": 909995595,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
					20.082405846862457
				]
			]
		},
		{
			"type": "ellipse",
			"version": 133,
			"versionNonce": 1895138981,
			"isDeleted": false,
			"id": "fVMvKnSfFm5jR_im0dcGu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3737.2497603517168,
			"y": 2353.14534237997,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.0024577934214,
			"height": 7.617464286740869,
			"seed": 636308203,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 145,
			"versionNonce": 1745314347,
			"isDeleted": false,
			"id": "2yLMmajMc8kmWgXvHapEW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3844.3448183548585,
			"y": 2352.457196617631,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.0024577934214,
			"height": 7.617464286740869,
			"seed": 231933477,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 164,
			"versionNonce": 137849349,
			"isDeleted": false,
			"id": "Qf3-i1mwmURajtHLqbWrg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3950.112349192377,
			"y": 2356.392934843457,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.0024577934214,
			"height": 7.617464286740869,
			"seed": 1066503941,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "eCgUhLqzHjmMLSC7KBSoR",
					"type": "arrow"
				}
			],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 169,
			"versionNonce": 1221584075,
			"isDeleted": false,
			"id": "Hf_63YI8q4kSn_G_8bii5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4046.3346280359474,
			"y": 2354.868861853977,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.0024577934214,
			"height": 7.617464286740869,
			"seed": 1329108709,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 221,
			"versionNonce": 1478877541,
			"isDeleted": false,
			"id": "0w5HZDYmXiZG4mk3vpYef",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4140.583726231598,
			"y": 2350.7245044039464,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#1e1e1e",
			"width": 9.0024577934214,
			"height": 7.617464286740869,
			"seed": 1301181253,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 538,
			"versionNonce": 246354795,
			"isDeleted": false,
			"id": "4yh8-z0h1Hie5Mr69K4KH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 40,
			"angle": 0,
			"x": 3951.5200391694134,
			"y": 2348.3511146231012,
			"strokeColor": "#e03131",
			"backgroundColor": "#1e1e1e",
			"width": 206.36403249534214,
			"height": 90.75072156025362,
			"seed": 1793011147,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-43.754399294898704,
					-7.018854661110957
				],
				[
					-65.30507357447526,
					-22.134322331769113
				],
				[
					-79.67218976085994,
					-75.81005398630947
				],
				[
					-101.87591477618163,
					-90.75072156025362
				],
				[
					-123.42658905575819,
					-74.70333786972108
				],
				[
					-139.75285744937702,
					-22.687680390063313
				],
				[
					-163.9157346719329,
					-4.157424879244715
				],
				[
					-206.36403249534214,
					-0.6479975486897338
				]
			]
		},
		{
			"type": "line",
			"version": 586,
			"versionNonce": 1175350469,
			"isDeleted": false,
			"id": "DFu0mioIjSnNQEPeaDy02",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 4054.0095586637444,
			"y": 2348.685451172339,
			"strokeColor": "#e03131",
			"backgroundColor": "#1e1e1e",
			"width": 206.36403249534214,
			"height": 90.75072156025362,
			"seed": 1512845739,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-43.754399294898704,
					-7.018854661110957
				],
				[
					-65.30507357447526,
					-22.134322331769113
				],
				[
					-79.67218976085994,
					-75.81005398630947
				],
				[
					-101.87591477618163,
					-90.75072156025362
				],
				[
					-123.42658905575819,
					-74.70333786972108
				],
				[
					-139.75285744937702,
					-22.687680390063313
				],
				[
					-163.9157346719329,
					-4.157424879244715
				],
				[
					-206.36403249534214,
					-0.6479975486897338
				]
			]
		},
		{
			"type": "line",
			"version": 656,
			"versionNonce": 971992587,
			"isDeleted": false,
			"id": "XPS6SMtNGB2PGPC2aDJGq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 4151.651600884695,
			"y": 2347.992954418998,
			"strokeColor": "#e03131",
			"backgroundColor": "#1e1e1e",
			"width": 206.36403249534214,
			"height": 90.75072156025362,
			"seed": 1327948331,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-43.754399294898704,
					-7.018854661110957
				],
				[
					-65.30507357447526,
					-22.134322331769113
				],
				[
					-79.67218976085994,
					-75.81005398630947
				],
				[
					-101.87591477618163,
					-90.75072156025362
				],
				[
					-123.42658905575819,
					-74.70333786972108
				],
				[
					-139.75285744937702,
					-22.687680390063313
				],
				[
					-163.9157346719329,
					-4.157424879244715
				],
				[
					-206.36403249534214,
					-0.6479975486897338
				]
			]
		},
		{
			"type": "ellipse",
			"version": 41,
			"versionNonce": 831425573,
			"isDeleted": false,
			"id": "ERUrrVTbtE8jxIDfw11JL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 3746.934091828467,
			"y": 2340.920889254084,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 10.38745130010102,
			"height": 11.77244480678155,
			"seed": 1448491147,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 56,
			"versionNonce": 1569420459,
			"isDeleted": false,
			"id": "NP2Q6IEfF_ZGfLfC62uXx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 3846.9303329447066,
			"y": 2339.662901829861,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 10.38745130010102,
			"height": 11.77244480678155,
			"seed": 1980687717,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 29,
			"versionNonce": 714325893,
			"isDeleted": false,
			"id": "MLD_tvTIgNEsWJ9prhiIb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 3947.018810272704,
			"y": 2341.7403920898805,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 10.38745130010102,
			"height": 11.77244480678155,
			"seed": 1678151717,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501117,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 29,
			"versionNonce": 1227728715,
			"isDeleted": false,
			"id": "epPzY2_RR-f3vdcZvIegj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 4046.0458460003333,
			"y": 2341.7403920898805,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 10.38745130010102,
			"height": 11.77244480678155,
			"seed": 379751141,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 32,
			"versionNonce": 1734051557,
			"isDeleted": false,
			"id": "2Eu-p23QIAN-hZ2POiXN8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 50,
			"angle": 0,
			"x": 4146.457875234644,
			"y": 2343.1253855965606,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 10.38745130010102,
			"height": 11.77244480678155,
			"seed": 1292817829,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "Ut5d2YtEPCS59yDs8dsaD",
					"type": "arrow"
				},
				{
					"id": "J1B99OTdL--LOzuLWXXnU",
					"type": "arrow"
				},
				{
					"id": "IWys09TbJOMFX6ufzMqZy",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 238,
			"versionNonce": 1932559851,
			"isDeleted": false,
			"id": "heMf8AGy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3666.4628085806453,
			"y": 2396.101387227077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 577.0394287109375,
			"height": 250,
			"seed": 911612869,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ut5d2YtEPCS59yDs8dsaD",
					"type": "arrow"
				},
				{
					"id": "eCgUhLqzHjmMLSC7KBSoR",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Control points live in the space of the basis function\nand help define it.\n\nDepending on the degree of our spline we have a different\namount of control points\n\nk points\nk-1 intervals\nn degree\nk-1-n Control points",
			"rawText": "Control points live in the space of the basis function\nand help define it.\n\nDepending on the degree of our spline we have a different\namount of control points\n\nk points\nk-1 intervals\nn degree\nk-1-n Control points",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Control points live in the space of the basis function\nand help define it.\n\nDepending on the degree of our spline we have a different\namount of control points\n\nk points\nk-1 intervals\nn degree\nk-1-n Control points",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 81,
			"versionNonce": 2054382149,
			"isDeleted": false,
			"id": "Ut5d2YtEPCS59yDs8dsaD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4146.804123611315,
			"y": 2355.2440787800124,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 115.6469578077922,
			"height": 19.389909093521965,
			"seed": 2051762059,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "2Eu-p23QIAN-hZ2POiXN8",
				"focus": 1.3426675827122632,
				"gap": 2.2892975370516977
			},
			"endBinding": {
				"elementId": "heMf8AGy",
				"focus": 0.888088338476235,
				"gap": 27.00737338026329
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
					39.47231494038351,
					19.389909093521965
				],
				[
					115.6469578077922,
					13.849935066801208
				]
			]
		},
		{
			"type": "arrow",
			"version": 101,
			"versionNonce": 580817035,
			"isDeleted": false,
			"id": "eCgUhLqzHjmMLSC7KBSoR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3957.060013196134,
			"y": 2349.7041047532916,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 306.77606172965307,
			"height": 38.08732143370389,
			"seed": 785021957,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Qf3-i1mwmURajtHLqbWrg",
				"focus": -2.8006146445754854,
				"gap": 6.935924752290784
			},
			"endBinding": {
				"elementId": "heMf8AGy",
				"focus": 0.6841608999020854,
				"gap": 27.699870133603326
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
					160.65924677489738,
					38.08732143370389
				],
				[
					306.77606172965307,
					18.697412340181927
				]
			]
		},
		{
			"type": "text",
			"version": 77,
			"versionNonce": 1220071845,
			"isDeleted": false,
			"id": "4uchgi0v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4256.787226554045,
			"y": 2341.9691761798103,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 112.43223571777344,
			"height": 60,
			"seed": 441512267,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "2 Control\nPoints Per\nBasis function",
			"rawText": "2 Control\nPoints Per\nBasis function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2 Control\nPoints Per\nBasis function",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 367,
			"versionNonce": 1496467243,
			"isDeleted": false,
			"id": "J1B99OTdL--LOzuLWXXnU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4150.440456731517,
			"y": 2356.0920794074996,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 102.31567014082884,
			"height": 95.02755908173731,
			"seed": 999416011,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "2Eu-p23QIAN-hZ2POiXN8",
				"focus": 0.5241363667389967,
				"gap": 1.3196135361810244
			},
			"endBinding": {
				"elementId": "vRbek3Z9",
				"focus": 0.029777761990471448,
				"gap": 4.012965867506864
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
					57.99587792706461,
					-89.48758505501701
				],
				[
					102.31567014082884,
					-95.02755908173731
				]
			]
		},
		{
			"type": "text",
			"version": 97,
			"versionNonce": 1062819077,
			"isDeleted": false,
			"id": "vRbek3Z9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4256.769092739853,
			"y": 2222.284702138718,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 151.24832153320312,
			"height": 60,
			"seed": 1418972901,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "J1B99OTdL--LOzuLWXXnU",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Knots tie the\nfunction's different\nsegments together",
			"rawText": "Knots tie the\nfunction's different\nsegments together",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Knots tie the\nfunction's different\nsegments together",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 129,
			"versionNonce": 2102798795,
			"isDeleted": false,
			"id": "LmAvoXthvMl_Qph_8h-_C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2826.69145903152,
			"y": 2828.8886042288404,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 400.7086207859358,
			"height": 53.34314444693916,
			"seed": 676530699,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b01ea08c25d66c649c5f4692cc8b9d37ea266711",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 261,
			"versionNonce": 1238527077,
			"isDeleted": false,
			"id": "1zYAZEWW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2807.284825768622,
			"y": 3117.97360094609,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 438.65692138671875,
			"height": 60,
			"seed": 1907522661,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is a trad between Interpolation of the end points\nand continuity, the more points the closer it is to\nthe point and less continuous it is and vice versa ",
			"rawText": "This is a trad between Interpolation of the end points\nand continuity, the more points the closer it is to\nthe point and less continuous it is and vice versa ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is a trad between Interpolation of the end points\nand continuity, the more points the closer it is to\nthe point and less continuous it is and vice versa ",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 126,
			"versionNonce": 1143257195,
			"isDeleted": false,
			"id": "MV6T23AFIhsapd8Zl2m-i",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2726.565077481733,
			"y": 2650.7911497895993,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 183.85926067871787,
			"height": 109.2233231754758,
			"seed": 779354597,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "KoxD0J7NUsTrlWQfJe8GI",
				"focus": -0.6135740759810037,
				"gap": 18.92460173370182
			},
			"endBinding": {
				"elementId": "yv2f8N8bEnKWzk3w4TA_P",
				"focus": -0.47573045767543803,
				"gap": 15.618479203299785
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
					-86.46846418058522,
					-8.19174923816081
				],
				[
					-89.19904725997185,
					-97.39079649813266
				],
				[
					-183.85926067871787,
					-109.2233231754758
				]
			]
		},
		{
			"type": "text",
			"version": 182,
			"versionNonce": 133273541,
			"isDeleted": false,
			"id": "cn8Eo2it",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2210.73678960867,
			"y": 2466.9318891108815,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 414.5447998046875,
			"height": 40,
			"seed": 1021294533,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Which can be written with control points\ncalled de Boor points in order to describe the curve",
			"rawText": "Which can be written with control points\ncalled de Boor points in order to describe the curve",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which can be written with control points\ncalled de Boor points in order to describe the curve",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 121,
			"versionNonce": 1533571851,
			"isDeleted": false,
			"id": "yv2f8N8bEnKWzk3w4TA_P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2329.2446506442416,
			"y": 2514.308127683292,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"width": 197.84268695547348,
			"height": 71.81309069778004,
			"seed": 2056048587,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "MV6T23AFIhsapd8Zl2m-i",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ee1c1c78dc92d17803633bf673f965a956eb02c1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 47,
			"versionNonce": 1137989413,
			"isDeleted": false,
			"id": "D6BwhjWE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2241.8536159462315,
			"y": 2586.1212175565474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"width": 372.624755859375,
			"height": 40,
			"seed": 1283654277,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "the i-th de Boor point only has influence in the\nparameter interval of [ti, ti+1+n]",
			"rawText": "the i-th de Boor point only has influence in the\nparameter interval of [ti, ti+1+n]",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the i-th de Boor point only has influence in the\nparameter interval of [ti, ti+1+n]",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 949,
			"versionNonce": 1402722731,
			"isDeleted": false,
			"id": "KlBWQdSdDWy-GvzoouFR1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3250.9310337642596,
			"y": -1229.540750234058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 894.0165995621128,
			"height": 230.67811705690514,
			"seed": 1306881035,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					6.950367876293484,
					177.31234866828197
				],
				[
					691.5616036912343,
					135.85956416465058
				],
				[
					695.0367876293813,
					216.1743341404362
				],
				[
					894.0165995621128,
					98.55932203389807
				],
				[
					690.7109281789494,
					-14.503782916468936
				],
				[
					695.0367876293815,
					74.97578692493914
				],
				[
					0,
					0
				]
			]
		},
		{
			"id": "UMBqHzAk",
			"type": "text",
			"x": 3458.375569095105,
			"y": -1292.172528761674,
			"width": 297.3961181640625,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 188579365,
			"version": 155,
			"versionNonce": 669526661,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "What about 3D?",
			"rawText": "What about 3D?",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What about 3D?",
			"lineHeight": 1.25
		},
		{
			"id": "3NomcNbZ",
			"type": "text",
			"x": 3464.0567058872352,
			"y": -1245.929973293752,
			"width": 275.6196594238281,
			"height": 50,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 953104875,
			"version": 121,
			"versionNonce": 1240034379,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "(Read after getting a good\ngrasp on 2d)",
			"rawText": "(Read after getting a good\ngrasp on 2d)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(Read after getting a good\ngrasp on 2d)",
			"lineHeight": 1.25
		},
		{
			"id": "5K0x2NL2RiyYIu-W_ZaTf",
			"type": "image",
			"x": 5388.078796866263,
			"y": -2332.7549117602575,
			"width": 351.66321595280607,
			"height": 305.71726813987664,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1977207717,
			"version": 233,
			"versionNonce": 887788005,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f8644b730f93b1536978ae6a05cd9a5d96ec3d6b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "fXSjKSW4",
			"type": "text",
			"x": 5384.346896665573,
			"y": -2032.821941862362,
			"width": 366.192138671875,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 145042437,
			"version": 84,
			"versionNonce": 1378593515,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Parametric Surfaces",
			"rawText": "Parametric Surfaces",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Parametric Surfaces",
			"lineHeight": 1.25
		},
		{
			"id": "mAw1pQiw",
			"type": "text",
			"x": 5462.694066925687,
			"y": -1973.7333892431845,
			"width": 204.17977905273438,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1931131627,
			"version": 173,
			"versionNonce": 2011761989,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "oTowDXa_QlK9dCq9qs0Ii",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Mapping 2d intervals\n\n\nInto 3D coordinates",
			"rawText": "Mapping 2d intervals\n\n\nInto 3D coordinates",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Mapping 2d intervals\n\n\nInto 3D coordinates",
			"lineHeight": 1.25
		},
		{
			"id": "OBd4KwMGn_suCSmhzHVn9",
			"type": "image",
			"x": 5516.109458144143,
			"y": -1942.8327232221363,
			"width": 96.65116859383778,
			"height": 35.04311375916925,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 586936293,
			"version": 102,
			"versionNonce": 552408459,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "27d81010cce038f0d3deec61a2c228f84f75e8a9",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "nPqH9E5gdVUCRjYQYcY1j",
			"type": "image",
			"x": 5414.719912927196,
			"y": -1862.800390638708,
			"width": 299.43025867226777,
			"height": 30.698685826021144,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 389635557,
			"version": 163,
			"versionNonce": 4267173,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7de1906c842673977844b07a0ffccfb2a85ee143",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "h3A1swZx",
			"type": "text",
			"x": 5997.309452146912,
			"y": -1950.3715871812733,
			"width": 556.2794189453125,
			"height": 325,
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
			"seed": 1947986795,
			"version": 461,
			"versionNonce": 1969761323,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "oTowDXa_QlK9dCq9qs0Ii",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "An example for this would be the Unit sphere\n\n\n\n\n\n\n\n\n\nsuch that each 2d part of the overall surface (u,v)\ndefined its own parametric curve which can be seen when\nwe fix one of their values to a constant",
			"rawText": "An example for this would be the Unit sphere\n\n\n\n\n\n\n\n\n\nsuch that each 2d part of the overall surface (u,v)\ndefined its own parametric curve which can be seen when\nwe fix one of their values to a constant",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "An example for this would be the Unit sphere\n\n\n\n\n\n\n\n\n\nsuch that each 2d part of the overall surface (u,v)\ndefined its own parametric curve which can be seen when\nwe fix one of their values to a constant",
			"lineHeight": 1.25
		},
		{
			"id": "Ztr_1wbn9VHxt1uwDytKd",
			"type": "image",
			"x": 6200.329161763671,
			"y": -1923.155307885579,
			"width": 154.44824399320268,
			"height": 32.83181234586045,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 392544133,
			"version": 291,
			"versionNonce": 362823685,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f4fd33f0d902a7a109bbc14089df4d14f27031c2",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "2pJndFPhj0XtbaV5RCA1j",
			"type": "image",
			"x": 6084.959596989911,
			"y": -1888.1072166390309,
			"width": 395.46839620074707,
			"height": 35.41508025678332,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 226409029,
			"version": 395,
			"versionNonce": 1132949195,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cb28b693cd70c1347d9ac086a579cf9de11e5e50",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Y3kyEoAPMKO2vFAa9k1W3",
			"type": "image",
			"x": 6209.288908810573,
			"y": -1854.4119289216108,
			"width": 155.22625924277747,
			"height": 133.243349696835,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#e03131",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1881044677,
			"version": 286,
			"versionNonce": 772011877,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9575241c5f1323a06c53ec5bec974844714111be",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "lw4uEWBfjQgkVz-r_F9L_",
			"type": "image",
			"x": 6115.424176063549,
			"y": -1616.5136339786718,
			"width": 249.09099179879706,
			"height": 135.756628918166,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#868e96",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2016172043,
			"version": 389,
			"versionNonce": 501570923,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2d98be3d150c4587e78f5db6eed0d111979125b6",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "oTowDXa_QlK9dCq9qs0Ii",
			"type": "arrow",
			"x": 5683.028391677226,
			"y": -1907.1782035958815,
			"width": 567.2964913248315,
			"height": 118.6360159641165,
			"angle": 0,
			"strokeColor": "#4dabf7",
			"backgroundColor": "#868e96",
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
			"seed": 793153739,
			"version": 469,
			"versionNonce": 599376581,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					405.58099693339864,
					-118.6360159641165
				],
				[
					567.2964913248315,
					-55.496642778897694
				]
			],
			"lastCommittedPoint": [
				455.84918659390405,
				-10.006445559378335
			],
			"startBinding": {
				"elementId": "mAw1pQiw",
				"focus": 0.6403871906818785,
				"gap": 16.154545698804213
			},
			"endBinding": {
				"elementId": "h3A1swZx",
				"focus": 0.6086190816887039,
				"gap": 12.303259193505937
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "taBVJ-ogSpWTJixeP0Jod",
			"type": "line",
			"x": 5291.773502505188,
			"y": -1822.4728618000674,
			"width": 524.7824782251773,
			"height": 1.1118272843752948,
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
			"seed": 1240536645,
			"version": 107,
			"versionNonce": 1607235595,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					524.7824782251773,
					-1.1118272843752948
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "elZeqkH2",
			"type": "text",
			"x": 5494.064106849997,
			"y": -1813.9558466719382,
			"width": 139.69259643554688,
			"height": 35,
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
			"seed": 434028427,
			"version": 73,
			"versionNonce": 727654949,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Properties",
			"rawText": "Properties",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Properties",
			"lineHeight": 1.25
		},
		{
			"id": "5ecWrftq",
			"type": "text",
			"x": 5149.093448373635,
			"y": -1760.8099872969235,
			"width": 836.6990356445312,
			"height": 350,
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
			"seed": 602820235,
			"version": 1068,
			"versionNonce": 389496491,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "We previously talked about how we attempt to define smoothness in a curve\nsome necessary but no sufficient properties were:\n\n1) Continuously differentiable:\na surface is n-continuously differentiable if its mapping is continuously differentiable\n\n2) Regularity\nFor a surface to be regular, both its curve domains need to be regular themselves\nas a kink in the subcurve would result in an obvious kink in the surface.\nBut this is not enough so we look for a new way to define it.\nEach component curve generates tangent lines along its curve, for a surface to be\nregular, these tangent lines have to be linearly independent at all times!\n(If one of them vanishes, it technically is linear dependency with the other\nline therefore they cant vanish either)",
			"rawText": "We previously talked about how we attempt to define smoothness in a curve\nsome necessary but no sufficient properties were:\n\n1) Continuously differentiable:\na surface is n-continuously differentiable if its mapping is continuously differentiable\n\n2) Regularity\nFor a surface to be regular, both its curve domains need to be regular themselves\nas a kink in the subcurve would result in an obvious kink in the surface.\nBut this is not enough so we look for a new way to define it.\nEach component curve generates tangent lines along its curve, for a surface to be\nregular, these tangent lines have to be linearly independent at all times!\n(If one of them vanishes, it technically is linear dependency with the other\nline therefore they cant vanish either)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We previously talked about how we attempt to define smoothness in a curve\nsome necessary but no sufficient properties were:\n\n1) Continuously differentiable:\na surface is n-continuously differentiable if its mapping is continuously differentiable\n\n2) Regularity\nFor a surface to be regular, both its curve domains need to be regular themselves\nas a kink in the subcurve would result in an obvious kink in the surface.\nBut this is not enough so we look for a new way to define it.\nEach component curve generates tangent lines along its curve, for a surface to be\nregular, these tangent lines have to be linearly independent at all times!\n(If one of them vanishes, it technically is linear dependency with the other\nline therefore they cant vanish either)",
			"lineHeight": 1.25
		},
		{
			"id": "V2ymwdsmkztwIjV97p0qg",
			"type": "image",
			"x": 5220.911353586456,
			"y": -1400.3199931182298,
			"width": 273.15275341558936,
			"height": 51.619417968300354,
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
			"seed": 955102981,
			"version": 147,
			"versionNonce": 165778821,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ad0e346915cd4bea3b30b3f84eaae19adbf23223",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "uolHvTqyRy6nUzUWDKr-a",
			"type": "image",
			"x": 5633.756703258423,
			"y": -1400.319993546211,
			"width": 247.58717143433296,
			"height": 56.05747277758482,
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
			"seed": 432925413,
			"version": 177,
			"versionNonce": 785396043,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0e628a0503e697924c6e163f3f26f312f98a3b55",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "HC0K9i6dxVZdWYz0PNf_6",
			"type": "image",
			"x": 5426.537553352146,
			"y": -1339.518269042235,
			"width": 281.810826003084,
			"height": 205.58903931738635,
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
			"seed": 1981850437,
			"version": 139,
			"versionNonce": 176069861,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "TYg6PucuhvQl2lXgYfxZE",
					"type": "arrow"
				},
				{
					"id": "T5QboqcwaEPIRZRFSz_vi",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "860e20fbb566e07529ac9d0f86dba342bc5d67b6",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "TYg6PucuhvQl2lXgYfxZE",
			"type": "arrow",
			"x": 5494.311341497043,
			"y": -1261.0411930961632,
			"width": 76.13150039253105,
			"height": 53.65894907184406,
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
			"seed": 1728681611,
			"version": 162,
			"versionNonce": 1475465195,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-37.607126699925175,
					-47.23822012307619
				],
				[
					-76.13150039253105,
					-53.65894907184406
				]
			],
			"lastCommittedPoint": [
				-76.13150039253105,
				-53.65894907184406
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "MEVS1DxU",
				"focus": -0.6644216482068784,
				"gap": 13.161656519910139
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "MEVS1DxU",
			"type": "text",
			"x": 5299.257930678352,
			"y": -1323.2071060801804,
			"width": 105.76025390625,
			"height": 20,
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
			"seed": 1895817899,
			"version": 102,
			"versionNonce": 885241925,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "TYg6PucuhvQl2lXgYfxZE",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "First tangent",
			"rawText": "First tangent",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "First tangent",
			"lineHeight": 1.25
		},
		{
			"id": "T5QboqcwaEPIRZRFSz_vi",
			"type": "arrow",
			"x": 5549.8047845542515,
			"y": -1208.7581145133406,
			"width": 60.99692501329264,
			"height": 101.81441618760141,
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
			"seed": 1112164613,
			"version": 212,
			"versionNonce": 883333771,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-14.675951882897607,
					92.64194626079052
				],
				[
					46.32097313039503,
					101.81441618760141
				]
			],
			"lastCommittedPoint": [
				46.32097313039503,
				101.81441618760141
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "lYBQ4Ng6",
				"focus": -0.5462599443168991,
				"gap": 8.646775344389425
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "lYBQ4Ng6",
			"type": "text",
			"x": 5604.772533029036,
			"y": -1117.0334152452315,
			"width": 119.37625122070312,
			"height": 20,
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
			"seed": 846602891,
			"version": 95,
			"versionNonce": 1116628901,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "T5QboqcwaEPIRZRFSz_vi",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "second tangent",
			"rawText": "second tangent",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "second tangent",
			"lineHeight": 1.25
		},
		{
			"id": "Z30Y6F831z5GwHGr-34-O",
			"type": "arrow",
			"x": 5437.900651447158,
			"y": -1196.375280112146,
			"width": 64.20728948767646,
			"height": 17.42769286094085,
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
			"seed": 1377916747,
			"version": 111,
			"versionNonce": 1101599019,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-64.20728948767646,
					17.42769286094085
				]
			],
			"lastCommittedPoint": [
				-64.20728948767646,
				17.42769286094085
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "Vw5zWdG3",
			"type": "text",
			"x": 5242.056148377593,
			"y": -1190.4131746597188,
			"width": 144.03231811523438,
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
			"seed": 448541733,
			"version": 127,
			"versionNonce": 1443638021,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "uIa2G3I-ni4jicDsiM8Z3",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "plane defined\nby those tangents",
			"rawText": "plane defined\nby those tangents",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "plane defined\nby those tangents",
			"lineHeight": 1.25
		},
		{
			"id": "oXZ4ioLe",
			"type": "text",
			"x": 5227.763278986044,
			"y": -1080.1376012196663,
			"width": 679.359375,
			"height": 75,
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
			"seed": 1824349547,
			"version": 275,
			"versionNonce": 6534091,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "In other words, the tangent plane cannot vanish\n(Tangent planes are independent of parameterization! it is constant\nw.r.t a single point on a surface)",
			"rawText": "In other words, the tangent plane cannot vanish\n(Tangent planes are independent of parameterization! it is constant\nw.r.t a single point on a surface)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In other words, the tangent plane cannot vanish\n(Tangent planes are independent of parameterization! it is constant\nw.r.t a single point on a surface)",
			"lineHeight": 1.25
		},
		{
			"id": "uIa2G3I-ni4jicDsiM8Z3",
			"type": "arrow",
			"x": 5232.376183069653,
			"y": -1176.356290869635,
			"width": 157.3655303146761,
			"height": 1.0421558298985474,
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
			"seed": 97523525,
			"version": 235,
			"versionNonce": 1874494053,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-157.3655303146761,
					-1.0421558298985474
				]
			],
			"lastCommittedPoint": [
				-157.3655303146761,
				-1.0421558298985474
			],
			"startBinding": {
				"elementId": "Vw5zWdG3",
				"focus": 0.263813117839714,
				"gap": 9.67996530793971
			},
			"endBinding": {
				"elementId": "_y4xSxpfiOtIaY5aZ_Y4c",
				"focus": 0.09261010885598844,
				"gap": 12.724124552147714
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "eHpIYeDV",
			"type": "text",
			"x": 5125.823939800257,
			"y": -1218.042524065576,
			"width": 75.5399169921875,
			"height": 25,
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
			"seed": 718550091,
			"version": 80,
			"versionNonce": 1626407531,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "How so?",
			"rawText": "How so?",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How so?",
			"lineHeight": 1.25
		},
		{
			"id": "vymePnse",
			"type": "text",
			"x": 4788.889976965556,
			"y": -1244.0964198130384,
			"width": 213.73974609375,
			"height": 25,
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
			"seed": 1965818021,
			"version": 154,
			"versionNonce": 610725317,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "3d Cross product ofc",
			"rawText": "3d Cross product ofc",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3d Cross product ofc",
			"lineHeight": 1.25
		},
		{
			"id": "_y4xSxpfiOtIaY5aZ_Y4c",
			"type": "image",
			"x": 4717.76945769315,
			"y": -1211.5159749335066,
			"width": 344.5170705096797,
			"height": 60.01560669782984,
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
			"seed": 314388203,
			"version": 171,
			"versionNonce": 1813740811,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "uIa2G3I-ni4jicDsiM8Z3",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a15a420a15e689a2e4e10d5fcb20235810ef2397",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "V4kTbKBgFaclk0R--cq4e",
			"type": "arrow",
			"x": 4758.4358825431955,
			"y": -1160.5563012838024,
			"width": 45.6885638942631,
			"height": 67.7996857953226,
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
			"seed": 1289896709,
			"version": 229,
			"versionNonce": 321842469,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-4.809322515186068,
					48.09322515185568
				],
				[
					40.87924137907703,
					67.7996857953226
				]
			],
			"lastCommittedPoint": [
				40.87924137907703,
				54.50565517210316
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "WOaU0lFP",
				"focus": -0.6074647688833351,
				"gap": 9.299802009017185
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "WOaU0lFP",
			"type": "text",
			"x": 4808.61492593129,
			"y": -1129.1050274502818,
			"width": 282.78460693359375,
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
			"seed": 682633867,
			"version": 240,
			"versionNonce": 761111467,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "V4kTbKBgFaclk0R--cq4e",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Normal vector of the tangent plane\nand thus the normal to that point\n(its sign depends on the\nparameterization though)",
			"rawText": "Normal vector of the tangent plane\nand thus the normal to that point\n(its sign depends on the\nparameterization though)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Normal vector of the tangent plane\nand thus the normal to that point\n(its sign depends on the\nparameterization though)",
			"lineHeight": 1.25
		},
		{
			"id": "xH6ficCcVJkE6vsP2o1pe",
			"type": "line",
			"x": 5106.609632870181,
			"y": -981.5751205159922,
			"width": 921.6666666666661,
			"height": 6.6666666666667425,
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
			"seed": 1296857061,
			"version": 132,
			"versionNonce": 461373573,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					921.6666666666661,
					-6.6666666666667425
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "iH8hvAIc",
			"type": "text",
			"x": 5501.422210874576,
			"y": -964.6793061826589,
			"width": 126.64451599121094,
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
			"seed": 1879657317,
			"version": 73,
			"versionNonce": 1558312523,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Definition",
			"rawText": "Definition",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Definition",
			"lineHeight": 1.25
		},
		{
			"id": "uIlSsSHG",
			"type": "text",
			"x": 5242.953311329165,
			"y": -929.6793061826592,
			"width": 648.9793090820312,
			"height": 225,
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
			"seed": 687860837,
			"version": 319,
			"versionNonce": 1394059237,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Similarly to parametric curves we want to use the formulation of\ncontrol point * Basis function in 3d\n\n\n\n\n\nSo do we need to redefine all the Basis functions in 3d?\nNo we can use Tensor products of function spaces",
			"rawText": "Similarly to parametric curves we want to use the formulation of\ncontrol point * Basis function in 3d\n\n\n\n\n\nSo do we need to redefine all the Basis functions in 3d?\nNo we can use Tensor products of function spaces",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Similarly to parametric curves we want to use the formulation of\ncontrol point * Basis function in 3d\n\n\n\n\n\nSo do we need to redefine all the Basis functions in 3d?\nNo we can use Tensor products of function spaces",
			"lineHeight": 1.25
		},
		{
			"id": "BQjuNpemhhamCTR940aTq",
			"type": "image",
			"x": 5436.942965870181,
			"y": -872.7834926633105,
			"width": 261,
			"height": 103.65580448065172,
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
			"seed": 1580123429,
			"version": 176,
			"versionNonce": 1233319147,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dc6c361e912582a77d1f1b09e7ec15e6dc1c15a1",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "dNuPVRSQcoLM9hAJH_gVk",
			"type": "arrow",
			"x": 5829.759282933572,
			"y": -714.773131199227,
			"width": 737.8284834789401,
			"height": 506.43248040714025,
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
			"seed": 304362251,
			"version": 303,
			"versionNonce": 1006854981,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					506.43248040714116,
					-56.83410601763501
				],
				[
					517.5963226606045,
					-452.64305864045014
				],
				[
					737.8284834789401,
					-506.43248040714025
				]
			],
			"lastCommittedPoint": [
				737.8284834789401,
				-506.43248040714025
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "K1xFKWex",
			"type": "text",
			"x": 6616.865934651807,
			"y": -1255.8439357460757,
			"width": 259.0290832519531,
			"height": 70,
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
			"seed": 1186854693,
			"version": 119,
			"versionNonce": 46866315,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Tensor Products\nof Function spaces",
			"rawText": "Tensor Products\nof Function spaces",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Tensor Products\nof Function spaces",
			"lineHeight": 1.25
		},
		{
			"id": "4OJKKVp4",
			"type": "text",
			"x": 6401.866148451634,
			"y": -1162.7961024935737,
			"width": 690.0392456054688,
			"height": 325,
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
			"seed": 690797253,
			"version": 223,
			"versionNonce": 983610021,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Given the basis functions \n\n\nof two linear real univariate function spaces R1 and R2\nwith dimensions m+1 and n+1\n\n\nThe tensor product space R1xR2  is the linear subspace of bivariate\nreal functions spanned by the basis functions \n\n\n\nWhich has (m+1) * (n+1) dimensions",
			"rawText": "Given the basis functions \n\n\nof two linear real univariate function spaces R1 and R2\nwith dimensions m+1 and n+1\n\n\nThe tensor product space R1xR2  is the linear subspace of bivariate\nreal functions spanned by the basis functions \n\n\n\nWhich has (m+1) * (n+1) dimensions",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given the basis functions \n\n\nof two linear real univariate function spaces R1 and R2\nwith dimensions m+1 and n+1\n\n\nThe tensor product space R1xR2  is the linear subspace of bivariate\nreal functions spanned by the basis functions \n\n\n\nWhich has (m+1) * (n+1) dimensions",
			"lineHeight": 1.25
		},
		{
			"id": "p9FwAA36WJ66L9F8n6RKS",
			"type": "image",
			"x": 6468.633419516069,
			"y": -1128.8175225438524,
			"width": 555.4941122339959,
			"height": 35.62789699061763,
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
			"seed": 445887045,
			"version": 165,
			"versionNonce": 1123350059,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "133b8f571062ba985f1fe7df4ce5f8affa26a8ee",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "yf1DdXdgtdkiH2ST-p7aJ",
			"type": "image",
			"x": 6409.910140951593,
			"y": -926.0078833599841,
			"width": 672.9406702178476,
			"height": 48.951862951867966,
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
			"seed": 1700488875,
			"version": 159,
			"versionNonce": 1268585989,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "67af7863c29a3caec28f7c4ef45711f6b8cbcd70",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "fUsz8uk0nML0-YJLZ8_WS",
			"type": "image",
			"x": 5357.423816873601,
			"y": -687.5761009566577,
			"width": 420.03829786319295,
			"height": 77.80738368522243,
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
			"seed": 485381669,
			"version": 162,
			"versionNonce": 418052299,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e03708358f627113a4816ace6d4964a4c0e868fa",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "uoLEwAUn",
			"type": "text",
			"x": 5198.223300220543,
			"y": -603.9476070253809,
			"width": 738.4393310546875,
			"height": 100,
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
			"seed": 379480805,
			"version": 325,
			"versionNonce": 2046168421,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "This parameterization has its limitations though, due to the nature of cij\nThe control points lie on a grid-like structure, they can be moved around\nbut they still remain in grid-like structure\nWe can write the following in Matrix notation",
			"rawText": "This parameterization has its limitations though, due to the nature of cij\nThe control points lie on a grid-like structure, they can be moved around\nbut they still remain in grid-like structure\nWe can write the following in Matrix notation",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This parameterization has its limitations though, due to the nature of cij\nThe control points lie on a grid-like structure, they can be moved around\nbut they still remain in grid-like structure\nWe can write the following in Matrix notation",
			"lineHeight": 1.25
		},
		{
			"id": "NaGH7Zf778ks_BHcDc_1P",
			"type": "image",
			"x": 5291.433694317206,
			"y": -503.94760760244867,
			"width": 552.0185427741708,
			"height": 125.36093612707776,
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
			"seed": 1746749547,
			"version": 144,
			"versionNonce": 1380427627,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "60cfd2f1fb408b0a0ee940f5bbc7b7e808e3b9fa",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "0vO-z4S5CHXYkfAeOaCYL",
			"type": "arrow",
			"x": 5582.813465029878,
			"y": -331.32753871164294,
			"width": 0,
			"height": 213.97584904745753,
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
			"seed": 1778511173,
			"version": 52,
			"versionNonce": 351869125,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					213.97584904745753
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "LkeQn1KH",
				"focus": -0.03209541715765479,
				"gap": 14.24604461167479
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "LkeQn1KH",
			"type": "text",
			"x": 5511.08951417586,
			"y": -103.10564505251062,
			"width": 148.20458984375,
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
			"seed": 311667243,
			"version": 51,
			"versionNonce": 626360843,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "0vO-z4S5CHXYkfAeOaCYL",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Polynomials",
			"rawText": "Polynomials",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Polynomials",
			"lineHeight": 1.25
		},
		{
			"id": "LMqZUKnY",
			"type": "text",
			"x": 5204.423931485627,
			"y": -62.24216132923232,
			"width": 754.5591430664062,
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
			"seed": 793283915,
			"version": 285,
			"versionNonce": 641972261,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "We can choose polynomials for our univariate basis functions and use\nthe Tensor products to make a multivariate polynomial function\n\n\n\n\n\nfor example a quadratic univariate basis function would result in this basis",
			"rawText": "We can choose polynomials for our univariate basis functions and use\nthe Tensor products to make a multivariate polynomial function\n\n\n\n\n\nfor example a quadratic univariate basis function would result in this basis",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can choose polynomials for our univariate basis functions and use\nthe Tensor products to make a multivariate polynomial function\n\n\n\n\n\nfor example a quadratic univariate basis function would result in this basis",
			"lineHeight": 1.25
		},
		{
			"id": "ArD2OiDxKYiWUo7S8GS0J",
			"type": "image",
			"x": 5456.428111900448,
			"y": -7.041625714962642,
			"width": 252.77070542038575,
			"height": 36.35353965596559,
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
			"seed": 2103212389,
			"version": 165,
			"versionNonce": 453970091,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "56e222b9f871e806cd159f3cbdb6634c376a7a53",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "NCcoPHK13LP1OqQUna8oC",
			"type": "image",
			"x": 5462.695759553751,
			"y": 42.867367996764216,
			"width": 240.2354106071357,
			"height": 49.099208007297804,
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
			"seed": 1495675269,
			"version": 144,
			"versionNonce": 667118469,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "99b922a2f75f96015c6b98b6e846e929d57cd840",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "gCBjUGsJEEf1uyS1K7sbk",
			"type": "image",
			"x": 5394.19393464418,
			"y": 150.41632746350183,
			"width": 375.0191369396359,
			"height": 42.454996634675766,
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
			"seed": 817779979,
			"version": 99,
			"versionNonce": 958315339,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "88dc1661372a46ea7749cb05565fb996f47669a7",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "uV2Ndjy7b2_BpmNcB2ZjD",
			"type": "arrow",
			"x": 5582.447092204383,
			"y": -331.8253794390918,
			"width": 790.2291227834185,
			"height": 281.09783677958256,
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
			"seed": 2088536299,
			"version": 357,
			"versionNonce": 2041950949,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-96.08956665424557,
					143.41726366305244
				],
				[
					-708.4812824954788,
					164.92985321251007
				],
				[
					-790.2291227834185,
					281.09783677958256
				]
			],
			"lastCommittedPoint": [
				-811.741712332876,
				281.09783677958256
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "RbcHbhOz",
				"focus": -0.2353944033207426,
				"gap": 6.672547058446298
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "RbcHbhOz",
			"type": "text",
			"x": 4731.231393985209,
			"y": -44.054995601062956,
			"width": 122.61250305175781,
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
			"seed": 195632709,
			"version": 24,
			"versionNonce": 1809783275,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "uV2Ndjy7b2_BpmNcB2ZjD",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Lagrange",
			"rawText": "Lagrange",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lagrange",
			"lineHeight": 1.25
		},
		{
			"id": "fEYCi5Cx",
			"type": "text",
			"x": 4552.975917341646,
			"y": 1.6088938871513392,
			"width": 488.0394287109375,
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
			"seed": 1159713285,
			"version": 190,
			"versionNonce": 413666885,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Given control points pij and parameter values u,v\nwe need to interpolate the curve such that\n\n\n\nand the desired surface is simply given by",
			"rawText": "Given control points pij and parameter values u,v\nwe need to interpolate the curve such that\n\n\n\nand the desired surface is simply given by",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given control points pij and parameter values u,v\nwe need to interpolate the curve such that\n\n\n\nand the desired surface is simply given by",
			"lineHeight": 1.25
		},
		{
			"id": "63CgYvTu6fgXvkQclo3Vx",
			"type": "image",
			"x": 4705.4007828248505,
			"y": 62.27278358140518,
			"width": 173.63437297727634,
			"height": 40.7509242701771,
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
			"seed": 1189298821,
			"version": 48,
			"versionNonce": 811246731,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "51633ffc1e5aebfb86adf0645bf68220421c581d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "WfcL0XttjVsUaJxmgGuLE",
			"type": "image",
			"x": 4641.461005999304,
			"y": 171.64382558326793,
			"width": 301.5139259144692,
			"height": 61.98524174453112,
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
			"seed": 380419621,
			"version": 75,
			"versionNonce": 326630821,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "78bb1d2affc61c00948d7c215371908d949e3762",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "yrX1-pMfI7ueV3cDE2zQb",
			"type": "arrow",
			"x": 5581.536671077665,
			"y": -335.8515478470689,
			"width": 832.7272727272739,
			"height": 241.81818181818187,
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
			"seed": 131848005,
			"version": 223,
			"versionNonce": 2118900523,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					103.63636363636397,
					145.4545454545455
				],
				[
					747.2727272727279,
					156.36363636363637
				],
				[
					832.7272727272739,
					241.81818181818187
				]
			],
			"lastCommittedPoint": [
				832.7272727272739,
				241.81818181818187
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "aFgKAOWY",
			"type": "text",
			"x": 6371.675763910006,
			"y": -85.72754337189676,
			"width": 85.17636108398438,
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
			"seed": 256936773,
			"version": 28,
			"versionNonce": 1095958789,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Bezier",
			"rawText": "Bezier",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bezier",
			"lineHeight": 1.25
		},
		{
			"id": "DOHkWiM4",
			"type": "text",
			"x": 6083.734311118933,
			"y": -32.04162554836737,
			"width": 661.0592651367188,
			"height": 650,
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
			"seed": 134932747,
			"version": 431,
			"versionNonce": 1914518987,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "We use Bernstein polynomials over [0,1] as polynomial basis \n\n\n\n\nand the control points turn into a control mesh!\nThe parameter curves (one variable is constant and the other\nis changing) are Bezier curves of their own\n\n\n\n\n\n\n\n\nBezier surfaces still have the Bezier properties:\n\n1) Partition of Unity\n\n\n2) Non-negativity\n\n\n3) The surface is inside the convex hull\n4) all 4 points at the corners of the control net are interpolated",
			"rawText": "We use Bernstein polynomials over [0,1] as polynomial basis \n\n\n\n\nand the control points turn into a control mesh!\nThe parameter curves (one variable is constant and the other\nis changing) are Bezier curves of their own\n\n\n\n\n\n\n\n\nBezier surfaces still have the Bezier properties:\n\n1) Partition of Unity\n\n\n2) Non-negativity\n\n\n3) The surface is inside the convex hull\n4) all 4 points at the corners of the control net are interpolated",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We use Bernstein polynomials over [0,1] as polynomial basis \n\n\n\n\nand the control points turn into a control mesh!\nThe parameter curves (one variable is constant and the other\nis changing) are Bezier curves of their own\n\n\n\n\n\n\n\n\nBezier surfaces still have the Bezier properties:\n\n1) Partition of Unity\n\n\n2) Non-negativity\n\n\n3) The surface is inside the convex hull\n4) all 4 points at the corners of the control net are interpolated",
			"lineHeight": 1.25
		},
		{
			"id": "v82ocwv6UrGtxo4sidnA_",
			"type": "image",
			"x": 6216.0496586676845,
			"y": -2.806944593055036,
			"width": 396.42857142857173,
			"height": 81.12956810631235,
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
			"seed": 1692569899,
			"version": 83,
			"versionNonce": 934713445,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7cc8974534cb0e253ec0c6b749c8791ad8364bcb",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "Ogo8mdpZuZxBy-GyTwqG2",
			"type": "image",
			"x": 6090.729320815234,
			"y": 171.64382618748314,
			"width": 647.0692462074185,
			"height": 88.76963774545258,
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
			"seed": 1168675493,
			"version": 157,
			"versionNonce": 921259115,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "GEo3XtTHmAbwEEPS-SxTl",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2a743352c26e52c14124754fb8326b722921251b",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "ZFDP6xN3jobmk0xkKmVZz",
			"type": "arrow",
			"x": 6625.016351920827,
			"y": 236.71775969574543,
			"width": 118.78539825746611,
			"height": 70.92735782665574,
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
			"seed": 1136016517,
			"version": 75,
			"versionNonce": 7357381,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.9625584197092394,
					59.67862202199075
				],
				[
					-118.78539825746611,
					70.92735782665574
				]
			],
			"lastCommittedPoint": [
				-129.94538666078643,
				71.71060226835988
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "g6dGF4H5",
				"focus": 0.3757210432313133,
				"gap": 10.912421772902235
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "g6dGF4H5",
			"type": "text",
			"x": 6335.038700957842,
			"y": 279.0703301629647,
			"width": 160.2798309326172,
			"height": 50,
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
			"seed": 512255819,
			"version": 52,
			"versionNonce": 813336331,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "ZFDP6xN3jobmk0xkKmVZz",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "new transformed\ncontrol points",
			"rawText": "new transformed\ncontrol points",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "new transformed\ncontrol points",
			"lineHeight": 1.25
		},
		{
			"id": "A2BAmWR3DmppqTSUFzbnl",
			"type": "image",
			"x": 6329.969968115453,
			"y": 444.32208796664656,
			"width": 170.41729547647995,
			"height": 46.10487953772503,
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
			"seed": 1994845733,
			"version": 138,
			"versionNonce": 261980965,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "722952b95e8e50ed794c7c934087e2faaf97c4d6",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "cvW3uRvHSIG9um0KZsdEQ",
			"type": "image",
			"x": 6329.4251689147995,
			"y": 523.5096342419769,
			"width": 169.6775503616917,
			"height": 37.53928105347162,
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
			"seed": 526593701,
			"version": 81,
			"versionNonce": 1699442091,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cc8b0f5d67acc0678f8be5cf3df584a13ddce52c",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "GEo3XtTHmAbwEEPS-SxTl",
			"type": "arrow",
			"x": 6189.729106621728,
			"y": 276.8733892907278,
			"width": 605.3981722436147,
			"height": 206.7476915144648,
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
			"seed": 1574434661,
			"version": 301,
			"versionNonce": 2041304709,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-150,
					81.66666666666674
				],
				[
					-551.309082932803,
					73.7807172202663
				],
				[
					-605.3981722436147,
					206.7476915144648
				]
			],
			"lastCommittedPoint": [
				-646.666666666667,
				255
			],
			"startBinding": {
				"elementId": "Ogo8mdpZuZxBy-GyTwqG2",
				"focus": 0.27842741411046007,
				"gap": 16.459925357792073
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "kwdm904F",
			"type": "text",
			"x": 5604.250905995007,
			"y": 362.2036708882057,
			"width": 364.68658447265625,
			"height": 76.1855197196665,
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
			"seed": 1000840485,
			"version": 436,
			"versionNonce": 679903307,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Does De Casteljau algorithm still work\nin 3d?\nFuck yeah, except we have to do an extra step\nin the other parameter's direction",
			"rawText": "Does De Casteljau algorithm still work\nin 3d?\nFuck yeah, except we have to do an extra step\nin the other parameter's direction",
			"fontSize": 15.237103943933299,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Does De Casteljau algorithm still work\nin 3d?\nFuck yeah, except we have to do an extra step\nin the other parameter's direction",
			"lineHeight": 1.25
		},
		{
			"id": "xaxgofS1",
			"type": "text",
			"x": 5493.443065667576,
			"y": 503.72224977073824,
			"width": 185.332763671875,
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
			"seed": 448969099,
			"version": 79,
			"versionNonce": 1767423461,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "De Casteljau",
			"rawText": "De Casteljau",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "De Casteljau",
			"lineHeight": 1.25
		},
		{
			"id": "Iivkyo2T",
			"type": "text",
			"x": 5279.739788131319,
			"y": 558.8234192685217,
			"width": 612.7393188476562,
			"height": 125,
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
			"seed": 769049419,
			"version": 259,
			"versionNonce": 67518187,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "1) Apply de casteljau algorithm in one direction alongside\nall parallel line on the grid of control points\n\n2) take all the end points from each parallel line in that grid\nand perform de casteljau on it",
			"rawText": "1) Apply de casteljau algorithm in one direction alongside\nall parallel line on the grid of control points\n\n2) take all the end points from each parallel line in that grid\nand perform de casteljau on it",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Apply de casteljau algorithm in one direction alongside\nall parallel line on the grid of control points\n\n2) take all the end points from each parallel line in that grid\nand perform de casteljau on it",
			"lineHeight": 1.25
		},
		{
			"id": "ou8Y5NzF",
			"type": "text",
			"x": 5138.033977408662,
			"y": 703.9245878010807,
			"width": 887.3390502929688,
			"height": 100,
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
			"seed": 1738528165,
			"version": 304,
			"versionNonce": 1437710661,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "But how do we pick the direction?\nThe results are the same, but the efficient is different!\nPick the direction with the shortest interval distance, that way you do many evaluations\non a short distance and then few evaluations on long distance!",
			"rawText": "But how do we pick the direction?\nThe results are the same, but the efficient is different!\nPick the direction with the shortest interval distance, that way you do many evaluations\non a short distance and then few evaluations on long distance!",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But how do we pick the direction?\nThe results are the same, but the efficient is different!\nPick the direction with the shortest interval distance, that way you do many evaluations\non a short distance and then few evaluations on long distance!",
			"lineHeight": 1.25
		},
		{
			"id": "LK5nzGr5mItoMxTdetZDN",
			"type": "arrow",
			"x": 5987.988442603164,
			"y": -566.3243443232552,
			"width": 1383.6111427921824,
			"height": 0.6074272878533975,
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
			"seed": 1985689573,
			"version": 136,
			"versionNonce": 1649748363,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1383.6111427921824,
					-0.6074272878533975
				]
			],
			"lastCommittedPoint": [
				1030.8838700649094,
				-2.4256091060351537
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "DcmA6viE",
			"type": "text",
			"x": 6334.881700139111,
			"y": -600.3112436897111,
			"width": 715.2791748046875,
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
			"seed": 2120337061,
			"version": 172,
			"versionNonce": 2014595237,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "i hate limitations, this is so not realistic omg give me something else pls",
			"rawText": "i hate limitations, this is so not realistic omg give me something else pls",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "i hate limitations, this is so not realistic omg give me something else pls",
			"lineHeight": 1.25
		},
		{
			"id": "NlJowQFk",
			"type": "text",
			"x": 7501.205123137025,
			"y": -648.1103099920348,
			"width": 366.192138671875,
			"height": 135,
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
			"seed": 920295685,
			"version": 209,
			"versionNonce": 2024652843,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Parametric Surfaces\nof\nIrregular Data",
			"rawText": "Parametric Surfaces\nof\nIrregular Data",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Parametric Surfaces\nof\nIrregular Data",
			"lineHeight": 1.25
		},
		{
			"id": "SK3ofbrk",
			"type": "text",
			"x": 7291.931150852801,
			"y": -452.1936433253685,
			"width": 746.359130859375,
			"height": 75,
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
			"seed": 1796525733,
			"version": 329,
			"versionNonce": 36563973,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Maybe we can try modelling parametric surfaces as height frields.\nWhat this means is that the parameters u and v are already and x and y\ncoordinates, but we try to model the height z",
			"rawText": "Maybe we can try modelling parametric surfaces as height frields.\nWhat this means is that the parameters u and v are already and x and y\ncoordinates, but we try to model the height z",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Maybe we can try modelling parametric surfaces as height frields.\nWhat this means is that the parameters u and v are already and x and y\ncoordinates, but we try to model the height z",
			"lineHeight": 1.25
		},
		{
			"id": "JeH3ly5YqqxI6RtHpiVUY",
			"type": "image",
			"x": 7528.301191838044,
			"y": -369.1380877698133,
			"width": 312,
			"height": 104,
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
			"seed": 1204322283,
			"version": 211,
			"versionNonce": 1895465675,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "KJ-maOe05KFSmTjJKAy2N",
					"type": "arrow"
				},
				{
					"id": "tJ9xkKRICUkTM7mpaee3B",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7ff0c2a264427fed4b2fb2d414ca1650ebbb3672",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "KJ-maOe05KFSmTjJKAy2N",
			"type": "arrow",
			"x": 7677.904898338039,
			"y": -249.64614996905198,
			"width": 519.0355154727004,
			"height": 278.4987317163036,
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
			"seed": 221953451,
			"version": 540,
			"versionNonce": 335291237,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-65.95714064207459,
					159.36973035877566
				],
				[
					-474.869510823748,
					159.5741725696042
				],
				[
					-519.0355154727004,
					278.4987317163036
				]
			],
			"lastCommittedPoint": [
				-381.33333333333303,
				320
			],
			"startBinding": {
				"elementId": "JeH3ly5YqqxI6RtHpiVUY",
				"focus": -0.12131579521036849,
				"gap": 15.49193780076132
			},
			"endBinding": {
				"elementId": "Hfplp5h5",
				"focus": -0.2516077630842701,
				"gap": 11.875271473488965
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "Hfplp5h5",
			"type": "text",
			"x": 7037.716171809603,
			"y": 40.7278532207406,
			"width": 298.9851989746094,
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
			"seed": 1752939429,
			"version": 99,
			"versionNonce": 1406529899,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "KJ-maOe05KFSmTjJKAy2N",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Radial Basis Function",
			"rawText": "Radial Basis Function",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Radial Basis Function",
			"lineHeight": 1.25
		},
		{
			"id": "cvXjdBrp",
			"type": "text",
			"x": 7618.21116382968,
			"y": -78.48267309504894,
			"width": 119.1405029296875,
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
			"seed": 1766693061,
			"version": 12,
			"versionNonce": 1909223109,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "examples",
			"rawText": "examples",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "examples",
			"lineHeight": 1.25
		},
		{
			"id": "q2DkrnTN",
			"type": "text",
			"x": 6869.979095822114,
			"y": 75.72785347278041,
			"width": 634.4593505859375,
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
			"seed": 1147780843,
			"version": 118,
			"versionNonce": 847940619,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "RBFs are independent of the dimension of the parameter values",
			"rawText": "RBFs are independent of the dimension of the parameter values",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "RBFs are independent of the dimension of the parameter values",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 605,
			"versionNonce": 2050772517,
			"isDeleted": false,
			"id": "tJ9xkKRICUkTM7mpaee3B",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7680.774616678905,
			"y": -249.72384616383852,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 519.0355154727004,
			"height": 278.4987317163036,
			"seed": 202527813,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JeH3ly5YqqxI6RtHpiVUY",
				"focus": 0.17703157950453752,
				"gap": 15.41424160597478
			},
			"endBinding": {
				"elementId": "RmDvQ4Nu",
				"focus": 0.06150908278252078,
				"gap": 8.047506023759638
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
					65.95714064207459,
					159.36973035877566
				],
				[
					474.869510823748,
					159.5741725696042
				],
				[
					519.0355154727004,
					278.4987317163036
				]
			]
		},
		{
			"id": "7Ei1KQhRT9z0I83S3q81M",
			"type": "image",
			"x": 7008.984719033316,
			"y": 107.23083445110441,
			"width": 292.7365550561899,
			"height": 108.79781056901176,
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
			"seed": 1402326635,
			"version": 53,
			"versionNonce": 286446251,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "baffbd8054c8c98e4fc47fb9fe4c5aeb6c711db4",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "xBQbRJUY",
			"type": "text",
			"x": 6993.047319206057,
			"y": 222.30514299817975,
			"width": 323.1366882324219,
			"height": 40,
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
			"seed": 186114763,
			"version": 81,
			"versionNonce": 1547256197,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Weighted sum of radial functions one for\neach point",
			"rawText": "Weighted sum of radial functions one for\neach point",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Weighted sum of radial functions one for\neach point",
			"lineHeight": 1.25
		},
		{
			"id": "ft0qnsfc",
			"type": "text",
			"x": 6951.353241322606,
			"y": 272.18143892623556,
			"width": 407.99951171875,
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
			"seed": 1369991275,
			"version": 66,
			"versionNonce": 270091595,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Distance is computed in parameter space",
			"rawText": "Distance is computed in parameter space",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Distance is computed in parameter space",
			"lineHeight": 1.25
		},
		{
			"id": "6UddchF9kFqy7KU_KVNU3",
			"type": "image",
			"x": 7087.550413181981,
			"y": 307.6451175330084,
			"width": 134.13049918465552,
			"height": 32.92734276013204,
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
			"seed": 573916235,
			"version": 58,
			"versionNonce": 218155237,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "818d60d5f592c896250c82be48fc7185bed23feb",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "RmDvQ4Nu",
			"type": "text",
			"x": 8045.930364498419,
			"y": 36.82239157622473,
			"width": 307.0492858886719,
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
			"seed": 232437867,
			"version": 56,
			"versionNonce": 1459119083,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "tJ9xkKRICUkTM7mpaee3B",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Least Squared Fitting",
			"rawText": "Least Squared Fitting",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Least Squared Fitting",
			"lineHeight": 1.25
		},
		{
			"id": "E4o7ODbR",
			"type": "text",
			"x": 7758.070801155878,
			"y": 85.00843584445784,
			"width": 917.259033203125,
			"height": 550,
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
			"seed": 1710468587,
			"version": 338,
			"versionNonce": 2116052037,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "Like before we try to Minimize the sum of squared residuals for a fixed class of functions \n\n\n\n\nsuch that we find the mesh polynomial that makes the least mistakes when it comes to\nthe points\nfor example using a quadratic Polynomial\n\n\n\nWhich we can represent as a linear system of equations\n\n\n\n\n\n\n\n\n\nResulting in the following",
			"rawText": "Like before we try to Minimize the sum of squared residuals for a fixed class of functions \n\n\n\n\nsuch that we find the mesh polynomial that makes the least mistakes when it comes to\nthe points\nfor example using a quadratic Polynomial\n\n\n\nWhich we can represent as a linear system of equations\n\n\n\n\n\n\n\n\n\nResulting in the following",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Like before we try to Minimize the sum of squared residuals for a fixed class of functions \n\n\n\n\nsuch that we find the mesh polynomial that makes the least mistakes when it comes to\nthe points\nfor example using a quadratic Polynomial\n\n\n\nWhich we can represent as a linear system of equations\n\n\n\n\n\n\n\n\n\nResulting in the following",
			"lineHeight": 1.25
		},
		{
			"id": "EAG4WPdXEqTycGDN-rirR",
			"type": "image",
			"x": 8052.876982655045,
			"y": 116.98814054317188,
			"width": 314.09678352896515,
			"height": 89.64707352306615,
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
			"seed": 1992349163,
			"version": 63,
			"versionNonce": 1035644555,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f7fd5e6b9125c966d8509897a9215bcb97032cd0",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "TYqD33ZKdht8qsqFKNS1P",
			"type": "image",
			"x": 7812.263742469317,
			"y": 287.9181676021383,
			"width": 815.0919309326986,
			"height": 40.97187162342583,
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
			"seed": 716759461,
			"version": 227,
			"versionNonce": 326472613,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bbb7c4aad8d733fe0437932289624c167d32518d",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "vTc0HknZEZhiH4Q9JsMdt",
			"type": "image",
			"x": 8014.68478281292,
			"y": 398.1944804500735,
			"width": 425.00892638298694,
			"height": 42.08009172108782,
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
			"seed": 408607851,
			"version": 129,
			"versionNonce": 924493099,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a8919df9e561344551c5f338aa454211cdbcb1cb",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "m9z0Mq_3IIiPw7LyeyBqX",
			"type": "image",
			"x": 7933.632344291793,
			"y": 440.2745724520618,
			"width": 552.5860593545015,
			"height": 160.00514060423066,
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
			"seed": 897195755,
			"version": 124,
			"versionNonce": 1496176389,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f9e859db0079a1a510eec317f28cb6acd0a4ce81",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "uoUOg1xiDK3QkoZJILPPn",
			"type": "image",
			"x": 7967.823609527902,
			"y": 647.0548800810732,
			"width": 533.9737628740824,
			"height": 167.07495075374095,
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
			"seed": 337170443,
			"version": 94,
			"versionNonce": 2055391179,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d97a5bc59d1fa1cdd2ec8913b5d30c2c640d7037",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "XN4meIyp",
			"type": "text",
			"x": 7775.644551741041,
			"y": 846.6560861034199,
			"width": 877.859130859375,
			"height": 100,
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
			"seed": 1640088613,
			"version": 438,
			"versionNonce": 2043063909,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "XnwKTUy4w1dBcXVa7gdnN",
					"type": "arrow"
				}
			],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "But you quickly notice a big issue when it comes to this approach\nwe try to find the best basis function that describes these evaluations\nbut then we lose all local control, because any error in one end of the parametric curve\nwill influence the solution in all the others.",
			"rawText": "But you quickly notice a big issue when it comes to this approach\nwe try to find the best basis function that describes these evaluations\nbut then we lose all local control, because any error in one end of the parametric curve\nwill influence the solution in all the others.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "But you quickly notice a big issue when it comes to this approach\nwe try to find the best basis function that describes these evaluations\nbut then we lose all local control, because any error in one end of the parametric curve\nwill influence the solution in all the others.",
			"lineHeight": 1.25
		},
		{
			"id": "XnwKTUy4w1dBcXVa7gdnN",
			"type": "arrow",
			"x": 8229.632765020757,
			"y": 959.5423499133257,
			"width": 2.237818323979809,
			"height": 154.4094643545592,
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
			"seed": 1289545355,
			"version": 60,
			"versionNonce": 1846384235,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					2.237818323979809,
					154.4094643545592
				]
			],
			"lastCommittedPoint": [
				2.237818323979809,
				154.4094643545592
			],
			"startBinding": {
				"elementId": "XN4meIyp",
				"focus": -0.03217813595832088,
				"gap": 12.886263809905813
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"type": "text",
			"version": 92,
			"versionNonce": 1947048389,
			"isDeleted": false,
			"id": "oM2dnDM8",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8014.951465023207,
			"y": 1133.3758166135403,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 438.3138732910156,
			"height": 35,
			"seed": 20001701,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Weighted Least Squared Fitting",
			"rawText": "Weighted Least Squared Fitting",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Weighted Least Squared Fitting",
			"lineHeight": 1.25
		},
		{
			"id": "7VpCleDo",
			"type": "text",
			"x": 7780.691254083891,
			"y": 1178.8485456632793,
			"width": 922.4990234375,
			"height": 225,
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
			"seed": 1507980709,
			"version": 421,
			"versionNonce": 998949227,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542583419,
			"link": null,
			"locked": false,
			"text": "Idea:\nhow about we introduce weight to the equation such that we\nonly care about the nearby points to influence our current result\n\nHow do we choose our weighing function?\nThe surface is n-times continuously differentiable if and only if the weighting function is too.\nthus we need a smooth weighing function.\nalso we want something that gradually goes down the further you are away\nbut also goes to zero after a certain distance",
			"rawText": "Idea:\nhow about we introduce weight to the equation such that we\nonly care about the nearby points to influence our current result\n\nHow do we choose our weighing function?\nThe surface is n-times continuously differentiable if and only if the weighting function is too.\nthus we need a smooth weighing function.\nalso we want something that gradually goes down the further you are away\nbut also goes to zero after a certain distance",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea:\nhow about we introduce weight to the equation such that we\nonly care about the nearby points to influence our current result\n\nHow do we choose our weighing function?\nThe surface is n-times continuously differentiable if and only if the weighting function is too.\nthus we need a smooth weighing function.\nalso we want something that gradually goes down the further you are away\nbut also goes to zero after a certain distance",
			"lineHeight": 1.25
		},
		{
			"id": "Xt0V7zvlwvqo4Fnv829w7",
			"type": "image",
			"x": 7837.8268759214325,
			"y": 1451.1126054368028,
			"width": 145.38298348360308,
			"height": 54.21060401083505,
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
			"seed": 646685131,
			"version": 87,
			"versionNonce": 403713515,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "5dMyWaDAesFKIzFdpcele",
					"type": "arrow"
				}
			],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7c5f5f52983d266fad9a971b71692d73e4d01b7a",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "oHLs3zhWaCyvrdccTT3-X",
			"type": "arrow",
			"x": 7840.22830293076,
			"y": 1610.3482401567096,
			"width": 146.88738923242818,
			"height": 1.9760635322745657,
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
			"seed": 1336253349,
			"version": 150,
			"versionNonce": 944238379,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					146.88738923242818,
					1.9760635322745657
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "5dMyWaDAesFKIzFdpcele",
			"type": "arrow",
			"x": 7840.22830293076,
			"y": 1610.3482401567096,
			"width": 1.9760635322745657,
			"height": 102.75530367829106,
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
			"seed": 1770142347,
			"version": 202,
			"versionNonce": 777617381,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542528010,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.9760635322745657,
					-102.75530367829106
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "Xt0V7zvlwvqo4Fnv829w7",
				"focus": 0.9253729584422538,
				"gap": 2.2697270307805866
			},
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "3YQzDMyVQiEpWUkzBsFRn",
			"type": "line",
			"x": 7842.204366463035,
			"y": 1526.0361961129836,
			"width": 131.07888097422983,
			"height": 82.335980511451,
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
				"type": 2
			},
			"seed": 1391083173,
			"version": 258,
			"versionNonce": 1206935659,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					8.5629419731913,
					48.084212618687616
				],
				[
					47.42552477459594,
					75.74910207053495
				],
				[
					91.55761032873306,
					82.335980511451
				],
				[
					131.07888097422983,
					82.335980511451
				]
			],
			"lastCommittedPoint": [
				131.07888097422983,
				82.335980511451
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "jwco2VW8",
			"type": "text",
			"x": 7816.076695988649,
			"y": 1637.3544417644655,
			"width": 190.5797882080078,
			"height": 50,
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
			"seed": 1221078533,
			"version": 104,
			"versionNonce": 1596606757,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542588348,
			"link": null,
			"locked": false,
			"text": "Smooth\nDoesnt go to zero!",
			"rawText": "Smooth\nDoesnt go to zero!",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Smooth\nDoesnt go to zero!",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 190,
			"versionNonce": 1184727467,
			"isDeleted": false,
			"id": "8Zur_W97g-6Cwirlhrkif",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7979.325332807188,
			"y": 1527.9672074558546,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 35.13824528305411,
			"height": 42.16589433966514,
			"seed": 645594731,
			"groupIds": [
				"vcr04BCe2g3jdkbnHgmBn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-35.13824528305411,
					42.16589433966514
				]
			]
		},
		{
			"type": "line",
			"version": 208,
			"versionNonce": 1047925835,
			"isDeleted": false,
			"id": "nrc5LYdpyQkkhvqZU-yQr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7979.325332807188,
			"y": 1568.9618269527516,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 33.96697044028534,
			"height": 42.16589433966514,
			"seed": 1728444683,
			"groupIds": [
				"vcr04BCe2g3jdkbnHgmBn"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-33.96697044028534,
					-42.16589433966514
				]
			]
		},
		{
			"id": "M9KZ7up8iKJF__httGZLV",
			"type": "image",
			"x": 8109.597031407588,
			"y": 1458.198995282461,
			"width": 227.97519356897644,
			"height": 40.03135839455241,
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
			"seed": 56891627,
			"version": 168,
			"versionNonce": 1591956203,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "vq_HPpOak9eQqzY8qKgO2",
					"type": "arrow"
				}
			],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "30d6e30b6f442aa9be14353f1cf64378c9adb9bf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 173,
			"versionNonce": 643159083,
			"isDeleted": false,
			"id": "f4NWv490pVAHOFbqGVu-3",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8151.128965342,
			"y": 1610.0339652724042,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 146.88738923242818,
			"height": 1.9760635322745657,
			"seed": 2020529285,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					146.88738923242818,
					1.9760635322745657
				]
			]
		},
		{
			"type": "arrow",
			"version": 260,
			"versionNonce": 21642053,
			"isDeleted": false,
			"id": "vq_HPpOak9eQqzY8qKgO2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8151.128965342,
			"y": 1610.0339652724042,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.0302985958987847,
			"height": 104.73136721056608,
			"seed": 1393294309,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542528013,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "M9KZ7up8iKJF__httGZLV",
				"focus": 0.6231921560323136,
				"gap": 7.0722443848245575
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
					1.0302985958987847,
					-104.73136721056608
				]
			]
		},
		{
			"type": "line",
			"version": 355,
			"versionNonce": 1569260907,
			"isDeleted": false,
			"id": "A6MIJdDKDTRoHwcLu40ey",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8151.787653186091,
			"y": 1536.9196145782357,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 132.39625666241318,
			"height": 71.13828716189346,
			"seed": 1649227589,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					28.323577295939685,
					11.197693349557085
				],
				[
					49.40158830687142,
					50.71896399505363
				],
				[
					92.87498601691641,
					71.13828716189346
				],
				[
					132.39625666241318,
					71.13828716189346
				]
			]
		},
		{
			"type": "text",
			"version": 127,
			"versionNonce": 407281483,
			"isDeleted": false,
			"id": "j4mHPXEy",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8126.977358399888,
			"y": 1637.04016688016,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 190.5797882080078,
			"height": 50,
			"seed": 546309797,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542594310,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Smooth\nDoesnt go to zero!",
			"rawText": "Smooth\nDoesnt go to zero!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Smooth\nDoesnt go to zero!",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 213,
			"versionNonce": 806413995,
			"isDeleted": false,
			"id": "ccIVh2ZVs9ClfTqMCAMJY",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8290.225995218427,
			"y": 1527.6529325715492,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 35.13824528305411,
			"height": 42.16589433966514,
			"seed": 1619126789,
			"groupIds": [
				"53auo61lT8ihtZZioCr2L"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-35.13824528305411,
					42.16589433966514
				]
			]
		},
		{
			"type": "line",
			"version": 231,
			"versionNonce": 1312086347,
			"isDeleted": false,
			"id": "TM1458SHaN1yNxJy5k63p",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8290.225995218427,
			"y": 1568.6475520684462,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 33.96697044028534,
			"height": 42.16589433966514,
			"seed": 1126195557,
			"groupIds": [
				"53auo61lT8ihtZZioCr2L"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-33.96697044028534,
					-42.16589433966514
				]
			]
		},
		{
			"id": "YF86glU7BSY4ABw_h1Bew",
			"type": "image",
			"x": 8410.03540178929,
			"y": 1443.219911983441,
			"width": 328.65666976572777,
			"height": 62.95883480573697,
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
			"seed": 339384331,
			"version": 187,
			"versionNonce": 1954641899,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "PEYlEILRadTCo8vkdZUmi",
					"type": "arrow"
				}
			],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0dbd0e385cd29db3dc16542bf84442b33840e7c5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 199,
			"versionNonce": 1819195691,
			"isDeleted": false,
			"id": "VUp9pERd2fgKgOCupM3xN",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8487.059765318178,
			"y": 1610.0339653576348,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 146.88738923242818,
			"height": 1.9760635322745657,
			"seed": 988564267,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"startBinding": null,
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
					146.88738923242818,
					1.9760635322745657
				]
			]
		},
		{
			"type": "arrow",
			"version": 301,
			"versionNonce": 1632406181,
			"isDeleted": false,
			"id": "PEYlEILRadTCo8vkdZUmi",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8487.059765318178,
			"y": 1610.0339653576348,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.33660425621201284,
			"height": 96.78297352343952,
			"seed": 556772811,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542528015,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "YF86glU7BSY4ABw_h1Bew",
				"focus": 0.5337863064444036,
				"gap": 7.0722450450169845
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
					-0.33660425621201284,
					-96.78297352343952
				]
			]
		},
		{
			"type": "line",
			"version": 574,
			"versionNonce": 74230379,
			"isDeleted": false,
			"id": "paR4Z3LM45RJ4CB3yJF_a",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8489.268174386512,
			"y": 1544.6682207846732,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 71.18226830488311,
			"height": 65.71426287704867,
			"seed": 976075883,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.386425765638705,
					4.611378146531251
				],
				[
					55.60047320383637,
					31.734878998096974
				],
				[
					70.01659795935666,
					63.38968104068658
				],
				[
					71.18226830488311,
					65.71426287704867
				]
			]
		},
		{
			"type": "text",
			"version": 174,
			"versionNonce": 1910646027,
			"isDeleted": false,
			"id": "cPt5BAyz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8489.568123891202,
			"y": 1637.0401669653907,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 137.25985717773438,
			"height": 50,
			"seed": 833681163,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Goes to zero\nC2 continuous",
			"rawText": "Goes to zero\nC2 continuous",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Goes to zero\nC2 continuous",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 183,
			"versionNonce": 336546731,
			"isDeleted": false,
			"id": "BPCLhNDP7J95GG33vfjFB",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8580.06255445899,
			"y": 1548.6878404319011,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 50.423727985209325,
			"height": 26.27715402046124,
			"seed": 446421003,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542527588,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.942706926660776,
					19.885413853322063
				],
				[
					50.423727985209325,
					-6.391740167139176
				]
			]
		},
		{
			"id": "vS2lUWl9CiylxBVAukg54",
			"type": "image",
			"x": 8019.585283628824,
			"y": 1765.301457376679,
			"width": 455.33898528182925,
			"height": 71.96990159929739,
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
			"seed": 1238993035,
			"version": 101,
			"versionNonce": 1254734437,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542649877,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "87b3ea6147160b353d2453160c4711221929c322",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "xUsmnCN4",
			"type": "text",
			"x": 8093.725198595566,
			"y": 1720.5355126463812,
			"width": 288.26123046875,
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
			"seed": 821635403,
			"version": 40,
			"versionNonce": 1252524619,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542645312,
			"link": null,
			"locked": false,
			"text": "Lets build the model:",
			"rawText": "Lets build the model:",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets build the model:",
			"lineHeight": 1.25
		},
		{
			"id": "Z89odO8SwiX3AdhRj0m_7",
			"type": "image",
			"x": 7861.469914147098,
			"y": 1825.8499798390685,
			"width": 726.2054907206112,
			"height": 202.7798926968548,
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
			"seed": 1842357541,
			"version": 97,
			"versionNonce": 892248971,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715542662101,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a05f99e6edf76d383d73b9bc33a3defba3028701",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 198,
			"versionNonce": 1539297099,
			"isDeleted": true,
			"id": "G5Cxoh8Rz1RabprBiwHBI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8632.118090459953,
			"y": 1456.1173894726394,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 35.13824528305411,
			"height": 42.16589433966514,
			"seed": 1446239659,
			"groupIds": [
				"G79VRcMFIQQPPgb6YfTN4"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-35.13824528305411,
					42.16589433966514
				]
			]
		},
		{
			"type": "line",
			"version": 216,
			"versionNonce": 476045029,
			"isDeleted": true,
			"id": "uN_uHCWkgm1jQ3WI9MokJ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8632.118090459953,
			"y": 1497.1120089695364,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 33.96697044028534,
			"height": 42.16589433966514,
			"seed": 1122037835,
			"groupIds": [
				"G79VRcMFIQQPPgb6YfTN4"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-33.96697044028534,
					-42.16589433966514
				]
			]
		},
		{
			"id": "FVOXOegKBQACCcMMg8U3l",
			"type": "ellipse",
			"x": 4803.643338165611,
			"y": -1628.7711533430615,
			"width": 116.56762615125263,
			"height": 84.62759217189728,
			"angle": 5.766396289333851,
			"strokeColor": "#868e96",
			"backgroundColor": "#868e96",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 40,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 587768197,
			"version": 288,
			"versionNonce": 1094561259,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false
		},
		{
			"id": "kZoJ6h2F",
			"type": "text",
			"x": 4901.861900995447,
			"y": -1618.1492692806364,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#868e96",
			"backgroundColor": "#868e96",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 40,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 991956843,
			"version": 5,
			"versionNonce": 1026341445,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501118,
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
			"id": "PnJyOY2o",
			"type": "text",
			"x": 5376.927082399526,
			"y": -2004.9160255426084,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#4dabf7",
			"backgroundColor": "#868e96",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 328926539,
			"version": 8,
			"versionNonce": 80132235,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "oTowDXa_QlK9dCq9qs0Ii",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "jOZ77HJE",
			"type": "text",
			"x": 4792.756790408255,
			"y": -1365.9127989739145,
			"width": 9.999984741210938,
			"height": 25,
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
			"seed": 1759090443,
			"version": 6,
			"versionNonce": 445065637,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "TYg6PucuhvQl2lXgYfxZE",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "AlW0k472",
			"type": "text",
			"x": 4872.181393023702,
			"y": -1171.2495540072252,
			"width": 8.000015258789062,
			"height": 20,
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
			"seed": 1751838565,
			"version": 5,
			"versionNonce": 336949035,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "T5QboqcwaEPIRZRFSz_vi",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "Mpx7nCMV",
			"type": "text",
			"x": 4742.849567055668,
			"y": -1242.7948194363507,
			"width": 8.000015258789062,
			"height": 20,
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
			"seed": 1608726763,
			"version": 5,
			"versionNonce": 1973202181,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Z30Y6F831z5GwHGr-34-O",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "O9fmstZW",
			"type": "text",
			"x": 4489.745993523451,
			"y": -1234.5107545392593,
			"width": 9.999984741210938,
			"height": 25,
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
			"seed": 1609075109,
			"version": 5,
			"versionNonce": 1100239307,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "uIa2G3I-ni4jicDsiM8Z3",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "3jmJTEu0",
			"type": "text",
			"x": 4089.679135639146,
			"y": -1170.096461886622,
			"width": 9.999984741210938,
			"height": 25,
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
			"seed": 275736421,
			"version": 5,
			"versionNonce": 233489509,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "V4kTbKBgFaclk0R--cq4e",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "MbqTd-dROlRn_NcdZmudy",
			"type": "arrow",
			"x": 5178.844147565334,
			"y": -759.766082247156,
			"width": 368.03801772136467,
			"height": 0,
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
			"seed": 425109701,
			"version": 104,
			"versionNonce": 777904235,
			"isDeleted": true,
			"boundElements": [],
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					368.03801772136467,
					0
				]
			],
			"lastCommittedPoint": [
				368.03801772136467,
				0
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "triangle"
		},
		{
			"id": "CSS2Bpvv",
			"type": "text",
			"x": 5357.863164055411,
			"y": -772.266082247156,
			"width": 9.999984741210938,
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
			"seed": 78380933,
			"version": 5,
			"versionNonce": 1463742405,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "MbqTd-dROlRn_NcdZmudy",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "XBbwOmdK",
			"type": "text",
			"x": 5695.100204687843,
			"y": -1007.1193882662636,
			"width": 9.999984741210938,
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
			"seed": 1117383627,
			"version": 5,
			"versionNonce": 1950128907,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501118,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "dNuPVRSQcoLM9hAJH_gVk",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "kiTWivME",
			"type": "text",
			"x": 5687.175830414073,
			"y": -6.0653772364156,
			"width": 9.999984741210938,
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
			"seed": 563941611,
			"version": 5,
			"versionNonce": 1874243365,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501118,
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
			"id": "ZCSeZL7j",
			"type": "text",
			"x": 5131.476723591507,
			"y": -126.55485428373379,
			"width": 9.999984741210938,
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
			"seed": 1184981035,
			"version": 5,
			"versionNonce": 262865323,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "uV2Ndjy7b2_BpmNcB2ZjD",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "hk9lD2iP",
			"type": "text",
			"x": 6011.562539755889,
			"y": -193.8585762046828,
			"width": 9.999984741210938,
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
			"seed": 567759621,
			"version": 5,
			"versionNonce": 1438614149,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "yrX1-pMfI7ueV3cDE2zQb",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "DShpnACR",
			"type": "text",
			"x": 6520.648206381355,
			"y": -105.81117305308061,
			"width": 9.999984741210938,
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
			"seed": 506729899,
			"version": 5,
			"versionNonce": 164861003,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
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
			"id": "kBICu5sd",
			"type": "text",
			"x": 6619.0538011305125,
			"y": 283.8963817177362,
			"width": 9.999984741210938,
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
			"seed": 1570162341,
			"version": 5,
			"versionNonce": 1578559973,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ZFDP6xN3jobmk0xkKmVZz",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "jj6NqY6n",
			"type": "text",
			"x": 5797.824483483443,
			"y": 331.89039823950066,
			"width": 9.999984741210938,
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
			"seed": 107577765,
			"version": 5,
			"versionNonce": 1653658347,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "GEo3XtTHmAbwEEPS-SxTl",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "jbtvWzDu",
			"type": "text",
			"x": 6498.430385265014,
			"y": -580.0371488762728,
			"width": 9.999984741210938,
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
			"seed": 1398718213,
			"version": 5,
			"versionNonce": 1774871877,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "LK5nzGr5mItoMxTdetZDN",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "ZZrKJWJU",
			"type": "text",
			"x": 7185.996855069908,
			"y": -37.02078907718686,
			"width": 9.999984741210938,
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
			"seed": 1534110283,
			"version": 5,
			"versionNonce": 980237707,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "KJ-maOe05KFSmTjJKAy2N",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 414,
			"versionNonce": 1547138213,
			"isDeleted": true,
			"id": "nLZTXEbaZIvwMAi6UHA5l",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7677.626825001316,
			"y": -249.4342738608685,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 333.2811181729144,
			"height": 279.6764628024458,
			"seed": 1056068779,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715542501119,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JeH3ly5YqqxI6RtHpiVUY",
				"focus": 0.12733278314153362,
				"gap": 15.703813908944795
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
					34.15840131623596,
					158.19199927263344
				],
				[
					308.8094276777004,
					166.64055908645727
				],
				[
					333.2811181729144,
					279.6764628024458
				]
			]
		},
		{
			"id": "xYUqi4XA",
			"type": "text",
			"x": 7111.132778662837,
			"y": -147.4141953476586,
			"width": 531.139404296875,
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
			"seed": 1931020523,
			"version": 5,
			"versionNonce": 1017336875,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
			"link": null,
			"locked": false,
			"text": "independent of the dimension of the parameter values",
			"rawText": "independent of the dimension of the parameter values",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "independent of the dimension of the parameter values",
			"lineHeight": 1.25
		},
		{
			"id": "sy7XuR71",
			"type": "text",
			"x": 7390.292211188198,
			"y": -91.63078292741181,
			"width": 531.139404296875,
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
			"seed": 1743545989,
			"version": 4,
			"versionNonce": 1359714309,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
			"link": null,
			"locked": false,
			"text": "independent of the dimension of the parameter values",
			"rawText": "independent of the dimension of the parameter values",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "independent of the dimension of the parameter values",
			"lineHeight": 1.25
		},
		{
			"id": "CBHvAw09",
			"type": "text",
			"x": 8209.07961468266,
			"y": 284.8227804575105,
			"width": 9.999984741210938,
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
			"seed": 257128741,
			"version": 8,
			"versionNonce": 1226675915,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
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
			"id": "azWrkTYv",
			"type": "text",
			"x": 8225.75168181214,
			"y": 1024.2470820906053,
			"width": 9.999984741210938,
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
			"seed": 1574757067,
			"version": 3,
			"versionNonce": 306466661,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "XnwKTUy4w1dBcXVa7gdnN",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "FG9NiXRl",
			"type": "text",
			"x": 8241.416410079995,
			"y": 1192.275455607154,
			"width": 9.999984741210938,
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
			"seed": 1265217573,
			"version": 3,
			"versionNonce": 1584825707,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
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
			"id": "cJHlrt53",
			"type": "text",
			"x": 7962.388169138356,
			"y": 1528.9323793111948,
			"width": 9.999984741210938,
			"height": 25,
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
			"roundness": null,
			"seed": 553238309,
			"version": 3,
			"versionNonce": 1311709893,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1715542501119,
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
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 28,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "triangle",
		"scrollX": -7592.528362770654,
		"scrollY": -1215.71735013552,
		"zoom": {
			"value": 1.0552782140015236
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