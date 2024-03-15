---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - MachineLearning
---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Maximum Liklihood ^VYzPA6gh

%%***>>>text element-link:[[Bayes Decision Theory]]<<<***%%Bayes decision theory is based off of the assumption that
we know the liklihood distribution and the prior information
This is not always the case!!
Perhaps we should find a way to estimate it :]  ^EAbNijDh

This is often quite difficult to do because we do not know what
distribution our data is in and we have finitely many samples
to use in order to preform the estimation! ^JvTwIAdN

Let's assume our data is drawn from a multivariate normal distribution
which is classified mainly through the variances and the mean of such distribution
with out finite data we can try to estimate those 2 values that best
represent our data!  ^1vt6PMYJ

We want to find the parameter theta (mean and cov) that is the most likely to represent 
our data x meaning p(x | theta) is the highest
If this is applied to All datapoints x then we have
the maximum likelihood distribution representing our data!
 ^XT9VonGF

Notations and assumptions ^YTCtef93

D is a dataset composed of N samples
Xk is a sample of data from D with index k  ^YVQd7Lvk

We assume that the datapoints are i.i.d
and are drawn from the same density function 
p(x | theta) in order to fit our
central limit theorem! ^bPDvKL5f

Since datapoints are i.i.d
we can assume that  the joint density function
of all x's is their individual density multiplied ^hPgALQS9

How do we find the maximum? ^rrcfSbZE

Given a function that is: ^jPwaPtOp

Continuously differentiable

and

Concave
 ^cnVbG749

We can solve this by finding a point where the gradient
is zero and such we would find the maximum value for this function

Mind you that theta can be any number of parameters
as such our gradient is
 ^BB554JnG

a differentiable function is a function whose derivative exists
at each point in its domain (has no vertical tangent line). 
A differentiable function does not contain any break, angle, or cusp

Dont forget it also has to be continuous! ^6UHWVQ4c

That way we dont head towards a minimum instead of a maximum ^fxxIXkb4

As our first example we take the standard
Normal distribution with an unknown mean and a unit constant variance ^pr2M1oRp

p is not concave! we need to transform it into a concave function
and keep the value of the argmax as it is! ^PJNyL6xf

Lets proceed by finding the derivative ^6NGBI53U

This is quite intuitive as it says that our best mean is
the empirical mean of our samples ^qUjlmof9

Lets try this with the multivariate version! ^rK9o6Cpn

Assuming that the covariance is fixed, this function is concave! ^dlqWj6JG

how do we know so? ^qXBXAxTq

if the second derivative of a function
is negative definite then it is always
concave ^AXIqRNKf

The first part of the function is a negative constant
the second part is a function for which we can find
the second derivative of which results in the minus of
the covariance matrix which is negative definite!
the sum of two negative definite functions is negative definite! ^nDC6TIjq

What is positive/negative definite? ^VYTGeCca

we can tell from the structure
of the covariance matrix that its positive definite! ^A1j0gEB8

A square matrix is positive definite if
multiplying it with any vector from both sides
always gives a positive number as a result, 
independently of how we choose the vector
and vice versa ^SOtN8YUh

-1 ^8R1JcNPx

-1 ^V4YfN4px

-1 ^S5uMDX8N

What next? ^fKy3AQFK

Now that we know our distribution parameters representing our data
with the assumption its Gaussian, We can build an optimal classifier
using bayes decision theory and our estimated distribution! ^dih83zQX

Whats the process of
building a classifier like? ^mpmFnc6E

Given Two possible classes w1 and w2 such that they're equally to occur in the wild P(w1) = P(w2) = 0.5
it is known that the data generation distribution is of the shape 
Our Current dataset contains {  ,   ,   ,    ,   ,   } such that the green points belong to class 1
and the red points belong to class 2

In order to build our classifier we need to identify our data generating distribution (Likelihood)
by estimating its most likely parameters from our dataset ^lF20IkkL

Example ^AdyDsb6z

0         2 ^OGjFFw5n

1   0      2   0 ^Zimlriq7

Turn it concave and find maximum ^pJQrKr0i

Turn it concave and find maximum ^fin3tyB2


