---

excalidraw-plugin: parsed
tags: [excalidraw]

---
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

%%***>>>text element-link:[[Differential Equations]]<<<***%%To Understand The process of simulating physical laws we must first understand
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

%%***>>>text element-link:[[Partial Derivatives]]<<<***%%Note that if this is Multidimensional we use the
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

[[rigid_body_example.mp4]] ^5Fx9oHhi

[[Li_et_al_2023.mp4]] ^BwETZSjv

[[particles_sprinkler2.mp4]] ^c8DXuN7T


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

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.18",
	"elements": [
		{
			"id": "7wbGjlV7D_1XnpOQG95Vz",
			"type": "image",
			"x": 1222.0499112859484,
			"y": 2525.453760218685,
			"width": 206.17622178840332,
			"height": 33.62009117571213,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 909438142,
			"version": 155,
			"versionNonce": 1854891298,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018374,
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
			"id": "y_dSTiU2qVhhyO_R8p1M9",
			"type": "image",
			"x": -439.08761041003964,
			"y": 1158.486601419693,
			"width": 196.85348201458058,
			"height": 145.16174033449286,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1108591778,
			"version": 91,
			"versionNonce": 274626046,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018374,
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
			"version": 127,
			"versionNonce": 57307362,
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
			"updated": 1706818018374,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 62,
			"versionNonce": 324732478,
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
			"updated": 1706818018374,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 179,
			"versionNonce": 678298786,
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
			"updated": 1706818018374,
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
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 459,
			"versionNonce": 1625001598,
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
			"updated": 1706818018374,
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
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "line",
			"version": 298,
			"versionNonce": 1464410210,
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
			"updated": 1706818018374,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
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
			"version": 62,
			"versionNonce": 1973489342,
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
			"updated": 1706818018374,
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
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 389,
			"versionNonce": 2076886050,
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
			"updated": 1706818018374,
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
			"version": 347,
			"versionNonce": 239896318,
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
			"updated": 1706818018374,
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
			"version": 693,
			"versionNonce": 803336162,
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
			"updated": 1706818018374,
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
			"version": 87,
			"versionNonce": 727643966,
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
			"updated": 1706818018374,
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
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 87,
			"versionNonce": 2006819746,
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
			"updated": 1706818018374,
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
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 77,
			"versionNonce": 356081534,
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
			"updated": 1706818018374,
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
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"id": "c8DXuN7T",
			"type": "embeddable",
			"x": -1406.910012690799,
			"y": 385.88092406390666,
			"width": 342.6666666666666,
			"height": 322.66666666666663,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"roundness": null,
			"seed": 21317,
			"version": 314,
			"versionNonce": 2100092770,
			"updated": 1706818018374,
			"isDeleted": false,
			"groupIds": [],
			"boundElements": [],
			"link": "[[particles_sprinkler2.mp4]]",
			"locked": false,
			"scale": [
				0.9164933755732255,
				0.9164933755732255
			],
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
			}
		},
		{
			"id": "0QR6r0HG",
			"type": "text",
			"x": -1338.6665612544382,
			"y": 353.5475907305733,
			"width": 210.1797637939453,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 266060514,
			"version": 132,
			"versionNonce": 1612496830,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018374,
			"link": null,
			"locked": false,
			"text": "Simple Point Dynamics",
			"rawText": "Simple Point Dynamics",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Simple Point Dynamics",
			"lineHeight": 1.25
		},
		{
			"id": "ZQ2cnIYK",
			"type": "text",
			"x": -1502.8763919233809,
			"y": 720.3115097051889,
			"width": 534.5994262695312,
			"height": 150,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1045470626,
			"version": 412,
			"versionNonce": 1289659170,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "There often is an emitter which produces those\nparticles, driven by a distribution or physics law.\neach particle is independent of the other and can\nhave different lifespans.\ntheyre usually rendered as screen-aligned transparent\nquads.",
			"rawText": "There often is an emitter which produces those\nparticles, driven by a distribution or physics law.\neach particle is independent of the other and can\nhave different lifespans.\ntheyre usually rendered as screen-aligned transparent\nquads.",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 143,
			"containerId": null,
			"originalText": "There often is an emitter which produces those\nparticles, driven by a distribution or physics law.\neach particle is independent of the other and can\nhave different lifespans.\ntheyre usually rendered as screen-aligned transparent\nquads.",
			"lineHeight": 1.25
		},
		{
			"id": "0duBlI0EDnnJAulvgLxKv",
			"type": "line",
			"x": -1234.1498958160446,
			"y": 236.64069410504754,
			"width": 1.777915032449073,
			"height": 112.89760456051528,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 578564350,
			"version": 59,
			"versionNonce": 1881806846,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.777915032449073,
					112.89760456051528
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "rsEKoM2z",
			"type": "text",
			"x": -185.75468359890522,
			"y": 29.750024783978844,
			"width": 807.399169921875,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1943449662,
			"version": 200,
			"versionNonce": 287436514,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "6JC8KLC7UinOXHQroa0qs",
					"type": "arrow"
				}
			],
			"updated": 1706818018375,
			"link": "[[Differential Equations]]",
			"locked": false,
			"text": "To Understand The process of simulating physical laws we must first understand\nDifferential equations",
			"rawText": "To Understand The process of simulating physical laws we must first understand\nDifferential equations",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "To Understand The process of simulating physical laws we must first understand\nDifferential equations",
			"lineHeight": 1.25
		},
		{
			"id": "6JC8KLC7UinOXHQroa0qs",
			"type": "arrow",
			"x": 228.53018626293692,
			"y": -27.289163502421587,
			"width": 0,
			"height": 52.36384469606983,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 990247294,
			"version": 40,
			"versionNonce": 2103601214,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					52.36384469606983
				]
			],
			"lastCommittedPoint": null,
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
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "YAwDLdq5",
			"type": "text",
			"x": -82.04954484700225,
			"y": 83.58879655931678,
			"width": 602.1193237304688,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1064221794,
			"version": 129,
			"versionNonce": 1317388962,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "We can encode relevant physical attributes into a vector x ",
			"rawText": "We can encode relevant physical attributes into a vector x ",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "We can encode relevant physical attributes into a vector x ",
			"lineHeight": 1.25
		},
		{
			"id": "5qtCk2Ge",
			"type": "text",
			"x": -84.34114960748911,
			"y": 110.15686626854313,
			"width": 607.4793090820312,
			"height": 50,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 925871166,
			"version": 100,
			"versionNonce": 396800126,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "For particles we encode position and velocity\nFor rigid-bodies we encode position, momentum, and orientation",
			"rawText": "For particles we encode position and velocity\nFor rigid-bodies we encode position, momentum, and orientation",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "For particles we encode position and velocity\nFor rigid-bodies we encode position, momentum, and orientation",
			"lineHeight": 1.25
		},
		{
			"id": "8ExUcaJT",
			"type": "text",
			"x": -250.30156169989573,
			"y": 168.04932817563292,
			"width": 947.4390869140625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1997673918,
			"version": 188,
			"versionNonce": 532225634,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "rXFVjzoxQPXMu_5yhsmYT",
					"type": "arrow"
				}
			],
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "Typically in order to solve differential equations and simulate physics we do numeric integration",
			"rawText": "Typically in order to solve differential equations and simulate physics we do numeric integration",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Typically in order to solve differential equations and simulate physics we do numeric integration",
			"lineHeight": 1.25
		},
		{
			"id": "rXFVjzoxQPXMu_5yhsmYT",
			"type": "arrow",
			"x": 214.72707295293665,
			"y": 205.20400902252527,
			"width": 1.2567462363478796,
			"height": 106.38123942627374,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1285815138,
			"version": 102,
			"versionNonce": 716697790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.2567462363478796,
					106.38123942627374
				]
			],
			"lastCommittedPoint": null,
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
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "YpmpnbGR",
			"type": "text",
			"x": -18.739016616592153,
			"y": 325.2293831936099,
			"width": 469.0579833984375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1075267902,
			"version": 54,
			"versionNonce": 1904935458,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "rXFVjzoxQPXMu_5yhsmYT",
					"type": "arrow"
				}
			],
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "Numeric Integration om a function",
			"rawText": "Numeric Integration om a function",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Numeric Integration om a function",
			"lineHeight": 1.25
		},
		{
			"id": "jA8A55CX",
			"type": "text",
			"x": -155.46450266776435,
			"y": 378.13902879462756,
			"width": 763.0192260742188,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1297928510,
			"version": 204,
			"versionNonce": 37169406,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "We first need to be able to describe the initial state/positions!\n\nThe next step is to be able to compute the following state given a step dt",
			"rawText": "We first need to be able to describe the initial state/positions!\n\nThe next step is to be able to compute the following state given a step dt",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "We first need to be able to describe the initial state/positions!\n\nThe next step is to be able to compute the following state given a step dt",
			"lineHeight": 1.25
		},
		{
			"id": "Wn8cIU3YUtOPFEZYxgq9X",
			"type": "arrow",
			"x": 664.1206128339184,
			"y": 443.57063553216636,
			"width": 324.53131378935564,
			"height": 0.5653855640929351,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1309819362,
			"version": 168,
			"versionNonce": 1055550946,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					324.53131378935564,
					0.5653855640929351
				]
			],
			"lastCommittedPoint": [
				324.53131378935564,
				0.5653855640929351
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "lUUwmJGOJFPGseapmzrXl",
				"focus": -0.04236002409937471,
				"gap": 6.655976850376419
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "eBCXbvbD",
			"type": "text",
			"x": 774.015972996981,
			"y": 404.451024933806,
			"width": 90.45989990234375,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 539782178,
			"version": 20,
			"versionNonce": 1302681918,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "Definition",
			"rawText": "Definition",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Definition",
			"lineHeight": 1.25
		},
		{
			"id": "4fUzG59T",
			"type": "text",
			"x": 1148.4741911649041,
			"y": 295.6333204724187,
			"width": 123.27984619140625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 526067874,
			"version": 225,
			"versionNonce": 1290166690,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "Phase space",
			"rawText": "Phase space",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Phase space",
			"lineHeight": 1.25
		},
		{
			"id": "lUUwmJGOJFPGseapmzrXl",
			"type": "image",
			"x": 995.3079034736504,
			"y": 328.8028754079323,
			"width": 421.48236319461563,
			"height": 221.9892003532568,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1270274238,
			"version": 288,
			"versionNonce": 610500990,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Wn8cIU3YUtOPFEZYxgq9X",
					"type": "arrow"
				}
			],
			"updated": 1706818018375,
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
			"id": "XZVjlnVw",
			"type": "text",
			"x": 964.1045851817323,
			"y": 552.6620173818898,
			"width": 498.27294921875,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 803115710,
			"version": 420,
			"versionNonce": 1722670434,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "Phase space is a vector field describing the rate of change\nas small vectors (normalized for less clutter when visualizing)\nits a visual way of describing what would happen if we dropped\na point in the field and let flow according to the vector field",
			"rawText": "Phase space is a vector field describing the rate of change\nas small vectors (normalized for less clutter when visualizing)\nits a visual way of describing what would happen if we dropped\na point in the field and let flow according to the vector field",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "Phase space is a vector field describing the rate of change\nas small vectors (normalized for less clutter when visualizing)\nits a visual way of describing what would happen if we dropped\na point in the field and let flow according to the vector field",
			"lineHeight": 1.25
		},
		{
			"id": "lt848rHAOJ3TUPBzaRTw3",
			"type": "arrow",
			"x": -227.53868765564266,
			"y": 429.42730989423313,
			"width": 284.42669240682517,
			"height": 196.43857892845472,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1734021246,
			"version": 222,
			"versionNonce": 162701758,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1706818018375,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				-284.42669240682517,
				196.43857892845472
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "j9Ftbw8m",
				"focus": -0.030007198330140275,
				"gap": 11.939234373128329
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "LD3TgHrR",
			"type": "text",
			"x": -467.8739609777366,
			"y": 377.2483123663622,
			"width": 218.75244140625,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1386145214,
			"version": 143,
			"versionNonce": 428859682,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "We first need to define our\nfunction of course",
			"rawText": "We first need to define our\nfunction of course",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "We first need to define our\nfunction of course",
			"lineHeight": 1.25
		},
		{
			"id": "j9Ftbw8m",
			"type": "text",
			"x": -651.2099479335606,
			"y": 637.8051231958161,
			"width": 278.4891357421875,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1925210658,
			"version": 88,
			"versionNonce": 1890826750,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "lt848rHAOJ3TUPBzaRTw3",
					"type": "arrow"
				}
			],
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "Newtonian Mechanics",
			"rawText": "Newtonian Mechanics",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Newtonian Mechanics",
			"lineHeight": 1.25
		},
		{
			"id": "EyVVJNYA3k5LVvoYXi6Zv",
			"type": "image",
			"x": -771.8107062179575,
			"y": 672.80512304634,
			"width": 519.6906530147962,
			"height": 70.31484850138695,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1472675810,
			"version": 154,
			"versionNonce": 1895525602,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
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
			"id": "IunQAiF5",
			"type": "text",
			"x": -667.7233722001552,
			"y": 743.1199723476561,
			"width": 302.99261474609375,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 224001214,
			"version": 161,
			"versionNonce": 1080543806,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "Velocity is the change of position\nAcceleration is the change of Velocity!",
			"rawText": "Velocity is the change of position\nAcceleration is the change of Velocity!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Velocity is the change of position\nAcceleration is the change of Velocity!",
			"lineHeight": 1.25
		},
		{
			"id": "JoI3LHqz",
			"type": "text",
			"x": -766.5155628953203,
			"y": 788.5442572611717,
			"width": 500.5769958496094,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1559764158,
			"version": 116,
			"versionNonce": 847216802,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "We know F (such as gravity) and the mass describing our scene",
			"rawText": "We know F (such as gravity) and the mass describing our scene",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "We know F (such as gravity) and the mass describing our scene",
			"lineHeight": 1.25
		},
		{
			"id": "rOLiHsbm",
			"type": "text",
			"x": -724.7154378224429,
			"y": 813.9685416359941,
			"width": 416.97674560546875,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2001910270,
			"version": 110,
			"versionNonce": 1471140478,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "Now we need to be able to compute p from our ODE",
			"rawText": "Now we need to be able to compute p from our ODE",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Now we need to be able to compute p from our ODE",
			"lineHeight": 1.25
		},
		{
			"id": "yiRCaGaRSuLta5Wbj8wkW",
			"type": "image",
			"x": -643.1083755659614,
			"y": 840.275901624628,
			"width": 121.89866804751124,
			"height": 60.94933402375562,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 951201442,
			"version": 171,
			"versionNonce": 432741474,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
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
			"id": "0P_VX_lD6WlT6nl4RgTwu",
			"type": "image",
			"x": -492.3318407900091,
			"y": 841.5768168033926,
			"width": 127.60108400675459,
			"height": 58.34750422531086,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 302248546,
			"version": 145,
			"versionNonce": 290247358,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
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
			"id": "ZaZtj7MJ",
			"type": "text",
			"x": 20.77453761314463,
			"y": 464.9660081866187,
			"width": 393.93682861328125,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 13536610,
			"version": 99,
			"versionNonce": 346898466,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"text": "There are many ways to do answer this question!",
			"rawText": "There are many ways to do answer this question!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "There are many ways to do answer this question!",
			"lineHeight": 1.25
		},
		{
			"id": "R5yqBvIcqc14D8oum8VnL",
			"type": "arrow",
			"x": 216.95741905176328,
			"y": 502.16255735630466,
			"width": 0.8070272547136028,
			"height": 137.19463330129486,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 2071638590,
			"version": 69,
			"versionNonce": 1205848830,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018375,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8070272547136028,
					137.19463330129486
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "mAGRmHTf",
				"focus": -0.02431029878126344,
				"gap": 14.526490584842918
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "mAGRmHTf",
			"type": "text",
			"x": 144.90452961946494,
			"y": 653.8836812424424,
			"width": 145.71983337402344,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1138129278,
			"version": 39,
			"versionNonce": 2132077538,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "R5yqBvIcqc14D8oum8VnL",
					"type": "arrow"
				}
			],
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "Euler's Method",
			"rawText": "Euler's Method",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Euler's Method",
			"lineHeight": 1.25
		},
		{
			"id": "HTZXtu4r",
			"type": "text",
			"x": 231.9710456459601,
			"y": 542.8093689840722,
			"width": 68.80015563964844,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1251801982,
			"version": 50,
			"versionNonce": 1508490046,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "simple\napproach",
			"rawText": "simple\napproach",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "simple\napproach",
			"lineHeight": 1.25
		},
		{
			"id": "D4lBFbR8",
			"type": "text",
			"x": -45.46120801099618,
			"y": 687.9625472033241,
			"width": 523.2490844726562,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 304148222,
			"version": 112,
			"versionNonce": 1594957730,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "Idea: Replace dt by a very small (tweakable) step h and compute",
			"rawText": "Idea: Replace dt by a very small (tweakable) step h and compute",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Idea: Replace dt by a very small (tweakable) step h and compute",
			"lineHeight": 1.25
		},
		{
			"id": "UcbvX1daF0K8Khlye-3U-",
			"type": "image",
			"x": 170.45148217044562,
			"y": 713.8319330022207,
			"width": 169.25564491999592,
			"height": 49.283261314939985,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 181390078,
			"version": 179,
			"versionNonce": 768320382,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"id": "bOV2UvZg",
			"type": "text",
			"x": -31.192017602920828,
			"y": 767.8403824198614,
			"width": 492.240966796875,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 203912098,
			"version": 231,
			"versionNonce": 550558562,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "This will obviously be only an approximation!\nand this method is quite sensitive to h!\nProblem: too big will cause explosion and inaccurate behaviour!",
			"rawText": "This will obviously be only an approximation!\nand this method is quite sensitive to h!\nProblem: too big will cause explosion and inaccurate behaviour!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "This will obviously be only an approximation!\nand this method is quite sensitive to h!\nProblem: too big will cause explosion and inaccurate behaviour!",
			"lineHeight": 1.25
		},
		{
			"id": "AT4Xjs7dSlbJ_hiYn-9TH",
			"type": "freedraw",
			"x": 241.12413318018554,
			"y": 749.3003839800608,
			"width": 0.5608494335147327,
			"height": 8.412741502721246,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 10523170,
			"version": 36,
			"versionNonce": 902202302,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.5608494335147327,
				8.412741502721246
			]
		},
		{
			"id": "P15egQL9A1WH7_8njCXMX",
			"type": "freedraw",
			"x": 241.2176080857713,
			"y": 742.5701907778838,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1174664674,
			"version": 6,
			"versionNonce": 1386422050,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.0001,
				0.0001
			]
		},
		{
			"id": "PRjB2WM944XQys8UUvm0Z",
			"type": "line",
			"x": -775.8658370542122,
			"y": 808.0986228844642,
			"width": 45.19942064431348,
			"height": 124.71691992597607,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1505126690,
			"version": 58,
			"versionNonce": 1945852926,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				-31.80699971266506,
				124.71691992597607
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "r4Rrx45h",
			"type": "text",
			"x": -904.7785534325093,
			"y": 933.2779232097585,
			"width": 190.51239013671875,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1544297378,
			"version": 80,
			"versionNonce": 1626794722,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "Usually forces we have\ngood physical models for",
			"rawText": "Usually forces we have\ngood physical models for",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Usually forces we have\ngood physical models for",
			"lineHeight": 1.25
		},
		{
			"id": "m7fJWSej_JnzeJCwe4EZJ",
			"type": "image",
			"x": -1087.487003083767,
			"y": 1073.1659092772422,
			"width": 73.71508097732475,
			"height": 22.594660835961605,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 860207550,
			"version": 195,
			"versionNonce": 2120952894,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"id": "PBuz1KzKVFP-OXmRysWjs",
			"type": "image",
			"x": -1164.6080201421278,
			"y": 1095.0302003759703,
			"width": 223.17449724501282,
			"height": 123.91979407612564,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1938963170,
			"version": 156,
			"versionNonce": 1381711522,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"id": "5JfsrjGK",
			"type": "text",
			"x": -1098.3217045621884,
			"y": 1043.7371807011098,
			"width": 105.23225402832031,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1765347298,
			"version": 17,
			"versionNonce": 49738878,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "earth gravity",
			"rawText": "earth gravity",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "earth gravity",
			"lineHeight": 1.25
		},
		{
			"id": "sOC6rlhM",
			"type": "text",
			"x": -903.416085678378,
			"y": 1040.6262097644496,
			"width": 116.73626708984375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 891726590,
			"version": 45,
			"versionNonce": 58661474,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "general gravity",
			"rawText": "general gravity",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "general gravity",
			"lineHeight": 1.25
		},
		{
			"id": "RXmOv38S8fySekcAnf3Ro",
			"type": "image",
			"x": -961.1751657846344,
			"y": 1061.6901544059842,
			"width": 250.92025292231682,
			"height": 46.10361563725779,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 236990562,
			"version": 208,
			"versionNonce": 1264563390,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"id": "VObI332cS_V91d50Kp266",
			"type": "line",
			"x": -818.4279750800367,
			"y": 988.9689633354208,
			"width": 1.1027228967727751,
			"height": 46.314361664458374,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 441428030,
			"version": 39,
			"versionNonce": 1664187938,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.1027228967727751,
					46.314361664458374
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "M7f0kTRrOwj6wRss7ApgM",
			"type": "line",
			"x": -820.082059425196,
			"y": 990.62304768058,
			"width": 224.40410949326872,
			"height": 51.276614699935976,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1600071138,
			"version": 115,
			"versionNonce": 1095134462,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				-224.40410949326872,
				51.276614699935976
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "2nsU8RZkXZGDNgMLyzz3b",
			"type": "line",
			"x": -817.16071376749,
			"y": 991.3155808084759,
			"width": 210.49373557446245,
			"height": 50.095670693485545,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1186183266,
			"version": 128,
			"versionNonce": 778136034,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				210.49373557446245,
				50.095670693485545
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "fIyZEqjo",
			"type": "text",
			"x": -644.3994701500263,
			"y": 1040.4920648837324,
			"width": 76.38417053222656,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1356258594,
			"version": 13,
			"versionNonce": 1915493694,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "Dampening",
			"rawText": "Dampening",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Dampening",
			"lineHeight": 1.25
		},
		{
			"id": "D3pRh0BEDXDiBy-bCbuju",
			"type": "image",
			"x": -640.3291297518891,
			"y": 1066.7697314833733,
			"width": 69.62226966329581,
			"height": 20.914199582650124,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1566111934,
			"version": 72,
			"versionNonce": 740154786,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"id": "OBMmrfMEXxP3mVYoj81tj",
			"type": "image",
			"x": -673.2050222229626,
			"y": 1088.372676059956,
			"width": 137.04488379275844,
			"height": 80.34592206673486,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1250224830,
			"version": 126,
			"versionNonce": 326223230,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"id": "sxBufYs8ogC6_bIQyNWIh",
			"type": "line",
			"x": -819.2347767181011,
			"y": 987.8241112459586,
			"width": 474.19714830141663,
			"height": 145.22789144256603,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1605497662,
			"version": 237,
			"versionNonce": 1771428194,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				474.19714830141663,
				145.22789144256603
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "gaKvaFL3",
			"type": "text",
			"x": -390.9337313219579,
			"y": 1133.0520026885247,
			"width": 91.79220581054688,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1649180286,
			"version": 16,
			"versionNonce": 106456510,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "Spring force",
			"rawText": "Spring force",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Spring force",
			"lineHeight": 1.25
		},
		{
			"id": "09i5l65sJW3zbHW6dhxWt",
			"type": "line",
			"x": -293.78969118969746,
			"y": 1233.2648415019028,
			"width": 71.12572375028896,
			"height": 41.52231947542009,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 175177790,
			"version": 87,
			"versionNonce": 1981308194,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				88.22121796323546,
				4.365586043541498
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "HC85tGXV",
			"type": "text",
			"x": -216.85940026554687,
			"y": 1184.8774467726364,
			"width": 41.53164744171562,
			"height": 9.48728810724586,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1749283454,
			"version": 129,
			"versionNonce": 1543568894,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "rest state",
			"rawText": "rest state",
			"fontSize": 7.58983048579668,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 6.000000000000009,
			"containerId": null,
			"originalText": "rest state",
			"lineHeight": 1.25
		},
		{
			"id": "npTtoBqAxk-FVupzhmuai",
			"type": "line",
			"x": -315.6998062981559,
			"y": 1254.5378940177654,
			"width": 101.26421779794146,
			"height": 23.352768594219242,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 2001045474,
			"version": 45,
			"versionNonce": 521431266,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				101.26421779794146,
				16.73959518700667
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "di7oRK4J",
			"type": "text",
			"x": -213.83183712674565,
			"y": 1260.1513393486628,
			"width": 46.118019448426935,
			"height": 7.773381261890155,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1189834082,
			"version": 81,
			"versionNonce": 1500286526,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "distance length",
			"rawText": "distance length",
			"fontSize": 6.21870500951213,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 4.999999999999994,
			"containerId": null,
			"originalText": "distance length",
			"lineHeight": 1.25
		},
		{
			"id": "1cK1hcBqOqomiW8f8BzWV",
			"type": "image",
			"x": 111.91242431584021,
			"y": 832.3966722535009,
			"width": 236.309739318825,
			"height": 248.51161914595883,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1378903934,
			"version": 146,
			"versionNonce": 739835042,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"id": "hZYuY3Jq",
			"type": "text",
			"x": 99.53901930776055,
			"y": 1075.740051887723,
			"width": 261.0565490722656,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 657998434,
			"version": 106,
			"versionNonce": 2071729790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "Problem 2: Inaccurate behaviour!",
			"rawText": "Problem 2: Inaccurate behaviour!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Problem 2: Inaccurate behaviour!",
			"lineHeight": 1.25
		},
		{
			"id": "TFvNukWozKvTEy62tw7N-",
			"type": "image",
			"x": 133.39909291974405,
			"y": 1147.103612228632,
			"width": 193.33640258502038,
			"height": 50.276605873173146,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 199325154,
			"version": 187,
			"versionNonce": 450173026,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"id": "8e3CeqFO",
			"type": "text",
			"x": 23.018204104395835,
			"y": 1103.1009167252103,
			"width": 410.4969177246094,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1280573218,
			"version": 124,
			"versionNonce": 2062587582,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "Consider the following function simulating a rotation\nin a circle",
			"rawText": "Consider the following function simulating a rotation\nin a circle",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Consider the following function simulating a rotation\nin a circle",
			"lineHeight": 1.25
		},
		{
			"id": "r3iq83-0kShe6rD14U5yP",
			"type": "image",
			"x": 145.4010599924004,
			"y": 1201.5693599939,
			"width": 175.86682192039308,
			"height": 52.52131333369205,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 765884542,
			"version": 162,
			"versionNonce": 1528282146,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"id": "TMYrp-j54gsXi-micshN0",
			"type": "image",
			"x": 339.7071273314945,
			"y": 1126.4505201144368,
			"width": 131.08817594015312,
			"height": 116.8538538052375,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 93702462,
			"version": 98,
			"versionNonce": 1349193470,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
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
			"id": "RhYkmyd8",
			"type": "text",
			"x": -16.31405758976884,
			"y": 1248.7437783655207,
			"width": 499.29705810546875,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1282517438,
			"version": 215,
			"versionNonce": 181397474,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "Eulers method will Spiral outwards given enough time no matter\nthe value of t",
			"rawText": "Eulers method will Spiral outwards given enough time no matter\nthe value of t",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Eulers method will Spiral outwards given enough time no matter\nthe value of t",
			"lineHeight": 1.25
		},
		{
			"id": "6GXTfLh3",
			"type": "text",
			"x": -92.61337041414623,
			"y": 1294.1831824035876,
			"width": 645.361328125,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1559888546,
			"version": 186,
			"versionNonce": 946634558,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "Using the taylor expansion of this function we can see that the error\nscales with h, meaning if we take 10x smaller h we will be 10 times more accurate",
			"rawText": "Using the taylor expansion of this function we can see that the error\nscales with h, meaning if we take 10x smaller h we will be 10 times more accurate",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Using the taylor expansion of this function we can see that the error\nscales with h, meaning if we take 10x smaller h we will be 10 times more accurate",
			"lineHeight": 1.25
		},
		{
			"id": "hj3Dd2dh",
			"type": "text",
			"x": 76.51745913141286,
			"y": 1340.1073382764428,
			"width": 307.09967041015625,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1474524926,
			"version": 69,
			"versionNonce": 839687074,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018376,
			"link": null,
			"locked": false,
			"text": "Also called First Order Method",
			"rawText": "Also called First Order Method",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Also called First Order Method",
			"lineHeight": 1.25
		},
		{
			"id": "KGRbnKCx_Cupsvt5KBG7u",
			"type": "arrow",
			"x": 549.6176719820755,
			"y": 1222.562422981753,
			"width": 260.17046084881486,
			"height": 1.0740539966298002,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 432348770,
			"version": 52,
			"versionNonce": 928376702,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					260.17046084881486,
					1.0740539966298002
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": {
				"elementId": "baGjBTwV",
				"focus": 0.000600156805711362,
				"gap": 11.21703101456518
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "1Duvmcng",
			"type": "text",
			"x": 600.708148028614,
			"y": 1191.789451255146,
			"width": 148.976318359375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 236500030,
			"version": 36,
			"versionNonce": 2130499426,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "Alternative method",
			"rawText": "Alternative method",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Alternative method",
			"lineHeight": 1.25
		},
		{
			"id": "nzoE1SIt",
			"type": "text",
			"x": 1342.5737288119499,
			"y": 930.4395518913473,
			"width": 247.8010711669922,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 433573282,
			"version": 226,
			"versionNonce": 493373374,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "Trapezoid Method",
			"rawText": "Trapezoid Method",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Trapezoid Method",
			"lineHeight": 1.25
		},
		{
			"id": "baGjBTwV",
			"type": "text",
			"x": 821.0051638454557,
			"y": 1194.4177227355888,
			"width": 347.1207275390625,
			"height": 60,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1918633634,
			"version": 194,
			"versionNonce": 32480034,
			"isDeleted": false,
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
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "the function varies within each step of t\nwhat if we can look ahead at next step of\nf and compensate for the variation",
			"rawText": "the function varies within each step of t\nwhat if we can look ahead at next step of\nf and compensate for the variation",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "the function varies within each step of t\nwhat if we can look ahead at next step of\nf and compensate for the variation",
			"lineHeight": 1.25
		},
		{
			"id": "Zofz2FY8LKJvS3emCi3oM",
			"type": "arrow",
			"x": 963.9786905819032,
			"y": 1187.9678345858915,
			"width": 354.95181707368863,
			"height": 233.0382750392605,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 973381218,
			"version": 180,
			"versionNonce": 180658174,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1706818018377,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				354.95181707368863,
				-233.0382750392605
			],
			"startBinding": {
				"elementId": "baGjBTwV",
				"focus": -0.20560731985889588,
				"gap": 6.449888149697244
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "7DN4FA_8nIZRuti06-1gF",
			"type": "image",
			"x": 1620.2985051263588,
			"y": 953.5838732908855,
			"width": 267.00594055248234,
			"height": 211.9822592761452,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 941059966,
			"version": 95,
			"versionNonce": 1767106274,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
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
			"id": "tgGL_9efkM67OcQBBsjyo",
			"type": "image",
			"x": 1310.8234043154514,
			"y": 1047.4211217425354,
			"width": 288.1289105658803,
			"height": 88.2446093613451,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1896985918,
			"version": 211,
			"versionNonce": 1936453694,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
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
			"id": "iJCOAVIx",
			"type": "text",
			"x": 1289.4809581602867,
			"y": 986.3806691898586,
			"width": 331.8086853027344,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2107403326,
			"version": 105,
			"versionNonce": 1035516578,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "Idea: Average your first and second step\ngradients in order to arrive at a better\napproximation",
			"rawText": "Idea: Average your first and second step\ngradients in order to arrive at a better\napproximation",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "Idea: Average your first and second step\ngradients in order to arrive at a better\napproximation",
			"lineHeight": 1.25
		},
		{
			"id": "Z5fFaV63",
			"type": "text",
			"x": 1280.213418810635,
			"y": 1136.607915595032,
			"width": 342.38470458984375,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1624180414,
			"version": 121,
			"versionNonce": 591345790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "This improves the approximation and scales\nquadratically with the error",
			"rawText": "This improves the approximation and scales\nquadratically with the error",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "This improves the approximation and scales\nquadratically with the error",
			"lineHeight": 1.25
		},
		{
			"id": "om5sWvvV",
			"type": "text",
			"x": 1319.6571761034656,
			"y": 1178.890418722316,
			"width": 260.5125427246094,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2140637282,
			"version": 54,
			"versionNonce": 499979874,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "also called Second Order Method",
			"rawText": "also called Second Order Method",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "also called Second Order Method",
			"lineHeight": 1.25
		},
		{
			"id": "5RScDtPd",
			"type": "text",
			"x": 1236.2128958369615,
			"y": 1200.6588874888428,
			"width": 449.1689147949219,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 893492898,
			"version": 151,
			"versionNonce": 1107261630,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "The problem still presists... but perhaps more accurate...\nis there a way to get rid of the method??",
			"rawText": "The problem still presists... but perhaps more accurate...\nis there a way to get rid of the method??",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "The problem still presists... but perhaps more accurate...\nis there a way to get rid of the method??",
			"lineHeight": 1.25
		},
		{
			"id": "OmYcNmij8kX4Of9d-nUEq",
			"type": "arrow",
			"x": 1447.3081228606297,
			"y": 1273.6757978885385,
			"width": 1.265119940580007,
			"height": 165.73071221597797,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1332508706,
			"version": 68,
			"versionNonce": 2053110306,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.265119940580007,
					165.73071221597797
				]
			],
			"lastCommittedPoint": [
				-1.265119940580007,
				165.73071221597797
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "WjuLSsdl",
			"type": "text",
			"x": 1175.4785253207747,
			"y": 1459.1339896845068,
			"width": 540.41943359375,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1330830270,
			"version": 121,
			"versionNonce": 1464709374,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "cwuAMPYz57_yZAf6wQHTg",
					"type": "arrow"
				}
			],
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "So far we have only looked at one type of\nequations, lets split this up into a more general sense",
			"rawText": "So far we have only looked at one type of\nequations, lets split this up into a more general sense",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "So far we have only looked at one type of\nequations, lets split this up into a more general sense",
			"lineHeight": 1.25
		},
		{
			"id": "cwuAMPYz57_yZAf6wQHTg",
			"type": "arrow",
			"x": 1440.2534153089457,
			"y": 1524.627202366279,
			"width": 277.12882868149904,
			"height": 233.32973219448036,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1713272290,
			"version": 161,
			"versionNonce": 1382049250,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1706818018377,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				-283.4996063523381,
				222.9772184793669
			],
			"startBinding": {
				"elementId": "WjuLSsdl",
				"focus": -0.02491902404550745,
				"gap": 15.49321268177232
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "nlTh8GJO",
			"type": "text",
			"x": 1011.7098761770517,
			"y": 1774.4583091998413,
			"width": 293.27325439453125,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2022175358,
			"version": 50,
			"versionNonce": 1319821630,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "Explicit Euler Method\n(Forward Euler)",
			"rawText": "Explicit Euler Method\n(Forward Euler)",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "Explicit Euler Method\n(Forward Euler)",
			"lineHeight": 1.25
		},
		{
			"id": "MWPWr6hu",
			"type": "text",
			"x": 1036.2269480361679,
			"y": 1842.7026138196832,
			"width": 247.42449951171875,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2092816930,
			"version": 104,
			"versionNonce": 1860000162,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "(What we have covered so far)",
			"rawText": "(What we have covered so far)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "(What we have covered so far)",
			"lineHeight": 1.25
		},
		{
			"id": "6yg8ePb2IlbqAz3QnCeRu",
			"type": "image",
			"x": 1028.4223084753835,
			"y": 1866.773058205992,
			"width": 262.237431424433,
			"height": 54.28481860696862,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 891609698,
			"version": 142,
			"versionNonce": 2071464318,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
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
			"id": "1bnCW631n6wR9GAF8HnUr",
			"type": "arrow",
			"x": 1439.8489736996758,
			"y": 1526.6628962111345,
			"width": 337.09175122623105,
			"height": 246.93078892686117,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 289930722,
			"version": 344,
			"versionNonce": 520476002,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				353.78972682503536,
				276.53360280405786
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "ZhNimlRz",
				"focus": 0.05603619898062451,
				"gap": 4.052317610613727
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "ZhNimlRz",
			"type": "text",
			"x": 1632.6516529234761,
			"y": 1777.6460027486091,
			"width": 291.6492614746094,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 415660542,
			"version": 60,
			"versionNonce": 485894590,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "1bnCW631n6wR9GAF8HnUr",
					"type": "arrow"
				}
			],
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "Implicit Euler Method\n(Backwards Euler)",
			"rawText": "Implicit Euler Method\n(Backwards Euler)",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "Implicit Euler Method\n(Backwards Euler)",
			"lineHeight": 1.25
		},
		{
			"id": "WID00ODUe-KiFu1ZKIMjA",
			"type": "image",
			"x": 1615.8072053101428,
			"y": 1846.432093353955,
			"width": 327.8963549288562,
			"height": 40.68192989191765,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1442203746,
			"version": 105,
			"versionNonce": 1948834082,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
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
			"id": "5FCqMd2H",
			"type": "text",
			"x": 1448.886623815531,
			"y": 1896.0578770960283,
			"width": 659.1793212890625,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 407616062,
			"version": 216,
			"versionNonce": 1648771582,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "This is more computationally difficult to compute\nsometimes we have a closed form solution\nBUT\nmore often than not we need an interative method for such things",
			"rawText": "This is more computationally difficult to compute\nsometimes we have a closed form solution\nBUT\nmore often than not we need an interative method for such things",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "This is more computationally difficult to compute\nsometimes we have a closed form solution\nBUT\nmore often than not we need an interative method for such things",
			"lineHeight": 1.25
		},
		{
			"id": "AFH0CCIY",
			"type": "text",
			"x": 1412.4957395145475,
			"y": 2014.2943006890973,
			"width": 734.519287109375,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 547353698,
			"version": 203,
			"versionNonce": 2109039842,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "The intuition behind this method comes from \"looking ahead\"\nand then saying \"if we were to walk backwards using the current gradient,\nwe would end up at the past step\"",
			"rawText": "The intuition behind this method comes from \"looking ahead\"\nand then saying \"if we were to walk backwards using the current gradient,\nwe would end up at the past step\"",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "The intuition behind this method comes from \"looking ahead\"\nand then saying \"if we were to walk backwards using the current gradient,\nwe would end up at the past step\"",
			"lineHeight": 1.25
		},
		{
			"id": "907uN-8DDZfIpy70rIxq6",
			"type": "image",
			"x": 1628.3236676640477,
			"y": 2118.827298882936,
			"width": 308.2871246367697,
			"height": 65.42996335503142,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1696859426,
			"version": 147,
			"versionNonce": 1852396094,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
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
			"id": "TTnhebc12IWkj-a1hEW0w",
			"type": "image",
			"x": 2047.3659232490672,
			"y": 2077.934042686778,
			"width": 327.17959421817716,
			"height": 247.43862960074844,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1688043262,
			"version": 178,
			"versionNonce": 87718050,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
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
			"id": "YquryVUd",
			"type": "text",
			"x": 1561.4612768920256,
			"y": 2187.486657409844,
			"width": 444.8009033203125,
			"height": 120,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 385137954,
			"version": 275,
			"versionNonce": 1547721342,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "This still does not solve the issue of inaccuracy\nas the error is still O(h)!\nBUT\nthis allows our problem to no longer explode with varying\nvalues of h (instead it always decays)!\nbecause Xi is now divided by 1+h",
			"rawText": "This still does not solve the issue of inaccuracy\nas the error is still O(h)!\nBUT\nthis allows our problem to no longer explode with varying\nvalues of h (instead it always decays)!\nbecause Xi is now divided by 1+h",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 114,
			"containerId": null,
			"originalText": "This still does not solve the issue of inaccuracy\nas the error is still O(h)!\nBUT\nthis allows our problem to no longer explode with varying\nvalues of h (instead it always decays)!\nbecause Xi is now divided by 1+h",
			"lineHeight": 1.25
		},
		{
			"id": "h7yITSVK5AWfF8eSE3q61",
			"type": "arrow",
			"x": 1776.4799285482522,
			"y": 2348.5094560874413,
			"width": 3.4541689508093896,
			"height": 122.86150734723151,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 948190498,
			"version": 147,
			"versionNonce": 1248269410,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-3.4541689508093896,
					122.86150734723151
				]
			],
			"lastCommittedPoint": [
				-5.100447095943991,
				123.43081972184837
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "AC4QXiR0",
				"focus": -0.012468633799616994,
				"gap": 15.163652849305436
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "rPO6LcI6",
			"type": "text",
			"x": 1579.6535485424638,
			"y": 2360.1478465420423,
			"width": 161.07237243652344,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1859292158,
			"version": 125,
			"versionNonce": 1116494526,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "In order to solve\nthis implicit equation\nwe can use Newtons\nMethod",
			"rawText": "In order to solve\nthis implicit equation\nwe can use Newtons\nMethod",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "In order to solve\nthis implicit equation\nwe can use Newtons\nMethod",
			"lineHeight": 1.25
		},
		{
			"id": "gLTFjzPK",
			"type": "text",
			"x": 1107.7667460035896,
			"y": 2382.445681017131,
			"width": 158.47984313964844,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 682167102,
			"version": 127,
			"versionNonce": 1057634338,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "Newtons Method",
			"rawText": "Newtons Method",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Newtons Method",
			"lineHeight": 1.25
		},
		{
			"id": "jlURFMdX",
			"type": "text",
			"x": 1047.814376777405,
			"y": 2442.632668768538,
			"width": 278.38458251953125,
			"height": 160,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2062617058,
			"version": 177,
			"versionNonce": 938365694,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "1) start from an initial x0 guess\n\n2) Iterate over the following\n\n\n\n\n3) This will converge quadratically ",
			"rawText": "1) start from an initial x0 guess\n\n2) Iterate over the following\n\n\n\n\n3) This will converge quadratically ",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 154,
			"containerId": null,
			"originalText": "1) start from an initial x0 guess\n\n2) Iterate over the following\n\n\n\n\n3) This will converge quadratically ",
			"lineHeight": 1.25
		},
		{
			"id": "4BlapFP7",
			"type": "text",
			"x": 1108.3189250635794,
			"y": 2407.927916757051,
			"width": 153.81982421875,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2059206462,
			"version": 60,
			"versionNonce": 1125311458,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "solving g(x) = 0",
			"rawText": "solving g(x) = 0",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "solving g(x) = 0",
			"lineHeight": 1.25
		},
		{
			"id": "-Rejw9OwNQvN2-M9R-mht",
			"type": "image",
			"x": 1003.3032094422249,
			"y": 2517.7291946672144,
			"width": 139.65032659914323,
			"height": 44.36807251326946,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1808097250,
			"version": 167,
			"versionNonce": 1457996606,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "hucY9lEnbxpcMrvnwt4mI",
					"type": "arrow"
				}
			],
			"updated": 1706818018377,
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
			"id": "hucY9lEnbxpcMrvnwt4mI",
			"type": "arrow",
			"x": 1149.9685343582514,
			"y": 2538.01741632316,
			"width": 74.0762666858111,
			"height": 1.7778304004596066,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 934965858,
			"version": 100,
			"versionNonce": 1620055970,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					74.0762666858111,
					1.7778304004596066
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "-Rejw9OwNQvN2-M9R-mht",
				"focus": -0.15674784289937949,
				"gap": 7.014998316883293
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "jwEY9M3R",
			"type": "text",
			"x": 1007.8850426457393,
			"y": 2618.1462943285496,
			"width": 381.4088134765625,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 296744354,
			"version": 165,
			"versionNonce": 1104685950,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": "[[Partial Derivatives]]",
			"locked": false,
			"text": "Note that if this is Multidimensional we use the\nJacobian matrix instead",
			"rawText": "Note that if this is Multidimensional we use the\nJacobian matrix instead",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Note that if this is Multidimensional we use the\nJacobian matrix instead",
			"lineHeight": 1.25
		},
		{
			"id": "lcYOP94RnqVVAfDi9LtLx",
			"type": "image",
			"x": 1040.3285689917582,
			"y": 2658.9356879622947,
			"width": 326.1354277763377,
			"height": 37.89383065591733,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 336078846,
			"version": 246,
			"versionNonce": 129028962,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
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
			"id": "FXlKGWALH4u--O5dKHL6E",
			"type": "arrow",
			"x": 1528.6689042387752,
			"y": 2401.1086001801177,
			"width": 196.9316181079373,
			"height": 2.009506307224001,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 1689736034,
			"version": 31,
			"versionNonce": 654445502,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-196.9316181079373,
					-2.009506307224001
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "1BvIwqeBKvrdTjpcsOqPs",
			"type": "image",
			"x": 1584.7439020030463,
			"y": 2563.1702270740207,
			"width": 395.50145549591593,
			"height": 35.860184532481206,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1326340862,
			"version": 211,
			"versionNonce": 1254364962,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1706818018377,
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
			"id": "AC4QXiR0",
			"type": "text",
			"x": 1688.0654642156296,
			"y": 2486.5346162839783,
			"width": 170.6403350830078,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1932576382,
			"version": 147,
			"versionNonce": 1149625342,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "h7yITSVK5AWfF8eSE3q61",
					"type": "arrow"
				}
			],
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"text": "Apply Newtons method",
			"rawText": "Apply Newtons method",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Apply Newtons method",
			"lineHeight": 1.25
		},
		{
			"id": "nSM3SGwAWym3aBljJTgwZ",
			"type": "image",
			"x": 1647.1894711164284,
			"y": 2510.382313320208,
			"width": 250.3745391195106,
			"height": 47.38396651560831,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1148825662,
			"version": 247,
			"versionNonce": 439935714,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
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
			"id": "YbNCS2ob9QlvUPhy-sE5l",
			"type": "image",
			"x": 1563.6264946542203,
			"y": 2631.266936289749,
			"width": 416.10239995812447,
			"height": 57.65502715919318,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 717734590,
			"version": 299,
			"versionNonce": 1818539070,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
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
			"id": "cagZoJusiA9KENj_8a3BH",
			"type": "line",
			"x": 1772.489462543309,
			"y": 2600.641266081473,
			"width": 52.83688898545893,
			"height": 40.896349101738906,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 696399714,
			"version": 78,
			"versionNonce": 10368674,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-52.83688898545893,
					40.896349101738906
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "DxYCbzfhMKdsFNkcOC6gb",
			"type": "line",
			"x": 1839.3564858921382,
			"y": 2599.1486985960078,
			"width": 70.15067181685208,
			"height": 43.58297057557638,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 159479714,
			"version": 41,
			"versionNonce": 142572670,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-70.15067181685208,
					43.58297057557638
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "gpzoNh4eTxfQz3zNjBr-a",
			"type": "line",
			"x": 1710.6971686450604,
			"y": 2596.462077122171,
			"width": 10.746485895347632,
			"height": 9.552431906975471,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 140324258,
			"version": 14,
			"versionNonce": 1587745378,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018377,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-10.746485895347632,
					9.552431906975471
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "r5PanhVQ",
			"type": "text",
			"x": 1684.5957242841205,
			"y": 2602.730860561124,
			"width": 11.008026123046875,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1568120894,
			"version": 29,
			"versionNonce": 513227966,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "0",
			"rawText": "0",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "0",
			"lineHeight": 1.25
		},
		{
			"id": "xdphR3BX",
			"type": "text",
			"x": 1647.932054334126,
			"y": 2695.2219260449942,
			"width": 244.89651489257812,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2084624382,
			"version": 60,
			"versionNonce": 655783458,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "We then update our parameter",
			"rawText": "We then update our parameter",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "We then update our parameter",
			"lineHeight": 1.25
		},
		{
			"id": "fCBk64LS8MRfVOpnyTHNH",
			"type": "image",
			"x": 1694.2243857429442,
			"y": 2721.4440180259085,
			"width": 154.39575724372992,
			"height": 26.731205731750254,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1878574910,
			"version": 100,
			"versionNonce": 1414329598,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
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
			"id": "5mTek0II",
			"type": "text",
			"x": 1598.8529535131006,
			"y": 2753.2514959758246,
			"width": 362.1767578125,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 907972862,
			"version": 138,
			"versionNonce": 451371490,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "often one step is enough but you can iterate\nmultiple times for better accuracy",
			"rawText": "often one step is enough but you can iterate\nmultiple times for better accuracy",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "often one step is enough but you can iterate\nmultiple times for better accuracy",
			"lineHeight": 1.25
		},
		{
			"id": "Ij3HToqP2qSv8yO56V04e",
			"type": "arrow",
			"x": 758.222362450533,
			"y": 93.50771711584605,
			"width": 1327.4185019250897,
			"height": 13.164481010827217,
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
			"seed": 2054140990,
			"version": 134,
			"versionNonce": 1931584830,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1327.4185019250897,
					13.164481010827217
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "aWzolj1E",
			"type": "text",
			"x": 2475.5484882782252,
			"y": -232.13839722719516,
			"width": 281.3731689453125,
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
			"seed": 1994568034,
			"version": 142,
			"versionNonce": 86300066,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "Rigid body Simulation",
			"rawText": "Rigid body Simulation",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Rigid body Simulation",
			"lineHeight": 1.25
		},
		{
			"id": "A6w5rOlm",
			"type": "text",
			"x": 2211.2355609240362,
			"y": -182.3865771148087,
			"width": 809.9990234375,
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
			"seed": 123740798,
			"version": 185,
			"versionNonce": 1819692414,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "We define points in a rigid body relative to the distance of their center of mass!",
			"rawText": "We define points in a rigid body relative to the distance of their center of mass!",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "We define points in a rigid body relative to the distance of their center of mass!",
			"lineHeight": 1.25
		},
		{
			"id": "KMNJJrdKMMmTDrbt9cKQ7",
			"type": "image",
			"x": 2436.3711422059196,
			"y": -147.72564511329273,
			"width": 382.16247333408865,
			"height": 54.59463904772695,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 931972770,
			"version": 85,
			"versionNonce": 1996345698,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
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
			"id": "e9CdG9uRN2FAwqsCSlsYZ",
			"type": "image",
			"x": 3042.1258324698556,
			"y": -175.9646937184158,
			"width": 389,
			"height": 299,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1996248802,
			"version": 48,
			"versionNonce": 1569451454,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
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
			"id": "KInRDWWXcD1cdGpmt0Dxu",
			"type": "line",
			"x": 2413.796994627189,
			"y": -116.0182633543094,
			"width": 155.16707610179583,
			"height": 14.186704100735625,
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
			"seed": 1340155390,
			"version": 30,
			"versionNonce": 63001890,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-155.16707610179583,
					14.186704100735625
				]
			],
			"lastCommittedPoint": [
				-155.16707610179583,
				14.186704100735625
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "ujycYwzI",
			"type": "text",
			"x": 2111.389858714506,
			"y": -99.17155223468586,
			"width": 172.1197967529297,
			"height": 50,
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
			"seed": 680551614,
			"version": 104,
			"versionNonce": 327386622,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "the bar indicating\nrest state",
			"rawText": "the bar indicating\nrest state",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "the bar indicating\nrest state",
			"lineHeight": 1.25
		},
		{
			"id": "V3E5hGSP",
			"type": "text",
			"x": 2292.8927476016875,
			"y": -74.17155186322323,
			"width": 669.1192626953125,
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
			"seed": 1506539774,
			"version": 301,
			"versionNonce": 2094948578,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "Under rotation and translation we can treat the points\nin a body as a system of particles and we only translate the\ncenter of mass and rotate the points around their center of mass",
			"rawText": "Under rotation and translation we can treat the points\nin a body as a system of particles and we only translate the\ncenter of mass and rotate the points around their center of mass",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "Under rotation and translation we can treat the points\nin a body as a system of particles and we only translate the\ncenter of mass and rotate the points around their center of mass",
			"lineHeight": 1.25
		},
		{
			"id": "GAzwhHFu5NCEyf8tzENfQ",
			"type": "image",
			"x": 2427.3455135323966,
			"y": 8.189922386934143,
			"width": 415,
			"height": 80,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1013614782,
			"version": 48,
			"versionNonce": 257824318,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
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
			"id": "nV7FhnHV",
			"type": "text",
			"x": 2539.698867795163,
			"y": 111.69451802559081,
			"width": 112.91987609863281,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1875093474,
			"version": 92,
			"versionNonce": 769914018,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "Translation",
			"rawText": "Translation",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Translation",
			"lineHeight": 1.25
		},
		{
			"id": "uGEYPg7EDC2MYsgC6fsQ0",
			"type": "line",
			"x": 2607.107874058041,
			"y": 73.00781033767345,
			"width": 5.839503047232938,
			"height": 32.117266759780364,
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
			"seed": 1490637950,
			"version": 33,
			"versionNonce": 167550590,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-5.839503047232938,
					32.117266759780364
				]
			],
			"lastCommittedPoint": [
				-5.839503047232938,
				32.117266759780364
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "3yCjf2Lax41tLOGBWmUKT",
			"type": "line",
			"x": 2736.3068789780664,
			"y": 71.54793457586533,
			"width": 26.277763712547312,
			"height": 37.95676980701313,
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
			"seed": 1923705186,
			"version": 18,
			"versionNonce": 411111522,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					26.277763712547312,
					37.95676980701313
				]
			],
			"lastCommittedPoint": [
				26.277763712547312,
				37.95676980701313
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "teKx00Qy",
			"type": "text",
			"x": 2725.0042588212978,
			"y": 111.69451802559075,
			"width": 85.37989807128906,
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
			"seed": 1190749538,
			"version": 18,
			"versionNonce": 2015370942,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "Rotation",
			"rawText": "Rotation",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Rotation",
			"lineHeight": 1.25
		},
		{
			"id": "U-XNOj9Fui2Ucy6ARwpOM",
			"type": "freedraw",
			"x": 2817.703619685012,
			"y": 129.96549513853876,
			"width": 289.337800466064,
			"height": 40.24909035354699,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 263274850,
			"version": 208,
			"versionNonce": 814003234,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
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
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-288.5783836669407,
				2.2782503973705843
			]
		},
		{
			"id": "83LJp6BX",
			"type": "text",
			"x": 2457.481152844809,
			"y": 170.60251525250516,
			"width": 465.85943603515625,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1528795554,
			"version": 154,
			"versionNonce": 241800958,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "This splits up our Velocity into two components\nLinear and Angular",
			"rawText": "This splits up our Velocity into two components\nLinear and Angular",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "This splits up our Velocity into two components\nLinear and Angular",
			"lineHeight": 1.25
		},
		{
			"id": "O3_CBWftQZ3uFyqSa-0Qj",
			"type": "line",
			"x": 2637.072059272343,
			"y": 249.29668246995362,
			"width": 291.70607970219544,
			"height": 182.07157994835035,
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
			"seed": 1852991906,
			"version": 108,
			"versionNonce": 400416738,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				-291.70607970219544,
				182.07157994835035
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Hg0ECsfw",
			"type": "text",
			"x": 2137.4908334305806,
			"y": 446.05145434962253,
			"width": 372.6795959472656,
			"height": 50,
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
			"seed": 851475710,
			"version": 57,
			"versionNonce": 1163527998,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "Linear Velocity\nis the Velocity of the center of mass",
			"rawText": "Linear Velocity\nis the Velocity of the center of mass",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "Linear Velocity\nis the Velocity of the center of mass",
			"lineHeight": 1.25
		},
		{
			"id": "6udG4--c5clcC9AU70bXe",
			"type": "image",
			"x": 2221.6056402053114,
			"y": 499.4325076485227,
			"width": 189.824371611313,
			"height": 81.18275012307726,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1936882686,
			"version": 49,
			"versionNonce": 1520145314,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
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
			"id": "T2JVGuIdB_Q0VhbHh32NX",
			"type": "line",
			"x": 2639.029818196519,
			"y": 250.27556193204148,
			"width": 297.5793564747228,
			"height": 176.19830317582293,
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
			"seed": 2041098530,
			"version": 185,
			"versionNonce": 1565683582,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				297.5793564747228,
				176.19830317582293
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "YCJbvN3E",
			"type": "text",
			"x": 2678.5494822884298,
			"y": 439.1992981150072,
			"width": 516.119384765625,
			"height": 50,
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
			"seed": 325828194,
			"version": 97,
			"versionNonce": 720162658,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "Angular Velocity\nis the Rotation velocity of points around their COM",
			"rawText": "Angular Velocity\nis the Rotation velocity of points around their COM",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "Angular Velocity\nis the Rotation velocity of points around their COM",
			"lineHeight": 1.25
		},
		{
			"id": "K1kXg9F7XQQNojNTIy4ri",
			"type": "image",
			"x": 2868.4735918025226,
			"y": 490.57278474161365,
			"width": 140.04278602624078,
			"height": 82.16796118886576,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1124378530,
			"version": 87,
			"versionNonce": 1653854142,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
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
			"id": "635Wreof64BONrAboxUvz",
			"type": "image",
			"x": 2614.780211842493,
			"y": 590.099378855032,
			"width": 748.4112287477363,
			"height": 320.05621665929874,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1798250338,
			"version": 166,
			"versionNonce": 488674082,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
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
			"id": "6uT93YrWJDCbTkpyKdySa",
			"type": "line",
			"x": 3003.0582465742123,
			"y": 593.9993610650108,
			"width": 68.81016212036866,
			"height": 34.40508106018433,
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
			"seed": 1682372898,
			"version": 29,
			"versionNonce": 826222590,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				68.81016212036866,
				-34.40508106018433
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "4TmLCOZY",
			"type": "text",
			"x": 3085.4512079651736,
			"y": 539.7190115328973,
			"width": 74.51216125488281,
			"height": 20,
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
			"seed": 1376262398,
			"version": 67,
			"versionNonce": 1671814882,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "chain rule",
			"rawText": "chain rule",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "chain rule",
			"lineHeight": 1.25
		},
		{
			"id": "f1D5dvFp9yvfG7Czliqr7",
			"type": "line",
			"x": 3116.680649143095,
			"y": 644.8581839343938,
			"width": 99.30983121468353,
			"height": 38.94503184889561,
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
			"seed": 1558999266,
			"version": 36,
			"versionNonce": 2035644478,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				99.30983121468353,
				-38.94503184889561
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "2ggLNT45",
			"type": "text",
			"x": 3214.9300499243595,
			"y": 581.7043781988265,
			"width": 121.55229187011719,
			"height": 40,
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
			"seed": 1138342946,
			"version": 61,
			"versionNonce": 185316002,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "derivative of\nrotation matrix",
			"rawText": "derivative of\nrotation matrix",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "derivative of\nrotation matrix",
			"lineHeight": 1.25
		},
		{
			"id": "Y-8GUZf8vVK136IqIPP21",
			"type": "line",
			"x": 2930.4354471451315,
			"y": 801.5188833395573,
			"width": 103.4677349191702,
			"height": 17.994388681594728,
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
			"seed": 1544119038,
			"version": 33,
			"versionNonce": 1119338622,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				-103.4677349191702,
				5.623246462998395
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "YAl8Jsm2",
			"type": "text",
			"x": 2751.7378425269076,
			"y": 817.8262980822526,
			"width": 116.72026062011719,
			"height": 20,
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
			"seed": 1615776738,
			"version": 16,
			"versionNonce": 906038882,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "rotation by 90",
			"rawText": "rotation by 90",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "rotation by 90",
			"lineHeight": 1.25
		},
		{
			"id": "gFdl8vFM",
			"type": "text",
			"x": 2772.580168762873,
			"y": 921.8563576477229,
			"width": 312.33660888671875,
			"height": 20,
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
			"seed": 1275109182,
			"version": 71,
			"versionNonce": 1898381502,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "Angular velocity is the change of angle!",
			"rawText": "Angular velocity is the change of angle!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Angular velocity is the change of angle!",
			"lineHeight": 1.25
		},
		{
			"id": "7wAHL__1fOZ7IVwIzzrQM",
			"type": "arrow",
			"x": 3452.9812136884398,
			"y": 607.1884640445684,
			"width": 393.68285672978936,
			"height": 7.600055149223749,
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
			"seed": 1584129954,
			"version": 48,
			"versionNonce": 1498739234,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					393.68285672978936,
					7.600055149223749
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "nEGxm2Qy",
			"type": "text",
			"x": 3474.709575423293,
			"y": 553.6070380655921,
			"width": 331.648681640625,
			"height": 40,
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
			"seed": 155012862,
			"version": 123,
			"versionNonce": 1212430590,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "How do we update Those velocities\nin our simulation according to some force?",
			"rawText": "How do we update Those velocities\nin our simulation according to some force?",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "How do we update Those velocities\nin our simulation according to some force?",
			"lineHeight": 1.25
		},
		{
			"id": "Zf5EOpJ0vtW9PxHu2cX9t",
			"type": "image",
			"x": 3410.7075104244764,
			"y": 647.5350199274476,
			"width": 471.4755895010668,
			"height": 60.751810541437024,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1951442878,
			"version": 110,
			"versionNonce": 2012634594,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
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
			"id": "3KmYmaBd",
			"type": "text",
			"x": 3883.8394738298425,
			"y": 555.2209877093486,
			"width": 396.8795166015625,
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
			"seed": 1278601442,
			"version": 169,
			"versionNonce": 1871735102,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018378,
			"link": null,
			"locked": false,
			"text": "We have two components to keep in mind",
			"rawText": "We have two components to keep in mind",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "We have two components to keep in mind",
			"lineHeight": 1.25
		},
		{
			"id": "RRxtoLb3oOC_3mq0itpJe",
			"type": "line",
			"x": 4090.227089611374,
			"y": 653.763677902293,
			"width": 177.88662304514173,
			"height": 207.14429130914527,
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
			"seed": 974971042,
			"version": 100,
			"versionNonce": 1017485438,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				-170.86478266178074,
				207.14429130914527
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "psmBVPVZ3jGK-KPEfHNyQ",
			"type": "image",
			"x": 3809.1308954052774,
			"y": 902.3762341085824,
			"width": 218.12220962751138,
			"height": 80.07983220590452,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 761735522,
			"version": 75,
			"versionNonce": 530176190,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
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
			"id": "yxSSsWiH",
			"type": "text",
			"x": 3873.202657625466,
			"y": 872.6110365170398,
			"width": 94.659912109375,
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
			"seed": 1701128254,
			"version": 63,
			"versionNonce": 1385959678,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
			"link": null,
			"locked": false,
			"text": "Momentum",
			"rawText": "Momentum",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Momentum",
			"lineHeight": 1.25
		},
		{
			"id": "B-p1RG5A8NH4odZEGKF6Z",
			"type": "line",
			"x": 4091.3973963419344,
			"y": 653.763677902293,
			"width": 268.0002412982726,
			"height": 184.9084634285025,
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
			"seed": 630068642,
			"version": 191,
			"versionNonce": 288178494,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				268.0002412982726,
				184.9084634285025
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "QjoOdZOc",
			"type": "text",
			"x": 4333.327660833567,
			"y": 856.2267422891978,
			"width": 52.13995361328125,
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
			"seed": 934935522,
			"version": 36,
			"versionNonce": 2125359486,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
			"link": null,
			"locked": false,
			"text": "Force",
			"rawText": "Force",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Force",
			"lineHeight": 1.25
		},
		{
			"id": "iakFg3GmdymFbYeUqOmFQ",
			"type": "image",
			"x": 4228.348842001809,
			"y": 890.9222345674743,
			"width": 275.28310172610145,
			"height": 68.99678764490523,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 251579426,
			"version": 155,
			"versionNonce": 710969790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
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
			"id": "oWJXHJoO",
			"type": "text",
			"x": 3732.93557414389,
			"y": 979.9351547506982,
			"width": 394.87957763671875,
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
			"seed": 218056830,
			"version": 95,
			"versionNonce": 325362174,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
			"link": null,
			"locked": false,
			"text": "To Compute the total Linear Momentum",
			"rawText": "To Compute the total Linear Momentum",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "To Compute the total Linear Momentum",
			"lineHeight": 1.25
		},
		{
			"id": "2u97J0dZcyuAvkeBImvNV",
			"type": "image",
			"x": 3784.0142969936483,
			"y": 1037.28562513564,
			"width": 334.27998291830465,
			"height": 287.5752443316027,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1595372286,
			"version": 169,
			"versionNonce": 750498366,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
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
			"id": "SRcnSodQ9AyiOraCjiHXZ",
			"type": "line",
			"x": 3888.92353496623,
			"y": 1049.8994905577158,
			"width": 173.28754774038543,
			"height": 24.292646879493304,
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
			"seed": 1715983458,
			"version": 74,
			"versionNonce": 1632025214,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				-173.28754774038543,
				-3.2390195839325315
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "DT3xzdvk",
			"type": "text",
			"x": 3621.095138385039,
			"y": 1011.8410104465097,
			"width": 95.95988464355469,
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
			"seed": 709340322,
			"version": 116,
			"versionNonce": 398899902,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
			"link": null,
			"locked": false,
			"text": "sum over \nindividual\nparticles",
			"rawText": "sum over \nindividual\nparticles",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "sum over \nindividual\nparticles",
			"lineHeight": 1.25
		},
		{
			"id": "-A1nepSsVrwtCYzHn1Ntz",
			"type": "line",
			"x": 4051.733178302198,
			"y": 1215.0280007929803,
			"width": 147.62378840334895,
			"height": 46.52010138761011,
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
			"seed": 637363326,
			"version": 68,
			"versionNonce": 920433406,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				147.62378840334895,
				37.52621511933876
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "I93VcHrU",
			"type": "text",
			"x": 4148.259989852705,
			"y": 1202.4982746639232,
			"width": 270.5445556640625,
			"height": 100,
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
			"seed": 570585058,
			"version": 224,
			"versionNonce": 688497470,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
			"link": null,
			"locked": false,
			"text": "Sum of the differences\nto the center of mass\nincluding the pass\nwhich is exactly how we define the\ncenter of mass!!",
			"rawText": "Sum of the differences\nto the center of mass\nincluding the pass\nwhich is exactly how we define the\ncenter of mass!!",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 94,
			"containerId": null,
			"originalText": "Sum of the differences\nto the center of mass\nincluding the pass\nwhich is exactly how we define the\ncenter of mass!!",
			"lineHeight": 1.25
		},
		{
			"id": "5j8ab0G1pZ6xETSkjrp4e",
			"type": "image",
			"x": 4210.793457333254,
			"y": 958.9605898489883,
			"width": 302.2026116486776,
			"height": 221.54886685940943,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1343344802,
			"version": 116,
			"versionNonce": 1622051710,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818022598,
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
			"id": "nIuMkzDH",
			"type": "text",
			"x": 3881.3073949558093,
			"y": 584.314540637698,
			"width": 405.6648254394531,
			"height": 60,
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
			"seed": 1815153506,
			"version": 127,
			"versionNonce": 708721726,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818018379,
			"link": null,
			"locked": false,
			"text": "The Linear dynamics of the object and the Angular\ndynamics of the object!\nEach of which gets a contribution from two things",
			"rawText": "The Linear dynamics of the object and the Angular\ndynamics of the object!\nEach of which gets a contribution from two things",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "The Linear dynamics of the object and the Angular\ndynamics of the object!\nEach of which gets a contribution from two things",
			"lineHeight": 1.25
		},
		{
			"id": "wTlAku18",
			"type": "text",
			"x": 4103.163667989676,
			"y": 791.3027584477378,
			"width": 82.0123291015625,
			"height": 35,
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
			"seed": 692339710,
			"version": 15,
			"versionNonce": 2051375074,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818042756,
			"link": null,
			"locked": false,
			"text": "Linear",
			"rawText": "Linear",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Linear",
			"lineHeight": 1.25
		},
		{
			"id": "762BKQ_vvNN3rjcfdtLCE",
			"type": "line",
			"x": 4410.523168652558,
			"y": 579.1780777939,
			"width": 982.4699810099874,
			"height": 311.9137751839081,
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
			"seed": 1855915454,
			"version": 581,
			"versionNonce": 878273790,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818109453,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				808.4057394279571,
				308.4091260245383
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "O9AWCny_uUKO-MXvj7fEq",
			"type": "line",
			"x": 5056.546830363049,
			"y": 714.6911786228637,
			"width": 262.84868695273144,
			"height": 198.59678569761945,
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
			"seed": 757646398,
			"version": 235,
			"versionNonce": 596894946,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818112786,
			"link": null,
			"locked": false,
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
			],
			"lastCommittedPoint": [
				-258.175821406905,
				213.783598721555
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "P90JzOp0",
			"type": "text",
			"x": 4747.983559987171,
			"y": 922.6366001962832,
			"width": 94.659912109375,
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
			"seed": 1789236322,
			"version": 50,
			"versionNonce": 811348322,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818170324,
			"link": null,
			"locked": false,
			"text": "Momentum",
			"rawText": "Momentum",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Momentum",
			"lineHeight": 1.25
		},
		{
			"id": "c7umexbr",
			"type": "text",
			"x": 5032.51938804527,
			"y": 838.194981133088,
			"width": 99.45640563964844,
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
			"seed": 1882770722,
			"version": 11,
			"versionNonce": 300449854,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818127256,
			"link": null,
			"locked": false,
			"text": "Angular",
			"rawText": "Angular",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Angular",
			"lineHeight": 1.25
		},
		{
			"id": "79w61s0K",
			"type": "text",
			"x": 5194.966370564302,
			"y": 901.9436585004878,
			"width": 400.0595703125,
			"height": 50,
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
			"seed": 915933374,
			"version": 69,
			"versionNonce": 2054746686,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818166110,
			"link": null,
			"locked": false,
			"text": "Torque\n(Force that affects the angular state)",
			"rawText": "Torque\n(Force that affects the angular state)",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "Torque\n(Force that affects the angular state)",
			"lineHeight": 1.25
		},
		{
			"id": "vwa0bwhiPIYX0hk9RoBXv",
			"type": "image",
			"x": 4990.888636322088,
			"y": 885.0554160921245,
			"width": 185.30655389862662,
			"height": 157.46492880548325,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2049229026,
			"version": 88,
			"versionNonce": 209775678,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818247420,
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
			"id": "IgjS9LqM",
			"type": "text",
			"x": 4976.538162518057,
			"y": 1052.1778416614934,
			"width": 196.9444122314453,
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
			"seed": 467491426,
			"version": 64,
			"versionNonce": 710147134,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818262134,
			"link": null,
			"locked": false,
			"text": "Which is the projection\nof the angular momentum",
			"rawText": "Which is the projection\nof the angular momentum",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Which is the projection\nof the angular momentum",
			"lineHeight": 1.25
		},
		{
			"id": "Ef-7qTGw4yONHypDp5mRV",
			"type": "image",
			"x": 4705.964542952494,
			"y": 957.4095548254397,
			"width": 247.95701966092818,
			"height": 266.47911028620234,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 257197246,
			"version": 64,
			"versionNonce": 242744638,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818348337,
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
			"id": "x98zRfpjx2xHU_jQzm8I0",
			"type": "line",
			"x": 4814.252596170034,
			"y": 1215.670632974247,
			"width": 49.02125322413485,
			"height": 18.609920205458593,
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
			"seed": 49446178,
			"version": 31,
			"versionNonce": 978305726,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818443325,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					49.02125322413485,
					18.609920205458593
				]
			],
			"lastCommittedPoint": [
				49.02125322413485,
				18.609920205458593
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "UHtGw2xB",
			"type": "text",
			"x": 4794.8497008345985,
			"y": 1234.2805531797055,
			"width": 136.84829711914062,
			"height": 20,
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
			"seed": 1535571362,
			"version": 21,
			"versionNonce": 2029452258,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1706818444844,
			"link": null,
			"locked": false,
			"text": "moment of inertia",
			"rawText": "moment of inertia",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "moment of inertia",
			"lineHeight": 1.25
		},
		{
			"id": "YwICZrpeHFQRouCDouOfe",
			"type": "image",
			"x": 2660.9869056203424,
			"y": 568.5319673047455,
			"width": 563.9213187606518,
			"height": 306.7640743106478,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1183212158,
			"version": 179,
			"versionNonce": 1675418366,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818018379,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6e3a3fe6601767719e97fcba8e5cd3b5eb911e41",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "f899EpXNsCjbWZmuC-ObP",
			"type": "image",
			"x": 2447.0041391770596,
			"y": 0.8284484652278792,
			"width": 338.4618686111769,
			"height": 56.059936830008596,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 698113314,
			"version": 75,
			"versionNonce": 2033245154,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818018379,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8d82cd4ee1def5bcb72e067ef50461279e42d432",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "9U3IrMhVDLEqq1kJakzTO",
			"type": "line",
			"x": 2593.968992201767,
			"y": 77.3874376230981,
			"width": 208.76223393857208,
			"height": 32.117266759780364,
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
			"seed": 89392802,
			"version": 47,
			"versionNonce": 331664190,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818018379,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-76.64347749493027,
					32.117266759780364
				],
				[
					-208.76223393857208,
					31.387328878876247
				]
			],
			"lastCommittedPoint": [
				-208.76223393857208,
				31.387328878876247
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "A8QxCCbH",
			"type": "text",
			"x": 2596.2683786402026,
			"y": 117.53402107282352,
			"width": 9.999984741210938,
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
			"seed": 1945612862,
			"version": 4,
			"versionNonce": 271519650,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818018379,
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
			"id": "TAxecWUxNCQto4jgjxRAM",
			"type": "freedraw",
			"x": 2820.7412868815063,
			"y": 120.85249354905638,
			"width": 27.339004768447012,
			"height": 18.985419978088245,
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
			"seed": 202650814,
			"version": 30,
			"versionNonce": 432321406,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818018379,
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
					2.2782503973705843
				],
				[
					0,
					3.7970839956176405
				],
				[
					0,
					4.556500794741169
				],
				[
					-0.7594167991233007,
					5.315917593864697
				],
				[
					-1.5188335982466015,
					6.834751192111781
				],
				[
					-2.278250397370357,
					8.353584790358852
				],
				[
					-3.797083995617413,
					9.11300158948238
				],
				[
					-4.556500794740714,
					9.872418388605908
				],
				[
					-6.075334392988225,
					11.391251986852964
				],
				[
					-8.353584790358582,
					12.150668785976492
				],
				[
					-9.872418388605638,
					12.91008558510002
				],
				[
					-11.391251986852694,
					12.91008558510002
				],
				[
					-12.91008558509975,
					13.669502384223549
				],
				[
					-14.428919183346807,
					14.428919183347077
				],
				[
					-15.947752781593863,
					15.188335982470605
				],
				[
					-17.46658637984092,
					15.188335982470605
				],
				[
					-19.744836777211276,
					15.947752781594133
				],
				[
					-20.50425357633503,
					16.70716958071766
				],
				[
					-22.023087174582088,
					16.70716958071766
				],
				[
					-22.78250397370539,
					17.46658637984119
				],
				[
					-25.0607543710762,
					18.226003178964717
				],
				[
					-25.8201711701995,
					18.226003178964717
				],
				[
					-26.579587969323256,
					18.985419978088245
				],
				[
					-27.339004768447012,
					18.985419978088245
				],
				[
					-27.339004768447012,
					18.985419978088245
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-27.339004768447012,
				18.985419978088245
			]
		},
		{
			"id": "qqJ98Ncf",
			"type": "text",
			"x": 2340.365987199542,
			"y": 431.36826241830397,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 715656994,
			"version": 3,
			"versionNonce": 1487981410,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818018379,
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
			"id": "XOrAm4Bb",
			"type": "text",
			"x": 2931.6091823006363,
			"y": 426.4738651078644,
			"width": 9.999984741210938,
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
			"seed": 227361570,
			"version": 3,
			"versionNonce": 1612551102,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818018379,
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
			"id": "d8Kd3WbF",
			"type": "text",
			"x": 2923.30675045494,
			"y": 486.6245422133397,
			"width": 9.999984741210938,
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
			"seed": 2037553278,
			"version": 3,
			"versionNonce": 1761939234,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818018379,
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
			"id": "0h6gsx5S",
			"type": "text",
			"x": 3850.3450642093894,
			"y": 868.6341890836313,
			"width": 9.999984741210938,
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
			"seed": 1249955362,
			"version": 3,
			"versionNonce": 1626369022,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818018379,
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
			"id": "uF9Vw5Cz",
			"type": "text",
			"x": 4290.380394900003,
			"y": 846.3983612029886,
			"width": 9.999984741210938,
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
			"seed": 436900002,
			"version": 3,
			"versionNonce": 899341026,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818018379,
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
			"id": "F0OvijqcDr6Sy-74uKscf",
			"type": "arrow",
			"x": 4336.925536305794,
			"y": 600.2059727501185,
			"width": 400.69822055460827,
			"height": 95.7937436894399,
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
			"seed": 882153570,
			"version": 121,
			"versionNonce": 476659106,
			"isDeleted": true,
			"boundElements": [],
			"updated": 1706818059202,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					351.6331323234317,
					-10.51394747810923
				],
				[
					400.69822055460827,
					85.27979621133068
				]
			],
			"lastCommittedPoint": [
				400.69822055460827,
				85.27979621133068
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "viByRFu5",
			"type": "text",
			"x": 4681.558638111647,
			"y": 572.1920252720092,
			"width": 14.00006103515625,
			"height": 35,
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
			"seed": 769542882,
			"version": 2,
			"versionNonce": 1846086910,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818058722,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 25,
			"containerId": "F0OvijqcDr6Sy-74uKscf",
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "2IFR9NRO",
			"type": "text",
			"x": 5100.948320849561,
			"y": 905.110449615287,
			"width": 14.00006103515625,
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
			"seed": 1340220222,
			"version": 2,
			"versionNonce": 384824162,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818071196,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		},
		{
			"id": "cQW8W7Ez",
			"type": "text",
			"x": 4682.726854498103,
			"y": 923.8019117985924,
			"width": 14.00006103515625,
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
			"seed": 1578695166,
			"version": 2,
			"versionNonce": 1765163170,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1706818088395,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "",
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
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": -3931.015848865555,
		"scrollY": -862.3804458354923,
		"zoom": {
			"value": 1.0207140583384198
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