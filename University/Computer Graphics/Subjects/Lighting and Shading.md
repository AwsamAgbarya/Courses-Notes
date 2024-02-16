---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Lighting and Shading ^dSSxyy0j

What is shading? ^Vwvij5lI

Shading is the calculation of the colour value of
a primitive according to physical law simulations
usually dictating how bright/how dark the original
colour is considering the conditions it is at. ^0e3RGCzP

What is Lighting? ^19qQu8QC

Lighting is applying some simulation of a type of
a light source and preforming shading on all
primitives within the scene given their material
and the properties that this light source provides. ^JOgZb8Z6

Types of
Light sources ^4XRmyxPC

Directed Light ^WJwZ2CaA

Position of the light source is at infinity
meaning all light rays are parallel mimicking the sun ^Yw9ARyiX

Ambient Light ^Fa90n1wA

Light comes from every direction 
all at once, this lead to the object
being lit from every side without any
shadows ^98x0N8WU

Point light ^0cZlZiiO

Point light is a light source that originates
from a finite point in space and illuminates
the rest of the space according to the 
direction of the object to that finite point ^ytKSD5f6

This can also can be limited to a specific
angle also known as spotlight ^KCdiyY6j

If we want to make this more realistic
we can simulate point light source
but as a line or a plane to
form shadows ^g5LFYXmy

Image based Lighting ^9VCujaAD

A more realistic simulation on ambient light where we
have a half-sphere of point lights that have different variables
and emit light from infinite points ^xxloJTHy

Types of reflection ^3iuFok3h

Diffuse Reflection ^RoHoBkTM

Specular Reflection ^2UUApPFF

Ideal Specular Reflection ^ApFiDUEs

reflection in an ideal manner (mirror-like)
without any diffuse of the light ray ^6fyg7RJ8

Glossy reflection where the light reflects
in a similar direction that it came from 
but it also heads in other different similar
directions (the more variation the less glossy) ^kC8Uqmlq

Light reflects equally in all directions
and thus has not glossiness to it but
looks illuminated from the light ^YOPUQe2N

Sometimes we combine different variations of these
reflection types in order to get something more realistic! ^advzfjV0

Lambert Ideal diffuse relfection! ^h2LgM7Ca

Reflected radiance is independent of reflection direction!
 it is based off of the angle between the normal and
 the light source ^7rQ3a7st

Radiance is light energy per angle per area ^pzSTHA10

Lin ^hstkn6Nk

L(diff) = L(in) * kd * cos(theta) ^MnEgpBAA

output
color ^yVo8FjPw

Input light
source color ^LVa0YIZl

Surface
color ^lIgoAVxh

Angle between norm
and light source

dot ( n , l )
if both n and l are normalized ^3tfArFCM

Phong Specular Reflection ^fNuczZ3v

Light ray and the reflected ray off of the surface
should have the same angle off of the surface normal
and should exist in a common plane together ^OESwOnPV

Lin ^l3srV0Py

How do I find the reflection ray? ^KrlOQ77m

r = 2p - l and p = n * dot(n,l)

therefore 

r = 2 (n * dot(n,l)) - l

 ^UAC3ueXs

Reflection vs Refraction ^WE0MMMVM

Refraction is when the reflected ray goes through
the medium it hits and passes through it to the other
side given a certain angle ^ZMQhiqY3

V.S ^mqbtk1up

Reflection is when the light ray bounces off of the surface
of the object it hits and reflects the color that it
hit the object with from the light source ^SsA65PiV

The angle of refraction is quite important, an ideal one would not change direction
at all and thus having perfect refraction and is transparent but that more often
than not is not the case and the medium ends up bending the light source
which gives off that glass refraction effect (or like water)
if the angle is too large however the medium becomes black ^s99id0sJ

Phong Illumination Model ^yJPDlVtN

Phong illumination model is the sum of three parts
 ^RM2yYWDB

L(out) = Lambient + Ldiffuse + Lspecular ^IbIg8igJ

Viewer ^Uqog7Aw6

Lspec = ks * cos( gamma ) ^xyxIaE9V

m ^2N1Y3Xu7

output
color ^92OCNybt

Specular
color ^L2g2fX60

Angle between viwer
and reflected ray

dot ( v , r )
if both r and v are normalized ^B97FmeJa

Describes shinyness
or how quickly the reflection
falls off with larger angles ^0rw9Gx8h

If Theta1 is larger than 90 our specular
needs to be set to zero because we do not
want any light coming from under the surface ^8YhS8lBh

if our gamma is bigger than 90 in either
direction we set specular to zero because
our cosine will have negative color effects
on our object ^J3I095EH

Blinn suggests that ^PK5PPMLs

Instead of computing the reflection vector which
has a lot of operations, we compute the half
vector for a more efficient way ^04qdqj1G

Lin ^i3pHyzt1

h = normalized(v+l) ^QvQfDfWv

Lspec = ks * cos( gamma ) ^wRIjbxZ9

n ^7a6dKe6L

Angle between bisector h
and norm 

dot ( n , h )
if both r and v are normalized ^g7v7cCCb

Micro-facet theory ^JjrQfqPo

Micro-facet theory suggests that on a magnified scale, surfaces are made
out of very small micro facets that can shadow each other by blocking light
and can occlude one another from the viewer ^LJF1cfND

Cook-Torrance model! ^xruNSttX

Lout = Lin * (kd / PI + fs) *  max(0,dot(n,l)) ^Pq7HN62F

light
input ^hwxR8geE

light
output ^qJypDx4Z

surface
color ^Spk9c1Pg

Removal of negative 
light computation ^t25okWaH

 D F G
fs = ___________________
4 * |dot(n,l)| * |dot(n,v)| ^fMW5SPeh

D  is the normal distribution function (NDF)
that describes which fraction of
facets are aligned with the half vector ^xTYrDY4S

G  is the fraction of microfacets
not occluded or shadowed by other facets

Since Occlusion and shadowing are two different cases
we usually preform this function twice over occlusion and over shadowing and
multiply both
Occlusion is between the viewer and the normals
Shadowing is between the light and the normals

This function is heavily dependent on the distribution D ^zmGJD72v

F is the Fersnel effect where for unpolarized
light and dielectric materials we often see stronger
reflection the larger the angle is the viewer is at
even if the material is not glossy ^xPgAZFpQ

F0 is the reflectance at
normal incidence ^OjfJfXNJ

Gourard Shading vs Phong Shading ^RfcRwZyl

Gourard shading is computed over each Vertex in the mesh
and then further interpolated from one vertex to another
thus leaving artefacts in the mesh that look undetailed
and the vertices are always the shinest points
 ^VeVcUUJH

V.S ^Vfl4lRa7

Phong shading interpolates the actual normals from
vertices to every point in the triangle and then
the color is calculated in them individually ^TDWR32dQ


this is a lot more obvious when we dont
have many triangles in the mesh ^Rl4oyqqq


