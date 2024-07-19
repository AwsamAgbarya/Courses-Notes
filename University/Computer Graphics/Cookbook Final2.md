---
tags:
  - Cookbook
  - ComputerGraphics
---
# Spatial Data structures:
- Oct-tree:
	- Subdivides space into 4 (or 8 in 3d) quadrant depending of the parent quadrant is too full
	- Good for dynamic usage
	- needs recursion limit otherwise you cant guarantee that the subdivision doesn't go to infinity.
- Kd-tree:
	- Splits according to a metric, either alternating space, or longest space, using the median
	- Compute the median using Quick-sort like median in nlogn, but we can improve the worst case by choosing a better approximation of the median in linear time
	- Store one array but reorganize its members according to split and have pointers for each child
- Radius search:
	- intersect spheres with cubes and only consider their elements (Sub-linear time)
- K nearest neighbor:
	- Traverse down the path that has your point until you reach the smallest subtree that has k or more points
	- do radius search and get them all
	- priority queue pop them one by one
# Parametric Surfaces:
> [!info]- Explicit Representation 
> Explicit representation is an explicit way to represent curves, such that we can input an interval typically between 0 and 1 and we get the coordinate representation of this point
> Example:
> t = [0, 2PI]
> [cos(t), sin(t), 0]
## Curves:
- #### Smoothness (necessary but not sufficient):
	-  n-time continuously differentiable which can be achieved if the mapping is also n-time continuously differentiable
	- The curve is regular, meaning that the tangent vector (which is independent of the parameterization) never vanishes at any point, note that partial derivatives can disappear but not the entire gradient vector that represents the tangent vector of this curve.
