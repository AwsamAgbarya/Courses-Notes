---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - calculus
---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
What are partial derivatives? ^tPpN0yZA

a derivative in the univariate situation is defined as follows ^m7HIMtM7

for each infinitely small nudge in x
what nudge happens to f ^MnMpj1Op

We can interpret it the same way for multivariate function!
(except maybe harder to visualize)  ^aslAVMAi

x ^YhgpLGGK

y ^Tfbih02i

f(x,y) ^vbUUHYbD

df ^SJ1q5B8Y

For every point in our 2d input space, what change is caused
in the output of the function
except
there are multiple ways to move in out input space thus we
need to evaluate it for every input dimension seperately
by treating all other dimensions as constants
WHICH IS WHY ITS CALLED PARTIAL!! ^4bpVsAWm

dy ^xpar5z5A

dx ^EkI6CasF

Second Partial derivatives? ^Pzft0FCg

as with normal derivatives, the actual derivative is a function and we
can extract another derivative out of it, this also applies to multivariate calculus
you have to keep in mind that we are deriving for multiple inputs

meaning at each stage we also have to derive for each input leading to
a tree structure of sorts ^Ty18TpWg

notice how deriving for x then y and deriving for y then x 
grants us the same results!
this is not always true but its quite common!
according to schwartz's theorem where the function has to meet
the criterion that its second partial derivative at that certain point
is continuous results in this equality ^QQKLxed2

Gradient ^S0A5yNXD

The gradient of a function is a vector valued partial derivative of a function
it is used to package all the information we get about the derivative ^fLsQRuTu

f =  ^qoNgOGZb

df ^xSWpQYaR

df ^4igCm5ra

dx ^PeGfxbWq

dy ^ONBc926R

The gradient of a point is a vector describing the direction of steepest ascent on that function
and its magnitude is the steepness measure ^Oj3eaTaq

Directional derivative ^0FrxbtTo

Directional derivative of vector v is the change of output thats resulted in
walking infinitely small steps in the direction of vector v ^HkqtKVf7

f =  ^BuYlVFy2

df ^OrnZKYet

df ^cwvZhjHN

dx ^fUANefa4

dy ^vADG5iul

v ^9bjao0H2

v = ^UgcG6uoO

a
b ^XauZSyZ7

a ^XklJLaeA

+ b ^0WRF3RV1

V ^gEak0ZKP

Say we want to find the highest directional gradient of vector v
this is intuitively the steepest ascent since it gives maximal change in the
function such that its in the direction of v (Assuming V is unit length)



As we know from the dot product, the highest values come when the two vectors
actually align thus the maximal value is in the direction of the gradient of the function ^U7pdCNUe

What is the Jacobian matrix? ^ZjhwEScA

The Jacobian matrix is a matrix that contains information about the
partial derivatives of a certain function to describe the infinitely small
changes that happen when we preform said function as a transformation. ^IjaBrRbl

F(x,y) =  ^uKE9MEru

g1(x,y) ^mRU2RE1X

g2(x,y) ^g9Fgh0CB

dx ^wIqODSJv

dx ^eLvjtOMB

dg1 ^9AeRtsBu

dg1 ^xMxgJzRP

dy ^3g6kNMHX

dy ^ci7X5aJq

dg2 ^H620KGJU

dg2 ^lJwngih5

What is the multi-variable chain rule? ^ps5bt5Lu

Assume that we have a function f that consists of two
other functions y and x, both of those functions depend on t
how do we find the derivative of this function w.t.r t? ^DUpwT0RX

t ^Gl89I5n5

x ^0LiWpUeW

y ^CLRkgu08

f ^VoiYw4N0

for every change of t
how much does x get affected
how much does y get affected ^HRh3b0nE

for every change of x,y
how much does f get affected ^NfVnVtYY

What is the Hessian Matrix? ^P94ocOl9

The hessian matrix is a matrix that packages all information gotten from
the second partial derivatives, its diagonal consists of partial derivatives consisting
of only one variables while the others serve as a combination ^rVvRRL0U

If we look at this matrix as a linear transformation we can see that its basis are how
the function curves in each dimension corresponding to each other dimension
the eigenvectors of this matrix are the actual principal axes and the eigen vectors are their degree of
curvature ^kB70gmGK