# Embedded files
7d137ba381113ff98b3e873dece9de75a22aebdd: [[Pasted Image 20231218143315_183.png]]
f788cb0eef590d8efa19cb9e6f696f6429103571: [[Pasted Image 20231218154546_690.png]]
7500b16ec165f59eb1ee266e9ddafa8a55990808: [[Pasted Image 20231218164606_094.png]]
853868975882718a7db6762cbb2c5ea2165208a3: [[Pasted Image 20231218164951_118.png]]
0af0f4ccf8fd37034a752bdfdeba7583c2992c60: [[Pasted Image 20231218165121_130.png]]
00bd6412e85bb066897051fada072b571ef86d95: [[Pasted Image 20231218165209_144.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.3",
	"elements": [
		{
			"type": "arrow",
			"version": 311,
			"versionNonce": 693085863,
			"isDeleted": false,
			"id": "-KHEt9ghWWSRnifwqMqda",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -770.6712196025156,
			"y": 1000.8831993750136,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 25.657367177756036,
			"height": 22.374753770619257,
			"seed": 1636853159,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					-25.657367177756036,
					-22.374753770619257
				]
			]
		},
		{
			"type": "arrow",
			"version": 310,
			"versionNonce": 299940681,
			"isDeleted": false,
			"id": "4wQVWqj3jcMma80erftcT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -771.9133600010757,
			"y": 1001.7161929752913,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 34.81973778305614,
			"height": 12.795911774169095,
			"seed": 367204551,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					-34.81973778305614,
					-12.795911774169095
				]
			]
		},
		{
			"type": "arrow",
			"version": 425,
			"versionNonce": 101857735,
			"isDeleted": false,
			"id": "3wfhjqrOjnC8bkYGQiXdz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -769.9919231338315,
			"y": 1001.3195461778043,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 15.662053790155918,
			"height": 32.578302853794284,
			"seed": 263350247,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					-15.662053790155918,
					-32.578302853794284
				]
			]
		},
		{
			"type": "arrow",
			"version": 248,
			"versionNonce": 1184655913,
			"isDeleted": false,
			"id": "CGfYpCXE4W7bz6WWO5908",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -770.4528630975316,
			"y": 1001.7678085438624,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 25.657367177755997,
			"height": 22.374753770619225,
			"seed": 755684103,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					25.657367177755997,
					-22.374753770619225
				]
			]
		},
		{
			"type": "arrow",
			"version": 247,
			"versionNonce": 1330997479,
			"isDeleted": false,
			"id": "XGIoP88oA79PrZAgg-_dt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -769.268707655057,
			"y": 1002.6008021441398,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 34.819737783056084,
			"height": 12.795911774169076,
			"seed": 1449712167,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					34.819737783056084,
					-12.795911774169076
				]
			]
		},
		{
			"type": "arrow",
			"version": 362,
			"versionNonce": 163527945,
			"isDeleted": false,
			"id": "rzVAut-liSsq3c75W5fMh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -771.457743537794,
			"y": 1002.2041553466531,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 15.662053790155895,
			"height": 32.578302853794234,
			"seed": 817429831,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					15.662053790155895,
					-32.578302853794234
				]
			]
		},
		{
			"type": "arrow",
			"version": 338,
			"versionNonce": 1655026695,
			"isDeleted": false,
			"id": "tiktqXhadnhcy5AmMIAYK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -928.1830346765478,
			"y": 1003.2989360916816,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 40.836465834505,
			"height": 35.61183271764157,
			"seed": 263322473,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					-40.836465834505,
					-35.61183271764157
				]
			]
		},
		{
			"type": "arrow",
			"version": 337,
			"versionNonce": 1254405097,
			"isDeleted": false,
			"id": "PN5vkVGi8zlUNhFjdF1el",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -930.1600350287677,
			"y": 1004.6247352067045,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 55.41936639457463,
			"height": 20.366073041205055,
			"seed": 1418765897,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					-55.41936639457463,
					-20.366073041205055
				]
			]
		},
		{
			"type": "arrow",
			"version": 452,
			"versionNonce": 939498279,
			"isDeleted": false,
			"id": "WgUC7KiocaHTJk395pQb5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -927.1018611156468,
			"y": 1003.9934290683266,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 24.927847041701767,
			"height": 51.85188106862805,
			"seed": 571929897,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					-24.927847041701767,
					-51.85188106862805
				]
			]
		},
		{
			"type": "arrow",
			"version": 275,
			"versionNonce": 2109230793,
			"isDeleted": false,
			"id": "SB6ppZNOduVxFMpYbyqoP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -927.8354967591246,
			"y": 1004.7068869484596,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 40.83646583450494,
			"height": 35.61183271764152,
			"seed": 1269852169,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					40.83646583450494,
					-35.61183271764152
				]
			]
		},
		{
			"type": "arrow",
			"version": 274,
			"versionNonce": 332373575,
			"isDeleted": false,
			"id": "n60N5NmOM2G8heDvFqjqg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -925.9507857155347,
			"y": 1006.0326860634825,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 55.41936639457454,
			"height": 20.36607304120502,
			"seed": 727219945,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					55.41936639457454,
					-20.36607304120502
				]
			]
		},
		{
			"type": "arrow",
			"version": 389,
			"versionNonce": 154504617,
			"isDeleted": false,
			"id": "-AJPYZkDqi5ip4oZCljV-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -929.4348723101015,
			"y": 1005.4013799251045,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 24.927847041701725,
			"height": 51.85188106862798,
			"seed": 1335540169,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					24.927847041701725,
					-51.85188106862798
				]
			]
		},
		{
			"type": "arrow",
			"version": 220,
			"versionNonce": 2029141351,
			"isDeleted": false,
			"id": "x46__-C0ktZlNXh3Wl5Ty",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -429.03362153794325,
			"y": 565.5503979765061,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 53.85038897982733,
			"height": 46.96074953942657,
			"seed": 1722058247,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					-53.85038897982733,
					-46.96074953942657
				]
			]
		},
		{
			"type": "arrow",
			"version": 219,
			"versionNonce": 1952968841,
			"isDeleted": false,
			"id": "bp7WghHn-0zSYflUJM0oq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -431.64066002192345,
			"y": 567.2987078900633,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 73.08062478907681,
			"height": 26.856412102483816,
			"seed": 945040679,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					-73.08062478907681,
					-26.856412102483816
				]
			]
		},
		{
			"type": "arrow",
			"version": 334,
			"versionNonce": 1521744007,
			"isDeleted": false,
			"id": "oAeckKeJIk0Q07JZr7jal",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -427.60789539785134,
			"y": 566.4662146656304,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 32.871949915191514,
			"height": 68.37623941790876,
			"seed": 2143416391,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989884,
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
					-32.871949915191514,
					-68.37623941790876
				]
			]
		},
		{
			"type": "ellipse",
			"version": 193,
			"versionNonce": 1426782057,
			"isDeleted": false,
			"id": "DdzJeXlLkO1O6bGCc6h4o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -269,
			"y": -421.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 525,
			"height": 261,
			"seed": 672004233,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "dSSxyy0j"
				}
			],
			"updated": 1702914989884,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 155,
			"versionNonce": 248598439,
			"isDeleted": false,
			"id": "dSSxyy0j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -182.88960843060937,
			"y": -313.03524744484446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 352.54815673828125,
			"height": 45,
			"seed": 1992311753,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989884,
			"link": null,
			"locked": false,
			"fontSize": 36,
			"fontFamily": 1,
			"text": "Lighting and Shading",
			"rawText": "Lighting and Shading",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "DdzJeXlLkO1O6bGCc6h4o",
			"originalText": "Lighting and Shading",
			"lineHeight": 1.25,
			"baseline": 32
		},
		{
			"type": "text",
			"version": 182,
			"versionNonce": 2104107593,
			"isDeleted": false,
			"id": "Vwvij5lI",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -384.0018720874111,
			"y": -79.26189686830469,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 228.48092651367188,
			"height": 35,
			"seed": 832571335,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is shading?",
			"rawText": "What is shading?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is shading?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 395,
			"versionNonce": 2138489543,
			"isDeleted": false,
			"id": "0e3RGCzP",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -528.0517856894511,
			"y": -19.186290949268425,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 485.09942626953125,
			"height": 100,
			"seed": 853481321,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Shading is the calculation of the colour value of\na primitive according to physical law simulations\nusually dictating how bright/how dark the original\ncolour is considering the conditions it is at.",
			"rawText": "Shading is the calculation of the colour value of\na primitive according to physical law simulations\nusually dictating how bright/how dark the original\ncolour is considering the conditions it is at.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Shading is the calculation of the colour value of\na primitive according to physical law simulations\nusually dictating how bright/how dark the original\ncolour is considering the conditions it is at.",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 256,
			"versionNonce": 1784738089,
			"isDeleted": false,
			"id": "19qQu8QC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 191.40827913099673,
			"y": -79.77898368314624,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 231.4209442138672,
			"height": 35,
			"seed": 506229801,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is Lighting?",
			"rawText": "What is Lighting?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is Lighting?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 697,
			"versionNonce": 490787303,
			"isDeleted": false,
			"id": "JOgZb8Z6",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 39.108335011378585,
			"y": -19.703377764109945,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ced4da",
			"width": 501.5994873046875,
			"height": 100,
			"seed": 1186858761,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "YNJwpUGDL3qHWcnjUXj7h",
					"type": "arrow"
				}
			],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lighting is applying some simulation of a type of\na light source and preforming shading on all\nprimitives within the scene given their material\nand the properties that this light source provides.",
			"rawText": "Lighting is applying some simulation of a type of\na light source and preforming shading on all\nprimitives within the scene given their material\nand the properties that this light source provides.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lighting is applying some simulation of a type of\na light source and preforming shading on all\nprimitives within the scene given their material\nand the properties that this light source provides.",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 279,
			"versionNonce": 1901782025,
			"isDeleted": false,
			"id": "YNJwpUGDL3qHWcnjUXj7h",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 549.099877388272,
			"y": -11.35370245997683,
			"strokeColor": "#e03131",
			"backgroundColor": "#ced4da",
			"width": 264.72983467047504,
			"height": 296.5427916245561,
			"seed": 1802810759,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JOgZb8Z6",
				"focus": 0.43419449348298195,
				"gap": 8.392055072205949
			},
			"endBinding": {
				"elementId": "vO0OUQMYyDebOgdiFJxKz",
				"gap": 1.38307312620951,
				"focus": 0.19827018098082588
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
					115.89028332607882,
					-48.85570767668037
				],
				[
					122.70735881584824,
					-280.63627432883794
				],
				[
					264.72983467047504,
					-296.5427916245561
				]
			]
		},
		{
			"type": "ellipse",
			"version": 114,
			"versionNonce": 289144071,
			"isDeleted": false,
			"id": "vO0OUQMYyDebOgdiFJxKz",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 814.9658214892763,
			"y": -390.83757139047026,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 204.51226469308017,
			"height": 178.3801419822978,
			"seed": 206448521,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "YNJwpUGDL3qHWcnjUXj7h",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "4XRmyxPC"
				},
				{
					"id": "LAfvka4rfNW1yQFIPBzpr",
					"type": "arrow"
				},
				{
					"id": "Wnv_FVoo6MUqdAaC9isNd",
					"type": "arrow"
				},
				{
					"id": "pjvPE-Q9j58unCFjiB5E5",
					"type": "arrow"
				},
				{
					"id": "FjDBGZGFnMGEpvd8cUcYy",
					"type": "arrow"
				}
			],
			"updated": 1702914989885,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 777222889,
			"isDeleted": false,
			"id": "4XRmyxPC",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 851.7660240037352,
			"y": -326.7144044116723,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 131.2998504638672,
			"height": 50,
			"seed": 2082385289,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Types of\nLight sources",
			"rawText": "Types of\nLight sources",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "vO0OUQMYyDebOgdiFJxKz",
			"originalText": "Types of\nLight sources",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 466,
			"versionNonce": 786744359,
			"isDeleted": false,
			"id": "LAfvka4rfNW1yQFIPBzpr",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 914.8980526749915,
			"y": -211.47319448485717,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 2.272772108477284,
			"height": 121.59221101153472,
			"seed": 1837658249,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "vO0OUQMYyDebOgdiFJxKz",
				"gap": 1.0070783826259913,
				"focus": 0.0019566065679876158
			},
			"endBinding": {
				"elementId": "WJwZ2CaA",
				"focus": 0.057733040622191166,
				"gap": 5.196798027302549
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
					-1.7787878053156874,
					75.52602384782708
				],
				[
					-2.272772108477284,
					121.59221101153472
				]
			]
		},
		{
			"type": "text",
			"version": 83,
			"versionNonce": 836122057,
			"isDeleted": false,
			"id": "WJwZ2CaA",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 837.9951765053296,
			"y": -84.68418544601991,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 140.73985290527344,
			"height": 25,
			"seed": 914002889,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "LAfvka4rfNW1yQFIPBzpr",
					"type": "arrow"
				}
			],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Directed Light",
			"rawText": "Directed Light",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Directed Light",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 167,
			"versionNonce": 640132935,
			"isDeleted": false,
			"id": "Yw9ARyiX",
			"fillStyle": "cross-hatch",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 709.814481163726,
			"y": -51.42497999269767,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 402.33685302734375,
			"height": 40,
			"seed": 1310525929,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Position of the light source is at infinity\nmeaning all light rays are parallel mimicking the sun",
			"rawText": "Position of the light source is at infinity\nmeaning all light rays are parallel mimicking the sun",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Position of the light source is at infinity\nmeaning all light rays are parallel mimicking the sun",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "ellipse",
			"version": 132,
			"versionNonce": 1862177961,
			"isDeleted": false,
			"id": "_d0yqPEQh2qSqOgU3bg52",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 949.1513554311114,
			"y": 11.619933447392398,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 32.72385331765702,
			"height": 30.04644713712152,
			"seed": 1439377481,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 127,
			"versionNonce": 1969301095,
			"isDeleted": false,
			"id": "h1YS-ZMc9RTbgvdl3Vnnr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 964.9144279976697,
			"y": 47.88353541950329,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 0.16479187659501804,
			"height": 9.722720719101176,
			"seed": 721908681,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.16479187659501804,
					9.722720719101176
				]
			]
		},
		{
			"type": "line",
			"version": 128,
			"versionNonce": 1769478025,
			"isDeleted": false,
			"id": "osPpV-ZdAq4efM-HbScbC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 953.2142047594293,
			"y": 43.43415475144003,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 9.063553212721445,
			"height": 9.063553212721445,
			"seed": 2032054505,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-9.063553212721445,
					9.063553212721445
				]
			]
		},
		{
			"type": "line",
			"version": 93,
			"versionNonce": 459129223,
			"isDeleted": false,
			"id": "V2SrBtFqCTa0fQQxzTDV7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 942.5027327807585,
			"y": 33.71143403233885,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 9.88751259569608,
			"height": 2.1422943957341616,
			"seed": 2681065,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-9.88751259569608,
					2.1422943957341616
				]
			]
		},
		{
			"type": "line",
			"version": 101,
			"versionNonce": 595476073,
			"isDeleted": false,
			"id": "4HI7UHvgrvII3e-i5lJ-f",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 943.656275916923,
			"y": 22.011210794098446,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 12.3593907446201,
			"height": 0.9887512595696109,
			"seed": 1462791241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.3593907446201,
					-0.9887512595696109
				]
			]
		},
		{
			"type": "line",
			"version": 96,
			"versionNonce": 156891303,
			"isDeleted": false,
			"id": "vLQtirUqJnGke7qg3oE8c",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 948.1056565849863,
			"y": 10.970155062237787,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 6.921258816987233,
			"height": 7.745218199961961,
			"seed": 4371111,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.921258816987233,
					-7.745218199961961
				]
			]
		},
		{
			"type": "line",
			"version": 101,
			"versionNonce": 1272744265,
			"isDeleted": false,
			"id": "sHp1UVMhvKFfm-sNPBsgN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 958.4875448104673,
			"y": 6.685566270769467,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 4.119796914873405,
			"height": 11.370639485050535,
			"seed": 1619692809,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.119796914873405,
					-11.370639485050535
				]
			]
		},
		{
			"type": "line",
			"version": 112,
			"versionNonce": 1426213831,
			"isDeleted": false,
			"id": "cfQztX7uLzmBmsIczMjiy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 968.3750574061634,
			"y": 5.202439381415047,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 0.3295837531899224,
			"height": 12.19459886802521,
			"seed": 84682215,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.3295837531899224,
					-12.19459886802521
				]
			]
		},
		{
			"type": "line",
			"version": 97,
			"versionNonce": 737048617,
			"isDeleted": false,
			"id": "xITtKD3QZOPowSQebpogt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 977.4386106188848,
			"y": 8.168693160123883,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 11.205847608455656,
			"height": 8.239593829746763,
			"seed": 727157705,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					11.205847608455656,
					-8.239593829746763
				]
			]
		},
		{
			"type": "line",
			"version": 100,
			"versionNonce": 712194791,
			"isDeleted": false,
			"id": "wKY1kU8kSNcX-hwmukIYw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 984.0302856826822,
			"y": 15.91391136008584,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 15.984812029708678,
			"height": 2.1422943957341545,
			"seed": 94758567,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					15.984812029708678,
					-2.1422943957341545
				]
			]
		},
		{
			"type": "line",
			"version": 115,
			"versionNonce": 1436519177,
			"isDeleted": false,
			"id": "HfrTsV5H0-oJPcmfNbm6K",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 986.1725800784163,
			"y": 26.4605914621617,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 18.291898302037907,
			"height": 0.4943756297848054,
			"seed": 477908105,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					18.291898302037907,
					0.4943756297848054
				]
			]
		},
		{
			"type": "line",
			"version": 105,
			"versionNonce": 2117682695,
			"isDeleted": false,
			"id": "gCZ6um7wopzIOgvHCE1fI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 983.0415344231126,
			"y": 36.018520304667945,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 16.149603906303696,
			"height": 7.580426323367021,
			"seed": 628291369,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.149603906303696,
					7.580426323367021
				]
			]
		},
		{
			"type": "line",
			"version": 104,
			"versionNonce": 292241897,
			"isDeleted": false,
			"id": "PKk6PrdqHPQjLe5leXR5g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 975.7906918529354,
			"y": 43.76373850462991,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 8.733969459531636,
			"height": 11.86501511483533,
			"seed": 839282247,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.733969459531636,
					11.86501511483533
				]
			]
		},
		{
			"type": "arrow",
			"version": 206,
			"versionNonce": 2136010023,
			"isDeleted": false,
			"id": "vUTZiMWjmzYVd5ktcidSi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 965.7578414264026,
			"y": 69.6282544715428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 54.22913680642205,
			"height": 62.02921812789383,
			"seed": 1204864489,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989885,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "iWXltCHCwfR-0xxsMJqvk",
				"focus": 0.28510213420976055,
				"gap": 1.8571622193979778
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
					-37.143244387960294,
					40.857568826756406
				],
				[
					-54.22913680642205,
					62.02921812789383
				]
			]
		},
		{
			"type": "arrow",
			"version": 227,
			"versionNonce": 207428809,
			"isDeleted": false,
			"id": "3ooiJTZZSJMlONdAV4jPv",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 941.6147325742284,
			"y": 66.47107869856613,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 54.22913680642205,
			"height": 62.02921812789383,
			"seed": 2008622441,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "iWXltCHCwfR-0xxsMJqvk",
				"focus": -0.05570578691184425,
				"gap": 5.014337992374649
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
					-37.143244387960294,
					40.857568826756406
				],
				[
					-54.22913680642205,
					62.02921812789383
				]
			]
		},
		{
			"type": "arrow",
			"version": 237,
			"versionNonce": 1227272263,
			"isDeleted": false,
			"id": "NHMPu1fsQiOrTNvKvxvlZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 916.7287588342949,
			"y": 64.98534892304777,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 54.22913680642205,
			"height": 62.02921812789383,
			"seed": 340613321,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "iWXltCHCwfR-0xxsMJqvk",
				"focus": -0.3887756375587634,
				"gap": 6.5000677678930145
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
					-37.143244387960294,
					40.857568826756406
				],
				[
					-54.22913680642205,
					62.02921812789383
				]
			]
		},
		{
			"type": "rectangle",
			"version": 193,
			"versionNonce": 1175493545,
			"isDeleted": false,
			"id": "iWXltCHCwfR-0xxsMJqvk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 809.3847825530896,
			"y": 133.51463481883462,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 109.572570944483,
			"height": 58.31489368909777,
			"seed": 457370473,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "vUTZiMWjmzYVd5ktcidSi",
					"type": "arrow"
				},
				{
					"id": "3ooiJTZZSJMlONdAV4jPv",
					"type": "arrow"
				},
				{
					"id": "NHMPu1fsQiOrTNvKvxvlZ",
					"type": "arrow"
				}
			],
			"updated": 1702914989886,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 430,
			"versionNonce": 1435963239,
			"isDeleted": false,
			"id": "Wnv_FVoo6MUqdAaC9isNd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 911.8578807042691,
			"y": -211.57921045777306,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 384.0971398286538,
			"height": 116.49207133059738,
			"seed": 1039111783,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "vO0OUQMYyDebOgdiFJxKz",
				"gap": 1,
				"focus": 0.35257628249602724
			},
			"endBinding": {
				"elementId": "Fa90n1wA",
				"focus": 0.1754834299922869,
				"gap": 7.365246608038575
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
					34.93210947401781,
					97.03363742782747
				],
				[
					352.1082476596682,
					65.28010026715356
				],
				[
					384.0971398286538,
					116.49207133059738
				]
			]
		},
		{
			"type": "text",
			"version": 107,
			"versionNonce": 1051803273,
			"isDeleted": false,
			"id": "Fa90n1wA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1230.9044549512532,
			"y": -87.7218925191371,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 129.45986938476562,
			"height": 25,
			"seed": 1963747495,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Wnv_FVoo6MUqdAaC9isNd",
					"type": "arrow"
				}
			],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ambient Light",
			"rawText": "Ambient Light",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Ambient Light",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 244,
			"versionNonce": 787384967,
			"isDeleted": false,
			"id": "98x0N8WU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1147.663413372757,
			"y": -61.38858709247569,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 287.40863037109375,
			"height": 80,
			"seed": 143417321,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "sCh5geaxOpx8O_R60TGcN",
					"type": "arrow"
				},
				{
					"id": "ZEUsyZR8ThG94EyZz1mE0",
					"type": "arrow"
				},
				{
					"id": "laJaxegauJ7MyAOHPnNv-",
					"type": "arrow"
				}
			],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Light comes from every direction \nall at once, this lead to the object\nbeing lit from every side without any\nshadows",
			"rawText": "Light comes from every direction \nall at once, this lead to the object\nbeing lit from every side without any\nshadows",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Light comes from every direction \nall at once, this lead to the object\nbeing lit from every side without any\nshadows",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "rectangle",
			"version": 216,
			"versionNonce": 1694139753,
			"isDeleted": false,
			"id": "lfoVYk5bpqhrnITH2IiCl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1231.2823198137355,
			"y": 79.5646031247469,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 109.572570944483,
			"height": 58.31489368909777,
			"seed": 1173160937,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "sCh5geaxOpx8O_R60TGcN",
					"type": "arrow"
				},
				{
					"id": "ZEUsyZR8ThG94EyZz1mE0",
					"type": "arrow"
				},
				{
					"id": "laJaxegauJ7MyAOHPnNv-",
					"type": "arrow"
				},
				{
					"id": "_IIIxcEcm4uP7XfgXPRCE",
					"type": "arrow"
				},
				{
					"id": "IqaTmCdZ1R6woDv3DAxvj",
					"type": "arrow"
				},
				{
					"id": "BdUoQcHlp8tb1G2ANABK6",
					"type": "arrow"
				},
				{
					"id": "ndcwZPve2ibT_wGuBYzAL",
					"type": "arrow"
				},
				{
					"id": "nOdqSDViI22qjJlvi0yvz",
					"type": "arrow"
				}
			],
			"updated": 1702914989886,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 276,
			"versionNonce": 1642701223,
			"isDeleted": false,
			"id": "sCh5geaxOpx8O_R60TGcN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1368.039329601763,
			"y": 33.38845638387171,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.174725618659977,
			"height": 40.56783009988918,
			"seed": 166957545,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "98x0N8WU",
				"focus": -0.6819710569910319,
				"gap": 14.777043476347401
			},
			"endBinding": {
				"elementId": "lfoVYk5bpqhrnITH2IiCl",
				"focus": 0.376930845485579,
				"gap": 5.608316640986004
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
					-20.9051345812604,
					26.949737165782288
				],
				[
					-30.174725618659977,
					40.56783009988918
				]
			]
		},
		{
			"type": "arrow",
			"version": 399,
			"versionNonce": 1144516681,
			"isDeleted": false,
			"id": "ZEUsyZR8ThG94EyZz1mE0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.627489680938048,
			"x": 1301.9127440508655,
			"y": 30.718131542887125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 31.198072267764246,
			"height": 39.51916342542664,
			"seed": 938073929,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "98x0N8WU",
				"focus": 0.03161298885268763,
				"gap": 6.693481678195809
			},
			"endBinding": {
				"elementId": "lfoVYk5bpqhrnITH2IiCl",
				"focus": -0.019380072072384978,
				"gap": 3.9140711992662744
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
					-20.9051345812604,
					26.949737165782288
				],
				[
					-31.198072267764246,
					39.51916342542664
				]
			]
		},
		{
			"type": "arrow",
			"version": 415,
			"versionNonce": 800380103,
			"isDeleted": false,
			"id": "laJaxegauJ7MyAOHPnNv-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.03413953478133,
			"x": 1234.2831122477476,
			"y": 32.33815028299461,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 31.179447953841418,
			"height": 41.13391812493648,
			"seed": 133732713,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "98x0N8WU",
				"focus": 0.7198090077518545,
				"gap": 13.000142161732057
			},
			"endBinding": {
				"elementId": "lfoVYk5bpqhrnITH2IiCl",
				"focus": -0.37034398363097026,
				"gap": 5.365939503077783
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
					-20.9051345812604,
					26.949737165782288
				],
				[
					-31.179447953841418,
					41.13391812493648
				]
			]
		},
		{
			"type": "arrow",
			"version": 389,
			"versionNonce": 1917124393,
			"isDeleted": false,
			"id": "_IIIxcEcm4uP7XfgXPRCE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.9544993893988254,
			"x": 1388.6139445263566,
			"y": 87.93114805737443,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.521496488640196,
			"height": 40.91460096986948,
			"seed": 321465097,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "lfoVYk5bpqhrnITH2IiCl",
				"focus": -0.00479314342777933,
				"gap": 6.983670392358476
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
					-20.9051345812604,
					26.949737165782288
				],
				[
					-30.521496488640196,
					40.91460096986948
				]
			]
		},
		{
			"type": "arrow",
			"version": 385,
			"versionNonce": 2146214887,
			"isDeleted": false,
			"id": "IqaTmCdZ1R6woDv3DAxvj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 4.082859018385562,
			"x": 1216.6155930161322,
			"y": 86.54406457745328,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.521496488640196,
			"height": 40.91460096986948,
			"seed": 1327765095,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "lfoVYk5bpqhrnITH2IiCl",
				"focus": 0.09795142758656893,
				"gap": 4.406757536420969
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
					-20.9051345812604,
					26.949737165782288
				],
				[
					-30.521496488640196,
					40.91460096986948
				]
			]
		},
		{
			"type": "arrow",
			"version": 474,
			"versionNonce": 1032663561,
			"isDeleted": false,
			"id": "BdUoQcHlp8tb1G2ANABK6",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 2.485897027348253,
			"x": 1300.5512201688332,
			"y": 148.7089735671317,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.521496488640196,
			"height": 40.91460096986948,
			"seed": 692656935,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "lfoVYk5bpqhrnITH2IiCl",
				"focus": 0.053188980343456316,
				"gap": 5.767187698361369
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
					-20.9051345812604,
					26.949737165782288
				],
				[
					-30.521496488640196,
					40.91460096986948
				]
			]
		},
		{
			"type": "arrow",
			"version": 400,
			"versionNonce": 312315655,
			"isDeleted": false,
			"id": "ndcwZPve2ibT_wGuBYzAL",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.9118993036069938,
			"x": 1367.4268737272437,
			"y": 144.68637786437012,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.521496488640196,
			"height": 40.91460096986948,
			"seed": 636634407,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "lfoVYk5bpqhrnITH2IiCl",
				"focus": -0.3483922533562435,
				"gap": 6.039148271425347
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
					-20.9051345812604,
					26.949737165782288
				],
				[
					-30.521496488640196,
					40.91460096986948
				]
			]
		},
		{
			"type": "arrow",
			"version": 402,
			"versionNonce": 453773545,
			"isDeleted": false,
			"id": "nOdqSDViI22qjJlvi0yvz",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.1802207723658142,
			"x": 1240.7151090902555,
			"y": 142.17225555014414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.521496488640196,
			"height": 40.91460096986948,
			"seed": 1134335785,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "lfoVYk5bpqhrnITH2IiCl",
				"focus": 0.24984717478868132,
				"gap": 4.897366736731726
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
					-20.9051345812604,
					26.949737165782288
				],
				[
					-30.521496488640196,
					40.91460096986948
				]
			]
		},
		{
			"id": "pjvPE-Q9j58unCFjiB5E5",
			"type": "arrow",
			"x": 913.9240947342762,
			"y": -211.50344150394224,
			"width": 726.5627451960061,
			"height": 111.44294746234797,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
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
			"seed": 371316167,
			"version": 667,
			"versionNonce": 1917064743,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					69.46492364014273,
					97.25089309619963
				],
				[
					647.3885346297718,
					34.45838807921771
				],
				[
					726.5627451960061,
					111.44294746234797
				]
			],
			"lastCommittedPoint": [
				901.1887294103884,
				132.56195503585064
			],
			"startBinding": {
				"elementId": "vO0OUQMYyDebOgdiFJxKz",
				"gap": 1,
				"focus": 0.5618165287468264
			},
			"endBinding": {
				"elementId": "0cZlZiiO",
				"focus": 0.29544862471146666,
				"gap": 7.259876463052933
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "0cZlZiiO",
			"type": "text",
			"x": 1592.1346009481201,
			"y": -92.80061757854133,
			"width": 100.15988159179688,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1625654985,
			"version": 86,
			"versionNonce": 1414333385,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "pjvPE-Q9j58unCFjiB5E5",
					"type": "arrow"
				}
			],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"text": "Point light",
			"rawText": "Point light",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Point light",
			"lineHeight": 1.25
		},
		{
			"id": "ytKSD5f6",
			"type": "text",
			"x": 1471.8346135298848,
			"y": -67.6489423423069,
			"width": 346.0168151855469,
			"height": 80,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1900582377,
			"version": 276,
			"versionNonce": 634173767,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "5RDMsV2mJfiB3DDIFHq7M",
					"type": "arrow"
				}
			],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"text": "Point light is a light source that originates\nfrom a finite point in space and illuminates\nthe rest of the space according to the \ndirection of the object to that finite point",
			"rawText": "Point light is a light source that originates\nfrom a finite point in space and illuminates\nthe rest of the space according to the \ndirection of the object to that finite point",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 74,
			"containerId": null,
			"originalText": "Point light is a light source that originates\nfrom a finite point in space and illuminates\nthe rest of the space according to the \ndirection of the object to that finite point",
			"lineHeight": 1.25
		},
		{
			"type": "ellipse",
			"version": 162,
			"versionNonce": 1969988265,
			"isDeleted": false,
			"id": "Jwtp8y4P3y4wZPGufhAIf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1634.0076368047576,
			"y": 95.02462066078401,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 32.72385331765702,
			"height": 30.04644713712152,
			"seed": 206580489,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 157,
			"versionNonce": 580122727,
			"isDeleted": false,
			"id": "ahNJl8YvhRud6HaAqjqPu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1649.7707093713157,
			"y": 131.2882226328949,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 0.16479187659501804,
			"height": 9.722720719101176,
			"seed": 1762124265,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.16479187659501804,
					9.722720719101176
				]
			]
		},
		{
			"type": "line",
			"version": 158,
			"versionNonce": 2064868745,
			"isDeleted": false,
			"id": "btpkR1TJxAYaMeuWw-Rdz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1638.0704861330755,
			"y": 126.83884196483166,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 9.063553212721445,
			"height": 9.063553212721445,
			"seed": 124107977,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-9.063553212721445,
					9.063553212721445
				]
			]
		},
		{
			"type": "line",
			"version": 123,
			"versionNonce": 2120635271,
			"isDeleted": false,
			"id": "i0udp_D7mPEzva8N6SgkR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1627.3590141544046,
			"y": 117.11612124573045,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 9.88751259569608,
			"height": 2.1422943957341616,
			"seed": 386218921,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989886,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-9.88751259569608,
					2.1422943957341616
				]
			]
		},
		{
			"type": "line",
			"version": 131,
			"versionNonce": 1082117225,
			"isDeleted": false,
			"id": "ua4BKcufmicCwBpEH9dRt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1628.5125572905695,
			"y": 105.41589800749006,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 12.3593907446201,
			"height": 0.9887512595696109,
			"seed": 1209130633,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-12.3593907446201,
					-0.9887512595696109
				]
			]
		},
		{
			"type": "line",
			"version": 126,
			"versionNonce": 1635797671,
			"isDeleted": false,
			"id": "4JdUi2ng3bsIELGP1tL5C",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1632.9619379586325,
			"y": 94.37484227562939,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 6.921258816987233,
			"height": 7.745218199961961,
			"seed": 960963945,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.921258816987233,
					-7.745218199961961
				]
			]
		},
		{
			"type": "line",
			"version": 131,
			"versionNonce": 763123529,
			"isDeleted": false,
			"id": "wI2jLr3isKPApokvcbpke",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1643.3438261841134,
			"y": 90.09025348416108,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 4.119796914873405,
			"height": 11.370639485050535,
			"seed": 636522569,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.119796914873405,
					-11.370639485050535
				]
			]
		},
		{
			"type": "line",
			"version": 142,
			"versionNonce": 948854215,
			"isDeleted": false,
			"id": "ryj67_JKprUjbf7AiFl-r",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1653.2313387798094,
			"y": 88.60712659480666,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 0.3295837531899224,
			"height": 12.19459886802521,
			"seed": 1407819561,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.3295837531899224,
					-12.19459886802521
				]
			]
		},
		{
			"type": "line",
			"version": 127,
			"versionNonce": 610567721,
			"isDeleted": false,
			"id": "ja_nHPYByVOr1DKq3G9cj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1662.2948919925311,
			"y": 91.57338037351549,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 11.205847608455656,
			"height": 8.239593829746763,
			"seed": 1100861961,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					11.205847608455656,
					-8.239593829746763
				]
			]
		},
		{
			"type": "line",
			"version": 130,
			"versionNonce": 648875239,
			"isDeleted": false,
			"id": "ZvGZnYrUnCA7oMgvU-sz8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1668.8865670563287,
			"y": 99.31859857347746,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 15.984812029708678,
			"height": 2.1422943957341545,
			"seed": 336111849,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					15.984812029708678,
					-2.1422943957341545
				]
			]
		},
		{
			"type": "line",
			"version": 145,
			"versionNonce": 807655689,
			"isDeleted": false,
			"id": "mhX3TeqC7PXrDIWCJPjN7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1671.0288614520628,
			"y": 109.86527867555331,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 18.291898302037907,
			"height": 0.4943756297848054,
			"seed": 1152754633,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					18.291898302037907,
					0.4943756297848054
				]
			]
		},
		{
			"type": "line",
			"version": 135,
			"versionNonce": 929617927,
			"isDeleted": false,
			"id": "WPnmHIKGM8LSqVTQOx8vk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1667.897815796759,
			"y": 119.42320751805956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 16.149603906303696,
			"height": 7.580426323367021,
			"seed": 264258217,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.149603906303696,
					7.580426323367021
				]
			]
		},
		{
			"type": "line",
			"version": 134,
			"versionNonce": 1916129257,
			"isDeleted": false,
			"id": "6uGwX6mRQjMvtYkYWHSRK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1660.6469732265818,
			"y": 127.16842571802152,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 8.733969459531636,
			"height": 11.86501511483533,
			"seed": 567543177,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					8.733969459531636,
					11.86501511483533
				]
			]
		},
		{
			"type": "arrow",
			"version": 358,
			"versionNonce": 1354645287,
			"isDeleted": false,
			"id": "xhiKclTCymF39Jze16z-4",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1690.2702264621496,
			"y": 83.65558198535943,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.174725618659977,
			"height": 40.56783009988918,
			"seed": 515817095,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
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
					20.9051345812604,
					-26.949737165782288
				],
				[
					30.174725618659977,
					-40.56783009988918
				]
			]
		},
		{
			"type": "arrow",
			"version": 424,
			"versionNonce": 1353050825,
			"isDeleted": false,
			"id": "5RDMsV2mJfiB3DDIFHq7M",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0.6556956262415383,
			"x": 1667.5737468287161,
			"y": 67.59537432964599,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 31.198072267764246,
			"height": 39.51916342542664,
			"seed": 1368610215,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "ytKSD5f6",
				"focus": -0.030318905211381655,
				"gap": 10.311916289359381
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
					-20.9051345812604,
					-26.949737165782288
				],
				[
					-31.198072267764246,
					-39.51916342542664
				]
			]
		},
		{
			"type": "arrow",
			"version": 452,
			"versionNonce": 1696186951,
			"isDeleted": false,
			"id": "DX1ftiBrxyApmvo-2JtZo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.03413953478133,
			"x": 1585.6767040047146,
			"y": 79.51470727537686,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 31.179447953841425,
			"height": 41.133918124936486,
			"seed": 1745356999,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
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
					20.905134581260402,
					-26.949737165782295
				],
				[
					31.179447953841425,
					-41.133918124936486
				]
			]
		},
		{
			"type": "arrow",
			"version": 452,
			"versionNonce": 1678748073,
			"isDeleted": false,
			"id": "r-Tg81a0G_NHibd5iCYj7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 5.328685917780761,
			"x": 1711.412234675301,
			"y": 88.48880197359067,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864006,
			"height": 40.9146009698693,
			"seed": 800675815,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
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
					20.905134581260306,
					26.949737165782164
				],
				[
					30.52149648864006,
					40.9146009698693
				]
			]
		},
		{
			"type": "arrow",
			"version": 415,
			"versionNonce": 1700258151,
			"isDeleted": false,
			"id": "DurjMIdgRB50Qa8iXkvAI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 2.200326288794024,
			"x": 1564.0963154456088,
			"y": 84.81630809732357,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.521496488640608,
			"height": 40.91460096987004,
			"seed": 246661895,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
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
					20.905134581260683,
					26.949737165782654
				],
				[
					30.521496488640608,
					40.91460096987004
				]
			]
		},
		{
			"type": "arrow",
			"version": 492,
			"versionNonce": 631147657,
			"isDeleted": false,
			"id": "sgxYuCRj3sc5CI5P3mO2W",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.797288279831333,
			"x": 1664.8409767088763,
			"y": 195.66621340444667,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.521496488640196,
			"height": 40.91460096986948,
			"seed": 1970522663,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
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
					-20.9051345812604,
					-26.949737165782288
				],
				[
					-30.521496488640196,
					-40.91460096986948
				]
			]
		},
		{
			"type": "arrow",
			"version": 445,
			"versionNonce": 1925520519,
			"isDeleted": false,
			"id": "WxxADjiokY-Gv2vUz4HEm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 1.9118993036069938,
			"x": 1685.1972610042278,
			"y": 176.55990908580418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.521496488640217,
			"height": 40.91460096986951,
			"seed": 283503943,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
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
					20.905134581260413,
					-26.949737165782306
				],
				[
					30.521496488640217,
					-40.91460096986951
				]
			]
		},
		{
			"type": "arrow",
			"version": 440,
			"versionNonce": 1561203561,
			"isDeleted": false,
			"id": "yZfZSTJn4I6av6iXGoOPi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.1802207723658142,
			"x": 1590.9383239953474,
			"y": 178.15952548500053,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 1013361767,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"id": "akEvoQVNdtfhTgjkxhAFj",
			"type": "arrow",
			"x": 1779.2726681865267,
			"y": 105.4790357749497,
			"width": 139.94938028101774,
			"height": 0.9855590160635757,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
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
			"seed": 9351623,
			"version": 163,
			"versionNonce": 1360917415,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					101.51257865454113,
					0.9855590160635757
				],
				[
					139.94938028101774,
					0.9855590160635757
				]
			],
			"lastCommittedPoint": [
				139.94938028101774,
				0.9855590160635757
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "KCdiyY6j",
			"type": "text",
			"x": 1759.196199829205,
			"y": 66.69583797651771,
			"width": 174.74825714731853,
			"height": 21.078340322125804,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 140264393,
			"version": 357,
			"versionNonce": 1319747145,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"text": "This can also can be limited to a specific\nangle also known as spotlight",
			"rawText": "This can also can be limited to a specific\nangle also known as spotlight",
			"fontSize": 8.431336128850326,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 17.99999999999999,
			"containerId": null,
			"originalText": "This can also can be limited to a specific\nangle also known as spotlight",
			"lineHeight": 1.25
		},
		{
			"id": "o0He_GE3ja0qk1AkggH4m",
			"type": "image",
			"x": 2037.1875790201339,
			"y": 0.609172001813505,
			"width": 91.00000000000001,
			"height": 83,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1138852295,
			"version": 157,
			"versionNonce": 412018375,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7d137ba381113ff98b3e873dece9de75a22aebdd",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 552,
			"versionNonce": 692915497,
			"isDeleted": false,
			"id": "WeTGzrX3FDhcGOH9bzL1Z",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.5638438070410814,
			"x": 2013.672166892377,
			"y": 100.32251187939107,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 1070742217,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "arrow",
			"version": 566,
			"versionNonce": 666138087,
			"isDeleted": false,
			"id": "E9xLnI53s58Br7hCK8uJl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 2.8122664865419598,
			"x": 2043.024136007276,
			"y": 119.74660908778037,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 650073609,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "arrow",
			"version": 525,
			"versionNonce": 878936073,
			"isDeleted": false,
			"id": "8LVpu4R2v4cVx-4Ak-C53",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.1802207723658142,
			"x": 2036.0459960054525,
			"y": 113.5162378891873,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 27.592058688933093,
			"height": 39.807010644548384,
			"seed": 210307337,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "_xAw4GhYfoea1AbpbfDY0",
				"gap": 15.07522862299372,
				"focus": 0.3206849706773261
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					27.592058688933093,
					-39.807010644548384
				]
			]
		},
		{
			"type": "arrow",
			"version": 499,
			"versionNonce": 1436229895,
			"isDeleted": false,
			"id": "OfnEYZAcdH_zz1RT0Rcmi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.3798374117685324,
			"x": 2017.5569863340545,
			"y": 106.36556434422332,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 1852821449,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "arrow",
			"version": 610,
			"versionNonce": 1038653161,
			"isDeleted": false,
			"id": "w7che2H7HrMcE68jy3C3W",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 2.994024582275795,
			"x": 2034.9475972782127,
			"y": 124.11104556610756,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 32.01430093409476,
			"height": 45.19253885657338,
			"seed": 612644361,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "_xAw4GhYfoea1AbpbfDY0",
				"gap": 9.790931791754588,
				"focus": 0.6766419211767376
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					32.01430093409476,
					-45.19253885657338
				]
			]
		},
		{
			"type": "arrow",
			"version": 577,
			"versionNonce": 1673488423,
			"isDeleted": false,
			"id": "WBTNKfhRjbGG-AtARHlNC",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.2759140955427632,
			"x": 2019.283572752578,
			"y": 112.40861680905556,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 1075599369,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989887,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "rectangle",
			"version": 303,
			"versionNonce": 1214763465,
			"isDeleted": false,
			"id": "_xAw4GhYfoea1AbpbfDY0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1960.8051030859588,
			"y": 126.50747378211875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 67.85218324462312,
			"height": 58.31489368909777,
			"seed": 916606953,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "8LVpu4R2v4cVx-4Ak-C53",
					"type": "arrow"
				},
				{
					"id": "w7che2H7HrMcE68jy3C3W",
					"type": "arrow"
				}
			],
			"updated": 1702914989888,
			"link": null,
			"locked": false
		},
		{
			"id": "kgoTgZj9vtasj3WRXab3X",
			"type": "arrow",
			"x": 1647.6340743175913,
			"y": 214.92154104499082,
			"width": 1.6794263804156344,
			"height": 122.59812577035524,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
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
			"seed": 2088438535,
			"version": 127,
			"versionNonce": 806210375,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-1.6794263804156344,
					86.490458591415
				],
				[
					-1.6794263804156344,
					122.59812577035524
				]
			],
			"lastCommittedPoint": [
				-1.6794263804156344,
				122.59812577035524
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "g5LFYXmy",
			"type": "text",
			"x": 1654.5943804281092,
			"y": 236.7540839903965,
			"width": 228.7193145751953,
			"height": 59.00717024480219,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffc9c9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 265433767,
			"version": 255,
			"versionNonce": 2029826217,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"text": "If we want to make this more realistic\nwe can simulate point light source\nbut as a line or a plane to\nform shadows",
			"rawText": "If we want to make this more realistic\nwe can simulate point light source\nbut as a line or a plane to\nform shadows",
			"fontSize": 11.801434048960438,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "If we want to make this more realistic\nwe can simulate point light source\nbut as a line or a plane to\nform shadows",
			"lineHeight": 1.25
		},
		{
			"id": "ZOdKa_xoV3LgJP4lhHsZK",
			"type": "line",
			"x": 1722.7369645389822,
			"y": 329.9030154010548,
			"width": 76.03594080503376,
			"height": 63.725359912790225,
			"angle": 0,
			"strokeColor": "#fee781",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 545238473,
			"version": 181,
			"versionNonce": 652397159,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					76.03594080503376,
					63.725359912790225
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "arrow",
			"version": 613,
			"versionNonce": 1163047817,
			"isDeleted": false,
			"id": "kqpqS9wu43NA91cWaY0am",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.5638438070410814,
			"x": 1680.6362796741362,
			"y": 367.1595418603449,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 2082172617,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "arrow",
			"version": 586,
			"versionNonce": 1963648391,
			"isDeleted": false,
			"id": "_F02K7Dw601CZesX0Eb6l",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.1802207723658142,
			"x": 1703.010108787212,
			"y": 380.35326787014117,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 27.592058688933093,
			"height": 39.807010644548384,
			"seed": 238333353,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					27.592058688933093,
					-39.807010644548384
				]
			]
		},
		{
			"type": "arrow",
			"version": 564,
			"versionNonce": 1638226537,
			"isDeleted": false,
			"id": "t90AJ2QXVSi7pjmHyqWT8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.3798374117685324,
			"x": 1682.4330293810765,
			"y": 376.4945424132451,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 32.2155560833296,
			"height": 44.45646814128975,
			"seed": 1283657865,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "sEyQINgi5vxE9eNbae28h",
				"focus": -0.21551503385520424,
				"gap": 15.801496753679658
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					32.2155560833296,
					-44.45646814128975
				]
			]
		},
		{
			"type": "arrow",
			"version": 642,
			"versionNonce": 2042797223,
			"isDeleted": false,
			"id": "Ye3p_DFs2X2L5Jt2bsRu0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.2759140955427632,
			"x": 1683.9925479960048,
			"y": 383.05193029504267,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 32.52061623866052,
			"height": 44.87256926773023,
			"seed": 1019352937,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "sEyQINgi5vxE9eNbae28h",
				"focus": 0.0975863776075556,
				"gap": 7.807063366391787
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					32.52061623866052,
					-44.87256926773023
				]
			]
		},
		{
			"type": "arrow",
			"version": 601,
			"versionNonce": 1858086217,
			"isDeleted": false,
			"id": "GX4CfOlnrnliDgGsUGEJv",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.5638438070410814,
			"x": 1697.0143201060423,
			"y": 388.10606334028995,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 31.999710210477588,
			"height": 44.22709391189102,
			"seed": 1838655303,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "sEyQINgi5vxE9eNbae28h",
				"focus": -0.15532803620607327,
				"gap": 13.960060941373058
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					31.999710210477588,
					-44.22709391189102
				]
			]
		},
		{
			"type": "arrow",
			"version": 570,
			"versionNonce": 2025222087,
			"isDeleted": false,
			"id": "7cEA3cU08ryT6YfEEJxNp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.1802207723658142,
			"x": 1721.480200739052,
			"y": 398.43566371532,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 27.592058688933093,
			"height": 39.807010644548384,
			"seed": 1322329703,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					27.592058688933093,
					-39.807010644548384
				]
			]
		},
		{
			"type": "arrow",
			"version": 544,
			"versionNonce": 1744737321,
			"isDeleted": false,
			"id": "FYDL3Q6TL8M-p_PzhQukC",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.3798374117685324,
			"x": 1702.991191067654,
			"y": 391.2849901703559,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 1187889543,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "arrow",
			"version": 656,
			"versionNonce": 201514727,
			"isDeleted": false,
			"id": "jgsaPDYab10wAX0hb3VmW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.2759140955427632,
			"x": 1695.6824446719784,
			"y": 398.67730909263105,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 39.466075102890045,
			"height": 42.87160090819788,
			"seed": 1187641511,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "sEyQINgi5vxE9eNbae28h",
				"focus": 0.20397537569190224,
				"gap": 14.886578974921122
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					39.466075102890045,
					-42.87160090819788
				]
			]
		},
		{
			"type": "arrow",
			"version": 579,
			"versionNonce": 1363945225,
			"isDeleted": false,
			"id": "CczPZBE49KiqOKntbzhrk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.5638438070410814,
			"x": 1745.610092834045,
			"y": 418.95098429550006,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 374357513,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "arrow",
			"version": 552,
			"versionNonce": 1446275591,
			"isDeleted": false,
			"id": "GZJmeGmYMlf0UHptQaRT7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.1802207723658142,
			"x": 1767.9839219471207,
			"y": 432.1447103052962,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 27.592058688933093,
			"height": 39.807010644548384,
			"seed": 2139985129,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					27.592058688933093,
					-39.807010644548384
				]
			]
		},
		{
			"type": "arrow",
			"version": 526,
			"versionNonce": 623140329,
			"isDeleted": false,
			"id": "rf4CkVTl7hRPV0Y56hpBK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.3798374117685324,
			"x": 1749.4949122757228,
			"y": 424.99403676033234,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 1220349897,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "arrow",
			"version": 604,
			"versionNonce": 1950847271,
			"isDeleted": false,
			"id": "Y8pjC_jQUFYW8sqiZ93nX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.2759140955427632,
			"x": 1751.221498694246,
			"y": 431.0370892251644,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 2012884649,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "arrow",
			"version": 572,
			"versionNonce": 43169993,
			"isDeleted": false,
			"id": "3o0Z3UL4idUCrb1R1onLb",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.5638438070410814,
			"x": 1718.790486423042,
			"y": 400.98922954317686,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 1210660681,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "arrow",
			"version": 545,
			"versionNonce": 799593543,
			"isDeleted": false,
			"id": "-nLFCE7Q0nOzzdeIvHBOz",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.1802207723658142,
			"x": 1741.1643155361178,
			"y": 414.1829555529731,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 27.592058688933093,
			"height": 39.807010644548384,
			"seed": 376792617,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					27.592058688933093,
					-39.807010644548384
				]
			]
		},
		{
			"type": "arrow",
			"version": 519,
			"versionNonce": 456308649,
			"isDeleted": false,
			"id": "UQtI0WHLVtSbhS6-pN2or",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.3798374117685324,
			"x": 1722.6753058647198,
			"y": 407.03228200800913,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 1830336777,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "arrow",
			"version": 597,
			"versionNonce": 1882501991,
			"isDeleted": false,
			"id": "1abm-B08zbPQ-hdHu_50Q",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 3.2759140955427632,
			"x": 1724.4018922832431,
			"y": 413.0753344728413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 30.52149648864039,
			"height": 40.914600969869745,
			"seed": 2106503145,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					20.905134581260533,
					-26.949737165782462
				],
				[
					30.52149648864039,
					-40.914600969869745
				]
			]
		},
		{
			"type": "rectangle",
			"version": 525,
			"versionNonce": 1630526089,
			"isDeleted": false,
			"id": "sEyQINgi5vxE9eNbae28h",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1610.2507918654758,
			"y": 387.8667813070956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 67.85218324462312,
			"height": 58.31489368909777,
			"seed": 651331847,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "jgsaPDYab10wAX0hb3VmW",
					"type": "arrow"
				},
				{
					"id": "t90AJ2QXVSi7pjmHyqWT8",
					"type": "arrow"
				},
				{
					"id": "Ye3p_DFs2X2L5Jt2bsRu0",
					"type": "arrow"
				},
				{
					"id": "GX4CfOlnrnliDgGsUGEJv",
					"type": "arrow"
				}
			],
			"updated": 1702914989888,
			"link": null,
			"locked": false
		},
		{
			"id": "FjDBGZGFnMGEpvd8cUcYy",
			"type": "arrow",
			"x": 911.2100557176963,
			"y": -209.7640598478652,
			"width": 769.6334244347964,
			"height": 91.26094854302704,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
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
			"seed": 369812457,
			"version": 236,
			"versionNonce": 1849142919,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					100.38704339732965,
					91.26094854302704
				],
				[
					769.6334244347964,
					8.11215574746302
				]
			],
			"lastCommittedPoint": [
				769.6333381930867,
				8.112077345908688
			],
			"startBinding": {
				"elementId": "vO0OUQMYyDebOgdiFJxKz",
				"gap": 2.844061772515275,
				"focus": 0.7556539846676354
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "9VCujaAD",
			"type": "text",
			"x": 1801.5106306728844,
			"y": -246.7403101664234,
			"width": 205.8397674560547,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1446639527,
			"version": 101,
			"versionNonce": 1967497577,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"text": "Image based Lighting",
			"rawText": "Image based Lighting",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Image based Lighting",
			"lineHeight": 1.25
		},
		{
			"id": "xxloJTHy",
			"type": "text",
			"x": 1700.109663849026,
			"y": -215.37605879222014,
			"width": 510.4171447753906,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 739077865,
			"version": 286,
			"versionNonce": 611206567,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"text": "A more realistic simulation on ambient light where we\nhave a half-sphere of point lights that have different variables\nand emit light from infinite points",
			"rawText": "A more realistic simulation on ambient light where we\nhave a half-sphere of point lights that have different variables\nand emit light from infinite points",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "A more realistic simulation on ambient light where we\nhave a half-sphere of point lights that have different variables\nand emit light from infinite points",
			"lineHeight": 1.25
		},
		{
			"id": "vqruvKlaffKmGEZ7Rhz5R",
			"type": "ellipse",
			"x": -210.34521127181972,
			"y": 118.15511874418246,
			"width": 413.7159446413431,
			"height": 181.50773061470693,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
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
			"seed": 11599145,
			"version": 275,
			"versionNonce": 1421839433,
			"isDeleted": false,
			"boundElements": [
				{
					"type": "text",
					"id": "3iuFok3h"
				}
			],
			"updated": 1702914989888,
			"link": null,
			"locked": false
		},
		{
			"id": "3iuFok3h",
			"type": "text",
			"x": -135.92249522042232,
			"y": 191.23631047381573,
			"width": 265.32916259765625,
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
			"seed": 399315049,
			"version": 225,
			"versionNonce": 33880263,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"text": "Types of reflection",
			"rawText": "Types of reflection",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 25,
			"containerId": "vqruvKlaffKmGEZ7Rhz5R",
			"originalText": "Types of reflection",
			"lineHeight": 1.25
		},
		{
			"id": "RoHoBkTM",
			"type": "text",
			"x": -529.702844032015,
			"y": 340.31486131307753,
			"width": 179.13978576660156,
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
			"seed": 476484393,
			"version": 164,
			"versionNonce": 1199119145,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"text": "Diffuse Reflection",
			"rawText": "Diffuse Reflection",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Diffuse Reflection",
			"lineHeight": 1.25
		},
		{
			"id": "o-nFrZY3wRkmkCQDMD72z",
			"type": "line",
			"x": -593.1320534748533,
			"y": 570.257807940195,
			"width": 335.1058125077377,
			"height": 2.5132935938081573,
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
			"seed": 557764713,
			"version": 158,
			"versionNonce": 1553483751,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					335.1058125077377,
					-2.5132935938081573
				]
			],
			"lastCommittedPoint": [
				335.1058125077377,
				-6.702116250154859
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "JJH56WiWnCJblHSParlcQ",
			"type": "arrow",
			"x": -428.09244081479244,
			"y": 566.9067498151175,
			"width": 2.223367239420895,
			"height": 162.5263190662527,
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
			"seed": 1528778601,
			"version": 193,
			"versionNonce": 232640009,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.8377645312693858,
					-124.82691515913223
				],
				[
					2.223367239420895,
					-162.5263190662527
				]
			],
			"lastCommittedPoint": [
				1.6755290625386579,
				-158.337496409906
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "QpuYI9aWPMcYlRaj4jjc4",
			"type": "arrow",
			"x": -570.512411130581,
			"y": 434.5399538745611,
			"width": 138.23114765944183,
			"height": 133.20456047182586,
			"angle": 0,
			"strokeColor": "#fee781",
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
			"seed": 1200670121,
			"version": 101,
			"versionNonce": 573879047,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					138.23114765944183,
					133.20456047182586
				]
			],
			"lastCommittedPoint": [
				138.23114765944183,
				133.20456047182586
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "6hbjOAPq_4zOXSohu_Sjl",
			"type": "arrow",
			"x": -428.57532889052544,
			"y": 567.4070400671619,
			"width": 53.850388979827244,
			"height": 46.9607495394265,
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
			"roundness": {
				"type": 2
			},
			"seed": 1894505415,
			"version": 157,
			"versionNonce": 1323902185,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989888,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					53.850388979827244,
					-46.9607495394265
				]
			],
			"lastCommittedPoint": [
				174.47641360148293,
				-122.13348952103809
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "arrow",
			"version": 156,
			"versionNonce": 1263974951,
			"isDeleted": false,
			"id": "SOyY2iYv_95EhlrHsBLPO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -426.08999082960713,
			"y": 569.1553499807189,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 73.0806247890767,
			"height": 26.856412102483773,
			"seed": 984649833,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					73.0806247890767,
					-26.856412102483773
				]
			]
		},
		{
			"type": "arrow",
			"version": 271,
			"versionNonce": 1176936393,
			"isDeleted": false,
			"id": "wK7QxSVLvemvnT1ygZBSc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -430.68439963856656,
			"y": 568.3228567562862,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 32.871949915191465,
			"height": 68.37623941790866,
			"seed": 663294473,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989888,
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
					32.871949915191465,
					-68.37623941790866
				]
			]
		},
		{
			"type": "text",
			"version": 247,
			"versionNonce": 216718663,
			"isDeleted": false,
			"id": "2UUApPFF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -91.33084565808849,
			"y": 341.42623633319073,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 188.11978149414062,
			"height": 25,
			"seed": 354363049,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Specular Reflection",
			"rawText": "Specular Reflection",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Specular Reflection",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 222,
			"versionNonce": 833732265,
			"isDeleted": false,
			"id": "hivSvzMmGZ26fx9A6i5Ng",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -154.7600551009267,
			"y": 571.3691829603082,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 335.1058125077377,
			"height": 2.5132935938081573,
			"seed": 1639344521,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					335.1058125077377,
					-2.5132935938081573
				]
			]
		},
		{
			"type": "arrow",
			"version": 260,
			"versionNonce": 1246600295,
			"isDeleted": false,
			"id": "6UgOjidmbGFW5fMt-R0Ve",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 10.279557559134105,
			"y": 568.0181248352307,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.223367239420895,
			"height": 162.5263190662527,
			"seed": 1679970409,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
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
					0.8377645312693858,
					-124.82691515913223
				],
				[
					2.223367239420895,
					-162.5263190662527
				]
			]
		},
		{
			"type": "arrow",
			"version": 168,
			"versionNonce": 3539337,
			"isDeleted": false,
			"id": "H1zIUBs_9erSTRZpujq03",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -132.14041275665443,
			"y": 435.65132889467435,
			"strokeColor": "#fee781",
			"backgroundColor": "#a5d8ff",
			"width": 138.23114765944183,
			"height": 133.20456047182586,
			"seed": 1110334281,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
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
					138.23114765944183,
					133.20456047182586
				]
			]
		},
		{
			"type": "arrow",
			"version": 297,
			"versionNonce": 1196128135,
			"isDeleted": false,
			"id": "qUecglx4Tt1dO1oK-21W3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 9.796669483401047,
			"y": 568.5184150872752,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 90.7930249541381,
			"height": 120.84602148804811,
			"seed": 1547045417,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
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
					90.7930249541381,
					-120.84602148804811
				]
			]
		},
		{
			"type": "arrow",
			"version": 285,
			"versionNonce": 1055844457,
			"isDeleted": false,
			"id": "0Bx_wd9LPNXfWmr2_t8F-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 12.282007544319413,
			"y": 570.2667250008323,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 102.97057571374637,
			"height": 37.60336074955603,
			"seed": 2066013449,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
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
					102.97057571374637,
					-37.60336074955603
				]
			]
		},
		{
			"type": "arrow",
			"version": 397,
			"versionNonce": 438365863,
			"isDeleted": false,
			"id": "Om8JMmEI708H7MYGlS4L5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 7.687598735359984,
			"y": 569.4342317763995,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 41.93968783615867,
			"height": 95.57945318081028,
			"seed": 1047942121,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
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
					41.93968783615867,
					-95.57945318081028
				]
			]
		},
		{
			"type": "arrow",
			"version": 360,
			"versionNonce": 1202189129,
			"isDeleted": false,
			"id": "4ZmJ4TvI57T3RJXnivJLf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 10.684169573143777,
			"y": 567.1477166975069,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 133.868053074079,
			"height": 75.21768101430894,
			"seed": 1463012105,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
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
					133.868053074079,
					-75.21768101430894
				]
			]
		},
		{
			"type": "arrow",
			"version": 422,
			"versionNonce": 1568309703,
			"isDeleted": false,
			"id": "Zqh_wuwrzfoJ-pq6hovR4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 11.99524907797813,
			"y": 566.8129803615134,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 146.63005459247734,
			"height": 131.63916141143812,
			"seed": 1561748935,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
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
					146.63005459247734,
					-131.63916141143812
				]
			]
		},
		{
			"type": "line",
			"version": 264,
			"versionNonce": 784114217,
			"isDeleted": false,
			"id": "-0Rgdpjrevv8x-rg6V2_6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 269.64437172642795,
			"y": 566.8204524203071,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 335.1058125077377,
			"height": 2.5132935938081573,
			"seed": 105176071,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					335.1058125077377,
					-2.5132935938081573
				]
			]
		},
		{
			"type": "arrow",
			"version": 305,
			"versionNonce": 578072807,
			"isDeleted": false,
			"id": "Zj_saemPTD5qLDNLymOD5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 434.68398438648876,
			"y": 563.4693942952296,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.223367239420895,
			"height": 162.5263190662527,
			"seed": 1836696359,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
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
					0.8377645312693858,
					-124.82691515913223
				],
				[
					2.223367239420895,
					-162.5263190662527
				]
			]
		},
		{
			"type": "arrow",
			"version": 213,
			"versionNonce": 1897428233,
			"isDeleted": false,
			"id": "PBfwXGv55TndfOi2Hcmy3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 292.2640140707002,
			"y": 431.1025983546733,
			"strokeColor": "#fee781",
			"backgroundColor": "#a5d8ff",
			"width": 138.23114765944183,
			"height": 133.20456047182586,
			"seed": 1740949063,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
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
					138.23114765944183,
					133.20456047182586
				]
			]
		},
		{
			"type": "arrow",
			"version": 467,
			"versionNonce": 580647943,
			"isDeleted": false,
			"id": "nICfC32JsBcLHii3Y0905",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 436.3996759053328,
			"y": 562.2642498215124,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 146.63005459247734,
			"height": 131.63916141143812,
			"seed": 184351207,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
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
					146.63005459247734,
					-131.63916141143812
				]
			]
		},
		{
			"type": "text",
			"version": 277,
			"versionNonce": 1647766505,
			"isDeleted": false,
			"id": "ApFiDUEs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 317.3661844221508,
			"y": 340.3648951640298,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 249.93971252441406,
			"height": 25,
			"seed": 1394042055,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ideal Specular Reflection",
			"rawText": "Ideal Specular Reflection",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Ideal Specular Reflection",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"id": "6fyg7RJ8",
			"type": "text",
			"x": 256.4724234365084,
			"y": 587.7204701778905,
			"width": 395.0395202636719,
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
			"seed": 63533863,
			"version": 224,
			"versionNonce": 837608231,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"text": "reflection in an ideal manner (mirror-like)\nwithout any diffuse of the light ray",
			"rawText": "reflection in an ideal manner (mirror-like)\nwithout any diffuse of the light ray",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "reflection in an ideal manner (mirror-like)\nwithout any diffuse of the light ray",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 443,
			"versionNonce": 1512277705,
			"isDeleted": false,
			"id": "kC8Uqmlq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -183.2276904291699,
			"y": 591.911852101166,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 456.47943115234375,
			"height": 100,
			"seed": 763981897,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Glossy reflection where the light reflects\nin a similar direction that it came from \nbut it also heads in other different similar\ndirections (the more variation the less glossy)",
			"rawText": "Glossy reflection where the light reflects\nin a similar direction that it came from \nbut it also heads in other different similar\ndirections (the more variation the less glossy)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Glossy reflection where the light reflects\nin a similar direction that it came from \nbut it also heads in other different similar\ndirections (the more variation the less glossy)",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"id": "YOPUQe2N",
			"type": "text",
			"x": -607.37624903376,
			"y": 594.2074439386184,
			"width": 378.59954833984375,
			"height": 75,
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
			"seed": 1466258439,
			"version": 178,
			"versionNonce": 1892935239,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "4aod3aEp9uwrZGh8-gqvy",
					"type": "arrow"
				}
			],
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"text": "Light reflects equally in all directions\nand thus has not glossiness to it but\nlooks illuminated from the light",
			"rawText": "Light reflects equally in all directions\nand thus has not glossiness to it but\nlooks illuminated from the light",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "Light reflects equally in all directions\nand thus has not glossiness to it but\nlooks illuminated from the light",
			"lineHeight": 1.25
		},
		{
			"id": "advzfjV0",
			"type": "text",
			"x": -221.6867753147493,
			"y": 712.5597149785888,
			"width": 561.6593627929688,
			"height": 50,
			"angle": 0.020519220696669116,
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
			"seed": 354529449,
			"version": 974,
			"versionNonce": 595183017,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "f4X4m0hb0s55zg39bMhl3",
					"type": "arrow"
				}
			],
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"text": "Sometimes we combine different variations of these\nreflection types in order to get something more realistic!",
			"rawText": "Sometimes we combine different variations of these\nreflection types in order to get something more realistic!",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "Sometimes we combine different variations of these\nreflection types in order to get something more realistic!",
			"lineHeight": 1.25
		},
		{
			"id": "4aod3aEp9uwrZGh8-gqvy",
			"type": "arrow",
			"x": -420.7230481260399,
			"y": 687.7090678346083,
			"width": 242.78681416225402,
			"height": 171.24094138980252,
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
			"seed": 1260946025,
			"version": 283,
			"versionNonce": 1043170663,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-22.28478004387847,
					163.03075926837369
				],
				[
					-242.78681416225402,
					171.24094138980252
				]
			],
			"lastCommittedPoint": [
				-242.78681416225402,
				171.24094138980252
			],
			"startBinding": {
				"elementId": "YOPUQe2N",
				"focus": -0.025759586577749675,
				"gap": 18.501623895989837
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "h2LgM7Ca",
			"type": "text",
			"x": -1174.8869201372936,
			"y": 699.1294320774659,
			"width": 457.3539733886719,
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
			"seed": 51065383,
			"version": 200,
			"versionNonce": 694495369,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"text": "Lambert Ideal diffuse relfection!",
			"rawText": "Lambert Ideal diffuse relfection!",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Lambert Ideal diffuse relfection!",
			"lineHeight": 1.25
		},
		{
			"id": "7rQ3a7st",
			"type": "text",
			"x": -1201.8632328219883,
			"y": 741.9701605631815,
			"width": 559.5794677734375,
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
			"seed": 1709357575,
			"version": 198,
			"versionNonce": 1766211719,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"text": "Reflected radiance is independent of reflection direction!\n it is based off of the angle between the normal and\n the light source",
			"rawText": "Reflected radiance is independent of reflection direction!\n it is based off of the angle between the normal and\n the light source",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "Reflected radiance is independent of reflection direction!\n it is based off of the angle between the normal and\n the light source",
			"lineHeight": 1.25
		},
		{
			"id": "hJWOI4LmfQXqd6HHb551X",
			"type": "arrow",
			"x": -1201.7953136293704,
			"y": 783.8593227038838,
			"width": 111.98341367153625,
			"height": 61.68577871737193,
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
			"seed": 224858185,
			"version": 123,
			"versionNonce": 1705062249,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-75.92095842138042,
					7.592095842138065
				],
				[
					-111.98341367153625,
					-54.09368287523387
				]
			],
			"lastCommittedPoint": [
				-111.98341367153625,
				-54.09368287523387
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "pzSTHA10",
			"type": "text",
			"x": -1548.1846864269198,
			"y": 667.1308491310109,
			"width": 425.5395202636719,
			"height": 25,
			"angle": 5.955319754347412,
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
			"seed": 1063966951,
			"version": 143,
			"versionNonce": 601528231,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"text": "Radiance is light energy per angle per area",
			"rawText": "Radiance is light energy per angle per area",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Radiance is light energy per angle per area",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 198,
			"versionNonce": 242833993,
			"isDeleted": false,
			"id": "yK8iEkcDGxzJJSFJU5Xj6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1092.030021969254,
			"y": 1006.0807620147083,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 335.1058125077377,
			"height": 2.5132935938081573,
			"seed": 951441353,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					335.1058125077377,
					-2.5132935938081573
				]
			]
		},
		{
			"type": "arrow",
			"version": 235,
			"versionNonce": 873925319,
			"isDeleted": false,
			"id": "QDyZ7-ynQyLghUZ1EbZct",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -926.9904093091933,
			"y": 1002.7297038896307,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.223367239420895,
			"height": 162.5263190662527,
			"seed": 2107242153,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
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
					0.8377645312693858,
					-124.82691515913223
				],
				[
					2.223367239420895,
					-162.5263190662527
				]
			]
		},
		{
			"type": "arrow",
			"version": 142,
			"versionNonce": 80292137,
			"isDeleted": false,
			"id": "drfazwCqmnn3Lm4GTgLZI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1069.4103796249815,
			"y": 870.3629079490746,
			"strokeColor": "#fee781",
			"backgroundColor": "#a5d8ff",
			"width": 138.23114765944183,
			"height": 133.20456047182586,
			"seed": 307706249,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hstkn6Nk",
				"focus": 1.2934569820705861,
				"gap": 11.488196667917009
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
					138.23114765944183,
					133.20456047182586
				]
			]
		},
		{
			"id": "h8dC-7aFN9Xo9AZ4J8ELY",
			"type": "freedraw",
			"x": -965.5804009128749,
			"y": 965.9936572999761,
			"width": 37.33363760453835,
			"height": 16.705220894234117,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1421423017,
			"version": 88,
			"versionNonce": 1721244135,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.12655470374420474,
					0
				],
				[
					0.12655470374420474,
					-0.12655470374420474
				],
				[
					0.2531094074884095,
					-0.2531094074882958
				],
				[
					0.37966411123261423,
					-0.5062188149767053
				],
				[
					0.506218814976819,
					-0.8858829262093195
				],
				[
					1.2655470374419338,
					-1.8983205561629575
				],
				[
					1.8983205561629575,
					-2.5310940748838675
				],
				[
					2.4045393711397764,
					-3.1638675936048912
				],
				[
					3.0373128898606865,
					-4.176305223558529
				],
				[
					3.796641112325915,
					-4.809078742279439
				],
				[
					4.555969334791143,
					-5.441852261000463
				],
				[
					5.062188149767849,
					-5.948071075977282
				],
				[
					5.821516372233077,
					-6.707399298442397
				],
				[
					6.833954002186601,
					-7.34017281716342
				],
				[
					7.719836928396035,
					-7.719836928396035
				],
				[
					8.099501039628649,
					-8.352610447117058
				],
				[
					8.985383965838082,
					-8.858829262093764
				],
				[
					9.365048077070583,
					-9.744712188303197
				],
				[
					9.491602780814787,
					-10.37748570702422
				],
				[
					9.997821595791606,
					-11.136813929489335
				],
				[
					10.63059511451263,
					-12.022696855698769
				],
				[
					11.51647804072195,
					-12.528915670675588
				],
				[
					12.275806263187178,
					-13.161689189396498
				],
				[
					13.161689189396611,
					-13.794462708117521
				],
				[
					14.04757211560593,
					-14.174126819350136
				],
				[
					14.80690033807116,
					-14.427236226838545
				],
				[
					15.819337968024684,
					-14.427236226838545
				],
				[
					16.958330301722526,
					-14.93345504181525
				],
				[
					17.844213227931846,
					-15.18656444930366
				],
				[
					18.603541450397074,
					-15.313119153047865
				],
				[
					19.6159790803506,
					-15.43967385679207
				],
				[
					20.248752599071622,
					-15.566228560536274
				],
				[
					20.628416710304236,
					-15.692783264280479
				],
				[
					21.134635525281055,
					-15.819337968024684
				],
				[
					21.640854340257874,
					-15.819337968024684
				],
				[
					22.14707315523458,
					-15.819337968024684
				],
				[
					22.526737266467194,
					-15.819337968024684
				],
				[
					23.159510785188218,
					-15.819337968024684
				],
				[
					23.539174896420832,
					-15.819337968024684
				],
				[
					24.171948415141742,
					-15.819337968024684
				],
				[
					24.804721933862766,
					-15.692783264280479
				],
				[
					25.6906048600722,
					-15.819337968024684
				],
				[
					26.57648778628152,
					-16.199002079257298
				],
				[
					27.588925416235156,
					-16.325556783001502
				],
				[
					28.09514423121186,
					-16.325556783001502
				],
				[
					28.727917749932885,
					-16.452111486745707
				],
				[
					29.234136564909704,
					-16.578666190489912
				],
				[
					29.993464787374933,
					-16.578666190489912
				],
				[
					30.626238306095843,
					-16.705220894234117
				],
				[
					31.259011824816866,
					-16.705220894234117
				],
				[
					31.63867593604948,
					-16.705220894234117
				],
				[
					32.144894751026186,
					-16.705220894234117
				],
				[
					32.651113566003005,
					-16.705220894234117
				],
				[
					33.03077767723562,
					-16.705220894234117
				],
				[
					33.41044178846823,
					-16.705220894234117
				],
				[
					34.04321530718926,
					-16.578666190489912
				],
				[
					34.42287941842187,
					-16.578666190489912
				],
				[
					34.92909823339858,
					-16.578666190489912
				],
				[
					35.435317048375396,
					-16.578666190489912
				],
				[
					35.941535863352215,
					-16.578666190489912
				],
				[
					36.321199974584715,
					-16.578666190489912
				],
				[
					36.827418789561534,
					-16.578666190489912
				],
				[
					37.080528197049944,
					-16.578666190489912
				],
				[
					37.20708290079415,
					-16.705220894234117
				],
				[
					37.33363760453835,
					-16.705220894234117
				],
				[
					37.33363760453835,
					-16.705220894234117
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				37.33363760453835,
				-16.705220894234117
			]
		},
		{
			"id": "4C6ZN5ZgdPX3NP2rYDYyT",
			"type": "freedraw",
			"x": -953.8729271812684,
			"y": 924.639531733419,
			"width": 11.871201968765149,
			"height": 18.142780367358,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 861268071,
			"version": 116,
			"versionNonce": 33299465,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33597741421033334,
					0.22398494280696468
				],
				[
					0.783947299824149,
					0.33597741421033334
				],
				[
					1.4559021282448157,
					0.559962357017298
				],
				[
					1.9038720138586314,
					0.783947299824149
				],
				[
					2.4638343708758157,
					1.1199247140344823
				],
				[
					2.799811785086149,
					1.567894599648298
				],
				[
					3.1357891992964824,
					1.791879542455149
				],
				[
					3.6957515563136667,
					2.2398494280689647
				],
				[
					4.031728970524,
					2.6878193136826667
				],
				[
					4.255713913330965,
					3.2477816706999647
				],
				[
					4.479698856137816,
					3.6957515563136667
				],
				[
					4.703683798944667,
					4.143721441927482
				],
				[
					4.927668741751631,
					4.591691327541298
				],
				[
					5.039661213155,
					4.927668741751518
				],
				[
					5.263646155961965,
					5.599623570172184
				],
				[
					5.375638627365333,
					6.047593455786
				],
				[
					5.487631098768816,
					6.383570869996333
				],
				[
					5.599623570172298,
					6.831540755610149
				],
				[
					5.823608512979149,
					7.391503112627333
				],
				[
					5.823608512979149,
					7.839472998241149
				],
				[
					5.935600984382631,
					8.287442883854851
				],
				[
					6.047593455786,
					9.183382655082482
				],
				[
					6.047593455786,
					9.743345012099667
				],
				[
					6.047593455786,
					10.191314897713482
				],
				[
					6.159585927189482,
					10.751277254730667
				],
				[
					6.159585927189482,
					11.199247140344482
				],
				[
					6.159585927189482,
					11.647217025958184
				],
				[
					6.159585927189482,
					12.431164325782333
				],
				[
					6.159585927189482,
					12.991126682799518
				],
				[
					6.159585927189482,
					13.327104097009851
				],
				[
					6.047593455786,
					13.775073982623667
				],
				[
					5.935600984382631,
					14.223043868237482
				],
				[
					5.711616041575667,
					14.89499869665815
				],
				[
					5.151653684558482,
					15.454961053675333
				],
				[
					4.927668741751631,
					15.90293093928915
				],
				[
					4.703683798944667,
					16.574885767709816
				],
				[
					4.591691327541298,
					17.022855653323518
				],
				[
					4.367706384734333,
					17.35883306753385
				],
				[
					4.255713913330965,
					17.694810481744184
				],
				[
					4.031728970524,
					17.806802953147667
				],
				[
					3.583759084910298,
					18.030787895954518
				],
				[
					3.2477816706999647,
					18.142780367358
				],
				[
					2.799811785086149,
					18.142780367358
				],
				[
					2.3518418994723334,
					18.142780367358
				],
				[
					1.9038720138586314,
					18.142780367358
				],
				[
					1.3439096568413333,
					18.142780367358
				],
				[
					0.559962357017298,
					18.142780367358
				],
				[
					0,
					18.030787895954518
				],
				[
					-0.6719548284206667,
					17.806802953147667
				],
				[
					-1.1199247140343687,
					17.694810481744184
				],
				[
					-1.6798870710516667,
					17.35883306753385
				],
				[
					-2.015864485262,
					17.134848124727
				],
				[
					-2.463834370875702,
					16.798870710516667
				],
				[
					-3.1357891992963687,
					16.462893296306333
				],
				[
					-3.5837590849101844,
					16.126915882096
				],
				[
					-4.031728970524,
					15.566953525078816
				],
				[
					-4.255713913330851,
					15.454961053675333
				],
				[
					-4.479698856137702,
					15.118983639465
				],
				[
					-4.815676270348035,
					14.671013753851184
				],
				[
					-5.039661213155,
					14.335036339640851
				],
				[
					-5.375638627365333,
					13.88706645402715
				],
				[
					-5.599623570172184,
					12.767141739992667
				],
				[
					-5.711616041575667,
					11.983194440168518
				],
				[
					-5.711616041575667,
					11.087254668941
				],
				[
					-5.711616041575667,
					10.527292311923816
				],
				[
					-5.711616041575667,
					9.631352540696184
				],
				[
					-5.711616041575667,
					8.847405240872149
				],
				[
					-5.711616041575667,
					7.839472998241149
				],
				[
					-5.711616041575667,
					7.167518169820482
				],
				[
					-5.711616041575667,
					6.607555812803298
				],
				[
					-5.711616041575667,
					5.935600984382631
				],
				[
					-5.599623570172184,
					5.263646155961965
				],
				[
					-5.599623570172184,
					4.703683798944667
				],
				[
					-5.487631098768702,
					3.9197364991206314
				],
				[
					-5.263646155961851,
					3.2477816706999647
				],
				[
					-5.151653684558369,
					2.9118042564896314
				],
				[
					-5.039661213155,
					2.3518418994723334
				],
				[
					-4.815676270348035,
					1.9038720138586314
				],
				[
					-4.591691327541184,
					1.4559021282448157
				],
				[
					-4.367706384734333,
					1.3439096568413333
				],
				[
					-4.143721441927369,
					1.007932242631
				],
				[
					-4.031728970524,
					0.783947299824149
				],
				[
					-3.9197364991205177,
					0.559962357017298
				],
				[
					-3.6957515563136667,
					0.4479698856138157
				],
				[
					-3.3597741421033334,
					0.4479698856138157
				],
				[
					-3.023796727893,
					0.4479698856138157
				],
				[
					-2.6878193136826667,
					0.4479698856138157
				],
				[
					-2.463834370875702,
					0.33597741421033334
				],
				[
					-2.3518418994723334,
					0.22398494280696468
				],
				[
					-2.239849428068851,
					0.22398494280696468
				],
				[
					-2.1278569566653687,
					0.11199247140348234
				],
				[
					-2.015864485262,
					0.11199247140348234
				],
				[
					-1.9038720138585177,
					0.11199247140348234
				],
				[
					-1.7918795424550353,
					0.11199247140348234
				],
				[
					-1.6798870710516667,
					0.11199247140348234
				],
				[
					-1.5678945996481843,
					0.11199247140348234
				],
				[
					-1.5678945996481843,
					0.11199247140348234
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-1.5678945996481843,
				0.11199247140348234
			]
		},
		{
			"id": "XDOjNHKZ6RzjpQMoFHRyK",
			"type": "freedraw",
			"x": -958.3526260374061,
			"y": 932.4790047316601,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1110096327,
			"version": 20,
			"versionNonce": 1080706311,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989889,
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
			"id": "OsyYipYz4hVCEWKFW1BwQ",
			"type": "freedraw",
			"x": -949.3932283251306,
			"y": 930.9111101320118,
			"width": 0.0001,
			"height": 0.0001,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 350755623,
			"version": 20,
			"versionNonce": 101561065,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989889,
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
			"id": "qNLHmcsJyXMMTA0PA4Qbq",
			"type": "freedraw",
			"x": -949.3932283251306,
			"y": 930.9111101320118,
			"width": 9.519360069292816,
			"height": 2.1278569566654824,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1248622727,
			"version": 54,
			"versionNonce": 1896483879,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989889,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.11199247140348234,
					0.11199247140348234
				],
				[
					-0.223984942806851,
					0.11199247140348234
				],
				[
					-0.33597741421033334,
					0.22398494280696468
				],
				[
					-0.6719548284206667,
					0.335977414210447
				],
				[
					-1.007932242631,
					0.4479698856138157
				],
				[
					-1.3439096568413333,
					0.559962357017298
				],
				[
					-2.1278569566654824,
					0.783947299824149
				],
				[
					-2.4638343708758157,
					0.783947299824149
				],
				[
					-2.9118042564895177,
					0.783947299824149
				],
				[
					-3.3597741421033334,
					0.783947299824149
				],
				[
					-3.6957515563136667,
					0.8959397712276314
				],
				[
					-4.031728970524,
					1.1199247140344823
				],
				[
					-4.479698856137816,
					1.2319171854379647
				],
				[
					-4.815676270348149,
					1.3439096568413333
				],
				[
					-5.039661213155,
					1.4559021282448157
				],
				[
					-5.375638627365333,
					1.567894599648298
				],
				[
					-5.599623570172184,
					1.567894599648298
				],
				[
					-5.823608512979149,
					1.567894599648298
				],
				[
					-5.935600984382518,
					1.6798870710516667
				],
				[
					-6.159585927189482,
					1.6798870710516667
				],
				[
					-6.271578398592851,
					1.791879542455149
				],
				[
					-6.607555812803184,
					1.9038720138586314
				],
				[
					-6.831540755610149,
					1.9038720138586314
				],
				[
					-7.055525698417,
					1.9038720138586314
				],
				[
					-7.391503112627333,
					1.9038720138586314
				],
				[
					-7.615488055434184,
					2.015864485262
				],
				[
					-7.839472998241149,
					2.015864485262
				],
				[
					-8.175450412451482,
					2.1278569566654824
				],
				[
					-8.511427826661816,
					2.1278569566654824
				],
				[
					-8.735412769468667,
					2.1278569566654824
				],
				[
					-9.071390183679,
					2.1278569566654824
				],
				[
					-9.295375126485851,
					2.1278569566654824
				],
				[
					-9.407367597889333,
					2.1278569566654824
				],
				[
					-9.519360069292816,
					2.1278569566654824
				],
				[
					-9.519360069292816,
					2.1278569566654824
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-9.519360069292816,
				2.1278569566654824
			]
		},
		{
			"id": "hstkn6Nk",
			"type": "text",
			"x": -1057.9221829570645,
			"y": 849.131344548727,
			"width": 25.699981689453125,
			"height": 25,
			"angle": 0,
			"strokeColor": "#ffec99",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1478487881,
			"version": 49,
			"versionNonce": 92892617,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "drfazwCqmnn3Lm4GTgLZI",
					"type": "arrow"
				},
				{
					"id": "PXy637pj2IurEe5vsVmcl",
					"type": "arrow"
				}
			],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"text": "Lin",
			"rawText": "Lin",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Lin",
			"lineHeight": 1.25
		},
		{
			"type": "arrow",
			"version": 281,
			"versionNonce": 73658183,
			"isDeleted": false,
			"id": "uJ46dZYextrgrdq9g4ajb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -770.5416147007894,
			"y": 1004.6964544063494,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.223367239420895,
			"height": 162.5263190662527,
			"seed": 871464871,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989890,
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
					0.8377645312693858,
					-124.82691515913223
				],
				[
					2.223367239420895,
					-162.5263190662527
				]
			]
		},
		{
			"type": "arrow",
			"version": 256,
			"versionNonce": 1468714153,
			"isDeleted": false,
			"id": "PXy637pj2IurEe5vsVmcl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1070.2220250629582,
			"y": 870.3129614064062,
			"strokeColor": "#fee781",
			"backgroundColor": "#a5d8ff",
			"width": 297.4399695967786,
			"height": 128.5493317602078,
			"seed": 1002367527,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hstkn6Nk",
				"focus": 1.0829438638990732,
				"gap": 12.299842105893731
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
					297.4399695967786,
					128.5493317602078
				]
			]
		},
		{
			"id": "x2r9iG0_AU1BUN7jXiikG",
			"type": "freedraw",
			"x": -774.3119699401677,
			"y": 960.4970227801282,
			"width": 31.636509599674355,
			"height": 23.162444528333026,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 884358057,
			"version": 79,
			"versionNonce": 1423208039,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.5649376714227401,
					0
				],
				[
					-1.4123441785568502,
					0.14123441785568502
				],
				[
					-2.2597506856909604,
					0.42370325356705507
				],
				[
					-2.9659227749693855,
					0.5649376714227401
				],
				[
					-3.5308604463921256,
					0.8474065071341101
				],
				[
					-3.9545636999591807,
					0.9886409249897952
				],
				[
					-4.378266953526236,
					1.1298753428454802
				],
				[
					-4.6607357892377195,
					1.4123441785568502
				],
				[
					-5.0844390428047745,
					1.5535785964125353
				],
				[
					-5.7906111320832,
					1.8360474321239053
				],
				[
					-6.63801763921731,
					2.1185162678352754
				],
				[
					-7.626658564207219,
					2.4009851035466454
				],
				[
					-8.332830653485644,
					2.5422195214023304
				],
				[
					-9.180237160619754,
					2.6834539392580155
				],
				[
					-10.168878085609549,
					2.9659227749693855
				],
				[
					-11.29875342845503,
					3.2483916106808692
				],
				[
					-12.287394353444938,
					3.6720948642479243
				],
				[
					-13.276035278434733,
					4.095798117814979
				],
				[
					-14.264676203424528,
					4.378266953526349
				],
				[
					-14.829613874847269,
					4.9432046249490895
				],
				[
					-15.959489217692862,
					5.22567346066046
				],
				[
					-16.806895724826973,
					5.649376714227515
				],
				[
					-17.795536649816768,
					6.07307996779457
				],
				[
					-18.501708739095193,
					6.4967832213617385
				],
				[
					-19.631584081940673,
					7.061720892784479
				],
				[
					-20.902693842641952,
					7.485424146351534
				],
				[
					-22.173803603343117,
					8.050361817774274
				],
				[
					-23.444913364044396,
					8.897768324908384
				],
				[
					-24.292319871178506,
					9.321471578475439
				],
				[
					-25.422195214023986,
					10.168878085609549
				],
				[
					-25.84589846759104,
					10.592581339176718
				],
				[
					-26.552070556869467,
					11.157519010599458
				],
				[
					-27.117008228292207,
					11.722456682022198
				],
				[
					-27.540711481859375,
					12.004925517733568
				],
				[
					-28.105649153282116,
					12.569863189156308
				],
				[
					-28.2468835711378,
					13.276035278434733
				],
				[
					-28.388117988993486,
					13.982207367713272
				],
				[
					-28.388117988993486,
					14.405910621280327
				],
				[
					-28.52935240684917,
					14.688379456991697
				],
				[
					-28.81182124256054,
					15.253317128414437
				],
				[
					-28.81182124256054,
					15.818254799837177
				],
				[
					-28.953055660416226,
					16.100723635548547
				],
				[
					-29.09429007827191,
					16.524426889115603
				],
				[
					-29.235524496127596,
					16.948130142682658
				],
				[
					-29.37675891398328,
					17.230598978394028
				],
				[
					-29.517993331838966,
					17.513067814105398
				],
				[
					-29.65922774969465,
					18.078005485528138
				],
				[
					-29.800462167550336,
					18.501708739095307
				],
				[
					-29.94169658540602,
					18.784177574806677
				],
				[
					-30.36539983897319,
					19.20788082837373
				],
				[
					-30.64786867468456,
					19.349115246229417
				],
				[
					-30.789103092540245,
					19.77281849979647
				],
				[
					-31.071571928251615,
					20.196521753363527
				],
				[
					-31.2128063461073,
					20.761459424786267
				],
				[
					-31.354040763962985,
					21.043928260497637
				],
				[
					-31.49527518181867,
					21.326397096209007
				],
				[
					-31.49527518181867,
					21.750100349776176
				],
				[
					-31.636509599674355,
					21.89133476763186
				],
				[
					-31.636509599674355,
					22.17380360334323
				],
				[
					-31.636509599674355,
					22.4562724390546
				],
				[
					-31.636509599674355,
					22.597506856910286
				],
				[
					-31.636509599674355,
					22.879975692621656
				],
				[
					-31.636509599674355,
					23.02121011047734
				],
				[
					-31.636509599674355,
					23.162444528333026
				],
				[
					-31.636509599674355,
					23.162444528333026
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-31.636509599674355,
				23.162444528333026
			]
		},
		{
			"id": "-61UQM7MPYZ0syDufJjmw",
			"type": "freedraw",
			"x": -795.6383670363767,
			"y": 938.1819847589293,
			"width": 10.592581339176718,
			"height": 22.4562724390546,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1541355593,
			"version": 67,
			"versionNonce": 1673351049,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.28246883571137005,
					0.14123441785568502
				],
				[
					0.8474065071341101,
					0.42370325356705507
				],
				[
					1.553578596412649,
					0.9886409249897952
				],
				[
					2.965922774969499,
					1.5535785964125353
				],
				[
					4.378266953526349,
					2.542219521402444
				],
				[
					5.366907878516145,
					3.2483916106808692
				],
				[
					6.3555488035060534,
					4.5195013713820344
				],
				[
					6.9204864749287935,
					5.931845549938885
				],
				[
					7.485424146351534,
					8.191596235629959
				],
				[
					7.485424146351534,
					9.886409249898179
				],
				[
					7.767892982062904,
					12.146159935589253
				],
				[
					7.767892982062904,
					14.123441785568957
				],
				[
					7.767892982062904,
					15.535785964125807
				],
				[
					7.202955310640164,
					17.371833396249713
				],
				[
					6.6380176392174235,
					18.784177574806677
				],
				[
					5.931845549938885,
					20.055287335507842
				],
				[
					5.22567346066046,
					21.04392826049775
				],
				[
					4.5195013713820344,
					21.60886593192049
				],
				[
					3.8133292821036093,
					21.60886593192049
				],
				[
					3.107157192825184,
					21.750100349776176
				],
				[
					2.118516267835389,
					21.89133476763186
				],
				[
					1.553578596412649,
					21.89133476763186
				],
				[
					0.8474065071341101,
					21.750100349776176
				],
				[
					0.14123441785568502,
					21.185162678353436
				],
				[
					-0.5649376714227401,
					20.478990589074897
				],
				[
					-1.412344178556964,
					19.914052917652157
				],
				[
					-2.259750685691074,
					18.92541199266236
				],
				[
					-2.683453939258129,
					17.654302231961196
				],
				[
					-2.824688357113814,
					16.665661306971288
				],
				[
					-2.824688357113814,
					14.970848292703067
				],
				[
					-2.824688357113814,
					13.417269696290418
				],
				[
					-2.683453939258129,
					11.439987846310828
				],
				[
					-2.118516267835389,
					9.745174832042494
				],
				[
					-1.836047432124019,
					8.332830653485644
				],
				[
					-1.1298753428454802,
					7.061720892784479
				],
				[
					-0.5649376714227401,
					5.22567346066046
				],
				[
					-0.14123441785568502,
					3.6720948642479243
				],
				[
					0.14123441785568502,
					2.965922774969499
				],
				[
					0.28246883571137005,
					2.1185162678352754
				],
				[
					0.7061720892784251,
					1.2711097607011652
				],
				[
					0.8474065071341101,
					0.7061720892784251
				],
				[
					0.9886409249897952,
					0.28246883571137005
				],
				[
					1.1298753428454802,
					0
				],
				[
					1.4123441785568502,
					-0.14123441785568502
				],
				[
					1.694813014268334,
					-0.28246883571137005
				],
				[
					1.977281849979704,
					-0.5649376714227401
				],
				[
					2.259750685691074,
					-0.5649376714227401
				],
				[
					2.400985103546759,
					-0.5649376714227401
				],
				[
					2.542219521402444,
					-0.5649376714227401
				],
				[
					2.683453939258129,
					-0.5649376714227401
				],
				[
					2.683453939258129,
					-0.42370325356705507
				],
				[
					2.683453939258129,
					-0.28246883571137005
				],
				[
					2.824688357113814,
					-0.14123441785568502
				],
				[
					2.824688357113814,
					-0.14123441785568502
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				2.824688357113814,
				-0.14123441785568502
			]
		},
		{
			"id": "ZZPRPOR_LHP2oqgDFoD7H",
			"type": "freedraw",
			"x": -788.8591149793036,
			"y": 945.5261744874251,
			"width": 9.321471578475553,
			"height": 2.683453939258129,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1935870281,
			"version": 35,
			"versionNonce": 1026034055,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.14123441785568502,
					0
				],
				[
					-0.8474065071342238,
					0.14123441785568502
				],
				[
					-1.412344178556964,
					0.42370325356705507
				],
				[
					-1.977281849979704,
					0.9886409249897952
				],
				[
					-2.683453939258129,
					1.4123441785568502
				],
				[
					-3.2483916106808692,
					1.5535785964125353
				],
				[
					-3.9545636999592944,
					1.6948130142682203
				],
				[
					-4.5195013713820344,
					1.9772818499795903
				],
				[
					-4.8019702070934045,
					1.9772818499795903
				],
				[
					-5.0844390428047745,
					2.1185162678352754
				],
				[
					-5.366907878516258,
					2.2597506856909604
				],
				[
					-5.931845549938998,
					2.2597506856909604
				],
				[
					-6.214314385650368,
					2.4009851035466454
				],
				[
					-6.7792520570731085,
					2.4009851035466454
				],
				[
					-7.202955310640164,
					2.5422195214023304
				],
				[
					-7.485424146351534,
					2.683453939258129
				],
				[
					-7.909127399918589,
					2.683453939258129
				],
				[
					-8.474065071341442,
					2.683453939258129
				],
				[
					-8.897768324908498,
					2.683453939258129
				],
				[
					-9.180237160619868,
					2.5422195214023304
				],
				[
					-9.321471578475553,
					2.4009851035466454
				],
				[
					-9.321471578475553,
					2.4009851035466454
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				-9.321471578475553,
				2.4009851035466454
			]
		},
		{
			"id": "MnEgpBAA",
			"type": "text",
			"x": -1153.9502495404063,
			"y": 1029.653432113454,
			"width": 449.2618408203125,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 179322441,
			"version": 97,
			"versionNonce": 274495081,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"text": "L(diff) = L(in) * kd * cos(theta)",
			"rawText": "L(diff) = L(in) * kd * cos(theta)",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "L(diff) = L(in) * kd * cos(theta)",
			"lineHeight": 1.25
		},
		{
			"id": "4njVi4uW8tW6UHpkHCTFV",
			"type": "line",
			"x": -1116.7204772955677,
			"y": 1073.3640695735207,
			"width": 0.6678015211703041,
			"height": 37.062984424947444,
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
			"seed": 1412803401,
			"version": 74,
			"versionNonce": 177946791,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.6678015211703041,
					37.062984424947444
				]
			],
			"lastCommittedPoint": [
				-0.6678015211703041,
				37.062984424947444
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "yVo8FjPw",
			"type": "text",
			"x": -1143.892330025234,
			"y": 1117.9270539984682,
			"width": 53.00810241699219,
			"height": 40,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 861974185,
			"version": 29,
			"versionNonce": 1882440009,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"text": "output\ncolor",
			"rawText": "output\ncolor",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "output\ncolor",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 99,
			"versionNonce": 786076615,
			"isDeleted": false,
			"id": "SgB59dQgeBpHexaGPw2Zp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -994.4429522508793,
			"y": 1070.4145316544302,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6678015211703041,
			"height": 37.062984424947444,
			"seed": 1664763175,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6678015211703041,
					37.062984424947444
				]
			]
		},
		{
			"type": "text",
			"version": 53,
			"versionNonce": 815706153,
			"isDeleted": false,
			"id": "LVa0YIZl",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1046.095696000098,
			"y": 1118.8086186482024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 95.15217590332031,
			"height": 40,
			"seed": 574670791,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Input light\nsource color",
			"rawText": "Input light\nsource color",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Input light\nsource color",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 110,
			"versionNonce": 839025383,
			"isDeleted": false,
			"id": "0hYQYpAJohdm7XahlC-IF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -905.0544492334827,
			"y": 1071.847529675262,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6678015211703041,
			"height": 37.062984424947444,
			"seed": 1322749223,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6678015211703041,
					37.062984424947444
				]
			]
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 1200145161,
			"isDeleted": false,
			"id": "lIgoAVxh",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -933.8219568334396,
			"y": 1116.805214084692,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60.928131103515625,
			"height": 40,
			"seed": 1107523591,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Surface\ncolor",
			"rawText": "Surface\ncolor",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Surface\ncolor",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"id": "g1fgpULWK_nwB2lcLMMfr",
			"type": "line",
			"x": -756.7754573848183,
			"y": 1076.0352756582017,
			"width": 1.669503802925533,
			"height": 36.0612821431921,
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
			"seed": 165265415,
			"version": 50,
			"versionNonce": 1688178183,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.669503802925533,
					36.0612821431921
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "text",
			"version": 209,
			"versionNonce": 1634564585,
			"isDeleted": false,
			"id": "3tfArFCM",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -887.7220477945339,
			"y": 1110.7950003941598,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 237.1845245361328,
			"height": 100,
			"seed": 1070804231,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Angle between norm\nand light source\n\ndot ( n , l )\nif both n and l are normalized",
			"rawText": "Angle between norm\nand light source\n\ndot ( n , l )\nif both n and l are normalized",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Angle between norm\nand light source\n\ndot ( n , l )\nif both n and l are normalized",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 375,
			"versionNonce": 1370371367,
			"isDeleted": false,
			"id": "5GPTPRNXEyRSlwVfPxT-t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 444.3738124120132,
			"y": 670.1142093089211,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 284.6945848532026,
			"height": 168.4201852453349,
			"seed": 1364265353,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989890,
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
					31.309586701007504,
					158.79962505167214
				],
				[
					284.6945848532026,
					168.4201852453349
				]
			]
		},
		{
			"type": "text",
			"version": 374,
			"versionNonce": 257447113,
			"isDeleted": false,
			"id": "fNuczZ3v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 852.0731689807619,
			"y": 685.7092395180332,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 352.32550048828125,
			"height": 35,
			"seed": 522783047,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Phong Specular Reflection",
			"rawText": "Phong Specular Reflection",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Phong Specular Reflection",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 444,
			"versionNonce": 1889204295,
			"isDeleted": false,
			"id": "OESwOnPV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 753.9995548552799,
			"y": 727.6091755614764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 541.83935546875,
			"height": 75,
			"seed": 1273383015,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Light ray and the reflected ray off of the surface\nshould have the same angle off of the surface normal\nand should exist in a common plane together",
			"rawText": "Light ray and the reflected ray off of the surface\nshould have the same angle off of the surface normal\nand should exist in a common plane together",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Light ray and the reflected ray off of the surface\nshould have the same angle off of the surface normal\nand should exist in a common plane together",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "line",
			"version": 291,
			"versionNonce": 887411625,
			"isDeleted": false,
			"id": "Cx4e0-67Qd7TBhETXBchf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 854.9627095556705,
			"y": 991.7197770130033,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 335.1058125077377,
			"height": 2.5132935938081573,
			"seed": 1760469895,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					335.1058125077377,
					-2.5132935938081573
				]
			]
		},
		{
			"type": "arrow",
			"version": 328,
			"versionNonce": 390223719,
			"isDeleted": false,
			"id": "vT0s_wUy4PuNGO5LeTWsq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1020.0023222157313,
			"y": 988.3687188879258,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.223367239420895,
			"height": 162.5263190662527,
			"seed": 1988008615,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989890,
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
					0.8377645312693858,
					-124.82691515913223
				],
				[
					2.223367239420895,
					-162.5263190662527
				]
			]
		},
		{
			"type": "arrow",
			"version": 334,
			"versionNonce": 910063241,
			"isDeleted": false,
			"id": "vudCR6oEOCYJ2JrYTBHJg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 877.582351899943,
			"y": 856.0019229473696,
			"strokeColor": "#fee781",
			"backgroundColor": "#a5d8ff",
			"width": 138.23114765944183,
			"height": 133.20456047182586,
			"seed": 960671175,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "l3srV0Py",
				"focus": 1.293456982070586,
				"gap": 11.488196667917009
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
					138.23114765944183,
					133.20456047182586
				]
			]
		},
		{
			"type": "freedraw",
			"version": 181,
			"versionNonce": 737202823,
			"isDeleted": false,
			"id": "uZjNI2ePtpFFNsIxL56r7",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 981.4123306120496,
			"y": 951.632672298271,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 37.33363760453835,
			"height": 16.705220894234117,
			"seed": 743922919,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.12655470374420474,
					0
				],
				[
					0.12655470374420474,
					-0.12655470374420474
				],
				[
					0.2531094074884095,
					-0.2531094074882958
				],
				[
					0.37966411123261423,
					-0.5062188149767053
				],
				[
					0.506218814976819,
					-0.8858829262093195
				],
				[
					1.2655470374419338,
					-1.8983205561629575
				],
				[
					1.8983205561629575,
					-2.5310940748838675
				],
				[
					2.4045393711397764,
					-3.1638675936048912
				],
				[
					3.0373128898606865,
					-4.176305223558529
				],
				[
					3.796641112325915,
					-4.809078742279439
				],
				[
					4.555969334791143,
					-5.441852261000463
				],
				[
					5.062188149767849,
					-5.948071075977282
				],
				[
					5.821516372233077,
					-6.707399298442397
				],
				[
					6.833954002186601,
					-7.34017281716342
				],
				[
					7.719836928396035,
					-7.719836928396035
				],
				[
					8.099501039628649,
					-8.352610447117058
				],
				[
					8.985383965838082,
					-8.858829262093764
				],
				[
					9.365048077070583,
					-9.744712188303197
				],
				[
					9.491602780814787,
					-10.37748570702422
				],
				[
					9.997821595791606,
					-11.136813929489335
				],
				[
					10.63059511451263,
					-12.022696855698769
				],
				[
					11.51647804072195,
					-12.528915670675588
				],
				[
					12.275806263187178,
					-13.161689189396498
				],
				[
					13.161689189396611,
					-13.794462708117521
				],
				[
					14.04757211560593,
					-14.174126819350136
				],
				[
					14.80690033807116,
					-14.427236226838545
				],
				[
					15.819337968024684,
					-14.427236226838545
				],
				[
					16.958330301722526,
					-14.93345504181525
				],
				[
					17.844213227931846,
					-15.18656444930366
				],
				[
					18.603541450397074,
					-15.313119153047865
				],
				[
					19.6159790803506,
					-15.43967385679207
				],
				[
					20.248752599071622,
					-15.566228560536274
				],
				[
					20.628416710304236,
					-15.692783264280479
				],
				[
					21.134635525281055,
					-15.819337968024684
				],
				[
					21.640854340257874,
					-15.819337968024684
				],
				[
					22.14707315523458,
					-15.819337968024684
				],
				[
					22.526737266467194,
					-15.819337968024684
				],
				[
					23.159510785188218,
					-15.819337968024684
				],
				[
					23.539174896420832,
					-15.819337968024684
				],
				[
					24.171948415141742,
					-15.819337968024684
				],
				[
					24.804721933862766,
					-15.692783264280479
				],
				[
					25.6906048600722,
					-15.819337968024684
				],
				[
					26.57648778628152,
					-16.199002079257298
				],
				[
					27.588925416235156,
					-16.325556783001502
				],
				[
					28.09514423121186,
					-16.325556783001502
				],
				[
					28.727917749932885,
					-16.452111486745707
				],
				[
					29.234136564909704,
					-16.578666190489912
				],
				[
					29.993464787374933,
					-16.578666190489912
				],
				[
					30.626238306095843,
					-16.705220894234117
				],
				[
					31.259011824816866,
					-16.705220894234117
				],
				[
					31.63867593604948,
					-16.705220894234117
				],
				[
					32.144894751026186,
					-16.705220894234117
				],
				[
					32.651113566003005,
					-16.705220894234117
				],
				[
					33.03077767723562,
					-16.705220894234117
				],
				[
					33.41044178846823,
					-16.705220894234117
				],
				[
					34.04321530718926,
					-16.578666190489912
				],
				[
					34.42287941842187,
					-16.578666190489912
				],
				[
					34.92909823339858,
					-16.578666190489912
				],
				[
					35.435317048375396,
					-16.578666190489912
				],
				[
					35.941535863352215,
					-16.578666190489912
				],
				[
					36.321199974584715,
					-16.578666190489912
				],
				[
					36.827418789561534,
					-16.578666190489912
				],
				[
					37.080528197049944,
					-16.578666190489912
				],
				[
					37.20708290079415,
					-16.705220894234117
				],
				[
					37.33363760453835,
					-16.705220894234117
				],
				[
					37.33363760453835,
					-16.705220894234117
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 235,
			"versionNonce": 1713421673,
			"isDeleted": false,
			"id": "aFUFkeK7yUbAb2NcQq-Md",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1002.1914052311064,
			"y": 940.8951997268588,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 11.871201968765149,
			"height": 18.142780367358,
			"seed": 860432391,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33597741421033334,
					0.22398494280696468
				],
				[
					0.783947299824149,
					0.33597741421033334
				],
				[
					1.4559021282448157,
					0.559962357017298
				],
				[
					1.9038720138586314,
					0.783947299824149
				],
				[
					2.4638343708758157,
					1.1199247140344823
				],
				[
					2.799811785086149,
					1.567894599648298
				],
				[
					3.1357891992964824,
					1.791879542455149
				],
				[
					3.6957515563136667,
					2.2398494280689647
				],
				[
					4.031728970524,
					2.6878193136826667
				],
				[
					4.255713913330965,
					3.2477816706999647
				],
				[
					4.479698856137816,
					3.6957515563136667
				],
				[
					4.703683798944667,
					4.143721441927482
				],
				[
					4.927668741751631,
					4.591691327541298
				],
				[
					5.039661213155,
					4.927668741751518
				],
				[
					5.263646155961965,
					5.599623570172184
				],
				[
					5.375638627365333,
					6.047593455786
				],
				[
					5.487631098768816,
					6.383570869996333
				],
				[
					5.599623570172298,
					6.831540755610149
				],
				[
					5.823608512979149,
					7.391503112627333
				],
				[
					5.823608512979149,
					7.839472998241149
				],
				[
					5.935600984382631,
					8.287442883854851
				],
				[
					6.047593455786,
					9.183382655082482
				],
				[
					6.047593455786,
					9.743345012099667
				],
				[
					6.047593455786,
					10.191314897713482
				],
				[
					6.159585927189482,
					10.751277254730667
				],
				[
					6.159585927189482,
					11.199247140344482
				],
				[
					6.159585927189482,
					11.647217025958184
				],
				[
					6.159585927189482,
					12.431164325782333
				],
				[
					6.159585927189482,
					12.991126682799518
				],
				[
					6.159585927189482,
					13.327104097009851
				],
				[
					6.047593455786,
					13.775073982623667
				],
				[
					5.935600984382631,
					14.223043868237482
				],
				[
					5.711616041575667,
					14.89499869665815
				],
				[
					5.151653684558482,
					15.454961053675333
				],
				[
					4.927668741751631,
					15.90293093928915
				],
				[
					4.703683798944667,
					16.574885767709816
				],
				[
					4.591691327541298,
					17.022855653323518
				],
				[
					4.367706384734333,
					17.35883306753385
				],
				[
					4.255713913330965,
					17.694810481744184
				],
				[
					4.031728970524,
					17.806802953147667
				],
				[
					3.583759084910298,
					18.030787895954518
				],
				[
					3.2477816706999647,
					18.142780367358
				],
				[
					2.799811785086149,
					18.142780367358
				],
				[
					2.3518418994723334,
					18.142780367358
				],
				[
					1.9038720138586314,
					18.142780367358
				],
				[
					1.3439096568413333,
					18.142780367358
				],
				[
					0.559962357017298,
					18.142780367358
				],
				[
					0,
					18.030787895954518
				],
				[
					-0.6719548284206667,
					17.806802953147667
				],
				[
					-1.1199247140343687,
					17.694810481744184
				],
				[
					-1.6798870710516667,
					17.35883306753385
				],
				[
					-2.015864485262,
					17.134848124727
				],
				[
					-2.463834370875702,
					16.798870710516667
				],
				[
					-3.1357891992963687,
					16.462893296306333
				],
				[
					-3.5837590849101844,
					16.126915882096
				],
				[
					-4.031728970524,
					15.566953525078816
				],
				[
					-4.255713913330851,
					15.454961053675333
				],
				[
					-4.479698856137702,
					15.118983639465
				],
				[
					-4.815676270348035,
					14.671013753851184
				],
				[
					-5.039661213155,
					14.335036339640851
				],
				[
					-5.375638627365333,
					13.88706645402715
				],
				[
					-5.599623570172184,
					12.767141739992667
				],
				[
					-5.711616041575667,
					11.983194440168518
				],
				[
					-5.711616041575667,
					11.087254668941
				],
				[
					-5.711616041575667,
					10.527292311923816
				],
				[
					-5.711616041575667,
					9.631352540696184
				],
				[
					-5.711616041575667,
					8.847405240872149
				],
				[
					-5.711616041575667,
					7.839472998241149
				],
				[
					-5.711616041575667,
					7.167518169820482
				],
				[
					-5.711616041575667,
					6.607555812803298
				],
				[
					-5.711616041575667,
					5.935600984382631
				],
				[
					-5.599623570172184,
					5.263646155961965
				],
				[
					-5.599623570172184,
					4.703683798944667
				],
				[
					-5.487631098768702,
					3.9197364991206314
				],
				[
					-5.263646155961851,
					3.2477816706999647
				],
				[
					-5.151653684558369,
					2.9118042564896314
				],
				[
					-5.039661213155,
					2.3518418994723334
				],
				[
					-4.815676270348035,
					1.9038720138586314
				],
				[
					-4.591691327541184,
					1.4559021282448157
				],
				[
					-4.367706384734333,
					1.3439096568413333
				],
				[
					-4.143721441927369,
					1.007932242631
				],
				[
					-4.031728970524,
					0.783947299824149
				],
				[
					-3.9197364991205177,
					0.559962357017298
				],
				[
					-3.6957515563136667,
					0.4479698856138157
				],
				[
					-3.3597741421033334,
					0.4479698856138157
				],
				[
					-3.023796727893,
					0.4479698856138157
				],
				[
					-2.6878193136826667,
					0.4479698856138157
				],
				[
					-2.463834370875702,
					0.33597741421033334
				],
				[
					-2.3518418994723334,
					0.22398494280696468
				],
				[
					-2.239849428068851,
					0.22398494280696468
				],
				[
					-2.1278569566653687,
					0.11199247140348234
				],
				[
					-2.015864485262,
					0.11199247140348234
				],
				[
					-1.9038720138585177,
					0.11199247140348234
				],
				[
					-1.7918795424550353,
					0.11199247140348234
				],
				[
					-1.6798870710516667,
					0.11199247140348234
				],
				[
					-1.5678945996481843,
					0.11199247140348234
				],
				[
					-1.5678945996481843,
					0.11199247140348234
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 139,
			"versionNonce": 392358311,
			"isDeleted": false,
			"id": "kGvZFbZSyYNXsaEGdrq1A",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 997.7117063749687,
			"y": 948.7346727251,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 202673959,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
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
			"version": 139,
			"versionNonce": 869738569,
			"isDeleted": false,
			"id": "21h3Qhh6QdQcxGCq9NNId",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1006.6711040872442,
			"y": 947.1667781254517,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 19272263,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
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
			"version": 173,
			"versionNonce": 1992629447,
			"isDeleted": false,
			"id": "PW_qKt5w4HcFa2GKKTr9q",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1006.6711040872442,
			"y": 947.1667781254517,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 9.519360069292816,
			"height": 2.1278569566654824,
			"seed": 1532637543,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.11199247140348234,
					0.11199247140348234
				],
				[
					-0.223984942806851,
					0.11199247140348234
				],
				[
					-0.33597741421033334,
					0.22398494280696468
				],
				[
					-0.6719548284206667,
					0.335977414210447
				],
				[
					-1.007932242631,
					0.4479698856138157
				],
				[
					-1.3439096568413333,
					0.559962357017298
				],
				[
					-2.1278569566654824,
					0.783947299824149
				],
				[
					-2.4638343708758157,
					0.783947299824149
				],
				[
					-2.9118042564895177,
					0.783947299824149
				],
				[
					-3.3597741421033334,
					0.783947299824149
				],
				[
					-3.6957515563136667,
					0.8959397712276314
				],
				[
					-4.031728970524,
					1.1199247140344823
				],
				[
					-4.479698856137816,
					1.2319171854379647
				],
				[
					-4.815676270348149,
					1.3439096568413333
				],
				[
					-5.039661213155,
					1.4559021282448157
				],
				[
					-5.375638627365333,
					1.567894599648298
				],
				[
					-5.599623570172184,
					1.567894599648298
				],
				[
					-5.823608512979149,
					1.567894599648298
				],
				[
					-5.935600984382518,
					1.6798870710516667
				],
				[
					-6.159585927189482,
					1.6798870710516667
				],
				[
					-6.271578398592851,
					1.791879542455149
				],
				[
					-6.607555812803184,
					1.9038720138586314
				],
				[
					-6.831540755610149,
					1.9038720138586314
				],
				[
					-7.055525698417,
					1.9038720138586314
				],
				[
					-7.391503112627333,
					1.9038720138586314
				],
				[
					-7.615488055434184,
					2.015864485262
				],
				[
					-7.839472998241149,
					2.015864485262
				],
				[
					-8.175450412451482,
					2.1278569566654824
				],
				[
					-8.511427826661816,
					2.1278569566654824
				],
				[
					-8.735412769468667,
					2.1278569566654824
				],
				[
					-9.071390183679,
					2.1278569566654824
				],
				[
					-9.295375126485851,
					2.1278569566654824
				],
				[
					-9.407367597889333,
					2.1278569566654824
				],
				[
					-9.519360069292816,
					2.1278569566654824
				],
				[
					-9.519360069292816,
					2.1278569566654824
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 143,
			"versionNonce": 423442217,
			"isDeleted": false,
			"id": "l3srV0Py",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 889.07054856786,
			"y": 834.770359547022,
			"strokeColor": "#ffec99",
			"backgroundColor": "#ffec99",
			"width": 25.699981689453125,
			"height": 25,
			"seed": 335375495,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "vudCR6oEOCYJ2JrYTBHJg",
					"type": "arrow"
				},
				{
					"id": "jomc8PW1rrwEgN-VadsQx",
					"type": "arrow"
				}
			],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lin",
			"rawText": "Lin",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lin",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 374,
			"versionNonce": 229895143,
			"isDeleted": false,
			"id": "eSUf4-9Id1eJ9yFr3uQlv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1176.451116824135,
			"y": 990.3354694046445,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.223367239420895,
			"height": 162.5263190662527,
			"seed": 1187791783,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989890,
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
					0.8377645312693858,
					-124.82691515913223
				],
				[
					2.223367239420895,
					-162.5263190662527
				]
			]
		},
		{
			"type": "arrow",
			"version": 449,
			"versionNonce": 1220438537,
			"isDeleted": false,
			"id": "jomc8PW1rrwEgN-VadsQx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 876.7707064619663,
			"y": 855.9519764047011,
			"strokeColor": "#fee781",
			"backgroundColor": "#a5d8ff",
			"width": 297.4399695967786,
			"height": 128.5493317602078,
			"seed": 1676883655,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "l3srV0Py",
				"focus": 1.082943863899067,
				"gap": 12.299842105893731
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
					297.4399695967786,
					128.5493317602078
				]
			]
		},
		{
			"type": "freedraw",
			"version": 172,
			"versionNonce": 2017187591,
			"isDeleted": false,
			"id": "9s2bFt2miY44RUPm4VWue",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1172.6807615847567,
			"y": 946.1360377784233,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffec99",
			"width": 31.636509599674355,
			"height": 23.162444528333026,
			"seed": 571393511,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.5649376714227401,
					0
				],
				[
					-1.4123441785568502,
					0.14123441785568502
				],
				[
					-2.2597506856909604,
					0.42370325356705507
				],
				[
					-2.9659227749693855,
					0.5649376714227401
				],
				[
					-3.5308604463921256,
					0.8474065071341101
				],
				[
					-3.9545636999591807,
					0.9886409249897952
				],
				[
					-4.378266953526236,
					1.1298753428454802
				],
				[
					-4.6607357892377195,
					1.4123441785568502
				],
				[
					-5.0844390428047745,
					1.5535785964125353
				],
				[
					-5.7906111320832,
					1.8360474321239053
				],
				[
					-6.63801763921731,
					2.1185162678352754
				],
				[
					-7.626658564207219,
					2.4009851035466454
				],
				[
					-8.332830653485644,
					2.5422195214023304
				],
				[
					-9.180237160619754,
					2.6834539392580155
				],
				[
					-10.168878085609549,
					2.9659227749693855
				],
				[
					-11.29875342845503,
					3.2483916106808692
				],
				[
					-12.287394353444938,
					3.6720948642479243
				],
				[
					-13.276035278434733,
					4.095798117814979
				],
				[
					-14.264676203424528,
					4.378266953526349
				],
				[
					-14.829613874847269,
					4.9432046249490895
				],
				[
					-15.959489217692862,
					5.22567346066046
				],
				[
					-16.806895724826973,
					5.649376714227515
				],
				[
					-17.795536649816768,
					6.07307996779457
				],
				[
					-18.501708739095193,
					6.4967832213617385
				],
				[
					-19.631584081940673,
					7.061720892784479
				],
				[
					-20.902693842641952,
					7.485424146351534
				],
				[
					-22.173803603343117,
					8.050361817774274
				],
				[
					-23.444913364044396,
					8.897768324908384
				],
				[
					-24.292319871178506,
					9.321471578475439
				],
				[
					-25.422195214023986,
					10.168878085609549
				],
				[
					-25.84589846759104,
					10.592581339176718
				],
				[
					-26.552070556869467,
					11.157519010599458
				],
				[
					-27.117008228292207,
					11.722456682022198
				],
				[
					-27.540711481859375,
					12.004925517733568
				],
				[
					-28.105649153282116,
					12.569863189156308
				],
				[
					-28.2468835711378,
					13.276035278434733
				],
				[
					-28.388117988993486,
					13.982207367713272
				],
				[
					-28.388117988993486,
					14.405910621280327
				],
				[
					-28.52935240684917,
					14.688379456991697
				],
				[
					-28.81182124256054,
					15.253317128414437
				],
				[
					-28.81182124256054,
					15.818254799837177
				],
				[
					-28.953055660416226,
					16.100723635548547
				],
				[
					-29.09429007827191,
					16.524426889115603
				],
				[
					-29.235524496127596,
					16.948130142682658
				],
				[
					-29.37675891398328,
					17.230598978394028
				],
				[
					-29.517993331838966,
					17.513067814105398
				],
				[
					-29.65922774969465,
					18.078005485528138
				],
				[
					-29.800462167550336,
					18.501708739095307
				],
				[
					-29.94169658540602,
					18.784177574806677
				],
				[
					-30.36539983897319,
					19.20788082837373
				],
				[
					-30.64786867468456,
					19.349115246229417
				],
				[
					-30.789103092540245,
					19.77281849979647
				],
				[
					-31.071571928251615,
					20.196521753363527
				],
				[
					-31.2128063461073,
					20.761459424786267
				],
				[
					-31.354040763962985,
					21.043928260497637
				],
				[
					-31.49527518181867,
					21.326397096209007
				],
				[
					-31.49527518181867,
					21.750100349776176
				],
				[
					-31.636509599674355,
					21.89133476763186
				],
				[
					-31.636509599674355,
					22.17380360334323
				],
				[
					-31.636509599674355,
					22.4562724390546
				],
				[
					-31.636509599674355,
					22.597506856910286
				],
				[
					-31.636509599674355,
					22.879975692621656
				],
				[
					-31.636509599674355,
					23.02121011047734
				],
				[
					-31.636509599674355,
					23.162444528333026
				],
				[
					-31.636509599674355,
					23.162444528333026
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 160,
			"versionNonce": 458637545,
			"isDeleted": false,
			"id": "D-oU5HncUqUclLgPfiCwQ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1151.3543644885478,
			"y": 923.8209997572242,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 10.592581339176718,
			"height": 22.4562724390546,
			"seed": 808153351,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989890,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.28246883571137005,
					0.14123441785568502
				],
				[
					0.8474065071341101,
					0.42370325356705507
				],
				[
					1.553578596412649,
					0.9886409249897952
				],
				[
					2.965922774969499,
					1.5535785964125353
				],
				[
					4.378266953526349,
					2.542219521402444
				],
				[
					5.366907878516145,
					3.2483916106808692
				],
				[
					6.3555488035060534,
					4.5195013713820344
				],
				[
					6.9204864749287935,
					5.931845549938885
				],
				[
					7.485424146351534,
					8.191596235629959
				],
				[
					7.485424146351534,
					9.886409249898179
				],
				[
					7.767892982062904,
					12.146159935589253
				],
				[
					7.767892982062904,
					14.123441785568957
				],
				[
					7.767892982062904,
					15.535785964125807
				],
				[
					7.202955310640164,
					17.371833396249713
				],
				[
					6.6380176392174235,
					18.784177574806677
				],
				[
					5.931845549938885,
					20.055287335507842
				],
				[
					5.22567346066046,
					21.04392826049775
				],
				[
					4.5195013713820344,
					21.60886593192049
				],
				[
					3.8133292821036093,
					21.60886593192049
				],
				[
					3.107157192825184,
					21.750100349776176
				],
				[
					2.118516267835389,
					21.89133476763186
				],
				[
					1.553578596412649,
					21.89133476763186
				],
				[
					0.8474065071341101,
					21.750100349776176
				],
				[
					0.14123441785568502,
					21.185162678353436
				],
				[
					-0.5649376714227401,
					20.478990589074897
				],
				[
					-1.412344178556964,
					19.914052917652157
				],
				[
					-2.259750685691074,
					18.92541199266236
				],
				[
					-2.683453939258129,
					17.654302231961196
				],
				[
					-2.824688357113814,
					16.665661306971288
				],
				[
					-2.824688357113814,
					14.970848292703067
				],
				[
					-2.824688357113814,
					13.417269696290418
				],
				[
					-2.683453939258129,
					11.439987846310828
				],
				[
					-2.118516267835389,
					9.745174832042494
				],
				[
					-1.836047432124019,
					8.332830653485644
				],
				[
					-1.1298753428454802,
					7.061720892784479
				],
				[
					-0.5649376714227401,
					5.22567346066046
				],
				[
					-0.14123441785568502,
					3.6720948642479243
				],
				[
					0.14123441785568502,
					2.965922774969499
				],
				[
					0.28246883571137005,
					2.1185162678352754
				],
				[
					0.7061720892784251,
					1.2711097607011652
				],
				[
					0.8474065071341101,
					0.7061720892784251
				],
				[
					0.9886409249897952,
					0.28246883571137005
				],
				[
					1.1298753428454802,
					0
				],
				[
					1.4123441785568502,
					-0.14123441785568502
				],
				[
					1.694813014268334,
					-0.28246883571137005
				],
				[
					1.977281849979704,
					-0.5649376714227401
				],
				[
					2.259750685691074,
					-0.5649376714227401
				],
				[
					2.400985103546759,
					-0.5649376714227401
				],
				[
					2.542219521402444,
					-0.5649376714227401
				],
				[
					2.683453939258129,
					-0.5649376714227401
				],
				[
					2.683453939258129,
					-0.42370325356705507
				],
				[
					2.683453939258129,
					-0.28246883571137005
				],
				[
					2.824688357113814,
					-0.14123441785568502
				],
				[
					2.824688357113814,
					-0.14123441785568502
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 128,
			"versionNonce": 484007463,
			"isDeleted": false,
			"id": "Fg38pxqNj82hjs7Cn0S2r",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1158.1336165456207,
			"y": 931.1651894857202,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 9.321471578475553,
			"height": 2.683453939258129,
			"seed": 667269159,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.14123441785568502,
					0
				],
				[
					-0.8474065071342238,
					0.14123441785568502
				],
				[
					-1.412344178556964,
					0.42370325356705507
				],
				[
					-1.977281849979704,
					0.9886409249897952
				],
				[
					-2.683453939258129,
					1.4123441785568502
				],
				[
					-3.2483916106808692,
					1.5535785964125353
				],
				[
					-3.9545636999592944,
					1.6948130142682203
				],
				[
					-4.5195013713820344,
					1.9772818499795903
				],
				[
					-4.8019702070934045,
					1.9772818499795903
				],
				[
					-5.0844390428047745,
					2.1185162678352754
				],
				[
					-5.366907878516258,
					2.2597506856909604
				],
				[
					-5.931845549938998,
					2.2597506856909604
				],
				[
					-6.214314385650368,
					2.4009851035466454
				],
				[
					-6.7792520570731085,
					2.4009851035466454
				],
				[
					-7.202955310640164,
					2.5422195214023304
				],
				[
					-7.485424146351534,
					2.683453939258129
				],
				[
					-7.909127399918589,
					2.683453939258129
				],
				[
					-8.474065071341442,
					2.683453939258129
				],
				[
					-8.897768324908498,
					2.683453939258129
				],
				[
					-9.180237160619868,
					2.5422195214023304
				],
				[
					-9.321471578475553,
					2.4009851035466454
				],
				[
					-9.321471578475553,
					2.4009851035466454
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"id": "37HtcClYa_hVYewXfew1S",
			"type": "freedraw",
			"x": 1012.2439769318258,
			"y": 952.5251429928737,
			"width": 0.6587275045662864,
			"height": 7.740048178653751,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 566961351,
			"version": 59,
			"versionNonce": 1049639881,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.1646818761415716
				],
				[
					0,
					0.4940456284247148
				],
				[
					0.1646818761415716,
					0.9880912568494296
				],
				[
					0.3293637522831432,
					1.646818761415716
				],
				[
					0.3293637522831432,
					2.470228142123574
				],
				[
					0.4940456284247148,
					2.964273770548175
				],
				[
					0.4940456284247148,
					3.6230012751144614
				],
				[
					0.4940456284247148,
					4.117046903539176
				],
				[
					0.4940456284247148,
					4.446410655822319
				],
				[
					0.4940456284247148,
					4.7757744081054625
				],
				[
					0.4940456284247148,
					5.105138160388606
				],
				[
					0.4940456284247148,
					5.434501912671749
				],
				[
					0.4940456284247148,
					5.928547541096464
				],
				[
					0.4940456284247148,
					6.257911293379607
				],
				[
					0.4940456284247148,
					6.58727504566275
				],
				[
					0.4940456284247148,
					6.916638797945893
				],
				[
					0.4940456284247148,
					7.246002550229036
				],
				[
					0.4940456284247148,
					7.410684426370608
				],
				[
					0.4940456284247148,
					7.57536630251218
				],
				[
					0.4940456284247148,
					7.740048178653751
				],
				[
					0.6587275045662864,
					7.740048178653751
				],
				[
					0.6587275045662864,
					7.740048178653751
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				0.6587275045662864,
				7.740048178653751
			]
		},
		{
			"id": "df9N2RA3kdqIlXevB1lAK",
			"type": "freedraw",
			"x": 1162.2550683971317,
			"y": 937.8826319834611,
			"width": 5.434501912671749,
			"height": 5.928547541096464,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 886882247,
			"version": 56,
			"versionNonce": 1584988487,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4940456284246011,
					0
				],
				[
					1.3174550091325727,
					0
				],
				[
					2.140864389840317,
					0
				],
				[
					2.47022814212346,
					0
				],
				[
					2.6349100182651455,
					0
				],
				[
					2.6349100182651455,
					0.3293637522831432
				],
				[
					2.6349100182651455,
					0.4940456284247148
				],
				[
					2.6349100182651455,
					1.1527731329910011
				],
				[
					2.6349100182651455,
					1.646818761415716
				],
				[
					2.6349100182651455,
					2.3055462659820023
				],
				[
					2.6349100182651455,
					2.799591894406717
				],
				[
					2.6349100182651455,
					3.4583193989730034
				],
				[
					2.47022814212346,
					3.7876831512561466
				],
				[
					1.9761825136988591,
					3.9523650273977182
				],
				[
					1.4821368852740306,
					4.11704690353929
				],
				[
					0.6587275045662864,
					4.281728779680861
				],
				[
					-0.16468187614168528,
					4.611092531964005
				],
				[
					-1.1527731329911148,
					4.7757744081054625
				],
				[
					-1.9761825136988591,
					4.940456284247148
				],
				[
					-2.3055462659820023,
					5.434501912671749
				],
				[
					-2.4702281421236876,
					5.763865664954892
				],
				[
					-2.6349100182651455,
					5.763865664954892
				],
				[
					-2.6349100182651455,
					5.5991837888133205
				],
				[
					-2.4702281421236876,
					5.269820036530177
				],
				[
					-2.140864389840317,
					4.940456284247148
				],
				[
					-1.8115006375574012,
					4.940456284247148
				],
				[
					-1.3174550091325727,
					4.7757744081054625
				],
				[
					-0.9880912568494296,
					4.611092531964005
				],
				[
					-0.8234093807079716,
					4.611092531964005
				],
				[
					-0.6587275045662864,
					4.611092531964005
				],
				[
					-0.49404562842482846,
					4.611092531964005
				],
				[
					-0.3293637522831432,
					4.611092531964005
				],
				[
					-0.16468187614168528,
					4.611092531964005
				],
				[
					0.1646818761414579,
					4.7757744081054625
				],
				[
					0.6587275045662864,
					4.940456284247148
				],
				[
					0.9880912568494296,
					5.269820036530177
				],
				[
					1.3174550091325727,
					5.434501912671749
				],
				[
					1.4821368852740306,
					5.5991837888133205
				],
				[
					1.8115006375571738,
					5.763865664954892
				],
				[
					2.140864389840317,
					5.928547541096464
				],
				[
					2.3055462659820023,
					5.928547541096464
				],
				[
					2.47022814212346,
					5.928547541096464
				],
				[
					2.6349100182651455,
					5.928547541096464
				],
				[
					2.7995918944066034,
					5.928547541096464
				],
				[
					2.7995918944066034,
					5.928547541096464
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				2.7995918944066034,
				5.928547541096464
			]
		},
		{
			"type": "arrow",
			"version": 497,
			"versionNonce": 579328681,
			"isDeleted": false,
			"id": "dLSYjaPESfdqYoPiV0IMZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1019.1052836607109,
			"y": 988.5940595517458,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 146.63005459247734,
			"height": 131.63916141143812,
			"seed": 799764009,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989891,
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
					146.63005459247734,
					-131.63916141143812
				]
			]
		},
		{
			"type": "arrow",
			"version": 490,
			"versionNonce": 242696295,
			"isDeleted": false,
			"id": "9ukXmpPEPNabQWN_E6IZI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1174.2827018430035,
			"y": 988.5940595517459,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 146.63005459247734,
			"height": 131.63916141143812,
			"seed": 1503812873,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989891,
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
					146.63005459247734,
					-131.63916141143812
				]
			]
		},
		{
			"id": "-DiVNC17X8WdXEb5l_7nr",
			"type": "freedraw",
			"x": 1179.1083271130692,
			"y": 946.0759829044144,
			"width": 26.98725157700028,
			"height": 10.927353399276171,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1891933481,
			"version": 52,
			"versionNonce": 669556105,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.1655659605951314,
					0
				],
				[
					0.8278298029754296,
					0
				],
				[
					1.4900936453559552,
					0
				],
				[
					2.1523574877362535,
					0
				],
				[
					3.1457532513068145,
					0.1655659605950177
				],
				[
					3.973583054282244,
					0.3311319211901491
				],
				[
					4.966978817852805,
					0.3311319211901491
				],
				[
					5.629242660233103,
					0.3311319211901491
				],
				[
					6.45707246320876,
					0.3311319211901491
				],
				[
					7.28490226618419,
					0.3311319211901491
				],
				[
					7.947166108564488,
					0.4966978817852805
				],
				[
					8.94056187213505,
					0.4966978817852805
				],
				[
					9.93395763570561,
					0.8278298029754296
				],
				[
					10.76178743868104,
					0.993395763570561
				],
				[
					11.920749162846732,
					1.3245276847607101
				],
				[
					13.079710887012425,
					1.8212255665459907
				],
				[
					14.404238571773249,
					1.986791527141122
				],
				[
					15.39763433534381,
					2.649055369521534
				],
				[
					16.39103009891437,
					3.145753251306701
				],
				[
					17.2188599018898,
					3.4768851724969636
				],
				[
					18.377821626055493,
					4.139149014877262
				],
				[
					19.04008546843579,
					4.635846896662656
				],
				[
					19.702349310816317,
					5.1325447784479366
				],
				[
					20.695745074386878,
					5.629242660233217
				],
				[
					21.358008916767176,
					6.291506502613515
				],
				[
					22.020272759147474,
					6.788204384398796
				],
				[
					22.51697064093287,
					7.119336305589059
				],
				[
					22.84810256212313,
					7.284902266184076
				],
				[
					23.344800443908298,
					7.450468226779208
				],
				[
					23.67593236509856,
					7.781600147969357
				],
				[
					24.172630246883728,
					8.11273206915962
				],
				[
					25.000460049859157,
					8.6094299509449
				],
				[
					25.33159197104942,
					8.94056187213505
				],
				[
					25.662723892239683,
					9.271693793325198
				],
				[
					25.993855813429718,
					9.43725975392033
				],
				[
					26.32498773461998,
					9.768391675110593
				],
				[
					26.490553695215112,
					9.93395763570561
				],
				[
					26.656119655810244,
					10.26508955689576
				],
				[
					26.656119655810244,
					10.43065551749089
				],
				[
					26.821685616405375,
					10.927353399276171
				],
				[
					26.98725157700028,
					10.927353399276171
				],
				[
					26.98725157700028,
					10.927353399276171
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				26.98725157700028,
				10.927353399276171
			]
		},
		{
			"id": "CFvi8U6_syWnEnO6a_lQW",
			"type": "freedraw",
			"x": 1020.782821212876,
			"y": 933.8225593095274,
			"width": 38.8377912993966,
			"height": 17.00925166396928,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1967416233,
			"version": 59,
			"versionNonce": 513842055,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.850462583198464,
					0
				],
				[
					1.9844126941297873,
					0
				],
				[
					3.4018503327939698,
					0
				],
				[
					4.535800443725179,
					0
				],
				[
					5.953238082389248,
					0
				],
				[
					7.370675721053317,
					0
				],
				[
					8.221138304251895,
					0
				],
				[
					9.071600887450245,
					0.28348752773285923
				],
				[
					9.922063470648823,
					0.5669750554657185
				],
				[
					11.056013581580032,
					0.850462583198464
				],
				[
					12.189963692511242,
					1.1339501109313233
				],
				[
					12.75693874797696,
					1.4174376386640688
				],
				[
					14.174376386641029,
					1.700925166396928
				],
				[
					15.875301553037957,
					1.9844126941297873
				],
				[
					17.292739191702026,
					2.2679002218626465
				],
				[
					18.710176830366322,
					3.118362805060997
				],
				[
					19.84412694129753,
					3.401850332793856
				],
				[
					20.694589524495882,
					3.6853378605267153
				],
				[
					21.54505210769446,
					4.25231291599232
				],
				[
					22.112027163160178,
					4.535800443725179
				],
				[
					23.245977274091388,
					5.386263026923643
				],
				[
					24.096439857289738,
					5.953238082389248
				],
				[
					24.663414912755456,
					6.520213137854853
				],
				[
					25.513877495954034,
					6.803700665587712
				],
				[
					26.364340079152385,
					7.654163248786176
				],
				[
					27.214802662350962,
					8.221138304251781
				],
				[
					28.065265245549313,
					8.7881133597175
				],
				[
					29.19921535648075,
					9.355088415183104
				],
				[
					30.0496779396791,
					10.205550998381568
				],
				[
					30.90014052287745,
					10.772526053847287
				],
				[
					31.46711557834317,
					11.339501109312891
				],
				[
					32.317578161541746,
					11.906476164778496
				],
				[
					33.1680407447401,
					12.189963692511355
				],
				[
					34.018503327938674,
					13.04042627570982
				],
				[
					34.585478383404165,
					13.323913803442565
				],
				[
					35.152453438869884,
					13.607401331175424
				],
				[
					35.7194284943356,
					14.174376386641143
				],
				[
					36.00291602206846,
					14.457863914373888
				],
				[
					36.85337860526681,
					15.024838969839607
				],
				[
					36.85337860526681,
					15.308326497572352
				],
				[
					37.13686613299967,
					15.308326497572352
				],
				[
					37.42035366073253,
					15.591814025305212
				],
				[
					37.70384118846516,
					15.591814025305212
				],
				[
					37.98732871619802,
					16.158789080770816
				],
				[
					38.27081624393088,
					16.158789080770816
				],
				[
					38.27081624393088,
					16.442276608503676
				],
				[
					38.55430377166374,
					16.442276608503676
				],
				[
					38.8377912993966,
					17.00925166396928
				],
				[
					38.8377912993966,
					17.00925166396928
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				38.8377912993966,
				17.00925166396928
			]
		},
		{
			"type": "freedraw",
			"version": 260,
			"versionNonce": 233702505,
			"isDeleted": false,
			"id": "kKqpNIwETWGIN2TLyyOdU",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1034.158281184059,
			"y": 939.1624025570326,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 11.871201968765149,
			"height": 18.142780367358,
			"seed": 823460809,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33597741421033334,
					0.22398494280696468
				],
				[
					0.783947299824149,
					0.33597741421033334
				],
				[
					1.4559021282448157,
					0.559962357017298
				],
				[
					1.9038720138586314,
					0.783947299824149
				],
				[
					2.4638343708758157,
					1.1199247140344823
				],
				[
					2.799811785086149,
					1.567894599648298
				],
				[
					3.1357891992964824,
					1.791879542455149
				],
				[
					3.6957515563136667,
					2.2398494280689647
				],
				[
					4.031728970524,
					2.6878193136826667
				],
				[
					4.255713913330965,
					3.2477816706999647
				],
				[
					4.479698856137816,
					3.6957515563136667
				],
				[
					4.703683798944667,
					4.143721441927482
				],
				[
					4.927668741751631,
					4.591691327541298
				],
				[
					5.039661213155,
					4.927668741751518
				],
				[
					5.263646155961965,
					5.599623570172184
				],
				[
					5.375638627365333,
					6.047593455786
				],
				[
					5.487631098768816,
					6.383570869996333
				],
				[
					5.599623570172298,
					6.831540755610149
				],
				[
					5.823608512979149,
					7.391503112627333
				],
				[
					5.823608512979149,
					7.839472998241149
				],
				[
					5.935600984382631,
					8.287442883854851
				],
				[
					6.047593455786,
					9.183382655082482
				],
				[
					6.047593455786,
					9.743345012099667
				],
				[
					6.047593455786,
					10.191314897713482
				],
				[
					6.159585927189482,
					10.751277254730667
				],
				[
					6.159585927189482,
					11.199247140344482
				],
				[
					6.159585927189482,
					11.647217025958184
				],
				[
					6.159585927189482,
					12.431164325782333
				],
				[
					6.159585927189482,
					12.991126682799518
				],
				[
					6.159585927189482,
					13.327104097009851
				],
				[
					6.047593455786,
					13.775073982623667
				],
				[
					5.935600984382631,
					14.223043868237482
				],
				[
					5.711616041575667,
					14.89499869665815
				],
				[
					5.151653684558482,
					15.454961053675333
				],
				[
					4.927668741751631,
					15.90293093928915
				],
				[
					4.703683798944667,
					16.574885767709816
				],
				[
					4.591691327541298,
					17.022855653323518
				],
				[
					4.367706384734333,
					17.35883306753385
				],
				[
					4.255713913330965,
					17.694810481744184
				],
				[
					4.031728970524,
					17.806802953147667
				],
				[
					3.583759084910298,
					18.030787895954518
				],
				[
					3.2477816706999647,
					18.142780367358
				],
				[
					2.799811785086149,
					18.142780367358
				],
				[
					2.3518418994723334,
					18.142780367358
				],
				[
					1.9038720138586314,
					18.142780367358
				],
				[
					1.3439096568413333,
					18.142780367358
				],
				[
					0.559962357017298,
					18.142780367358
				],
				[
					0,
					18.030787895954518
				],
				[
					-0.6719548284206667,
					17.806802953147667
				],
				[
					-1.1199247140343687,
					17.694810481744184
				],
				[
					-1.6798870710516667,
					17.35883306753385
				],
				[
					-2.015864485262,
					17.134848124727
				],
				[
					-2.463834370875702,
					16.798870710516667
				],
				[
					-3.1357891992963687,
					16.462893296306333
				],
				[
					-3.5837590849101844,
					16.126915882096
				],
				[
					-4.031728970524,
					15.566953525078816
				],
				[
					-4.255713913330851,
					15.454961053675333
				],
				[
					-4.479698856137702,
					15.118983639465
				],
				[
					-4.815676270348035,
					14.671013753851184
				],
				[
					-5.039661213155,
					14.335036339640851
				],
				[
					-5.375638627365333,
					13.88706645402715
				],
				[
					-5.599623570172184,
					12.767141739992667
				],
				[
					-5.711616041575667,
					11.983194440168518
				],
				[
					-5.711616041575667,
					11.087254668941
				],
				[
					-5.711616041575667,
					10.527292311923816
				],
				[
					-5.711616041575667,
					9.631352540696184
				],
				[
					-5.711616041575667,
					8.847405240872149
				],
				[
					-5.711616041575667,
					7.839472998241149
				],
				[
					-5.711616041575667,
					7.167518169820482
				],
				[
					-5.711616041575667,
					6.607555812803298
				],
				[
					-5.711616041575667,
					5.935600984382631
				],
				[
					-5.599623570172184,
					5.263646155961965
				],
				[
					-5.599623570172184,
					4.703683798944667
				],
				[
					-5.487631098768702,
					3.9197364991206314
				],
				[
					-5.263646155961851,
					3.2477816706999647
				],
				[
					-5.151653684558369,
					2.9118042564896314
				],
				[
					-5.039661213155,
					2.3518418994723334
				],
				[
					-4.815676270348035,
					1.9038720138586314
				],
				[
					-4.591691327541184,
					1.4559021282448157
				],
				[
					-4.367706384734333,
					1.3439096568413333
				],
				[
					-4.143721441927369,
					1.007932242631
				],
				[
					-4.031728970524,
					0.783947299824149
				],
				[
					-3.9197364991205177,
					0.559962357017298
				],
				[
					-3.6957515563136667,
					0.4479698856138157
				],
				[
					-3.3597741421033334,
					0.4479698856138157
				],
				[
					-3.023796727893,
					0.4479698856138157
				],
				[
					-2.6878193136826667,
					0.4479698856138157
				],
				[
					-2.463834370875702,
					0.33597741421033334
				],
				[
					-2.3518418994723334,
					0.22398494280696468
				],
				[
					-2.239849428068851,
					0.22398494280696468
				],
				[
					-2.1278569566653687,
					0.11199247140348234
				],
				[
					-2.015864485262,
					0.11199247140348234
				],
				[
					-1.9038720138585177,
					0.11199247140348234
				],
				[
					-1.7918795424550353,
					0.11199247140348234
				],
				[
					-1.6798870710516667,
					0.11199247140348234
				],
				[
					-1.5678945996481843,
					0.11199247140348234
				],
				[
					-1.5678945996481843,
					0.11199247140348234
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 164,
			"versionNonce": 322015911,
			"isDeleted": false,
			"id": "u1azfKtJ9zCrGzLHvHJzH",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1029.678582327921,
			"y": 947.0018755552738,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 2033427113,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989891,
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
			"version": 164,
			"versionNonce": 543395657,
			"isDeleted": false,
			"id": "wAHBr9owuj8TQrrNRbyx2",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1038.6379800401967,
			"y": 945.4339809556255,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1172006281,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989891,
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
			"version": 198,
			"versionNonce": 886482375,
			"isDeleted": false,
			"id": "wRqhrDYQsg0fR_bypVgvC",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1038.6379800401967,
			"y": 945.4339809556255,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 9.519360069292816,
			"height": 2.1278569566654824,
			"seed": 1917308009,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.11199247140348234,
					0.11199247140348234
				],
				[
					-0.223984942806851,
					0.11199247140348234
				],
				[
					-0.33597741421033334,
					0.22398494280696468
				],
				[
					-0.6719548284206667,
					0.335977414210447
				],
				[
					-1.007932242631,
					0.4479698856138157
				],
				[
					-1.3439096568413333,
					0.559962357017298
				],
				[
					-2.1278569566654824,
					0.783947299824149
				],
				[
					-2.4638343708758157,
					0.783947299824149
				],
				[
					-2.9118042564895177,
					0.783947299824149
				],
				[
					-3.3597741421033334,
					0.783947299824149
				],
				[
					-3.6957515563136667,
					0.8959397712276314
				],
				[
					-4.031728970524,
					1.1199247140344823
				],
				[
					-4.479698856137816,
					1.2319171854379647
				],
				[
					-4.815676270348149,
					1.3439096568413333
				],
				[
					-5.039661213155,
					1.4559021282448157
				],
				[
					-5.375638627365333,
					1.567894599648298
				],
				[
					-5.599623570172184,
					1.567894599648298
				],
				[
					-5.823608512979149,
					1.567894599648298
				],
				[
					-5.935600984382518,
					1.6798870710516667
				],
				[
					-6.159585927189482,
					1.6798870710516667
				],
				[
					-6.271578398592851,
					1.791879542455149
				],
				[
					-6.607555812803184,
					1.9038720138586314
				],
				[
					-6.831540755610149,
					1.9038720138586314
				],
				[
					-7.055525698417,
					1.9038720138586314
				],
				[
					-7.391503112627333,
					1.9038720138586314
				],
				[
					-7.615488055434184,
					2.015864485262
				],
				[
					-7.839472998241149,
					2.015864485262
				],
				[
					-8.175450412451482,
					2.1278569566654824
				],
				[
					-8.511427826661816,
					2.1278569566654824
				],
				[
					-8.735412769468667,
					2.1278569566654824
				],
				[
					-9.071390183679,
					2.1278569566654824
				],
				[
					-9.295375126485851,
					2.1278569566654824
				],
				[
					-9.407367597889333,
					2.1278569566654824
				],
				[
					-9.519360069292816,
					2.1278569566654824
				],
				[
					-9.519360069292816,
					2.1278569566654824
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 84,
			"versionNonce": 631553577,
			"isDeleted": false,
			"id": "6bxgTF5W-NQQqfTgctWUs",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1044.2108528847784,
			"y": 950.7923458230474,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.6587275045662864,
			"height": 7.740048178653751,
			"seed": 1715754825,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.1646818761415716
				],
				[
					0,
					0.4940456284247148
				],
				[
					0.1646818761415716,
					0.9880912568494296
				],
				[
					0.3293637522831432,
					1.646818761415716
				],
				[
					0.3293637522831432,
					2.470228142123574
				],
				[
					0.4940456284247148,
					2.964273770548175
				],
				[
					0.4940456284247148,
					3.6230012751144614
				],
				[
					0.4940456284247148,
					4.117046903539176
				],
				[
					0.4940456284247148,
					4.446410655822319
				],
				[
					0.4940456284247148,
					4.7757744081054625
				],
				[
					0.4940456284247148,
					5.105138160388606
				],
				[
					0.4940456284247148,
					5.434501912671749
				],
				[
					0.4940456284247148,
					5.928547541096464
				],
				[
					0.4940456284247148,
					6.257911293379607
				],
				[
					0.4940456284247148,
					6.58727504566275
				],
				[
					0.4940456284247148,
					6.916638797945893
				],
				[
					0.4940456284247148,
					7.246002550229036
				],
				[
					0.4940456284247148,
					7.410684426370608
				],
				[
					0.4940456284247148,
					7.57536630251218
				],
				[
					0.4940456284247148,
					7.740048178653751
				],
				[
					0.6587275045662864,
					7.740048178653751
				],
				[
					0.6587275045662864,
					7.740048178653751
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 196,
			"versionNonce": 44848359,
			"isDeleted": false,
			"id": "0ha6MJoALirWB15GgT5LY",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1191.9577472674853,
			"y": 921.7419231227585,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 10.592581339176718,
			"height": 22.4562724390546,
			"seed": 1842957415,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.28246883571137005,
					0.14123441785568502
				],
				[
					0.8474065071341101,
					0.42370325356705507
				],
				[
					1.553578596412649,
					0.9886409249897952
				],
				[
					2.965922774969499,
					1.5535785964125353
				],
				[
					4.378266953526349,
					2.542219521402444
				],
				[
					5.366907878516145,
					3.2483916106808692
				],
				[
					6.3555488035060534,
					4.5195013713820344
				],
				[
					6.9204864749287935,
					5.931845549938885
				],
				[
					7.485424146351534,
					8.191596235629959
				],
				[
					7.485424146351534,
					9.886409249898179
				],
				[
					7.767892982062904,
					12.146159935589253
				],
				[
					7.767892982062904,
					14.123441785568957
				],
				[
					7.767892982062904,
					15.535785964125807
				],
				[
					7.202955310640164,
					17.371833396249713
				],
				[
					6.6380176392174235,
					18.784177574806677
				],
				[
					5.931845549938885,
					20.055287335507842
				],
				[
					5.22567346066046,
					21.04392826049775
				],
				[
					4.5195013713820344,
					21.60886593192049
				],
				[
					3.8133292821036093,
					21.60886593192049
				],
				[
					3.107157192825184,
					21.750100349776176
				],
				[
					2.118516267835389,
					21.89133476763186
				],
				[
					1.553578596412649,
					21.89133476763186
				],
				[
					0.8474065071341101,
					21.750100349776176
				],
				[
					0.14123441785568502,
					21.185162678353436
				],
				[
					-0.5649376714227401,
					20.478990589074897
				],
				[
					-1.412344178556964,
					19.914052917652157
				],
				[
					-2.259750685691074,
					18.92541199266236
				],
				[
					-2.683453939258129,
					17.654302231961196
				],
				[
					-2.824688357113814,
					16.665661306971288
				],
				[
					-2.824688357113814,
					14.970848292703067
				],
				[
					-2.824688357113814,
					13.417269696290418
				],
				[
					-2.683453939258129,
					11.439987846310828
				],
				[
					-2.118516267835389,
					9.745174832042494
				],
				[
					-1.836047432124019,
					8.332830653485644
				],
				[
					-1.1298753428454802,
					7.061720892784479
				],
				[
					-0.5649376714227401,
					5.22567346066046
				],
				[
					-0.14123441785568502,
					3.6720948642479243
				],
				[
					0.14123441785568502,
					2.965922774969499
				],
				[
					0.28246883571137005,
					2.1185162678352754
				],
				[
					0.7061720892784251,
					1.2711097607011652
				],
				[
					0.8474065071341101,
					0.7061720892784251
				],
				[
					0.9886409249897952,
					0.28246883571137005
				],
				[
					1.1298753428454802,
					0
				],
				[
					1.4123441785568502,
					-0.14123441785568502
				],
				[
					1.694813014268334,
					-0.28246883571137005
				],
				[
					1.977281849979704,
					-0.5649376714227401
				],
				[
					2.259750685691074,
					-0.5649376714227401
				],
				[
					2.400985103546759,
					-0.5649376714227401
				],
				[
					2.542219521402444,
					-0.5649376714227401
				],
				[
					2.683453939258129,
					-0.5649376714227401
				],
				[
					2.683453939258129,
					-0.42370325356705507
				],
				[
					2.683453939258129,
					-0.28246883571137005
				],
				[
					2.824688357113814,
					-0.14123441785568502
				],
				[
					2.824688357113814,
					-0.14123441785568502
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 164,
			"versionNonce": 211620105,
			"isDeleted": false,
			"id": "9f-aFZKkc7nZHgjhYlDbz",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1198.7369993245582,
			"y": 929.0861128512546,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 9.321471578475553,
			"height": 2.683453939258129,
			"seed": 1575036807,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.14123441785568502,
					0
				],
				[
					-0.8474065071342238,
					0.14123441785568502
				],
				[
					-1.412344178556964,
					0.42370325356705507
				],
				[
					-1.977281849979704,
					0.9886409249897952
				],
				[
					-2.683453939258129,
					1.4123441785568502
				],
				[
					-3.2483916106808692,
					1.5535785964125353
				],
				[
					-3.9545636999592944,
					1.6948130142682203
				],
				[
					-4.5195013713820344,
					1.9772818499795903
				],
				[
					-4.8019702070934045,
					1.9772818499795903
				],
				[
					-5.0844390428047745,
					2.1185162678352754
				],
				[
					-5.366907878516258,
					2.2597506856909604
				],
				[
					-5.931845549938998,
					2.2597506856909604
				],
				[
					-6.214314385650368,
					2.4009851035466454
				],
				[
					-6.7792520570731085,
					2.4009851035466454
				],
				[
					-7.202955310640164,
					2.5422195214023304
				],
				[
					-7.485424146351534,
					2.683453939258129
				],
				[
					-7.909127399918589,
					2.683453939258129
				],
				[
					-8.474065071341442,
					2.683453939258129
				],
				[
					-8.897768324908498,
					2.683453939258129
				],
				[
					-9.180237160619868,
					2.5422195214023304
				],
				[
					-9.321471578475553,
					2.4009851035466454
				],
				[
					-9.321471578475553,
					2.4009851035466454
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 92,
			"versionNonce": 1681858567,
			"isDeleted": false,
			"id": "8uDhDk7O0Ev6ePkuRpIQK",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1202.8584511760694,
			"y": 935.8035553489957,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 5.434501912671749,
			"height": 5.928547541096464,
			"seed": 847290023,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.4940456284246011,
					0
				],
				[
					1.3174550091325727,
					0
				],
				[
					2.140864389840317,
					0
				],
				[
					2.47022814212346,
					0
				],
				[
					2.6349100182651455,
					0
				],
				[
					2.6349100182651455,
					0.3293637522831432
				],
				[
					2.6349100182651455,
					0.4940456284247148
				],
				[
					2.6349100182651455,
					1.1527731329910011
				],
				[
					2.6349100182651455,
					1.646818761415716
				],
				[
					2.6349100182651455,
					2.3055462659820023
				],
				[
					2.6349100182651455,
					2.799591894406717
				],
				[
					2.6349100182651455,
					3.4583193989730034
				],
				[
					2.47022814212346,
					3.7876831512561466
				],
				[
					1.9761825136988591,
					3.9523650273977182
				],
				[
					1.4821368852740306,
					4.11704690353929
				],
				[
					0.6587275045662864,
					4.281728779680861
				],
				[
					-0.16468187614168528,
					4.611092531964005
				],
				[
					-1.1527731329911148,
					4.7757744081054625
				],
				[
					-1.9761825136988591,
					4.940456284247148
				],
				[
					-2.3055462659820023,
					5.434501912671749
				],
				[
					-2.4702281421236876,
					5.763865664954892
				],
				[
					-2.6349100182651455,
					5.763865664954892
				],
				[
					-2.6349100182651455,
					5.5991837888133205
				],
				[
					-2.4702281421236876,
					5.269820036530177
				],
				[
					-2.140864389840317,
					4.940456284247148
				],
				[
					-1.8115006375574012,
					4.940456284247148
				],
				[
					-1.3174550091325727,
					4.7757744081054625
				],
				[
					-0.9880912568494296,
					4.611092531964005
				],
				[
					-0.8234093807079716,
					4.611092531964005
				],
				[
					-0.6587275045662864,
					4.611092531964005
				],
				[
					-0.49404562842482846,
					4.611092531964005
				],
				[
					-0.3293637522831432,
					4.611092531964005
				],
				[
					-0.16468187614168528,
					4.611092531964005
				],
				[
					0.1646818761414579,
					4.7757744081054625
				],
				[
					0.6587275045662864,
					4.940456284247148
				],
				[
					0.9880912568494296,
					5.269820036530177
				],
				[
					1.3174550091325727,
					5.434501912671749
				],
				[
					1.4821368852740306,
					5.5991837888133205
				],
				[
					1.8115006375571738,
					5.763865664954892
				],
				[
					2.140864389840317,
					5.928547541096464
				],
				[
					2.3055462659820023,
					5.928547541096464
				],
				[
					2.47022814212346,
					5.928547541096464
				],
				[
					2.6349100182651455,
					5.928547541096464
				],
				[
					2.7995918944066034,
					5.928547541096464
				],
				[
					2.7995918944066034,
					5.928547541096464
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"id": "5D0BDVEoCsP_HeQjP6GvE",
			"type": "line",
			"x": 1282.8698021830114,
			"y": 917.3638582950496,
			"width": 223.19764999731296,
			"height": 87.92634696863843,
			"angle": 0,
			"strokeColor": "#1971c2",
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
			"seed": 1401655593,
			"version": 122,
			"versionNonce": 1523058665,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					159.4268928552233,
					-10.628459523681613
				],
				[
					223.19764999731296,
					77.29788744495681
				]
			],
			"lastCommittedPoint": [
				223.19764999731296,
				77.29788744495681
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "KrlOQ77m",
			"type": "text",
			"x": 1336.6902369734707,
			"y": 874.8500202003231,
			"width": 261.45654296875,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 45717159,
			"version": 66,
			"versionNonce": 462128935,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"text": "How do I find the reflection ray?",
			"rawText": "How do I find the reflection ray?",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "How do I find the reflection ray?",
			"lineHeight": 1.25
		},
		{
			"id": "djWRD53lNjSp20-SYAT-5",
			"type": "image",
			"x": 1650.0260149080643,
			"y": 956.5848672540815,
			"width": 212.21762225078623,
			"height": 244.60873301537993,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1972699977,
			"version": 299,
			"versionNonce": 1513169609,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f788cb0eef590d8efa19cb9e6f696f6429103571",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "qzFO5S9l0Hgjf8BgQ1UwA",
			"type": "rectangle",
			"x": 1649.2068904411854,
			"y": 956.0035355047652,
			"width": 215.42258086355127,
			"height": 248.32348412271102,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"seed": 1020763145,
			"version": 269,
			"versionNonce": 1996360263,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false
		},
		{
			"id": "UAC3ueXs",
			"type": "text",
			"x": 1397.76955355979,
			"y": 1001.6418139986083,
			"width": 242.4005126953125,
			"height": 140,
			"angle": 0,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1173516809,
			"version": 173,
			"versionNonce": 125034921,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"text": "r = 2p - l and p = n * dot(n,l)\n\ntherefore \n\nr = 2 (n * dot(n,l)) - l\n\n",
			"rawText": "r = 2p - l and p = n * dot(n,l)\n\ntherefore \n\nr = 2 (n * dot(n,l)) - l\n\n",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 134,
			"containerId": null,
			"originalText": "r = 2p - l and p = n * dot(n,l)\n\ntherefore \n\nr = 2 (n * dot(n,l)) - l\n\n",
			"lineHeight": 1.25
		},
		{
			"id": "Ml7SpJ98_vQ2m09IMrHjE",
			"type": "line",
			"x": -275.37108789444005,
			"y": 222.50661459159085,
			"width": 564.7936419366711,
			"height": 97.15373688610919,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1988389959,
			"version": 843,
			"versionNonce": 1131620711,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-256.8470642262946,
					59.91579926675536
				],
				[
					-564.7936419366711,
					-37.23793761935383
				]
			],
			"lastCommittedPoint": [
				-683.1375293647098,
				-86.53075371953003
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "WE0MMMVM",
			"type": "text",
			"x": -1413.9800194281515,
			"y": 50.312585963310795,
			"width": 240.17971801757812,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1975186503,
			"version": 485,
			"versionNonce": 1069270153,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"text": "Reflection vs Refraction",
			"rawText": "Reflection vs Refraction",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "Reflection vs Refraction",
			"lineHeight": 1.25
		},
		{
			"id": "ZMQhiqY3",
			"type": "text",
			"x": -1798.9861447571611,
			"y": 132.01187299367894,
			"width": 433.9849548339844,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2014561415,
			"version": 145,
			"versionNonce": 2117559431,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"text": "Refraction is when the reflected ray goes through\nthe medium it hits and passes through it to the other\nside given a certain angle",
			"rawText": "Refraction is when the reflected ray goes through\nthe medium it hits and passes through it to the other\nside given a certain angle",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "Refraction is when the reflected ray goes through\nthe medium it hits and passes through it to the other\nside given a certain angle",
			"lineHeight": 1.25
		},
		{
			"id": "mqbtk1up",
			"type": "text",
			"x": -1346.6865673492878,
			"y": 155.1211658894764,
			"width": 22.384048461914062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1484039657,
			"version": 18,
			"versionNonce": 784616297,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"text": "V.S",
			"rawText": "V.S",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "V.S",
			"lineHeight": 1.25
		},
		{
			"id": "SsA65PiV",
			"type": "text",
			"x": -1315.2919061975683,
			"y": 134.21275803137394,
			"width": 472.40093994140625,
			"height": 60,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1531034889,
			"version": 249,
			"versionNonce": 1191656359,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"text": "Reflection is when the light ray bounces off of the surface\nof the object it hits and reflects the color that it\nhit the object with from the light source",
			"rawText": "Reflection is when the light ray bounces off of the surface\nof the object it hits and reflects the color that it\nhit the object with from the light source",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "Reflection is when the light ray bounces off of the surface\nof the object it hits and reflects the color that it\nhit the object with from the light source",
			"lineHeight": 1.25
		},
		{
			"id": "XsCXSFhaBkyFEGkvEgcHV",
			"type": "line",
			"x": -1567.3509265022044,
			"y": 202.54352345412485,
			"width": 131.3032162057891,
			"height": 249.84273352743276,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1105874951,
			"version": 438,
			"versionNonce": 2094593609,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-66.11342843447005,
					167.5381727975788
				],
				[
					65.18978777131906,
					249.84273352743276
				]
			],
			"lastCommittedPoint": [
				-317.47136429888974,
				146.7423194981535
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "s99id0sJ",
			"type": "text",
			"x": -1486.8509020036847,
			"y": 391.5344396842859,
			"width": 658.0333251953125,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2030791497,
			"version": 487,
			"versionNonce": 302984903,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"text": "The angle of refraction is quite important, an ideal one would not change direction\nat all and thus having perfect refraction and is transparent but that more often\nthan not is not the case and the medium ends up bending the light source\nwhich gives off that glass refraction effect (or like water)\nif the angle is too large however the medium becomes black",
			"rawText": "The angle of refraction is quite important, an ideal one would not change direction\nat all and thus having perfect refraction and is transparent but that more often\nthan not is not the case and the medium ends up bending the light source\nwhich gives off that glass refraction effect (or like water)\nif the angle is too large however the medium becomes black",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 94,
			"containerId": null,
			"originalText": "The angle of refraction is quite important, an ideal one would not change direction\nat all and thus having perfect refraction and is transparent but that more often\nthan not is not the case and the medium ends up bending the light source\nwhich gives off that glass refraction effect (or like water)\nif the angle is too large however the medium becomes black",
			"lineHeight": 1.25
		},
		{
			"id": "f4X4m0hb0s55zg39bMhl3",
			"type": "arrow",
			"x": 31.350244019708725,
			"y": 775.8342616831137,
			"width": 0,
			"height": 180.16576248370097,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1030020521,
			"version": 100,
			"versionNonce": 1020609833,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989891,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					180.16576248370097
				]
			],
			"lastCommittedPoint": [
				-9.160970973747453,
				181.6925909793256
			],
			"startBinding": {
				"elementId": "advzfjV0",
				"focus": 0.0988065822438897,
				"gap": 13.83673320881337
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "yJPDlVtN",
			"type": "text",
			"x": -185.1518358701153,
			"y": 968.2554452663007,
			"width": 425.01611328125,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1931253033,
			"version": 65,
			"versionNonce": 434879975,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"text": "Phong Illumination Model",
			"rawText": "Phong Illumination Model",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 32,
			"containerId": null,
			"originalText": "Phong Illumination Model",
			"lineHeight": 1.25
		},
		{
			"id": "RM2yYWDB",
			"type": "text",
			"x": -240.4370302413347,
			"y": 1054.9036007839513,
			"width": 495.5993957519531,
			"height": 50,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2014336745,
			"version": 85,
			"versionNonce": 438614025,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"text": "Phong illumination model is the sum of three parts\n",
			"rawText": "Phong illumination model is the sum of three parts\n",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "Phong illumination model is the sum of three parts\n",
			"lineHeight": 1.25
		},
		{
			"id": "IbIg8igJ",
			"type": "text",
			"x": -276.35732488132567,
			"y": 1108.213225753643,
			"width": 580.722412109375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 126684519,
			"version": 73,
			"versionNonce": 296315143,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "glymOs0Q-Avef36nBpM_6",
					"type": "arrow"
				}
			],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"text": "L(out) = Lambient + Ldiffuse + Lspecular",
			"rawText": "L(out) = Lambient + Ldiffuse + Lspecular",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "L(out) = Lambient + Ldiffuse + Lspecular",
			"lineHeight": 1.25
		},
		{
			"id": "PfIgWr9qLQYc4BB4FvZ4m",
			"type": "arrow",
			"x": 1021.3353619308833,
			"y": 988.2310401952263,
			"width": 260.8897005941027,
			"height": 166.62210671857906,
			"angle": 0,
			"strokeColor": "#2f9e44",
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
			"seed": 28630311,
			"version": 179,
			"versionNonce": 1187172073,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					226.57298878853942,
					-145.12248004521405
				],
				[
					260.8897005941027,
					-166.62210671857906
				]
			],
			"lastCommittedPoint": [
				260.8897005941027,
				-166.62210671857906
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Jernz6JIG-EdivfgdXefQ",
			"type": "arrow",
			"x": 1173.2623530643082,
			"y": 988.2310401952263,
			"width": 112.04613131696033,
			"height": 164.14138056396007,
			"angle": 0,
			"strokeColor": "#2f9e44",
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
			"seed": 1405384553,
			"version": 154,
			"versionNonce": 381988903,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					89.30614156628576,
					-131.4784861948093
				],
				[
					112.04613131696033,
					-164.14138056396007
				]
			],
			"lastCommittedPoint": [
				108.73849644413485,
				-160.8337456911347
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "Uqog7Aw6",
				"focus": 0.31330635343879915,
				"gap": 1
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "Uqog7Aw6",
			"type": "text",
			"x": 1279.118822506567,
			"y": 803.4747632122504,
			"width": 45.90409851074219,
			"height": 20,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 683307305,
			"version": 33,
			"versionNonce": 691734985,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "Jernz6JIG-EdivfgdXefQ",
					"type": "arrow"
				}
			],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"text": "Viewer",
			"rawText": "Viewer",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Viewer",
			"lineHeight": 1.25
		},
		{
			"id": "KLKHx8GnnlczAsCAGKpIC",
			"type": "freedraw",
			"x": 1092.4453579407323,
			"y": 924.6969973753032,
			"width": 5.773454078951545,
			"height": 13.196466466175025,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 365400937,
			"version": 46,
			"versionNonce": 1663701831,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.16495583082712528
				],
				[
					0.1649558308270116,
					0.16495583082712528
				],
				[
					0.1649558308270116,
					0.32991166165436425
				],
				[
					0.32991166165425057,
					0.32991166165436425
				],
				[
					0.49486749248148953,
					0.49486749248148953
				],
				[
					0.6598233233087285,
					0.6598233233087285
				],
				[
					1.154690815790218,
					0.8247791541359675
				],
				[
					1.4846024774444686,
					1.1546908157903317
				],
				[
					1.6495583082717076,
					1.319646646617457
				],
				[
					1.8145141390989465,
					1.8145141390990602
				],
				[
					1.9794699699261855,
					1.9794699699261855
				],
				[
					2.309381631580436,
					2.4743374624077887
				],
				[
					2.804249124062153,
					2.969204954889392
				],
				[
					3.1341607857164036,
					3.6290282781981205
				],
				[
					3.4640724473708815,
					4.12389577067961
				],
				[
					3.793984109025132,
					4.9486749248155775
				],
				[
					4.12389577067961,
					5.608498248124306
				],
				[
					4.288851601506849,
					6.103365740605909
				],
				[
					4.6187632631610995,
					6.763189063914638
				],
				[
					4.7837190939883385,
					7.258056556396241
				],
				[
					4.9486749248155775,
					7.917879879704969
				],
				[
					5.113630755642589,
					8.577703203013698
				],
				[
					5.278586586469828,
					9.237526526322426
				],
				[
					5.278586586469828,
					9.73239401880403
				],
				[
					5.443542417297067,
					10.062305680458394
				],
				[
					5.443542417297067,
					10.392217342112758
				],
				[
					5.443542417297067,
					10.722129003767122
				],
				[
					5.608498248124306,
					11.216996496248726
				],
				[
					5.608498248124306,
					11.54690815790309
				],
				[
					5.773454078951545,
					11.711863988730329
				],
				[
					5.773454078951545,
					12.041775650384693
				],
				[
					5.773454078951545,
					12.371687312039057
				],
				[
					5.773454078951545,
					12.536643142866296
				],
				[
					5.773454078951545,
					12.701598973693422
				],
				[
					5.773454078951545,
					12.866554804520547
				],
				[
					5.773454078951545,
					13.031510635347786
				],
				[
					5.773454078951545,
					13.196466466175025
				],
				[
					5.773454078951545,
					13.196466466175025
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				5.773454078951545,
				13.196466466175025
			]
		},
		{
			"id": "k-W0OD0-os6xPKDkFs8S1",
			"type": "freedraw",
			"x": 1214.0178052603694,
			"y": 928.6559373151557,
			"width": 13.031510635347786,
			"height": 9.73239401880403,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 295040617,
			"version": 52,
			"versionNonce": 1252583593,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.1649558308270116,
					0
				],
				[
					0.9897349849629791,
					0
				],
				[
					1.9794699699261855,
					0.16495583082712528
				],
				[
					3.4640724473708815,
					0.4948674924816032
				],
				[
					4.9486749248155775,
					0.4948674924816032
				],
				[
					5.938409909778784,
					0.4948674924816032
				],
				[
					6.928144894741763,
					0.6598233233087285
				],
				[
					7.42301238722348,
					0.8247791541359675
				],
				[
					8.082835710532208,
					1.1546908157903317
				],
				[
					8.577703203013698,
					1.484602477444696
				],
				[
					8.907614864667948,
					1.8145141390990602
				],
				[
					9.237526526322426,
					2.1444258007534245
				],
				[
					9.567438187976904,
					2.804249124062153
				],
				[
					10.062305680458394,
					3.299116616543756
				],
				[
					10.227261511285633,
					3.7939841090253594
				],
				[
					10.557173172939883,
					4.288851601506849
				],
				[
					10.722129003767122,
					4.783719093988452
				],
				[
					10.887084834594361,
					4.9486749248155775
				],
				[
					11.0520406654216,
					5.278586586469942
				],
				[
					11.216996496248612,
					5.773454078951545
				],
				[
					11.216996496248612,
					5.938409909778784
				],
				[
					11.381952327075851,
					6.268321571433148
				],
				[
					11.54690815790309,
					6.4332774022602734
				],
				[
					11.54690815790309,
					6.598233233087512
				],
				[
					11.711863988730329,
					6.928144894741877
				],
				[
					11.711863988730329,
					7.093100725569116
				],
				[
					11.87681981955734,
					7.258056556396241
				],
				[
					12.04177565038458,
					7.587968218050605
				],
				[
					12.206731481211818,
					7.587968218050605
				],
				[
					12.206731481211818,
					7.752924048877844
				],
				[
					12.371687312039057,
					7.917879879704969
				],
				[
					12.371687312039057,
					8.082835710532208
				],
				[
					12.536643142866296,
					8.247791541359334
				],
				[
					12.536643142866296,
					8.412747372186573
				],
				[
					12.536643142866296,
					8.577703203013812
				],
				[
					12.701598973693308,
					8.742659033840937
				],
				[
					12.701598973693308,
					8.907614864668062
				],
				[
					12.701598973693308,
					9.072570695495301
				],
				[
					12.866554804520547,
					9.072570695495301
				],
				[
					12.866554804520547,
					9.23752652632254
				],
				[
					12.866554804520547,
					9.402482357149665
				],
				[
					13.031510635347786,
					9.567438187976904
				],
				[
					13.031510635347786,
					9.73239401880403
				],
				[
					13.031510635347786,
					9.73239401880403
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				13.031510635347786,
				9.73239401880403
			]
		},
		{
			"id": "ey61vp3LLIyO9si3eOkv0",
			"type": "freedraw",
			"x": 1108.875493873617,
			"y": 912.9919336973719,
			"width": 15.705074464796553,
			"height": 12.132356103136658,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 473033671,
			"version": 82,
			"versionNonce": 1060508263,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.07443163253446983,
					0
				],
				[
					0.4465897952075011,
					-0.07443163253458351
				],
				[
					0.8931795904150022,
					-0.07443163253458351
				],
				[
					1.414201018156973,
					-0.07443163253458351
				],
				[
					1.8607908133644742,
					-0.07443163253458351
				],
				[
					2.3073806085719752,
					-0.07443163253458351
				],
				[
					2.828402036313946,
					0
				],
				[
					3.12612856645228,
					0.14886326506916703
				],
				[
					3.6471499941944785,
					0.4465897952075011
				],
				[
					3.9448765243328126,
					0.7443163253457215
				],
				[
					4.317034687005616,
					1.1909061205532225
				],
				[
					4.6147612171439505,
					1.7863591808298906
				],
				[
					4.838056114747815,
					2.158517343502808
				],
				[
					4.986919379816982,
					2.6051071387103093
				],
				[
					5.135782644886149,
					2.977265301383227
				],
				[
					5.284645909955316,
					3.274991831521561
				],
				[
					5.284645909955316,
					3.423855096590728
				],
				[
					5.284645909955316,
					3.7960132592636455
				],
				[
					5.284645909955316,
					4.242603054471033
				],
				[
					5.284645909955316,
					4.7636244822131175
				],
				[
					5.284645909955316,
					5.210214277420619
				],
				[
					5.284645909955316,
					5.731235705162703
				],
				[
					5.210214277420619,
					6.177825500370204
				],
				[
					5.135782644886149,
					6.401120397973955
				],
				[
					4.986919379816982,
					6.773278560646759
				],
				[
					4.9124877472822845,
					7.071005090785093
				],
				[
					4.7636244822131175,
					7.294299988388843
				],
				[
					4.7636244822131175,
					7.517594885992594
				],
				[
					4.689192849678648,
					7.740889783596344
				],
				[
					4.689192849678648,
					7.964184681200095
				],
				[
					4.6147612171439505,
					8.113047946269262
				],
				[
					4.540329584609481,
					8.261911211338429
				],
				[
					4.540329584609481,
					8.48520610894218
				],
				[
					4.4658979520747835,
					8.634069374011347
				],
				[
					4.391466319540314,
					8.857364271615097
				],
				[
					4.391466319540314,
					9.006227536684264
				],
				[
					4.391466319540314,
					9.080659169218848
				],
				[
					4.317034687005616,
					9.155090801753431
				],
				[
					4.317034687005616,
					9.080659169218848
				],
				[
					4.317034687005616,
					8.857364271615097
				],
				[
					4.317034687005616,
					8.559637741476763
				],
				[
					4.317034687005616,
					8.113047946269262
				],
				[
					4.317034687005616,
					7.517594885992594
				],
				[
					4.317034687005616,
					6.698846928112289
				],
				[
					4.391466319540314,
					5.65680407262812
				],
				[
					4.540329584609481,
					4.689192849678534
				],
				[
					4.689192849678648,
					3.7960132592636455
				],
				[
					4.7636244822131175,
					3.274991831521561
				],
				[
					4.986919379816982,
					2.530675506175726
				],
				[
					5.210214277420619,
					2.009654078433641
				],
				[
					5.433509175024483,
					1.56306428322614
				],
				[
					5.8800989702317565,
					1.116474488018639
				],
				[
					6.103393867835621,
					0.7443163253457215
				],
				[
					6.475552030508425,
					0.37215816267291757
				],
				[
					6.996573458250623,
					0
				],
				[
					7.592026518527291,
					-0.29772653013833406
				],
				[
					8.113047946269262,
					-0.6698846928112516
				],
				[
					8.857364271615097,
					-1.0420428554841692
				],
				[
					9.676112229495402,
					-1.5630642832262538
				],
				[
					10.569291819910404,
					-2.009654078433755
				],
				[
					11.23917651272177,
					-2.307380608572089
				],
				[
					11.909061205532907,
					-2.679538771244893
				],
				[
					12.430082633274878,
					-2.7539704037794763
				],
				[
					12.87667242848238,
					-2.82840203631406
				],
				[
					13.24883059115541,
					-2.9028336688486434
				],
				[
					13.546557121293745,
					-2.9028336688486434
				],
				[
					13.993146916501246,
					-2.9028336688486434
				],
				[
					14.216441814104883,
					-2.977265301383227
				],
				[
					14.514168344243217,
					-2.977265301383227
				],
				[
					14.886326506916248,
					-2.977265301383227
				],
				[
					15.258484669589052,
					-2.977265301383227
				],
				[
					15.481779567192689,
					-2.977265301383227
				],
				[
					15.630642832261856,
					-2.9028336688486434
				],
				[
					15.705074464796553,
					-2.9028336688486434
				],
				[
					15.705074464796553,
					-2.9028336688486434
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				15.705074464796553,
				-2.9028336688486434
			]
		},
		{
			"id": "UnXWq-FvaPstzPv3bdyk4",
			"type": "freedraw",
			"x": 1231.7201714049102,
			"y": 914.3531496563992,
			"width": 13.814618006890214,
			"height": 10.21903249824743,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2034425959,
			"version": 64,
			"versionNonce": 79162249,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.7569653702405503,
					0
				],
				[
					1.7031720830414088,
					0
				],
				[
					2.460137453281959,
					0
				],
				[
					3.40634416608259,
					0
				],
				[
					3.9740681937630598,
					0
				],
				[
					4.73103356400361,
					0.37848268512027516
				],
				[
					5.109516249123772,
					0.9462067128007448
				],
				[
					5.677240276804241,
					1.8924134256014895
				],
				[
					6.244964304484711,
					3.2171028235223957
				],
				[
					6.623446989604872,
					4.1633095363231405
				],
				[
					7.001929674725261,
					5.487998934244047
				],
				[
					7.191171017285342,
					6.244964304484597
				],
				[
					7.3804123598454225,
					6.812688332165067
				],
				[
					7.3804123598454225,
					7.191171017285342
				],
				[
					7.3804123598454225,
					7.3804123598454225
				],
				[
					7.191171017285342,
					7.948136387525892
				],
				[
					6.81268833216518,
					8.137377730085973
				],
				[
					6.4342056470447915,
					8.515860415206248
				],
				[
					5.866481619364322,
					8.705101757766442
				],
				[
					5.29875759168408,
					8.894343100326523
				],
				[
					4.541792221443302,
					8.894343100326523
				],
				[
					4.1633095363231405,
					8.894343100326523
				],
				[
					3.9740681937630598,
					8.894343100326523
				],
				[
					3.784826851202979,
					8.894343100326523
				],
				[
					3.784826851202979,
					8.705101757766442
				],
				[
					3.9740681937630598,
					8.705101757766442
				],
				[
					4.1633095363231405,
					8.326619072646167
				],
				[
					4.541792221443302,
					7.758895044965698
				],
				[
					4.73103356400361,
					7.3804123598454225
				],
				[
					5.48799893424416,
					6.055722961924516
				],
				[
					5.866481619364322,
					5.109516249123772
				],
				[
					6.05572296192463,
					4.352550878883221
				],
				[
					6.244964304484711,
					3.7848268512028653
				],
				[
					6.623446989604872,
					2.8386201384021206
				],
				[
					6.81268833216518,
					2.0816547681615702
				],
				[
					7.191171017285342,
					1.5139307404811007
				],
				[
					7.569653702405731,
					1.1354480553609392
				],
				[
					7.758895044965811,
					0.7569653702405503
				],
				[
					8.326619072646281,
					0.7569653702405503
				],
				[
					8.705101757766442,
					0.5677240276804696
				],
				[
					9.083584442886831,
					0.18924134256019443
				],
				[
					9.462067128006993,
					0
				],
				[
					10.029791155687462,
					-0.18924134256008074
				],
				[
					10.597515183367932,
					-0.5677240276803559
				],
				[
					11.165239211048174,
					-0.7569653702405503
				],
				[
					11.543721896168563,
					-0.9462067128006311
				],
				[
					11.922204581288952,
					-1.1354480553608255
				],
				[
					12.111445923849033,
					-1.3246893979209062
				],
				[
					12.489928608969194,
					-1.3246893979209062
				],
				[
					12.679169951529275,
					-1.3246893979209062
				],
				[
					12.868411294089583,
					-1.3246893979209062
				],
				[
					13.057652636649664,
					-1.3246893979209062
				],
				[
					13.246893979209744,
					-1.3246893979209062
				],
				[
					13.436135321770053,
					-1.3246893979209062
				],
				[
					13.625376664330133,
					-1.3246893979209062
				],
				[
					13.814618006890214,
					-1.3246893979209062
				],
				[
					13.814618006890214,
					-1.3246893979209062
				]
			],
			"pressures": [],
			"simulatePressure": true,
			"lastCommittedPoint": [
				13.814618006890214,
				-1.3246893979209062
			]
		},
		{
			"id": "xyxIaE9V",
			"type": "text",
			"x": 834.3029561908622,
			"y": 1014.031624900905,
			"width": 372.40155029296875,
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
			"seed": 326766951,
			"version": 67,
			"versionNonce": 867511687,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"text": "Lspec = ks * cos( gamma )",
			"rawText": "Lspec = ks * cos( gamma )",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Lspec = ks * cos( gamma )",
			"lineHeight": 1.25
		},
		{
			"id": "2N1Y3Xu7",
			"type": "text",
			"x": 1205.4140350337227,
			"y": 1004.6600161694223,
			"width": 10.128021240234375,
			"height": 20,
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
			"seed": 1131189673,
			"version": 69,
			"versionNonce": 1872990825,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"text": "m",
			"rawText": "m",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "m",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 190,
			"versionNonce": 2078532775,
			"isDeleted": false,
			"id": "rll8Btu90oZ2vUPbaagaa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 876.3690934836523,
			"y": 1056.3298898831026,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6678015211703041,
			"height": 37.062984424947444,
			"seed": 1364234121,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6678015211703041,
					37.062984424947444
				]
			]
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 272063817,
			"isDeleted": false,
			"id": "92OCNybt",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 849.1972407539859,
			"y": 1100.89287430805,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 53.00810241699219,
			"height": 40,
			"seed": 1770501737,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "output\ncolor",
			"rawText": "output\ncolor",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "output\ncolor",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 189,
			"versionNonce": 930002887,
			"isDeleted": false,
			"id": "QZEKhOID-WL8PiSW5GOMN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 977.5246727092594,
			"y": 1050.7203703983078,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.6678015211703041,
			"height": 37.062984424947444,
			"seed": 830210825,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.6678015211703041,
					37.062984424947444
				]
			]
		},
		{
			"type": "text",
			"version": 193,
			"versionNonce": 1171180585,
			"isDeleted": false,
			"id": "L2g2fX60",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 946.5971614471932,
			"y": 1095.6780548077377,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 65.24813842773438,
			"height": 40,
			"seed": 720943593,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Specular\ncolor",
			"rawText": "Specular\ncolor",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Specular\ncolor",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 129,
			"versionNonce": 1550984935,
			"isDeleted": false,
			"id": "l9ASJhe26nzCLTo3glAXa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1125.8036645579239,
			"y": 1054.908116381247,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.669503802925533,
			"height": 36.0612821431921,
			"seed": 91985097,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.669503802925533,
					36.0612821431921
				]
			]
		},
		{
			"type": "text",
			"version": 313,
			"versionNonce": 2018860809,
			"isDeleted": false,
			"id": "B97FmeJa",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 993.0730699367825,
			"y": 1089.6678411172052,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 240.75253295898438,
			"height": 100,
			"seed": 77599657,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Angle between viwer\nand reflected ray\n\ndot ( v , r )\nif both r and v are normalized",
			"rawText": "Angle between viwer\nand reflected ray\n\ndot ( v , r )\nif both r and v are normalized",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Angle between viwer\nand reflected ray\n\ndot ( v , r )\nif both r and v are normalized",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"id": "BpoJ_545MWIT3wZcg4ETb",
			"type": "line",
			"x": 1219.8764510882227,
			"y": 1022.6652649352347,
			"width": 27.37815777304104,
			"height": 38.20907733160675,
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
			"roundness": {
				"type": 2
			},
			"seed": 1157595623,
			"version": 45,
			"versionNonce": 1769648647,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					27.37815777304104,
					38.20907733160675
				]
			],
			"lastCommittedPoint": [
				27.37815777304104,
				38.20907733160675
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "0rw9Gx8h",
			"type": "text",
			"x": 1217.7391313949067,
			"y": 1065.086366539617,
			"width": 161.95874210980756,
			"height": 43.75362066215135,
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
			"seed": 793874151,
			"version": 170,
			"versionNonce": 105289193,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"text": "Describes shinyness\nor how quickly the reflection\nfalls off with larger angles",
			"rawText": "Describes shinyness\nor how quickly the reflection\nfalls off with larger angles",
			"fontSize": 11.667632176573699,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 38.99999999999998,
			"containerId": null,
			"originalText": "Describes shinyness\nor how quickly the reflection\nfalls off with larger angles",
			"lineHeight": 1.25
		},
		{
			"id": "8YhS8lBh",
			"type": "text",
			"x": 784.5024913980897,
			"y": 1201.4416691840315,
			"width": 297.7658458364742,
			"height": 49.93380111262421,
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
			"seed": 847544423,
			"version": 199,
			"versionNonce": 1468324135,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"text": "If Theta1 is larger than 90 our specular\nneeds to be set to zero because we do not\nwant any light coming from under the surface",
			"rawText": "If Theta1 is larger than 90 our specular\nneeds to be set to zero because we do not\nwant any light coming from under the surface",
			"fontSize": 13.315680296699785,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 44.000000000000014,
			"containerId": null,
			"originalText": "If Theta1 is larger than 90 our specular\nneeds to be set to zero because we do not\nwant any light coming from under the surface",
			"lineHeight": 1.25
		},
		{
			"id": "J3I095EH",
			"type": "text",
			"x": 1130.7486807540236,
			"y": 1200.6413108003924,
			"width": 275.49345667988655,
			"height": 65.59354909450364,
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
			"seed": 1688832713,
			"version": 235,
			"versionNonce": 1924001993,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"text": "if our gamma is bigger than 90 in either\ndirection we set specular to zero because\nour cosine will have negative color effects\non our object",
			"rawText": "if our gamma is bigger than 90 in either\ndirection we set specular to zero because\nour cosine will have negative color effects\non our object",
			"fontSize": 13.118709818900726,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60.000000000000014,
			"containerId": null,
			"originalText": "if our gamma is bigger than 90 in either\ndirection we set specular to zero because\nour cosine will have negative color effects\non our object",
			"lineHeight": 1.25
		},
		{
			"id": "GFglWAJzK8A7HxAJbzkte",
			"type": "line",
			"x": 1395.077950223836,
			"y": 1152.0441639907203,
			"width": 468.3620767647849,
			"height": 230.21186824031815,
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
			"roundness": {
				"type": 2
			},
			"seed": 500442087,
			"version": 120,
			"versionNonce": 1274879047,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					136.27484154455624,
					199.78156381774738
				],
				[
					468.3620767647849,
					230.21186824031815
				]
			],
			"lastCommittedPoint": [
				468.3620767647849,
				230.21186824031815
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "PK5PPMLs",
			"type": "text",
			"x": 1637.0537164148543,
			"y": 1344.61917922896,
			"width": 155.92034912109375,
			"height": 20,
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
			"seed": 813152071,
			"version": 46,
			"versionNonce": 1395060649,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"text": "Blinn suggests that",
			"rawText": "Blinn suggests that",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "Blinn suggests that",
			"lineHeight": 1.25
		},
		{
			"id": "04qdqj1G",
			"type": "text",
			"x": 1875.8343797374177,
			"y": 1349.3435225852318,
			"width": 385.12078857421875,
			"height": 60,
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
			"seed": 310184135,
			"version": 193,
			"versionNonce": 180353895,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"text": "Instead of computing the reflection vector which\nhas a lot of operations, we compute the half\nvector for a more efficient way",
			"rawText": "Instead of computing the reflection vector which\nhas a lot of operations, we compute the half\nvector for a more efficient way",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "Instead of computing the reflection vector which\nhas a lot of operations, we compute the half\nvector for a more efficient way",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 293,
			"versionNonce": 2111640201,
			"isDeleted": false,
			"id": "BO-dOP776UEQ0cNFRLuyc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1881.6617707119995,
			"y": 1331.4810474502074,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 335.1058125077377,
			"height": 2.5132935938081573,
			"seed": 696625447,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					335.1058125077377,
					-2.5132935938081573
				]
			]
		},
		{
			"type": "arrow",
			"version": 330,
			"versionNonce": 672790151,
			"isDeleted": false,
			"id": "fXD6avgz1_M9HIlk2HVQI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2046.7013833720603,
			"y": 1328.1299893251298,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.223367239420895,
			"height": 162.5263190662527,
			"seed": 1164176455,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989892,
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
					0.8377645312693858,
					-124.82691515913223
				],
				[
					2.223367239420895,
					-162.5263190662527
				]
			]
		},
		{
			"type": "arrow",
			"version": 336,
			"versionNonce": 2005653865,
			"isDeleted": false,
			"id": "VqCKDkXtRH1CJHIRJDwrK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1904.281413056272,
			"y": 1195.7631933845735,
			"strokeColor": "#fee781",
			"backgroundColor": "#a5d8ff",
			"width": 138.23114765944183,
			"height": 133.20456047182586,
			"seed": 1322044263,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "u81KwZ5L6NdiCTpKJuG-l",
				"focus": 1.293456982070586,
				"gap": 11.488196667917009
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
					138.23114765944183,
					133.20456047182586
				]
			]
		},
		{
			"type": "freedraw",
			"version": 183,
			"versionNonce": 2059898279,
			"isDeleted": false,
			"id": "4WjTeitvi_JCzkZGd4DiX",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2008.1113917683788,
			"y": 1291.3939427354749,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 37.33363760453835,
			"height": 16.705220894234117,
			"seed": 1913439879,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.12655470374420474,
					0
				],
				[
					0.12655470374420474,
					-0.12655470374420474
				],
				[
					0.2531094074884095,
					-0.2531094074882958
				],
				[
					0.37966411123261423,
					-0.5062188149767053
				],
				[
					0.506218814976819,
					-0.8858829262093195
				],
				[
					1.2655470374419338,
					-1.8983205561629575
				],
				[
					1.8983205561629575,
					-2.5310940748838675
				],
				[
					2.4045393711397764,
					-3.1638675936048912
				],
				[
					3.0373128898606865,
					-4.176305223558529
				],
				[
					3.796641112325915,
					-4.809078742279439
				],
				[
					4.555969334791143,
					-5.441852261000463
				],
				[
					5.062188149767849,
					-5.948071075977282
				],
				[
					5.821516372233077,
					-6.707399298442397
				],
				[
					6.833954002186601,
					-7.34017281716342
				],
				[
					7.719836928396035,
					-7.719836928396035
				],
				[
					8.099501039628649,
					-8.352610447117058
				],
				[
					8.985383965838082,
					-8.858829262093764
				],
				[
					9.365048077070583,
					-9.744712188303197
				],
				[
					9.491602780814787,
					-10.37748570702422
				],
				[
					9.997821595791606,
					-11.136813929489335
				],
				[
					10.63059511451263,
					-12.022696855698769
				],
				[
					11.51647804072195,
					-12.528915670675588
				],
				[
					12.275806263187178,
					-13.161689189396498
				],
				[
					13.161689189396611,
					-13.794462708117521
				],
				[
					14.04757211560593,
					-14.174126819350136
				],
				[
					14.80690033807116,
					-14.427236226838545
				],
				[
					15.819337968024684,
					-14.427236226838545
				],
				[
					16.958330301722526,
					-14.93345504181525
				],
				[
					17.844213227931846,
					-15.18656444930366
				],
				[
					18.603541450397074,
					-15.313119153047865
				],
				[
					19.6159790803506,
					-15.43967385679207
				],
				[
					20.248752599071622,
					-15.566228560536274
				],
				[
					20.628416710304236,
					-15.692783264280479
				],
				[
					21.134635525281055,
					-15.819337968024684
				],
				[
					21.640854340257874,
					-15.819337968024684
				],
				[
					22.14707315523458,
					-15.819337968024684
				],
				[
					22.526737266467194,
					-15.819337968024684
				],
				[
					23.159510785188218,
					-15.819337968024684
				],
				[
					23.539174896420832,
					-15.819337968024684
				],
				[
					24.171948415141742,
					-15.819337968024684
				],
				[
					24.804721933862766,
					-15.692783264280479
				],
				[
					25.6906048600722,
					-15.819337968024684
				],
				[
					26.57648778628152,
					-16.199002079257298
				],
				[
					27.588925416235156,
					-16.325556783001502
				],
				[
					28.09514423121186,
					-16.325556783001502
				],
				[
					28.727917749932885,
					-16.452111486745707
				],
				[
					29.234136564909704,
					-16.578666190489912
				],
				[
					29.993464787374933,
					-16.578666190489912
				],
				[
					30.626238306095843,
					-16.705220894234117
				],
				[
					31.259011824816866,
					-16.705220894234117
				],
				[
					31.63867593604948,
					-16.705220894234117
				],
				[
					32.144894751026186,
					-16.705220894234117
				],
				[
					32.651113566003005,
					-16.705220894234117
				],
				[
					33.03077767723562,
					-16.705220894234117
				],
				[
					33.41044178846823,
					-16.705220894234117
				],
				[
					34.04321530718926,
					-16.578666190489912
				],
				[
					34.42287941842187,
					-16.578666190489912
				],
				[
					34.92909823339858,
					-16.578666190489912
				],
				[
					35.435317048375396,
					-16.578666190489912
				],
				[
					35.941535863352215,
					-16.578666190489912
				],
				[
					36.321199974584715,
					-16.578666190489912
				],
				[
					36.827418789561534,
					-16.578666190489912
				],
				[
					37.080528197049944,
					-16.578666190489912
				],
				[
					37.20708290079415,
					-16.705220894234117
				],
				[
					37.33363760453835,
					-16.705220894234117
				],
				[
					37.33363760453835,
					-16.705220894234117
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 237,
			"versionNonce": 561955913,
			"isDeleted": false,
			"id": "1_I0pDfzSnqW1nQ15jP3r",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2028.8904663874355,
			"y": 1280.6564701640627,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 11.871201968765149,
			"height": 18.142780367358,
			"seed": 501243303,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989892,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33597741421033334,
					0.22398494280696468
				],
				[
					0.783947299824149,
					0.33597741421033334
				],
				[
					1.4559021282448157,
					0.559962357017298
				],
				[
					1.9038720138586314,
					0.783947299824149
				],
				[
					2.4638343708758157,
					1.1199247140344823
				],
				[
					2.799811785086149,
					1.567894599648298
				],
				[
					3.1357891992964824,
					1.791879542455149
				],
				[
					3.6957515563136667,
					2.2398494280689647
				],
				[
					4.031728970524,
					2.6878193136826667
				],
				[
					4.255713913330965,
					3.2477816706999647
				],
				[
					4.479698856137816,
					3.6957515563136667
				],
				[
					4.703683798944667,
					4.143721441927482
				],
				[
					4.927668741751631,
					4.591691327541298
				],
				[
					5.039661213155,
					4.927668741751518
				],
				[
					5.263646155961965,
					5.599623570172184
				],
				[
					5.375638627365333,
					6.047593455786
				],
				[
					5.487631098768816,
					6.383570869996333
				],
				[
					5.599623570172298,
					6.831540755610149
				],
				[
					5.823608512979149,
					7.391503112627333
				],
				[
					5.823608512979149,
					7.839472998241149
				],
				[
					5.935600984382631,
					8.287442883854851
				],
				[
					6.047593455786,
					9.183382655082482
				],
				[
					6.047593455786,
					9.743345012099667
				],
				[
					6.047593455786,
					10.191314897713482
				],
				[
					6.159585927189482,
					10.751277254730667
				],
				[
					6.159585927189482,
					11.199247140344482
				],
				[
					6.159585927189482,
					11.647217025958184
				],
				[
					6.159585927189482,
					12.431164325782333
				],
				[
					6.159585927189482,
					12.991126682799518
				],
				[
					6.159585927189482,
					13.327104097009851
				],
				[
					6.047593455786,
					13.775073982623667
				],
				[
					5.935600984382631,
					14.223043868237482
				],
				[
					5.711616041575667,
					14.89499869665815
				],
				[
					5.151653684558482,
					15.454961053675333
				],
				[
					4.927668741751631,
					15.90293093928915
				],
				[
					4.703683798944667,
					16.574885767709816
				],
				[
					4.591691327541298,
					17.022855653323518
				],
				[
					4.367706384734333,
					17.35883306753385
				],
				[
					4.255713913330965,
					17.694810481744184
				],
				[
					4.031728970524,
					17.806802953147667
				],
				[
					3.583759084910298,
					18.030787895954518
				],
				[
					3.2477816706999647,
					18.142780367358
				],
				[
					2.799811785086149,
					18.142780367358
				],
				[
					2.3518418994723334,
					18.142780367358
				],
				[
					1.9038720138586314,
					18.142780367358
				],
				[
					1.3439096568413333,
					18.142780367358
				],
				[
					0.559962357017298,
					18.142780367358
				],
				[
					0,
					18.030787895954518
				],
				[
					-0.6719548284206667,
					17.806802953147667
				],
				[
					-1.1199247140343687,
					17.694810481744184
				],
				[
					-1.6798870710516667,
					17.35883306753385
				],
				[
					-2.015864485262,
					17.134848124727
				],
				[
					-2.463834370875702,
					16.798870710516667
				],
				[
					-3.1357891992963687,
					16.462893296306333
				],
				[
					-3.5837590849101844,
					16.126915882096
				],
				[
					-4.031728970524,
					15.566953525078816
				],
				[
					-4.255713913330851,
					15.454961053675333
				],
				[
					-4.479698856137702,
					15.118983639465
				],
				[
					-4.815676270348035,
					14.671013753851184
				],
				[
					-5.039661213155,
					14.335036339640851
				],
				[
					-5.375638627365333,
					13.88706645402715
				],
				[
					-5.599623570172184,
					12.767141739992667
				],
				[
					-5.711616041575667,
					11.983194440168518
				],
				[
					-5.711616041575667,
					11.087254668941
				],
				[
					-5.711616041575667,
					10.527292311923816
				],
				[
					-5.711616041575667,
					9.631352540696184
				],
				[
					-5.711616041575667,
					8.847405240872149
				],
				[
					-5.711616041575667,
					7.839472998241149
				],
				[
					-5.711616041575667,
					7.167518169820482
				],
				[
					-5.711616041575667,
					6.607555812803298
				],
				[
					-5.711616041575667,
					5.935600984382631
				],
				[
					-5.599623570172184,
					5.263646155961965
				],
				[
					-5.599623570172184,
					4.703683798944667
				],
				[
					-5.487631098768702,
					3.9197364991206314
				],
				[
					-5.263646155961851,
					3.2477816706999647
				],
				[
					-5.151653684558369,
					2.9118042564896314
				],
				[
					-5.039661213155,
					2.3518418994723334
				],
				[
					-4.815676270348035,
					1.9038720138586314
				],
				[
					-4.591691327541184,
					1.4559021282448157
				],
				[
					-4.367706384734333,
					1.3439096568413333
				],
				[
					-4.143721441927369,
					1.007932242631
				],
				[
					-4.031728970524,
					0.783947299824149
				],
				[
					-3.9197364991205177,
					0.559962357017298
				],
				[
					-3.6957515563136667,
					0.4479698856138157
				],
				[
					-3.3597741421033334,
					0.4479698856138157
				],
				[
					-3.023796727893,
					0.4479698856138157
				],
				[
					-2.6878193136826667,
					0.4479698856138157
				],
				[
					-2.463834370875702,
					0.33597741421033334
				],
				[
					-2.3518418994723334,
					0.22398494280696468
				],
				[
					-2.239849428068851,
					0.22398494280696468
				],
				[
					-2.1278569566653687,
					0.11199247140348234
				],
				[
					-2.015864485262,
					0.11199247140348234
				],
				[
					-1.9038720138585177,
					0.11199247140348234
				],
				[
					-1.7918795424550353,
					0.11199247140348234
				],
				[
					-1.6798870710516667,
					0.11199247140348234
				],
				[
					-1.5678945996481843,
					0.11199247140348234
				],
				[
					-1.5678945996481843,
					0.11199247140348234
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 141,
			"versionNonce": 1307918535,
			"isDeleted": false,
			"id": "c8almAZkGkcScQjHjVnXy",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2024.410767531298,
			"y": 1288.4959431623038,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 896798919,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989892,
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
			"version": 141,
			"versionNonce": 663835433,
			"isDeleted": false,
			"id": "3c2YmdR2OwDS23RypO6O5",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2033.3701652435734,
			"y": 1286.9280485626555,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 40132583,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
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
			"version": 175,
			"versionNonce": 1396674535,
			"isDeleted": false,
			"id": "JHN9dh_bJ8UGuJxbfZXTs",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2033.3701652435734,
			"y": 1286.9280485626555,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 9.519360069292816,
			"height": 2.1278569566654824,
			"seed": 1723714311,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.11199247140348234,
					0.11199247140348234
				],
				[
					-0.223984942806851,
					0.11199247140348234
				],
				[
					-0.33597741421033334,
					0.22398494280696468
				],
				[
					-0.6719548284206667,
					0.335977414210447
				],
				[
					-1.007932242631,
					0.4479698856138157
				],
				[
					-1.3439096568413333,
					0.559962357017298
				],
				[
					-2.1278569566654824,
					0.783947299824149
				],
				[
					-2.4638343708758157,
					0.783947299824149
				],
				[
					-2.9118042564895177,
					0.783947299824149
				],
				[
					-3.3597741421033334,
					0.783947299824149
				],
				[
					-3.6957515563136667,
					0.8959397712276314
				],
				[
					-4.031728970524,
					1.1199247140344823
				],
				[
					-4.479698856137816,
					1.2319171854379647
				],
				[
					-4.815676270348149,
					1.3439096568413333
				],
				[
					-5.039661213155,
					1.4559021282448157
				],
				[
					-5.375638627365333,
					1.567894599648298
				],
				[
					-5.599623570172184,
					1.567894599648298
				],
				[
					-5.823608512979149,
					1.567894599648298
				],
				[
					-5.935600984382518,
					1.6798870710516667
				],
				[
					-6.159585927189482,
					1.6798870710516667
				],
				[
					-6.271578398592851,
					1.791879542455149
				],
				[
					-6.607555812803184,
					1.9038720138586314
				],
				[
					-6.831540755610149,
					1.9038720138586314
				],
				[
					-7.055525698417,
					1.9038720138586314
				],
				[
					-7.391503112627333,
					1.9038720138586314
				],
				[
					-7.615488055434184,
					2.015864485262
				],
				[
					-7.839472998241149,
					2.015864485262
				],
				[
					-8.175450412451482,
					2.1278569566654824
				],
				[
					-8.511427826661816,
					2.1278569566654824
				],
				[
					-8.735412769468667,
					2.1278569566654824
				],
				[
					-9.071390183679,
					2.1278569566654824
				],
				[
					-9.295375126485851,
					2.1278569566654824
				],
				[
					-9.407367597889333,
					2.1278569566654824
				],
				[
					-9.519360069292816,
					2.1278569566654824
				],
				[
					-9.519360069292816,
					2.1278569566654824
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 146,
			"versionNonce": 774833673,
			"isDeleted": false,
			"id": "i3pHyzt1",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1915.7696097241892,
			"y": 1174.531629984226,
			"strokeColor": "#ffec99",
			"backgroundColor": "#ffec99",
			"width": 25.699981689453125,
			"height": 25,
			"seed": 1325191719,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "VqCKDkXtRH1CJHIRJDwrK",
					"type": "arrow"
				}
			],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lin",
			"rawText": "Lin",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lin",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "freedraw",
			"version": 61,
			"versionNonce": 1421015815,
			"isDeleted": false,
			"id": "AzdlIxk7kA4havvpE8dXT",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2038.943038088155,
			"y": 1292.2864134300776,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.6587275045662864,
			"height": 7.740048178653751,
			"seed": 682150119,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.1646818761415716
				],
				[
					0,
					0.4940456284247148
				],
				[
					0.1646818761415716,
					0.9880912568494296
				],
				[
					0.3293637522831432,
					1.646818761415716
				],
				[
					0.3293637522831432,
					2.470228142123574
				],
				[
					0.4940456284247148,
					2.964273770548175
				],
				[
					0.4940456284247148,
					3.6230012751144614
				],
				[
					0.4940456284247148,
					4.117046903539176
				],
				[
					0.4940456284247148,
					4.446410655822319
				],
				[
					0.4940456284247148,
					4.7757744081054625
				],
				[
					0.4940456284247148,
					5.105138160388606
				],
				[
					0.4940456284247148,
					5.434501912671749
				],
				[
					0.4940456284247148,
					5.928547541096464
				],
				[
					0.4940456284247148,
					6.257911293379607
				],
				[
					0.4940456284247148,
					6.58727504566275
				],
				[
					0.4940456284247148,
					6.916638797945893
				],
				[
					0.4940456284247148,
					7.246002550229036
				],
				[
					0.4940456284247148,
					7.410684426370608
				],
				[
					0.4940456284247148,
					7.57536630251218
				],
				[
					0.4940456284247148,
					7.740048178653751
				],
				[
					0.6587275045662864,
					7.740048178653751
				],
				[
					0.6587275045662864,
					7.740048178653751
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "arrow",
			"version": 499,
			"versionNonce": 1079205097,
			"isDeleted": false,
			"id": "A6_1z-l02-zxryNTN0Zvk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2045.8043448170401,
			"y": 1328.3553299889495,
			"strokeColor": "#1971c2",
			"backgroundColor": "#a5d8ff",
			"width": 146.63005459247734,
			"height": 131.63916141143812,
			"seed": 469433127,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989893,
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
					146.63005459247734,
					-131.63916141143812
				]
			]
		},
		{
			"type": "freedraw",
			"version": 61,
			"versionNonce": 650904103,
			"isDeleted": false,
			"id": "X8EujP6zHT5nbduOtnOwB",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2047.4818823692053,
			"y": 1273.5838297467312,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 38.8377912993966,
			"height": 17.00925166396928,
			"seed": 559873607,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.850462583198464,
					0
				],
				[
					1.9844126941297873,
					0
				],
				[
					3.4018503327939698,
					0
				],
				[
					4.535800443725179,
					0
				],
				[
					5.953238082389248,
					0
				],
				[
					7.370675721053317,
					0
				],
				[
					8.221138304251895,
					0
				],
				[
					9.071600887450245,
					0.28348752773285923
				],
				[
					9.922063470648823,
					0.5669750554657185
				],
				[
					11.056013581580032,
					0.850462583198464
				],
				[
					12.189963692511242,
					1.1339501109313233
				],
				[
					12.75693874797696,
					1.4174376386640688
				],
				[
					14.174376386641029,
					1.700925166396928
				],
				[
					15.875301553037957,
					1.9844126941297873
				],
				[
					17.292739191702026,
					2.2679002218626465
				],
				[
					18.710176830366322,
					3.118362805060997
				],
				[
					19.84412694129753,
					3.401850332793856
				],
				[
					20.694589524495882,
					3.6853378605267153
				],
				[
					21.54505210769446,
					4.25231291599232
				],
				[
					22.112027163160178,
					4.535800443725179
				],
				[
					23.245977274091388,
					5.386263026923643
				],
				[
					24.096439857289738,
					5.953238082389248
				],
				[
					24.663414912755456,
					6.520213137854853
				],
				[
					25.513877495954034,
					6.803700665587712
				],
				[
					26.364340079152385,
					7.654163248786176
				],
				[
					27.214802662350962,
					8.221138304251781
				],
				[
					28.065265245549313,
					8.7881133597175
				],
				[
					29.19921535648075,
					9.355088415183104
				],
				[
					30.0496779396791,
					10.205550998381568
				],
				[
					30.90014052287745,
					10.772526053847287
				],
				[
					31.46711557834317,
					11.339501109312891
				],
				[
					32.317578161541746,
					11.906476164778496
				],
				[
					33.1680407447401,
					12.189963692511355
				],
				[
					34.018503327938674,
					13.04042627570982
				],
				[
					34.585478383404165,
					13.323913803442565
				],
				[
					35.152453438869884,
					13.607401331175424
				],
				[
					35.7194284943356,
					14.174376386641143
				],
				[
					36.00291602206846,
					14.457863914373888
				],
				[
					36.85337860526681,
					15.024838969839607
				],
				[
					36.85337860526681,
					15.308326497572352
				],
				[
					37.13686613299967,
					15.308326497572352
				],
				[
					37.42035366073253,
					15.591814025305212
				],
				[
					37.70384118846516,
					15.591814025305212
				],
				[
					37.98732871619802,
					16.158789080770816
				],
				[
					38.27081624393088,
					16.158789080770816
				],
				[
					38.27081624393088,
					16.442276608503676
				],
				[
					38.55430377166374,
					16.442276608503676
				],
				[
					38.8377912993966,
					17.00925166396928
				],
				[
					38.8377912993966,
					17.00925166396928
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 262,
			"versionNonce": 2106185673,
			"isDeleted": false,
			"id": "0EYCt-JS9RnwVCNcKzKVF",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2060.857342340388,
			"y": 1278.9236729942363,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 11.871201968765149,
			"height": 18.142780367358,
			"seed": 1570086247,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.33597741421033334,
					0.22398494280696468
				],
				[
					0.783947299824149,
					0.33597741421033334
				],
				[
					1.4559021282448157,
					0.559962357017298
				],
				[
					1.9038720138586314,
					0.783947299824149
				],
				[
					2.4638343708758157,
					1.1199247140344823
				],
				[
					2.799811785086149,
					1.567894599648298
				],
				[
					3.1357891992964824,
					1.791879542455149
				],
				[
					3.6957515563136667,
					2.2398494280689647
				],
				[
					4.031728970524,
					2.6878193136826667
				],
				[
					4.255713913330965,
					3.2477816706999647
				],
				[
					4.479698856137816,
					3.6957515563136667
				],
				[
					4.703683798944667,
					4.143721441927482
				],
				[
					4.927668741751631,
					4.591691327541298
				],
				[
					5.039661213155,
					4.927668741751518
				],
				[
					5.263646155961965,
					5.599623570172184
				],
				[
					5.375638627365333,
					6.047593455786
				],
				[
					5.487631098768816,
					6.383570869996333
				],
				[
					5.599623570172298,
					6.831540755610149
				],
				[
					5.823608512979149,
					7.391503112627333
				],
				[
					5.823608512979149,
					7.839472998241149
				],
				[
					5.935600984382631,
					8.287442883854851
				],
				[
					6.047593455786,
					9.183382655082482
				],
				[
					6.047593455786,
					9.743345012099667
				],
				[
					6.047593455786,
					10.191314897713482
				],
				[
					6.159585927189482,
					10.751277254730667
				],
				[
					6.159585927189482,
					11.199247140344482
				],
				[
					6.159585927189482,
					11.647217025958184
				],
				[
					6.159585927189482,
					12.431164325782333
				],
				[
					6.159585927189482,
					12.991126682799518
				],
				[
					6.159585927189482,
					13.327104097009851
				],
				[
					6.047593455786,
					13.775073982623667
				],
				[
					5.935600984382631,
					14.223043868237482
				],
				[
					5.711616041575667,
					14.89499869665815
				],
				[
					5.151653684558482,
					15.454961053675333
				],
				[
					4.927668741751631,
					15.90293093928915
				],
				[
					4.703683798944667,
					16.574885767709816
				],
				[
					4.591691327541298,
					17.022855653323518
				],
				[
					4.367706384734333,
					17.35883306753385
				],
				[
					4.255713913330965,
					17.694810481744184
				],
				[
					4.031728970524,
					17.806802953147667
				],
				[
					3.583759084910298,
					18.030787895954518
				],
				[
					3.2477816706999647,
					18.142780367358
				],
				[
					2.799811785086149,
					18.142780367358
				],
				[
					2.3518418994723334,
					18.142780367358
				],
				[
					1.9038720138586314,
					18.142780367358
				],
				[
					1.3439096568413333,
					18.142780367358
				],
				[
					0.559962357017298,
					18.142780367358
				],
				[
					0,
					18.030787895954518
				],
				[
					-0.6719548284206667,
					17.806802953147667
				],
				[
					-1.1199247140343687,
					17.694810481744184
				],
				[
					-1.6798870710516667,
					17.35883306753385
				],
				[
					-2.015864485262,
					17.134848124727
				],
				[
					-2.463834370875702,
					16.798870710516667
				],
				[
					-3.1357891992963687,
					16.462893296306333
				],
				[
					-3.5837590849101844,
					16.126915882096
				],
				[
					-4.031728970524,
					15.566953525078816
				],
				[
					-4.255713913330851,
					15.454961053675333
				],
				[
					-4.479698856137702,
					15.118983639465
				],
				[
					-4.815676270348035,
					14.671013753851184
				],
				[
					-5.039661213155,
					14.335036339640851
				],
				[
					-5.375638627365333,
					13.88706645402715
				],
				[
					-5.599623570172184,
					12.767141739992667
				],
				[
					-5.711616041575667,
					11.983194440168518
				],
				[
					-5.711616041575667,
					11.087254668941
				],
				[
					-5.711616041575667,
					10.527292311923816
				],
				[
					-5.711616041575667,
					9.631352540696184
				],
				[
					-5.711616041575667,
					8.847405240872149
				],
				[
					-5.711616041575667,
					7.839472998241149
				],
				[
					-5.711616041575667,
					7.167518169820482
				],
				[
					-5.711616041575667,
					6.607555812803298
				],
				[
					-5.711616041575667,
					5.935600984382631
				],
				[
					-5.599623570172184,
					5.263646155961965
				],
				[
					-5.599623570172184,
					4.703683798944667
				],
				[
					-5.487631098768702,
					3.9197364991206314
				],
				[
					-5.263646155961851,
					3.2477816706999647
				],
				[
					-5.151653684558369,
					2.9118042564896314
				],
				[
					-5.039661213155,
					2.3518418994723334
				],
				[
					-4.815676270348035,
					1.9038720138586314
				],
				[
					-4.591691327541184,
					1.4559021282448157
				],
				[
					-4.367706384734333,
					1.3439096568413333
				],
				[
					-4.143721441927369,
					1.007932242631
				],
				[
					-4.031728970524,
					0.783947299824149
				],
				[
					-3.9197364991205177,
					0.559962357017298
				],
				[
					-3.6957515563136667,
					0.4479698856138157
				],
				[
					-3.3597741421033334,
					0.4479698856138157
				],
				[
					-3.023796727893,
					0.4479698856138157
				],
				[
					-2.6878193136826667,
					0.4479698856138157
				],
				[
					-2.463834370875702,
					0.33597741421033334
				],
				[
					-2.3518418994723334,
					0.22398494280696468
				],
				[
					-2.239849428068851,
					0.22398494280696468
				],
				[
					-2.1278569566653687,
					0.11199247140348234
				],
				[
					-2.015864485262,
					0.11199247140348234
				],
				[
					-1.9038720138585177,
					0.11199247140348234
				],
				[
					-1.7918795424550353,
					0.11199247140348234
				],
				[
					-1.6798870710516667,
					0.11199247140348234
				],
				[
					-1.5678945996481843,
					0.11199247140348234
				],
				[
					-1.5678945996481843,
					0.11199247140348234
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 166,
			"versionNonce": 1517757767,
			"isDeleted": false,
			"id": "Gei9IoAThtafFeLMfopjY",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2056.3776434842503,
			"y": 1286.7631459924778,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 334190727,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
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
			"version": 166,
			"versionNonce": 133035689,
			"isDeleted": false,
			"id": "2ldSBvbLp2RPMSONV-L93",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2065.337041196526,
			"y": 1285.1952513928295,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.0001,
			"height": 0.0001,
			"seed": 1780264871,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
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
			"version": 200,
			"versionNonce": 789636199,
			"isDeleted": false,
			"id": "ZizZnrVo61-JHA1lDvkSr",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2065.337041196526,
			"y": 1285.1952513928295,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 9.519360069292816,
			"height": 2.1278569566654824,
			"seed": 441852615,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.11199247140348234,
					0.11199247140348234
				],
				[
					-0.223984942806851,
					0.11199247140348234
				],
				[
					-0.33597741421033334,
					0.22398494280696468
				],
				[
					-0.6719548284206667,
					0.335977414210447
				],
				[
					-1.007932242631,
					0.4479698856138157
				],
				[
					-1.3439096568413333,
					0.559962357017298
				],
				[
					-2.1278569566654824,
					0.783947299824149
				],
				[
					-2.4638343708758157,
					0.783947299824149
				],
				[
					-2.9118042564895177,
					0.783947299824149
				],
				[
					-3.3597741421033334,
					0.783947299824149
				],
				[
					-3.6957515563136667,
					0.8959397712276314
				],
				[
					-4.031728970524,
					1.1199247140344823
				],
				[
					-4.479698856137816,
					1.2319171854379647
				],
				[
					-4.815676270348149,
					1.3439096568413333
				],
				[
					-5.039661213155,
					1.4559021282448157
				],
				[
					-5.375638627365333,
					1.567894599648298
				],
				[
					-5.599623570172184,
					1.567894599648298
				],
				[
					-5.823608512979149,
					1.567894599648298
				],
				[
					-5.935600984382518,
					1.6798870710516667
				],
				[
					-6.159585927189482,
					1.6798870710516667
				],
				[
					-6.271578398592851,
					1.791879542455149
				],
				[
					-6.607555812803184,
					1.9038720138586314
				],
				[
					-6.831540755610149,
					1.9038720138586314
				],
				[
					-7.055525698417,
					1.9038720138586314
				],
				[
					-7.391503112627333,
					1.9038720138586314
				],
				[
					-7.615488055434184,
					2.015864485262
				],
				[
					-7.839472998241149,
					2.015864485262
				],
				[
					-8.175450412451482,
					2.1278569566654824
				],
				[
					-8.511427826661816,
					2.1278569566654824
				],
				[
					-8.735412769468667,
					2.1278569566654824
				],
				[
					-9.071390183679,
					2.1278569566654824
				],
				[
					-9.295375126485851,
					2.1278569566654824
				],
				[
					-9.407367597889333,
					2.1278569566654824
				],
				[
					-9.519360069292816,
					2.1278569566654824
				],
				[
					-9.519360069292816,
					2.1278569566654824
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 86,
			"versionNonce": 841693577,
			"isDeleted": false,
			"id": "kPoPhQLifYsuLfnu1_Bd0",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2070.9099140411076,
			"y": 1290.5536162602511,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.6587275045662864,
			"height": 7.740048178653751,
			"seed": 1697919463,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.1646818761415716
				],
				[
					0,
					0.4940456284247148
				],
				[
					0.1646818761415716,
					0.9880912568494296
				],
				[
					0.3293637522831432,
					1.646818761415716
				],
				[
					0.3293637522831432,
					2.470228142123574
				],
				[
					0.4940456284247148,
					2.964273770548175
				],
				[
					0.4940456284247148,
					3.6230012751144614
				],
				[
					0.4940456284247148,
					4.117046903539176
				],
				[
					0.4940456284247148,
					4.446410655822319
				],
				[
					0.4940456284247148,
					4.7757744081054625
				],
				[
					0.4940456284247148,
					5.105138160388606
				],
				[
					0.4940456284247148,
					5.434501912671749
				],
				[
					0.4940456284247148,
					5.928547541096464
				],
				[
					0.4940456284247148,
					6.257911293379607
				],
				[
					0.4940456284247148,
					6.58727504566275
				],
				[
					0.4940456284247148,
					6.916638797945893
				],
				[
					0.4940456284247148,
					7.246002550229036
				],
				[
					0.4940456284247148,
					7.410684426370608
				],
				[
					0.4940456284247148,
					7.57536630251218
				],
				[
					0.4940456284247148,
					7.740048178653751
				],
				[
					0.6587275045662864,
					7.740048178653751
				],
				[
					0.6587275045662864,
					7.740048178653751
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 48,
			"versionNonce": 1147518855,
			"isDeleted": false,
			"id": "chifP23tYCiPHwd1LQNOw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2119.1444190970615,
			"y": 1264.458267812507,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 5.773454078951545,
			"height": 13.196466466175025,
			"seed": 1136876807,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.16495583082712528
				],
				[
					0.1649558308270116,
					0.16495583082712528
				],
				[
					0.1649558308270116,
					0.32991166165436425
				],
				[
					0.32991166165425057,
					0.32991166165436425
				],
				[
					0.49486749248148953,
					0.49486749248148953
				],
				[
					0.6598233233087285,
					0.6598233233087285
				],
				[
					1.154690815790218,
					0.8247791541359675
				],
				[
					1.4846024774444686,
					1.1546908157903317
				],
				[
					1.6495583082717076,
					1.319646646617457
				],
				[
					1.8145141390989465,
					1.8145141390990602
				],
				[
					1.9794699699261855,
					1.9794699699261855
				],
				[
					2.309381631580436,
					2.4743374624077887
				],
				[
					2.804249124062153,
					2.969204954889392
				],
				[
					3.1341607857164036,
					3.6290282781981205
				],
				[
					3.4640724473708815,
					4.12389577067961
				],
				[
					3.793984109025132,
					4.9486749248155775
				],
				[
					4.12389577067961,
					5.608498248124306
				],
				[
					4.288851601506849,
					6.103365740605909
				],
				[
					4.6187632631610995,
					6.763189063914638
				],
				[
					4.7837190939883385,
					7.258056556396241
				],
				[
					4.9486749248155775,
					7.917879879704969
				],
				[
					5.113630755642589,
					8.577703203013698
				],
				[
					5.278586586469828,
					9.237526526322426
				],
				[
					5.278586586469828,
					9.73239401880403
				],
				[
					5.443542417297067,
					10.062305680458394
				],
				[
					5.443542417297067,
					10.392217342112758
				],
				[
					5.443542417297067,
					10.722129003767122
				],
				[
					5.608498248124306,
					11.216996496248726
				],
				[
					5.608498248124306,
					11.54690815790309
				],
				[
					5.773454078951545,
					11.711863988730329
				],
				[
					5.773454078951545,
					12.041775650384693
				],
				[
					5.773454078951545,
					12.371687312039057
				],
				[
					5.773454078951545,
					12.536643142866296
				],
				[
					5.773454078951545,
					12.701598973693422
				],
				[
					5.773454078951545,
					12.866554804520547
				],
				[
					5.773454078951545,
					13.031510635347786
				],
				[
					5.773454078951545,
					13.196466466175025
				],
				[
					5.773454078951545,
					13.196466466175025
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 84,
			"versionNonce": 1836916841,
			"isDeleted": false,
			"id": "OLaQHIUQv84YcSf1jdKz5",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2135.574555029946,
			"y": 1252.7532041345758,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 15.705074464796553,
			"height": 12.132356103136658,
			"seed": 1501570087,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.07443163253446983,
					0
				],
				[
					0.4465897952075011,
					-0.07443163253458351
				],
				[
					0.8931795904150022,
					-0.07443163253458351
				],
				[
					1.414201018156973,
					-0.07443163253458351
				],
				[
					1.8607908133644742,
					-0.07443163253458351
				],
				[
					2.3073806085719752,
					-0.07443163253458351
				],
				[
					2.828402036313946,
					0
				],
				[
					3.12612856645228,
					0.14886326506916703
				],
				[
					3.6471499941944785,
					0.4465897952075011
				],
				[
					3.9448765243328126,
					0.7443163253457215
				],
				[
					4.317034687005616,
					1.1909061205532225
				],
				[
					4.6147612171439505,
					1.7863591808298906
				],
				[
					4.838056114747815,
					2.158517343502808
				],
				[
					4.986919379816982,
					2.6051071387103093
				],
				[
					5.135782644886149,
					2.977265301383227
				],
				[
					5.284645909955316,
					3.274991831521561
				],
				[
					5.284645909955316,
					3.423855096590728
				],
				[
					5.284645909955316,
					3.7960132592636455
				],
				[
					5.284645909955316,
					4.242603054471033
				],
				[
					5.284645909955316,
					4.7636244822131175
				],
				[
					5.284645909955316,
					5.210214277420619
				],
				[
					5.284645909955316,
					5.731235705162703
				],
				[
					5.210214277420619,
					6.177825500370204
				],
				[
					5.135782644886149,
					6.401120397973955
				],
				[
					4.986919379816982,
					6.773278560646759
				],
				[
					4.9124877472822845,
					7.071005090785093
				],
				[
					4.7636244822131175,
					7.294299988388843
				],
				[
					4.7636244822131175,
					7.517594885992594
				],
				[
					4.689192849678648,
					7.740889783596344
				],
				[
					4.689192849678648,
					7.964184681200095
				],
				[
					4.6147612171439505,
					8.113047946269262
				],
				[
					4.540329584609481,
					8.261911211338429
				],
				[
					4.540329584609481,
					8.48520610894218
				],
				[
					4.4658979520747835,
					8.634069374011347
				],
				[
					4.391466319540314,
					8.857364271615097
				],
				[
					4.391466319540314,
					9.006227536684264
				],
				[
					4.391466319540314,
					9.080659169218848
				],
				[
					4.317034687005616,
					9.155090801753431
				],
				[
					4.317034687005616,
					9.080659169218848
				],
				[
					4.317034687005616,
					8.857364271615097
				],
				[
					4.317034687005616,
					8.559637741476763
				],
				[
					4.317034687005616,
					8.113047946269262
				],
				[
					4.317034687005616,
					7.517594885992594
				],
				[
					4.317034687005616,
					6.698846928112289
				],
				[
					4.391466319540314,
					5.65680407262812
				],
				[
					4.540329584609481,
					4.689192849678534
				],
				[
					4.689192849678648,
					3.7960132592636455
				],
				[
					4.7636244822131175,
					3.274991831521561
				],
				[
					4.986919379816982,
					2.530675506175726
				],
				[
					5.210214277420619,
					2.009654078433641
				],
				[
					5.433509175024483,
					1.56306428322614
				],
				[
					5.8800989702317565,
					1.116474488018639
				],
				[
					6.103393867835621,
					0.7443163253457215
				],
				[
					6.475552030508425,
					0.37215816267291757
				],
				[
					6.996573458250623,
					0
				],
				[
					7.592026518527291,
					-0.29772653013833406
				],
				[
					8.113047946269262,
					-0.6698846928112516
				],
				[
					8.857364271615097,
					-1.0420428554841692
				],
				[
					9.676112229495402,
					-1.5630642832262538
				],
				[
					10.569291819910404,
					-2.009654078433755
				],
				[
					11.23917651272177,
					-2.307380608572089
				],
				[
					11.909061205532907,
					-2.679538771244893
				],
				[
					12.430082633274878,
					-2.7539704037794763
				],
				[
					12.87667242848238,
					-2.82840203631406
				],
				[
					13.24883059115541,
					-2.9028336688486434
				],
				[
					13.546557121293745,
					-2.9028336688486434
				],
				[
					13.993146916501246,
					-2.9028336688486434
				],
				[
					14.216441814104883,
					-2.977265301383227
				],
				[
					14.514168344243217,
					-2.977265301383227
				],
				[
					14.886326506916248,
					-2.977265301383227
				],
				[
					15.258484669589052,
					-2.977265301383227
				],
				[
					15.481779567192689,
					-2.977265301383227
				],
				[
					15.630642832261856,
					-2.9028336688486434
				],
				[
					15.705074464796553,
					-2.9028336688486434
				],
				[
					15.705074464796553,
					-2.9028336688486434
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "arrow",
			"version": 233,
			"versionNonce": 213005991,
			"isDeleted": false,
			"id": "x9ki-egJKoSxCB_gdBJjB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2048.25455521547,
			"y": 1327.6227054008414,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 260.8897005941027,
			"height": 166.62210671857906,
			"seed": 2043688967,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989893,
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
					226.57298878853942,
					-145.12248004521405
				],
				[
					260.8897005941027,
					-166.62210671857906
				]
			]
		},
		{
			"id": "z68VDriPuRPAeNgY5F1Ti",
			"type": "arrow",
			"x": 2047.5341512712225,
			"y": 1327.2747911746321,
			"width": 47.767721678470025,
			"height": 217.83949683640958,
			"angle": 0,
			"strokeColor": "#f08c00",
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
			"seed": 127589321,
			"version": 301,
			"versionNonce": 2007968585,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					33.48803069421183,
					-161.34158902912827
				],
				[
					47.767721678470025,
					-217.83949683640958
				]
			],
			"lastCommittedPoint": [
				47.767721678470025,
				-217.83949683640958
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "QvQfDfWv",
			"type": "text",
			"x": 2111.8680789655086,
			"y": 1107.6689372665644,
			"width": 147.1363067626953,
			"height": 20,
			"angle": 0,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 629137895,
			"version": 79,
			"versionNonce": 2124597703,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"text": "h = normalized(v+l)",
			"rawText": "h = normalized(v+l)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "h = normalized(v+l)",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 1226627625,
			"isDeleted": false,
			"id": "wRIjbxZ9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 1911.572262387263,
			"y": 1413.8414083540542,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 317.32818603515625,
			"height": 29.842277830891923,
			"seed": 1645548521,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"fontSize": 23.87382226471354,
			"fontFamily": 1,
			"text": "Lspec = ks * cos( gamma )",
			"rawText": "Lspec = ks * cos( gamma )",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lspec = ks * cos( gamma )",
			"lineHeight": 1.25,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 154,
			"versionNonce": 122943719,
			"isDeleted": false,
			"id": "7a6dKe6L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 2229.0339722770245,
			"y": 1405.850832597274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 6.3628387451171875,
			"height": 17.0527301890811,
			"seed": 201109193,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"fontSize": 13.64218415126488,
			"fontFamily": 1,
			"text": "n",
			"rawText": "n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "n",
			"lineHeight": 1.25,
			"baseline": 12
		},
		{
			"type": "text",
			"version": 388,
			"versionNonce": 1118940425,
			"isDeleted": false,
			"id": "g7v7cCCb",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2052.6581273917923,
			"y": 1483.3832230259616,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 240.75253295898438,
			"height": 100,
			"seed": 931619881,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Angle between bisector h\nand norm \n\ndot ( n , h )\nif both r and v are normalized",
			"rawText": "Angle between bisector h\nand norm \n\ndot ( n , h )\nif both r and v are normalized",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Angle between bisector h\nand norm \n\ndot ( n , h )\nif both r and v are normalized",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"id": "WjupR7NNLF_WcNPqCmvqe",
			"type": "line",
			"x": 2165.8927763474485,
			"y": 1439.5899795462547,
			"width": 1.9044313396893813,
			"height": 38.08862679378967,
			"angle": 0,
			"strokeColor": "#f08c00",
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
			"seed": 1188535337,
			"version": 46,
			"versionNonce": 1012024327,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.9044313396893813,
					38.08862679378967
				]
			],
			"lastCommittedPoint": [
				1.9044313396893813,
				38.08862679378967
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "WA_oZXdqNG2--bqFyjWTD",
			"type": "arrow",
			"x": -672.874026476565,
			"y": 1054.346757187028,
			"width": 450.21865972886553,
			"height": 63.13029177009935,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1945791145,
			"version": 178,
			"versionNonce": 468263913,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					450.21865972886553,
					-63.13029177009935
				]
			],
			"lastCommittedPoint": [
				402.04027916747395,
				-8.306617338171009
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "CrCGB7q8PtiF5rfzFe7e0",
			"type": "arrow",
			"x": 809.0265066531326,
			"y": 1027.7655817048812,
			"width": 521.6555688371359,
			"height": 34.88779282031783,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1878824041,
			"version": 228,
			"versionNonce": 1301949223,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-521.6555688371359,
					-34.88779282031783
				]
			],
			"lastCommittedPoint": [
				-495.07439335498884,
				23.25852854687855
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "glymOs0Q-Avef36nBpM_6",
			"type": "arrow",
			"x": -1.062355622883274,
			"y": 1154.9853706894687,
			"width": 6.302986196347092,
			"height": 241.61447085997224,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 558845481,
			"version": 91,
			"versionNonce": 281984713,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-6.302986196347092,
					241.61447085997224
				]
			],
			"lastCommittedPoint": [
				-6.302986196347092,
				241.61447085997224
			],
			"startBinding": {
				"elementId": "IbIg8igJ",
				"focus": 0.049180686928914974,
				"gap": 11.772144935825736
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "JjrQfqPo",
			"type": "text",
			"x": -177.3113816890608,
			"y": 1413.5137771323941,
			"width": 331.48809814453125,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 809566601,
			"version": 46,
			"versionNonce": 932720199,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"text": "Micro-facet theory",
			"rawText": "Micro-facet theory",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 32,
			"containerId": null,
			"originalText": "Micro-facet theory",
			"lineHeight": 1.25
		},
		{
			"id": "LJF1cfND",
			"type": "text",
			"x": -385.2744388464017,
			"y": 1461.2257219177823,
			"width": 757.919189453125,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 149802729,
			"version": 234,
			"versionNonce": 1342045609,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "1-h-_bmWonEmzQtST7N9U",
					"type": "arrow"
				}
			],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"text": "Micro-facet theory suggests that on a magnified scale, surfaces are made\nout of very small micro facets that can shadow each other by blocking light\nand can occlude one another from the viewer",
			"rawText": "Micro-facet theory suggests that on a magnified scale, surfaces are made\nout of very small micro facets that can shadow each other by blocking light\nand can occlude one another from the viewer",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "Micro-facet theory suggests that on a magnified scale, surfaces are made\nout of very small micro facets that can shadow each other by blocking light\nand can occlude one another from the viewer",
			"lineHeight": 1.25
		},
		{
			"id": "1-h-_bmWonEmzQtST7N9U",
			"type": "arrow",
			"x": -13.86191147724594,
			"y": 1551.0578788150287,
			"width": 0,
			"height": 90.43398145076299,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1884362823,
			"version": 35,
			"versionNonce": 891866471,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					90.43398145076299
				]
			],
			"lastCommittedPoint": [
				0,
				90.43398145076299
			],
			"startBinding": {
				"elementId": "LJF1cfND",
				"focus": 0.019915229650940197,
				"gap": 14.832156897246477
			},
			"endBinding": {
				"elementId": "xruNSttX",
				"focus": -0.0567628552520923,
				"gap": 7.288849394999033
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "xruNSttX",
			"type": "text",
			"x": -190.65667105553405,
			"y": 1648.7807096607908,
			"width": 374.86810302734375,
			"height": 45,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 145177833,
			"version": 52,
			"versionNonce": 681730185,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "1-h-_bmWonEmzQtST7N9U",
					"type": "arrow"
				}
			],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"text": "Cook-Torrance model!",
			"rawText": "Cook-Torrance model!",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 32,
			"containerId": null,
			"originalText": "Cook-Torrance model!",
			"lineHeight": 1.25
		},
		{
			"id": "Pq7HN62F",
			"type": "text",
			"x": -325.3790165270734,
			"y": 1708.4204554494283,
			"width": 640.55859375,
			"height": 35,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 815166793,
			"version": 107,
			"versionNonce": 1905821831,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"text": "Lout = Lin * (kd / PI + fs) *  max(0,dot(n,l))",
			"rawText": "Lout = Lin * (kd / PI + fs) *  max(0,dot(n,l))",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Lout = Lin * (kd / PI + fs) *  max(0,dot(n,l))",
			"lineHeight": 1.25
		},
		{
			"id": "6kU_w0TPgDpHi6Iuj81NP",
			"type": "line",
			"x": -203.01260155407135,
			"y": 1744.4248505849032,
			"width": 0.9989087210281014,
			"height": 76.91597151916335,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 233649063,
			"version": 172,
			"versionNonce": 2021091177,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.9989087210281014,
					76.91597151916335
				]
			],
			"lastCommittedPoint": [
				-0.9989087210281014,
				76.91597151916335
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "hwxR8geE",
			"type": "text",
			"x": -236.37964382002133,
			"y": 1831.3408221040665,
			"width": 64.73626708984375,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2058612967,
			"version": 147,
			"versionNonce": 2057559975,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"text": "light\ninput",
			"rawText": "light\ninput",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "light\ninput",
			"lineHeight": 1.25
		},
		{
			"type": "line",
			"version": 184,
			"versionNonce": 1506316873,
			"isDeleted": false,
			"id": "W24bhobSYKeMnyNlV3T6N",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -302.2495161078508,
			"y": 1749.355838978774,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.9989087210281014,
			"height": 76.91597151916335,
			"seed": 394384327,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-0.9989087210281014,
					76.91597151916335
				]
			]
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 1920422599,
			"isDeleted": false,
			"id": "qJypDx4Z",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -361.97049698736265,
			"y": 1840.8155240741405,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 92.764404296875,
			"height": 70,
			"seed": 418803399,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "light\noutput",
			"rawText": "light\noutput",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "light\noutput",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"id": "BGGEB9wZbm0drpPvwk458",
			"type": "line",
			"x": -100.33293994220423,
			"y": 1743.2398307892863,
			"width": 0.9989087210281014,
			"height": 75.91706279813525,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1758469353,
			"version": 171,
			"versionNonce": 292643113,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.9989087210281014,
					75.91706279813525
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "Spk9c1Pg",
			"type": "text",
			"x": -148.73952673777933,
			"y": 1836.1492546346183,
			"width": 104.804443359375,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1159785607,
			"version": 158,
			"versionNonce": 28271079,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989893,
			"link": null,
			"locked": false,
			"text": "surface\ncolor",
			"rawText": "surface\ncolor",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "surface\ncolor",
			"lineHeight": 1.25
		},
		{
			"id": "OcqyjNdst2Slz1iHINWov",
			"type": "line",
			"x": 214.4752617376747,
			"y": 1753.959100181964,
			"width": 0.9989087210281014,
			"height": 81.91051512430408,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 613262985,
			"version": 186,
			"versionNonce": 1021137929,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0.9989087210281014,
					81.91051512430408
				]
			],
			"lastCommittedPoint": [
				0.9989087210281014,
				96.89414593972538
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "t25okWaH",
			"type": "text",
			"x": 189.4927222012252,
			"y": 1843.7309711850594,
			"width": 292.3492431640625,
			"height": 70,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 963989993,
			"version": 96,
			"versionNonce": 156798215,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"text": "Removal of negative \nlight computation",
			"rawText": "Removal of negative \nlight computation",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 60,
			"containerId": null,
			"originalText": "Removal of negative \nlight computation",
			"lineHeight": 1.25
		},
		{
			"id": "XuJd2Yf2nQOXMqZQAoZA9",
			"type": "line",
			"x": 48.17693514409507,
			"y": 1756.5418059048461,
			"width": 5.709243017721519,
			"height": 265.47980032404416,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 146252295,
			"version": 94,
			"versionNonce": 1074260713,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					5.709243017721519,
					265.47980032404416
				]
			],
			"lastCommittedPoint": [
				5.709243017721519,
				265.47980032404416
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"id": "fMW5SPeh",
			"type": "text",
			"x": -279.3099273709714,
			"y": 2040.4250237834176,
			"width": 660.2403564453125,
			"height": 135,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1357575785,
			"version": 131,
			"versionNonce": 351228967,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"text": " D F G\nfs = ___________________\n4 * |dot(n,l)| * |dot(n,v)|",
			"rawText": " D F G\nfs = ___________________\n4 * |dot(n,l)| * |dot(n,v)|",
			"fontSize": 36,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 122,
			"containerId": null,
			"originalText": " D F G\nfs = ___________________\n4 * |dot(n,l)| * |dot(n,v)|",
			"lineHeight": 1.25
		},
		{
			"id": "xNPNLcNHvZ_pej2z2vSz-",
			"type": "arrow",
			"x": 123.32492917315619,
			"y": 2065.8704889573883,
			"width": 487.85693041335526,
			"height": 154.90196078431427,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1001491849,
			"version": 225,
			"versionNonce": 1937548745,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					332.22222222222206,
					-22.222222222222626
				],
				[
					487.85693041335526,
					132.67973856209164
				]
			],
			"lastCommittedPoint": [
				438.8888888888888,
				164.44444444444434
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "7aj0DzF6i4quNJTXKlOi4",
			"type": "arrow",
			"x": -6.6750708268438075,
			"y": 2064.759377846277,
			"width": 406.8441492735577,
			"height": 230.55144739207208,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 92835689,
			"version": 184,
			"versionNonce": 207632199,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-343.33333333333326,
					-23.333333333333485
				],
				[
					-406.8441492735577,
					207.2181140587386
				]
			],
			"lastCommittedPoint": [
				-404.4444444444441,
				194.44444444444434
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "xTYrDY4S",
				"focus": -0.010802978131787952,
				"gap": 11.83006535947743
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "dpLhNHZBbuYkXfvLphgO0",
			"type": "arrow",
			"x": 43.97852394439815,
			"y": 2043.9750641207866,
			"width": 732.9411764705882,
			"height": 83.52941176470586,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 478661511,
			"version": 318,
			"versionNonce": 307692713,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-610.5882352941176,
					-83.52941176470586
				],
				[
					-732.9411764705882,
					-37.64705882352928
				]
			],
			"lastCommittedPoint": [
				-730.5882352941176,
				-96.47058823529414
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "xTYrDY4S",
			"type": "text",
			"x": -641.3258392168744,
			"y": 2283.807557264493,
			"width": 433.33953857421875,
			"height": 75,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 831101255,
			"version": 124,
			"versionNonce": 638039655,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "7aj0DzF6i4quNJTXKlOi4",
					"type": "arrow"
				}
			],
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"text": "D  is the normal distribution function (NDF)\nthat describes which fraction of\nfacets are aligned with the half vector",
			"rawText": "D  is the normal distribution function (NDF)\nthat describes which fraction of\nfacets are aligned with the half vector",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "D  is the normal distribution function (NDF)\nthat describes which fraction of\nfacets are aligned with the half vector",
			"lineHeight": 1.25
		},
		{
			"id": "zmGJD72v",
			"type": "text",
			"x": 244.81354153914788,
			"y": 2215.3263600327323,
			"width": 759.3992919921875,
			"height": 250,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1746058057,
			"version": 372,
			"versionNonce": 1749190537,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"text": "G  is the fraction of microfacets\nnot occluded or shadowed by other facets\n\nSince Occlusion and shadowing are two different cases\nwe usually preform this function twice over occlusion and over shadowing and\nmultiply both\nOcclusion is between the viewer and the normals\nShadowing is between the light and the normals\n\nThis function is heavily dependent on the distribution D",
			"rawText": "G  is the fraction of microfacets\nnot occluded or shadowed by other facets\n\nSince Occlusion and shadowing are two different cases\nwe usually preform this function twice over occlusion and over shadowing and\nmultiply both\nOcclusion is between the viewer and the normals\nShadowing is between the light and the normals\n\nThis function is heavily dependent on the distribution D",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 243,
			"containerId": null,
			"originalText": "G  is the fraction of microfacets\nnot occluded or shadowed by other facets\n\nSince Occlusion and shadowing are two different cases\nwe usually preform this function twice over occlusion and over shadowing and\nmultiply both\nOcclusion is between the viewer and the normals\nShadowing is between the light and the normals\n\nThis function is heavily dependent on the distribution D",
			"lineHeight": 1.25
		},
		{
			"id": "xPgAZFpQ",
			"type": "text",
			"x": -1129.2412147638067,
			"y": 2022.5284332548952,
			"width": 511.8194580078125,
			"height": 100,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1745445449,
			"version": 241,
			"versionNonce": 414339463,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"text": "F is the Fersnel effect where for unpolarized\nlight and dielectric materials we often see stronger\nreflection the larger the angle is the viewer is at\neven if the material is not glossy",
			"rawText": "F is the Fersnel effect where for unpolarized\nlight and dielectric materials we often see stronger\nreflection the larger the angle is the viewer is at\neven if the material is not glossy",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "F is the Fersnel effect where for unpolarized\nlight and dielectric materials we often see stronger\nreflection the larger the angle is the viewer is at\neven if the material is not glossy",
			"lineHeight": 1.25
		},
		{
			"id": "ogpdognUhXxdj8Uvs5bm-",
			"type": "image",
			"x": -1108.8799442898858,
			"y": 2144.48116802247,
			"width": 478.10982322966504,
			"height": 40.63933497452153,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 417864135,
			"version": 88,
			"versionNonce": 1065004649,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7500b16ec165f59eb1ee266e9ddafa8a55990808",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "AFI2Umg7KLFvQfKwYUPSM",
			"type": "rectangle",
			"x": -1112.0146050702901,
			"y": 2141.8678317629206,
			"width": 483.7014875129862,
			"height": 46.50787291253255,
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
			"seed": 572317225,
			"version": 111,
			"versionNonce": 228362407,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "jBhYK3w4T2mt9edgccONN",
					"type": "arrow"
				}
			],
			"updated": 1702914989894,
			"link": null,
			"locked": false
		},
		{
			"id": "jBhYK3w4T2mt9edgccONN",
			"type": "arrow",
			"x": -1018.1793541757992,
			"y": 2198.4865015445052,
			"width": 64.1143142564548,
			"height": 59.93294593538167,
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
			"seed": 1882907849,
			"version": 53,
			"versionNonce": 248183113,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-6.039754241549986,
					55.28698113418932
				],
				[
					-64.1143142564548,
					59.93294593538167
				]
			],
			"lastCommittedPoint": [
				-64.1143142564548,
				59.93294593538167
			],
			"startBinding": {
				"elementId": "AFI2Umg7KLFvQfKwYUPSM",
				"focus": 0.5907359641152728,
				"gap": 10.110796869052137
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "OjfJfXNJ",
			"type": "text",
			"x": -1299.52742208124,
			"y": 2205.4554487462938,
			"width": 247.69972229003906,
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
			"seed": 240636391,
			"version": 45,
			"versionNonce": 1383259079,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"text": "F0 is the reflectance at\nnormal incidence",
			"rawText": "F0 is the reflectance at\nnormal incidence",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "F0 is the reflectance at\nnormal incidence",
			"lineHeight": 1.25
		},
		{
			"id": "jKjf9EQQ2xfl5280cepnH",
			"type": "image",
			"x": -1269.1153361524773,
			"y": 2278.048465969899,
			"width": 199.60516567102906,
			"height": 66.2623705711203,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1752308521,
			"version": 98,
			"versionNonce": 1737418793,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "853868975882718a7db6762cbb2c5ea2165208a3",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "8z5VnZzP5-zCMzUegj-Pz",
			"type": "rectangle",
			"x": -1269.4221434167591,
			"y": 2276.7845161481837,
			"width": 201.94535460654174,
			"height": 66.5184895844036,
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
			"seed": 1479493897,
			"version": 47,
			"versionNonce": 1263651559,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false
		},
		{
			"id": "oKGDbolfYfRPvtd1VPNyS",
			"type": "image",
			"x": -695.3761437428091,
			"y": 2386.1345024519674,
			"width": 540.3835085773361,
			"height": 86.17626695537854,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2025989063,
			"version": 137,
			"versionNonce": 598866697,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0af0f4ccf8fd37034a752bdfdeba7583c2992c60",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "trXhcz13omVMiJNMQHAv3",
			"type": "rectangle",
			"x": -700.8974362778619,
			"y": 2381.6411191987727,
			"width": 547.8454047276532,
			"height": 94.88825637439777,
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
			"seed": 319721415,
			"version": 120,
			"versionNonce": 616945159,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false
		},
		{
			"id": "rFx-JdhTu75RciKJoEDfP",
			"type": "image",
			"x": 398.75317101903715,
			"y": 2503.1180672407713,
			"width": 450.93603618066516,
			"height": 76.82613949744666,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1543771273,
			"version": 141,
			"versionNonce": 1404023273,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "00bd6412e85bb066897051fada072b571ef86d95",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "RUwzjeBMbJHT5jAcUoYlN",
			"type": "rectangle",
			"x": 396.8140120237912,
			"y": 2499.4957905005,
			"width": 452.7328239461177,
			"height": 79.09814855150535,
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
			"seed": 816921447,
			"version": 88,
			"versionNonce": 1170963751,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702914989894,
			"link": null,
			"locked": false
		},
		{
			"id": "MH6SoX4lSIFFNx_2o9bo5",
			"type": "line",
			"x": -592.9605070729956,
			"y": -80.13840810448676,
			"width": 934.2680335657244,
			"height": 369.9891830158653,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1515853127,
			"version": 400,
			"versionNonce": 1151711623,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702915040651,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-393.9048336290582,
					-369.9891830158653
				],
				[
					-779.1285267603057,
					-308.88165333704666
				],
				[
					-934.2680335657244,
					-251.12490048675375
				]
			],
			"lastCommittedPoint": [
				-941.1511917779997,
				-286.9878073583138
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": null
		},
		{
			"type": "text",
			"version": 620,
			"versionNonce": 1323447305,
			"isDeleted": false,
			"id": "RfcRwZyl",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1764.0347406323158,
			"y": -312.68237722923163,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 335.9996337890625,
			"height": 25,
			"seed": 548768807,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702915036054,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Gourard Shading vs Phong Shading",
			"rawText": "Gourard Shading vs Phong Shading",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gourard Shading vs Phong Shading",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 582,
			"versionNonce": 2121321193,
			"isDeleted": false,
			"id": "VeVcUUJH",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2109.9128721932566,
			"y": -247.86472592582317,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 465.6169128417969,
			"height": 100,
			"seed": 849309511,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702915036055,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Gourard shading is computed over each Vertex in the mesh\nand then further interpolated from one vertex to another\nthus leaving artefacts in the mesh that look undetailed\nand the vertices are always the shinest points\n",
			"rawText": "Gourard shading is computed over each Vertex in the mesh\nand then further interpolated from one vertex to another\nthus leaving artefacts in the mesh that look undetailed\nand the vertices are always the shinest points\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gourard shading is computed over each Vertex in the mesh\nand then further interpolated from one vertex to another\nthus leaving artefacts in the mesh that look undetailed\nand the vertices are always the shinest points\n",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "text",
			"version": 129,
			"versionNonce": 835290569,
			"isDeleted": false,
			"id": "Vfl4lRa7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1613.6144966006036,
			"y": -188.64454073538002,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 39.17216491699219,
			"height": 35,
			"seed": 799010407,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702915036055,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "V.S",
			"rawText": "V.S",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V.S",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 601,
			"versionNonce": 872932521,
			"isDeleted": false,
			"id": "TDWR32dQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1554.2469527470334,
			"y": -247.15381413255216,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 407.92083740234375,
			"height": 60,
			"seed": 847481223,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1702915036055,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Phong shading interpolates the actual normals from\nvertices to every point in the triangle and then\nthe color is calculated in them individually",
			"rawText": "Phong shading interpolates the actual normals from\nvertices to every point in the triangle and then\nthe color is calculated in them individually",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Phong shading interpolates the actual normals from\nvertices to every point in the triangle and then\nthe color is calculated in them individually",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"id": "Rl4oyqqq",
			"type": "text",
			"x": -2011.354739206089,
			"y": -172.1097026602584,
			"width": 259.0989881278556,
			"height": 49.3383024485562,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1125348297,
			"version": 83,
			"versionNonce": 1624729481,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1702915036055,
			"link": null,
			"locked": false,
			"text": "\nthis is a lot more obvious when we dont\nhave many triangles in the mesh",
			"rawText": "\nthis is a lot more obvious when we dont\nhave many triangles in the mesh",
			"fontSize": 13.156880652948324,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 43.99999999999998,
			"containerId": null,
			"originalText": "\nthis is a lot more obvious when we dont\nhave many triangles in the mesh",
			"lineHeight": 1.25
		},
		{
			"text": "Gourard shading is computed over each Vertex in the mesh\nand then further interpolated from one vertex to another\nthus leaving artefacts in the mesh that look undetailed\nand the vertices are always the shinest points\n\nthis is a lot more obvious when we dont\nhave many triangles in the mesh",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 235,
			"id": "8sG8MhcT",
			"type": "text",
			"x": -1983.854679737327,
			"y": -276.87467443076366,
			"width": 814.8314208984375,
			"height": 245,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"roundness": null,
			"seed": 74502,
			"version": 2,
			"versionNonce": 582163079,
			"updated": 1702914989894,
			"isDeleted": true,
			"groupIds": [],
			"boundElements": [],
			"link": null,
			"locked": false,
			"containerId": null,
			"originalText": "Gourard shading is computed over each Vertex in the mesh\nand then further interpolated from one vertex to another\nthus leaving artefacts in the mesh that look undetailed\nand the vertices are always the shinest points\n\nthis is a lot more obvious when we dont\nhave many triangles in the mesh",
			"rawText": "Gourard shading is computed over each Vertex in the mesh\nand then further interpolated from one vertex to another\nthus leaving artefacts in the mesh that look undetailed\nand the vertices are always the shinest points\n\nthis is a lot more obvious when we dont\nhave many triangles in the mesh",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#e3fafc",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 2,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1630.1731366484687,
		"scrollY": -345.8250493746332,
		"zoom": {
			"value": 0.3700573226408062
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#82E9F2FF",
			"Regular": "#C3F4F9FF"
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