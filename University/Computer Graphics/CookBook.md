### [[Representation]]:
- To find a point in space via triangulation [[Triangulation.png]]:
	$$ X = \frac{ Y * \sin{\alpha}}{\sin{(180-2\alpha)}} $$

### [[Transformation]]:
* Scaling Matrix:
	$$ \begin{pmatrix}   s_{1} & 0 & 0\\   0 & s_{2} & 0 \\ 0 & 0 & s_{3}   \end{pmatrix} $$
* Shearing Matrix:
	$$ \begin{pmatrix}   1 & s_{1} & s_{2}\\   s_{3} & 1 & s_{4} \\ s_{5} & s_{6} & 1   \end{pmatrix} $$
* Rotation Matrix:
	$$ \begin{pmatrix}   \cos & -\sin & \sin \\   \sin & \cos & -\sin \\ -\sin & \sin & \cos   \end{pmatrix} $$
* Change of Basis:
	RoAx is the rotation axis, MinXr is the cross product between the minimum canonical basis (minimum according to r components)
	$$ \begin{bmatrix}   rowAx_{x} & rowAx_{y} & rowAx_{z} & Origin_{x} \\  minXr_{x}  & minXr_{y} & minXr_{z} & Origin_{y} \\ rXs_{x} & rXs_{y} & rXs_{z} & Origin_{z} \\ 0 & 0 & 0 & 1 \end{bmatrix} $$
* Local to Global:
	$$ G_{j} = L_{1} * L_{2} * \dots * L_{3} = G_{j-1} * L_{j}$$
* Primary View Projection along z axis:
	$$ \begin{pmatrix}   1 & 0 & 0 & 0\\   0 & 1 & 0 & 0\\ 0 & 0 & 0 & 1\end{pmatrix} $$
* Isometric Matrix transformation (Without the primary view):
	$$ \begin{bmatrix}   -\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} & 0 & 0 \\  -\frac{1}{\sqrt{6}}  & -\frac{1}{\sqrt{6}} & \frac{2}{\sqrt{6}} & 0 \\ \frac{1}{\sqrt{3}} & \frac{1}{\sqrt{3}} & \frac{1}{\sqrt{3}} & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} $$
* Oblique Projections (Without the primary view):
	$$ \begin{bmatrix}   1 & 0 & -\frac{\cos\alpha}{\tan\beta} & 0\\   0 & 1 & \frac{\sin\alpha}{\tan\beta} & 0\\ 0 & 0 & -\frac{1}{\sin\beta} & 0 \\
0 & 0& 0 & 1   \end{bmatrix} $$
* Perspective Transformation (without the Primary view):
	$$ \begin{bmatrix}   1 & 0 & 0 & 0\\   0 & 1 & 0 & 0\\ 0 & 0 & 1 & 0\\ 0 & 0 & \frac{1}{z_{0}} & 1\end{bmatrix} $$
* Perspective Transformation + Frustum transformation (without primary view):
	$$ \begin{bmatrix}   \frac{2n}{r-l} & 0 & \frac{l+r}{r-l} & 0\\   0 & \frac{2n}{t-b} & \frac{b+t}{t-b} & 0\\ 0 & 0 & -\frac{n+f}{f-n} & -\frac{2nf}{f-n}\\ 0 & 0 & -1 & 0\end{bmatrix} $$
* Representation of rotation in 2D:
	We use angles to represent rotations in 2d! positive angles represent ccw and negative angles represent cw

* Representation of orientation in 2D:
	We use Euler angles in order to represent orientation in 2D
	$$x + iy = \cos\theta +i\sin\theta = e^i\theta$$
* Representation of rotation in 3D:
	$$v = \text{ Rotation Axis such that } \|v\|=\theta $$
* Representation of Orientation in 3D:
	$$e_{0} = \cos\frac{\theta}{2}$$
	$$\begin{bmatrix}