# Embedded files
6661b23942bededd2c4121143ba0cb957325b014: $$log p (D|\theta) = \sum_i ( - \frac{1}{2} 2 (x_k - \theta)(-1)) = 0$$
c5ec327d3faca5caa4a7cb93a6bae3705d0897a8: $$\sum_i (x_k) = N \theta$$
4aaa64297bfc288b20f6eb61d3905d118bd42f96: $$\frac{1}{N}\sum_i (x_k) = \theta$$
576090472a3a408bf038a6644c2d1202d59ebe7d: $$log p (D | \theta) = \sum_{k=1}^N 0 + \sum (x_k - \mu) = 0$$
e8fce304b5456e1524c9ce50ef639adab54c08fe: $$\sum_{k=1}^N \sum x_k = \sum_{k=1}^N \sum \mu$$
7e7f770dfad5cde1fc5cc52f628f25cacf072d4c: $$\frac{1}{N} \sum_{k=1}^N  x_k = \mu$$
4c5aaf7d4b581b380debc6ba9ccdf643071a4cc5: $$(1 - \theta_i)^k \theta_i$$
5ba0b960246bd0516aad17f188c68bd1f54386a4: $$P(D_1 | \theta_1) = \Pi_{x \in D_1} P(x=k | \theta_1) =\Pi_{x \in D_1} (1- \theta_1)^k \theta_1$$
63708e6185b9f9dbb2c1e094191bded40d6debe8: $$\color{green} \theta_1 ^2 (1-\theta_1)^2$$
657d578be398a4756c1ab056700ce1eebe652285: $$P(D_2 | \theta_2) = \Pi_{x \in D_2} P(x=k | \theta_2) =\Pi_{x \in D_2} (1- \theta_2)^k \theta_2$$
cd601c0365f16d6ec67edf9aec1663494551183a: $$\color{red} \theta_2 ^4 (1-\theta_2)^3$$
f9486515180c037244c5673a630208120e8da8c6: $$\color{green} 2log\theta_1 + 2log(1-\theta_1)$$
75ff53dc20a5d5aa6563518069741cefc159f63c: $$\color{green} \frac{\partial p(D1|\theta1)} {\partial \theta_1} = \frac{2}{\theta_1} + \frac{-2}{(1-\theta_1)} = 0$$
b2c21c2620d792891d6d51d302c55517b83d7872: $$\color{green} \theta_1 = \frac{1}{2}$$
6299a2b68dc5b3001bb03bc9f304856d602394f1: $$\color{red} 4log\theta_2 + 3log(1-\theta_2)$$
5af5f17626c1476f966f682943bac16ce878d902: $$\color{red} \frac{\partial p(D_2|\theta2)} {\partial \theta_2} = \frac{4}{\theta_2} + \frac{-3}{(1-\theta_2)} = 0$$
9dd3ea07d0dd3e73b4dd28775dda6105c87f3ac3: $$\color{red} \theta_2 = \frac{4}{7}$$
550c29b4e6b1a47143145ed5579ab30411d12c26: $$\arg\max_j p(x|w_j) p(w_j) \begin{cases}
w_1 \text{ if } \frac{1}{2}^x\frac{1}{2} \cdot \frac{1}{2}> \frac{3}{7}^x\frac{4}{7}\cdot \frac{1}{2} \\
w_2 \text{ if } \frac{1}{2}^x\frac{1}{2} \cdot \frac{1}{2}< \frac{3}{7}^x\frac{4}{7} \cdot \frac{1}{2}\\ 
\end{cases}$$
2d284656f48d8919df3825786734a6acb5c04bdb: [[Pasted Image 20231225160721_257.png]]
4dabf3cb8ed0a28d321d027a756bd4e00922f0a5: [[Pasted Image 20231225160906_276.png]]
3665df99c87e0502e88d820d917582bff39319c4: [[Pasted Image 20231225161303_306.png]]
a7025a742a7029b0a403e94f0e371079da5e2bc0: [[Pasted Image 20231225161420_379.png]]
0c0b49a568ddf3cd7fe20b21ad32abec67da68b7: [[Pasted Image 20231225162048_438.png]]
3c717a38b9ca7293c3567b512d14dfd5b5ce2b17: [[Pasted Image 20231225162148_455.png]]
5c9ae05d0b40e4d415b8bd4ff3fa05e6ac37c892: [[Pasted Image 20231225162306_472.png]]
52af72bc844093f1dee4af08f5b7cdf0be08a171: [[Pasted Image 20231225162321_481.png]]
4d7dbc1363411903a18c49d7a68ddcae4fc8f87a: [[Pasted Image 20231225164206_546.png]]
8d05b02d3c246f780b19446730f781dca4badd2c: [[Pasted Image 20231225164555_389.png]]
6d66490a4905ab0f75e49774ab2408e6f56202e2: [[Pasted Image 20231225170155_616.png]]
afa3397e57b25f26bcaafdbd387913082fe9503c: [[Pasted Image 20231227101732_011.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.22",
	"elements": [
		{
			"type": "ellipse",
			"version": 149,
			"versionNonce": 877603414,
			"isDeleted": false,
			"id": "nhHQi752EalCV6-Cmg9cZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -194.65725727828385,
			"y": -432.2474127806879,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 369,
			"height": 162,
			"seed": 1346010768,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "VYzPA6gh"
				}
			],
			"updated": 1708696476686,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 108,
			"versionNonce": 1531956746,
			"isDeleted": false,
			"id": "VYzPA6gh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -129.20295395163546,
			"y": -368.52306205679827,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 238.1689910888672,
			"height": 35,
			"seed": 761134736,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Maximum Liklihood",
			"rawText": "Maximum Liklihood",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "nhHQi752EalCV6-Cmg9cZ",
			"originalText": "Maximum Liklihood",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 277,
			"versionNonce": 484667286,
			"isDeleted": false,
			"id": "EAbNijDh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -283.2555329979609,
			"y": -233.99641097111464,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 588.8593139648438,
			"height": 100,
			"seed": 1795661968,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476686,
			"link": "[[Bayes Decision Theory]]",
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Bayes decision theory is based off of the assumption that\nwe know the liklihood distribution and the prior information\nThis is not always the case!!\nPerhaps we should find a way to estimate it :] ",
			"rawText": "Bayes decision theory is based off of the assumption that\nwe know the liklihood distribution and the prior information\nThis is not always the case!!\nPerhaps we should find a way to estimate it :] ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bayes decision theory is based off of the assumption that\nwe know the liklihood distribution and the prior information\nThis is not always the case!!\nPerhaps we should find a way to estimate it :] ",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 261,
			"versionNonce": 687701194,
			"isDeleted": false,
			"id": "JvTwIAdN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -255.52106188417713,
			"y": -133.87087615623255,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 515.2649536132812,
			"height": 60,
			"seed": 1520388720,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Gg7yax8fhcb7zktmN9NmE",
					"type": "arrow"
				}
			],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is often quite difficult to do because we do not know what\ndistribution our data is in and we have finitely many samples\nto use in order to preform the estimation!",
			"rawText": "This is often quite difficult to do because we do not know what\ndistribution our data is in and we have finitely many samples\nto use in order to preform the estimation!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is often quite difficult to do because we do not know what\ndistribution our data is in and we have finitely many samples\nto use in order to preform the estimation!",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 252,
			"versionNonce": 222104790,
			"isDeleted": false,
			"id": "Gg7yax8fhcb7zktmN9NmE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 9.58225735688966,
			"y": -63.45818971743262,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 0.8512388380696478,
			"height": 92.9319994872435,
			"seed": 1114911856,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "JvTwIAdN",
				"focus": -0.02753187279204229,
				"gap": 10.412686438799938
			},
			"endBinding": {
				"elementId": "1vt6PMYJ",
				"focus": -0.013985691690884877,
				"gap": 12.885273860180376
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
					0.8512388380696478,
					92.9319994872435
				]
			]
		},
		{
			"type": "text",
			"version": 290,
			"versionNonce": 981947274,
			"isDeleted": false,
			"id": "1vt6PMYJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -386.6333492169334,
			"y": 42.35908362999126,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 806.5791015625,
			"height": 100,
			"seed": 314260080,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Gg7yax8fhcb7zktmN9NmE",
					"type": "arrow"
				},
				{
					"id": "dTRbfd-noFjfe7gdRPZpt",
					"type": "arrow"
				}
			],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Let's assume our data is drawn from a multivariate normal distribution\nwhich is classified mainly through the variances and the mean of such distribution\nwith out finite data we can try to estimate those 2 values that best\nrepresent our data! ",
			"rawText": "Let's assume our data is drawn from a multivariate normal distribution\nwhich is classified mainly through the variances and the mean of such distribution\nwith out finite data we can try to estimate those 2 values that best\nrepresent our data! ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Let's assume our data is drawn from a multivariate normal distribution\nwhich is classified mainly through the variances and the mean of such distribution\nwith out finite data we can try to estimate those 2 values that best\nrepresent our data! ",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 54,
			"versionNonce": 317784598,
			"isDeleted": false,
			"id": "dTRbfd-noFjfe7gdRPZpt",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 9.115860796019888,
			"y": 154.33555768832161,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 3.3741814213612997,
			"height": 119.22107688810047,
			"seed": 269304944,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "1vt6PMYJ",
				"focus": 0.022965864199841292,
				"gap": 11.976474058330354
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
					3.3741814213612997,
					119.22107688810047
				]
			]
		},
		{
			"type": "text",
			"version": 294,
			"versionNonce": 304632394,
			"isDeleted": false,
			"id": "XT9VonGF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -448.2384195670901,
			"y": 305.04899450912785,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 912.4591064453125,
			"height": 125,
			"seed": 481465968,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "uD4HQ8h6x-DQ6gh82eJOc",
					"type": "arrow"
				}
			],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We want to find the parameter theta (mean and cov) that is the most likely to represent \nour data x meaning p(x | theta) is the highest\nIf this is applied to All datapoints x then we have\nthe maximum likelihood distribution representing our data!\n",
			"rawText": "We want to find the parameter theta (mean and cov) that is the most likely to represent \nour data x meaning p(x | theta) is the highest\nIf this is applied to All datapoints x then we have\nthe maximum likelihood distribution representing our data!\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We want to find the parameter theta (mean and cov) that is the most likely to represent \nour data x meaning p(x | theta) is the highest\nIf this is applied to All datapoints x then we have\nthe maximum likelihood distribution representing our data!\n",
			"lineHeight": 1.25,
			"baseline": 118
		},
		{
			"type": "line",
			"version": 194,
			"versionNonce": 1089752918,
			"isDeleted": false,
			"id": "Y0i0AhpRc7BPq7tYeqgT6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -318.1410028451627,
			"y": 394.6686026586928,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 314.26519746432484,
			"height": 255.82289758499422,
			"seed": 326208112,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-151.0678317635526,
					-15.437588647370319
				],
				[
					-205.0993920293488,
					-240.38530893762385
				],
				[
					-314.26519746432484,
					-255.82289758499422
				]
			]
		},
		{
			"type": "text",
			"version": 178,
			"versionNonce": 851147018,
			"isDeleted": false,
			"id": "YTCtef93",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -949.9905723400348,
			"y": 79.81708427692949,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 265.5196838378906,
			"height": 25,
			"seed": 932874864,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Notations and assumptions",
			"rawText": "Notations and assumptions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Notations and assumptions",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 211,
			"versionNonce": 60552342,
			"isDeleted": false,
			"id": "YVQd7Lvk",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1000.0975029377305,
			"y": 110.40675600521533,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 356.62481689453125,
			"height": 40,
			"seed": 1553823888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "D is a dataset composed of N samples\nXk is a sample of data from D with index k ",
			"rawText": "D is a dataset composed of N samples\nXk is a sample of data from D with index k ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "D is a dataset composed of N samples\nXk is a sample of data from D with index k ",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 300,
			"versionNonce": 196855754,
			"isDeleted": false,
			"id": "bPDvKL5f",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1007.1835050647487,
			"y": 152.0986774224448,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 374.32073974609375,
			"height": 80,
			"seed": 2062432400,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We assume that the datapoints are i.i.d\nand are drawn from the same density function \np(x | theta) in order to fit our\ncentral limit theorem!",
			"rawText": "We assume that the datapoints are i.i.d\nand are drawn from the same density function \np(x | theta) in order to fit our\ncentral limit theorem!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We assume that the datapoints are i.i.d\nand are drawn from the same density function \np(x | theta) in order to fit our\ncentral limit theorem!",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "line",
			"version": 118,
			"versionNonce": 1956442582,
			"isDeleted": false,
			"id": "y5EW6C1n8hrWjEm6GdykV",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1001.5049429643309,
			"y": 208.48137498287286,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 159.4573165380857,
			"height": 44.04898246908442,
			"seed": 581790832,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-46.69192141722942,
					40.52506387155768
				],
				[
					-159.4573165380857,
					-3.5239185975267446
				]
			]
		},
		{
			"type": "text",
			"version": 284,
			"versionNonce": 1698971274,
			"isDeleted": false,
			"id": "hPgALQS9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1490.1593903663775,
			"y": 131.83614548666597,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 376.48077392578125,
			"height": 60,
			"seed": 224421008,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Since datapoints are i.i.d\nwe can assume that  the joint density function\nof all x's is their individual density multiplied",
			"rawText": "Since datapoints are i.i.d\nwe can assume that  the joint density function\nof all x's is their individual density multiplied",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Since datapoints are i.i.d\nwe can assume that  the joint density function\nof all x's is their individual density multiplied",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 125,
			"versionNonce": 789333782,
			"isDeleted": false,
			"id": "FSE7w8J8REEEBDg9HulGn",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1390.5363058430587,
			"y": 195.270254286061,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 205.42595365935782,
			"height": 65.87797824248372,
			"seed": 2061053552,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2d284656f48d8919df3825786734a6acb5c04bdb",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 32,
			"versionNonce": 1276108106,
			"isDeleted": false,
			"id": "J8V1U378p82vbxrscLwHU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -106.87777574095162,
			"y": 414.8822060492249,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 263,
			"height": 56,
			"seed": 1191142000,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4dabf3cb8ed0a28d321d027a756bd4e00922f0a5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 144,
			"versionNonce": 593425494,
			"isDeleted": false,
			"id": "uD4HQ8h6x-DQ6gh82eJOc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 293.6467351972843,
			"y": 448.7905642992504,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 473.14857336815015,
			"height": 375.3906036639868,
			"seed": 2072724592,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "XT9VonGF",
				"focus": 1.0407979711016568,
				"gap": 18.741569790122526
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
					289.3635903243232,
					-24.765352325054664
				],
				[
					284.14983194010114,
					-337.590855378377
				],
				[
					473.14857336815015,
					-375.3906036639868
				]
			]
		},
		{
			"type": "text",
			"version": 78,
			"versionNonce": 2105123850,
			"isDeleted": false,
			"id": "rrcfSbZE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 804.460133953907,
			"y": 59.16900427076399,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 284.419677734375,
			"height": 25,
			"seed": 1762050160,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How do we find the maximum?",
			"rawText": "How do we find the maximum?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How do we find the maximum?",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 121,
			"versionNonce": 1802107286,
			"isDeleted": false,
			"id": "jPwaPtOp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 843.7492350126221,
			"y": 144.48141367993173,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 197.3604278564453,
			"height": 20,
			"seed": 1746738800,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Given a function that is:",
			"rawText": "Given a function that is:",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given a function that is:",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 158,
			"versionNonce": 1400672970,
			"isDeleted": false,
			"id": "cnVbG749",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 840.6275645528167,
			"y": 167.29534320616824,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 206.4164276123047,
			"height": 120,
			"seed": 607661680,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476686,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Continuously differentiable\n\nand\n\nConcave\n",
			"rawText": "Continuously differentiable\n\nand\n\nConcave\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Continuously differentiable\n\nand\n\nConcave\n",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "text",
			"version": 316,
			"versionNonce": 509761238,
			"isDeleted": false,
			"id": "BB554JnG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 693.9671940229442,
			"y": 270.6605554383008,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 533.4890747070312,
			"height": 120,
			"seed": 2052150896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "We can solve this by finding a point where the gradient\nis zero and such we would find the maximum value for this function\n\nMind you that theta can be any number of parameters\nas such our gradient is\n",
			"rawText": "We can solve this by finding a point where the gradient\nis zero and such we would find the maximum value for this function\n\nMind you that theta can be any number of parameters\nas such our gradient is\n",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We can solve this by finding a point where the gradient\nis zero and such we would find the maximum value for this function\n\nMind you that theta can be any number of parameters\nas such our gradient is\n",
			"lineHeight": 1.25,
			"baseline": 114
		},
		{
			"type": "image",
			"version": 37,
			"versionNonce": 817080714,
			"isDeleted": false,
			"id": "JB_xGvXqAj-ChjtJd8oBq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 848.7130020664481,
			"y": 90.93264330792185,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 175.47909369473712,
			"height": 46.96838195546867,
			"seed": 900678768,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3665df99c87e0502e88d820d917582bff39319c4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 119,
			"versionNonce": 618466326,
			"isDeleted": false,
			"id": "PqjP7ghKiFzhffoX415ju",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 800.8778488145815,
			"y": 378.5554652427205,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 268.30376400633236,
			"height": 140.17761665579067,
			"seed": 393223312,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a7025a742a7029b0a403e94f0e371079da5e2bc0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 115,
			"versionNonce": 1817831498,
			"isDeleted": false,
			"id": "jemDWVWVK1fzLg_MsSYPW",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1059.779404883514,
			"y": 175.8856397374247,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 275.43768318752836,
			"height": 235.37402017843348,
			"seed": 1024109168,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					185.29444141706472,
					-23.036606230229665
				],
				[
					188.2992161427469,
					-199.31672347024795
				],
				[
					275.43768318752836,
					-235.37402017843348
				]
			]
		},
		{
			"type": "text",
			"version": 215,
			"versionNonce": 214899030,
			"isDeleted": false,
			"id": "6UHWVQ4c",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1315.3312506317286,
			"y": -92.54090242351222,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 536.5610961914062,
			"height": 100,
			"seed": 1664969840,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "a differentiable function is a function whose derivative exists\nat each point in its domain (has no vertical tangent line). \nA differentiable function does not contain any break, angle, or cusp\n\nDont forget it also has to be continuous!",
			"rawText": "a differentiable function is a function whose derivative exists\nat each point in its domain (has no vertical tangent line). \nA differentiable function does not contain any break, angle, or cusp\n\nDont forget it also has to be continuous!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "a differentiable function is a function whose derivative exists\nat each point in its domain (has no vertical tangent line). \nA differentiable function does not contain any break, angle, or cusp\n\nDont forget it also has to be continuous!",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "line",
			"version": 105,
			"versionNonce": 1045057290,
			"isDeleted": false,
			"id": "R1rVP6zocyVNMQSUFAuDe",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 985.661628316688,
			"y": 256.01296575561486,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 533.8483095961916,
			"height": 171.27215936388143,
			"seed": 2091984016,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					429.68278577254443,
					-11.017507327501221
				],
				[
					441.70188467527316,
					-167.2657930629719
				],
				[
					533.8483095961916,
					-171.27215936388143
				]
			]
		},
		{
			"type": "text",
			"version": 143,
			"versionNonce": 1569554070,
			"isDeleted": false,
			"id": "fxxIXkb4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1535.6446472459484,
			"y": 79.73284851559657,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 520.609130859375,
			"height": 20,
			"seed": 1954690160,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "That way we dont head towards a minimum instead of a maximum",
			"rawText": "That way we dont head towards a minimum instead of a maximum",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "That way we dont head towards a minimum instead of a maximum",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 248,
			"versionNonce": 721411530,
			"isDeleted": false,
			"id": "pr2M1oRp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -984.697720934066,
			"y": 560.8628478368402,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 702.2392578125,
			"height": 50,
			"seed": 702283888,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "As our first example we take the standard\nNormal distribution with an unknown mean and a unit constant variance",
			"rawText": "As our first example we take the standard\nNormal distribution with an unknown mean and a unit constant variance",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "As our first example we take the standard\nNormal distribution with an unknown mean and a unit constant variance",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 178,
			"versionNonce": 1808612310,
			"isDeleted": false,
			"id": "n_j7e3ZLUENP_npyC06bi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -802.3308481430747,
			"y": 620.3887062083941,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 347.3640763608462,
			"height": 67.94873157332823,
			"seed": 1790322320,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0c0b49a568ddf3cd7fe20b21ad32abec67da68b7",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 264,
			"versionNonce": 1872073866,
			"isDeleted": false,
			"id": "PJNyL6xf",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -907.5427429726523,
			"y": 686.4241583750622,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 526.8010864257812,
			"height": 40,
			"seed": 2089410192,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "p is not concave! we need to transform it into a concave function\nand keep the value of the argmax as it is!",
			"rawText": "p is not concave! we need to transform it into a concave function\nand keep the value of the argmax as it is!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "p is not concave! we need to transform it into a concave function\nand keep the value of the argmax as it is!",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 258,
			"versionNonce": 765677846,
			"isDeleted": false,
			"id": "VYJ3ZODX6reTR_ztGgf-C",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -844.8028242626334,
			"y": 738.2716249672874,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 413.5114160398093,
			"height": 126.54599748977164,
			"seed": 1487660656,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "fl4zluKxDUnx8h33AlfSj",
					"type": "arrow"
				}
			],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3c717a38b9ca7293c3567b512d14dfd5b5ce2b17",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 218,
			"versionNonce": 1841722186,
			"isDeleted": false,
			"id": "aJuhCF6qtjgUFxXfV8bUD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1181.0053004222468,
			"y": 619.2110098094281,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 199.1801029190543,
			"height": 125.51738845750624,
			"seed": 396635280,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rofqTxu-wF14GgvrQZNPJ",
					"type": "arrow"
				}
			],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5c9ae05d0b40e4d415b8bd4ff3fa05e6ac37c892",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 251,
			"versionNonce": 243580502,
			"isDeleted": false,
			"id": "VInkabGjjavVBR1HaL-FT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1165.4799001463716,
			"y": 784.8513353310591,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 175.69429869162295,
			"height": 125.95227646464397,
			"seed": 673909360,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rofqTxu-wF14GgvrQZNPJ",
					"type": "arrow"
				}
			],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "52af72bc844093f1dee4af08f5b7cdf0be08a171",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 376,
			"versionNonce": 401439242,
			"isDeleted": false,
			"id": "rofqTxu-wF14GgvrQZNPJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1067.365970074698,
			"y": 749.7772614637596,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 1.0807137606170727,
			"height": 30.800342177586458,
			"seed": 99211408,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "aJuhCF6qtjgUFxXfV8bUD",
				"focus": -0.11464607858985137,
				"gap": 5.048863196825209
			},
			"endBinding": {
				"elementId": "VInkabGjjavVBR1HaL-FT",
				"focus": 0.15220542146129146,
				"gap": 4.273731689713031
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
					1.0807137606170727,
					30.800342177586458
				]
			]
		},
		{
			"type": "arrow",
			"version": 63,
			"versionNonce": 1128694678,
			"isDeleted": false,
			"id": "fl4zluKxDUnx8h33AlfSj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -694.1010267306684,
			"y": 893.1741523857851,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.1534144775567938,
			"height": 153.4041255150604,
			"seed": 519060080,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "VYJ3ZODX6reTR_ztGgf-C",
				"focus": 0.2738139202422724,
				"gap": 28.356529928726047
			},
			"endBinding": {
				"elementId": "NRyB7aed",
				"focus": -0.0968252420268972,
				"gap": 12.555190072784626
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
					1.1534144775567938,
					153.4041255150604
				]
			]
		},
		{
			"type": "text",
			"version": 97,
			"versionNonce": 1560651978,
			"isDeleted": false,
			"id": "6NGBI53U",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -677.7376592232249,
			"y": 930.0834156676042,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 299.4566345214844,
			"height": 20,
			"seed": 239694448,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Lets proceed by finding the derivative",
			"rawText": "Lets proceed by finding the derivative",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets proceed by finding the derivative",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 56,
			"versionNonce": 505258198,
			"isDeleted": false,
			"id": "YAHd_XxjzBMQswuYfkH8O",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -637.4518420612908,
			"y": 953.0153972209793,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 201.35854823857574,
			"height": 34.561541861845086,
			"seed": 798911632,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4d7dbc1363411903a18c49d7a68ddcae4fc8f87a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 69,
			"versionNonce": 346685322,
			"isDeleted": false,
			"id": "NRyB7aed",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -822.285607163941,
			"y": 1059.13346797363,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 287,
			"height": 42,
			"seed": 1728,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "fl4zluKxDUnx8h33AlfSj",
					"type": "arrow"
				}
			],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6661b23942bededd2c4121143ba0cb957325b014",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 67,
			"versionNonce": 1654593046,
			"isDeleted": false,
			"id": "Y74-qNxOdmlHj1qqHKnzU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -846.692434403844,
			"y": 1066.1237134260239,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 24.31861836966123,
			"height": 21.837126699287634,
			"seed": 1145560688,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8d05b02d3c246f780b19446730f781dca4badd2c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 118,
			"versionNonce": 1796570698,
			"isDeleted": false,
			"id": "UfkHb74u",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -731.5448532375751,
			"y": 1109.0666114339622,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 99,
			"height": 36,
			"seed": 85586,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c5ec327d3faca5caa4a7cb93a6bae3705d0897a8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 63,
			"versionNonce": 432005974,
			"isDeleted": false,
			"id": "yGHkgAkG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -735.8930040228483,
			"y": 1151.0442072501135,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 109,
			"height": 42,
			"seed": 58929,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4aaa64297bfc288b20f6eb61d3905d118bd42f96",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 137,
			"versionNonce": 1294148874,
			"isDeleted": false,
			"id": "qUjlmof9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -911.4105130898594,
			"y": 1195.3312679232665,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 447.31298828125,
			"height": 40,
			"seed": 794521712,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "This is quite intuitive as it says that our best mean is\nthe empirical mean of our samples",
			"rawText": "This is quite intuitive as it says that our best mean is\nthe empirical mean of our samples",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "This is quite intuitive as it says that our best mean is\nthe empirical mean of our samples",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 210,
			"versionNonce": 1708460182,
			"isDeleted": false,
			"id": "0fzcSe8nJHdZFO_FBt-kP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -486.22598140536786,
			"y": 1149.1426052610375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 433.75412207516786,
			"height": 561.2473464550894,
			"seed": 1984046736,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476687,
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
					307.6466936124194,
					-1.3857959171730272
				],
				[
					309.03248952959245,
					-498.8865301823017
				],
				[
					433.75412207516786,
					-561.2473464550894
				]
			]
		},
		{
			"type": "text",
			"version": 100,
			"versionNonce": 1414394826,
			"isDeleted": false,
			"id": "rK9o6Cpn",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -34.42790537696192,
			"y": 572.9230955513905,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 429.5395202636719,
			"height": 25,
			"seed": 88384112,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lets try this with the multivariate version!",
			"rawText": "Lets try this with the multivariate version!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lets try this with the multivariate version!",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 93,
			"versionNonce": 1452508630,
			"isDeleted": false,
			"id": "ZElZrgBnztGM87jSfqWsc",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -71.17741068739701,
			"y": 607.4422278248726,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 516.896490056273,
			"height": 59.32633707605575,
			"seed": 1992516208,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6d66490a4905ab0f75e49774ab2408e6f56202e2",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 115,
			"versionNonce": 850455178,
			"isDeleted": false,
			"id": "dlqWj6JG",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -72.1896453708834,
			"y": 666.1743159523525,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 503.61700439453125,
			"height": 20,
			"seed": 323811984,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "kXjpKqCLtAefGFxaEqlTI",
					"type": "arrow"
				}
			],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Assuming that the covariance is fixed, this function is concave!",
			"rawText": "Assuming that the covariance is fixed, this function is concave!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assuming that the covariance is fixed, this function is concave!",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 112,
			"versionNonce": 1024482070,
			"isDeleted": false,
			"id": "kXjpKqCLtAefGFxaEqlTI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 443.21223536434803,
			"y": 679.129302316142,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 189.7528881331935,
			"height": 72.12326969768446,
			"seed": 18295952,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "dlqWj6JG",
				"focus": 1.0036147920752432,
				"gap": 11.78487634070018
			},
			"endBinding": {
				"elementId": "AXIqRNKf",
				"focus": -0.6335858055374305,
				"gap": 14.156868300343604
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
					110.7607356071581,
					-72.12326969768446
				],
				[
					189.7528881331935,
					-51.516621212631776
				]
			]
		},
		{
			"type": "text",
			"version": 34,
			"versionNonce": 520554826,
			"isDeleted": false,
			"id": "qXBXAxTq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 5.949763113119044,
			"x": 464.1656693060436,
			"y": 571.8030081231592,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 153.85629272460938,
			"height": 20,
			"seed": 1895644272,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "how do we know so?",
			"rawText": "how do we know so?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "how do we know so?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 154,
			"versionNonce": 2143324246,
			"isDeleted": false,
			"id": "AXIqRNKf",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 647.1219917978851,
			"y": 596.7027083759313,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 301.39263916015625,
			"height": 60,
			"seed": 953729680,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "kXjpKqCLtAefGFxaEqlTI",
					"type": "arrow"
				}
			],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "if the second derivative of a function\nis negative definite then it is always\nconcave",
			"rawText": "if the second derivative of a function\nis negative definite then it is always\nconcave",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "if the second derivative of a function\nis negative definite then it is always\nconcave",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 388,
			"versionNonce": 1580685654,
			"isDeleted": false,
			"id": "nDC6TIjq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 559.3338820045163,
			"y": 654.2607113242407,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 501.7130126953125,
			"height": 100,
			"seed": 2125667952,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "pS4ASA2EfvU5yYQSPdG3e",
					"type": "arrow"
				}
			],
			"updated": 1708707029347,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "The first part of the function is a negative constant\nthe second part is a function for which we can find\nthe second derivative of which results in the minus of\nthe covariance matrix which is negative definite!\nthe sum of two negative definite functions is negative definite!",
			"rawText": "The first part of the function is a negative constant\nthe second part is a function for which we can find\nthe second derivative of which results in the minus of\nthe covariance matrix which is negative definite!\nthe sum of two negative definite functions is negative definite!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The first part of the function is a negative constant\nthe second part is a function for which we can find\nthe second derivative of which results in the minus of\nthe covariance matrix which is negative definite!\nthe sum of two negative definite functions is negative definite!",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "arrow",
			"version": 262,
			"versionNonce": 1878491914,
			"isDeleted": false,
			"id": "RPyl0kaakCU3IVkAVUyuI",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1020.1983929458236,
			"y": 726.3528717610544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 243.6031201385099,
			"height": 113.07074597904978,
			"seed": 1406400624,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708717357466,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "SOtN8YUh",
				"focus": 0.8164336153131606,
				"gap": 15.782098561834573
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
					95.30574924336861,
					-18.889427777964897
				],
				[
					104.75046313235111,
					-104.75046313235123
				],
				[
					243.6031201385099,
					-113.07074597904978
				]
			]
		},
		{
			"type": "text",
			"version": 69,
			"versionNonce": 462995146,
			"isDeleted": false,
			"id": "VYTGeCca",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1002.5423346255013,
			"y": 572.6616184767031,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 272.28857421875,
			"height": 20,
			"seed": 1611442832,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What is positive/negative definite?",
			"rawText": "What is positive/negative definite?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What is positive/negative definite?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 96,
			"versionNonce": 1475198614,
			"isDeleted": false,
			"id": "pS4ASA2EfvU5yYQSPdG3e",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 929.3252969362809,
			"y": 770.7797575377148,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 160.42053464659557,
			"height": 95.52660185098921,
			"seed": 320523888,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708707029348,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "nDC6TIjq",
				"focus": -0.3231849260507069,
				"gap": 16.5190462134741
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
					42.79091621108637,
					92.95077079035764
				],
				[
					160.42053464659557,
					95.52660185098921
				]
			]
		},
		{
			"type": "text",
			"version": 154,
			"versionNonce": 2087343498,
			"isDeleted": false,
			"id": "A1j0gEB8",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1013.7103294366932,
			"y": 854.28581443909,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 407.9368896484375,
			"height": 40,
			"seed": 1900206704,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476687,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "we can tell from the structure\nof the covariance matrix that its positive definite!",
			"rawText": "we can tell from the structure\nof the covariance matrix that its positive definite!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "we can tell from the structure\nof the covariance matrix that its positive definite!",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 206,
			"versionNonce": 2023595082,
			"isDeleted": false,
			"id": "SOtN8YUh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1279.583611646168,
			"y": 601.2045831074582,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 355.20074462890625,
			"height": 100,
			"seed": 755492496,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "RPyl0kaakCU3IVkAVUyuI",
					"type": "arrow"
				}
			],
			"updated": 1708717357465,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "A square matrix is positive definite if\nmultiplying it with any vector from both sides\nalways gives a positive number as a result, \nindependently of how we choose the vector\nand vice versa",
			"rawText": "A square matrix is positive definite if\nmultiplying it with any vector from both sides\nalways gives a positive number as a result, \nindependently of how we choose the vector\nand vice versa",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A square matrix is positive definite if\nmultiplying it with any vector from both sides\nalways gives a positive number as a result, \nindependently of how we choose the vector\nand vice versa",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "image",
			"version": 91,
			"versionNonce": 1683690570,
			"isDeleted": false,
			"id": "3zKxcaav",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 60.96549872357639,
			"y": 696.6324199215455,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 245.01020386914502,
			"height": 46.93682066458717,
			"seed": 88832,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476688,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "576090472a3a408bf038a6644c2d1202d59ebe7d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 1908845910,
			"isDeleted": false,
			"id": "8R1JcNPx",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 220.66092003023084,
			"y": 690.6236984375955,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 10.912033081054688,
			"height": 20,
			"seed": 1113422480,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476688,
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
			"type": "image",
			"version": 95,
			"versionNonce": 1967520522,
			"isDeleted": false,
			"id": "iHDajJxEWbrOwzFwSU3ru",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 30.527688609741062,
			"y": 706.8527660268271,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 24.31861836966123,
			"height": 21.837126699287634,
			"seed": 1168258672,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476688,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "8d05b02d3c246f780b19446730f781dca4badd2c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 84,
			"versionNonce": 1718784662,
			"isDeleted": false,
			"id": "u1b5QOuw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 139.92136072581619,
			"y": 743.8384595355776,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 156,
			"height": 50,
			"seed": 34489,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476688,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e8fce304b5456e1524c9ce50ef639adab54c08fe",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 66,
			"versionNonce": 2127830538,
			"isDeleted": false,
			"id": "4m7xlwOZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 136.33399629197834,
			"y": 797.5601651408247,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 101,
			"height": 50,
			"seed": 90556,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "PengzOokAfKIxT6WRfZK1",
					"type": "arrow"
				}
			],
			"updated": 1708707005470,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7e7f770dfad5cde1fc5cc52f628f25cacf072d4c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 57,
			"versionNonce": 1055903702,
			"isDeleted": false,
			"id": "V4YfN4px",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 192.48360875746062,
			"y": 740.7972209013165,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 10.912033081054688,
			"height": 20,
			"seed": 2006041712,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476688,
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
			"version": 57,
			"versionNonce": 1150697610,
			"isDeleted": false,
			"id": "S5uMDX8N",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 282.340292508538,
			"y": 740.7972209013165,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 10.912033081054688,
			"height": 20,
			"seed": 606067344,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476688,
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
			"type": "arrow",
			"version": 82,
			"versionNonce": 659776790,
			"isDeleted": false,
			"id": "6r--DxiZpW339Yog1vIrK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -124.24354695068303,
			"y": 489.45428042776837,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 217.54181906558256,
			"height": 51.73967588586822,
			"seed": 64010896,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476688,
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
					-217.54181906558256,
					51.73967588586822
				]
			]
		},
		{
			"type": "arrow",
			"version": 63,
			"versionNonce": 902930250,
			"isDeleted": false,
			"id": "nq2XRSq4O_o-XcQpXczFA",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 191.19503106543084,
			"y": 878.3599820938529,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.175901724678738,
			"height": 186.9683742239332,
			"seed": 1824074896,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708696476688,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "dih83zQX",
				"focus": 0.0009336948151765863,
				"gap": 10.583115522109438
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
					1.175901724678738,
					186.9683742239332
				]
			]
		},
		{
			"type": "text",
			"version": 17,
			"versionNonce": 17977942,
			"isDeleted": false,
			"id": "fKy3AQFK",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 198.302611614385,
			"y": 960.6731028213705,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 89.26419067382812,
			"height": 20,
			"seed": 615987312,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708696476688,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "What next?",
			"rawText": "What next?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "What next?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 238,
			"versionNonce": 1630851350,
			"isDeleted": false,
			"id": "dih83zQX",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -80.80564191692156,
			"y": 1075.9114718398955,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 546.3531494140625,
			"height": 60,
			"seed": 1828982896,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "nq2XRSq4O_o-XcQpXczFA",
					"type": "arrow"
				},
				{
					"id": "OOKztwP7pZcPa2rQTBEQF",
					"type": "arrow"
				}
			],
			"updated": 1708709198840,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Now that we know our distribution parameters representing our data\nwith the assumption its Gaussian, We can build an optimal classifier\nusing bayes decision theory and our estimated distribution!",
			"rawText": "Now that we know our distribution parameters representing our data\nwith the assumption its Gaussian, We can build an optimal classifier\nusing bayes decision theory and our estimated distribution!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Now that we know our distribution parameters representing our data\nwith the assumption its Gaussian, We can build an optimal classifier\nusing bayes decision theory and our estimated distribution!",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 391,
			"versionNonce": 2112973846,
			"isDeleted": false,
			"id": "Di5BDo8hi1ywx8hMd82nM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 319.731670620768,
			"y": 791.5236829005527,
			"strokeColor": "transparent",
			"backgroundColor": "#a5d8ff",
			"width": 256.8703503865957,
			"height": 65.92247930275465,
			"seed": 403128825,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707000840,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "afa3397e57b25f26bcaafdbd387913082fe9503c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 316,
			"versionNonce": 1172877130,
			"isDeleted": false,
			"id": "OOKztwP7pZcPa2rQTBEQF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 191.48048968764317,
			"y": 1145.294877809575,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 1.9351001473636131,
			"height": 197.98935392430462,
			"seed": 2047802954,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708707020783,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "dih83zQX",
				"focus": 0.004663648648121271,
				"gap": 9.383405969679416
			},
			"endBinding": {
				"elementId": "AdyDsb6z",
				"focus": 0.10252107308681699,
				"gap": 1
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
					1.9351001473636131,
					197.98935392430462
				]
			]
		},
		{
			"type": "text",
			"version": 210,
			"versionNonce": 482811606,
			"isDeleted": false,
			"id": "mpmFnc6E",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 205.29884182091564,
			"y": 1225.867227257572,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 190.1124267578125,
			"height": 40,
			"seed": 938862102,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Whats the process of\nbuilding a classifier like?",
			"rawText": "Whats the process of\nbuilding a classifier like?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Whats the process of\nbuilding a classifier like?",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 735,
			"versionNonce": 191419414,
			"isDeleted": false,
			"id": "lF20IkkL",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -225.623356254187,
			"y": 1374.8091745379927,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 835.2494506835938,
			"height": 140,
			"seed": 327121686,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Given Two possible classes w1 and w2 such that they're equally to occur in the wild P(w1) = P(w2) = 0.5\nit is known that the data generation distribution is of the shape \nOur Current dataset contains {  ,   ,   ,    ,   ,   } such that the green points belong to class 1\nand the red points belong to class 2\n\nIn order to build our classifier we need to identify our data generating distribution (Likelihood)\nby estimating its most likely parameters from our dataset",
			"rawText": "Given Two possible classes w1 and w2 such that they're equally to occur in the wild P(w1) = P(w2) = 0.5\nit is known that the data generation distribution is of the shape \nOur Current dataset contains {  ,   ,   ,    ,   ,   } such that the green points belong to class 1\nand the red points belong to class 2\n\nIn order to build our classifier we need to identify our data generating distribution (Likelihood)\nby estimating its most likely parameters from our dataset",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Given Two possible classes w1 and w2 such that they're equally to occur in the wild P(w1) = P(w2) = 0.5\nit is known that the data generation distribution is of the shape \nOur Current dataset contains {  ,   ,   ,    ,   ,   } such that the green points belong to class 1\nand the red points belong to class 2\n\nIn order to build our classifier we need to identify our data generating distribution (Likelihood)\nby estimating its most likely parameters from our dataset",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "text",
			"version": 94,
			"versionNonce": 1050796374,
			"isDeleted": false,
			"id": "AdyDsb6z",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 151.20927751969043,
			"y": 1344.2842317338796,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 76.7799072265625,
			"height": 25,
			"seed": 1145863574,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "OOKztwP7pZcPa2rQTBEQF",
					"type": "arrow"
				}
			],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Example",
			"rawText": "Example",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Example",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 236,
			"versionNonce": 1301152726,
			"isDeleted": false,
			"id": "OGjFFw5n",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 56.4625821955016,
			"y": 1415.93295270355,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#a5d8ff",
			"width": 94.40019226074219,
			"height": 20,
			"seed": 1904343830,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "0         2",
			"rawText": "0         2",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0         2",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 136,
			"versionNonce": 738924822,
			"isDeleted": false,
			"id": "Zimlriq7",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 83.445444269875,
			"y": 1414.8386872163564,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 133.74427795410156,
			"height": 20,
			"seed": 1985771414,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1   0      2   0",
			"rawText": "1   0      2   0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1   0      2   0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 115,
			"versionNonce": 2092140118,
			"isDeleted": false,
			"id": "qd98XdHd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 451.9583569787946,
			"y": 1393.464190339005,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 75,
			"height": 19,
			"seed": 37595,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "4c5aaf7d4b581b380debc6ba9ccdf643071a4cc5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 145,
			"versionNonce": 274484118,
			"isDeleted": false,
			"id": "YJBzVww3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -43.89520286144557,
			"y": 1519.2326404577102,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 501.1924177357087,
			"height": 26.378548301879405,
			"seed": 72464,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5ba0b960246bd0516aad17f188c68bd1f54386a4",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 210,
			"versionNonce": 1429891286,
			"isDeleted": false,
			"id": "tGYqrEtm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -40.689592399042965,
			"y": 1553.5136297977128,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 133.60125743390734,
			"height": 32.13194799043341,
			"seed": 83474,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "CEfVDXVplgQK1iqRYHp6c",
					"type": "arrow"
				}
			],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "63708e6185b9f9dbb2c1e094191bded40d6debe8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 272,
			"versionNonce": 910863190,
			"isDeleted": false,
			"id": "NJsw8NkupAuQWwbfSN_fm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -44.330464959313446,
			"y": 1750.9671492005434,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 501.1924177357087,
			"height": 26.378548301879405,
			"seed": 1090915094,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "657d578be398a4756c1ab056700ce1eebe652285",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 309,
			"versionNonce": 902221974,
			"isDeleted": false,
			"id": "Lj_BHpBWkkVcs9zsOdJv6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -43.35532434425676,
			"y": 1788.8429962813757,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 133.60125743390734,
			"height": 32.13194799043341,
			"seed": 762313482,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "N8y2TrzmxBXN1o5P600uH",
					"type": "arrow"
				}
			],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "cd601c0365f16d6ec67edf9aec1663494551183a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 238,
			"versionNonce": 113829066,
			"isDeleted": false,
			"id": "CEfVDXVplgQK1iqRYHp6c",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 100.14007075593878,
			"y": 1575.24900240789,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#a5d8ff",
			"width": 73.27781147976452,
			"height": 0,
			"seed": 1986039050,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708707020784,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "tGYqrEtm",
				"focus": 0.35288234729176515,
				"gap": 7.2284057210744095
			},
			"endBinding": {
				"elementId": "pJQrKr0i",
				"focus": -0.07098339855040195,
				"gap": 15.782913241795427
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
					73.27781147976452,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 131,
			"versionNonce": 1017598038,
			"isDeleted": false,
			"id": "pJQrKr0i",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 189.20079547749873,
			"y": 1564.539168422386,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#a5d8ff",
			"width": 266.7845458984375,
			"height": 20,
			"seed": 119770966,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "CEfVDXVplgQK1iqRYHp6c",
					"type": "arrow"
				}
			],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Turn it concave and find maximum",
			"rawText": "Turn it concave and find maximum",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Turn it concave and find maximum",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 283,
			"versionNonce": 1313059542,
			"isDeleted": false,
			"id": "jWFa1INv5OaCnqo1AM7fC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -61.33184963376672,
			"y": 1629.0133705632372,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 194.62336149877706,
			"height": 22.057314303194737,
			"seed": 1583188374,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "A_Xr6x5KmPl_zC2kNzQq5",
					"type": "arrow"
				}
			],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f9486515180c037244c5673a630208120e8da8c6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 361,
			"versionNonce": 842644042,
			"isDeleted": false,
			"id": "A_Xr6x5KmPl_zC2kNzQq5",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 136.30900928262335,
			"y": 1640.1346437053442,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#a5d8ff",
			"width": 75.63841454603664,
			"height": 0.29054816153188767,
			"seed": 247398422,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708707020784,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jWFa1INv5OaCnqo1AM7fC",
				"focus": 0.04192150667963138,
				"gap": 3.017497417613015
			},
			"endBinding": {
				"elementId": "ml6eKqlH",
				"focus": -0.11446514728036196,
				"gap": 8.266576212000103
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
					75.63841454603664,
					-0.29054816153188767
				]
			]
		},
		{
			"type": "image",
			"version": 191,
			"versionNonce": 1377589910,
			"isDeleted": false,
			"id": "ml6eKqlH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 221.15519104275353,
			"y": 1617.2019574826143,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 238.11761799581316,
			"height": 39.68626966596886,
			"seed": 7382,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "A_Xr6x5KmPl_zC2kNzQq5",
					"type": "arrow"
				}
			],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "75ff53dc20a5d5aa6563518069741cefc159f63c",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 134,
			"versionNonce": 2032872726,
			"isDeleted": false,
			"id": "OR7H4zYt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 169.02944519532707,
			"y": 1668.3169667107122,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 80.470551291441,
			"height": 51.62261780960366,
			"seed": 50339,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b2c21c2620d792891d6d51d302c55517b83d7872",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 445,
			"versionNonce": 345190346,
			"isDeleted": false,
			"id": "N8y2TrzmxBXN1o5P600uH",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 96.78102914879213,
			"y": 1810.1732067406567,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 73.27781147976452,
			"height": 0,
			"seed": 1523535242,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708707020785,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Lj_BHpBWkkVcs9zsOdJv6",
				"focus": 0.3276636987979526,
				"gap": 6.5350960591415515
			},
			"endBinding": {
				"elementId": "fin3tyB2",
				"focus": -0.0709833985504247,
				"gap": 15.782913241795427
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
					73.27781147976452,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 212,
			"versionNonce": 998727574,
			"isDeleted": false,
			"id": "fin3tyB2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 185.84175387035208,
			"y": 1799.4633727551525,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 266.7845458984375,
			"height": 20,
			"seed": 459344970,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "N8y2TrzmxBXN1o5P600uH",
					"type": "arrow"
				}
			],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Turn it concave and find maximum",
			"rawText": "Turn it concave and find maximum",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Turn it concave and find maximum",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 308,
			"versionNonce": 1834545686,
			"isDeleted": false,
			"id": "ee0a1qK6RhiWgaFcwbFit",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -47.47782996686544,
			"y": 1841.2320717918392,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 194.62336149877706,
			"height": 22.057314303194737,
			"seed": 465701834,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "KcqWySAQZNhtnVU0VxhtN",
					"type": "arrow"
				}
			],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6299a2b68dc5b3001bb03bc9f304856d602394f1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 458,
			"versionNonce": 1143817546,
			"isDeleted": false,
			"id": "KcqWySAQZNhtnVU0VxhtN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 157.01555452743176,
			"y": 1853.1741435778456,
			"strokeColor": "#e03131",
			"backgroundColor": "#a5d8ff",
			"width": 75.63841454603664,
			"height": 0.29054816153188767,
			"seed": 87657366,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708707020785,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ee0a1qK6RhiWgaFcwbFit",
				"focus": 0.1162143540848662,
				"gap": 9.870022995520145
			},
			"endBinding": {
				"elementId": "Y41_zkwpOchSSf2vV2REp",
				"focus": -0.11360797859753866,
				"gap": 9.207767214093536
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
					75.63841454603664,
					-0.29054816153188767
				]
			]
		},
		{
			"type": "image",
			"version": 238,
			"versionNonce": 1053483478,
			"isDeleted": false,
			"id": "Y41_zkwpOchSSf2vV2REp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 242.1100343868111,
			"y": 1830.199987853597,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 237.62102179731488,
			"height": 39.76920866900668,
			"seed": 1013950678,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "KcqWySAQZNhtnVU0VxhtN",
					"type": "arrow"
				}
			],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5af5f17626c1476f966f682943bac16ce878d902",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 154,
			"versionNonce": 1322312790,
			"isDeleted": false,
			"id": "OHldZ1WNgRhsGLC848r9M",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 174.24409291169445,
			"y": 1876.3504030223398,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 80.470551291441,
			"height": 51.62261780960366,
			"seed": 2120497622,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9dd3ea07d0dd3e73b4dd28775dda6105c87f3ac3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "freedraw",
			"version": 246,
			"versionNonce": 857598358,
			"isDeleted": false,
			"id": "hJPcy_PpsYyl_pwbUYi1W",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 453.5641797331224,
			"y": 1512.2523904719021,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 72.90509016701287,
			"height": 400.07421380906226,
			"seed": 1812253514,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					1.2050428126779025,
					0.6025214063390649
				],
				[
					3.6151284380337074,
					1.8075642190169674
				],
				[
					5.422692657050504,
					3.01260703169487
				],
				[
					8.43529968874526,
					4.217649844372772
				],
				[
					10.845385314101065,
					5.422692657050675
				],
				[
					13.25547093945687,
					7.230256876067415
				],
				[
					15.063035158473724,
					8.435299688745317
				],
				[
					16.268077971151627,
					9.64034250142322
				],
				[
					17.47312078382953,
					10.242863907762057
				],
				[
					19.280685002846383,
					10.845385314101122
				],
				[
					21.088249221863236,
					12.652949533117862
				],
				[
					22.895813440880033,
					13.255470939456927
				],
				[
					24.703377659896887,
					15.063035158473667
				],
				[
					25.90842047257479,
					16.26807797115157
				],
				[
					28.318506097930594,
					18.678163596507375
				],
				[
					29.523548910608497,
					21.690770628202245
				],
				[
					30.7285917232864,
					23.498334847218985
				],
				[
					31.933634535964302,
					26.510941878913854
				],
				[
					32.53615594230325,
					29.523548910608497
				],
				[
					33.741198754981156,
					32.53615594230337
				],
				[
					34.34372016132011,
					34.94624156765917
				],
				[
					34.34372016132011,
					38.56137000569288
				],
				[
					34.34372016132011,
					40.971455631048684
				],
				[
					34.34372016132011,
					44.586584069082164
				],
				[
					34.34372016132011,
					48.80423391345494
				],
				[
					34.34372016132011,
					54.226926570505384
				],
				[
					34.34372016132011,
					57.239533602200254
				],
				[
					34.34372016132011,
					60.85466204023396
				],
				[
					33.741198754981156,
					64.46979047826767
				],
				[
					33.741198754981156,
					68.08491891630138
				],
				[
					33.741198754981156,
					71.09752594799602
				],
				[
					33.138677348642204,
					75.31517579236879
				],
				[
					32.53615594230325,
					77.7252614177246
				],
				[
					31.33111312962535,
					81.94291126209714
				],
				[
					30.126070316947448,
					85.55803970013085
				],
				[
					28.921027504269546,
					89.17316813816456
				],
				[
					25.30589906623584,
					98.21098923324871
				],
				[
					25.30589906623584,
					100.62107485860452
				],
				[
					25.30589906623584,
					103.63368189029939
				],
				[
					24.100856253557936,
					107.2488103283331
				],
				[
					22.293292034541082,
					109.6588959536889
				],
				[
					21.088249221863236,
					112.0689815790447
				],
				[
					20.485727815524285,
					114.47906720440028
				],
				[
					19.883206409185334,
					116.88915282975609
				],
				[
					18.67816359650743,
					120.50428126778979
				],
				[
					18.07564219016848,
					122.31184548680676
				],
				[
					17.47312078382953,
					124.72193111216257
				],
				[
					16.870599377490578,
					127.73453814385721
				],
				[
					16.268077971151627,
					130.144623769213
				],
				[
					16.268077971151627,
					133.75975220724672
				],
				[
					15.665556564812675,
					136.16983783260252
				],
				[
					15.665556564812675,
					138.57992345795833
				],
				[
					15.665556564812675,
					142.19505189599204
				],
				[
					15.665556564812675,
					146.41270174036458
				],
				[
					15.665556564812675,
					151.2328729910762
				],
				[
					16.870599377490578,
					155.45052283544896
				],
				[
					17.47312078382953,
					159.6681726798215
				],
				[
					18.07564219016848,
					163.28330111785522
				],
				[
					19.280685002846383,
					166.2959081495501
				],
				[
					20.485727815524285,
					168.7059937749059
				],
				[
					21.088249221863236,
					171.71860080660053
				],
				[
					22.895813440880033,
					174.12868643195634
				],
				[
					25.30589906623584,
					178.3463362763291
				],
				[
					27.113463285252692,
					180.15390049534585
				],
				[
					28.318506097930594,
					182.56398612070166
				],
				[
					31.33111312962535,
					184.97407174605746
				],
				[
					33.741198754981156,
					186.17911455873536
				],
				[
					36.15128438033696,
					187.38415737141327
				],
				[
					37.958848599353814,
					188.58920018409117
				],
				[
					39.76641281837067,
					189.19172159043
				],
				[
					42.17649844372647,
					190.3967644031079
				],
				[
					44.58658406908228,
					190.3967644031079
				],
				[
					47.59919110077692,
					190.3967644031079
				],
				[
					49.40675531979389,
					190.3967644031079
				],
				[
					50.61179813247179,
					190.3967644031079
				],
				[
					52.41936235148853,
					190.3967644031079
				],
				[
					54.829447976844335,
					190.3967644031079
				],
				[
					56.63701219586119,
					190.3967644031079
				],
				[
					57.84205500853909,
					190.3967644031079
				],
				[
					58.44457641487804,
					190.3967644031079
				],
				[
					59.047097821216994,
					190.3967644031079
				],
				[
					59.649619227555945,
					190.3967644031079
				],
				[
					56.63701219586119,
					190.99928580944697
				],
				[
					56.03449078952224,
					190.99928580944697
				],
				[
					53.62440516416643,
					190.99928580944697
				],
				[
					51.81684094514969,
					191.6018072157858
				],
				[
					50.009276726132725,
					191.6018072157858
				],
				[
					48.80423391345482,
					192.20432862212488
				],
				[
					46.99666969443808,
					192.8068500284637
				],
				[
					45.189105475421115,
					193.40937143480278
				],
				[
					42.77901985006531,
					195.21693565381952
				],
				[
					41.57397703738741,
					195.21693565381952
				],
				[
					40.97145563104857,
					195.21693565381952
				],
				[
					40.368934224709506,
					195.21693565381952
				],
				[
					39.76641281837067,
					195.81945706015858
				],
				[
					39.1638914120316,
					195.81945706015858
				],
				[
					37.958848599353814,
					197.0244998728365
				],
				[
					37.35632719301486,
					197.0244998728365
				],
				[
					36.75380578667591,
					197.62702127917532
				],
				[
					36.15128438033696,
					198.2295426855144
				],
				[
					35.54876297399801,
					198.83206409185323
				],
				[
					34.94624156765906,
					200.03710690453113
				],
				[
					34.34372016132011,
					201.24214971720903
				],
				[
					33.741198754981156,
					203.049713936226
				],
				[
					33.741198754981156,
					203.65223534256484
				],
				[
					33.741198754981156,
					204.25475674890367
				],
				[
					33.138677348642204,
					206.06232096792064
				],
				[
					33.138677348642204,
					207.8698851869376
				],
				[
					33.138677348642204,
					209.07492799961528
				],
				[
					32.53615594230325,
					210.88249221863225
				],
				[
					32.53615594230325,
					212.08753503131015
				],
				[
					32.53615594230325,
					213.29257784398806
				],
				[
					33.138677348642204,
					214.49762065666596
				],
				[
					33.138677348642204,
					216.3051848756827
				],
				[
					33.741198754981156,
					218.11274909469967
				],
				[
					33.741198754981156,
					219.9203133137164
				],
				[
					33.741198754981156,
					221.72787753273337
				],
				[
					34.34372016132011,
					224.74048456442802
				],
				[
					34.34372016132011,
					227.15057018978382
				],
				[
					34.94624156765906,
					229.56065581513963
				],
				[
					35.54876297399801,
					232.5732628468345
				],
				[
					36.15128438033696,
					234.9833484721903
				],
				[
					37.35632719301486,
					238.59847691022378
				],
				[
					37.958848599353814,
					242.21360534825772
				],
				[
					38.561370005692766,
					245.8287337862912
				],
				[
					39.1638914120316,
					248.84134081798607
				],
				[
					40.368934224709506,
					251.8539478496807
				],
				[
					42.17649844372647,
					254.86655488137558
				],
				[
					43.381541256404375,
					259.0842047257481
				],
				[
					44.58658406908228,
					263.3018545701209
				],
				[
					46.39414828809902,
					266.9169830081546
				],
				[
					49.40675531979389,
					271.13463285252715
				],
				[
					52.41936235148853,
					275.95480410323876
				],
				[
					55.43196938318329,
					280.77497535395037
				],
				[
					58.44457641487804,
					286.1976680110008
				],
				[
					60.85466204023385,
					290.4153178553736
				],
				[
					62.6622262592507,
					294.0304462934073
				],
				[
					64.46979047826756,
					297.645574731441
				],
				[
					66.87987610362336,
					303.06826738849145
				],
				[
					68.68744032264021,
					307.285917232864
				],
				[
					69.89248313531812,
					312.1060884835756
				],
				[
					71.70004735433497,
					316.9262597342872
				],
				[
					72.30256876067381,
					319.9388667659821
				],
				[
					72.90509016701287,
					324.15651661035463
				],
				[
					72.90509016701287,
					328.3741664547274
				],
				[
					72.90509016701287,
					333.79685911177785
				],
				[
					72.90509016701287,
					337.41198754981156
				],
				[
					72.90509016701287,
					342.23215880052317
				],
				[
					72.30256876067381,
					345.24476583221804
				],
				[
					71.70004735433497,
					350.6674584892685
				],
				[
					69.28996172897916,
					356.09015114631893
				],
				[
					67.48239750996231,
					360.91032239703054
				],
				[
					65.0723118846065,
					365.73049364774215
				],
				[
					63.867269071928604,
					371.1531863047926
				],
				[
					61.4571834465728,
					375.37083614916537
				],
				[
					59.649619227555945,
					379.58848599353814
				],
				[
					58.44457641487804,
					381.99857161889395
				],
				[
					57.23953360220014,
					385.0111786505886
				],
				[
					55.43196938318329,
					388.02378568228323
				],
				[
					53.62440516416643,
					391.0363927139781
				],
				[
					44.58658406908228,
					397.0616067773676
				],
				[
					40.97145563104857,
					397.66412818370645
				],
				[
					38.561370005692766,
					398.86917099638436
				],
				[
					36.75380578667591,
					399.4716924027234
				],
				[
					34.34372016132011,
					399.4716924027234
				],
				[
					33.138677348642204,
					400.07421380906226
				],
				[
					31.33111312962535,
					400.07421380906226
				],
				[
					29.523548910608497,
					400.07421380906226
				],
				[
					27.113463285252692,
					400.07421380906226
				],
				[
					25.30589906623584,
					400.07421380906226
				],
				[
					22.895813440880033,
					398.86917099638436
				],
				[
					21.690770628202188,
					398.86917099638436
				],
				[
					19.883206409185334,
					398.2666495900455
				],
				[
					18.07564219016848,
					398.2666495900455
				],
				[
					17.47312078382953,
					398.2666495900455
				],
				[
					16.870599377490578,
					398.2666495900455
				],
				[
					16.268077971151627,
					398.2666495900455
				],
				[
					15.665556564812675,
					398.2666495900455
				],
				[
					15.665556564812675,
					398.2666495900455
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "image",
			"version": 127,
			"versionNonce": 706234070,
			"isDeleted": false,
			"id": "EI0tH7je",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 527.1383910328332,
			"y": 1676.4161367125994,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 329.0708719641455,
			"height": 47.41655215621693,
			"seed": 32432,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708707019982,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "550c29b4e6b1a47143145ed5579ab30411d12c26",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 52,
			"versionNonce": 900831050,
			"isDeleted": false,
			"id": "PengzOokAfKIxT6WRfZK1",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 246.82012211319704,
			"y": 824.2944634590011,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 73.9708836648893,
			"height": 1.5096098707120973,
			"seed": 84532886,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708707005470,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "4m7xlwOZ",
				"focus": 0.1136548360735928,
				"gap": 9.486125821218707
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
					73.9708836648893,
					-1.5096098707120973
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
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": -999.0692261697119,
		"scrollY": -414.33852698295084,
		"zoom": {
			"value": 1.8255147993748362
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