- #### Arclength:
	- Calculates the magnitude of the tangential vectors at every point through the integral $\int_{a}^{b} \|p^{'}(t)\| dt$
	- The curve is parameterized by the arclength if its regular and the length of its tangent is 1 everywhere
	- hard to analytically compute
- #### Important properties:
	- Our control points are used as coefficients for calculating the curve
	- Smooth and predictable editing
	- No unwanted oscillation 
	- Local control
	- Easy rendering
	- Affine invariant
- We want the general form of the curve to be represented as Control points * Basis functions
- The same curve segment can be re-parameterized in different ways and still represent the same curve

## Curve Generation through Interpolation:
-  Which basis functions should we use?
- #### Polynomials:
	- Polynomial is compromise of a monomial of degree n that forms n+1 dimensional vector space and coefficients $f(x) = b(x)\cdot c$
	- Coefficients are hard to tune to our liking because they are unpredictable (in a realistic manner) which we can infer from the taylor expansion as coefficient k affects the kth derivative at the point we are evaluating
- #### Lagrange:
	- $L_{i}^{n}(t) = \frac{\prod_{j=0, j!=i}^{n}(t-t_{j})}{\prod_{j=0,j!=i}^{n}(t_{i}-t_{j})}$
	- Perfectly interpolates each point and has some oscillation in between according to the degree due to the fact that the Lagrange polynomial on the defined intervals is only 1 for the point itself and 0 for everything else
	- Depends on the choice of parameterization
	- Lagrange polynomials form partition of Unity i.e $1 = \sum_{i=0}^{n}L_{i}^{n}(u)$
	- Lagrange polynomials are affine invariant $T\left(\sum_{i=0}^{n}p_{i}L_{i}^{n}(u)\right)= \sum_{i=0}^{n}Tp_{i}L_{i}^{n}(u)$ meaning we can generate the curve then transform it or transform the points then generate the curve which is quite useful to transfer between coordinate systems for diff devices
- #### Hermite:
	- Interpolates geometric points and their derivatives but requires twice as many basis functions
	- $p(u) = p_{0}H_{0}^{3}(u) + m_{0}H_{1}^{3}(u) + m_{1}H_{2}^{3}(u) + p_{1}H_{3}^{3}(u)$
- #### Radial Basis functions:
	- Interpolation is represented through some basis functions that are symmetrically radial around a center and fall off
	- $p(u) = \sum_{i}w_{i}r(\|t_{i}-u\|)$
	-  in order to calculate the weights of the basis functions we need to solve a LSE for every point i.
## Curve Generation through Approximation:
- Interpolation is not always necessary, sometimes we get better solutions from relaxing the interpolation and only approximating something across all points, easier to control!
- We usually have a polynomial function and some values we want to predict, we try to minimize the squared distances to all points
- $f(x) = b(t) \cdot c$
- $min_{p\in \prod_{d}} \sum_{i=0}^{n}\|f(x) - f_i\|^2$
- This problem is convex and continuously differentiable (if the function f is) meaning if we set the first derivative to 0 we can reach a solution.
- $J(x) =(b(x)\cdot c - f_{i})^{T}(b(x)\cdot c -f_{i}) = c^{T}b(x)^{T}b(x)c - 2c^{T}b(x)^{T}f_{i}+f_{i}^{T}f_{i}$
- $J^{'}(x) = b(x)^{T}b(x)c + (b(x)^{T}b(x))^{T}c-2b(x)^{T}f_{i} = b(x)^{T}b(x)c- b(x)^{T}f_{i}$
- $\sum_{i} b(x_{i})b(x_{i})^{T}c = \sum_{i}b(x_{i})f_{i}$
- Fits one global polynomial to all points while considering all of them at every point which can be very bad
- We can perform a weighted version of this algorithm around a specific root such that points outside a certain distance fall off to 0 effect
- This is a local polynomial with local coefficients, if we do it for every single point we achieve moving least squares.
- Wendlands function: $(1-\frac{d}{h})^4(\frac{4d}{h}+1)$
## Bezier curves:
- Bezier curves are curves defined by a control polygon such that the Bezier curve is contained in its convex hull, interpolates the first and last point and smoothly follows the control polygon.
- The control polygon points are defined on a fixed interval from 0 to 1.
- We use Bernstein polynomials as basis function for Bezier curves.
- #### Bernstein Polynomials:
	- Basis of ith point of degree n : $B_{i}^{n} = \begin{bmatrix} n\\ i \end{bmatrix} u^{i}(1-u)^{n-i}$
	- forms the basis for n+1 points (n+1 dimensional vector space)
	-  Has partition of Unity over the [0,1] interval: $\sum_{i=0}^{n}B_{i}^{n}(u)=1$ this means that every point on the curve is a linear combination of the other points which makes it follow the curve, also makes it affine invariant.
	- Non-negativity: $B_{i}^{n}(u) \geq 0$ which makes it a convex combination of the control points and thus only existing in its convex hull.
	- Recursively defined: $B_{i}^{n}(u) = uB_{i-1}^{n-1} + (1-u)B_{i}^{n-1}(u)$ so its a linear interpolation of the previous two Berstein polynomials of previous degree such that  $B_{0}^{0} = 1$ and $B_{j}^{n}=0$ if $j \ne {0...n}$
	- that means that B-polynom of degree 0 will only represent the control points between them, a B-polynom of degree 1 will interpolate between those points linearly, a B-polynom of degree 2 will interpolate  the straight lines formed by the control polygonetc...
	- Symmetry: $B_{i}^{n}(u) = B_{n-i}^{n}(1-u)$ i.e they produce the same weights from either side of the curve according to their control points.
- The derivative of Bezier curve can be expressed as: $p^{'}(t) = n \sum_{i=0}^{n-1}(b_{i-1} - b_{i}) B_{i}^{n-1}(t)$ Resulting in something related to the consecutive segments of the polygon and at the start and end it is the exact segment.
- Variational diminishing property says that a Bezier curve does not oscillate more than the polygon itself, i.e the number of intersections the control polygon has with a line is always larger or equals than the bezier curve.
- #### De casteljau Algorithm:
	- This algorithm is used for evaluation of a certain point in a bezier curve and also used for subdivision which can be used to intersect the curve with a line.
	- The same way we represented the Bernstein polynomials in a recursive manner, we can define the segments in a recursive manner: $b_{i}^{n}(u) = ub_{i+1}^{n-1} + (1-u)b_{i}^{n-1}(u)$ down until $b_{i}^{0}=b_{i}$
	- This algorithm is used to evaluate the point and the tangent at the certain interval we picked.
- #### Subdivision:
	- used to get more control over the curve.
	- can be done with de casteljau but you cannot move all points freely otherwise you ruin the continuity.
	-  Generate new control points via $b_{i}^{'} = (1-\frac{i}{n+1})b_{i} + \frac{i}{n+1}b_{i-1}$

> [!info]- Parametric continuity (Cn)
> is when all segments in  a spline match their first derivative up to degree n on the connection points. 

>[!info]- Geometric continuity (Gn)
>is when all segments in the spline can be reparameterized such that the connection points will be Cn continuous
## Splines:
- A combination of curves, each of which are regular and continuous and their intersection is also regular and continuous.
- Has exponential decay local control (because we have a bunch of constraints that control neighboring segments that needs to be adjusted if my segment moves)
- Doesn't require a lot of editing for variations, the more points there are.
- #### Smoothness:
	- Every polynomial segment must be continuously differentiable and regular.
	- At the connection points the positions and the derivatives of the two connecting curves must match (Cn continuity)
	- For example:
		- C0 continuity: The two  curves match their position
		- C1 continuity: The two curves match their first derivative, which for Bezier curves is the first and last segments (equal direction and length)
		- G1 continuity: the two curves match their first derivative in direction but not in length.
		- C2 continuity: One order of differences higher i.e the difference of the 2nd to last points is equal at their intersection
	- As always these conditions are necessary but not sufficient we can always create a non-smooth curve using cusps
- #### B-splines:
	- Better locality for splines at the cost of continuity, Formulated as Basis function * control point
	- We define knots such that the first and last n are equal respectively and the ones in the middle are ascending
	- Our basis function is defined as: $N_{i}^{n}(t) = \frac{t-t_{i}}{t_{i+n}-t_{i}}N_{i}^{n-1}(t) + \frac{t_{i+1+n}-t}{t_{i+1+n}-t_{i+1}}N_{i+1}^{n-1}(t)$
	- We can see from our basis function that:
		- Our degree affects our local control, i.e basis function of degree n has control from knot i until knot i+n+1 (if $N_0^2$ has control from 0-3 and $N_1^2$ has control from 1-4 then $N_0^3$ has control from 0 to 4)
		- $N_{i}^{0} = 1$ if t lies within i and i+1 and 0 otherwise
		- The basis functions are a partition of Unity.
		- If we have n knots the curve would interpolate that point and if we have n+1 points lying on the curve then that line is interpolated.
		- **Why we need knots:** N is defined to operate in n+1 interval, meaning the first is gonna be in 0 -> n+1 and the last will be in m -> m+n+1 and we want those basis functions to be 0 at each side except the first and last will be 1 at the start/end to interpolate the points.
		- **Continuity vs interpolation**: While having mu points makes you interpolate that point, you also give up mu parametric continuity at that point (C n-mu) so if you have a polynomial of degree 4 and knots of multiplicity 3 then you are only c1 continuous.
		- **Continuity vs degree:** The higher the degree of the polynomial the higher the continuity Cn
		- **Degree vs interpolation:** In order to interpolate a point in a B-spline of degree n you need n knots of that point. ??
		- **Control Points:** We have k-n-1 Control points and basis functions because if we have for example 10 Knots we have 9 spaces for basis functions of degree 0 to lie in and thus 8 intervals between those basis functions for basis functions of degree 1 to lie in etc....
## Surfaces:
- Ties two different intervals into xyz coordinates
- if one interval is fixed it creates a curve from the other
- #### Smoothness:
	- its mapping has to be continuously differentiable
	- it has to be regular, i.e all its curve domains have to be regular and linearly independent... The tangent at every part of every curve has to be non-zero to not hace any kinks. A better way to define this is by creating the tangent plane from those two tangent vectors and say that the tangent plane cannot disappear
	- tangent planes and normals are independent of parameterization but their sign is.
- #### Tensor products:
	- In order to formulate surfaces with control points* Basis functions we have to define basis functions for them.
	- We define basis functions as tensor product of curve basis functions (Univariate functions)
	- Points have to lie on a regular grid in order to contribute to both basis functions
- #### Polynomials:
	- We can choose to univariate polynomials of degree n,m such that each of them form a n+1,m+1 vector spaces and their tensor product would be in the space of (n+1)(m+1) vector space.
	- an example of a multi-variate bi-linear polynomial is (1,u,v,uv) and while its made up of two linear polynomials, itself is not linear and does not only form linear lines but also curves ones.
- #### Bezier:
	- Very similar to Bezier curves
	- Forms a partition of UNity, non-negative and interpolates the 4 corners and the surface is inside the convex hull.
	- De casteljau can be performed twice in order to evaluate the point that we want BUT it has a complexity of: $n_{1} \cdot \sum^{n_{2}-1} 3i + \sum^{n_{1}-1} 3i = n_{1} \cdot n_{2}^{2} + n_{1}^{2}$
	- in De casteljau we usually want to do many evaluations on short distances (SHORTEST FIRST) and few evaluations on long distances instead of the opposite
- #### Irregular data:
	- Modelling data as a height field, i.e we have a function such that we tell it what x,y we are at and it gives us the final z, this is more useful for data that just wont lie on a grid like the polynomials
	- BOTH RBF and WLS work for this
- QUESTION5 ??

# Implicit Surfaces:
> [!info]- Implicit representation:
> An implicit representation of a curve/surface is a 
> representation of a surface through an equation that takes as input the position of the point and produces a scalar value that indicates if that point is on the curve/surface
- Curve definition (typically from R3 to R) is the zero set of the implicit representation such that the interior is negative values and the exterior is positive values.
- Properties:
	- The curve from our implicit representation is always a closed curve (no boundaries).
	- should be continuously differentiable in the neighborhood of the surface and the gradient shouldn't be zero at the surface in order to separate the interior from the exterior
	- continuous around the zero set 
- While this configuration is arbitrary, the definition is quite convenient because the gradient of the implicit definition will point in the direction of the outward normals.
- This representation can be transformed is composite with the inverse of the transformation matrix.
## Algebraic surfaces:
- Algebraic curves/surfaces are the zero-set of polynomial functions (typically we only look at linear and quadratic), algebraic curves are also called conic sections.
- Typically written in the regular polynomial way but can also be written in a quadratic matrix form (symmetric bilinear) $x^{T}K x$
- Closed under affine and projective transformations.
- Transformations need to be multiplied from both sides in the bilinear form $K^{'} = A^{-T}KA^{-1}$
- The symmetric matrix in the middle can be a smiley parabola if its PSD and a frowning parabola if its NSD.
- The matrix K describes the shape:
	- If the xy terms are 0 then it is either an ellipse or a circled:
		- if the quadratic terms are equal its a circle otherwise its an ellipse
		- if the determinant of the matrix is 0 then it is a singular point.
	- if the xy terms are not 0 then its either a hyperbola or a parabola:
		- if B^2 -4AC =0 then it is a parabola, if its bigger than 0 then its a hyperbola.
		- If the determinant of the matrix ix 0 then it is a degenerate form of hyperbola (2 lines intersection each other) and parabola (one line)
- The matrix K can always be diagonaizable via rotations.
- This diagonal matrix is the eigenvalues of the matrix which is the solution of the characteristic polynomial of the equation.
	- if all eigenvalues are positive then the form is degenerate and we have no real shape
	- if one is negative then we have non-degenerate forms
	- if one is zero then we have 2 lines
	- if two are zero then we have 1 line
## Combinations:
- to Union implicit functions we have to take the minimum of the two functions, this might produce coarse results and thus we can softmin it using $\frac{1}{1+\alpha}(g+f - \sqrt{g^{2}+f^{2}-2\alpha gf})$
- To intersect implicit functions we have to take the minimum of the two functions this might product coarse results and thus we can softmax it using $\frac{1}{1+\alpha}(g+f + \sqrt{g^{2}+f^{2}-2\alpha gf})$
- This is not the "intuitive way" because we want to just add and subtract things from each other.
## Blobs:
- We can represent circles as gaussians along a certain radius, this will allow our previous desire of combinations just be an addition and subtraction of implicit surfaces, because those RBF functions describe the surface using values that decay further away and the sum of them will be just that. $\sum_{i} v_{i}a_{i}e^{-b_{i}\|p-p_{i}\|^2}$
- This function has no local support i.e doesnt tend to zero and every functions tends to every single function so we replace it with something with local support.
## Skeletons:
- a skeleton is an offset surface, meaning we define a skeleton line, point or polygon and the surface is defined by taking the smallest distance to any part of the set S and using a distance function on it.
## Convolution Surfaces:
-  Combining the idea of blobs and Skeletons, we want a surface that is described by an offset surface of a skeleton but we also want to describe its surface via Blobs such that we can add and subtract them from each other easily, this is exactly a convolution surface.
- Instead of summing over a fixed number of points $\sum_{i} v_{i}a_{i}e^{-b_{i}\|p-p_{i}\|^2}$ we sum over an infinite number of points along the line/segment of the skeleton $\int_{S} e^{-b_{i}\|p-q\|^{2}}dq - c$ (c is the threshold)
- This is a covolution surface because we are convolving a gaussian over an indicator function.
- Convolutions are linear, so you can convolve 2 segments then combine or combine then convolve.
- The gaussian convolution intersects the edges in half because at the edge we only have the area of half of the gaussian as opposed to the middle where we have all of it, so if we want to preserve the endpoints we can just set the threshold to 1/2.
## From Points:
- if we have a set of points describing a surface we need to find a function that describes those points as the zero set of that function, but that information on its own is not enough to solve this otherwise we can just describe everything as the zero set and that would be our solution.
- The way to do this is by adding extra information via a signed distance function which is what we want from our implicit representation, a function that gives negative values (distances) for interior zero for the surface and positive values (distance) for the exterior.
- So to add interior and exterior information we need to add 2N constraints, this is done via normals:
	- If we have the normals then its quite easy to set up, in the direction of the normal with a specific alpha we set the value to be alpha, for both positive and negative values. This alpha can be decided only if the point we choose is still the closest neighbour to us otherwise we are treading territory close to other side of the surface.
	- If we don't have the normals then we need to compute the normals, we can do so with a least squares approach, by calculating the normal that as the minimal projection magnitude from all the neighbors of that point $argmin_{\|n\|=1}\sum_{j\in Neighbors} (n^{T}(p_{j}-p_{i}))^{2} =argmin_{\|n\|=1}n^{T}\Sigma_{i}n$ which is the solution to the smallest eigenvector of the covariance matrix, but the sign is not trivial. (points can be weighted according to the distance)
- #### RBF approach:
	- given our points and constraints we construct an RBF per point according to the distance to that point and solve a LSE to get the weight of that RBF
	- for very large systems this is unfeasible, this we sub-sample the points until we are satisfied with the quality trade-off (we sub-sample according to some radius that removes redundant information)
- #### Hoppe's approach:
	- implicit functions are piece-wise linear, why not just fit a local line/plane to every single point and in the neighborhood of that point only evaluate according to that line? (distance can be computed according to normals at those planes)
	- This causes artifacts because the function is no longer continuous i.e not a closed loop and will have holes in it, so we use a weighted version of it such that if we are on the edge of neighborhood of one point we are also considering the neighboring planes.
	- MLS is the weighted version of Hoppe's approach, we have to solve the problem $min \sum \theta(d_{i})(f(p_{i})-0)^{2} + \sum \theta(d_{i}) (f(p_{i}+\alpha_{i} n_{i})- \alpha_{i})^{2}$
	- This MLS approach fits a local polynomial to each point but also weights it according to the distance to that point.
	- This can produce complex functions even with fitted constant polynomials due to the weighting function being complex
	- we choose a weight function that is local and tends to 0
	- the LSE for fitting a local plane for our point needs to see 1 sample for constant polynomials, 4 samples for linear and 10 for quadratic.
	- if you don't have enough samples to evaluate the LSE, then you are likely very far away from the surface and don't need to be accurate as long as you get the right sign, so you can take the k nearest neighbors or a constant value.
	- For normals on the surface we need the gradient which is not the gradient of the local polynomial but the gradient of the implicit function itself. We can use finite differentiation by varying the function in each direction and dividing by epsilon. OR we can use the derivative of the implicit function, or for degree >0 we use the derivative of the linear polynomial.
## Tessellation and marching cubes:
- #### Tesselation:
	- The zero set of a complicated equation is hard to compute/generate, evaluation is otherwise easy, tesselation is an algorithm for rendering an approximation of the zero set.
	- Sample points on a grid and evaluate all of them so that they're either in or out, then proceed to divide each square into one of 8 cases that have a deterministic way of connecting edges.
	- There are ambiguous cases for which we just have to stick with a deterministic choice to keep things consistent.
	- Can also be split into triangles where solutions for all cases are unique.
- #### Marching cubes:
	-  3D Tesselation, taking one layer at a time, one cube at a time and evaluating the case according to 256 different cases and connecting the edges we have.
	- Those 256 cases are technically only 14 but in practice we do 256 for an easier table creation.
	- We linearly interpolate between the edges according to their value: $v = \frac{f(b)}{f(b)-f(a)} v_{a} + (1-\frac{f(b)}{f(b)-f(a)})v_{b}$
	- If we have access to the neighboring cubes we can also compute the normals at these vertices
	- If during the ambiguous cases we decide on something wrong, we will have holes in our cubes, thus we should pick carefully accordingly by looking at the previous cube.
	- We can also use Tetrahedra instead of cubes which avoids the whole ambiguity cases and it has less cases but will generate more triangles 
	- Optimizations:
		- if one corner has a value really close to the surface while others dont, you might want to snap it to the surface that way you dont get a super small triangle that does not contribute any info the the surface
		- if you have the surface intersect the cube really close to an edge then it will generate skinny triangles that also can be snapped out.
		- Basically snap to corners and if more than one vertex snaps to a corner then the triangle is generate and can be discarded
		- To reduce anti-aliasing artifacts you can also calculate the normals at each vertex and if they heavily disagree you calculate the intersection of their tangents and add a point there to add sharp features, because grid sampling is like undersampling high frequencies features
## Rendering:
- Rendering techniques are based on a change of sign (changing from pos to neg)
- #### Raycasting:
	- shoot a bunch of rays from the eye through every pixel
	- Secondary rays can be shot from the intersection location of the first ray
	- We evaluate the ray in the function using some fixed interval and at the sign change we count it as intersection with the surface.
- #### Sphere marching:
	- Since we are using SDFs, we know that there is no surface within our radius so we move that value distance forward and evaluate again
	- This is good close to the surface but bad far away because we arent really doing an SDF far away, we are just approximating the SDF by some value
		- If we are really far away just take the distance to the closest point
		- or just make your step size dynamically go back and fourth according to the sign
		- Scale the step with some weight [0,1]
# Polygon Meshes:
## Representations:
- #### Definitions:
	- A geometric graph is a pair of nodes and edges and for each point is attached some spatial coordinates.
	- Polygons are geometric graphs, polygons can be closed if they're a closed loop, polygons can be planar if they lie in a plane, polygons are simple if they don't have self intersections and every vertex is incident upon 2 edges
	- polygon mesh is a finite closed simply polygons set, such that no two polygons are intersecting with more than a point or edge, every edge belongs to at least one polygon.
	- Polyhedron is a closed simple polygon mesh that has cyclically ordered faces.
	- Orientable polygon mesh if every face has the same Orientation, by definition every polyhedron is orientable and if a closed mesh is not orientable it has a self intersection
- #### Euler Poincare theory:
	- Characteristics of a polygon is defined by the formula v - e - f = c
	- For a finite planar closed polygon mesh with a single boundary satisfied c=1
	- For manifolds that are homeomorphic to a sphere c=2
	- Further triangle mesh information:
		- Every triangle has 3 edges and every edge has 2 faces so 2e=3f
		- if we substitute in Euler poincare we get that $v - \frac{3}{2}f + f = c$ i.e $2v = f+ 2c$
		- Similarly $v -e + \frac{2}{3}e =c$ i.e $3v = e + 3c$ and we also have 2 vertices on each edge so the avg valence of a vertex is 6
	- Euler poincare also has a version with a genus:
		- $v - e + f= 2(1-g)$
		- Proof through the spanning tree method we get V=e+1 and (F+1) = e+1
- #### Data Structures:
	- Indexed Face set:
		- No neighborhood relationship
		- For each vertex we store a position and some attributes like associated face etc...
		- for each face we store three vertices
		- edges are not directly accessable
		- This has store of e
	- HE
		- for each vertex we store positions and one HE
		- for each face with store one HE
		- for each HE we store Next, opp, face, starting vertex and maybe previous
		- Storage requirement is 9e
		- We store boundaries as HE to be able to go around the boundary
	- HFAH:
		- Vertex degree affects the size of rows in the vertex table which needs to be dynamic
		- each edge stores incident faces and vertices
		- each face stores incident edges
		- each vertex stores outgoing edges
		- Storage requirement is 8e
## Compression:
- Vertex table has O(v) if each vertex has 3x16 bits for coordinates and k attributes and v different vertices.
- Face table has O(vlogv) if each vertex has 3xlog2(v) bits per face and v different vertices meaning ~1/2f different faces.
- #### Cut Border Algorithm (2b avg, 5b max):
	-  Start with a random Triangle
	- Define an action per case youre gonna face
		- New vertex operation (50%) we move the tail to a new vertex that we have not encountered yet
		- Connect forward operation (45%) we move the head along the cut border to an already known vertex to create a new triangle
		- Connect backward operation (1%) we move the tail not the head
		- Boundary move operation (1%) We move along the boundary without actually defining a triangle
		- Split border operation (3%) We move our head to an already existing boundary and split it into a loop and our current one
		- Merge border operation (0%) we move the head across a different border and merge it with ours
	- perform BFS and record the action that you took during it
	- Encode the actions as bits and send them
	- Reconstruct accordingly
- #### Valence coding:
	- Perform circular movement around a pivot node and counting up with the valence, record the valence of it and store that information
	- Merging and splitting are also possible operations here sadly which we need to record extra information that isn't just the valence.
	- Skipping works on meshes without holes otherwise we do need merging
- #### Coordinate compression:
	- Create coordinates are on a grid and normalize them as ints relative to the bounding box in a desired resolution
	- use neighbouring triangles to predict new coordinates by using correction error
	- infer possible valence off of the curvature of the geometry
## Simplification:
- #### Uses of simplification:
	- Level of details
	- Passing to a 3D printer
	- Interactive editing
- #### Criteria:
	- Hausdorff distance:
		- Minimum distance of a point from any other point in the pointset $min_{p_{i} \in S} \|p-p_i\|$
		- One-sided Hausdorff distance is the maximal hausdorff distance of every point in a set to another
		- The actual Hausdorff distance is the maximum of both Hausdorff distances
	- Parametric distance:
		- Given certain uv coordinates we compute the difference in their mapping and return the maximal distance of all possible uv options
		- This upper bounds the Hausdorff distance
		- $O(n^{3}log_{2}(n))$
- #### Iterative Simplification
	-  Operations:
		-  Vertex removal: remove a vertex and retriangulate the hole in the mesh, this is the most general case but the number of triangulations is large and is upper bounded by the Catalan number.
		- Edge collapse: special case of Vertex removal such that we remove and edge and map both its end points to one point (either in the middle or to one side) this is used in practice.
			-  Can be replayed back by an edge split if we encode which edge we split $log_{2}(n)$ and the two edges we split at *5bits avg*  and the original 2 vertices that we collapsed.
		- Triangle collapse: collapse small triangles that dont contribute much
	- Errors:
		-  Hausdorff distance: when perform a vertex removal and mapping to a new vertex we consider the original vertex's projection onto each of the triangles and computing the minimal hausdorff distance to them so see how far the vertex moved, This gets expensive in subsequent steps where you have to keep track of the original mesh as it projects onto subsequent triangulations.
		- Quadric error: Consider the sum of suqared distances from the destination point to each of the edges of the original point $(a_{i}v_{x}+ b_{i}v_{y} + c )^{2}$and write it in a quadratic error way $\sum_{i}vT Q_{ik}v = v^{T}Qv$
			- This is the best method as it considers the original mesh by accumulating the quadric errors of each subsequent step but it also leads it to hugely overestimate the error due to all distances being squared.
			- very fast and simple and allows for connection of disconnected edges.
			- We need to not collapse boundaries and not flip faces when considering which vertex to choose
			- we sort all quadric errors of all vertices in a PQ and update them accordingly after every pop
		- Clustering:
			- Faster with dense meshes
			- Clusters according to resolution grid and only takes in the multi-cell triangles
			- bad approximation.
## Laplacian:
- The laplacian is the concatenation of the divergence and the gradient operator such that it tells us how much each point differs from the average of its infinitismal neighborhood
- The laplace beltrami operator is an operator that generalizes to manifolds and not just Functions
- Discretizing a derivative can be either by interpolating the points or by defining the FEM into our interval or using the integral definition to get the next and previous  point
- Uniform laplacian is $\frac{1}{\|N_{i}\|} \sum_{N_{i}} f(v_{j}) - f(v_{i})$
	- In the discretized sense we have $\frac{1}{\|N_{i}\|}$ in the diagonal of the mass matrix and $-\|N_{i}\|$ in the diagonal of the stiffness matrix
- Cotan laplacian uses stokes divergence theorem to compute the laplacian by summing the gradient in the direction of the normals
	- Integrate over the dual edges (or sum in this case), and use the actual edges as normals (after normalization)
	- We assume that the gradient is constant in this direction of the normal and compute it according to v_j - v_i
	- We end up with dual/edge for the stiffness matrix or cotan alpha + beta
	- and the mass matrix is 1/ the area of the Vornoi cell (for Delaunay meshes)
- Explicit Euler smoothing:
	- $f(t_{1)}= f(t_{0}) + h\cdot \Delta f(t_0)$
	- explodes
	- Euler's method suffer from inaccuracies , error decreases linearly O(h)
- Implicit Euler smoothing:
	- Implicit Euler overtime dampens the motion which is stable
	-  $f(t_{1)}= f(t_{0}) + h\cdot \Delta f(t_1)$
	- $(I-h\Delta)  f(t_{1}) = f(t_{0})$
- Trapezoidal method smoothing:
	- $f(t_{1)}= f(t_{0}) + h\cdot \Delta f(\frac{t_{0}+t_{1}}{2})$
	- $(I - \frac{h\Delta}{2})f(t_{1}) = f(t_{0})+ \frac{\Delta f(t_{0})}{2}$
- Laplacian Manifold Harmonics:
	- Eigenfunctions of laplacian are the sine and cosine functions
	- if we perform eigenvalue decomposition we can use those eigenvectors as a Fourier transform basis functions and we can compute their coefficients via $\tilde{x} = x^{T}\star_{0}H_{k}$ 
	- we can perform low pass filters in fourier domain and transform back into spatial domain 
## Deformation:
- We want to make adjustments to the mesh through some intuitive handles and be able to make small adjustments without destroying the underlying structure
- #### Space deformation:
	- You distort the space around the mesh and through the parameterization the mesh follows along with the deformation. This is a mapping from R3 to R3.
	- This method is volume preserving i.e if two things are close to each other they behave similarly
	-  Lattice deformation:
		- We consider a grid over out mesh and define it as the 3 dimensional bsplines and we try to solve for the displacement of those control points  though $d(u) = \sum_{i} d(c_{l}) N_{l}(u)$
		- We can solve this as a linear system of equations for unknown Cs and while we dont have any solution because this is under-determined, we can find the best matching solution to it by computing the SVD with some desirable constraints
		- can also add constraints to fix things in place
	-  Cage deformation:
		- We surround the mesh with a grid instead of all control points instead of a grid which makes it more intuitive to maneuver.
		- We have similar definitions except now we have a phi function that is hard to write out as a function but it interpolates between its point and every other pount from 1 to 0
	- Radial basis functions:
		- We dont use any grids instead we use direct points on the surface as handles and describe the space deformation as a radial basis function from that point such that points that are really far away are zero.
		- We add some constraints that some points are not moving
		- Solve LSE for weights to find weights
- #### Surface deformation:
	- we are directly modifying the geometry and computing new vertex positions
	- Naive laplacian:
		- Laplacian holds information for local geometry and we want the laplacian to not change very much so we solve that the laplacian of the modified vertices is as close as possible to the original ones which results in $L_{s}^{T}ML_{s}p^{'} = L_{s}\delta$
		- Linear deformations they preserve the local geometry orientation so we need a non-linear method
	- ARAP:
		- We want our mesh to move as rigid as possible, i,e if we take neighborhoods we want to describe the difference of our vertices as a rotation of the original in the least squares sense.
		- our energy function is $E = \sum_{vertices}\sum_{neighbors} w_{ij} \| (v_{i}^{'} - v_{j}^{'}) - R_{i}(v_{i}-v_{j})\|^{2}$
		- Local solve for every neighborhood
		- we decompose the covariance matrix that describes the change in SVD sense and take the one that scales with 1
		- Global solve for the entire system using least squares by setting the energy function derivative to zero
		- we arrive at $Lv^{'} = L(R_{i}+R_{j})v$
		- which we can solve very easily by computing cholesky decomposition at the very start of L and back subsittuing.
## Subdivision
- Normal smoothing schemes wont be able to deal with irregular meshes so we devise some subdivision smoothing schemes furthermore some meshes have arbitrary topology
-  Subdivision can be stationary and non-stationary in their masking, they can be interpolating to the original mesh and non-interpolant, they can be linear in their masking and non-linear
- Doo Sabins algorithm cuts corners with linear interpolation and approximates the cubic b-spline that is created by that control polygon but leave some artifacts at irregular vertices.
- Sqrt(3) is a 3-1 subdivision scheme in triangular meshes that adds vertices in the barycenters of each triangle, connects the vertices and flips the edges.
- Loop subdivision is a 4-1 subdivision scheme that adds a midpoint to every edge and connects them in the triangle face to create 4 faces, and it smooths the old and new vertices using certain masks.
- Catmull Clark is an algorithm that after one iteration will turn any mesh into a quad mesh and smooths the 3 types of vertices (center, midpoint of edge and old) differently.







Exam:
meet 25m
start with topic of choice
spatial data structures
can you write down the bernstein basis (explain not memeorize)
affine combinations 
tangents of least squares fitting polynom is not tangent example const function
higher polynomials have more than one zero so they produce surfaces somewhere else
1. volume gradient go around vertex compute triangle normals and weight by area
	1. integral of surface normals over a certain region doesnt depend on vertex pos
2. surface area gradient for each triangle  (mean curvature normal) multiple position of vertices with cotan laplacian
3. avg triangles over vertex
4. sum of edges

hf requires orientability
genus is important
avg degree

why decasteljau is better and slower