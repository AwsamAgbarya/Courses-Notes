---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - Subject
  - ComputerGraphics
---
Child of [[Animation]]
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Physical simulation ^EGTuJMe7

What is Physical Simulation? ^V7OR6Ora

It is the simulation of physical properties acting upon
a collection of objects and controlling the outcome of its
movement.
The end position is not specified like key-frame animation, thus
this is harder to control and requires solving some physics linear system
of equations over time in order to progress through time ^6oSkeTXQ

Examples of collections
of objects ^DCnD0gX9

Rigid Body
Collisions, Fractures etc.. ^aeVKL8i2

Particle Systems
Fire, Sprinklers, Sparks, Smoke ^h87jHnaU

Continuum Mechanics
Fluids ^QGmMHAKQ

Simple Point Dynamics ^0QR6r0HG

There often is an emitter which produces those
particles, driven by a distribution or physics law.
each particle is independent of the other and can
have different lifespans.
theyre usually rendered as screen-aligned transparent
quads. ^ZQ2cnIYK

To Understand The process of simulating physical laws we must first understand
Differential equations ^rsEKoM2z

We can encode relevant physical attributes into a vector x  ^YAwDLdq5

For particles we encode position and velocity
For rigid-bodies we encode position, momentum, and orientation ^5qtCk2Ge

Typically in order to solve differential equations and simulate physics we do numeric integration ^8ExUcaJT

Numeric Integration om a function ^YpmpnbGR

We first need to be able to describe the initial state/positions!

The next step is to be able to compute the following state given a step dt ^jA8A55CX

Definition ^eBCXbvbD

Phase space ^4fUzG59T

Phase space is a vector field describing the rate of change
as small vectors (normalized for less clutter when visualizing)
its a visual way of describing what would happen if we dropped
a point in the field and let flow according to the vector field ^XZVjlnVw

We first need to define our
function of course ^LD3TgHrR

Newtonian Mechanics ^j9Ftbw8m

Velocity is the change of position
Acceleration is the change of Velocity! ^IunQAiF5

We know F (such as gravity) and the mass describing our scene ^JoI3LHqz

Now we need to be able to compute p from our ODE ^rOLiHsbm

There are many ways to do answer this question! ^ZaZtj7MJ

Euler's Method ^mAGRmHTf

simple
approach ^HTZXtu4r

Idea: Replace dt by a very small (tweakable) step h and compute ^D4lBFbR8

This will obviously be only an approximation!
and this method is quite sensitive to h!
Problem: too big will cause explosion and inaccurate behaviour! ^bOV2UvZg

Usually forces we have
good physical models for ^r4Rrx45h

earth gravity ^5JfsrjGK

general gravity ^sOC6rlhM

Dampening ^fIyZEqjo

Spring force ^gaKvaFL3

rest state ^HC85tGXV

distance length ^di7oRK4J

Problem 2: Inaccurate behaviour! ^hZYuY3Jq

Consider the following function simulating a rotation
in a circle ^8e3CeqFO

Eulers method will Spiral outwards given enough time no matter
the value of t ^RhYkmyd8

Using the taylor expansion of this function we can see that the error
scales with h, meaning if we take 10x smaller h we will be 10 times more accurate ^6GXTfLh3

Also called First Order Method ^hj3Dd2dh

Alternative method ^1Duvmcng

Trapezoid Method ^nzoE1SIt

the function varies within each step of t
what if we can look ahead at next step of
f and compensate for the variation ^baGjBTwV

Idea: Average your first and second step
gradients in order to arrive at a better
approximation ^iJCOAVIx

This improves the approximation and scales
quadratically with the error ^Z5fFaV63

also called Second Order Method ^om5sWvvV

The problem still presists... but perhaps more accurate...
is there a way to get rid of the method?? ^5RScDtPd

So far we have only looked at one type of
equations, lets split this up into a more general sense ^WjuLSsdl

Explicit Euler Method
(Forward Euler) ^nlTh8GJO

(What we have covered so far) ^MWPWr6hu

Implicit Euler Method
(Backwards Euler) ^ZhNimlRz

This is more computationally difficult to compute
sometimes we have a closed form solution
BUT
more often than not we need an interative method for such things ^5FCqMd2H

The intuition behind this method comes from "looking ahead"
and then saying "if we were to walk backwards using the current gradient,
we would end up at the past step" ^AFH0CCIY

This still does not solve the issue of inaccuracy
as the error is still O(h)!
BUT
this allows our problem to no longer explode with varying
values of h (instead it always decays)!
because Xi is now divided by 1+h ^YquryVUd

In order to solve
this implicit equation
we can use Newtons
Method ^rPO6LcI6

Newtons Method ^gLTFjzPK

1) start from an initial x0 guess

2) Iterate over the following




3) This will converge quadratically  ^jlURFMdX

solving g(x) = 0 ^4BlapFP7

Note that if this is Multidimensional we use the
Jacobian matrix instead ^jwEY9M3R

Apply Newtons method ^AC4QXiR0

0 ^r5PanhVQ

We then update our parameter ^xdphR3BX

often one step is enough but you can iterate
multiple times for better accuracy ^5mTek0II

Rigid body Simulation ^aWzolj1E

We define points in a rigid body relative to the distance of their center of mass! ^A6w5rOlm

the bar indicating
rest state ^ujycYwzI

Under rotation and translation we can treat the points
in a body as a system of particles and we only translate the
center of mass and rotate the points around their center of mass ^V3E5hGSP

Translation ^nV7FhnHV

Rotation ^teKx00Qy

This splits up our Velocity into two components
Linear and Angular ^83LJp6BX

Linear Velocity
is the Velocity of the center of mass ^Hg0ECsfw

Angular Velocity
is the Rotation velocity of points around their COM ^YCJbvN3E

chain rule ^4TmLCOZY

derivative of
rotation matrix ^2ggLNT45

rotation by 90 ^YAl8Jsm2

Angular velocity is the change of angle! ^gFdl8vFM

How do we update Those velocities
in our simulation according to some force? ^nEGxm2Qy

We have two components to keep in mind ^3KmYmaBd

Momentum ^yxSSsWiH

Force ^QjoOdZOc

To Compute the total Linear Momentum ^oWJXHJoO

sum over 
individual
particles ^DT3xzdvk

Sum of the differences
to the center of mass
including the pass
which is exactly how we define the
center of mass!! ^I93VcHrU

The Linear dynamics of the object and the Angular
dynamics of the object!
Each of which gets a contribution from two things ^nIuMkzDH

Linear ^wTlAku18

Momentum ^P90JzOp0

Angular ^c7umexbr

Torque
(Force that affects the angular state) ^79w61s0K

Which is the projection
of the angular momentum ^IgjS9LqM

moment of inertia ^UHtGw2xB

Runge Kutta ^ijAExZTw

This is a 4th order method so the error decreases
with O(h^4) ^b2vXUhrG

Runge-Kutta methods can be used for adaptive step sizes which is
really useful for example

Runge-Kutta 45 method
Uses 4th order solution to estimate error and set step size
Then uses a 5th order solution using that 4th order step size
WHich is great because for larger curvature we preferably want less
step size for more accuracy, wheres over smooth/straight lines we can
jump further and save on computation ^inveRmbY

# Element Links
5Fx9oHhi: [[rigid_body_example.mp4]]
BwETZSjv: [[Li_et_al_2023.mp4]]
c8DXuN7T: [[particles_sprinkler2.mp4]]
rsEKoM2z: [[Differential Equations]]
jwEY9M3R: [[Partial Derivatives]]