# Embedded files
062f747b872f430825ccbe1e32cef94004f31131: $$\color{white}\max_{\|v\|=1} <\nabla f * v>$$
61d1bb35d69958aa1b0505900663c43a69fbcc50: [[Pasted Image 20240102172056_915.png]]
7fcaedad630b026b08975630186fe4348740cc2e: [[Pasted Image 20240102172141_934.png]]
24771122d5db5d792e239064e80cbf42183cdd75: [[Pasted Image 20240102173508_069.png]]
5b85ab416271304988788bd725ab5e287a88919e: [[Pasted Image 20240102182229_610.png]]
0b41ddd8289553c34a713efb54fd45388e681c99: [[Pasted Image 20240102182632_677.png]]
f3c611841fc2d9db0d6c94834fb6c762c06ab18a: [[Pasted Image 20240102182953_707.png]]
f0b44aa8f1f4c14f9004fb3838633007a2b64c8a: [[Pasted Image 20240102183008_718.png]]
96bc3a9efa1d7ddfc6859f026021bd83611a4ff2: [[Pasted Image 20240102183023_719.png]]
32fdf7b52a3e500d5c1ef20547e7cc11d096c103: [[Pasted Image 20240102183038_720.png]]
7ce00d90897cb534a2631ac3d74127d921426c50: [[Pasted Image 20240102183256_732.png]]
aae17a15e1973b8b0e60dfcabc6978101c2dcce4: [[Pasted Image 20240102183410_430.png]]
a7f7cff3c29b470224f3ae6aa0d77c76f94e3d81: [[Pasted Image 20240102183613_769.png]]
ce100aef540a7e4fbfcbf5646ae77c2c0532af53: [[Pasted Image 20240102183628_770.png]]
9530336a26333fdc1705b97c24cd07f139b9a050: [[Pasted Image 20240104135038_064.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.20",
	"elements": [
		{
			"type": "text",
			"version": 142,
			"versionNonce": 1080467027,
			"isDeleted": false,
			"id": "tPpN0yZA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -128.54643621052637,
			"y": -402.1052621578948,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 412.66571044921875,
			"height": 35,
			"seed": 1948337694,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What are partial derivatives?",
			"rawText": "What are partial derivatives?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What are partial derivatives?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 328,
			"versionNonce": 1435984989,
			"isDeleted": false,
			"id": "m7HIMtM7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -227.356048,
			"y": -355.30263099999996,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 603.0993041992188,
			"height": 25,
			"seed": 808364126,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "a derivative in the univariate situation is defined as follows",
			"rawText": "a derivative in the univariate situation is defined as follows",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a derivative in the univariate situation is defined as follows",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 265,
			"versionNonce": 1766117565,
			"isDeleted": false,
			"id": "MJXbxmq5BdzN9ubyrDvrW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -288.68158900000003,
			"y": -318.50000000000006,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 376,
			"height": 305,
			"seed": 1166143710,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "61d1bb35d69958aa1b0505900663c43a69fbcc50",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 135,
			"versionNonce": 1455121811,
			"isDeleted": false,
			"id": "lJhKb4Gk8xeRuef_FQqnZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 103.26201498640125,
			"y": -249.08022780899893,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 182,
			"height": 148,
			"seed": 2140834782,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7fcaedad630b026b08975630186fe4348740cc2e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 211,
			"versionNonce": 289779997,
			"isDeleted": false,
			"id": "kGzGsr9rAwbaY3CHf_PaH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 249.56043787665806,
			"y": -173.29640771576487,
			"strokeColor": "#131313",
			"backgroundColor": "transparent",
			"width": 51.73078270378858,
			"height": 92.7586448481726,
			"seed": 190415518,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.7838200932340555
				],
				[
					-0.891910046617113,
					-5.35146027970228
				],
				[
					-1.7838200932341124,
					-8.027190419553392
				],
				[
					-2.6757301398511117,
					-10.702920559404504
				],
				[
					-3.567640186468225,
					-13.378650699255672
				],
				[
					-5.351460279702337,
					-16.94629088572384
				],
				[
					-6.2433703263193365,
					-19.622021025574952
				],
				[
					-7.135280372936336,
					-20.51393107219201
				],
				[
					-7.135280372936336,
					-21.405841118809064
				],
				[
					-7.135280372936336,
					-17.838200932340897
				],
				[
					-8.027190419553449,
					-11.59483060602156
				],
				[
					-8.027190419553449,
					-5.35146027970228
				],
				[
					-9.811010512787561,
					1.7838200932341124
				],
				[
					-10.70292055940456,
					7.135280372936336
				],
				[
					-10.70292055940456,
					11.59483060602156
				],
				[
					-10.70292055940456,
					13.378650699255672
				],
				[
					-10.70292055940456,
					14.270560745872729
				],
				[
					-10.70292055940456,
					15.162470792489785
				],
				[
					-12.486740652638673,
					10.70292055940456
				],
				[
					-14.270560745872785,
					3.567640186468168
				],
				[
					-16.054380839106784,
					-1.7838200932340555
				],
				[
					-16.946290885723897,
					-11.59483060602156
				],
				[
					-16.946290885723897,
					-17.838200932340897
				],
				[
					-16.946290885723897,
					-24.081571258660176
				],
				[
					-16.946290885723897,
					-29.433031538362457
				],
				[
					-16.054380839106784,
					-31.21685163159654
				],
				[
					-14.270560745872785,
					-32.1087616782136
				],
				[
					-11.59483060602156,
					-29.433031538362457
				],
				[
					-9.811010512787561,
					-22.29775116542612
				],
				[
					-7.135280372936336,
					-11.59483060602156
				],
				[
					-7.135280372936336,
					-2.6757301398511117
				],
				[
					-6.2433703263193365,
					6.2433703263193365
				],
				[
					-7.135280372936336,
					11.59483060602156
				],
				[
					-8.027190419553449,
					13.378650699255672
				],
				[
					-8.919100466170448,
					14.270560745872729
				],
				[
					-11.59483060602156,
					11.59483060602156
				],
				[
					-16.054380839106784,
					2.6757301398511117
				],
				[
					-20.51393107219201,
					-4.459550233085224
				],
				[
					-24.973481305277232,
					-14.270560745872729
				],
				[
					-26.757301398511345,
					-20.51393107219201
				],
				[
					-28.541121491745457,
					-24.973481305277232
				],
				[
					-30.32494158497957,
					-29.433031538362457
				],
				[
					-31.21685163159657,
					-33.89258177144768
				],
				[
					-31.21685163159657,
					-34.78449181806474
				],
				[
					-31.21685163159657,
					-35.676401864681765
				],
				[
					-32.10876167821357,
					-35.676401864681765
				],
				[
					-33.00067172483068,
					-29.433031538362457
				],
				[
					-34.784491818064794,
					-20.51393107219201
				],
				[
					-35.67640186468179,
					-10.702920559404504
				],
				[
					-37.460221957915905,
					-2.6757301398511117
				],
				[
					-38.352132004532905,
					1.7838200932341124
				],
				[
					-39.24404205115002,
					2.6757301398511117
				],
				[
					-39.24404205115002,
					-0.8919100466170562
				],
				[
					-39.24404205115002,
					-4.459550233085224
				],
				[
					-38.352132004532905,
					-8.919100466170448
				],
				[
					-37.460221957915905,
					-13.378650699255672
				],
				[
					-36.56831191129879,
					-16.94629088572384
				],
				[
					-34.784491818064794,
					-20.51393107219201
				],
				[
					-34.784491818064794,
					-22.29775116542612
				],
				[
					-33.89258177144768,
					-23.189661212043177
				],
				[
					-33.00067172483068,
					-24.973481305277232
				],
				[
					-32.10876167821357,
					-24.973481305277232
				],
				[
					-32.10876167821357,
					-24.081571258660176
				],
				[
					-32.10876167821357,
					-19.622021025574952
				],
				[
					-32.10876167821357,
					-12.486740652638616
				],
				[
					-32.10876167821357,
					-3.567640186468168
				],
				[
					-32.10876167821357,
					6.2433703263193365
				],
				[
					-32.10876167821357,
					16.054380839106784
				],
				[
					-32.10876167821357,
					24.081571258660233
				],
				[
					-32.10876167821357,
					31.21685163159657
				],
				[
					-32.10876167821357,
					33.89258177144768
				],
				[
					-32.10876167821357,
					35.67640186468179
				],
				[
					-32.10876167821357,
					36.56831191129885
				],
				[
					-31.21685163159657,
					36.56831191129885
				],
				[
					-31.21685163159657,
					34.78449181806474
				],
				[
					-29.433031538362457,
					28.541121491745457
				],
				[
					-28.541121491745457,
					22.29775116542612
				],
				[
					-26.757301398511345,
					12.486740652638616
				],
				[
					-26.757301398511345,
					0.8919100466170562
				],
				[
					-26.757301398511345,
					-10.702920559404504
				],
				[
					-26.757301398511345,
					-18.730110978957953
				],
				[
					-26.757301398511345,
					-24.973481305277232
				],
				[
					-26.757301398511345,
					-26.757301398511316
				],
				[
					-26.757301398511345,
					-22.29775116542612
				],
				[
					-25.865391351894345,
					-13.378650699255672
				],
				[
					-25.865391351894345,
					-3.567640186468168
				],
				[
					-25.865391351894345,
					6.2433703263193365
				],
				[
					-25.865391351894345,
					13.378650699255672
				],
				[
					-25.865391351894345,
					20.51393107219201
				],
				[
					-25.865391351894345,
					24.081571258660233
				],
				[
					-25.865391351894345,
					25.86539135189429
				],
				[
					-25.865391351894345,
					24.973481305277232
				],
				[
					-25.865391351894345,
					17.838200932340897
				],
				[
					-25.865391351894345,
					7.135280372936336
				],
				[
					-25.865391351894345,
					-4.459550233085224
				],
				[
					-25.865391351894345,
					-16.054380839106784
				],
				[
					-28.541121491745457,
					-33.00067172483065
				],
				[
					-30.32494158497957,
					-42.81168223761813
				],
				[
					-32.10876167821357,
					-49.05505256393744
				],
				[
					-32.10876167821357,
					-50.83887265717152
				],
				[
					-31.21685163159657,
					-48.16314251732041
				],
				[
					-28.541121491745457,
					-43.703592284235185
				],
				[
					-25.865391351894345,
					-33.89258177144768
				],
				[
					-23.18966121204312,
					-18.730110978957953
				],
				[
					-20.51393107219201,
					-2.6757301398511117
				],
				[
					-20.51393107219201,
					11.59483060602156
				],
				[
					-19.62202102557501,
					24.973481305277232
				],
				[
					-18.73011097895801,
					33.89258177144768
				],
				[
					-17.838200932340897,
					39.24404205114996
				],
				[
					-16.054380839106784,
					41.91977219100107
				],
				[
					-13.378650699255672,
					40.13595209776702
				],
				[
					-8.919100466170448,
					30.324941584979513
				],
				[
					-5.351460279702337,
					15.162470792489785
				],
				[
					-2.6757301398511117,
					3.567640186468168
				],
				[
					0.8919100466169994,
					-5.35146027970228
				],
				[
					12.48674065263856,
					2.6757301398511117
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 217,
			"versionNonce": 1409235763,
			"isDeleted": false,
			"id": "u0Btw59wkS_2obvMfihBv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 257.5876282962114,
			"y": -163.48539720297737,
			"strokeColor": "#131313",
			"backgroundColor": "transparent",
			"width": 44.59550233085224,
			"height": 153.40852801813162,
			"seed": 1499828254,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.8919100466169994,
					-0.8919100466170562
				],
				[
					-0.8919100466169994,
					-2.6757301398511686
				],
				[
					0,
					-3.567640186468168
				],
				[
					0.891910046617113,
					-4.459550233085224
				],
				[
					0.891910046617113,
					-5.35146027970228
				],
				[
					0.891910046617113,
					-4.459550233085224
				],
				[
					0.891910046617113,
					-3.567640186468168
				],
				[
					0.891910046617113,
					-0.8919100466170562
				],
				[
					0,
					1.7838200932340555
				],
				[
					-0.8919100466169994,
					2.6757301398511117
				],
				[
					-0.8919100466169994,
					3.567640186468168
				],
				[
					-1.7838200932339987,
					3.567640186468168
				],
				[
					-2.6757301398511117,
					3.567640186468168
				],
				[
					-2.6757301398511117,
					0.8919100466170562
				],
				[
					-4.459550233085224,
					-2.6757301398511686
				],
				[
					-5.3514602797022235,
					-7.135280372936393
				],
				[
					-5.3514602797022235,
					-9.811010512787504
				],
				[
					-5.3514602797022235,
					-10.70292055940456
				],
				[
					-4.459550233085224,
					-12.486740652638616
				],
				[
					-3.567640186468111,
					-13.378650699255672
				],
				[
					0,
					-13.378650699255672
				],
				[
					1.7838200932341124,
					-13.378650699255672
				],
				[
					3.567640186468225,
					-12.486740652638616
				],
				[
					5.351460279702337,
					-10.70292055940456
				],
				[
					8.027190419553449,
					-5.35146027970228
				],
				[
					8.919100466170448,
					-0.8919100466170562
				],
				[
					8.919100466170448,
					2.6757301398511117
				],
				[
					8.919100466170448,
					4.459550233085224
				],
				[
					7.13528037293645,
					7.135280372936336
				],
				[
					5.351460279702337,
					8.027190419553392
				],
				[
					4.459550233085224,
					8.027190419553392
				],
				[
					1.7838200932341124,
					3.567640186468168
				],
				[
					-0.8919100466169994,
					-2.6757301398511686
				],
				[
					-1.7838200932339987,
					-9.811010512787504
				],
				[
					-4.459550233085224,
					-16.94629088572384
				],
				[
					-5.3514602797022235,
					-24.973481305277232
				],
				[
					-5.3514602797022235,
					-28.541121491745457
				],
				[
					-4.459550233085224,
					-32.108761678213625
				],
				[
					-1.7838200932339987,
					-33.89258177144768
				],
				[
					0.891910046617113,
					-34.78449181806474
				],
				[
					3.567640186468225,
					-34.78449181806474
				],
				[
					5.351460279702337,
					-33.89258177144768
				],
				[
					6.2433703263193365,
					-32.108761678213625
				],
				[
					8.027190419553449,
					-27.6492114451284
				],
				[
					8.919100466170448,
					-19.62202102557501
				],
				[
					9.811010512787561,
					-15.162470792489785
				],
				[
					9.811010512787561,
					-10.70292055940456
				],
				[
					9.811010512787561,
					-8.027190419553392
				],
				[
					8.919100466170448,
					-4.459550233085224
				],
				[
					8.919100466170448,
					-6.2433703263193365
				],
				[
					8.027190419553449,
					-12.486740652638616
				],
				[
					6.2433703263193365,
					-18.730110978957953
				],
				[
					4.459550233085224,
					-28.541121491745457
				],
				[
					3.567640186468225,
					-37.46022195791588
				],
				[
					1.7838200932341124,
					-44.59550233085224
				],
				[
					1.7838200932341124,
					-52.62269275040563
				],
				[
					1.7838200932341124,
					-54.40651284363972
				],
				[
					1.7838200932341124,
					-56.1903329368738
				],
				[
					3.567640186468225,
					-50.83887265717155
				],
				[
					6.2433703263193365,
					-41.9197721910011
				],
				[
					10.70292055940456,
					-28.541121491745457
				],
				[
					12.486740652638673,
					-13.378650699255672
				],
				[
					16.054380839106898,
					-0.8919100466170562
				],
				[
					16.054380839106898,
					8.919100466170448
				],
				[
					17.838200932340897,
					16.054380839106784
				],
				[
					17.838200932340897,
					20.51393107219201
				],
				[
					17.838200932340897,
					22.29775116542612
				],
				[
					17.838200932340897,
					18.730110978957953
				],
				[
					17.838200932340897,
					11.59483060602156
				],
				[
					16.054380839106898,
					1.7838200932340555
				],
				[
					15.162470792489785,
					-8.027190419553392
				],
				[
					13.378650699255672,
					-19.62202102557501
				],
				[
					12.486740652638673,
					-29.433031538362457
				],
				[
					12.486740652638673,
					-33.89258177144768
				],
				[
					12.486740652638673,
					-35.67640186468179
				],
				[
					13.378650699255672,
					-36.56831191129882
				],
				[
					17.838200932340897,
					-28.541121491745457
				],
				[
					21.40584111880912,
					-16.054380839106784
				],
				[
					24.973481305277346,
					0.8919100466170562
				],
				[
					26.757301398511345,
					16.054380839106784
				],
				[
					29.43303153836257,
					32.10876167821357
				],
				[
					31.21685163159657,
					43.703592284235185
				],
				[
					34.784491818064794,
					54.40651284363969
				],
				[
					35.67640186468179,
					59.75797312334197
				],
				[
					38.352132004532905,
					63.32561330981014
				],
				[
					38.352132004532905,
					66.0013434496613
				],
				[
					39.24404205115002,
					66.8932534962783
				],
				[
					39.24404205115002,
					62.43370326319308
				],
				[
					37.460221957915905,
					56.1903329368738
				],
				[
					36.568311911298906,
					49.946962610554465
				],
				[
					34.784491818064794,
					41.91977219100107
				],
				[
					33.00067172483068,
					37.46022195791585
				],
				[
					32.10876167821368,
					30.324941584979513
				],
				[
					29.43303153836257,
					26.757301398511345
				],
				[
					29.43303153836257,
					25.86539135189429
				],
				[
					29.43303153836257,
					33.89258177144768
				],
				[
					29.43303153836257,
					46.3793224240863
				],
				[
					29.43303153836257,
					66.8932534962783
				],
				[
					29.43303153836257,
					82.05572428876809
				],
				[
					29.43303153836257,
					93.65055489478965
				],
				[
					29.43303153836257,
					97.21819508125782
				],
				[
					29.43303153836257,
					94.5424649414067
				],
				[
					29.43303153836257,
					87.40718456847037
				],
				[
					28.541121491745457,
					81.16381424215103
				],
				[
					28.541121491745457,
					74.0285338692147
				],
				[
					28.541121491745457,
					67.78516354289536
				],
				[
					27.649211445128458,
					63.32561330981014
				],
				[
					27.649211445128458,
					59.75797312334197
				],
				[
					27.649211445128458,
					58.86606307672491
				],
				[
					27.649211445128458,
					60.649883169959026
				],
				[
					27.649211445128458,
					64.2175233564272
				],
				[
					27.649211445128458,
					65.10943340304425
				],
				[
					27.649211445128458,
					66.0013434496613
				],
				[
					27.649211445128458,
					66.8932534962783
				],
				[
					26.757301398511345,
					66.8932534962783
				],
				[
					26.757301398511345,
					66.0013434496613
				],
				[
					26.757301398511345,
					65.10943340304425
				],
				[
					26.757301398511345,
					62.43370326319308
				],
				[
					26.757301398511345,
					59.75797312334197
				],
				[
					29.43303153836257,
					57.08224298349086
				],
				[
					31.21685163159657,
					55.298422890256745
				],
				[
					31.21685163159657,
					55.298422890256745
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 227,
			"versionNonce": 1527481725,
			"isDeleted": false,
			"id": "MnMpj1Op",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 106.854830417931,
			"y": -104.61933412625245,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 337.39959716796875,
			"height": 50,
			"seed": 305475358,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "for each infinitely small nudge in x\nwhat nudge happens to f",
			"rawText": "for each infinitely small nudge in x\nwhat nudge happens to f",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "for each infinitely small nudge in x\nwhat nudge happens to f",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 254,
			"versionNonce": 1366777043,
			"isDeleted": false,
			"id": "aslAVMAi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -219.6130129000083,
			"y": 2.0000004253758927,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 593.539306640625,
			"height": 50,
			"seed": 924279518,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We can interpret it the same way for multivariate function!\n(except maybe harder to visualize) ",
			"rawText": "We can interpret it the same way for multivariate function!\n(except maybe harder to visualize) ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can interpret it the same way for multivariate function!\n(except maybe harder to visualize) ",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 92,
			"versionNonce": 702008797,
			"isDeleted": false,
			"id": "CEtpHFkHUNUftbOF5AEXb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -244.20236195631338,
			"y": 117.55979857270079,
			"strokeColor": "#1b6893",
			"backgroundColor": "transparent",
			"width": 2.687437166216853,
			"height": 276.8060281203362,
			"seed": 746339330,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.687437166216853,
					276.8060281203362
				]
			]
		},
		{
			"type": "line",
			"version": 70,
			"versionNonce": 1522158195,
			"isDeleted": false,
			"id": "CCO2j4GCkUm5TXbIfhQQr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -334.67941321894756,
			"y": 299.40971348670803,
			"strokeColor": "#1b6893",
			"backgroundColor": "transparent",
			"width": 324.28408472350065,
			"height": 7.166499109911683,
			"seed": 52043422,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					324.28408472350065,
					7.166499109911683
				]
			]
		},
		{
			"type": "text",
			"version": 23,
			"versionNonce": 2092698173,
			"isDeleted": false,
			"id": "YhgpLGGK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -20.494385556329178,
			"y": 278.80602854571214,
			"strokeColor": "#1b6893",
			"backgroundColor": "transparent",
			"width": 11.239990234375,
			"height": 25,
			"seed": 1411503682,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "x",
			"rawText": "x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 23,
			"versionNonce": 1150190611,
			"isDeleted": false,
			"id": "Tfbih02i",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -224.70542227237343,
			"y": 109.49748707405017,
			"strokeColor": "#1b6893",
			"backgroundColor": "transparent",
			"width": 9.379989624023438,
			"height": 25,
			"seed": 198681986,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "y",
			"rawText": "y",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "y",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "freedraw",
			"version": 50,
			"versionNonce": 1956231837,
			"isDeleted": false,
			"id": "caCJjNCYQ2cZlsK1wZzeR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -179.70386996710886,
			"y": 217.8907861114634,
			"strokeColor": "#1b6893",
			"backgroundColor": "transparent",
			"width": 7.166499109911626,
			"height": 9.85393627612848,
			"seed": 1748024514,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.895812388738932,
					-0.895812388738932
				],
				[
					-0.895812388738932,
					-1.791624777477864
				],
				[
					0,
					-1.791624777477864
				],
				[
					0.8958123887389888,
					-2.687437166216796
				],
				[
					2.687437166216853,
					-2.687437166216796
				],
				[
					3.5832495549558416,
					-1.791624777477864
				],
				[
					4.479061943694774,
					-0.895812388738932
				],
				[
					4.479061943694774,
					0.895812388738932
				],
				[
					5.374874332433706,
					2.6874371662169096
				],
				[
					5.374874332433706,
					4.479061943694774
				],
				[
					5.374874332433706,
					5.374874332433706
				],
				[
					5.374874332433706,
					6.270686721172638
				],
				[
					5.374874332433706,
					7.166499109911683
				],
				[
					3.5832495549558416,
					7.166499109911683
				],
				[
					0.8958123887389888,
					5.374874332433706
				],
				[
					0,
					3.5832495549558416
				],
				[
					-0.895812388738932,
					2.6874371662169096
				],
				[
					-0.895812388738932,
					0.895812388738932
				],
				[
					-1.7916247774779208,
					0
				],
				[
					-0.895812388738932,
					0
				],
				[
					0,
					0.895812388738932
				],
				[
					0,
					1.7916247774779777
				],
				[
					0.8958123887389888,
					1.7916247774779777
				],
				[
					0.8958123887389888,
					2.6874371662169096
				],
				[
					0.8958123887389888,
					3.5832495549558416
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
			"type": "arrow",
			"version": 121,
			"versionNonce": 116033971,
			"isDeleted": false,
			"id": "Kmf5A4pNv8Ytxk2WAR4ND",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -151.03787352746235,
			"y": 205.34941266911812,
			"strokeColor": "#1b6893",
			"backgroundColor": "transparent",
			"width": 410.2820740424401,
			"height": 85.9979893189394,
			"seed": 1936137602,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645215,
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
					191.7038511901357,
					-74.35242826533306
				],
				[
					410.2820740424401,
					11.645561053606343
				]
			]
		},
		{
			"type": "line",
			"version": 79,
			"versionNonce": 438460157,
			"isDeleted": false,
			"id": "noV7q4e73eHrVudAwp2-t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 144.58021475639185,
			"y": 303.8887754304028,
			"strokeColor": "#1b6893",
			"backgroundColor": "transparent",
			"width": 347.57520683071346,
			"height": 5.374874332433706,
			"seed": 1122450718,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					347.57520683071346,
					5.374874332433706
				]
			]
		},
		{
			"type": "text",
			"version": 39,
			"versionNonce": 1458887507,
			"isDeleted": false,
			"id": "vbUUHYbD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 459.7189487223108,
			"y": 318.22177365022605,
			"strokeColor": "#1b6893",
			"backgroundColor": "transparent",
			"width": 50.539947509765625,
			"height": 25,
			"seed": 314121118,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "f(x,y)",
			"rawText": "f(x,y)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f(x,y)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 74,
			"versionNonce": 1675065181,
			"isDeleted": false,
			"id": "3PXVgd20VbaxZLqqYIdod",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 344.34637744517823,
			"y": 306.5762125966197,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 34.93668316081914,
			"height": 0.895812388738932,
			"seed": 864132318,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645215,
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
					-34.93668316081914,
					0.895812388738932
				]
			]
		},
		{
			"type": "text",
			"version": 60,
			"versionNonce": 17037555,
			"isDeleted": false,
			"id": "SJ1q5B8Y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 321.2550162098641,
			"y": 323.59664798265976,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 21.0999755859375,
			"height": 25,
			"seed": 1879333150,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645215,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "df",
			"rawText": "df",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "df",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "freedraw",
			"version": 27,
			"versionNonce": 2081063869,
			"isDeleted": false,
			"id": "6H0BnTQAfuhqf6YCX7Y3G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -179.70386996710886,
			"y": 298.5139010979691,
			"strokeColor": "#1b6893",
			"backgroundColor": "transparent",
			"width": 0.8958123887389888,
			"height": 8.958123887389547,
			"seed": 2137816798,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					0.895812388738932
				],
				[
					0,
					2.6874371662169096
				],
				[
					0.8958123887389888,
					3.5832495549558416
				],
				[
					0.8958123887389888,
					6.270686721172751
				],
				[
					0.8958123887389888,
					7.166499109911683
				],
				[
					0.8958123887389888,
					8.958123887389547
				],
				[
					0.8958123887389888,
					8.958123887389547
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "freedraw",
			"version": 32,
			"versionNonce": 43934355,
			"isDeleted": false,
			"id": "XVbCJDJcV0UCTcU3lKvHd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -240.6191124013576,
			"y": 219.68241088894138,
			"strokeColor": "#1b6893",
			"backgroundColor": "transparent",
			"width": 10.749748664867411,
			"height": 0,
			"seed": 1528395038,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-0.895812388738932,
					0
				],
				[
					-1.7916247774779208,
					0
				],
				[
					-3.583249554955785,
					0
				],
				[
					-4.479061943694774,
					0
				],
				[
					-5.374874332433706,
					0
				],
				[
					-6.270686721172694,
					0
				],
				[
					-7.166499109911626,
					0
				],
				[
					-8.062311498650558,
					0
				],
				[
					-8.958123887389547,
					0
				],
				[
					-9.85393627612848,
					0
				],
				[
					-10.749748664867411,
					0
				],
				[
					-10.749748664867411,
					0
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 402,
			"versionNonce": 1188889629,
			"isDeleted": false,
			"id": "4bpVsAWm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -212.10239757569087,
			"y": 366.59564264212946,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 607.6593627929688,
			"height": 175,
			"seed": 635787330,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "For every point in our 2d input space, what change is caused\nin the output of the function\nexcept\nthere are multiple ways to move in out input space thus we\nneed to evaluate it for every input dimension seperately\nby treating all other dimensions as constants\nWHICH IS WHY ITS CALLED PARTIAL!!",
			"rawText": "For every point in our 2d input space, what change is caused\nin the output of the function\nexcept\nthere are multiple ways to move in out input space thus we\nneed to evaluate it for every input dimension seperately\nby treating all other dimensions as constants\nWHICH IS WHY ITS CALLED PARTIAL!!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "For every point in our 2d input space, what change is caused\nin the output of the function\nexcept\nthere are multiple ways to move in out input space thus we\nneed to evaluate it for every input dimension seperately\nby treating all other dimensions as constants\nWHICH IS WHY ITS CALLED PARTIAL!!",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "arrow",
			"version": 56,
			"versionNonce": 1685755955,
			"isDeleted": false,
			"id": "9Ywk26uJXAy3BOK3Wdvi9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -179.35957731920482,
			"y": 221.6178573389549,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 35.357335728929826,
			"height": 0,
			"seed": 170858178,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645216,
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
					35.357335728929826,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 44,
			"versionNonce": 675313789,
			"isDeleted": false,
			"id": "OrIwNaMneDO30YWD81mbi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -180.1452958909588,
			"y": 221.2249980530779,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 0.3928592858769946,
			"height": 29.857305726651845,
			"seed": 1500779842,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645216,
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
					0.3928592858769946,
					-29.857305726651845
				]
			]
		},
		{
			"type": "text",
			"version": 21,
			"versionNonce": 1417615827,
			"isDeleted": false,
			"id": "xpar5z5A",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -219.2040133840031,
			"y": 202.367752330982,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 20.759979248046875,
			"height": 25,
			"seed": 1535521310,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dy",
			"rawText": "dy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dy",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 21,
			"versionNonce": 167141597,
			"isDeleted": false,
			"id": "EkI6CasF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -168.27658795341515,
			"y": 238.90366591754284,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 22.619979858398438,
			"height": 25,
			"seed": 173118914,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dx",
			"rawText": "dx",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dx",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 63,
			"versionNonce": 2143446899,
			"isDeleted": false,
			"id": "Fsi6gqyBG7FZBrAAHkuAK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 574.8947705721365,
			"y": 293.7100696105385,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 349.3333333333335,
			"height": 1.3333333333333712,
			"seed": 1298524382,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645216,
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
					349.3333333333335,
					1.3333333333333712
				]
			]
		},
		{
			"type": "text",
			"version": 78,
			"versionNonce": 563100989,
			"isDeleted": false,
			"id": "Pzft0FCg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1177.3759870028007,
			"y": 144.71006961053848,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 379.0375671386719,
			"height": 35,
			"seed": 237361502,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Second Partial derivatives?",
			"rawText": "Second Partial derivatives?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Second Partial derivatives?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 440,
			"versionNonce": 747307283,
			"isDeleted": false,
			"id": "Ty18TpWg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 963.1386263664076,
			"y": 225.3767362772051,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 834.178955078125,
			"height": 150,
			"seed": 802517762,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "as with normal derivatives, the actual derivative is a function and we\ncan extract another derivative out of it, this also applies to multivariate calculus\nyou have to keep in mind that we are deriving for multiple inputs\n\nmeaning at each stage we also have to derive for each input leading to\na tree structure of sorts",
			"rawText": "as with normal derivatives, the actual derivative is a function and we\ncan extract another derivative out of it, this also applies to multivariate calculus\nyou have to keep in mind that we are deriving for multiple inputs\n\nmeaning at each stage we also have to derive for each input leading to\na tree structure of sorts",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "as with normal derivatives, the actual derivative is a function and we\ncan extract another derivative out of it, this also applies to multivariate calculus\nyou have to keep in mind that we are deriving for multiple inputs\n\nmeaning at each stage we also have to derive for each input leading to\na tree structure of sorts",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "image",
			"version": 57,
			"versionNonce": 1987022237,
			"isDeleted": false,
			"id": "hNMiSBZbBUfp7qM-7IZrz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 799.1500086673745,
			"y": 403.0434029438717,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 1127.4895238095241,
			"height": 645.3333333333335,
			"seed": 508895710,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "24771122d5db5d792e239064e80cbf42183cdd75",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 70,
			"versionNonce": 340747955,
			"isDeleted": false,
			"id": "3u3-VKvVjLZbgrzxnil6y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1850.9078111950844,
			"y": 841.5140771784781,
			"strokeColor": "#131313",
			"backgroundColor": "transparent",
			"width": 38,
			"height": 34,
			"seed": 1056353410,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1,
					0
				],
				[
					3,
					-3
				],
				[
					5,
					-7
				],
				[
					7,
					-9
				],
				[
					8,
					-9
				],
				[
					9,
					-7
				],
				[
					12,
					-1
				],
				[
					14,
					3
				],
				[
					15,
					6
				],
				[
					17,
					10
				],
				[
					17,
					12
				],
				[
					17,
					14
				],
				[
					15,
					14
				],
				[
					13,
					15
				],
				[
					12,
					15
				],
				[
					10,
					14
				],
				[
					9,
					13
				],
				[
					8,
					12
				],
				[
					7,
					9
				],
				[
					7,
					6
				],
				[
					7,
					4
				],
				[
					8,
					3
				],
				[
					10,
					3
				],
				[
					15,
					6
				],
				[
					19,
					10
				],
				[
					22,
					13
				],
				[
					23,
					15
				],
				[
					23,
					16
				],
				[
					23,
					17
				],
				[
					21,
					17
				],
				[
					18,
					17
				],
				[
					14,
					14
				],
				[
					11,
					11
				],
				[
					4,
					7
				],
				[
					-4,
					0
				],
				[
					-8,
					-6
				],
				[
					-10,
					-10
				],
				[
					-13,
					-14
				],
				[
					-14,
					-16
				],
				[
					-12,
					-17
				],
				[
					-5,
					-13
				],
				[
					1,
					-7
				],
				[
					7,
					-2
				],
				[
					10,
					1
				],
				[
					13,
					5
				],
				[
					14,
					9
				],
				[
					15,
					10
				],
				[
					15,
					11
				],
				[
					13,
					11
				],
				[
					11,
					11
				],
				[
					9,
					10
				],
				[
					4,
					7
				],
				[
					-3,
					2
				],
				[
					-5,
					-2
				],
				[
					-6,
					-5
				],
				[
					-6,
					-8
				],
				[
					-6,
					-9
				],
				[
					-4,
					-9
				],
				[
					-1,
					-7
				],
				[
					3,
					-4
				],
				[
					9,
					2
				],
				[
					13,
					7
				],
				[
					18,
					11
				],
				[
					22,
					14
				],
				[
					23,
					14
				],
				[
					24,
					14
				],
				[
					24,
					14
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 382,
			"versionNonce": 667275773,
			"isDeleted": false,
			"id": "QQKLxed2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1194.4581957165688,
			"y": 1042.2640771784781,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 693.3992309570312,
			"height": 150,
			"seed": 82398,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "notice how deriving for x then y and deriving for y then x \ngrants us the same results!\nthis is not always true but its quite common!\naccording to schwartz's theorem where the function has to meet\nthe criterion that its second partial derivative at that certain point\nis continuous results in this equality",
			"rawText": "notice how deriving for x then y and deriving for y then x \ngrants us the same results!\nthis is not always true but its quite common!\naccording to schwartz's theorem where the function has to meet\nthe criterion that its second partial derivative at that certain point\nis continuous results in this equality",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "notice how deriving for x then y and deriving for y then x \ngrants us the same results!\nthis is not always true but its quite common!\naccording to schwartz's theorem where the function has to meet\nthe criterion that its second partial derivative at that certain point\nis continuous results in this equality",
			"lineHeight": 1.25,
			"baseline": 143
		},
		{
			"type": "arrow",
			"version": 88,
			"versionNonce": 2109085779,
			"isDeleted": false,
			"id": "wWwqE1ovVxbXcxm7M7jUo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -465.4986329636022,
			"y": 294.2253412031576,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 349.3333333333334,
			"height": 1.333333333333371,
			"seed": 346185922,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645216,
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
					-349.3333333333334,
					1.333333333333371
				]
			]
		},
		{
			"type": "text",
			"version": 79,
			"versionNonce": 1922337373,
			"isDeleted": false,
			"id": "S0A5yNXD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1325.3779676521126,
			"y": 203.12470460182243,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 119.08448791503906,
			"height": 35,
			"seed": 2025032798,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Gradient",
			"rawText": "Gradient",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gradient",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 198,
			"versionNonce": 378902003,
			"isDeleted": false,
			"id": "fLsQRuTu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1661.570910093203,
			"y": 270.0303440813158,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 783.59912109375,
			"height": 50,
			"seed": 2021906014,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The gradient of a function is a vector valued partial derivative of a function\nit is used to package all the information we get about the derivative",
			"rawText": "The gradient of a function is a vector valued partial derivative of a function\nit is used to package all the information we get about the derivative",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The gradient of a function is a vector valued partial derivative of a function\nit is used to package all the information we get about the derivative",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 142,
			"versionNonce": 2007840445,
			"isDeleted": false,
			"id": "ftsDmZTK5r0r8tm8Y-mcc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1350.8572249611323,
			"y": 405.90255818840143,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 22.082740423938958,
			"height": 20.658047493362346,
			"seed": 678320002,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					22.082740423938958,
					0.7123464652883627
				],
				[
					9.260504048748544,
					20.658047493362346
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 116,
			"versionNonce": 234119059,
			"isDeleted": false,
			"id": "qoNgOGZb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1317.6128670582373,
			"y": 399.4778652578247,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 58.88426208496094,
			"height": 35,
			"seed": 1154409566,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "f = ",
			"rawText": "f = ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f = ",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "line",
			"version": 249,
			"versionNonce": 1102141213,
			"isDeleted": false,
			"id": "2vO8ku7gY9TMd8R1cnJ3L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1242.810463872236,
			"y": 332.1146090997723,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 17.808661632209123,
			"height": 176.12065879247052,
			"seed": 1491443998,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-17.808661632209123,
					-0.7123464652883627
				],
				[
					-17.70858853646564,
					174.41484745105714
				],
				[
					-1.6057382456699543,
					175.40831232718216
				]
			]
		},
		{
			"type": "line",
			"version": 336,
			"versionNonce": 1846080819,
			"isDeleted": false,
			"id": "XHxugzk74bDVONb_lr8xC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1223.5580084330566,
			"y": 332.82695556506064,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 21.701548917359105,
			"height": 174.46488399892905,
			"seed": 133876894,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					19.233354562785735,
					0.7123464652883627
				],
				[
					21.701548917359105,
					174.46488399892905
				],
				[
					2.618303998188594,
					174.41484745105708
				]
			]
		},
		{
			"type": "line",
			"version": 94,
			"versionNonce": 185756541,
			"isDeleted": false,
			"id": "8Y6pVUuF249dKW0GnTQVx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1244.8129711120434,
			"y": 371.2990594257053,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 29.47279132503877,
			"height": 0.33115495870828227,
			"seed": 81208414,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					29.47279132503877,
					0.33115495870828227
				]
			]
		},
		{
			"type": "line",
			"version": 129,
			"versionNonce": 909760211,
			"isDeleted": false,
			"id": "YuBRv-hawknPtPdiWPRJu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1246.303168426231,
			"y": 457.5025872199707,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 29.47279132503877,
			"height": 0.33115495870828227,
			"seed": 1604664130,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					29.47279132503877,
					0.33115495870828227
				]
			]
		},
		{
			"type": "text",
			"version": 97,
			"versionNonce": 1142027229,
			"isDeleted": false,
			"id": "xSWpQYaR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1241.7856055979719,
			"y": 429.6150077777417,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 21.0999755859375,
			"height": 25,
			"seed": 274416798,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "df",
			"rawText": "df",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "df",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 57,
			"versionNonce": 891126899,
			"isDeleted": false,
			"id": "4igCm5ra",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1240.792140721847,
			"y": 340.9166916554571,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 21.0999755859375,
			"height": 25,
			"seed": 1098270366,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "df",
			"rawText": "df",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "df",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 78,
			"versionNonce": 1489072189,
			"isDeleted": false,
			"id": "PeGfxbWq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1241.5521428580776,
			"y": 377.2598486824547,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 22.619979858398438,
			"height": 25,
			"seed": 2094907934,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dx",
			"rawText": "dx",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dx",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 97,
			"versionNonce": 578453011,
			"isDeleted": false,
			"id": "ONBc926R",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1244.264847098693,
			"y": 462.366673070488,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 20.759979248046875,
			"height": 25,
			"seed": 170389186,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dy",
			"rawText": "dy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dy",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 237,
			"versionNonce": 922902685,
			"isDeleted": false,
			"id": "Oj3eaTaq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1735.9872747055585,
			"y": 539.0698755859494,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 967.3790283203125,
			"height": 50,
			"seed": 1805056670,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The gradient of a point is a vector describing the direction of steepest ascent on that function\nand its magnitude is the steepness measure",
			"rawText": "The gradient of a point is a vector describing the direction of steepest ascent on that function\nand its magnitude is the steepness measure",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The gradient of a point is a vector describing the direction of steepest ascent on that function\nand its magnitude is the steepness measure",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 113,
			"versionNonce": 2034713523,
			"isDeleted": false,
			"id": "sFtAJCM4PHA02lpLB5i1y",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 94.82072507460418,
			"y": 584.2276149531278,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 1.34329808157554,
			"height": 197.1129354129156,
			"seed": 1211324738,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "0FrxbtTo",
				"focus": -0.026039129378143847,
				"gap": 12.218815675750648
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
					-1.34329808157554,
					197.1129354129156
				]
			]
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 344343805,
			"isDeleted": false,
			"id": "0FrxbtTo",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -50.19481837939668,
			"y": 793.5593660417941,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 294.6172180175781,
			"height": 35,
			"seed": 1935845854,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "sFtAJCM4PHA02lpLB5i1y",
					"type": "arrow"
				}
			],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Directional derivative",
			"rawText": "Directional derivative",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Directional derivative",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 241,
			"versionNonce": 296375635,
			"isDeleted": false,
			"id": "HkqtKVf7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -284.4557894487325,
			"y": 839.8284142443325,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 763.13916015625,
			"height": 50,
			"seed": 2022741890,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Directional derivative of vector v is the change of output thats resulted in\nwalking infinitely small steps in the direction of vector v",
			"rawText": "Directional derivative of vector v is the change of output thats resulted in\nwalking infinitely small steps in the direction of vector v",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Directional derivative of vector v is the change of output thats resulted in\nwalking infinitely small steps in the direction of vector v",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 299,
			"versionNonce": 1959697757,
			"isDeleted": false,
			"id": "9oZgZEz8RM0wvosjk326h",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 129.640189124299,
			"y": 990.7718205581375,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 22.082740423938958,
			"height": 20.658047493362346,
			"seed": 2140947778,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					22.082740423938958,
					0.7123464652883627
				],
				[
					9.260504048748544,
					20.658047493362346
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 273,
			"versionNonce": 2063217395,
			"isDeleted": false,
			"id": "BuYlVFy2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 162.884547027194,
			"y": 984.3471276275607,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 58.88426208496094,
			"height": 35,
			"seed": 2082884866,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "f = ",
			"rawText": "f = ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f = ",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "line",
			"version": 677,
			"versionNonce": 1865214397,
			"isDeleted": false,
			"id": "o_3970kPQq605-F5KDzq-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1.406963815806506,
			"y": 964.5789202308176,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 19.305720775751983,
			"height": 71.07350110640604,
			"seed": 832134338,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-19.305720775751983,
					0.07453917544756006
				],
				[
					-19.2049152877688,
					70.86999904640292
				],
				[
					-0.540935867498721,
					71.07350110640604
				]
			]
		},
		{
			"type": "line",
			"version": 696,
			"versionNonce": 364731539,
			"isDeleted": false,
			"id": "0OrFnuFqNZoqvSKDaN8h6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 12.495248721773294,
			"y": 964.7184119503283,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 21.740615958447535,
			"height": 70.19218535050308,
			"seed": 764703874,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					21.715655998618978,
					0.2850946046931064
				],
				[
					21.74061595844754,
					70.19218535050308
				],
				[
					2.6230174585166455,
					70.17215977231763
				]
			]
		},
		{
			"type": "line",
			"version": 298,
			"versionNonce": 885172765,
			"isDeleted": false,
			"id": "Y_oyLvdUwzbexKWU1DLg0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 239.1050339189381,
			"y": 997.7040689914086,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 29.47279132503877,
			"height": 0.33115495870828227,
			"seed": 1909888066,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					29.47279132503877,
					0.33115495870828227
				]
			]
		},
		{
			"type": "line",
			"version": 335,
			"versionNonce": 1839878707,
			"isDeleted": false,
			"id": "YIWYgSrgkW_E_hdEKJVzU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 316.2884283524059,
			"y": 998.3928231469179,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 29.47279132503877,
			"height": 0.33115495870828227,
			"seed": 1883159554,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					29.47279132503877,
					0.33115495870828227
				]
			]
		},
		{
			"type": "text",
			"version": 303,
			"versionNonce": 1451318909,
			"isDeleted": false,
			"id": "OrnZKYet",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 320.805991180665,
			"y": 970.5052437046891,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 21.0999755859375,
			"height": 25,
			"seed": 114027458,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "df",
			"rawText": "df",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "df",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 261,
			"versionNonce": 1403491283,
			"isDeleted": false,
			"id": "cwvZhjHN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 243.12586430913444,
			"y": 967.3217012211605,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 21.0999755859375,
			"height": 25,
			"seed": 2073895810,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "df",
			"rawText": "df",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "df",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 282,
			"versionNonce": 1261078237,
			"isDeleted": false,
			"id": "fUANefa4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 242.36586217290397,
			"y": 1003.6648582481582,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 22.619979858398438,
			"height": 25,
			"seed": 2029085506,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dx",
			"rawText": "dx",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dx",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 303,
			"versionNonce": 936092019,
			"isDeleted": false,
			"id": "vADG5iul",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 318.32674967994404,
			"y": 1003.2569089974352,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 20.759979248046875,
			"height": 25,
			"seed": 153594626,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dy",
			"rawText": "dy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dy",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 176,
			"versionNonce": 894411581,
			"isDeleted": false,
			"id": "9bjao0H2",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 146.86997062837173,
			"y": 1001.4805269310293,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 8.368011474609375,
			"height": 20,
			"seed": 1854330142,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "v",
			"rawText": "v",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "v",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 198,
			"versionNonce": 1130167059,
			"isDeleted": false,
			"id": "UgcG6uoO",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -76.28132053681134,
			"y": 983.7765116675275,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 45.920196533203125,
			"height": 35,
			"seed": 1086787458,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645216,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "v =",
			"rawText": "v =",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "v =",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 180,
			"versionNonce": 1766994845,
			"isDeleted": false,
			"id": "XauZSyZ7",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 0.6021125114151289,
			"y": 972.2756542954974,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 13.339981079101562,
			"height": 50,
			"seed": 1532062302,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "a\nb",
			"rawText": "a\nb",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a\nb",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 118,
			"versionNonce": 852631731,
			"isDeleted": false,
			"id": "XklJLaeA",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 222.08026587505282,
			"y": 981.8775722032781,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 13.339981079101562,
			"height": 25,
			"seed": 1135253570,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "a",
			"rawText": "a",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 125,
			"versionNonce": 862173181,
			"isDeleted": false,
			"id": "0WRF3RV1",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 277.9001612865514,
			"y": 985.298163148828,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 32.65995788574219,
			"height": 25,
			"seed": 854182622,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "+ b",
			"rawText": "+ b",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "+ b",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 113,
			"versionNonce": 1876005459,
			"isDeleted": false,
			"id": "gugo7j9upH4Egnz1h2FTe",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1756.4635048134146,
			"y": 897.0106948162711,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 309.61571989375284,
			"height": 0.8190892060680426,
			"seed": 1863871155,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
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
					309.61571989375284,
					0.8190892060680426
				]
			]
		},
		{
			"type": "arrow",
			"version": 112,
			"versionNonce": 1569042525,
			"isDeleted": false,
			"id": "aNOf1Ct0Ul4UBDuUbVjf_",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1755.6444156073464,
			"y": 895.3725164041348,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 2.457267618204469,
			"height": 274.39488403282326,
			"seed": 1312446493,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
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
					2.457267618204469,
					-274.39488403282326
				]
			]
		},
		{
			"type": "arrow",
			"version": 92,
			"versionNonce": 1798426611,
			"isDeleted": false,
			"id": "lcsMv-LNRTUsR6CZkZLCI",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1631.1428562849908,
			"y": 813.4635957973219,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 63.88895807331414,
			"height": 65.52713648545034,
			"seed": 1407940157,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
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
					63.88895807331414,
					-65.52713648545034
				]
			]
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 1971952829,
			"isDeleted": false,
			"id": "gEak0ZKP",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1550.3084878167824,
			"y": 768.4136894635748,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 10.339996337890625,
			"height": 25,
			"seed": 1292526035,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "V",
			"rawText": "V",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "V",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 511,
			"versionNonce": 922311059,
			"isDeleted": false,
			"id": "U7pdCNUe",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1421.425313584655,
			"y": 640.6357733169467,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 875.5989990234375,
			"height": 200,
			"seed": 36257757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Say we want to find the highest directional gradient of vector v\nthis is intuitively the steepest ascent since it gives maximal change in the\nfunction such that its in the direction of v (Assuming V is unit length)\n\n\n\nAs we know from the dot product, the highest values come when the two vectors\nactually align thus the maximal value is in the direction of the gradient of the function",
			"rawText": "Say we want to find the highest directional gradient of vector v\nthis is intuitively the steepest ascent since it gives maximal change in the\nfunction such that its in the direction of v (Assuming V is unit length)\n\n\n\nAs we know from the dot product, the highest values come when the two vectors\nactually align thus the maximal value is in the direction of the gradient of the function",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Say we want to find the highest directional gradient of vector v\nthis is intuitively the steepest ascent since it gives maximal change in the\nfunction such that its in the direction of v (Assuming V is unit length)\n\n\n\nAs we know from the dot product, the highest values come when the two vectors\nactually align thus the maximal value is in the direction of the gradient of the function",
			"lineHeight": 1.25,
			"baseline": 193
		},
		{
			"type": "image",
			"version": 103,
			"versionNonce": 1393622301,
			"isDeleted": false,
			"id": "PC9G9pJQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1178.5073301908928,
			"y": 731.2382831036472,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 186.16531489758648,
			"height": 43.80360350531446,
			"seed": 90297,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "062f747b872f430825ccbe1e32cef94004f31131",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 195,
			"versionNonce": 1616817971,
			"isDeleted": false,
			"id": "ZjhwEScA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1359.7701840616728,
			"y": 1306.4085992267244,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 408.80169677734375,
			"height": 35,
			"seed": 1542536925,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is the Jacobian matrix?",
			"rawText": "What is the Jacobian matrix?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is the Jacobian matrix?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 1569542525,
			"isDeleted": false,
			"id": "IjaBrRbl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1509.7701840616728,
			"y": 1345.4085992267244,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 724.8592529296875,
			"height": 75,
			"seed": 1820285757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The Jacobian matrix is a matrix that contains information about the\npartial derivatives of a certain function to describe the infinitely small\nchanges that happen when we preform said function as a transformation.",
			"rawText": "The Jacobian matrix is a matrix that contains information about the\npartial derivatives of a certain function to describe the infinitely small\nchanges that happen when we preform said function as a transformation.",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The Jacobian matrix is a matrix that contains information about the\npartial derivatives of a certain function to describe the infinitely small\nchanges that happen when we preform said function as a transformation.",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "line",
			"version": 320,
			"versionNonce": 164122835,
			"isDeleted": false,
			"id": "STZSPo-g1g3ebMsaOsBWs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1249.9271237094604,
			"y": 1565.1651798391135,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 47,
			"height": 255,
			"seed": 298511261,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-45,
					0
				],
				[
					-45,
					254
				],
				[
					2,
					255
				]
			]
		},
		{
			"type": "line",
			"version": 350,
			"versionNonce": 306190813,
			"isDeleted": false,
			"id": "7uKq_F-6O2er728D7Tb6S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1004.1157055439078,
			"y": 1568.7166617460207,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 47,
			"height": 255,
			"seed": 1006989309,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					45,
					0
				],
				[
					45,
					254
				],
				[
					-2,
					255
				]
			]
		},
		{
			"type": "line",
			"version": 147,
			"versionNonce": 1154268787,
			"isDeleted": false,
			"id": "rfoMWRNWXhOdp21w7eL3f",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1256.365902989106,
			"y": 1618.2489343264294,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 49.34139852979342,
			"height": 0.6492289280235752,
			"seed": 1496344669,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					49.34139852979342,
					-0.6492289280235752
				]
			]
		},
		{
			"type": "line",
			"version": 149,
			"versionNonce": 1245369917,
			"isDeleted": false,
			"id": "t5bPyqeEOHEYzJpRv6hmY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1254.4182162050352,
			"y": 1745.8294649651787,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 49.34139852979342,
			"height": 0.6492289280235752,
			"seed": 454907069,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					49.34139852979342,
					-0.6492289280235752
				]
			]
		},
		{
			"type": "line",
			"version": 149,
			"versionNonce": 741505043,
			"isDeleted": false,
			"id": "h1VnyMeiy4OWjd-eA6ukk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1069.3879717183097,
			"y": 1746.4786938932023,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 49.34139852979342,
			"height": 0.6492289280235752,
			"seed": 2104341789,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					49.34139852979342,
					-0.6492289280235752
				]
			]
		},
		{
			"type": "line",
			"version": 149,
			"versionNonce": 1079969437,
			"isDeleted": false,
			"id": "D5DA61usHvqoljQiOjrdf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1064.1941402941209,
			"y": 1617.2821372165063,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 49.34139852979342,
			"height": 0.6492289280235752,
			"seed": 194185597,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					49.34139852979342,
					-0.6492289280235752
				]
			]
		},
		{
			"type": "text",
			"version": 115,
			"versionNonce": 1039138227,
			"isDeleted": false,
			"id": "uKE9MEru",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1314.9649193003402,
			"y": 1467.17242552112,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 118.49649047851562,
			"height": 35,
			"seed": 1724830173,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "F(x,y) = ",
			"rawText": "F(x,y) = ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "F(x,y) = ",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "line",
			"version": 161,
			"versionNonce": 1465789181,
			"isDeleted": false,
			"id": "H7Hhggv-WUnO8bync9NTE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1170.667684489991,
			"y": 1433.218689839704,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 20.775325696755147,
			"height": 111.66737562005886,
			"seed": 204639805,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-18.827638912684336,
					0.6492289280236037
				],
				[
					-18.178409984660732,
					111.66737562005886
				],
				[
					1.947686784070811,
					111.66737562005886
				]
			]
		},
		{
			"type": "line",
			"version": 241,
			"versionNonce": 1965805395,
			"isDeleted": false,
			"id": "-u69Uk2RkmOfS884ykXhZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1131.4194366916524,
			"y": 1434.4140419731177,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 20.775325696755147,
			"height": 111.66737562005886,
			"seed": 1520418461,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					18.827638912684336,
					0.6492289280236037
				],
				[
					18.178409984660732,
					111.66737562005886
				],
				[
					-1.947686784070811,
					111.66737562005886
				]
			]
		},
		{
			"type": "text",
			"version": 101,
			"versionNonce": 532267869,
			"isDeleted": false,
			"id": "mRU2RE1X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1179.970019942541,
			"y": 1454.449413040294,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 56.25994873046875,
			"height": 25,
			"seed": 1489494781,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "g1(x,y)",
			"rawText": "g1(x,y)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "g1(x,y)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 607939827,
			"isDeleted": false,
			"id": "g9Fgh0CB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1185.0292449032795,
			"y": 1509.8277033464888,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 65.07994079589844,
			"height": 25,
			"seed": 992770909,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "g2(x,y)",
			"rawText": "g2(x,y)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "g2(x,y)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 97,
			"versionNonce": 499339197,
			"isDeleted": false,
			"id": "wIqODSJv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1239.7590490132905,
			"y": 1625.390452534689,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 22.619979858398438,
			"height": 25,
			"seed": 706676669,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dx",
			"rawText": "dx",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dx",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 99,
			"versionNonce": 245913235,
			"isDeleted": false,
			"id": "eLvjtOMB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1238.4605911572432,
			"y": 1752.4746720597627,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 22.619979858398438,
			"height": 25,
			"seed": 1203832861,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dx",
			"rawText": "dx",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dx",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 124,
			"versionNonce": 1335644189,
			"isDeleted": false,
			"id": "9AeRtsBu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1245.7544210555532,
			"y": 1585.138258997226,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 26.819976806640625,
			"height": 25,
			"seed": 1979972733,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dg1",
			"rawText": "dg1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dg1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 90,
			"versionNonce": 1126566963,
			"isDeleted": false,
			"id": "xMxgJzRP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1053.582658360568,
			"y": 1582.37669291758,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 26.819976806640625,
			"height": 25,
			"seed": 1554605277,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dg1",
			"rawText": "dg1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dg1",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 105,
			"versionNonce": 1932936317,
			"isDeleted": false,
			"id": "3g6kNMHX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1047.9557438691768,
			"y": 1629.9350550308543,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 20.759979248046875,
			"height": 25,
			"seed": 792903997,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dy",
			"rawText": "dy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dy",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 103,
			"versionNonce": 899419603,
			"isDeleted": false,
			"id": "ci7X5aJq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1053.1495752933656,
			"y": 1752.4746720597627,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 20.759979248046875,
			"height": 25,
			"seed": 858886557,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dy",
			"rawText": "dy",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dy",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 121,
			"versionNonce": 206744797,
			"isDeleted": false,
			"id": "H620KGJU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1248.8659592322208,
			"y": 1716.282502457993,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 35.63996887207031,
			"height": 25,
			"seed": 94852605,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dg2",
			"rawText": "dg2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dg2",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 132,
			"versionNonce": 421583731,
			"isDeleted": false,
			"id": "lJwngih5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1064.484943673519,
			"y": 1714.1701653063706,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 35.63996887207031,
			"height": 25,
			"seed": 564498013,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "dg2",
			"rawText": "dg2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "dg2",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 61,
			"versionNonce": 713230653,
			"isDeleted": false,
			"id": "vRGjaYiNHT5xtCl3T_IAf",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1142.3295685858402,
			"y": 948.266220697105,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 4.615384615384755,
			"height": 293.8461538461537,
			"seed": 663682387,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
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
					-4.615384615384755,
					293.8461538461537
				]
			]
		},
		{
			"type": "arrow",
			"version": 48,
			"versionNonce": 2046489875,
			"isDeleted": false,
			"id": "7qAPi5-JugtdtK--izn8N",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -808.6002978565718,
			"y": 1646.8002803204802,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 430,
			"height": 4,
			"seed": 1005876669,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
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
					430,
					4
				]
			]
		},
		{
			"type": "image",
			"version": 241,
			"versionNonce": 1864948125,
			"isDeleted": false,
			"id": "SdPlDQePPuAJ0nbO3_QVk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -4.117831546309162,
			"y": 1419.2103177010829,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 274,
			"height": 104.13301662707838,
			"seed": 539559069,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5b85ab416271304988788bd725ab5e287a88919e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 197,
			"versionNonce": 396417715,
			"isDeleted": false,
			"id": "ps5bt5Lu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -112.61783154630916,
			"y": 1277.3433343281613,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 516.4901123046875,
			"height": 35,
			"seed": 1765304573,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is the multi-variable chain rule?",
			"rawText": "What is the multi-variable chain rule?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is the multi-variable chain rule?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 285,
			"versionNonce": 1400217085,
			"isDeleted": false,
			"id": "DUpwT0RX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -166.61783154630916,
			"y": 1318.3433343281613,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 609.2994384765625,
			"height": 75,
			"seed": 932987229,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Assume that we have a function f that consists of two\nother functions y and x, both of those functions depend on t\nhow do we find the derivative of this function w.t.r t?",
			"rawText": "Assume that we have a function f that consists of two\nother functions y and x, both of those functions depend on t\nhow do we find the derivative of this function w.t.r t?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assume that we have a function f that consists of two\nother functions y and x, both of those functions depend on t\nhow do we find the derivative of this function w.t.r t?",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 172,
			"versionNonce": 2126056531,
			"isDeleted": false,
			"id": "gk058bPkhA7Gp-PA7QKSu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -121.11783154630916,
			"y": 1542.1136799245937,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 554,
			"height": 106.22965440356745,
			"seed": 1353059773,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0b41ddd8289553c34a713efb54fd45388e681c99",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 242,
			"versionNonce": 778753629,
			"isDeleted": false,
			"id": "RNwCNLfrSu6FGaHZ5CGZC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -441.61783154630916,
			"y": 1820.3433343281613,
			"strokeColor": "#2e9ada",
			"backgroundColor": "transparent",
			"width": 307,
			"height": 2,
			"seed": 1400327709,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645217,
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
					307,
					-2
				]
			]
		},
		{
			"type": "arrow",
			"version": 173,
			"versionNonce": 1662650867,
			"isDeleted": false,
			"id": "Jv6WnO671Gb4-KEzpV7pg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 80.38216845369084,
			"y": 1933.3433343281613,
			"strokeColor": "#9c4872",
			"backgroundColor": "transparent",
			"width": 3,
			"height": 243,
			"seed": 2130805373,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645217,
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
					3,
					-243
				]
			]
		},
		{
			"type": "arrow",
			"version": 151,
			"versionNonce": 2061107901,
			"isDeleted": false,
			"id": "wR80tGMZTCRHo8XEAXFi2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -19.617831546309162,
			"y": 1825.3433343281613,
			"strokeColor": "#9c4872",
			"backgroundColor": "transparent",
			"width": 307,
			"height": 1,
			"seed": 939928285,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "0LiWpUeW",
				"focus": 2.1179406342610974,
				"gap": 14
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
					307,
					1
				]
			]
		},
		{
			"type": "text",
			"version": 75,
			"versionNonce": 969560979,
			"isDeleted": false,
			"id": "Gl89I5n5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -151.26782544279354,
			"y": 1836.3433343281613,
			"strokeColor": "#2e9ada",
			"backgroundColor": "transparent",
			"width": 11.29998779296875,
			"height": 25,
			"seed": 1326892861,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "t",
			"rawText": "t",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "t",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 65,
			"versionNonce": 1566876445,
			"isDeleted": false,
			"id": "0LiWpUeW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 277.76217333650334,
			"y": 1840.3433343281613,
			"strokeColor": "#9c4872",
			"backgroundColor": "transparent",
			"width": 11.239990234375,
			"height": 25,
			"seed": 110417821,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "wR80tGMZTCRHo8XEAXFi2",
					"type": "arrow"
				}
			],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "x",
			"rawText": "x",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 64,
			"versionNonce": 318794035,
			"isDeleted": false,
			"id": "CLRkgu08",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 104.69217364167912,
			"y": 1685.3433343281613,
			"strokeColor": "#9c4872",
			"backgroundColor": "transparent",
			"width": 9.379989624023438,
			"height": 25,
			"seed": 1488051197,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "y",
			"rawText": "y",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "y",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 120,
			"versionNonce": 1786525565,
			"isDeleted": false,
			"id": "RMU6lekdzdxX1zXCc61vj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 354.38216845369084,
			"y": 1820.3433343281613,
			"strokeColor": "#247a6d",
			"backgroundColor": "transparent",
			"width": 278,
			"height": 1,
			"seed": 2104448093,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645217,
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
					278,
					1
				]
			]
		},
		{
			"type": "text",
			"version": 64,
			"versionNonce": 874695379,
			"isDeleted": false,
			"id": "VoiYw4N0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 617.5221754727338,
			"y": 1841.3433343281613,
			"strokeColor": "#247a6d",
			"backgroundColor": "transparent",
			"width": 9.719985961914062,
			"height": 25,
			"seed": 815710397,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "f",
			"rawText": "f",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "f",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 252,
			"versionNonce": 744636381,
			"isDeleted": false,
			"id": "48uCEVpx_Czel4JKsE2c_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -235.04649837052978,
			"y": 1933.8928066863934,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 244.08858340830272,
			"height": 102.38615075851624,
			"seed": 937533725,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645217,
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
					86.82345584322178,
					102.38615075851624
				],
				[
					189.20960660173802,
					81.08983140074486
				],
				[
					244.08858340830272,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 173,
			"versionNonce": 1908930675,
			"isDeleted": false,
			"id": "sCUHuQwBBtj9829q-Ii0n",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 202.34713766985158,
			"y": 1916.6919333589626,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 244.90767261437088,
			"height": 113.03431043740193,
			"seed": 682194301,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645217,
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
					90.9189018735625,
					98.29070472817563
				],
				[
					208.86774754737314,
					67.98440410365481
				],
				[
					244.90767261437088,
					-14.743605709226301
				]
			]
		},
		{
			"type": "text",
			"version": 148,
			"versionNonce": 1764244541,
			"isDeleted": false,
			"id": "HRh3b0nE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -278.03655593320855,
			"y": 2078.052506954384,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 302.21966552734375,
			"height": 75,
			"seed": 1849146845,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "for every change of t\nhow much does x get affected\nhow much does y get affected",
			"rawText": "for every change of t\nhow much does x get affected\nhow much does y get affected",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "for every change of t\nhow much does x get affected\nhow much does y get affected",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 1236693523,
			"isDeleted": false,
			"id": "NfVnVtYY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 199.43337176406817,
			"y": 2053.4798307723404,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 300.69964599609375,
			"height": 50,
			"seed": 262011453,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "for every change of x,y\nhow much does f get affected",
			"rawText": "for every change of x,y\nhow much does f get affected",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "for every change of x,y\nhow much does f get affected",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 83,
			"versionNonce": 682601629,
			"isDeleted": false,
			"id": "6hHm8Ua_1buv_pROAmmSv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -251.9085866238422,
			"y": 2163.257226312799,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 50.00000000000001,
			"height": 83,
			"seed": 901622429,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f3c611841fc2d9db0d6c94834fb6c762c06ab18a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 136,
			"versionNonce": 1021622195,
			"isDeleted": false,
			"id": "Rb_E4XpCfb57rhnMd1Ahn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -70.0332558629326,
			"y": 2161.257226312799,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 58,
			"height": 87,
			"seed": 1900564221,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f0b44aa8f1f4c14f9004fb3838633007a2b64c8a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 80,
			"versionNonce": 2057965821,
			"isDeleted": false,
			"id": "TvDOCC55CdCwit3EMU1TZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 229.18010065218243,
			"y": 2115.082160160617,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 62,
			"height": 105,
			"seed": 1086285661,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "96bc3a9efa1d7ddfc6859f026021bd83611a4ff2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 97,
			"versionNonce": 1769556307,
			"isDeleted": false,
			"id": "8eFM_AZs7bo_MYkRMeWnu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 424.46184506192185,
			"y": 2121.394987458277,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 47,
			"height": 100,
			"seed": 1450472381,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645217,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "32fdf7b52a3e500d5c1ef20547e7cc11d096c103",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 130,
			"versionNonce": 2090395997,
			"isDeleted": false,
			"id": "cOGyaMglSlVrY1U2OovcP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -315.0067064338027,
			"y": 1820.0975133275701,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 41.70239411665864,
			"height": 0,
			"seed": 512291869,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645217,
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
					41.70239411665864,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 92,
			"versionNonce": 1691002611,
			"isDeleted": false,
			"id": "aO9YUhzJCorMpd9U0nsj7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 118.42473405737076,
			"y": 1765.4058489122804,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 28.02947801283608,
			"height": 1.3672916103822104,
			"seed": 82733181,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645218,
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
					28.02947801283608,
					1.3672916103822104
				]
			]
		},
		{
			"type": "arrow",
			"version": 105,
			"versionNonce": 533575101,
			"isDeleted": false,
			"id": "SdpUHjggUFO4hc2vD2Fk-",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 147.1378578753979,
			"y": 1765.4058489122804,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 0.6836458051911904,
			"height": 43.75333153223204,
			"seed": 2070302941,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645218,
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
					0.6836458051911904,
					-43.75333153223204
				]
			]
		},
		{
			"type": "arrow",
			"version": 113,
			"versionNonce": 1432309907,
			"isDeleted": false,
			"id": "0SL4_Xlt5_T8JSt2h9W8Y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 483.4915940294313,
			"y": 1821.4648049379525,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 60.84447666201015,
			"height": 0,
			"seed": 1065495869,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704372645218,
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
					-60.84447666201015,
					0
				]
			]
		},
		{
			"type": "image",
			"version": 198,
			"versionNonce": 795473437,
			"isDeleted": false,
			"id": "LyAQ0-o1y1LsXg7vtpKVR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -179.3359145979033,
			"y": 1659.8403876499178,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 135.90827443054266,
			"height": 55.81946985540145,
			"seed": 1621327261,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645218,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7ce00d90897cb534a2631ac3d74127d921426c50",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 148,
			"versionNonce": 1290651187,
			"isDeleted": false,
			"id": "_oVmj4wk90Pu6X3i1MtTg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -181.2254017870448,
			"y": 1722.5500621723959,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 141.75564821610732,
			"height": 60.83000996246751,
			"seed": 100385277,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645218,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "aae17a15e1973b8b0e60dfcabc6978101c2dcce4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 192,
			"versionNonce": 375335549,
			"isDeleted": false,
			"id": "FRd8frNYFYWGOT1lPJfuA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 208.7953282794914,
			"y": 1725.0186626275663,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 173.89224616576004,
			"height": 52.83451727160261,
			"seed": 1955363421,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645218,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a7f7cff3c29b470224f3ae6aa0d77c76f94e3d81",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 254,
			"versionNonce": 1650231251,
			"isDeleted": false,
			"id": "wDfKBU6mwY3fy50s9qxNN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 201.55539276271907,
			"y": 1655.122594195626,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 170.20236438501058,
			"height": 62.34156369916086,
			"seed": 1428629181,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645218,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ce100aef540a7e4fbfcbf5646ae77c2c0532af53",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 40,
			"versionNonce": 1701761757,
			"isDeleted": false,
			"id": "YPxK0dp-blWrLn3mVCoZZ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1587.6342083904772,
			"y": 1616.6952516967212,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 434.6666666666665,
			"height": 2.6666666666667425,
			"seed": 961877661,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645218,
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
					-434.6666666666665,
					2.6666666666667425
				]
			]
		},
		{
			"type": "text",
			"version": 134,
			"versionNonce": 197268851,
			"isDeleted": false,
			"id": "P94ocOl9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2758.3008750571435,
			"y": 1518.3619183633882,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 393.4576110839844,
			"height": 35,
			"seed": 1848524659,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645218,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "What is the Hessian Matrix?",
			"rawText": "What is the Hessian Matrix?",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is the Hessian Matrix?",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 338,
			"versionNonce": 422211389,
			"isDeleted": false,
			"id": "rVvRRL0U",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2956.9675417238104,
			"y": 1573.6952516967217,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 842.9390869140625,
			"height": 75,
			"seed": 2007126611,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645218,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The hessian matrix is a matrix that packages all information gotten from\nthe second partial derivatives, its diagonal consists of partial derivatives consisting\nof only one variables while the others serve as a combination",
			"rawText": "The hessian matrix is a matrix that packages all information gotten from\nthe second partial derivatives, its diagonal consists of partial derivatives consisting\nof only one variables while the others serve as a combination",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The hessian matrix is a matrix that packages all information gotten from\nthe second partial derivatives, its diagonal consists of partial derivatives consisting\nof only one variables while the others serve as a combination",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "image",
			"version": 41,
			"versionNonce": 946138899,
			"isDeleted": false,
			"id": "V121Q46thFyjqB-npgKOs",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2777.134208390478,
			"y": 1684.8619183633882,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 475,
			"height": 413,
			"seed": 958339357,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372645218,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9530336a26333fdc1705b97c24cd07f139b9a050",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 42,
			"versionNonce": 1111315699,
			"isDeleted": false,
			"id": "oTG_5uMafDKiiAXsUFa0K",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2511.046661090855,
			"y": 1689.9523650683861,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 22.857142857143117,
			"height": 11.428571428571331,
			"seed": 2101607517,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372647899,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.9523809523809632
				],
				[
					0.9523809523811906,
					-0.9523809523809632
				],
				[
					0.9523809523811906,
					-1.9047619047619264
				],
				[
					0.9523809523811906,
					-2.8571428571428896
				],
				[
					-0.9523809523807358,
					-3.809523809523853
				],
				[
					-1.9047619047619264,
					-3.809523809523853
				],
				[
					-2.8571428571426623,
					-3.809523809523853
				],
				[
					-4.761904761904589,
					-3.809523809523853
				],
				[
					-7.619047619047706,
					-3.809523809523853
				],
				[
					-8.571428571428442,
					-3.809523809523853
				],
				[
					-9.523809523809177,
					-3.809523809523853
				],
				[
					-10.476190476190368,
					-2.8571428571428896
				],
				[
					-11.428571428571558,
					-2.8571428571428896
				],
				[
					-11.428571428571558,
					-1.9047619047619264
				],
				[
					-12.380952380952294,
					-1.9047619047619264
				],
				[
					-13.33333333333303,
					-1.9047619047619264
				],
				[
					-14.28571428571422,
					-1.9047619047619264
				],
				[
					-17.142857142856883,
					0.9523809523809632
				],
				[
					-18.095238095238074,
					2.8571428571428896
				],
				[
					-21.904761904761926,
					4.761904761904816
				],
				[
					-21.904761904761926,
					6.6666666666667425
				],
				[
					-21.904761904761926,
					7.619047619047478
				],
				[
					-20.952380952380736,
					7.619047619047478
				],
				[
					-20,
					7.619047619047478
				],
				[
					-19.04761904761881,
					7.619047619047478
				],
				[
					-17.142857142856883,
					7.619047619047478
				],
				[
					-15.238095238094957,
					7.619047619047478
				],
				[
					-14.28571428571422,
					6.6666666666667425
				],
				[
					-11.428571428571558,
					5.714285714285779
				],
				[
					-9.523809523809177,
					4.761904761904816
				],
				[
					-8.571428571428442,
					3.809523809523853
				],
				[
					-6.666666666666515,
					2.8571428571428896
				],
				[
					-5.714285714285779,
					1.9047619047619264
				],
				[
					-5.714285714285779,
					0.9523809523809632
				],
				[
					-4.761904761904589,
					0.9523809523809632
				],
				[
					-4.761904761904589,
					0
				],
				[
					-4.761904761904589,
					-0.9523809523809632
				],
				[
					-4.761904761904589,
					-1.9047619047619264
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
			"version": 68,
			"versionNonce": 1215183165,
			"isDeleted": false,
			"id": "idyg1uLkT1XxQj-aG0Yu_",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -2514.2471485948618,
			"y": 1689.9912661871692,
			"strokeColor": "#131313",
			"backgroundColor": "transparent",
			"width": 26.91614122766441,
			"height": 23.686204280345237,
			"seed": 873264179,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372654790,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-1.0766456491066947
				],
				[
					0,
					-2.153291298213162
				],
				[
					0,
					-3.2299369473198567
				],
				[
					1.076645649106922,
					-3.2299369473198567
				],
				[
					2.1532912982133894,
					-3.2299369473198567
				],
				[
					3.2299369473203114,
					-4.306582596426324
				],
				[
					5.383228245533246,
					-4.306582596426324
				],
				[
					5.383228245533246,
					-3.2299369473198567
				],
				[
					6.459873894639713,
					0
				],
				[
					6.459873894639713,
					3.2299369473198567
				],
				[
					6.459873894639713,
					5.383228245533019
				],
				[
					5.383228245533246,
					8.613165192852875
				],
				[
					3.2299369473203114,
					10.766456491066037
				],
				[
					1.076645649106922,
					12.9197477892792
				],
				[
					-1.0766456491064673,
					12.9197477892792
				],
				[
					-1.0766456491064673,
					11.843102140172505
				],
				[
					-1.0766456491064673,
					7.536519543746181
				],
				[
					-2.1532912982129346,
					6.459873894639486
				],
				[
					-2.1532912982129346,
					5.383228245533019
				],
				[
					-2.1532912982129346,
					4.306582596426324
				],
				[
					-2.1532912982129346,
					3.2299369473198567
				],
				[
					-2.1532912982129346,
					1.0766456491066947
				],
				[
					-1.0766456491064673,
					1.0766456491066947
				],
				[
					1.076645649106922,
					-1.0766456491066947
				],
				[
					4.306582596426779,
					-1.0766456491066947
				],
				[
					7.536519543746181,
					-1.0766456491066947
				],
				[
					10.766456491066492,
					-2.153291298213162
				],
				[
					13.996393438385894,
					-2.153291298213162
				],
				[
					15.073039087492361,
					-2.153291298213162
				],
				[
					15.073039087492361,
					-1.0766456491066947
				],
				[
					12.919747789279427,
					1.0766456491066947
				],
				[
					10.766456491066492,
					4.306582596426324
				],
				[
					7.536519543746181,
					6.459873894639486
				],
				[
					4.306582596426779,
					8.613165192852875
				],
				[
					2.1532912982133894,
					9.689810841959343
				],
				[
					0,
					10.766456491066037
				],
				[
					-1.0766456491064673,
					10.766456491066037
				],
				[
					-2.1532912982129346,
					10.766456491066037
				],
				[
					-4.306582596425869,
					10.766456491066037
				],
				[
					-5.383228245532791,
					10.766456491066037
				],
				[
					-6.459873894639259,
					10.766456491066037
				],
				[
					-7.536519543746181,
					10.766456491066037
				],
				[
					-9.689810841959115,
					8.613165192852875
				],
				[
					-10.766456491065583,
					7.536519543746181
				],
				[
					-10.766456491065583,
					6.459873894639486
				],
				[
					-11.84310214017205,
					2.153291298213162
				],
				[
					-11.84310214017205,
					0
				],
				[
					-11.84310214017205,
					-1.0766456491066947
				],
				[
					-11.84310214017205,
					-3.2299369473198567
				],
				[
					-11.84310214017205,
					-4.306582596426324
				],
				[
					-9.689810841959115,
					-5.383228245533019
				],
				[
					-6.459873894639259,
					-7.536519543746181
				],
				[
					-4.306582596425869,
					-8.613165192852875
				],
				[
					-1.0766456491064673,
					-10.766456491066037
				],
				[
					1.076645649106922,
					-10.766456491066037
				],
				[
					2.1532912982133894,
					-10.766456491066037
				],
				[
					4.306582596426779,
					-10.766456491066037
				],
				[
					6.459873894639713,
					-10.766456491066037
				],
				[
					7.536519543746181,
					-10.766456491066037
				],
				[
					7.536519543746181,
					-9.689810841959343
				],
				[
					8.613165192853103,
					-9.689810841959343
				],
				[
					9.68981084195957,
					-8.613165192852875
				],
				[
					10.766456491066492,
					-6.459873894639486
				],
				[
					10.766456491066492,
					-5.383228245533019
				],
				[
					11.84310214017296,
					-4.306582596426324
				],
				[
					11.84310214017296,
					-4.306582596426324
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 357,
			"versionNonce": 2104939475,
			"isDeleted": false,
			"id": "kB70gmGK",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3053.4628763771057,
			"y": 2090.503447654823,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1037.5189208984375,
			"height": 100,
			"seed": 1951714813,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704372825899,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "If we look at this matrix as a linear transformation we can see that its basis are how\nthe function curves in each dimension corresponding to each other dimension\nthe eigenvectors of this matrix are the actual principal axes and the eigen vectors are their degree of\ncurvature",
			"rawText": "If we look at this matrix as a linear transformation we can see that its basis are how\nthe function curves in each dimension corresponding to each other dimension\nthe eigenvectors of this matrix are the actual principal axes and the eigen vectors are their degree of\ncurvature",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If we look at this matrix as a linear transformation we can see that its basis are how\nthe function curves in each dimension corresponding to each other dimension\nthe eigenvectors of this matrix are the actual principal axes and the eigen vectors are their degree of\ncurvature",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "image",
			"version": 195,
			"versionNonce": 1982704046,
			"isDeleted": true,
			"id": "o_-jEBqnXNWydtkZHHbhi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -208.59782199677466,
			"y": -141.09293686895253,
			"strokeColor": "#ffffff",
			"backgroundColor": "transparent",
			"width": 306,
			"height": 132,
			"seed": 674266910,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708115512248,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e726528bee98096ae7651e655f61e359b2089840",
			"scale": [
				1,
				1
			]
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#131313",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 4,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 3063.1338689500217,
		"scrollY": -67.62249253657461,
		"zoom": {
			"value": 0.3803062174639487
		},
		"currentItemRoundness": "sharp",
		"gridSize": null,
		"gridColor": {
			"Bold": "#494949FF",
			"Regular": "#252525FF"
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