e_{1} \\ e_{2} \\ e_{3}
\end{bmatrix} = v\sin\frac{\theta}{2}$$
* Quaternions:
	$$q=w +ix + jy+ kz \text{ such that} $$
	$$w^2 + x^2 + y^2 + k^2 = 1$$
	$$i^2 = j^2 = k^2 = ijk = -1$$
	Multiplying two components with the right order gives the next component and the wrong order gives the negative next component

	$$ q_{1}q_{2}=w_{1}w_{2} - v_{1}\dot{v_{2}} , w_{1}v_{2} + w_{2}v_{1} + v_{1}xv_{2}$$
	Inverse is just -w normalized without a square
* Rotation around an arbitrary axis using quaternions:
	$$p'=qpq^-1 \text{ such that p is a normal rotation around xyz with angle |theta| and q is a quaternion representing an orientation}$$
* SLERP:
	$$ q_{1} = e^{t\log(q^-1q_{2})}$$
### [[Incidence geometry]]:
* Line Explicit representation:
	$$P(t) = o + td$$
* Plane implicit representation:
	$$ 0 = n^T(p-o)$$
* Sphere implicit representation:
	$$ \|p-c\| - r = 0$$
* Line Line intersection:
	$$v = o_{1}+td_{1} - o_{2}+sd_{2} $$
	$$d_{0}^Tv=0, d_{1}^Tv=0 $$
* Line plane intersection:
	$$ 0 = n^T(o + td - c)$$
* Line Sphere intersection:
	We can multiply both sides in order to get rid of the norm that way we have a quadratic equation
	$$ \| o + td - c\| - r = 0$$
* Or we can use Pythag to calculate the length of the "in" part of the span by projecting onto the line
	$$t_{in}^2 = r^2 - (c-o)^2 + projection_{c\to o + td}$$
* Plane Plane intersection:
	To find d we can just use the cross product of two normals
	$$d = n_{1}xn_{2}$$
	In order to find the origin point we assume o is a span of the two norms:
	$$o=an_{1} + bn_{2}$$
	Then solve that each normal is orthogonal to the center-o:
	$$n_{i}^T(an_{1}+bn_{2}-c_{i}= 0 )$$
* Barycentric coordinates:
	$$p(u,v,w) = uv_{0} + vv_{1} + wv_{2}, v+u+w=1$$
	$$p(u,v) = v(v_{2}-v_{0}) + u (v_{2}-v_{0}) + v_{0}$$
* Cramer's rule:
	$$x_{i} = \frac{\\det(A_{i=x_{i}})}{\\det (A)}$$
### [[Rasterization]]:
* Floating Bersenhams algorithm:
	$$E_{0} = \frac{\nabla y}{\nabla x} - \frac{1}{2}$$
	$$E_{i+1} = \begin{cases} E_{i}+\frac{\nabla y}{\nabla x}+1,& \text{if } E_{i}\geq0 \\ E_{i} + \frac{\nabla y}{\nabla x},& \text{if } E_{i}<0\end{cases}$$
* Integer Bersenhams algorithm:
	$$E_{0} = 2\nabla y-\nabla x$$
	$$E_{i+1} = \begin{cases} E_{i}+2\nabla y-2\nabla x,& \text{if } E_{i}\geq0 \\ E_{i} + 2\nabla y,& \text{if } E_{i}<0\end{cases}$$
* DDA:
	$$(x,ROUND(\frac{\nabla y}{\nabla x}x_{i}+b))$$
### [[Lighting and Shading]]:
* Phong Ilumination model:
	$$L_{out} = L_{ambient} + L_{in}k_{diffuse}\cos(n^Tl) + L_{in}k_{spec}\cos((2*n(n^Tl)-l)^Tv)$$
	$$\begin{cases} \text{set diffuse and specular to 0},& \text{if } \|\beta\|> \pi/2 \\ L_{spec}==value,& \text{if } \|\gamma\| < \pi/2\end{cases}$$
* Cook-Torrance:
	$$L_{out} = (\frac{k_{d}}{2}+\frac{DGF}{4\|n^Tl\|\|n^Tv\|})max(0,n^Tl)L_{in} $$
	