# Embedded files
8e44a6637e7522c18661934dc1a730883c094095: [[Pasted Image 20240201165058_801.png]]
9b9bc039fe0fd1a77658a4f3c56fa11e3b2e5317: [[Pasted Image 20240201191449_966.png]]
fe314b6dad9e4af0b03d4a1b4af1d331c3be863c: [[Pasted Image 20240201191834_006.png]]
fae3c258343debeb180f3916fe5b4c652fae0874: [[Pasted Image 20240201192229_030.png]]
4f0d311613f712fc7f6c8464fafc63ea0c897936: [[Pasted Image 20240201192247_050.png]]
42336e547488d2fde4f355dec90932b63faf277f: [[Pasted Image 20240201192617_068.png]]
dedd114542fc68f93a9c6df6fcffa628f547538e: [[Pasted Image 20240201193249_098.png]]
cb5130d670dd890451811ab83a5e96ff6107dab4: [[Pasted Image 20240201193255_623.png]]
9c917631533449a7ee5a5f18a6e0024321260ee6: [[Pasted Image 20240201193340_117.png]]
46afc23e296203dad329fc78e4e49194433517d8: [[Pasted Image 20240201193442_122.png]]
04739f90e876bbed240b8d9a6c39e399f4cecb56: [[Pasted Image 20240201193446_241.png]]
c364688d263e4c4f6c0a2a7ec334601eccfbc621: [[Pasted Image 20240201193627_150.png]]
1eb8161136f55b862695b8ef773841cbd902e176: [[Pasted Image 20240201194049_195.png]]
39e2ddb70e7e985e675589657f1fea72d7c34fa8: [[Pasted Image 20240201194425_207.png]]
fe323709663af7da8e11988dd377f8a4941a67b4: [[Pasted Image 20240201194511_225.png]]
dd31d117e4334d5aee7911094659e46db358904c: [[Pasted Image 20240201194545_229.png]]
10cd23150ca7450457f970a1784a7a9d0afcb43e: [[Pasted Image 20240201195455_306.png]]
86932f4f96de3494a4bb39703b42e05eea84b2b4: [[Pasted Image 20240201195603_343.png]]
c91ab01bb82e884b3f6f5d64f38758a01774e198: [[Pasted Image 20240201195945_397.png]]
5e93f85298edf38174f7e5e681be71a8ad7a1e10: [[Pasted Image 20240201200114_410.png]]
505a7f0121d4a3d2f349a42e4376eba4a4bdcdac: [[Pasted Image 20240201200528_428.png]]
4a45eaf1ac937c7f03330aace7c77d84cf142544: [[Pasted Image 20240201200543_441.png]]
44508a81010727bb6c2e318e9d8c1f1db74fc00f: [[Pasted Image 20240201201541_522.png]]
c4792e8117d9f026398020202f30726f2b3c884b: [[Pasted Image 20240201201556_535.png]]
3d8d431145ce1be25ee445509e49fdec6015ed30: [[Pasted Image 20240201201849_571.png]]
881a2a5bbb7e159a29549c1fffdcad65d294db46: [[Pasted Image 20240201201951_590.png]]
320e0876d5ed4aec2556269073338c38f5bc631a: [[Pasted Image 20240201202021_604.png]]
667674f94ab3c8841bdc9da56f24b4065c1a759d: [[Pasted Image 20240201202106_607.png]]
bd64163a9b9a6d7c046e7a16cf0fdf41ef794f4e: [[Pasted Image 20240201202253_632.png]]
855d702d1e6150794a4a5101ce7ceebb5f203d6c: [[Pasted Image 20240201204701_750.png]]
1388f415f81089be12125b197e90932b02d8660c: [[Pasted Image 20240201204745_830.png]]
b70cc6682a7123110cc66b72494165538794866b: [[Pasted Image 20240201205120_793.png]]
b4d415efefba10b4ab943632ec053ef36ccff702: [[Pasted Image 20240201205431_818.png]]
93dd2a49513e41f987fe28e134578d2920b4e351: [[Pasted Image 20240201205555_842.png]]
30fd520c5ad0c1210b1a7ab877503fe02457f53d: [[Pasted Image 20240201205630_867.png]]
77a14e34e8a1ca6a6500af5215584b06ac1677d9: [[Pasted Image 20240201210022_926.png]]
cdd48c1a112d966f5d0e77103a9b0fb02f712460: [[Pasted Image 20240201210113_936.png]]
164f4afebfc1a35637e12e50d08da4112c764a27: [[Pasted Image 20240201210145_948.png]]
efc48163263554e28209ab02ec50894c2c8fcfa0: [[Pasted Image 20240201210300_967.png]]
2d0dc2146836f71cecdab04226eca94a8b6142e9: [[Pasted Image 20240201210551_011.png]]
fb3a54225cdf65e7ef171b55d57840fac7fe23ee: [[Pasted Image 20240201211119_093.png]]
ca3399f96d8f05129aa01f7b14f7779104425851: [[Pasted Image 20240201211234_106.png]]
4d03c16fe10c6313c99f05d602e32e7a5a2be078: [[Pasted Image 20240508200938_951.png]]
ad4c59cb1c8122d56ab21332f4fad1246a000f76: [[Pasted Image 20240508200957_962.png]]
929929208084b872a8447fffcebef941a50415f5: [[Pasted Image 20240508201012_963.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.1.6",
	"elements": [
		{
			"type": "image",
			"version": 156,
			"versionNonce": 1456428518,
			"isDeleted": false,
			"id": "7wbGjlV7D_1XnpOQG95Vz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1222.0499112859484,
			"y": 2525.453760218685,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 206.17622178840332,
			"height": 33.62009117571213,
			"seed": 909438142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c4792e8117d9f026398020202f30726f2b3c884b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 92,
			"versionNonce": 1088807802,
			"isDeleted": false,
			"id": "y_dSTiU2qVhhyO_R8p1M9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -439.08761041003964,
			"y": 1158.486601419693,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 196.85348201458058,
			"height": 145.16174033449286,
			"seed": 1108591778,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c364688d263e4c4f6c0a2a7ec334601eccfbc621",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 128,
			"versionNonce": 326609190,
			"isDeleted": false,
			"id": "PBDZJCF_j2nkAqECR9u7M",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -10.989882870786914,
			"y": -406.738711232956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 441,
			"height": 165,
			"seed": 745195682,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "EGTuJMe7"
				}
			],
			"updated": 1710511727513,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 63,
			"versionNonce": 1074750522,
			"isDeleted": false,
			"id": "EGTuJMe7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 83.36856931410279,
			"y": -341.5750206808462,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 252.44900512695312,
			"height": 35,
			"seed": 1861485922,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Physical simulation",
			"rawText": "Physical simulation",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "PBDZJCF_j2nkAqECR9u7M",
			"originalText": "Physical simulation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 180,
			"versionNonce": 372479078,
			"isDeleted": false,
			"id": "V7OR6Ora",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 25.010117129213086,
			"y": -231.738711232956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 385.86956787109375,
			"height": 35,
			"seed": 1379451682,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is Physical Simulation?",
			"rawText": "What is Physical Simulation?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is Physical Simulation?",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 460,
			"versionNonce": 1204473082,
			"isDeleted": false,
			"id": "6oSkeTXQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -138.08949224578691,
			"y": -196.738711232956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 714.19921875,
			"height": 150,
			"seed": 2132915390,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "6JC8KLC7UinOXHQroa0qs",
					"type": "arrow"
				}
			],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "It is the simulation of physical properties acting upon\na collection of objects and controlling the outcome of its\nmovement.\nThe end position is not specified like key-frame animation, thus\nthis is harder to control and requires solving some physics linear system\nof equations over time in order to progress through time",
			"rawText": "It is the simulation of physical properties acting upon\na collection of objects and controlling the outcome of its\nmovement.\nThe end position is not specified like key-frame animation, thus\nthis is harder to control and requires solving some physics linear system\nof equations over time in order to progress through time",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "It is the simulation of physical properties acting upon\na collection of objects and controlling the outcome of its\nmovement.\nThe end position is not specified like key-frame animation, thus\nthis is harder to control and requires solving some physics linear system\nof equations over time in order to progress through time",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 299,
			"versionNonce": 147855270,
			"isDeleted": false,
			"id": "mYYYbbqMk09FgOoeqlfYh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -88.24943350430908,
			"y": -170.99826186647806,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 853.5005664956909,
			"height": 65,
			"seed": 370800382,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-326.5005664956909,
					-57.25955063352194
				],
				[
					-588.5005664956909,
					-64.25955063352194
				],
				[
					-853.5005664956909,
					0.7404493664780603
				]
			]
		},
		{
			"type": "text",
			"version": 63,
			"versionNonce": 1033575866,
			"isDeleted": false,
			"id": "DCnD0gX9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1062.7617567919933,
			"y": -162.11307565789468,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 228.0197296142578,
			"height": 50,
			"seed": 1706550078,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Examples of collections\nof objects",
			"rawText": "Examples of collections\nof objects",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Examples of collections\nof objects",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 390,
			"versionNonce": 1400517350,
			"isDeleted": false,
			"id": "rFTmmaYjGaiiMW1QafSOR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1360.0731816147477,
			"y": -22.36967573115666,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 251.24057331933852,
			"height": 251.24057331933852,
			"seed": 1463925694,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8e44a6637e7522c18661934dc1a730883c094095",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "embeddable",
			"version": 349,
			"versionNonce": 1587762811,
			"isDeleted": false,
			"id": "5Fx9oHhi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1083.1391459456395,
			"y": -25.90986897861447,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 276.93403433076804,
			"height": 257.6757193682049,
			"seed": 51972,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": "[[rigid_body_example.mp4]]",
			"locked": false,
			"customData": {
				"mdProps": {
					"useObsidianDefaults": false,
					"backgroundMatchCanvas": false,
					"backgroundMatchElement": true,
					"backgroundColor": "#A5D8FF",
					"backgroundOpacity": 100,
					"borderMatchElement": true,
					"borderColor": "#1E1E1E",
					"borderOpacity": 100,
					"filenameVisible": false
				}
			},
			"scale": [
				0.5789467431972063,
				0.5789467431972063
			]
		},
		{
			"type": "embeddable",
			"version": 695,
			"versionNonce": 1354688039,
			"isDeleted": false,
			"id": "BwETZSjv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -780.5116489032384,
			"y": -22.36967577929886,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 276.9340346220864,
			"height": 256.00000024437435,
			"seed": 58711,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": "[[Li_et_al_2023.mp4]]",
			"locked": false,
			"customData": {
				"mdProps": {
					"useObsidianDefaults": false,
					"backgroundMatchCanvas": true,
					"backgroundMatchElement": false,
					"backgroundColor": "#A5D8FF",
					"backgroundOpacity": 100,
					"borderMatchElement": true,
					"borderColor": "#1E1E1E",
					"borderOpacity": 100,
					"filenameVisible": false
				}
			},
			"scale": [
				0.5789467431972063,
				0.5789467431972063
			]
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 1269200698,
			"isDeleted": false,
			"id": "aeVKL8i2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1069.8119908289098,
			"y": -85.44883710435687,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 250.27972412109375,
			"height": 50,
			"seed": 409294654,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Rigid Body\nCollisions, Fractures etc..",
			"rawText": "Rigid Body\nCollisions, Fractures etc..",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Rigid Body\nCollisions, Fractures etc..",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 25899366,
			"isDeleted": false,
			"id": "h87jHnaU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1380.3027331820267,
			"y": -85.44883739263727,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 291.6996765136719,
			"height": 50,
			"seed": 1212608894,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Particle Systems\nFire, Sprinklers, Sparks, Smoke",
			"rawText": "Particle Systems\nFire, Sprinklers, Sparks, Smoke",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Particle Systems\nFire, Sprinklers, Sparks, Smoke",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 78,
			"versionNonce": 352813050,
			"isDeleted": false,
			"id": "QGmMHAKQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -740.9645311321411,
			"y": -85.4488374744737,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 197.8397979736328,
			"height": 50,
			"seed": 1801861950,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Continuum Mechanics\nFluids",
			"rawText": "Continuum Mechanics\nFluids",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Continuum Mechanics\nFluids",
			"lineHeight": 1.25
		},
		{
			"type": "embeddable",
			"version": 316,
			"versionNonce": 1093407911,
			"isDeleted": false,
			"id": "c8DXuN7T",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1406.910012690799,
			"y": 385.88092406390666,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 342.6666666666666,
			"height": 322.66666666666663,
			"seed": 21317,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": "[[particles_sprinkler2.mp4]]",
			"locked": false,
			"customData": {
				"mdProps": {
					"useObsidianDefaults": false,
					"backgroundMatchCanvas": false,
					"backgroundMatchElement": true,
					"backgroundColor": "#fff",
					"backgroundOpacity": 60,
					"borderMatchElement": true,
					"borderColor": "#fff",
					"borderOpacity": 0,
					"filenameVisible": false
				}
			},
			"scale": [
				0.9164933755732255,
				0.9164933755732255
			]
		},
		{
			"type": "text",
			"version": 133,
			"versionNonce": 1187606714,
			"isDeleted": false,
			"id": "0QR6r0HG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1338.6665612544382,
			"y": 353.5475907305733,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 210.1797637939453,
			"height": 25,
			"seed": 266060514,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Simple Point Dynamics",
			"rawText": "Simple Point Dynamics",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Simple Point Dynamics",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 413,
			"versionNonce": 2035191782,
			"isDeleted": false,
			"id": "ZQ2cnIYK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1502.8763919233809,
			"y": 720.3115097051889,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 534.5994262695312,
			"height": 150,
			"seed": 1045470626,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "There often is an emitter which produces those\nparticles, driven by a distribution or physics law.\neach particle is independent of the other and can\nhave different lifespans.\ntheyre usually rendered as screen-aligned transparent\nquads.",
			"rawText": "There often is an emitter which produces those\nparticles, driven by a distribution or physics law.\neach particle is independent of the other and can\nhave different lifespans.\ntheyre usually rendered as screen-aligned transparent\nquads.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "There often is an emitter which produces those\nparticles, driven by a distribution or physics law.\neach particle is independent of the other and can\nhave different lifespans.\ntheyre usually rendered as screen-aligned transparent\nquads.",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 60,
			"versionNonce": 1955547514,
			"isDeleted": false,
			"id": "0duBlI0EDnnJAulvgLxKv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1234.1498958160446,
			"y": 236.64069410504754,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.777915032449073,
			"height": 112.89760456051528,
			"seed": 578564350,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727513,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.777915032449073,
					112.89760456051528
				]
			]
		},
		{
			"type": "text",
			"version": 201,
			"versionNonce": 1442816806,
			"isDeleted": false,
			"id": "rsEKoM2z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -185.75468359890522,
			"y": 29.750024783978844,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 807.399169921875,
			"height": 50,
			"seed": 1943449662,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "6JC8KLC7UinOXHQroa0qs",
					"type": "arrow"
				}
			],
			"updated": 1710511727513,
			"link": "[[Differential Equations]]",
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "To Understand The process of simulating physical laws we must first understand\nDifferential equations",
			"rawText": "To Understand The process of simulating physical laws we must first understand\nDifferential equations",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "To Understand The process of simulating physical laws we must first understand\nDifferential equations",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 41,
			"versionNonce": 1167854138,
			"isDeleted": false,
			"id": "6JC8KLC7UinOXHQroa0qs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 228.53018626293692,
			"y": -27.289163502421587,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0,
			"height": 52.36384469606983,
			"seed": 990247294,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6oSkeTXQ",
				"focus": -0.026659421863793067,
				"gap": 19.44954773053442
			},
			"endBinding": {
				"elementId": "rsEKoM2z",
				"focus": 0.026220698002275347,
				"gap": 4.675343590330598
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
					52.36384469606983
				]
			]
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 2041335398,
			"isDeleted": false,
			"id": "YAwDLdq5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -82.04954484700225,
			"y": 83.58879655931678,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 602.1193237304688,
			"height": 25,
			"seed": 1064221794,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can encode relevant physical attributes into a vector x ",
			"rawText": "We can encode relevant physical attributes into a vector x ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can encode relevant physical attributes into a vector x ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 101,
			"versionNonce": 13808378,
			"isDeleted": false,
			"id": "5qtCk2Ge",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -84.34114960748911,
			"y": 110.15686626854313,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 607.4793090820312,
			"height": 50,
			"seed": 925871166,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "For particles we encode position and velocity\nFor rigid-bodies we encode position, momentum, and orientation",
			"rawText": "For particles we encode position and velocity\nFor rigid-bodies we encode position, momentum, and orientation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "For particles we encode position and velocity\nFor rigid-bodies we encode position, momentum, and orientation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 189,
			"versionNonce": 824283558,
			"isDeleted": false,
			"id": "8ExUcaJT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -250.30156169989573,
			"y": 168.04932817563292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 947.4390869140625,
			"height": 25,
			"seed": 1997673918,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rXFVjzoxQPXMu_5yhsmYT",
					"type": "arrow"
				}
			],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Typically in order to solve differential equations and simulate physics we do numeric integration",
			"rawText": "Typically in order to solve differential equations and simulate physics we do numeric integration",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Typically in order to solve differential equations and simulate physics we do numeric integration",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 103,
			"versionNonce": 414598074,
			"isDeleted": false,
			"id": "rXFVjzoxQPXMu_5yhsmYT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 214.72707295293665,
			"y": 205.20400902252527,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.2567462363478796,
			"height": 106.38123942627374,
			"seed": 1285815138,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8ExUcaJT",
				"focus": 0.018948871140456434,
				"gap": 12.154680846892347
			},
			"endBinding": {
				"elementId": "YpmpnbGR",
				"focus": 0.0023931963794767957,
				"gap": 13.644134744810913
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
					1.2567462363478796,
					106.38123942627374
				]
			]
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 663514342,
			"isDeleted": false,
			"id": "YpmpnbGR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -18.739016616592153,
			"y": 325.2293831936099,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 469.0579833984375,
			"height": 35,
			"seed": 1075267902,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rXFVjzoxQPXMu_5yhsmYT",
					"type": "arrow"
				}
			],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Numeric Integration om a function",
			"rawText": "Numeric Integration om a function",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Numeric Integration om a function",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 205,
			"versionNonce": 929676410,
			"isDeleted": false,
			"id": "jA8A55CX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -155.46450266776435,
			"y": 378.13902879462756,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 763.0192260742188,
			"height": 75,
			"seed": 1297928510,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We first need to be able to describe the initial state/positions!\n\nThe next step is to be able to compute the following state given a step dt",
			"rawText": "We first need to be able to describe the initial state/positions!\n\nThe next step is to be able to compute the following state given a step dt",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We first need to be able to describe the initial state/positions!\n\nThe next step is to be able to compute the following state given a step dt",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 169,
			"versionNonce": 444194854,
			"isDeleted": false,
			"id": "Wn8cIU3YUtOPFEZYxgq9X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 664.1206128339184,
			"y": 443.57063553216636,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 324.53131378935564,
			"height": 0.5653855640929351,
			"seed": 1309819362,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "lUUwmJGOJFPGseapmzrXl",
				"focus": -0.04236002409937471,
				"gap": 6.655976850376419
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
					324.53131378935564,
					0.5653855640929351
				]
			]
		},
		{
			"type": "text",
			"version": 21,
			"versionNonce": 1253055802,
			"isDeleted": false,
			"id": "eBCXbvbD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 774.015972996981,
			"y": 404.451024933806,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 90.45989990234375,
			"height": 25,
			"seed": 539782178,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Definition",
			"rawText": "Definition",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Definition",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 226,
			"versionNonce": 232188774,
			"isDeleted": false,
			"id": "4fUzG59T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1148.4741911649041,
			"y": 295.6333204724187,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 123.27984619140625,
			"height": 25,
			"seed": 526067874,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Phase space",
			"rawText": "Phase space",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Phase space",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 289,
			"versionNonce": 267150842,
			"isDeleted": false,
			"id": "lUUwmJGOJFPGseapmzrXl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 995.3079034736504,
			"y": 328.8028754079323,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 421.48236319461563,
			"height": 221.9892003532568,
			"seed": 1270274238,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Wn8cIU3YUtOPFEZYxgq9X",
					"type": "arrow"
				}
			],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9b9bc039fe0fd1a77658a4f3c56fa11e3b2e5317",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 421,
			"versionNonce": 2146471590,
			"isDeleted": false,
			"id": "XZVjlnVw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 964.1045851817323,
			"y": 552.6620173818898,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 498.27294921875,
			"height": 80,
			"seed": 803115710,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Phase space is a vector field describing the rate of change\nas small vectors (normalized for less clutter when visualizing)\nits a visual way of describing what would happen if we dropped\na point in the field and let flow according to the vector field",
			"rawText": "Phase space is a vector field describing the rate of change\nas small vectors (normalized for less clutter when visualizing)\nits a visual way of describing what would happen if we dropped\na point in the field and let flow according to the vector field",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Phase space is a vector field describing the rate of change\nas small vectors (normalized for less clutter when visualizing)\nits a visual way of describing what would happen if we dropped\na point in the field and let flow according to the vector field",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 223,
			"versionNonce": 539072186,
			"isDeleted": false,
			"id": "lt848rHAOJ3TUPBzaRTw3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -227.53868765564266,
			"y": 429.42730989423313,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 284.42669240682517,
			"height": 196.43857892845472,
			"seed": 1734021246,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "j9Ftbw8m",
				"focus": -0.030007198330140275,
				"gap": 11.939234373128329
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
					-258.8487524421827,
					19.43923437312833
				],
				[
					-284.42669240682517,
					196.43857892845472
				]
			]
		},
		{
			"type": "text",
			"version": 144,
			"versionNonce": 494127590,
			"isDeleted": false,
			"id": "LD3TgHrR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -467.8739609777366,
			"y": 377.2483123663622,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 218.75244140625,
			"height": 40,
			"seed": 1386145214,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We first need to define our\nfunction of course",
			"rawText": "We first need to define our\nfunction of course",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We first need to define our\nfunction of course",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 89,
			"versionNonce": 2079502202,
			"isDeleted": false,
			"id": "j9Ftbw8m",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -651.2099479335606,
			"y": 637.8051231958161,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 278.4891357421875,
			"height": 35,
			"seed": 1925210658,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "lt848rHAOJ3TUPBzaRTw3",
					"type": "arrow"
				}
			],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Newtonian Mechanics",
			"rawText": "Newtonian Mechanics",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Newtonian Mechanics",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 155,
			"versionNonce": 1970117926,
			"isDeleted": false,
			"id": "EyVVJNYA3k5LVvoYXi6Zv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -771.8107062179575,
			"y": 672.80512304634,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 519.6906530147962,
			"height": 70.31484850138695,
			"seed": 1472675810,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fe314b6dad9e4af0b03d4a1b4af1d331c3be863c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 162,
			"versionNonce": 396537914,
			"isDeleted": false,
			"id": "IunQAiF5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -667.7233722001552,
			"y": 743.1199723476561,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 302.99261474609375,
			"height": 40,
			"seed": 224001214,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Velocity is the change of position\nAcceleration is the change of Velocity!",
			"rawText": "Velocity is the change of position\nAcceleration is the change of Velocity!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Velocity is the change of position\nAcceleration is the change of Velocity!",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 759892070,
			"isDeleted": false,
			"id": "JoI3LHqz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -766.5155628953203,
			"y": 788.5442572611717,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 500.5769958496094,
			"height": 20,
			"seed": 1559764158,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We know F (such as gravity) and the mass describing our scene",
			"rawText": "We know F (such as gravity) and the mass describing our scene",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We know F (such as gravity) and the mass describing our scene",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 1729403130,
			"isDeleted": false,
			"id": "rOLiHsbm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -724.7154378224429,
			"y": 813.9685416359941,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 416.97674560546875,
			"height": 20,
			"seed": 2001910270,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Now we need to be able to compute p from our ODE",
			"rawText": "Now we need to be able to compute p from our ODE",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Now we need to be able to compute p from our ODE",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 172,
			"versionNonce": 886639526,
			"isDeleted": false,
			"id": "yiRCaGaRSuLta5Wbj8wkW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -643.1083755659614,
			"y": 840.275901624628,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 121.89866804751124,
			"height": 60.94933402375562,
			"seed": 951201442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fae3c258343debeb180f3916fe5b4c652fae0874",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 146,
			"versionNonce": 1774938554,
			"isDeleted": false,
			"id": "0P_VX_lD6WlT6nl4RgTwu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -492.3318407900091,
			"y": 841.5768168033926,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 127.60108400675459,
			"height": 58.34750422531086,
			"seed": 302248546,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4f0d311613f712fc7f6c8464fafc63ea0c897936",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 100,
			"versionNonce": 2051319526,
			"isDeleted": false,
			"id": "ZaZtj7MJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 20.77453761314463,
			"y": 464.9660081866187,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 393.93682861328125,
			"height": 20,
			"seed": 13536610,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "There are many ways to do answer this question!",
			"rawText": "There are many ways to do answer this question!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "There are many ways to do answer this question!",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 70,
			"versionNonce": 921313914,
			"isDeleted": false,
			"id": "R5yqBvIcqc14D8oum8VnL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 216.95741905176328,
			"y": 502.16255735630466,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0.8070272547136028,
			"height": 137.19463330129486,
			"seed": 2071638590,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "mAGRmHTf",
				"focus": -0.02431029878126344,
				"gap": 14.526490584842918
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
					-0.8070272547136028,
					137.19463330129486
				]
			]
		},
		{
			"type": "text",
			"version": 40,
			"versionNonce": 505076262,
			"isDeleted": false,
			"id": "mAGRmHTf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 144.90452961946494,
			"y": 653.8836812424424,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 145.71983337402344,
			"height": 25,
			"seed": 1138129278,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "R5yqBvIcqc14D8oum8VnL",
					"type": "arrow"
				}
			],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Euler's Method",
			"rawText": "Euler's Method",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Euler's Method",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 154387258,
			"isDeleted": false,
			"id": "HTZXtu4r",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 231.9710456459601,
			"y": 542.8093689840722,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 68.80015563964844,
			"height": 40,
			"seed": 1251801982,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "simple\napproach",
			"rawText": "simple\napproach",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "simple\napproach",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 113,
			"versionNonce": 659072358,
			"isDeleted": false,
			"id": "D4lBFbR8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -45.46120801099618,
			"y": 687.9625472033241,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 523.2490844726562,
			"height": 20,
			"seed": 304148222,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Idea: Replace dt by a very small (tweakable) step h and compute",
			"rawText": "Idea: Replace dt by a very small (tweakable) step h and compute",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea: Replace dt by a very small (tweakable) step h and compute",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 180,
			"versionNonce": 1259031546,
			"isDeleted": false,
			"id": "UcbvX1daF0K8Khlye-3U-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 170.45148217044562,
			"y": 713.8319330022207,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 169.25564491999592,
			"height": 49.283261314939985,
			"seed": 181390078,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "42336e547488d2fde4f355dec90932b63faf277f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 232,
			"versionNonce": 924518566,
			"isDeleted": false,
			"id": "bOV2UvZg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -31.192017602920828,
			"y": 767.8403824198614,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 492.240966796875,
			"height": 60,
			"seed": 203912098,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This will obviously be only an approximation!\nand this method is quite sensitive to h!\nProblem: too big will cause explosion and inaccurate behaviour!",
			"rawText": "This will obviously be only an approximation!\nand this method is quite sensitive to h!\nProblem: too big will cause explosion and inaccurate behaviour!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This will obviously be only an approximation!\nand this method is quite sensitive to h!\nProblem: too big will cause explosion and inaccurate behaviour!",
			"lineHeight": 1.25
		},
		{
			"type": "freedraw",
			"version": 37,
			"versionNonce": 578010298,
			"isDeleted": false,
			"id": "AT4Xjs7dSlbJ_hiYn-9TH",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 241.12413318018554,
			"y": 749.3003839800608,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0.5608494335147327,
			"height": 8.412741502721246,
			"seed": 10523170,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.1869498111716439
				],
				[
					0.0934749055857651,
					0.5608494335147043
				],
				[
					0.0934749055857651,
					1.0282239614437003
				],
				[
					0.0934749055857651,
					1.4955984893726963
				],
				[
					0.0934749055857651,
					2.0564479228874006
				],
				[
					0.0934749055857651,
					2.4303475452305747
				],
				[
					0.0934749055857651,
					2.8977220731595708
				],
				[
					0.18694981117158704,
					3.365096601088453
				],
				[
					0.18694981117158704,
					3.738996223431627
				],
				[
					0.28042471675735214,
					4.019420940189093
				],
				[
					0.28042471675735214,
					4.393320562532153
				],
				[
					0.28042471675735214,
					4.673745279289619
				],
				[
					0.28042471675735214,
					4.954169996046971
				],
				[
					0.28042471675735214,
					5.2345947128043235
				],
				[
					0.28042471675735214,
					5.608494335147498
				],
				[
					0.28042471675735214,
					5.795444146319028
				],
				[
					0.28042471675735214,
					6.075868863076494
				],
				[
					0.28042471675735214,
					6.356293579833846
				],
				[
					0.28042471675735214,
					6.73019320217702
				],
				[
					0.28042471675735214,
					6.91714301334855
				],
				[
					0.28042471675735214,
					7.104092824520194
				],
				[
					0.28042471675735214,
					7.384517541277546
				],
				[
					0.37389962234314567,
					7.477992446863368
				],
				[
					0.37389962234314567,
					7.75841716362072
				],
				[
					0.37389962234314567,
					7.851892069206542
				],
				[
					0.4673745279289392,
					8.038841880378072
				],
				[
					0.4673745279289392,
					8.132316785963894
				],
				[
					0.4673745279289392,
					8.225791691549603
				],
				[
					0.5608494335147327,
					8.319266597135424
				],
				[
					0.5608494335147327,
					8.412741502721246
				],
				[
					0.5608494335147327,
					8.412741502721246
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 7,
			"versionNonce": 1027539942,
			"isDeleted": false,
			"id": "P15egQL9A1WH7_8njCXMX",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 241.2176080857713,
			"y": 742.5701907778838,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1174664674,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
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
			"version": 59,
			"versionNonce": 2098206074,
			"isDeleted": false,
			"id": "PRjB2WM944XQys8UUvm0Z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -775.8658370542122,
			"y": 808.0986228844642,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 45.19942064431348,
			"height": 124.71691992597607,
			"seed": 1505126690,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-45.19942064431348,
					40.177262794945364
				],
				[
					-31.80699971266506,
					124.71691992597607
				]
			]
		},
		{
			"type": "text",
			"version": 81,
			"versionNonce": 734107430,
			"isDeleted": false,
			"id": "r4Rrx45h",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -904.7785534325093,
			"y": 933.2779232097585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 190.51239013671875,
			"height": 40,
			"seed": 1544297378,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727514,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Usually forces we have\ngood physical models for",
			"rawText": "Usually forces we have\ngood physical models for",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Usually forces we have\ngood physical models for",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 196,
			"versionNonce": 472077882,
			"isDeleted": false,
			"id": "m7fJWSej_JnzeJCwe4EZJ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1087.487003083767,
			"y": 1073.1659092772422,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 73.71508097732475,
			"height": 22.594660835961605,
			"seed": 860207550,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dedd114542fc68f93a9c6df6fcffa628f547538e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 157,
			"versionNonce": 722453094,
			"isDeleted": false,
			"id": "PBuz1KzKVFP-OXmRysWjs",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1164.6080201421278,
			"y": 1095.0302003759703,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 223.17449724501282,
			"height": 123.91979407612564,
			"seed": 1938963170,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cb5130d670dd890451811ab83a5e96ff6107dab4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 18,
			"versionNonce": 546340602,
			"isDeleted": false,
			"id": "5JfsrjGK",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1098.3217045621884,
			"y": 1043.7371807011098,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 105.23225402832031,
			"height": 20,
			"seed": 1765347298,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "earth gravity",
			"rawText": "earth gravity",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "earth gravity",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 46,
			"versionNonce": 1308001702,
			"isDeleted": false,
			"id": "sOC6rlhM",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -903.416085678378,
			"y": 1040.6262097644496,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 116.73626708984375,
			"height": 20,
			"seed": 891726590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "general gravity",
			"rawText": "general gravity",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "general gravity",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 209,
			"versionNonce": 383422394,
			"isDeleted": false,
			"id": "RXmOv38S8fySekcAnf3Ro",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -961.1751657846344,
			"y": 1061.6901544059842,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 250.92025292231682,
			"height": 46.10361563725779,
			"seed": 236990562,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9c917631533449a7ee5a5f18a6e0024321260ee6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 40,
			"versionNonce": 1168302310,
			"isDeleted": false,
			"id": "VObI332cS_V91d50Kp266",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -818.4279750800367,
			"y": 988.9689633354208,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.1027228967727751,
			"height": 46.314361664458374,
			"seed": 441428030,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.1027228967727751,
					46.314361664458374
				]
			]
		},
		{
			"type": "line",
			"version": 116,
			"versionNonce": 52725882,
			"isDeleted": false,
			"id": "M7f0kTRrOwj6wRss7ApgM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -820.082059425196,
			"y": 990.62304768058,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 224.40410949326872,
			"height": 51.276614699935976,
			"seed": 1600071138,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-30.876241109638954,
					24.811265177388464
				],
				[
					-214.47960342231352,
					20.951735038683523
				],
				[
					-224.40410949326872,
					51.276614699935976
				]
			]
		},
		{
			"type": "line",
			"version": 129,
			"versionNonce": 362927142,
			"isDeleted": false,
			"id": "2nsU8RZkXZGDNgMLyzz3b",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -817.16071376749,
			"y": 991.3155808084759,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 210.49373557446245,
			"height": 50.095670693485545,
			"seed": 1186183266,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					36.307871420049196,
					23.89885207395639
				],
				[
					188.89285004607882,
					17.004952437238217
				],
				[
					210.49373557446245,
					50.095670693485545
				]
			]
		},
		{
			"type": "text",
			"version": 14,
			"versionNonce": 1831954746,
			"isDeleted": false,
			"id": "fIyZEqjo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -644.3994701500263,
			"y": 1040.4920648837324,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 76.38417053222656,
			"height": 20,
			"seed": 1356258594,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Dampening",
			"rawText": "Dampening",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Dampening",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 73,
			"versionNonce": 1205886822,
			"isDeleted": false,
			"id": "D3pRh0BEDXDiBy-bCbuju",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -640.3291297518891,
			"y": 1066.7697314833733,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 69.62226966329581,
			"height": 20.914199582650124,
			"seed": 1566111934,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "46afc23e296203dad329fc78e4e49194433517d8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 131,
			"versionNonce": 1818505722,
			"isDeleted": false,
			"id": "OBMmrfMEXxP3mVYoj81tj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -673.2050222229626,
			"y": 1088.372676059956,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 137.04488379275844,
			"height": 80.34592206673486,
			"seed": 1250224830,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "04739f90e876bbed240b8d9a6c39e399f4cecb56",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 238,
			"versionNonce": 548111014,
			"isDeleted": false,
			"id": "sxBufYs8ogC6_bIQyNWIh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -819.2347767181011,
			"y": 987.8241112459586,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 474.19714830141663,
			"height": 145.22789144256603,
			"seed": 1605497662,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					67.39857945400854,
					26.478013356932024
				],
				[
					433.2765822043401,
					13.640188699025657
				],
				[
					474.19714830141663,
					145.22789144256603
				]
			]
		},
		{
			"type": "text",
			"version": 17,
			"versionNonce": 868213434,
			"isDeleted": false,
			"id": "gaKvaFL3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -390.9337313219579,
			"y": 1133.0520026885247,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 91.79220581054688,
			"height": 20,
			"seed": 1649180286,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Spring force",
			"rawText": "Spring force",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Spring force",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 88,
			"versionNonce": 1387281894,
			"isDeleted": false,
			"id": "09i5l65sJW3zbHW6dhxWt",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -293.78969118969746,
			"y": 1233.2648415019028,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 71.12572375028896,
			"height": 41.52231947542009,
			"seed": 175177790,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					27.28796389639257,
					-26.060868904543668
				],
				[
					71.12572375028896,
					-41.52231947542009
				]
			]
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 501709690,
			"isDeleted": false,
			"id": "HC85tGXV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -216.85940026554687,
			"y": 1184.8774467726364,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 41.467529296875,
			"height": 9.48728810724585,
			"seed": 1749283454,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 7.58983048579668,
			"fontFamily": 1,
			"text": "rest state",
			"rawText": "rest state",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "rest state",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 46,
			"versionNonce": 855347494,
			"isDeleted": false,
			"id": "npTtoBqAxk-FVupzhmuai",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -315.6998062981559,
			"y": 1254.5378940177654,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 101.26421779794146,
			"height": 23.352768594219242,
			"seed": 2001045474,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					53.938695602576956,
					23.352768594219242
				],
				[
					101.26421779794146,
					16.73959518700667
				]
			]
		},
		{
			"type": "text",
			"version": 82,
			"versionNonce": 958266426,
			"isDeleted": false,
			"id": "di7oRK4J",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -213.83183712674565,
			"y": 1260.1513393486628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 46.00273132324219,
			"height": 7.773381261890162,
			"seed": 1189834082,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 6.21870500951213,
			"fontFamily": 1,
			"text": "distance length",
			"rawText": "distance length",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "distance length",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 147,
			"versionNonce": 1828355174,
			"isDeleted": false,
			"id": "1cK1hcBqOqomiW8f8BzWV",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 111.91242431584021,
			"y": 832.3966722535009,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 236.309739318825,
			"height": 248.51161914595883,
			"seed": 1378903934,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1eb8161136f55b862695b8ef773841cbd902e176",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 107,
			"versionNonce": 1397122298,
			"isDeleted": false,
			"id": "hZYuY3Jq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 99.53901930776055,
			"y": 1075.740051887723,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 261.0565490722656,
			"height": 20,
			"seed": 657998434,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Problem 2: Inaccurate behaviour!",
			"rawText": "Problem 2: Inaccurate behaviour!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Problem 2: Inaccurate behaviour!",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 188,
			"versionNonce": 913964966,
			"isDeleted": false,
			"id": "TFvNukWozKvTEy62tw7N-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 133.39909291974405,
			"y": 1147.103612228632,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 193.33640258502038,
			"height": 50.276605873173146,
			"seed": 199325154,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "39e2ddb70e7e985e675589657f1fea72d7c34fa8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 125,
			"versionNonce": 98809274,
			"isDeleted": false,
			"id": "8e3CeqFO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 23.018204104395835,
			"y": 1103.1009167252103,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 410.4969177246094,
			"height": 40,
			"seed": 1280573218,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Consider the following function simulating a rotation\nin a circle",
			"rawText": "Consider the following function simulating a rotation\nin a circle",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Consider the following function simulating a rotation\nin a circle",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 163,
			"versionNonce": 61283046,
			"isDeleted": false,
			"id": "r3iq83-0kShe6rD14U5yP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 145.4010599924004,
			"y": 1201.5693599939,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 175.86682192039308,
			"height": 52.52131333369205,
			"seed": 765884542,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fe323709663af7da8e11988dd377f8a4941a67b4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 99,
			"versionNonce": 1108930170,
			"isDeleted": false,
			"id": "TMYrp-j54gsXi-micshN0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 339.7071273314945,
			"y": 1126.4505201144368,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 131.08817594015312,
			"height": 116.8538538052375,
			"seed": 93702462,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dd31d117e4334d5aee7911094659e46db358904c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 216,
			"versionNonce": 990826022,
			"isDeleted": false,
			"id": "RhYkmyd8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -16.31405758976884,
			"y": 1248.7437783655207,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 499.29705810546875,
			"height": 40,
			"seed": 1282517438,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Eulers method will Spiral outwards given enough time no matter\nthe value of t",
			"rawText": "Eulers method will Spiral outwards given enough time no matter\nthe value of t",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Eulers method will Spiral outwards given enough time no matter\nthe value of t",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 187,
			"versionNonce": 1554583354,
			"isDeleted": false,
			"id": "6GXTfLh3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -92.61337041414623,
			"y": 1294.1831824035876,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 645.361328125,
			"height": 40,
			"seed": 1559888546,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Using the taylor expansion of this function we can see that the error\nscales with h, meaning if we take 10x smaller h we will be 10 times more accurate",
			"rawText": "Using the taylor expansion of this function we can see that the error\nscales with h, meaning if we take 10x smaller h we will be 10 times more accurate",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Using the taylor expansion of this function we can see that the error\nscales with h, meaning if we take 10x smaller h we will be 10 times more accurate",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 70,
			"versionNonce": 1771968870,
			"isDeleted": false,
			"id": "hj3Dd2dh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 76.51745913141286,
			"y": 1340.1073382764428,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 307.09967041015625,
			"height": 25,
			"seed": 1474524926,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Also called First Order Method",
			"rawText": "Also called First Order Method",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Also called First Order Method",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 53,
			"versionNonce": 435623930,
			"isDeleted": false,
			"id": "KGRbnKCx_Cupsvt5KBG7u",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 549.6176719820755,
			"y": 1222.562422981753,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 260.17046084881486,
			"height": 1.0740539966298002,
			"seed": 432348770,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "baGjBTwV",
				"focus": 0.000600156805711362,
				"gap": 11.21703101456518
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
					260.17046084881486,
					1.0740539966298002
				]
			]
		},
		{
			"type": "text",
			"version": 37,
			"versionNonce": 1990327462,
			"isDeleted": false,
			"id": "1Duvmcng",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 600.708148028614,
			"y": 1191.789451255146,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 148.976318359375,
			"height": 20,
			"seed": 236500030,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Alternative method",
			"rawText": "Alternative method",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Alternative method",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 227,
			"versionNonce": 973473978,
			"isDeleted": false,
			"id": "nzoE1SIt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1342.5737288119499,
			"y": 930.4395518913473,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 247.8010711669922,
			"height": 35,
			"seed": 433573282,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Trapezoid Method",
			"rawText": "Trapezoid Method",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Trapezoid Method",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 195,
			"versionNonce": 1472690150,
			"isDeleted": false,
			"id": "baGjBTwV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 821.0051638454557,
			"y": 1194.4177227355888,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 347.1207275390625,
			"height": 60,
			"seed": 1918633634,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "KGRbnKCx_Cupsvt5KBG7u",
					"type": "arrow"
				},
				{
					"id": "Zofz2FY8LKJvS3emCi3oM",
					"type": "arrow"
				}
			],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "the function varies within each step of t\nwhat if we can look ahead at next step of\nf and compensate for the variation",
			"rawText": "the function varies within each step of t\nwhat if we can look ahead at next step of\nf and compensate for the variation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the function varies within each step of t\nwhat if we can look ahead at next step of\nf and compensate for the variation",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 181,
			"versionNonce": 75030906,
			"isDeleted": false,
			"id": "Zofz2FY8LKJvS3emCi3oM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 963.9786905819032,
			"y": 1187.9678345858915,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 354.95181707368863,
			"height": 233.0382750392605,
			"seed": 973381218,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "baGjBTwV",
				"focus": -0.20560731985889588,
				"gap": 6.449888149697244
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
					35.60306979766483,
					-211.46065698006964
				],
				[
					354.95181707368863,
					-233.0382750392605
				]
			]
		},
		{
			"type": "image",
			"version": 97,
			"versionNonce": 2023580048,
			"isDeleted": false,
			"id": "7DN4FA_8nIZRuti06-1gF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1620.2985051263588,
			"y": 953.5838732908855,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 267.00594055248234,
			"height": 211.9822592761452,
			"seed": 941059966,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rkBnyeQYOxvFRRm5RsWwS",
					"type": "arrow"
				}
			],
			"updated": 1715191690004,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "10cd23150ca7450457f970a1784a7a9d0afcb43e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 212,
			"versionNonce": 1418895930,
			"isDeleted": false,
			"id": "tgGL_9efkM67OcQBBsjyo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1310.8234043154514,
			"y": 1047.4211217425354,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 288.1289105658803,
			"height": 88.2446093613451,
			"seed": 1896985918,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727515,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "86932f4f96de3494a4bb39703b42e05eea84b2b4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 1829451366,
			"isDeleted": false,
			"id": "iJCOAVIx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1289.4809581602867,
			"y": 986.3806691898586,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 331.8086853027344,
			"height": 60,
			"seed": 2107403326,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Idea: Average your first and second step\ngradients in order to arrive at a better\napproximation",
			"rawText": "Idea: Average your first and second step\ngradients in order to arrive at a better\napproximation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Idea: Average your first and second step\ngradients in order to arrive at a better\napproximation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 122,
			"versionNonce": 624315130,
			"isDeleted": false,
			"id": "Z5fFaV63",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1280.213418810635,
			"y": 1136.607915595032,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 342.38470458984375,
			"height": 40,
			"seed": 1624180414,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This improves the approximation and scales\nquadratically with the error",
			"rawText": "This improves the approximation and scales\nquadratically with the error",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This improves the approximation and scales\nquadratically with the error",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 677607846,
			"isDeleted": false,
			"id": "om5sWvvV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1319.6571761034656,
			"y": 1178.890418722316,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 260.5125427246094,
			"height": 20,
			"seed": 2140637282,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "also called Second Order Method",
			"rawText": "also called Second Order Method",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "also called Second Order Method",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 152,
			"versionNonce": 484891578,
			"isDeleted": false,
			"id": "5RScDtPd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1236.2128958369615,
			"y": 1200.6588874888428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 449.1689147949219,
			"height": 40,
			"seed": 893492898,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The problem still presists... but perhaps more accurate...\nis there a way to get rid of the method??",
			"rawText": "The problem still presists... but perhaps more accurate...\nis there a way to get rid of the method??",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The problem still presists... but perhaps more accurate...\nis there a way to get rid of the method??",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 69,
			"versionNonce": 777082086,
			"isDeleted": false,
			"id": "OmYcNmij8kX4Of9d-nUEq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1447.3081228606297,
			"y": 1273.6757978885385,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.265119940580007,
			"height": 165.73071221597797,
			"seed": 1332508706,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727516,
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
					-1.265119940580007,
					165.73071221597797
				]
			]
		},
		{
			"type": "text",
			"version": 122,
			"versionNonce": 432493690,
			"isDeleted": false,
			"id": "WjuLSsdl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1175.4785253207747,
			"y": 1459.1339896845068,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 540.41943359375,
			"height": 50,
			"seed": 1330830270,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "cwuAMPYz57_yZAf6wQHTg",
					"type": "arrow"
				}
			],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "So far we have only looked at one type of\nequations, lets split this up into a more general sense",
			"rawText": "So far we have only looked at one type of\nequations, lets split this up into a more general sense",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "So far we have only looked at one type of\nequations, lets split this up into a more general sense",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 162,
			"versionNonce": 1214367782,
			"isDeleted": false,
			"id": "cwuAMPYz57_yZAf6wQHTg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1440.2534153089457,
			"y": 1524.627202366279,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 277.12882868149904,
			"height": 233.32973219448036,
			"seed": 1713272290,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "WjuLSsdl",
				"focus": -0.02491902404550745,
				"gap": 15.49321268177232
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
					-37.428318816179626,
					122.63747016365164
				],
				[
					-246.07128753615848,
					127.41555341678122
				],
				[
					-277.12882868149904,
					233.32973219448036
				]
			]
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 1033549114,
			"isDeleted": false,
			"id": "nlTh8GJO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1011.7098761770517,
			"y": 1774.4583091998413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 293.27325439453125,
			"height": 70,
			"seed": 2022175358,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Explicit Euler Method\n(Forward Euler)",
			"rawText": "Explicit Euler Method\n(Forward Euler)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Explicit Euler Method\n(Forward Euler)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 105,
			"versionNonce": 109171558,
			"isDeleted": false,
			"id": "MWPWr6hu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1036.2269480361679,
			"y": 1842.7026138196832,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 247.42449951171875,
			"height": 20,
			"seed": 2092816930,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "(What we have covered so far)",
			"rawText": "(What we have covered so far)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "(What we have covered so far)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 143,
			"versionNonce": 2042887674,
			"isDeleted": false,
			"id": "6yg8ePb2IlbqAz3QnCeRu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1028.4223084753835,
			"y": 1866.773058205992,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 262.237431424433,
			"height": 54.28481860696862,
			"seed": 891609698,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c91ab01bb82e884b3f6f5d64f38758a01774e198",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 345,
			"versionNonce": 1929279142,
			"isDeleted": false,
			"id": "1bnCW631n6wR9GAF8HnUr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1439.8489736996758,
			"y": 1526.6628962111345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 337.09175122623105,
			"height": 246.93078892686117,
			"seed": 289930722,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "ZhNimlRz",
				"focus": 0.05603619898062451,
				"gap": 4.052317610613727
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
					36.100992533166846,
					122.74337461276718
				],
				[
					306.85843653191864,
					131.4076128207273
				],
				[
					337.09175122623105,
					246.93078892686117
				]
			]
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 457584314,
			"isDeleted": false,
			"id": "ZhNimlRz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1632.6516529234761,
			"y": 1777.6460027486091,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 291.6492614746094,
			"height": 70,
			"seed": 415660542,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "1bnCW631n6wR9GAF8HnUr",
					"type": "arrow"
				}
			],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Implicit Euler Method\n(Backwards Euler)",
			"rawText": "Implicit Euler Method\n(Backwards Euler)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Implicit Euler Method\n(Backwards Euler)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 106,
			"versionNonce": 1183101414,
			"isDeleted": false,
			"id": "WID00ODUe-KiFu1ZKIMjA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1615.8072053101428,
			"y": 1846.432093353955,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 327.8963549288562,
			"height": 40.68192989191765,
			"seed": 1442203746,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5e93f85298edf38174f7e5e681be71a8ad7a1e10",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 217,
			"versionNonce": 1455703930,
			"isDeleted": false,
			"id": "5FCqMd2H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1448.886623815531,
			"y": 1896.0578770960283,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 659.1793212890625,
			"height": 100,
			"seed": 407616062,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This is more computationally difficult to compute\nsometimes we have a closed form solution\nBUT\nmore often than not we need an interative method for such things",
			"rawText": "This is more computationally difficult to compute\nsometimes we have a closed form solution\nBUT\nmore often than not we need an interative method for such things",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is more computationally difficult to compute\nsometimes we have a closed form solution\nBUT\nmore often than not we need an interative method for such things",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 471958822,
			"isDeleted": false,
			"id": "AFH0CCIY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1412.4957395145475,
			"y": 2014.2943006890973,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 734.519287109375,
			"height": 75,
			"seed": 547353698,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The intuition behind this method comes from \"looking ahead\"\nand then saying \"if we were to walk backwards using the current gradient,\nwe would end up at the past step\"",
			"rawText": "The intuition behind this method comes from \"looking ahead\"\nand then saying \"if we were to walk backwards using the current gradient,\nwe would end up at the past step\"",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The intuition behind this method comes from \"looking ahead\"\nand then saying \"if we were to walk backwards using the current gradient,\nwe would end up at the past step\"",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 148,
			"versionNonce": 1417758778,
			"isDeleted": false,
			"id": "907uN-8DDZfIpy70rIxq6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1628.3236676640477,
			"y": 2118.827298882936,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 308.2871246367697,
			"height": 65.42996335503142,
			"seed": 1696859426,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "505a7f0121d4a3d2f349a42e4376eba4a4bdcdac",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 179,
			"versionNonce": 625078374,
			"isDeleted": false,
			"id": "TTnhebc12IWkj-a1hEW0w",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2047.3659232490672,
			"y": 2077.934042686778,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 327.17959421817716,
			"height": 247.43862960074844,
			"seed": 1688043262,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4a45eaf1ac937c7f03330aace7c77d84cf142544",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 276,
			"versionNonce": 1012936954,
			"isDeleted": false,
			"id": "YquryVUd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1561.4612768920256,
			"y": 2187.486657409844,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 444.8009033203125,
			"height": 120,
			"seed": 385137954,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This still does not solve the issue of inaccuracy\nas the error is still O(h)!\nBUT\nthis allows our problem to no longer explode with varying\nvalues of h (instead it always decays)!\nbecause Xi is now divided by 1+h",
			"rawText": "This still does not solve the issue of inaccuracy\nas the error is still O(h)!\nBUT\nthis allows our problem to no longer explode with varying\nvalues of h (instead it always decays)!\nbecause Xi is now divided by 1+h",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This still does not solve the issue of inaccuracy\nas the error is still O(h)!\nBUT\nthis allows our problem to no longer explode with varying\nvalues of h (instead it always decays)!\nbecause Xi is now divided by 1+h",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 148,
			"versionNonce": 1572008870,
			"isDeleted": false,
			"id": "h7yITSVK5AWfF8eSE3q61",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1776.4799285482522,
			"y": 2348.5094560874413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 3.4541689508093896,
			"height": 122.86150734723151,
			"seed": 948190498,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "AC4QXiR0",
				"focus": -0.012468633799616994,
				"gap": 15.163652849305436
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
					-3.4541689508093896,
					122.86150734723151
				]
			]
		},
		{
			"type": "text",
			"version": 126,
			"versionNonce": 1105461690,
			"isDeleted": false,
			"id": "rPO6LcI6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1579.6535485424638,
			"y": 2360.1478465420423,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 161.07237243652344,
			"height": 80,
			"seed": 1859292158,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "In order to solve\nthis implicit equation\nwe can use Newtons\nMethod",
			"rawText": "In order to solve\nthis implicit equation\nwe can use Newtons\nMethod",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "In order to solve\nthis implicit equation\nwe can use Newtons\nMethod",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 1067552486,
			"isDeleted": false,
			"id": "gLTFjzPK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1107.7667460035896,
			"y": 2382.445681017131,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 158.47984313964844,
			"height": 25,
			"seed": 682167102,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Newtons Method",
			"rawText": "Newtons Method",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Newtons Method",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 178,
			"versionNonce": 808434298,
			"isDeleted": false,
			"id": "jlURFMdX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1047.814376777405,
			"y": 2442.632668768538,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 278.38458251953125,
			"height": 160,
			"seed": 2062617058,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1) start from an initial x0 guess\n\n2) Iterate over the following\n\n\n\n\n3) This will converge quadratically ",
			"rawText": "1) start from an initial x0 guess\n\n2) Iterate over the following\n\n\n\n\n3) This will converge quadratically ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) start from an initial x0 guess\n\n2) Iterate over the following\n\n\n\n\n3) This will converge quadratically ",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 2006630950,
			"isDeleted": false,
			"id": "4BlapFP7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1108.3189250635794,
			"y": 2407.927916757051,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 153.81982421875,
			"height": 25,
			"seed": 2059206462,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "solving g(x) = 0",
			"rawText": "solving g(x) = 0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "solving g(x) = 0",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 168,
			"versionNonce": 1980128058,
			"isDeleted": false,
			"id": "-Rejw9OwNQvN2-M9R-mht",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1003.3032094422249,
			"y": 2517.7291946672144,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 139.65032659914323,
			"height": 44.36807251326946,
			"seed": 1808097250,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "hucY9lEnbxpcMrvnwt4mI",
					"type": "arrow"
				}
			],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "44508a81010727bb6c2e318e9d8c1f1db74fc00f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 101,
			"versionNonce": 411798886,
			"isDeleted": false,
			"id": "hucY9lEnbxpcMrvnwt4mI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1149.9685343582514,
			"y": 2538.01741632316,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 74.0762666858111,
			"height": 1.7778304004596066,
			"seed": 934965858,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "-Rejw9OwNQvN2-M9R-mht",
				"focus": -0.15674784289937949,
				"gap": 7.014998316883293
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
					74.0762666858111,
					1.7778304004596066
				]
			]
		},
		{
			"type": "text",
			"version": 166,
			"versionNonce": 835380218,
			"isDeleted": false,
			"id": "jwEY9M3R",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1007.8850426457393,
			"y": 2618.1462943285496,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 381.4088134765625,
			"height": 40,
			"seed": 296744354,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": "[[Partial Derivatives]]",
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Note that if this is Multidimensional we use the\nJacobian matrix instead",
			"rawText": "Note that if this is Multidimensional we use the\nJacobian matrix instead",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note that if this is Multidimensional we use the\nJacobian matrix instead",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 247,
			"versionNonce": 1338044582,
			"isDeleted": false,
			"id": "lcYOP94RnqVVAfDi9LtLx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1040.3285689917582,
			"y": 2658.9356879622947,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 326.1354277763377,
			"height": 37.89383065591733,
			"seed": 336078846,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3d8d431145ce1be25ee445509e49fdec6015ed30",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 32,
			"versionNonce": 1031820474,
			"isDeleted": false,
			"id": "FXlKGWALH4u--O5dKHL6E",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1528.6689042387752,
			"y": 2401.1086001801177,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 196.9316181079373,
			"height": 2.009506307224001,
			"seed": 1689736034,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727516,
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
					-196.9316181079373,
					-2.009506307224001
				]
			]
		},
		{
			"type": "image",
			"version": 212,
			"versionNonce": 417852390,
			"isDeleted": false,
			"id": "1BvIwqeBKvrdTjpcsOqPs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1584.7439020030463,
			"y": 2563.1702270740207,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 395.50145549591593,
			"height": 35.860184532481206,
			"seed": 1326340862,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "881a2a5bbb7e159a29549c1fffdcad65d294db46",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 148,
			"versionNonce": 986295674,
			"isDeleted": false,
			"id": "AC4QXiR0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1688.0654642156296,
			"y": 2486.5346162839783,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 170.6403350830078,
			"height": 20,
			"seed": 1932576382,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "h7yITSVK5AWfF8eSE3q61",
					"type": "arrow"
				}
			],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Apply Newtons method",
			"rawText": "Apply Newtons method",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Apply Newtons method",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 248,
			"versionNonce": 1913487142,
			"isDeleted": false,
			"id": "nSM3SGwAWym3aBljJTgwZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1647.1894711164284,
			"y": 2510.382313320208,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 250.3745391195106,
			"height": 47.38396651560831,
			"seed": 1148825662,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "320e0876d5ed4aec2556269073338c38f5bc631a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 300,
			"versionNonce": 518647354,
			"isDeleted": false,
			"id": "YbNCS2ob9QlvUPhy-sE5l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1563.6264946542203,
			"y": 2631.266936289749,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 416.10239995812447,
			"height": 57.65502715919318,
			"seed": 717734590,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "667674f94ab3c8841bdc9da56f24b4065c1a759d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 79,
			"versionNonce": 262056550,
			"isDeleted": false,
			"id": "cagZoJusiA9KENj_8a3BH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1772.489462543309,
			"y": 2600.641266081473,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 52.83688898545893,
			"height": 40.896349101738906,
			"seed": 696399714,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727516,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-52.83688898545893,
					40.896349101738906
				]
			]
		},
		{
			"type": "line",
			"version": 42,
			"versionNonce": 1053038330,
			"isDeleted": false,
			"id": "DxYCbzfhMKdsFNkcOC6gb",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1839.3564858921382,
			"y": 2599.1486985960078,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 70.15067181685208,
			"height": 43.58297057557638,
			"seed": 159479714,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-70.15067181685208,
					43.58297057557638
				]
			]
		},
		{
			"type": "line",
			"version": 15,
			"versionNonce": 275279270,
			"isDeleted": false,
			"id": "gpzoNh4eTxfQz3zNjBr-a",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1710.6971686450604,
			"y": 2596.462077122171,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 10.746485895347632,
			"height": 9.552431906975471,
			"seed": 140324258,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-10.746485895347632,
					9.552431906975471
				]
			]
		},
		{
			"type": "text",
			"version": 30,
			"versionNonce": 1524311994,
			"isDeleted": false,
			"id": "r5PanhVQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1684.5957242841205,
			"y": 2602.730860561124,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 11.008026123046875,
			"height": 20,
			"seed": 1568120894,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
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
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 61,
			"versionNonce": 832030950,
			"isDeleted": false,
			"id": "xdphR3BX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1647.932054334126,
			"y": 2695.2219260449942,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 244.89651489257812,
			"height": 20,
			"seed": 2084624382,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We then update our parameter",
			"rawText": "We then update our parameter",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We then update our parameter",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 101,
			"versionNonce": 726802554,
			"isDeleted": false,
			"id": "fCBk64LS8MRfVOpnyTHNH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1694.2243857429442,
			"y": 2721.4440180259085,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 154.39575724372992,
			"height": 26.731205731750254,
			"seed": 1878574910,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bd64163a9b9a6d7c046e7a16cf0fdf41ef794f4e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 139,
			"versionNonce": 45726758,
			"isDeleted": false,
			"id": "5mTek0II",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1598.8529535131006,
			"y": 2753.2514959758246,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 362.1767578125,
			"height": 40,
			"seed": 907972862,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "often one step is enough but you can iterate\nmultiple times for better accuracy",
			"rawText": "often one step is enough but you can iterate\nmultiple times for better accuracy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "often one step is enough but you can iterate\nmultiple times for better accuracy",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 135,
			"versionNonce": 1810628922,
			"isDeleted": false,
			"id": "Ij3HToqP2qSv8yO56V04e",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 758.222362450533,
			"y": 93.50771711584605,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1327.4185019250897,
			"height": 13.164481010827217,
			"seed": 2054140990,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727517,
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
					1327.4185019250897,
					13.164481010827217
				]
			]
		},
		{
			"type": "text",
			"version": 143,
			"versionNonce": 431703910,
			"isDeleted": false,
			"id": "aWzolj1E",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2475.5484882782252,
			"y": -232.13839722719516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 281.3731689453125,
			"height": 35,
			"seed": 1994568034,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Rigid body Simulation",
			"rawText": "Rigid body Simulation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Rigid body Simulation",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 186,
			"versionNonce": 1745603066,
			"isDeleted": false,
			"id": "A6w5rOlm",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2211.2355609240362,
			"y": -182.3865771148087,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 809.9990234375,
			"height": 25,
			"seed": 123740798,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We define points in a rigid body relative to the distance of their center of mass!",
			"rawText": "We define points in a rigid body relative to the distance of their center of mass!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We define points in a rigid body relative to the distance of their center of mass!",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 86,
			"versionNonce": 1189702310,
			"isDeleted": false,
			"id": "KMNJJrdKMMmTDrbt9cKQ7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2436.3711422059196,
			"y": -147.72564511329273,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 382.16247333408865,
			"height": 54.59463904772695,
			"seed": 931972770,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "855d702d1e6150794a4a5101ce7ceebb5f203d6c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 49,
			"versionNonce": 112491194,
			"isDeleted": false,
			"id": "e9CdG9uRN2FAwqsCSlsYZ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3042.1258324698556,
			"y": -175.9646937184158,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 389,
			"height": 299,
			"seed": 1996248802,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1388f415f81089be12125b197e90932b02d8660c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 31,
			"versionNonce": 1223763430,
			"isDeleted": false,
			"id": "KInRDWWXcD1cdGpmt0Dxu",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2413.796994627189,
			"y": -116.0182633543094,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 155.16707610179583,
			"height": 14.186704100735625,
			"seed": 1340155390,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-155.16707610179583,
					14.186704100735625
				]
			]
		},
		{
			"type": "text",
			"version": 105,
			"versionNonce": 1451823994,
			"isDeleted": false,
			"id": "ujycYwzI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2111.389858714506,
			"y": -99.17155223468586,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 172.1197967529297,
			"height": 50,
			"seed": 680551614,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "the bar indicating\nrest state",
			"rawText": "the bar indicating\nrest state",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "the bar indicating\nrest state",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 302,
			"versionNonce": 14645542,
			"isDeleted": false,
			"id": "V3E5hGSP",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2292.8927476016875,
			"y": -74.17155186322323,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 669.1192626953125,
			"height": 75,
			"seed": 1506539774,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Under rotation and translation we can treat the points\nin a body as a system of particles and we only translate the\ncenter of mass and rotate the points around their center of mass",
			"rawText": "Under rotation and translation we can treat the points\nin a body as a system of particles and we only translate the\ncenter of mass and rotate the points around their center of mass",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Under rotation and translation we can treat the points\nin a body as a system of particles and we only translate the\ncenter of mass and rotate the points around their center of mass",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 49,
			"versionNonce": 432837690,
			"isDeleted": false,
			"id": "GAzwhHFu5NCEyf8tzENfQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2427.3455135323966,
			"y": 8.189922386934143,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 415,
			"height": 80,
			"seed": 1013614782,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b70cc6682a7123110cc66b72494165538794866b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 93,
			"versionNonce": 639722598,
			"isDeleted": false,
			"id": "nV7FhnHV",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2539.698867795163,
			"y": 111.69451802559081,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 112.91987609863281,
			"height": 25,
			"seed": 1875093474,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Translation",
			"rawText": "Translation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Translation",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 34,
			"versionNonce": 1382153466,
			"isDeleted": false,
			"id": "uGEYPg7EDC2MYsgC6fsQ0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2607.107874058041,
			"y": 73.00781033767345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 5.839503047232938,
			"height": 32.117266759780364,
			"seed": 1490637950,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-5.839503047232938,
					32.117266759780364
				]
			]
		},
		{
			"type": "line",
			"version": 19,
			"versionNonce": 2055464870,
			"isDeleted": false,
			"id": "3yCjf2Lax41tLOGBWmUKT",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2736.3068789780664,
			"y": 71.54793457586533,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 26.277763712547312,
			"height": 37.95676980701313,
			"seed": 1923705186,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					26.277763712547312,
					37.95676980701313
				]
			]
		},
		{
			"type": "text",
			"version": 19,
			"versionNonce": 1305234874,
			"isDeleted": false,
			"id": "teKx00Qy",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2725.0042588212978,
			"y": 111.69451802559075,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 85.37989807128906,
			"height": 25,
			"seed": 1190749538,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Rotation",
			"rawText": "Rotation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Rotation",
			"lineHeight": 1.25
		},
		{
			"type": "freedraw",
			"version": 209,
			"versionNonce": 2117337830,
			"isDeleted": false,
			"id": "U-XNOj9Fui2Ucy6ARwpOM",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2817.703619685012,
			"y": 129.96549513853876,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 289.337800466064,
			"height": 40.24909035354699,
			"seed": 263274850,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					1.5188335982470562
				],
				[
					0,
					3.0376671964941124
				],
				[
					-0.7594167991233007,
					4.556500794741169
				],
				[
					-0.7594167991233007,
					5.315917593864697
				],
				[
					-0.7594167991233007,
					6.075334392988225
				],
				[
					-1.5188335982466015,
					6.834751192111753
				],
				[
					-2.278250397370357,
					6.834751192111753
				],
				[
					-3.0376671964941124,
					7.594167991235281
				],
				[
					-4.556500794740714,
					7.594167991235281
				],
				[
					-5.315917593864469,
					7.594167991235281
				],
				[
					-7.594167991234826,
					8.35358479035881
				],
				[
					-9.113001589482337,
					8.35358479035881
				],
				[
					-11.391251986852694,
					9.113001589482337
				],
				[
					-12.91008558509975,
					9.113001589482337
				],
				[
					-14.428919183346807,
					9.872418388605865
				],
				[
					-16.707169580717164,
					9.872418388605865
				],
				[
					-18.226003178964675,
					9.872418388605865
				],
				[
					-19.744836777211276,
					9.872418388605865
				],
				[
					-20.50425357633503,
					9.872418388605865
				],
				[
					-22.78250397370539,
					9.872418388605865
				],
				[
					-23.541920772829144,
					9.872418388605865
				],
				[
					-24.3013375719529,
					9.872418388605865
				],
				[
					-25.8201711701995,
					9.872418388605865
				],
				[
					-27.339004768447012,
					9.872418388605865
				],
				[
					-29.61725516581737,
					9.872418388605865
				],
				[
					-31.136088764064425,
					9.113001589482337
				],
				[
					-32.65492236231148,
					9.113001589482337
				],
				[
					-34.93317275968184,
					9.113001589482337
				],
				[
					-36.45200635792935,
					9.113001589482337
				],
				[
					-38.730256755299706,
					9.113001589482337
				],
				[
					-41.00850715267006,
					9.113001589482337
				],
				[
					-43.286757550040875,
					9.113001589482337
				],
				[
					-46.32442474653499,
					9.113001589482337
				],
				[
					-48.6026751439058,
					9.113001589482337
				],
				[
					-50.880925541276156,
					9.113001589482337
				],
				[
					-53.15917593864651,
					9.113001589482337
				],
				[
					-56.196843135140625,
					9.113001589482337
				],
				[
					-59.23451033163474,
					9.113001589482337
				],
				[
					-61.51276072900555,
					9.113001589482337
				],
				[
					-63.79101112637636,
					9.113001589482337
				],
				[
					-66.06926152374672,
					9.113001589482337
				],
				[
					-69.10692872024083,
					9.113001589482337
				],
				[
					-71.38517911761119,
					9.872418388605865
				],
				[
					-74.4228463141053,
					9.872418388605865
				],
				[
					-76.70109671147611,
					9.872418388605865
				],
				[
					-78.97934710884692,
					9.872418388605865
				],
				[
					-81.25759750621728,
					10.631835187729394
				],
				[
					-83.53584790358809,
					10.631835187729394
				],
				[
					-85.05468150183515,
					10.631835187729394
				],
				[
					-87.3329318992055,
					10.631835187729394
				],
				[
					-88.85176549745256,
					10.631835187729394
				],
				[
					-90.37059909569962,
					10.631835187729394
				],
				[
					-92.64884949307043,
					10.631835187729394
				],
				[
					-97.9647670869349,
					10.631835187729394
				],
				[
					-100.24301748430571,
					9.872418388605865
				],
				[
					-101.76185108255277,
					9.872418388605865
				],
				[
					-103.28068468079982,
					9.872418388605865
				],
				[
					-105.55893507817018,
					9.872418388605865
				],
				[
					-107.07776867641724,
					9.872418388605865
				],
				[
					-108.59660227466429,
					9.872418388605865
				],
				[
					-110.11543587291135,
					9.872418388605865
				],
				[
					-111.6342694711584,
					9.872418388605865
				],
				[
					-113.15310306940546,
					9.872418388605865
				],
				[
					-113.91251986852922,
					9.872418388605865
				],
				[
					-115.43135346677627,
					9.872418388605865
				],
				[
					-116.95018706502333,
					9.872418388605865
				],
				[
					-117.70960386414663,
					10.631835187729394
				],
				[
					-119.22843746239369,
					11.391251986852922
				],
				[
					-119.98785426151744,
					12.15066878597645
				],
				[
					-120.74727106064074,
					12.910085585099978
				],
				[
					-121.5066878597645,
					13.669502384223506
				],
				[
					-122.2661046588878,
					13.669502384223506
				],
				[
					-123.78493825713485,
					15.188335982470562
				],
				[
					-124.54435505625861,
					15.94775278159409
				],
				[
					-124.54435505625861,
					16.70716958071762
				],
				[
					-125.30377185538191,
					17.466586379841146
				],
				[
					-126.06318865450567,
					17.466586379841146
				],
				[
					-127.58202225275272,
					19.74483677721173
				],
				[
					-127.58202225275272,
					20.50425357633526
				],
				[
					-128.34143905187602,
					21.263670375458787
				],
				[
					-128.34143905187602,
					22.782503973705843
				],
				[
					-128.34143905187602,
					23.54192077282937
				],
				[
					-128.34143905187602,
					25.060754371076428
				],
				[
					-128.34143905187602,
					25.820171170199956
				],
				[
					-128.34143905187602,
					26.579587969323484
				],
				[
					-128.34143905187602,
					27.339004768447012
				],
				[
					-128.34143905187602,
					28.09842156757054
				],
				[
					-128.34143905187602,
					29.617255165817596
				],
				[
					-128.34143905187602,
					30.376671964941124
				],
				[
					-127.58202225275272,
					31.89550556318818
				],
				[
					-127.58202225275272,
					33.41433916143524
				],
				[
					-126.82260545362897,
					34.173755960558765
				],
				[
					-126.82260545362897,
					35.69258955880582
				],
				[
					-126.06318865450567,
					36.45200635792935
				],
				[
					-126.06318865450567,
					37.21142315705288
				],
				[
					-126.06318865450567,
					38.73025675529993
				],
				[
					-126.06318865450567,
					39.48967355442346
				],
				[
					-126.06318865450567,
					40.24909035354699
				],
				[
					-126.82260545362897,
					39.48967355442346
				],
				[
					-127.58202225275272,
					37.21142315705288
				],
				[
					-129.10085585099978,
					35.69258955880582
				],
				[
					-129.86027265012308,
					34.173755960558765
				],
				[
					-131.37910624837014,
					32.65492236231171
				],
				[
					-132.8979398466172,
					31.136088764064652
				],
				[
					-134.41677344486425,
					30.376671964941124
				],
				[
					-135.176190243988,
					28.09842156757054
				],
				[
					-135.9356070431113,
					27.339004768447012
				],
				[
					-137.45444064135836,
					25.820171170199956
				],
				[
					-138.21385744048212,
					24.3013375719529
				],
				[
					-138.97327423960542,
					23.54192077282937
				],
				[
					-139.73269103872917,
					22.782503973705843
				],
				[
					-141.25152463697623,
					21.263670375458787
				],
				[
					-141.25152463697623,
					20.50425357633526
				],
				[
					-142.01094143609953,
					19.74483677721173
				],
				[
					-142.77035823522328,
					18.985419978088203
				],
				[
					-143.52977503434659,
					18.226003178964675
				],
				[
					-143.52977503434659,
					17.466586379841146
				],
				[
					-144.28919183347034,
					17.466586379841146
				],
				[
					-145.8080254317174,
					16.70716958071762
				],
				[
					-147.32685902996445,
					16.70716958071762
				],
				[
					-148.8456926282115,
					16.70716958071762
				],
				[
					-151.12394302558187,
					16.70716958071762
				],
				[
					-153.40219342295268,
					15.94775278159409
				],
				[
					-156.4398606194468,
					15.94775278159409
				],
				[
					-157.95869421769385,
					15.94775278159409
				],
				[
					-159.4775278159409,
					15.188335982470562
				],
				[
					-160.99636141418796,
					15.188335982470562
				],
				[
					-162.51519501243502,
					15.188335982470562
				],
				[
					-164.03402861068207,
					15.188335982470562
				],
				[
					-165.55286220892913,
					15.188335982470562
				],
				[
					-167.07169580717618,
					15.188335982470562
				],
				[
					-168.59052940542324,
					15.188335982470562
				],
				[
					-169.34994620454654,
					15.188335982470562
				],
				[
					-171.62819660191735,
					15.188335982470562
				],
				[
					-172.38761340104065,
					15.188335982470562
				],
				[
					-173.1470302001644,
					15.188335982470562
				],
				[
					-174.66586379841146,
					15.188335982470562
				],
				[
					-176.94411419578182,
					15.188335982470562
				],
				[
					-181.500614990523,
					15.188335982470562
				],
				[
					-183.01944858877005,
					15.188335982470562
				],
				[
					-185.29769898614086,
					15.188335982470562
				],
				[
					-187.57594938351122,
					15.188335982470562
				],
				[
					-189.85419978088203,
					15.188335982470562
				],
				[
					-192.89186697737614,
					15.188335982470562
				],
				[
					-194.4107005756232,
					15.188335982470562
				],
				[
					-196.68895097299355,
					15.188335982470562
				],
				[
					-198.96720137036436,
					15.188335982470562
				],
				[
					-199.72661816948766,
					15.188335982470562
				],
				[
					-202.76428536598178,
					15.188335982470562
				],
				[
					-205.0425357633526,
					15.188335982470562
				],
				[
					-206.56136936159965,
					15.188335982470562
				],
				[
					-208.83961975897,
					15.188335982470562
				],
				[
					-211.87728695546411,
					15.188335982470562
				],
				[
					-214.91495415195823,
					15.188335982470562
				],
				[
					-217.19320454932904,
					15.188335982470562
				],
				[
					-219.4714549466994,
					15.188335982470562
				],
				[
					-222.5091221431935,
					15.188335982470562
				],
				[
					-224.02795574144056,
					15.94775278159409
				],
				[
					-226.30620613881138,
					15.94775278159409
				],
				[
					-228.58445653618173,
					15.94775278159409
				],
				[
					-230.86270693355254,
					15.94775278159409
				],
				[
					-232.3815405317996,
					15.94775278159409
				],
				[
					-234.65979092916996,
					15.94775278159409
				],
				[
					-238.45687492478783,
					15.94775278159409
				],
				[
					-241.49454212128194,
					15.94775278159409
				],
				[
					-243.7727925186523,
					15.94775278159409
				],
				[
					-246.0510429160231,
					15.94775278159409
				],
				[
					-248.32929331339346,
					15.94775278159409
				],
				[
					-250.60754371076428,
					15.94775278159409
				],
				[
					-252.12637730901133,
					15.94775278159409
				],
				[
					-254.4046277063817,
					15.94775278159409
				],
				[
					-255.16404450550544,
					16.70716958071762
				],
				[
					-256.6828781037525,
					16.70716958071762
				],
				[
					-258.96112850112286,
					16.70716958071762
				],
				[
					-260.4799620993699,
					16.70716958071762
				],
				[
					-262.7582124967407,
					16.70716958071762
				],
				[
					-264.2770460949878,
					16.70716958071762
				],
				[
					-267.3147132914819,
					16.70716958071762
				],
				[
					-269.59296368885225,
					16.70716958071762
				],
				[
					-271.1117972870993,
					16.70716958071762
				],
				[
					-273.3900476844701,
					16.70716958071762
				],
				[
					-274.9088812827172,
					16.70716958071762
				],
				[
					-277.9465484792113,
					16.70716958071762
				],
				[
					-280.22479887658164,
					16.70716958071762
				],
				[
					-281.7436324748287,
					16.70716958071762
				],
				[
					-283.26246607307576,
					16.70716958071762
				],
				[
					-284.7812996713228,
					16.70716958071762
				],
				[
					-285.54071647044657,
					16.70716958071762
				],
				[
					-286.30013326956987,
					15.94775278159409
				],
				[
					-287.0595500686936,
					15.188335982470562
				],
				[
					-287.0595500686936,
					14.428919183347034
				],
				[
					-287.8189668678169,
					13.669502384223506
				],
				[
					-287.8189668678169,
					12.15066878597645
				],
				[
					-288.5783836669407,
					10.631835187729394
				],
				[
					-289.337800466064,
					9.113001589482337
				],
				[
					-289.337800466064,
					8.35358479035881
				],
				[
					-289.337800466064,
					7.594167991235281
				],
				[
					-289.337800466064,
					6.834751192111753
				],
				[
					-289.337800466064,
					6.075334392988225
				],
				[
					-289.337800466064,
					5.315917593864697
				],
				[
					-289.337800466064,
					4.556500794741169
				],
				[
					-289.337800466064,
					3.7970839956176405
				],
				[
					-288.5783836669407,
					3.0376671964941124
				],
				[
					-288.5783836669407,
					2.2782503973705843
				],
				[
					-288.5783836669407,
					2.2782503973705843
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 155,
			"versionNonce": 825132666,
			"isDeleted": false,
			"id": "83LJp6BX",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2457.481152844809,
			"y": 170.60251525250516,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 465.85943603515625,
			"height": 50,
			"seed": 1528795554,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This splits up our Velocity into two components\nLinear and Angular",
			"rawText": "This splits up our Velocity into two components\nLinear and Angular",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This splits up our Velocity into two components\nLinear and Angular",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 109,
			"versionNonce": 599701030,
			"isDeleted": false,
			"id": "O3_CBWftQZ3uFyqSa-0Qj",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2637.072059272343,
			"y": 249.29668246995362,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 291.70607970219544,
			"height": 182.07157994835035,
			"seed": 1852991906,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-3.9155178483515556,
					58.7327677252743
				],
				[
					-229.05779412856964,
					62.648285573625856
				],
				[
					-291.70607970219544,
					182.07157994835035
				]
			]
		},
		{
			"type": "text",
			"version": 58,
			"versionNonce": 88844090,
			"isDeleted": false,
			"id": "Hg0ECsfw",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2137.4908334305806,
			"y": 446.05145434962253,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 372.6795959472656,
			"height": 50,
			"seed": 851475710,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Linear Velocity\nis the Velocity of the center of mass",
			"rawText": "Linear Velocity\nis the Velocity of the center of mass",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Linear Velocity\nis the Velocity of the center of mass",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 50,
			"versionNonce": 68223334,
			"isDeleted": false,
			"id": "6udG4--c5clcC9AU70bXe",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2221.6056402053114,
			"y": 499.4325076485227,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 189.824371611313,
			"height": 81.18275012307726,
			"seed": 1936882686,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b4d415efefba10b4ab943632ec053ef36ccff702",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 186,
			"versionNonce": 1116123130,
			"isDeleted": false,
			"id": "T2JVGuIdB_Q0VhbHh32NX",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2639.029818196519,
			"y": 250.27556193204148,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 297.5793564747228,
			"height": 176.19830317582293,
			"seed": 2041098530,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					42.091816869779905,
					48.94397310439527
				],
				[
					271.14961099834954,
					53.83837041483477
				],
				[
					297.5793564747228,
					176.19830317582293
				]
			]
		},
		{
			"type": "text",
			"version": 98,
			"versionNonce": 309847206,
			"isDeleted": false,
			"id": "YCJbvN3E",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2678.5494822884298,
			"y": 439.1992981150072,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 516.119384765625,
			"height": 50,
			"seed": 325828194,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Angular Velocity\nis the Rotation velocity of points around their COM",
			"rawText": "Angular Velocity\nis the Rotation velocity of points around their COM",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Angular Velocity\nis the Rotation velocity of points around their COM",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 88,
			"versionNonce": 1558356154,
			"isDeleted": false,
			"id": "K1kXg9F7XQQNojNTIy4ri",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2868.4735918025226,
			"y": 490.57278474161365,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 140.04278602624078,
			"height": 82.16796118886576,
			"seed": 1124378530,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "93dd2a49513e41f987fe28e134578d2920b4e351",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 167,
			"versionNonce": 1352687590,
			"isDeleted": false,
			"id": "635Wreof64BONrAboxUvz",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2614.780211842493,
			"y": 590.099378855032,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 748.4112287477363,
			"height": 320.05621665929874,
			"seed": 1798250338,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "30fd520c5ad0c1210b1a7ab877503fe02457f53d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 30,
			"versionNonce": 1342339450,
			"isDeleted": false,
			"id": "6uT93YrWJDCbTkpyKdySa",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3003.0582465742123,
			"y": 593.9993610650108,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 68.81016212036866,
			"height": 34.40508106018433,
			"seed": 1682372898,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					39.78087497583829,
					-26.34139018670362
				],
				[
					68.81016212036866,
					-34.40508106018433
				]
			]
		},
		{
			"type": "text",
			"version": 68,
			"versionNonce": 43479846,
			"isDeleted": false,
			"id": "4TmLCOZY",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3085.4512079651736,
			"y": 539.7190115328973,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 74.51216125488281,
			"height": 20,
			"seed": 1376262398,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "chain rule",
			"rawText": "chain rule",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "chain rule",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 37,
			"versionNonce": 724122170,
			"isDeleted": false,
			"id": "f1D5dvFp9yvfG7Czliqr7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3116.680649143095,
			"y": 644.8581839343938,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 99.30983121468353,
			"height": 38.94503184889561,
			"seed": 1558999266,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					53.22487686015711,
					-35.05052866400604
				],
				[
					99.30983121468353,
					-38.94503184889561
				]
			]
		},
		{
			"type": "text",
			"version": 62,
			"versionNonce": 1657413222,
			"isDeleted": false,
			"id": "2ggLNT45",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3214.9300499243595,
			"y": 581.7043781988265,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 121.55229187011719,
			"height": 40,
			"seed": 1138342946,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "derivative of\nrotation matrix",
			"rawText": "derivative of\nrotation matrix",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "derivative of\nrotation matrix",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 34,
			"versionNonce": 490332922,
			"isDeleted": false,
			"id": "Y-8GUZf8vVK136IqIPP21",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2930.4354471451315,
			"y": 801.5188833395573,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 103.4677349191702,
			"height": 17.994388681594728,
			"seed": 1544119038,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-72.53987937267902,
					-12.371142218596333
				],
				[
					-103.4677349191702,
					5.623246462998395
				]
			]
		},
		{
			"type": "text",
			"version": 17,
			"versionNonce": 1443193254,
			"isDeleted": false,
			"id": "YAl8Jsm2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2751.7378425269076,
			"y": 817.8262980822526,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 116.72026062011719,
			"height": 20,
			"seed": 1615776738,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727517,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "rotation by 90",
			"rawText": "rotation by 90",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "rotation by 90",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 72,
			"versionNonce": 12022714,
			"isDeleted": false,
			"id": "gFdl8vFM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2772.580168762873,
			"y": 921.8563576477229,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 312.33660888671875,
			"height": 20,
			"seed": 1275109182,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Angular velocity is the change of angle!",
			"rawText": "Angular velocity is the change of angle!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Angular velocity is the change of angle!",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 49,
			"versionNonce": 527842534,
			"isDeleted": false,
			"id": "7wAHL__1fOZ7IVwIzzrQM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3452.9812136884398,
			"y": 607.1884640445684,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 393.68285672978936,
			"height": 7.600055149223749,
			"seed": 1584129954,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727518,
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
					393.68285672978936,
					7.600055149223749
				]
			]
		},
		{
			"type": "text",
			"version": 124,
			"versionNonce": 1740958842,
			"isDeleted": false,
			"id": "nEGxm2Qy",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3474.709575423293,
			"y": 553.6070380655921,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 331.648681640625,
			"height": 40,
			"seed": 155012862,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "How do we update Those velocities\nin our simulation according to some force?",
			"rawText": "How do we update Those velocities\nin our simulation according to some force?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we update Those velocities\nin our simulation according to some force?",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 111,
			"versionNonce": 346664998,
			"isDeleted": false,
			"id": "Zf5EOpJ0vtW9PxHu2cX9t",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3410.7075104244764,
			"y": 647.5350199274476,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 471.4755895010668,
			"height": 60.751810541437024,
			"seed": 1951442878,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "77a14e34e8a1ca6a6500af5215584b06ac1677d9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 170,
			"versionNonce": 673533242,
			"isDeleted": false,
			"id": "3KmYmaBd",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3883.8394738298425,
			"y": 555.2209877093486,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 396.8795166015625,
			"height": 25,
			"seed": 1278601442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We have two components to keep in mind",
			"rawText": "We have two components to keep in mind",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We have two components to keep in mind",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 101,
			"versionNonce": 1368177510,
			"isDeleted": false,
			"id": "RRxtoLb3oOC_3mq0itpJe",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4090.227089611374,
			"y": 653.763677902293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 177.88662304514173,
			"height": 207.14429130914527,
			"seed": 974971042,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					7.0218403833609955,
					111.17913940321353
				],
				[
					-148.62895478113796,
					150.96956824225845
				],
				[
					-170.86478266178074,
					207.14429130914527
				]
			]
		},
		{
			"type": "image",
			"version": 76,
			"versionNonce": 1731958266,
			"isDeleted": false,
			"id": "psmBVPVZ3jGK-KPEfHNyQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3809.1308954052774,
			"y": 902.3762341085824,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 218.12220962751138,
			"height": 80.07983220590452,
			"seed": 761735522,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cdd48c1a112d966f5d0e77103a9b0fb02f712460",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 64,
			"versionNonce": 1819041446,
			"isDeleted": false,
			"id": "yxSSsWiH",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3873.202657625466,
			"y": 872.6110365170398,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 94.659912109375,
			"height": 25,
			"seed": 1701128254,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Momentum",
			"rawText": "Momentum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Momentum",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 192,
			"versionNonce": 638240442,
			"isDeleted": false,
			"id": "B-p1RG5A8NH4odZEGKF6Z",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4091.3973963419344,
			"y": 653.763677902293,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 268.0002412982726,
			"height": 184.9084634285025,
			"seed": 630068642,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					55.00441633632681,
					101.81668555873239
				],
				[
					238.74257303426975,
					105.32760575041289
				],
				[
					268.0002412982726,
					184.9084634285025
				]
			]
		},
		{
			"type": "text",
			"version": 37,
			"versionNonce": 703961574,
			"isDeleted": false,
			"id": "QjoOdZOc",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4333.327660833567,
			"y": 856.2267422891978,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 52.13995361328125,
			"height": 25,
			"seed": 934935522,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Force",
			"rawText": "Force",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Force",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 156,
			"versionNonce": 1295376250,
			"isDeleted": false,
			"id": "iakFg3GmdymFbYeUqOmFQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4228.348842001809,
			"y": 890.9222345674743,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 275.28310172610145,
			"height": 68.99678764490523,
			"seed": 251579426,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "164f4afebfc1a35637e12e50d08da4112c764a27",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 96,
			"versionNonce": 825584934,
			"isDeleted": false,
			"id": "oWJXHJoO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3732.93557414389,
			"y": 979.9351547506982,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 394.87957763671875,
			"height": 25,
			"seed": 218056830,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "To Compute the total Linear Momentum",
			"rawText": "To Compute the total Linear Momentum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "To Compute the total Linear Momentum",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 170,
			"versionNonce": 956293178,
			"isDeleted": false,
			"id": "2u97J0dZcyuAvkeBImvNV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3784.0142969936483,
			"y": 1037.28562513564,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 334.27998291830465,
			"height": 287.5752443316027,
			"seed": 1595372286,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "efc48163263554e28209ab02ec50894c2c8fcfa0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 75,
			"versionNonce": 1066981478,
			"isDeleted": false,
			"id": "SRcnSodQ9AyiOraCjiHXZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3888.92353496623,
			"y": 1049.8994905577158,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 173.28754774038543,
			"height": 24.292646879493304,
			"seed": 1715983458,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-38.05848011120588,
					-24.292646879493304
				],
				[
					-173.28754774038543,
					-3.2390195839325315
				]
			]
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 1162594554,
			"isDeleted": false,
			"id": "DT3xzdvk",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3621.095138385039,
			"y": 1011.8410104465097,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 95.95988464355469,
			"height": 75,
			"seed": 709340322,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "sum over \nindividual\nparticles",
			"rawText": "sum over \nindividual\nparticles",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "sum over \nindividual\nparticles",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 69,
			"versionNonce": 1559026598,
			"isDeleted": false,
			"id": "-A1nepSsVrwtCYzHn1Ntz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4051.733178302198,
			"y": 1215.0280007929803,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 147.62378840334895,
			"height": 46.52010138761011,
			"seed": 637363326,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					57.06465770213481,
					46.52010138761011
				],
				[
					147.62378840334895,
					37.52621511933876
				]
			]
		},
		{
			"type": "text",
			"version": 225,
			"versionNonce": 1503435194,
			"isDeleted": false,
			"id": "I93VcHrU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4148.259989852705,
			"y": 1202.4982746639232,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 270.5445556640625,
			"height": 100,
			"seed": 570585058,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Sum of the differences\nto the center of mass\nincluding the pass\nwhich is exactly how we define the\ncenter of mass!!",
			"rawText": "Sum of the differences\nto the center of mass\nincluding the pass\nwhich is exactly how we define the\ncenter of mass!!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Sum of the differences\nto the center of mass\nincluding the pass\nwhich is exactly how we define the\ncenter of mass!!",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 117,
			"versionNonce": 257849062,
			"isDeleted": false,
			"id": "5j8ab0G1pZ6xETSkjrp4e",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4210.793457333254,
			"y": 958.9605898489883,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 302.2026116486776,
			"height": 221.54886685940943,
			"seed": 1343344802,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2d0dc2146836f71cecdab04226eca94a8b6142e9",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 1964331642,
			"isDeleted": false,
			"id": "nIuMkzDH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 3881.3073949558093,
			"y": 584.314540637698,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 405.6648254394531,
			"height": 60,
			"seed": 1815153506,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The Linear dynamics of the object and the Angular\ndynamics of the object!\nEach of which gets a contribution from two things",
			"rawText": "The Linear dynamics of the object and the Angular\ndynamics of the object!\nEach of which gets a contribution from two things",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The Linear dynamics of the object and the Angular\ndynamics of the object!\nEach of which gets a contribution from two things",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 16,
			"versionNonce": 259697190,
			"isDeleted": false,
			"id": "wTlAku18",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4103.163667989676,
			"y": 791.3027584477378,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 82.0123291015625,
			"height": 35,
			"seed": 692339710,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 28,
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
			"type": "line",
			"version": 582,
			"versionNonce": 981005114,
			"isDeleted": false,
			"id": "762BKQ_vvNN3rjcfdtLCE",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4410.523168652558,
			"y": 579.1780777939,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 982.4699810099874,
			"height": 311.9137751839081,
			"seed": 1855915454,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					420.55789912437103,
					0
				],
				[
					632.0050650730118,
					80.60693066550436
				],
				[
					667.0515566667109,
					210.2789495621853
				],
				[
					932.2366763923546,
					204.43786762990226
				],
				[
					982.4699810099874,
					311.9137751839081
				]
			]
		},
		{
			"type": "line",
			"version": 236,
			"versionNonce": 2083419494,
			"isDeleted": false,
			"id": "O9AWCny_uUKO-MXvj7fEq",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5056.546830363049,
			"y": 714.6911786228637,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 262.84868695273144,
			"height": 198.59678569761945,
			"seed": 757646398,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-10.513947478109003,
					94.62552730298341
				],
				[
					-239.4843592235993,
					108.64412394046235
				],
				[
					-262.84868695273144,
					198.59678569761945
				]
			]
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 2083159034,
			"isDeleted": false,
			"id": "P90JzOp0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4747.983559987171,
			"y": 922.6366001962832,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 94.659912109375,
			"height": 25,
			"seed": 1789236322,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Momentum",
			"rawText": "Momentum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Momentum",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 12,
			"versionNonce": 247912614,
			"isDeleted": false,
			"id": "c7umexbr",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5032.51938804527,
			"y": 838.194981133088,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 99.45640563964844,
			"height": 35,
			"seed": 1882770722,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Angular",
			"rawText": "Angular",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Angular",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 70,
			"versionNonce": 1210903738,
			"isDeleted": false,
			"id": "79w61s0K",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 5194.966370564302,
			"y": 901.9436585004878,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 400.0595703125,
			"height": 50,
			"seed": 915933374,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Torque\n(Force that affects the angular state)",
			"rawText": "Torque\n(Force that affects the angular state)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Torque\n(Force that affects the angular state)",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 89,
			"versionNonce": 1324405734,
			"isDeleted": false,
			"id": "vwa0bwhiPIYX0hk9RoBXv",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4990.888636322088,
			"y": 885.0554160921245,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 185.30655389862662,
			"height": 157.46492880548325,
			"seed": 2049229026,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fb3a54225cdf65e7ef171b55d57840fac7fe23ee",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 1948468602,
			"isDeleted": false,
			"id": "IgjS9LqM",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4976.538162518057,
			"y": 1052.1778416614934,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 196.9444122314453,
			"height": 40,
			"seed": 467491426,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Which is the projection\nof the angular momentum",
			"rawText": "Which is the projection\nof the angular momentum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Which is the projection\nof the angular momentum",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 65,
			"versionNonce": 1186555686,
			"isDeleted": false,
			"id": "Ef-7qTGw4yONHypDp5mRV",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4705.964542952494,
			"y": 957.4095548254397,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 247.95701966092818,
			"height": 266.47911028620234,
			"seed": 257197246,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ca3399f96d8f05129aa01f7b14f7779104425851",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 32,
			"versionNonce": 693143098,
			"isDeleted": false,
			"id": "x98zRfpjx2xHU_jQzm8I0",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4814.252596170034,
			"y": 1215.670632974247,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 49.02125322413485,
			"height": 18.609920205458593,
			"seed": 49446178,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					49.02125322413485,
					18.609920205458593
				]
			]
		},
		{
			"type": "text",
			"version": 22,
			"versionNonce": 915247718,
			"isDeleted": false,
			"id": "UHtGw2xB",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 4794.8497008345985,
			"y": 1234.2805531797055,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 136.84829711914062,
			"height": 20,
			"seed": 1535571362,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1710511727518,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "moment of inertia",
			"rawText": "moment of inertia",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "moment of inertia",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 85,
			"versionNonce": 948851600,
			"isDeleted": false,
			"id": "rkBnyeQYOxvFRRm5RsWwS",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1910.9767352610204,
			"y": 1048.1583531557483,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 244.70588235294122,
			"height": 2.352941176470722,
			"seed": 1837841776,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1715191690004,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "7DN4FA_8nIZRuti06-1gF",
				"focus": -0.120512449310094,
				"gap": 23.67228958217936
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
					244.70588235294122,
					2.352941176470722
				]
			]
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 1328079248,
			"isDeleted": false,
			"id": "ijAExZTw",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2324.0836372198896,
			"y": 936.0838727439836,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 174.6927490234375,
			"height": 35,
			"seed": 364789136,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715191702739,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Runge Kutta",
			"rawText": "Runge Kutta",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Runge Kutta",
			"lineHeight": 1.25
		},
		{
			"type": "image",
			"version": 169,
			"versionNonce": 244440432,
			"isDeleted": false,
			"id": "KYVRhUaJgTjT3Y8VNuZGp",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2561.223275226167,
			"y": 966.1277304055095,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 270.089502270414,
			"height": 209.28577103789547,
			"seed": 1934009200,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715191797527,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4d03c16fe10c6313c99f05d602e32e7a5a2be078",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 133,
			"versionNonce": 1017016176,
			"isDeleted": false,
			"id": "8b3D1fgKOpfcQMDbt1Y-1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2288.393397327881,
			"y": 993.7661729456572,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 261.6091205554873,
			"height": 154.17857104902433,
			"seed": 211905424,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715191796043,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ad4c59cb1c8122d56ab21332f4fad1246a000f76",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 136,
			"versionNonce": 466458992,
			"isDeleted": false,
			"id": "H8550k_PV-cVboCAD4gaD",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2214.2995654186943,
			"y": 1144.7691899644874,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 371.20972033874887,
			"height": 44.40546385772667,
			"seed": 1787393904,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715191817450,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "929929208084b872a8447fffcebef941a50415f5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 91,
			"versionNonce": 770192784,
			"isDeleted": false,
			"id": "b2vXUhrG",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2166.4513414952203,
			"y": 1209.190294961116,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 511.37939453125,
			"height": 50,
			"seed": 891866992,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1715191861047,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "This is a 4th order method so the error decreases\nwith O(h^4)",
			"rawText": "This is a 4th order method so the error decreases\nwith O(h^4)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is a 4th order method so the error decreases\nwith O(h^4)",
			"lineHeight": 1.25
		},
		{
			"id": "inveRmbY",
			"type": "text",
			"x": 2083.874033238647,
			"y": 1285.4786145936564,
			"width": 702.1792602539062,
			"height": 225,
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
			"seed": 1862047632,
			"version": 401,
			"versionNonce": 124333456,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1715192296963,
			"link": null,
			"locked": false,
			"text": "Runge-Kutta methods can be used for adaptive step sizes which is\nreally useful for example\n\nRunge-Kutta 45 method\nUses 4th order solution to estimate error and set step size\nThen uses a 5th order solution using that 4th order step size\nWHich is great because for larger curvature we preferably want less\nstep size for more accuracy, wheres over smooth/straight lines we can\njump further and save on computation",
			"rawText": "Runge-Kutta methods can be used for adaptive step sizes which is\nreally useful for example\n\nRunge-Kutta 45 method\nUses 4th order solution to estimate error and set step size\nThen uses a 5th order solution using that 4th order step size\nWHich is great because for larger curvature we preferably want less\nstep size for more accuracy, wheres over smooth/straight lines we can\njump further and save on computation",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Runge-Kutta methods can be used for adaptive step sizes which is\nreally useful for example\n\nRunge-Kutta 45 method\nUses 4th order solution to estimate error and set step size\nThen uses a 5th order solution using that 4th order step size\nWHich is great because for larger curvature we preferably want less\nstep size for more accuracy, wheres over smooth/straight lines we can\njump further and save on computation",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#a5d8ff",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 0,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": -1207.1858855878222,
		"scrollY": -428.53417014921223,
		"zoom": {
			"value": 0.7200000000000002
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