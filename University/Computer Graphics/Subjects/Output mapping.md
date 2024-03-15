---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - Subject
  - ComputerGraphics
---
Child of [[CGRoadmap]]
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Output mapping ^RocOKWCJ

Images split into two types ^s2kW75PG

Raster Images ^ANx8THLV

Vector images ^GBSnN40L

GIF, TIFF, JFIF (JPEG), PNG, (PS) ^8KB9CrbZ

SVG, EPS, CGM, (PS, PDF) ^kkA3EQtG

Images compromised of pixels
The resolution depends on the number of pixels
(Higher resolution usually means better quality)
This lecture's main focus! ^iYlc88DP

Images compromised of vertices and vectors
Similar to 2D Graphics programming ^IHHgNpM4

So far We can store the color of each pixel
in an image are three 32 bit color values (R,G,B) ^tn9eT5q9

Thats 79 Octillion different color combinations for one pixel
which is way more than what humans can distinguish ^n5ZborKE

Possible issues that
can occur? ^CI0qH64W

Too many colors, wasted storage!
Compatibility issues with different devices or printers! ^82R1zxKB

Raster Images ^TYkpPJIz

Color in each pixel of the image is stored in 3 bytes (24bits)
alpha/transparency channel adds one byte ^gb8uOyv8

16.7million combinations which is still plenty! ^vmesB74i

Tone Mapping ^XNE3LPcp

Motivation
There is no physical limit for the radiance of a point coming through the input!!
RGB can range from 0 to infinity in reality, but our displays are limited to 255 ^yA8gqHMG

Naive Solutions ^auPSSdQD

How about we Clamp everything
higher than a fixed value? ^EUy1sU3l

How about we We linearly interpolate
from the lowest to the highest value? ^ozBrc2Ib

Areas that are too bright immediately
get mapped to 1, we lose out on a lot of
details in those bright spots.
Laptop emits light and has light contribution from window
thus is extremely bright ^AiyuY5y1

Too dark!!
the extreme range of bright colors makes
any other color mapped to an extremely
small range!! ^tvN9XG64

Human vision is logarithmic not linear!
The difference between between 1 to 2 candles
is more noticeable than the difference between 99 and 100 candles ^vWnX2LjA

Use a mapping that
is much more precise towards 0
to match our vision ^6qAyMgeY

Note: we do not precieve every color
with the same brightness (Greens are
a lot more bright) ^mVrSJfnU

Reinhard Tone mapping ^QbX7LYSP

Brings all luminance values into a displayable range ^lUOv2DVA

Low luminance values are scaled with precision ~ 1
High luminance value are scaled with precision ~ 1/L ^xTy1aslF

Side effect: No value that maps to maximum luminance of 1 (Burnout) ^xxUum5eV

We use Schlicks method in order to apply this ^hwr4NdoC

output color ^bI4KhqVR

avoid division by 0 ^pilve2aB

Clamping is still necessary! ^dZlocMn1

details on the screen
are visible! ^vD201Pms

Overall constrant is lowered, can no longer see
white on the screen ^9Lkq5dWl

Extended Reinhard Tone-Mapping ^hfUlgE66

Parameter Lwhite is the smallest luminance that will be mapped to pure white
which is often set to the highest luminance in the scene
A blend between ERT and Linear mapping.  ^1Bi33v6p

Reinhard Tone-Mapping is a popular choice but there are many more ^Fpg4jNSR

Filmic Tone-Mappings (Not physically accurate, but is made to look aesthetically pleasing) 
Camera Response Functions (Made to Tone-Map response of a real camera)
Local Tone mappings (Depending on pixel position can be more realistic to simulate human vision) ^k3Ae1Tv8

Color Correction ^KEuML9ol

The coordinates of one color w.r.t to a certain space is
highly different from that same color in a different color space
if color is not specified we assume sRGB ^g69K26SN

SRGB dates back to 1995 where screens need gamma
correction! we need to account for those changes ^dxW92IhB

Image color must be gamma encoded before being sent to the display ^5tfzaemr

store the gamma encoded version ^o7hGL1q8

Remember to discretize after encoding to able to store it
in 24bits ^g5kAk01z

Gamma encoding before discretization allocates
more bits to darker parts of an image ^nVIb4Agb

Compression ^RtofhKFG

we want to reduce Storage size and number
of bits to send in a network!
High resolutions with 3bytes per pixel needs a lot of
storage which is often unnecessary and impractically large ^O3RW7x8H

Images usually only contain a subset of colors ^gRsWKgy9

Create a color table with 256 entries is often sufficient
Every entry in the table contains a 24bit color
each pixel contains an 8bit pointer to the table color ^g2jDG5T7

How to generate color table?

Quantization of the colors into representative colors!
Resulting 256 colors are usually enough for reasonable image representation ^zOUR3xfh

Median Cut algorithm ^MI2PGLp6

Every pixel color is a point in the RGB cube
we take axis aligned bounding boxes for all the color points
in this space, then we compute:

1) Find the cube with the biggest diagonal (biggest variance)

2) find its longest edge of the rectangle

3) Divide it into 2 boxes according to the median

4) once you have 256 boxes, point each one to the center color ^mXIEqu8j

how is the reduction typically done? ^zySIveuk

Dithering ^HSs4CkXH

Dithering is a type of noise to randomize quantization error
that creates the illusion of color depth with a limited color table
Humans do not look at individual colors but a combination of neighbouring
colors! ^83jcboTd

what if my output device
has only a limited
amount of colors? ^qq74oHDd

Naive Solution
Rounding ^5v9Hqd2O

Round everything above 0.5 to white
and everything below 0.5 to black ^MNwk1oGc

this is bad! ^fPAX8pQD

Floyd Steinberg Algorithm ^Ycyx3w5F

1) Decide on a specific mask usually specially crafted
    for example purposes we are using this one ^JyGHu5Mk

current pixel ^fqVeKKVR

already
computed ^41SdbhDN

2) Spread every quantization error to neighboring
pixels according to a mask ^uiUWPl8p

If a pixel is rounded downwards, it becomes more likely
that a neighboring pixel is rounded upwards ^6DXQooIB

JPEG compression ^5swaUqzf

Algorithms for compressing images in full color
Optimized for smooth color transitions with few sharp edges (not really
suited for texts and synthetic images)
This process is made up of 5 steps ^Pvf1KJhu

Step 1: 
Conversion from RGB to YCrCb color space
Y = Luminance    Cr= Red Chrominance     Cb= Blue Chrominance ^r8Q3QwKz

Step 2: 
Chroma sub-sampling
Lossy reduction of the amount of values we store
 CR and CB are averaged over small regions in the image ^Y4kmZ2Ty

No information is lost here! but we convert our data into
Luminance which humans are sensitive to and we dont want to give up
red/blue chrominance which we can afford losing some of! ^yIsaOxsT

No loss ^fQbs3EnN

Step 3:
Discrete Cosine Transformation ^QJdzRdmz

for each 2x2 pixel
we store 4Y 4Cr 4Cb
values ^JK24Kb3N

share same cr cb values ^80Yis0VA

Cr ^4nCEHS2d

Cb ^DpYOPV2L

Tiling the image into small blocks typically 8x8 or 16x16
then we Convert the blocks into frequency space
Color values are transformed into interval [-128,127] ^9NMmxaSp

Since humans are limited for high spatial frequencies, the DCT restricts
lossy operations to high frequencies ^GrkfxX25

Why?
Well if the the blocks are
too small we aren't really doing
anything and if blocks are too big
then theres more of a chance
that we encounter high frequency
that we do want to encode ^35Uokia6

smooth image content leads to small differences which results
in coefficients for high frequencies to be negligible thus we can
describe our data in a way that later on allows us to ignore
high frequencies without it affecting the human perception.
Youre more likely to encounter blocks of the image where little to no
high frequency being described and that can be minimized! but in other regions
it might be important to keep to jump between colors! ^99nzJ0YO

Quantization ^kw8ZeyBw

Takes in multiple DCT coefficients and combines them into groups
of constant value that way we do not have to store as much
to describe the data, higher coefficients get larger groups while smaller
coefficients get more detail ^54VVCwov

The number of quantization levels is the main parameter for
controlling the compression and quality of the image
 ^XSiSuww1

Specific quantization tables (different in brightness and chroma)
have been designed to minimize the visible loss of information (for human observers) ^QJ5epKVd

the closer the colors are
to each other the less
"high frequency" there is in block ^U9jaJ8Fs

Entropy Encoding ^2GicTw7C

We Serialize the data by traversing the quantization table from
low spatial frequency to high spatial frequency and forming blocks
of data containing the frequencies ^yBN2m2le

The blocks are transformed into a sequential bit stream  ^jbMj7eYB

DC coefficients are encoded differentially (difference to previous DC coefficient is often small) ^783eSoqz

large spatial frequencies usually
containing long sequences of zeros ^DRRQKFfD


# Embedded files
5e473649f738deb0e1412305e8e83f532db35cea: $$L_{out} = \frac{L_{in}}{1 + L_{in}}$$
16f4cb8156437418aad9114ae0a101b08923f140: $$C_{out} = C_{in} \frac{L_{out}}{L_in + \epsilon}$$
b558f2aeb012da6276c5f6ff840f7c25fcd39927: $$L_{out} = \frac{L_{in} \left(1+ \frac{L_{in}}{L^2_{white}} \right)}{1 + L_{in}}$$
57eda99c7c0e95c71e8be2882cbab808b1650c1e: $$V = C^{\frac{1}{\gamma}}$$
6ed3867c95ea4479d2c4080cbe3c9af2fdafb233: [[cropped_Pasted Image 20240301110357_337]]
96e3a592dab4ebd506e099bf71cb73cb364755b6: [[Pasted Image 20240301112157_187.png]]
b5539d24305e4241a5379794b592965457ad2416: [[cropped_Pasted Image 20240301114404_337]]
645180e97bc5dec8188e7afb2c5b24b7de1a4b6f: [[Pasted Image 20240301122326_401.png]]
6aeb4f2d12f3361ea5be0a764f823d3fc856cf67: [[Pasted Image 20240301122700_515.png]]
0527e0bdaca8da6ee30e9d6b426742e327a78535: [[cropped_Pasted Image 20240301133704_943]]
dc36b6bc596ddcd7612e9b35c9c2ecdc72915278: [[cropped_Pasted Image 20240301135809_079]]
1eefc6fef2c04f8f54be494d68c5de1bf55bd438: [[Pasted Image 20240301144102_339.png]]
126eca767037b861eb439d5f120d9434d6cd44a3: [[Pasted Image 20240301144117_353.png]]
3773f74cf1a231ecfd1694f64e0e0db7d4f2bc38: [[Pasted Image 20240301144535_375.png]]
2e85a3cc4f4db04a51667efe9237d207067fa773: [[Pasted Image 20240301144605_376.png]]
51b1ad8e59234b6bc48d6b78756c2f90e5e97b54: [[Pasted Image 20240301152315_916.png]]
e0b0ac862baa9ed6747cfff917a997be0a156f2f: [[Pasted Image 20240301152736_962.png]]
1e8da59bb635d4d9d734608f716111d2e5c5fa03: [[Pasted Image 20240301152853_972.png]]
010f1c6d94d56fd545bee1737f2f4c0c80b811bc: [[Pasted Image 20240301154929_099.png]]
f0f5100a4664a60e57d551f493fb78e00b7416fd: [[Pasted Image 20240301155016_131.png]]
1a840a0a481d5267ce1f41e67dbcd1977b067baf: [[Pasted Image 20240301155032_140.png]]
6439629eb58b293c56041e4094a4640aa98e99fd: [[Pasted Image 20240301155047_142.png]]
f08dd78ab34febe50a3ff7381066a9c819b29c1e: [[Pasted Image 20240301202357_872.png]]
e8ee0efb19565fbd32e0da5150e94d78d3282ca1: [[Pasted Image 20240304174057_613.png]]
9581418968868cf54a89f7999015fe96a9d45cf1: [[Pasted Image 20240304174250_630.png]]
29357b030b9cb32a53d3c306425c9d7b60ced8f7: [[Pasted Image 20240304175923_727.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.23",
	"elements": [
		{
			"type": "image",
			"version": 164,
			"versionNonce": 930689228,
			"isDeleted": false,
			"id": "quTA_ml1IBHfEWva5LJFh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1061.4252378861754,
			"y": 1246.6724209139215,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 278.77840058582353,
			"height": 278.77840058582353,
			"seed": 1053185908,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165719,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "645180e97bc5dec8188e7afb2c5b24b7de1a4b6f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 187,
			"versionNonce": 2089292276,
			"isDeleted": false,
			"id": "UkyedumupltVz3j5_1q--",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -163.25,
			"y": -424.2578125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#9775fa",
			"width": 333,
			"height": 138,
			"seed": 660851811,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "RocOKWCJ"
				}
			],
			"updated": 1709320165719,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 149,
			"versionNonce": 2100377420,
			"isDeleted": false,
			"id": "RocOKWCJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -101.39571650652502,
			"y": -372.5481804018718,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 208.8248748779297,
			"height": 35,
			"seed": 1943083075,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165719,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Output mapping",
			"rawText": "Output mapping",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "UkyedumupltVz3j5_1q--",
			"originalText": "Output mapping",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 632,
			"versionNonce": 320451444,
			"isDeleted": false,
			"id": "5vp5IXpq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -388.5575148076414,
			"y": -216.91534759337546,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 218.16591767493225,
			"height": 251.0060338038173,
			"seed": 8204,
			"groupIds": [
				"U4ClFWb6ioDzGIuu9TEVq"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "vV3yTspe51VNUuS6_oGP5",
					"type": "arrow"
				}
			],
			"updated": 1709320165719,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6ed3867c95ea4479d2c4080cbe3c9af2fdafb233",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 713,
			"versionNonce": 186936780,
			"isDeleted": false,
			"id": "6aDp7vl0UKcy-WFKFFd7d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -279.78369950248555,
			"y": 33.80175834448781,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 110.47755109701961,
			"height": 57.58829812840105,
			"seed": 824815052,
			"groupIds": [
				"U4ClFWb6ioDzGIuu9TEVq"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
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
					-108.17801835925313,
					1.099776526757656
				],
				[
					-108.87787614900812,
					-56.48852160164339
				],
				[
					1.5996749480115027,
					-0.5998781055041719
				]
			]
		},
		{
			"type": "line",
			"version": 832,
			"versionNonce": 2046502132,
			"isDeleted": false,
			"id": "FHSX32f5a6eyKL812SnrP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -279.1753420314046,
			"y": 33.93446174527989,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 110.47755109701967,
			"height": 57.588298128401064,
			"seed": 600791284,
			"groupIds": [
				"U4ClFWb6ioDzGIuu9TEVq"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
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
					108.1780183592532,
					1.0997765267576565
				],
				[
					108.87787614900816,
					-56.48852160164341
				],
				[
					-1.5996749480115038,
					-0.5998781055041721
				]
			]
		},
		{
			"type": "line",
			"version": 941,
			"versionNonce": 309122124,
			"isDeleted": false,
			"id": "a-5Kr_CNaa-cQhpfOhDEa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -278.2702702119882,
			"y": -216.78152485489937,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 110.47755109701977,
			"height": 57.588298128401114,
			"seed": 400687308,
			"groupIds": [
				"U4ClFWb6ioDzGIuu9TEVq"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
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
					108.1780183592533,
					-1.0997765267576576
				],
				[
					108.87787614900826,
					56.48852160164346
				],
				[
					-1.599674948011505,
					0.5998781055041726
				]
			]
		},
		{
			"type": "line",
			"version": 1016,
			"versionNonce": 917661300,
			"isDeleted": false,
			"id": "KMbuMuOhYUGlbTVFAoYZo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -280.7395011130902,
			"y": -216.9088992879728,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 110.47755109701977,
			"height": 57.588298128401114,
			"seed": 986420684,
			"groupIds": [
				"U4ClFWb6ioDzGIuu9TEVq"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
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
					-108.1780183592533,
					-1.0997765267576576
				],
				[
					-108.87787614900826,
					56.48852160164346
				],
				[
					1.599674948011505,
					0.5998781055041726
				]
			]
		},
		{
			"type": "text",
			"version": 159,
			"versionNonce": 283405004,
			"isDeleted": false,
			"id": "s2kW75PG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -133.43983433948296,
			"y": -255.19783963811622,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 273.3796691894531,
			"height": 25,
			"seed": 1597658740,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "vV3yTspe51VNUuS6_oGP5",
					"type": "arrow"
				},
				{
					"id": "lR2L6-XvLKxpWYD5w_sNE",
					"type": "arrow"
				}
			],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Images split into two types",
			"rawText": "Images split into two types",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Images split into two types",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "arrow",
			"version": 168,
			"versionNonce": 772110324,
			"isDeleted": false,
			"id": "vV3yTspe51VNUuS6_oGP5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 8.510072570133786,
			"y": -216.7219564615526,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 175.56773258581342,
			"height": 129.97088788408342,
			"seed": 1015215732,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "s2kW75PG",
				"focus": -0.07785112670892361,
				"gap": 13.475883176563627
			},
			"endBinding": {
				"elementId": "5vp5IXpq",
				"focus": 0.08716131725919321,
				"gap": 3.3339371170295493
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
					-26.010213739524374,
					120.84745460517465
				],
				[
					-175.56773258581342,
					129.97088788408342
				]
			]
		},
		{
			"type": "arrow",
			"version": 447,
			"versionNonce": 958738764,
			"isDeleted": false,
			"id": "lR2L6-XvLKxpWYD5w_sNE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 7.484781254469851,
			"y": -215.90696202133307,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 167.86585449585937,
			"height": 125.21629980409355,
			"seed": 574503668,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "s2kW75PG",
				"focus": 0.008478858339654016,
				"gap": 14.290877616783149
			},
			"endBinding": {
				"elementId": "ZdwytZ6L5G407tyTqAAZG",
				"focus": 0.018329387500526675,
				"gap": 7.636945538156709
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
					23.784881503148767,
					117.67257164715681
				],
				[
					167.86585449585937,
					125.21629980409355
				]
			]
		},
		{
			"type": "image",
			"version": 290,
			"versionNonce": 1006262644,
			"isDeleted": false,
			"id": "ZdwytZ6L5G407tyTqAAZG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 182.9875812884859,
			"y": -194.31867866508304,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 224.1126527073099,
			"height": 224.1126527073099,
			"seed": 1472088908,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "lR2L6-XvLKxpWYD5w_sNE",
					"type": "arrow"
				}
			],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "96e3a592dab4ebd506e099bf71cb73cb364755b6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 48,
			"versionNonce": 1518938060,
			"isDeleted": false,
			"id": "ANx8THLV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -353.16479854091864,
			"y": -240.90696168266572,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 147.31982421875,
			"height": 25,
			"seed": 238922700,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Raster Images",
			"rawText": "Raster Images",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Raster Images",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 43,
			"versionNonce": 1272384244,
			"isDeleted": false,
			"id": "GBSnN40L",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 228.9609177980757,
			"y": -216.72195586939807,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 134.49984741210938,
			"height": 25,
			"seed": 1600300748,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Vector images",
			"rawText": "Vector images",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vector images",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 67,
			"versionNonce": 1227509324,
			"isDeleted": false,
			"id": "8KB9CrbZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -378.14370684694757,
			"y": 43.21425615659313,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 197.03695678710938,
			"height": 13.786353854153983,
			"seed": 1291461836,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"fontSize": 11.029083083323187,
			"fontFamily": 1,
			"text": "GIF, TIFF, JFIF (JPEG), PNG, (PS)",
			"rawText": "GIF, TIFF, JFIF (JPEG), PNG, (PS)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "GIF, TIFF, JFIF (JPEG), PNG, (PS)",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 389,
			"versionNonce": 1881246836,
			"isDeleted": false,
			"id": "kkA3EQtG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 228.9609180037677,
			"y": 36.452554681829355,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 143.10057067871094,
			"height": 13.654878038477143,
			"seed": 1519789044,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"fontSize": 10.923902430781714,
			"fontFamily": 1,
			"text": "SVG, EPS, CGM, (PS, PDF)",
			"rawText": "SVG, EPS, CGM, (PS, PDF)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SVG, EPS, CGM, (PS, PDF)",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 1172481228,
			"isDeleted": false,
			"id": "iYlc88DP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -466.4012632436056,
			"y": 57.00061019266327,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 373.7927551269531,
			"height": 80,
			"seed": 854545140,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Images compromised of pixels\nThe resolution depends on the number of pixels\n(Higher resolution usually means better quality)\nThis lecture's main focus!",
			"rawText": "Images compromised of pixels\nThe resolution depends on the number of pixels\n(Higher resolution usually means better quality)\nThis lecture's main focus!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Images compromised of pixels\nThe resolution depends on the number of pixels\n(Higher resolution usually means better quality)\nThis lecture's main focus!",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 426,
			"versionNonce": 2057297396,
			"isDeleted": false,
			"id": "IHHgNpM4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 136.31696456449623,
			"y": 57.000609633667054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 350.3367004394531,
			"height": 40,
			"seed": 881757300,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Images compromised of vertices and vectors\nSimilar to 2D Graphics programming",
			"rawText": "Images compromised of vertices and vectors\nSimilar to 2D Graphics programming",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Images compromised of vertices and vectors\nSimilar to 2D Graphics programming",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "image",
			"version": 131,
			"versionNonce": 1716267852,
			"isDeleted": false,
			"id": "LqNKqrOr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -154.25406860133262,
			"y": 221.39831602036998,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 324.1760144759271,
			"height": 292.32603639998484,
			"seed": 54005,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b5539d24305e4241a5379794b592965457ad2416",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "ellipse",
			"version": 482,
			"versionNonce": 341311348,
			"isDeleted": false,
			"id": "48IwIJBkogs4upoZphooH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 70,
			"angle": 0,
			"x": -350.6568907371878,
			"y": 354.2048358136048,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 82.12285108668999,
			"height": 73.77025317440324,
			"seed": 625123060,
			"groupIds": [
				"Cp633sD772O47pEbdDJyc"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 771,
			"versionNonce": 2093015500,
			"isDeleted": false,
			"id": "Md46YSO-W6vMF_CT-IVlX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 70,
			"angle": 0,
			"x": -320.8572619815497,
			"y": 306.8148471732436,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 82.12285108668999,
			"height": 73.77025317440324,
			"seed": 490124916,
			"groupIds": [
				"Cp633sD772O47pEbdDJyc"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 674,
			"versionNonce": 1435496692,
			"isDeleted": false,
			"id": "sVaTwr4MerqGDW5QQebG1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 60,
			"angle": 0,
			"x": -290.4757326526194,
			"y": 354.2048354971244,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#099268",
			"width": 82.12285108668999,
			"height": 73.77025317440324,
			"seed": 33091316,
			"groupIds": [
				"Cp633sD772O47pEbdDJyc"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 307,
			"versionNonce": 5949516,
			"isDeleted": false,
			"id": "rqCZNuYMvcNnY7f-0qcxQ",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 70,
			"angle": 0,
			"x": -159.59891909833974,
			"y": 216.07958877271338,
			"strokeColor": "#868e96",
			"backgroundColor": "transparent",
			"width": 334.775859553475,
			"height": 302.62745119755834,
			"seed": 735441396,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 255,
			"versionNonce": 1573761652,
			"isDeleted": false,
			"id": "tShq0RbklxTe7uSi8cOjU",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -156.0659581321096,
			"y": 219.85473532360604,
			"strokeColor": "#ced4da",
			"backgroundColor": "transparent",
			"width": 327.91165432356627,
			"height": 295.3190423467531,
			"seed": 1397819468,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 556,
			"versionNonce": 1962139340,
			"isDeleted": false,
			"id": "CMxHh6LK59mRjp1YKG7M-",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -163.55767362180572,
			"y": 212.08587681474998,
			"strokeColor": "#343a40",
			"backgroundColor": "transparent",
			"width": 342.65436817399564,
			"height": 310.6181825162483,
			"seed": 1372864116,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 150,
			"versionNonce": 1809269748,
			"isDeleted": false,
			"id": "tn9eT5q9",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -238.9701902048411,
			"y": 531.2105351262024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 493.4794006347656,
			"height": 50,
			"seed": 1720020300,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "So far We can store the color of each pixel\nin an image are three 32 bit color values (R,G,B)",
			"rawText": "So far We can store the color of each pixel\nin an image are three 32 bit color values (R,G,B)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "So far We can store the color of each pixel\nin an image are three 32 bit color values (R,G,B)",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 182,
			"versionNonce": 1395008844,
			"isDeleted": false,
			"id": "n5ZborKE",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -230.43629396622813,
			"y": 581.2105350195304,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 474.1929931640625,
			"height": 40,
			"seed": 369256908,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rNHr2rImH7gi88xCW0lck",
					"type": "arrow"
				},
				{
					"id": "Yj6K6QXWtOUfhFv67RcV4",
					"type": "arrow"
				}
			],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Thats 79 Octillion different color combinations for one pixel\nwhich is way more than what humans can distinguish",
			"rawText": "Thats 79 Octillion different color combinations for one pixel\nwhich is way more than what humans can distinguish",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Thats 79 Octillion different color combinations for one pixel\nwhich is way more than what humans can distinguish",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "ellipse",
			"version": 571,
			"versionNonce": 1974642036,
			"isDeleted": false,
			"id": "eW6vmzayQqgnyz-QGhfJn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 70,
			"angle": 0,
			"x": 223.89190353446455,
			"y": 354.2048355231821,
			"strokeColor": "#1971c2",
			"backgroundColor": "#1971c2",
			"width": 82.12285108668999,
			"height": 73.77025317440324,
			"seed": 1574683724,
			"groupIds": [
				"MXMdRG081Cr8zvH6kCcFR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 849,
			"versionNonce": 1884003276,
			"isDeleted": false,
			"id": "y-eKdAx-QjDqtHt8ilLqr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 70,
			"angle": 0,
			"x": 253.69153229010263,
			"y": 306.814846882821,
			"strokeColor": "#e03131",
			"backgroundColor": "#e03131",
			"width": 82.12285108668999,
			"height": 73.77025317440324,
			"seed": 1895127756,
			"groupIds": [
				"MXMdRG081Cr8zvH6kCcFR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 759,
			"versionNonce": 1084610292,
			"isDeleted": false,
			"id": "eKlw1lAToyX0tJgBBkWuy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 60,
			"angle": 0,
			"x": 284.07306161903296,
			"y": 354.20483520670183,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#099268",
			"width": 82.12285108668999,
			"height": 73.77025317440324,
			"seed": 1234706764,
			"groupIds": [
				"MXMdRG081Cr8zvH6kCcFR"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 168,
			"versionNonce": 1719550540,
			"isDeleted": false,
			"id": "CI0qH64W",
			"fillStyle": "solid",
			"strokeWidth": 4,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -93.15035824385416,
			"y": 655.6934861472754,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 201.83973693847656,
			"height": 50,
			"seed": 629087220,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "lj0_WfQBm4gjR5Fjc02pL",
					"type": "arrow"
				},
				{
					"id": "rNHr2rImH7gi88xCW0lck",
					"type": "arrow"
				}
			],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Possible issues that\ncan occur?",
			"rawText": "Possible issues that\ncan occur?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Possible issues that\ncan occur?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 147,
			"versionNonce": 2033637492,
			"isDeleted": false,
			"id": "lj0_WfQBm4gjR5Fjc02pL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 168.10882235787108,
			"y": 620.932550696263,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 70.34137194184007,
			"height": 57.96129048007606,
			"seed": 1260550388,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "CI0qH64W",
				"focus": 0.22302395790561752,
				"gap": 5.397270011915566
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
					16.31919829050696,
					51.77124974919434
				],
				[
					-54.022173651333105,
					57.96129048007606
				]
			]
		},
		{
			"type": "arrow",
			"version": 163,
			"versionNonce": 2090342604,
			"isDeleted": false,
			"id": "rNHr2rImH7gi88xCW0lck",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -158.1723118816183,
			"y": 629.5656652336005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 73.15502681951365,
			"height": 54.02217365133299,
			"seed": 1952959476,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165720,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "n5ZborKE",
				"focus": 0.6404845665196366,
				"gap": 8.355130214070073
			},
			"endBinding": {
				"elementId": "CI0qH64W",
				"focus": -0.22243052134651192,
				"gap": 8.186125108757452
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
					-16.319198290506964,
					51.771249749194354
				],
				[
					56.83582852900669,
					54.02217365133299
				]
			]
		},
		{
			"type": "text",
			"version": 135,
			"versionNonce": 1261152756,
			"isDeleted": false,
			"id": "82R1zxKB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -206.20423789471198,
			"y": 705.6934860442187,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 425.7288818359375,
			"height": 40,
			"seed": 441650380,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HxbdMcr-k0I1KVj-ymgNR",
					"type": "arrow"
				},
				{
					"id": "LGjylE-SSdgmzXxxjyUS_",
					"type": "arrow"
				},
				{
					"id": "n5jnT9ZVSkuUY3HeRPjV5",
					"type": "arrow"
				}
			],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Too many colors, wasted storage!\nCompatibility issues with different devices or printers!",
			"rawText": "Too many colors, wasted storage!\nCompatibility issues with different devices or printers!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Too many colors, wasted storage!\nCompatibility issues with different devices or printers!",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 82,
			"versionNonce": 238231372,
			"isDeleted": false,
			"id": "TYkpPJIz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 535.4314598422455,
			"y": 569.5053250311383,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 206.24775390624998,
			"height": 35,
			"seed": 1991379444,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Raster Images",
			"rawText": "Raster Images",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Raster Images",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 206,
			"versionNonce": 2039106420,
			"isDeleted": false,
			"id": "gb8uOyv8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 333.0862297062838,
			"y": 609.7674923750599,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 610.9393310546875,
			"height": 50,
			"seed": 2117743348,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Color in each pixel of the image is stored in 3 bytes (24bits)\nalpha/transparency channel adds one byte",
			"rawText": "Color in each pixel of the image is stored in 3 bytes (24bits)\nalpha/transparency channel adds one byte",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Color in each pixel of the image is stored in 3 bytes (24bits)\nalpha/transparency channel adds one byte",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 108,
			"versionNonce": 1940477388,
			"isDeleted": false,
			"id": "vmesB74i",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 472.3795342954546,
			"y": 665.029660265649,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 332.35272216796875,
			"height": 20,
			"seed": 979487348,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "16.7million combinations which is still plenty!",
			"rawText": "16.7million combinations which is still plenty!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "16.7million combinations which is still plenty!",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 76,
			"versionNonce": 1989721332,
			"isDeleted": false,
			"id": "Yj6K6QXWtOUfhFv67RcV4",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 256.51293237394725,
			"y": 584.7029048286417,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 221.33913662618363,
			"height": 2.367263493328096,
			"seed": 1295601780,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "n5ZborKE",
				"focus": -0.8510840179912085,
				"gap": 12.756233176112886
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
					221.33913662618363,
					2.367263493328096
				]
			]
		},
		{
			"type": "arrow",
			"version": 107,
			"versionNonce": 1779743820,
			"isDeleted": false,
			"id": "HxbdMcr-k0I1KVj-ymgNR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -0.3620074195829375,
			"y": 756.765087749628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 596.915492427287,
			"height": 247.65642770919362,
			"seed": 2002994380,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "82R1zxKB",
				"focus": 0.11199923123428546,
				"gap": 11.071601705409307
			},
			"endBinding": {
				"elementId": "XNE3LPcp",
				"focus": 0.10836638313773649,
				"gap": 6.598015020993216
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
					74.08525615232281,
					127.00329626112489
				],
				[
					536.5889267032527,
					125.94493545894886
				],
				[
					596.915492427287,
					247.65642770919362
				]
			]
		},
		{
			"type": "text",
			"version": 63,
			"versionNonce": 2078080628,
			"isDeleted": false,
			"id": "XNE3LPcp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 507.0373696396419,
			"y": 1011.0195304798149,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 181.384765625,
			"height": 35,
			"seed": 92536820,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "HxbdMcr-k0I1KVj-ymgNR",
					"type": "arrow"
				}
			],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Tone Mapping",
			"rawText": "Tone Mapping",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Tone Mapping",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 200,
			"versionNonce": 2068796108,
			"isDeleted": false,
			"id": "yA8gqHMG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 200.22016910042223,
			"y": 1046.0195295865722,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 795.0191650390625,
			"height": 75,
			"seed": 1219251828,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Pi9-pmKAkkSWj5jowOExm",
					"type": "arrow"
				},
				{
					"id": "oIk5gVkknNveNDzFCH6W1",
					"type": "arrow"
				}
			],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Motivation\nThere is no physical limit for the radiance of a point coming through the input!!\nRGB can range from 0 to infinity in reality, but our displays are limited to 255",
			"rawText": "Motivation\nThere is no physical limit for the radiance of a point coming through the input!!\nRGB can range from 0 to infinity in reality, but our displays are limited to 255",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Motivation\nThere is no physical limit for the radiance of a point coming through the input!!\nRGB can range from 0 to infinity in reality, but our displays are limited to 255",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 199,
			"versionNonce": 572329972,
			"isDeleted": false,
			"id": "Pi9-pmKAkkSWj5jowOExm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1003.3388633927973,
			"y": 1091.7681084284252,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 197.0024283172511,
			"height": 122.2541738075256,
			"seed": 1777307980,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "yA8gqHMG",
				"focus": -0.2579808214803076,
				"gap": 8.09952925331254
			},
			"endBinding": {
				"elementId": "EUy1sU3l",
				"focus": 0.06117209877743891,
				"gap": 5.768951180410795
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
					173.10146234869035,
					10.237183257180732
				],
				[
					197.0024283172511,
					122.2541738075256
				]
			]
		},
		{
			"type": "text",
			"version": 39,
			"versionNonce": 1710430540,
			"isDeleted": false,
			"id": "auPSSdQD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1031.3007838552282,
			"y": 1059.1952526101231,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 148.81982421875,
			"height": 25,
			"seed": 841142772,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Naive Solutions",
			"rawText": "Naive Solutions",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Naive Solutions",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 82,
			"versionNonce": 2036265332,
			"isDeleted": false,
			"id": "EUy1sU3l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1045.3458326614295,
			"y": 1219.7912334163616,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 303.879638671875,
			"height": 50,
			"seed": 482565708,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Pi9-pmKAkkSWj5jowOExm",
					"type": "arrow"
				}
			],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How about we Clamp everything\nhigher than a fixed value?",
			"rawText": "How about we Clamp everything\nhigher than a fixed value?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How about we Clamp everything\nhigher than a fixed value?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 293,
			"versionNonce": 89788364,
			"isDeleted": false,
			"id": "oIk5gVkknNveNDzFCH6W1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1007.8092740548029,
			"y": 1090.8375681276536,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 578.4180959368948,
			"height": 127.62249803589862,
			"seed": 1364846196,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "yA8gqHMG",
				"focus": 0.01509891144752886,
				"gap": 12.569939915318173
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
					507.40235106208047,
					8.233709550703452
				],
				[
					578.4180959368948,
					127.62249803589862
				]
			]
		},
		{
			"type": "text",
			"version": 157,
			"versionNonce": 552116980,
			"isDeleted": false,
			"id": "ozBrc2Ib",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1396.5552549039965,
			"y": 1226.9342020927631,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 378.23956298828125,
			"height": 50,
			"seed": 438693708,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How about we We linearly interpolate\nfrom the lowest to the highest value?",
			"rawText": "How about we We linearly interpolate\nfrom the lowest to the highest value?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How about we We linearly interpolate\nfrom the lowest to the highest value?",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "ellipse",
			"version": 56,
			"versionNonce": 966669900,
			"isDeleted": false,
			"id": "3YUo9wlHtWJrF8De-IPVf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1144.0768318103637,
			"y": 1392.8079255962462,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 32.972306059755056,
			"height": 31.803075348416314,
			"seed": 2042253644,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "3JvixPBHIZ-trGLTxaIjd",
					"type": "arrow"
				}
			],
			"updated": 1709320165721,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 50,
			"versionNonce": 1598039156,
			"isDeleted": false,
			"id": "v5FPnhHGNUkTKtF96zBqY",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 1219.141443478317,
			"y": 1315.1710063633473,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 74.83076552568559,
			"height": 62.67076612776168,
			"seed": 1643053900,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "90Bg37WMuxMWg-f7P1caN",
					"type": "arrow"
				}
			],
			"updated": 1709320165721,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 463,
			"versionNonce": 1335463116,
			"isDeleted": false,
			"id": "90Bg37WMuxMWg-f7P1caN",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1287.7762858336314,
			"y": 1367.9701684279573,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 82.55259249171831,
			"height": 195.68977109185744,
			"seed": 665375180,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "v5FPnhHGNUkTKtF96zBqY",
				"focus": -0.19989566150602697,
				"gap": 2.7529619201757995
			},
			"endBinding": {
				"elementId": "AiyuY5y1",
				"focus": -0.043889908021133586,
				"gap": 1.2373584280355772
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
					55.5273537970229,
					55.5273537970229
				],
				[
					47.83380477695323,
					135.4733631794836
				],
				[
					-27.025238694695418,
					195.68977109185744
				]
			]
		},
		{
			"type": "arrow",
			"version": 271,
			"versionNonce": 975926772,
			"isDeleted": false,
			"id": "3JvixPBHIZ-trGLTxaIjd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1143.2713651088488,
			"y": 1416.138475336218,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 62.88640068578502,
			"height": 145.17392498739719,
			"seed": 1426494668,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "3YUo9wlHtWJrF8De-IPVf",
				"focus": 0.27816905340273507,
				"gap": 2.428381806649739
			},
			"endBinding": {
				"elementId": "AiyuY5y1",
				"focus": 0.05254397180831714,
				"gap": 3.5848976242350545
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
					-38.13324296903966,
					28.76718329243363
				],
				[
					-43.819779201264964,
					90.98457971560379
				],
				[
					19.066621484520056,
					145.17392498739719
				]
			]
		},
		{
			"type": "text",
			"version": 296,
			"versionNonce": 1759908684,
			"isDeleted": false,
			"id": "AiyuY5y1",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 984.7185481663969,
			"y": 1564.8972979478503,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 449.8729553222656,
			"height": 100,
			"seed": 432122484,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "90Bg37WMuxMWg-f7P1caN",
					"type": "arrow"
				},
				{
					"id": "3JvixPBHIZ-trGLTxaIjd",
					"type": "arrow"
				}
			],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Areas that are too bright immediately\nget mapped to 1, we lose out on a lot of\ndetails in those bright spots.\nLaptop emits light and has light contribution from window\nthus is extremely bright",
			"rawText": "Areas that are too bright immediately\nget mapped to 1, we lose out on a lot of\ndetails in those bright spots.\nLaptop emits light and has light contribution from window\nthus is extremely bright",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Areas that are too bright immediately\nget mapped to 1, we lose out on a lot of\ndetails in those bright spots.\nLaptop emits light and has light contribution from window\nthus is extremely bright",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "image",
			"version": 216,
			"versionNonce": 246454132,
			"isDeleted": false,
			"id": "y539Zccx7hUQIf0_v1_Ms",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1478.64128903285,
			"y": 1290.0929042350188,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 237.2331184739567,
			"height": 237.2331184739567,
			"seed": 565777140,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6aeb4f2d12f3361ea5be0a764f823d3fc856cf67",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 228,
			"versionNonce": 1675479500,
			"isDeleted": false,
			"id": "tvN9XG64",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1446.8852702149854,
			"y": 1562.354167919178,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 328.4647216796875,
			"height": 80,
			"seed": 2050735732,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Too dark!!\nthe extreme range of bright colors makes\nany other color mapped to an extremely\nsmall range!!",
			"rawText": "Too dark!!\nthe extreme range of bright colors makes\nany other color mapped to an extremely\nsmall range!!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Too dark!!\nthe extreme range of bright colors makes\nany other color mapped to an extremely\nsmall range!!",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "text",
			"version": 272,
			"versionNonce": 689277172,
			"isDeleted": false,
			"id": "vWnX2LjA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1344.8771219491668,
			"y": 1654.8972982786934,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 532.4810180664062,
			"height": 60,
			"seed": 1082162292,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "MWspoqwjc2GIxm4RAiu18",
					"type": "arrow"
				}
			],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Human vision is logarithmic not linear!\nThe difference between between 1 to 2 candles\nis more noticeable than the difference between 99 and 100 candles",
			"rawText": "Human vision is logarithmic not linear!\nThe difference between between 1 to 2 candles\nis more noticeable than the difference between 99 and 100 candles",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Human vision is logarithmic not linear!\nThe difference between between 1 to 2 candles\nis more noticeable than the difference between 99 and 100 candles",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 118,
			"versionNonce": 1134211148,
			"isDeleted": false,
			"id": "MWspoqwjc2GIxm4RAiu18",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1618.3483441209648,
			"y": 1725.8027733070774,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 326.17115894425365,
			"height": 124.67624408407096,
			"seed": 1703255924,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "vWnX2LjA",
				"focus": -0.11163719807659536,
				"gap": 10.90547502838399
			},
			"endBinding": {
				"elementId": "6qAyMgeY",
				"focus": 0.16576252409827594,
				"gap": 8.180547551542986
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
					-69.34362967260586,
					115.78947836532893
				],
				[
					-326.17115894425365,
					124.67624408407096
				]
			]
		},
		{
			"type": "text",
			"version": 109,
			"versionNonce": 1558202996,
			"isDeleted": false,
			"id": "6qAyMgeY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1035.5321143097385,
			"y": 1819.3753373755508,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 248.4645233154297,
			"height": 60,
			"seed": 1153563212,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "MWspoqwjc2GIxm4RAiu18",
					"type": "arrow"
				},
				{
					"id": "Yd6cYZFkpKiWfp3Bp0RpL",
					"type": "arrow"
				}
			],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Use a mapping that\nis much more precise towards 0\nto match our vision",
			"rawText": "Use a mapping that\nis much more precise towards 0\nto match our vision",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Use a mapping that\nis much more precise towards 0\nto match our vision",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 104,
			"versionNonce": 402048716,
			"isDeleted": false,
			"id": "mVrSJfnU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1012.5790646617961,
			"y": 1898.9587895028258,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 297.31268310546875,
			"height": 60,
			"seed": 1007696756,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Note: we do not precieve every color\nwith the same brightness (Greens are\na lot more bright)",
			"rawText": "Note: we do not precieve every color\nwith the same brightness (Greens are\na lot more bright)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Note: we do not precieve every color\nwith the same brightness (Greens are\na lot more bright)",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "arrow",
			"version": 62,
			"versionNonce": 483843060,
			"isDeleted": false,
			"id": "XrfdkM8uz8G79MpJPJLZH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 596.5033192776915,
			"y": 1147.1999184517588,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.2462057965846043,
			"height": 158.35750865921,
			"seed": 1241156940,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "QbX7LYSP",
				"focus": 0.01680201502502188,
				"gap": 11.903864654500694
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
					2.2462057965846043,
					158.35750865921
				]
			]
		},
		{
			"type": "arrow",
			"version": 322,
			"versionNonce": 1703677260,
			"isDeleted": false,
			"id": "Yd6cYZFkpKiWfp3Bp0RpL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1027.7748322219231,
			"y": 1882.8323168331956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 263.0957544631709,
			"height": 541.8223839050827,
			"seed": 43346164,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6qAyMgeY",
				"focus": -1.0834627575331721,
				"gap": 7.757282087815383
			},
			"endBinding": {
				"elementId": "QbX7LYSP",
				"focus": -0.6763096377611766,
				"gap": 15.259763305161755
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
					-153.8650970660409,
					-56.15514491461363
				],
				[
					-73.59528177568825,
					-489.4639416489508
				],
				[
					-263.0957544631709,
					-541.8223839050827
				]
			]
		},
		{
			"type": "text",
			"version": 89,
			"versionNonce": 318717300,
			"isDeleted": false,
			"id": "QbX7LYSP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 443.77002246140296,
			"y": 1317.4612917654695,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 305.6492919921875,
			"height": 35,
			"seed": 1342472436,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "XrfdkM8uz8G79MpJPJLZH",
					"type": "arrow"
				},
				{
					"id": "Yd6cYZFkpKiWfp3Bp0RpL",
					"type": "arrow"
				}
			],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Reinhard Tone mapping",
			"rawText": "Reinhard Tone mapping",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Reinhard Tone mapping",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 83,
			"versionNonce": 229934028,
			"isDeleted": false,
			"id": "di78PVQ1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 508.29948989911446,
			"y": 1356.0266740106872,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 180.2096808848058,
			"height": 60.0698936282686,
			"seed": 27289,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "5e473649f738deb0e1412305e8e83f532db35cea",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 48,
			"versionNonce": 949972724,
			"isDeleted": false,
			"id": "lUOv2DVA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 345.2446314701468,
			"y": 1430.1103672638515,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 506.31939697265625,
			"height": 25,
			"seed": 2126065612,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Brings all luminance values into a displayable range",
			"rawText": "Brings all luminance values into a displayable range",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Brings all luminance values into a displayable range",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 915024460,
			"isDeleted": false,
			"id": "xTy1aslF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 343.6746237407042,
			"y": 1455.1103674629926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 509.45941162109375,
			"height": 50,
			"seed": 544813300,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165721,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Low luminance values are scaled with precision ~ 1\nHigh luminance value are scaled with precision ~ 1/L",
			"rawText": "Low luminance values are scaled with precision ~ 1\nHigh luminance value are scaled with precision ~ 1/L",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Low luminance values are scaled with precision ~ 1\nHigh luminance value are scaled with precision ~ 1/L",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 72,
			"versionNonce": 1849520244,
			"isDeleted": false,
			"id": "xxUum5eV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 322.2358419598089,
			"y": 1505.450820579687,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 552.3369750976562,
			"height": 20,
			"seed": 548582644,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Side effect: No value that maps to maximum luminance of 1 (Burnout)",
			"rawText": "Side effect: No value that maps to maximum luminance of 1 (Burnout)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Side effect: No value that maps to maximum luminance of 1 (Burnout)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 533,
			"versionNonce": 853999820,
			"isDeleted": false,
			"id": "aiBWzvjN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 504.16451412000976,
			"y": 1596.6204347242585,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 184.860307636199,
			"height": 49.563995525647556,
			"seed": 1525,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "16f4cb8156437418aad9114ae0a101b08923f140",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 159,
			"versionNonce": 329204212,
			"isDeleted": false,
			"id": "hwr4NdoC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 371.8749264143887,
			"y": 1560.0747504941064,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 449.4394836425781,
			"height": 25,
			"seed": 1997908852,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We use Schlicks method in order to apply this",
			"rawText": "We use Schlicks method in order to apply this",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We use Schlicks method in order to apply this",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 27,
			"versionNonce": 1785005900,
			"isDeleted": false,
			"id": "vSr_bYju5NuDt03TDneS8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 496.4334683742246,
			"y": 1617.9574995962773,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 68.29276749136511,
			"height": 0,
			"seed": 1765145716,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165722,
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
					-68.29276749136511,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 36,
			"versionNonce": 533390196,
			"isDeleted": false,
			"id": "bI4KhqVR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 318.2488203608539,
			"y": 1611.795977865665,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 97.85618591308594,
			"height": 20,
			"seed": 479640140,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "output color",
			"rawText": "output color",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "output color",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 24,
			"versionNonce": 1096695244,
			"isDeleted": false,
			"id": "TkOjJN5M0jlICNW1XXyHb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 691.9762215987034,
			"y": 1636.1091166162093,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 44.48850331145513,
			"height": 4.996035131232929,
			"seed": 1620926796,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165722,
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
					44.48850331145513,
					4.996035131232929
				]
			]
		},
		{
			"type": "text",
			"version": 64,
			"versionNonce": 956716276,
			"isDeleted": false,
			"id": "pilve2aB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 744.3211325909401,
			"y": 1637.4253809321278,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 108.82318115234375,
			"height": 15.115139161772301,
			"seed": 915105652,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 12.092111329417842,
			"fontFamily": 1,
			"text": "avoid division by 0",
			"rawText": "avoid division by 0",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "avoid division by 0",
			"lineHeight": 1.25,
			"baseline": 10
		},
		{
			"type": "text",
			"version": 81,
			"versionNonce": 15508556,
			"isDeleted": false,
			"id": "dZlocMn1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 508.29948998340865,
			"y": 1654.8972978340364,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 208.2084503173828,
			"height": 20,
			"seed": 981601268,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Clamping is still necessary!",
			"rawText": "Clamping is still necessary!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Clamping is still necessary!",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 14,
			"versionNonce": 1289197172,
			"isDeleted": false,
			"id": "83sfasUa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 518.9274459336284,
			"y": 1682.7426804372703,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 208.71545105669048,
			"height": 237.46516435072476,
			"seed": 98062,
			"groupIds": [
				"XJ3wAIsqNKIx-qunNNGLr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0527e0bdaca8da6ee30e9d6b426742e327a78535",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 962,
			"versionNonce": 1055537868,
			"isDeleted": false,
			"id": "R4aGLlxVOG6o6Jupi58Od",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 621.99998388224,
			"y": 1920.9273773951509,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 105.6164428675011,
			"height": 55.85444377849958,
			"seed": 652070220,
			"groupIds": [
				"XJ3wAIsqNKIx-qunNNGLr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
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
					-104.92290112754056,
					2.7399672422026438
				],
				[
					-104.23567543737443,
					-53.114476536296934
				],
				[
					0.6935417399605512,
					-2.7741669598424323
				]
			]
		},
		{
			"type": "line",
			"version": 933,
			"versionNonce": 671393780,
			"isDeleted": false,
			"id": "D8yHZPlo0oY2oN3WHkSHh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 621.0086664053096,
			"y": 1923.7405841213285,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 109.7776933072647,
			"height": 57.58829812840113,
			"seed": 1053705164,
			"groupIds": [
				"XJ3wAIsqNKIx-qunNNGLr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
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
					108.1780183592532,
					1.0997765267576565
				],
				[
					107.1440217991069,
					-56.48852160164347
				],
				[
					-1.5996749480115038,
					-0.5998781055041721
				]
			]
		},
		{
			"type": "line",
			"version": 1038,
			"versionNonce": 1173422412,
			"isDeleted": false,
			"id": "Cbh6-LsLKJ9f9JawR408d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 623.9943634446076,
			"y": 1681.693869270657,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 107.69706808738306,
			"height": 55.85444377849967,
			"seed": 510388812,
			"groupIds": [
				"XJ3wAIsqNKIx-qunNNGLr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
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
					106.09739313937155,
					-1.0997765267577506
				],
				[
					103.32954222932335,
					54.75466725174192
				],
				[
					-1.599674948011505,
					0.5998781055041726
				]
			]
		},
		{
			"type": "line",
			"version": 1128,
			"versionNonce": 244550004,
			"isDeleted": false,
			"id": "TiM3lz2HwlIRNzenl1I98",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 620.5588266699707,
			"y": 1681.219723967603,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 105.61644286750118,
			"height": 54.4078963817617,
			"seed": 949010636,
			"groupIds": [
				"XJ3wAIsqNKIx-qunNNGLr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
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
					-104.01676791948967,
					0.6340778231435706
				],
				[
					-103.67631309930391,
					54.4078963817617
				],
				[
					1.599674948011505,
					0.5998781055041726
				]
			]
		},
		{
			"type": "ellipse",
			"version": 54,
			"versionNonce": 2103113676,
			"isDeleted": false,
			"id": "AjGs5EfqlJ2sfIZ2NUWFF",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 565.3302725885084,
			"y": 1801.005862474873,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 37.742148576891395,
			"height": 32.127614077849785,
			"seed": 17980492,
			"groupIds": [
				"XJ3wAIsqNKIx-qunNNGLr"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "4FXikR2Dwx1J9bQSvxJeT",
					"type": "arrow"
				}
			],
			"updated": 1709320165722,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 114,
			"versionNonce": 1405762292,
			"isDeleted": false,
			"id": "4FXikR2Dwx1J9bQSvxJeT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 565.3302725885084,
			"y": 1824.7116748041603,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 120.4005731461167,
			"height": 76.1081343203432,
			"seed": 1166828020,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "AjGs5EfqlJ2sfIZ2NUWFF",
				"focus": -0.5502022348354865,
				"gap": 1.9608356348903726
			},
			"endBinding": {
				"elementId": "vD201Pms",
				"focus": 0.03887180087929399,
				"gap": 4.604357409053591
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
					-86.71336615186647,
					-5.614534499041611
				],
				[
					-120.4005731461167,
					-76.1081343203432
				]
			]
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 1363287628,
			"isDeleted": false,
			"id": "vD201Pms",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 352.5316387868748,
			"y": 1703.9991830747636,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 168.57635498046875,
			"height": 40,
			"seed": 942244940,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "4FXikR2Dwx1J9bQSvxJeT",
					"type": "arrow"
				}
			],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "details on the screen\nare visible!",
			"rawText": "details on the screen\nare visible!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "details on the screen\nare visible!",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 1915665524,
			"isDeleted": false,
			"id": "9Lkq5dWl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 437.7544709206711,
			"y": 1925.346855686805,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 372.3687438964844,
			"height": 40,
			"seed": 1668439028,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "CueeHbJCREdurNAQxChn_",
					"type": "arrow"
				}
			],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Overall constrant is lowered, can no longer see\nwhite on the screen",
			"rawText": "Overall constrant is lowered, can no longer see\nwhite on the screen",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Overall constrant is lowered, can no longer see\nwhite on the screen",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 196,
			"versionNonce": 444626124,
			"isDeleted": false,
			"id": "CueeHbJCREdurNAQxChn_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 621.7376449594591,
			"y": 1971.5418637593164,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.5046343370008799,
			"height": 84.34067434634676,
			"seed": 394405452,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9Lkq5dWl",
				"focus": 0.012656053688295223,
				"gap": 6.195008072511428
			},
			"endBinding": {
				"elementId": "hfUlgE66",
				"focus": 0.003290415531428155,
				"gap": 10.192765057703127
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
					0.5046343370008799,
					84.34067434634676
				]
			]
		},
		{
			"type": "text",
			"version": 89,
			"versionNonce": 596053492,
			"isDeleted": false,
			"id": "hfUlgE66",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 398.2314664323519,
			"y": 2066.0753031633662,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 446.88189697265625,
			"height": 35,
			"seed": 1241016140,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "CueeHbJCREdurNAQxChn_",
					"type": "arrow"
				}
			],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Extended Reinhard Tone-Mapping",
			"rawText": "Extended Reinhard Tone-Mapping",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Extended Reinhard Tone-Mapping",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 218,
			"versionNonce": 112196428,
			"isDeleted": false,
			"id": "E1R_JelT9qcprtNv54GYq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 513.6400722821181,
			"y": 2102.584041098521,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 216.77213412113807,
			"height": 65.91901154560924,
			"seed": 1553071732,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b558f2aeb012da6276c5f6ff840f7c25fcd39927",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 214,
			"versionNonce": 2027499380,
			"isDeleted": false,
			"id": "1Bi33v6p",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 314.3013890824061,
			"y": 2179.827345420739,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 617.5693359375,
			"height": 60,
			"seed": 1148781684,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Parameter Lwhite is the smallest luminance that will be mapped to pure white\nwhich is often set to the highest luminance in the scene\nA blend between ERT and Linear mapping. ",
			"rawText": "Parameter Lwhite is the smallest luminance that will be mapped to pure white\nwhich is often set to the highest luminance in the scene\nA blend between ERT and Linear mapping. ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Parameter Lwhite is the smallest luminance that will be mapped to pure white\nwhich is often set to the highest luminance in the scene\nA blend between ERT and Linear mapping. ",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 168,
			"versionNonce": 2798028,
			"isDeleted": false,
			"id": "zrolzKnX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 524.998691332045,
			"y": 2246.083556217107,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 220.50151676758793,
			"height": 251.8317682507524,
			"seed": 8909,
			"groupIds": [
				"BCTID34jmP1LTfvYa9w7-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "dc36b6bc596ddcd7612e9b35c9c2ecdc72915278",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 1173,
			"versionNonce": 1919623412,
			"isDeleted": false,
			"id": "yjIIJEos4zsgCYsswdfl7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 633.6337456894936,
			"y": 2499.0454264389527,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 113.66991642563964,
			"height": 55.85444377849958,
			"seed": 358512716,
			"groupIds": [
				"BCTID34jmP1LTfvYa9w7-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
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
					-112.66323223087231,
					1.4873974229755245
				],
				[
					-111.97600654070618,
					-54.36704635552405
				],
				[
					1.006684194767331,
					-1.4093578726742635
				]
			]
		},
		{
			"type": "line",
			"version": 1059,
			"versionNonce": 369793100,
			"isDeleted": false,
			"id": "2fbUr1Q9yXUyoAY-T2k7y",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 638.7570931795925,
			"y": 2498.4489516709186,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 109.7776933072647,
			"height": 57.58829812840113,
			"seed": 234983116,
			"groupIds": [
				"BCTID34jmP1LTfvYa9w7-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
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
					108.1780183592532,
					1.0997765267576565
				],
				[
					107.1440217991069,
					-56.48852160164347
				],
				[
					-1.5996749480115038,
					-0.5998781055041721
				]
			]
		},
		{
			"type": "line",
			"version": 1254,
			"versionNonce": 398647924,
			"isDeleted": false,
			"id": "L6m4G-VZWd7qVjnqNpPFR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 636.0445429235864,
			"y": 2245.6592484164225,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 112.08794312896305,
			"height": 55.85444377849967,
			"seed": 1593693516,
			"groupIds": [
				"BCTID34jmP1LTfvYa9w7-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
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
					112.08794312896305,
					-0.5988992809386673
				],
				[
					109.32009221891485,
					55.255544497561004
				],
				[
					0,
					1.9813596323820093
				]
			]
		},
		{
			"type": "line",
			"version": 1239,
			"versionNonce": 1680453324,
			"isDeleted": false,
			"id": "UQuuyW3-lfGxH99scmi2G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 630.5944079831642,
			"y": 2244.585225007864,
			"strokeColor": "transparent",
			"backgroundColor": "#ffffff",
			"width": 108.69855785120706,
			"height": 54.848198522290886,
			"seed": 95243212,
			"groupIds": [
				"BCTID34jmP1LTfvYa9w7-"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
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
					-105.99812755187202,
					1.0743799636727545
				],
				[
					-105.65767273168626,
					54.848198522290886
				],
				[
					2.7004302993350393,
					1.0401802460332874
				]
			]
		},
		{
			"type": "text",
			"version": 91,
			"versionNonce": 262566900,
			"isDeleted": false,
			"id": "Fpg4jNSR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 451.8154091282606,
			"y": 2503.3432222725824,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 369.95916748046875,
			"height": 13.84511352447203,
			"seed": 1855596236,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 11.076090819577624,
			"fontFamily": 1,
			"text": "Reinhard Tone-Mapping is a popular choice but there are many more",
			"rawText": "Reinhard Tone-Mapping is a popular choice but there are many more",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Reinhard Tone-Mapping is a popular choice but there are many more",
			"lineHeight": 1.25,
			"baseline": 9
		},
		{
			"type": "text",
			"version": 290,
			"versionNonce": 2065823052,
			"isDeleted": false,
			"id": "k3Ae1Tv8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 438.36820389003833,
			"y": 2519.293595010931,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 402.98345947265625,
			"height": 31.976858292519402,
			"seed": 983801588,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 8.527162211338508,
			"fontFamily": 1,
			"text": "Filmic Tone-Mappings (Not physically accurate, but is made to look aesthetically pleasing) \nCamera Response Functions (Made to Tone-Map response of a real camera)\nLocal Tone mappings (Depending on pixel position can be more realistic to simulate human vision)",
			"rawText": "Filmic Tone-Mappings (Not physically accurate, but is made to look aesthetically pleasing) \nCamera Response Functions (Made to Tone-Map response of a real camera)\nLocal Tone mappings (Depending on pixel position can be more realistic to simulate human vision)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Filmic Tone-Mappings (Not physically accurate, but is made to look aesthetically pleasing) \nCamera Response Functions (Made to Tone-Map response of a real camera)\nLocal Tone mappings (Depending on pixel position can be more realistic to simulate human vision)",
			"lineHeight": 1.25,
			"baseline": 28
		},
		{
			"type": "arrow",
			"version": 86,
			"versionNonce": 941348212,
			"isDeleted": false,
			"id": "LGjylE-SSdgmzXxxjyUS_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 0.6648529058127224,
			"y": 761.3207510198429,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 7.681019312495209,
			"height": 401.9733440205814,
			"seed": 1512960204,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "82R1zxKB",
				"focus": 0.031307067390952376,
				"gap": 15.627264975624144
			},
			"endBinding": {
				"elementId": "KEuML9ol",
				"focus": 0.01975122895263484,
				"gap": 8.706954454040442
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
					7.681019312495209,
					401.9733440205814
				]
			]
		},
		{
			"type": "text",
			"version": 46,
			"versionNonce": 1213033420,
			"isDeleted": false,
			"id": "KEuML9ol",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -102.80394351914708,
			"y": 1167.0010494944647,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 219.9969482421875,
			"height": 35,
			"seed": 1297782348,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "LGjylE-SSdgmzXxxjyUS_",
					"type": "arrow"
				}
			],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Color Correction",
			"rawText": "Color Correction",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Color Correction",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 223,
			"versionNonce": 1047070452,
			"isDeleted": false,
			"id": "g69K26SN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -307.3237446651059,
			"y": 1205.7080032177694,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 631.3392333984375,
			"height": 75,
			"seed": 1517627340,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "NUMY9s8Pil-kp23P9vqck",
					"type": "arrow"
				}
			],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "The coordinates of one color w.r.t to a certain space is\nhighly different from that same color in a different color space\nif color is not specified we assume sRGB",
			"rawText": "The coordinates of one color w.r.t to a certain space is\nhighly different from that same color in a different color space\nif color is not specified we assume sRGB",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "The coordinates of one color w.r.t to a certain space is\nhighly different from that same color in a different color space\nif color is not specified we assume sRGB",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 41,
			"versionNonce": 2110132812,
			"isDeleted": false,
			"id": "NUMY9s8Pil-kp23P9vqck",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 12.50715050767701,
			"y": 1288.9735597329159,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 77.7796350670842,
			"seed": 1500794740,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165722,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "g69K26SN",
				"focus": -0.013182385169267547,
				"gap": 8.2655565151465
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
					0,
					77.7796350670842
				]
			]
		},
		{
			"type": "text",
			"version": 133,
			"versionNonce": 924059764,
			"isDeleted": false,
			"id": "dxW92IhB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -252.69255619647691,
			"y": 1380.110366770879,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 530.3994140625,
			"height": 50,
			"seed": 1542098932,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "SRGB dates back to 1995 where screens need gamma\ncorrection! we need to account for those changes",
			"rawText": "SRGB dates back to 1995 where screens need gamma\ncorrection! we need to account for those changes",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SRGB dates back to 1995 where screens need gamma\ncorrection! we need to account for those changes",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 42,
			"versionNonce": 2053499084,
			"isDeleted": false,
			"id": "5tfzaemr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -261.8933925473498,
			"y": 1431.5759433942135,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 548.8010864257812,
			"height": 20,
			"seed": 1889119988,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Image color must be gamma encoded before being sent to the display",
			"rawText": "Image color must be gamma encoded before being sent to the display",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Image color must be gamma encoded before being sent to the display",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 75,
			"versionNonce": 904059380,
			"isDeleted": false,
			"id": "nKVMMWVI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -41.79157434276738,
			"y": 1453.0415185465217,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 108.59745144905756,
			"height": 34.97206063613718,
			"seed": 89524,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "57eda99c7c0e95c71e8be2882cbab808b1650c1e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 48,
			"versionNonce": 835120972,
			"isDeleted": false,
			"id": "o7hGL1q8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -123.87773460263976,
			"y": 1495.4508206529772,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 262.14453125,
			"height": 20,
			"seed": 881281652,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "store the gamma encoded version",
			"rawText": "store the gamma encoded version",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "store the gamma encoded version",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 116,
			"versionNonce": 1708882804,
			"isDeleted": false,
			"id": "DbX-i2xEOmCAuvKiUGPAk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -217.72132565270226,
			"y": 1535.4018483752284,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 187.68718074435958,
			"height": 183.0447416446758,
			"seed": 1124517196,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1eefc6fef2c04f8f54be494d68c5de1bf55bd438",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 125,
			"versionNonce": 339944908,
			"isDeleted": false,
			"id": "NODB4LIX0yr6s7WT7xu0t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 38.110492841321665,
			"y": 1533.7103453999089,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 188.40401270590542,
			"height": 186.42774683836095,
			"seed": 1800294988,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xcLc2TXX15SVWqfmjGvCG",
					"type": "arrow"
				}
			],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "126eca767037b861eb439d5f120d9434d6cd44a3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 210,
			"versionNonce": 558099700,
			"isDeleted": false,
			"id": "xcLc2TXX15SVWqfmjGvCG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 12.368650553349255,
			"y": 1722.2848857646763,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.5554301339402059,
			"height": 100.53285424317005,
			"seed": 567970292,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NODB4LIX0yr6s7WT7xu0t",
				"focus": 1.2719015909570641,
				"gap": 25.741842287972418
			},
			"endBinding": {
				"elementId": "g5kAk01z",
				"focus": 0.0007406343720166607,
				"gap": 13.923839687262216
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
					0.5554301339402059,
					100.53285424317005
				]
			]
		},
		{
			"type": "text",
			"version": 143,
			"versionNonce": 1995738188,
			"isDeleted": false,
			"id": "g5kAk01z",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -277.29555441911253,
			"y": 1836.7415796951086,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 580.4392700195312,
			"height": 50,
			"seed": 1101543284,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "xcLc2TXX15SVWqfmjGvCG",
					"type": "arrow"
				}
			],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Remember to discretize after encoding to able to store it\nin 24bits",
			"rawText": "Remember to discretize after encoding to able to store it\nin 24bits",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Remember to discretize after encoding to able to store it\nin 24bits",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 54,
			"versionNonce": 161623668,
			"isDeleted": false,
			"id": "nVIb4Agb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -222.03565122383247,
			"y": 1886.741579678805,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 469.9194641113281,
			"height": 50,
			"seed": 2079462004,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Gamma encoding before discretization allocates\nmore bits to darker parts of an image",
			"rawText": "Gamma encoding before discretization allocates\nmore bits to darker parts of an image",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Gamma encoding before discretization allocates\nmore bits to darker parts of an image",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 143,
			"versionNonce": 2075468492,
			"isDeleted": false,
			"id": "MzBNe1u2-bG03qbwYIiL2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -189.60416539019783,
			"y": 1945.3468562982898,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 403.94563201084594,
			"height": 165.2000892121209,
			"seed": 1943795316,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "3773f74cf1a231ecfd1694f64e0e0db7d4f2bc38",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 158,
			"versionNonce": 532430836,
			"isDeleted": false,
			"id": "wMPUuB5OSv_imqEBZy2tc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -219.0788441326921,
			"y": 2135.543546988317,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 462.8949897639442,
			"height": 132.41204198921335,
			"seed": 1995614452,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2e85a3cc4f4db04a51667efe9237d207067fa773",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 163,
			"versionNonce": 2032068940,
			"isDeleted": false,
			"id": "n5jnT9ZVSkuUY3HeRPjV5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 0.6875374170618898,
			"y": 761.6027429879252,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 596.915492427287,
			"height": 247.65642770919362,
			"seed": 207113292,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "82R1zxKB",
				"focus": -0.06669187670869209,
				"gap": 15.90925694370651
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
					-74.08525615232281,
					127.00329626112489
				],
				[
					-536.5889267032527,
					125.94493545894886
				],
				[
					-596.915492427287,
					247.65642770919362
				]
			]
		},
		{
			"type": "text",
			"version": 17,
			"versionNonce": 1536696692,
			"isDeleted": false,
			"id": "RtofhKFG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -679.198135686358,
			"y": 1016.7353195221411,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 157.55665588378906,
			"height": 35,
			"seed": 457379188,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Compression",
			"rawText": "Compression",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Compression",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 181,
			"versionNonce": 1653333964,
			"isDeleted": false,
			"id": "O3RW7x8H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -885.4429838477809,
			"y": 1051.7353200254954,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 575.1793212890625,
			"height": 100,
			"seed": 990107764,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "E_dlWj8gwBl69i2OaHEIW",
					"type": "arrow"
				}
			],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "we want to reduce Storage size and number\nof bits to send in a network!\nHigh resolutions with 3bytes per pixel needs a lot of\nstorage which is often unnecessary and impractically large",
			"rawText": "we want to reduce Storage size and number\nof bits to send in a network!\nHigh resolutions with 3bytes per pixel needs a lot of\nstorage which is often unnecessary and impractically large",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "we want to reduce Storage size and number\nof bits to send in a network!\nHigh resolutions with 3bytes per pixel needs a lot of\nstorage which is often unnecessary and impractically large",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 24,
			"versionNonce": 1148965620,
			"isDeleted": false,
			"id": "gRsWKgy9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -777.3590578842156,
			"y": 1156.728009636675,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 372.7686767578125,
			"height": 20,
			"seed": 32949620,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "E_dlWj8gwBl69i2OaHEIW",
					"type": "arrow"
				},
				{
					"id": "_6S-XmLk_mJPLQgI8ZDly",
					"type": "arrow"
				}
			],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Images usually only contain a subset of colors",
			"rawText": "Images usually only contain a subset of colors",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Images usually only contain a subset of colors",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 224,
			"versionNonce": 806749772,
			"isDeleted": false,
			"id": "E_dlWj8gwBl69i2OaHEIW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -895.0239475221163,
			"y": 1100.667974928198,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 148.096663580724,
			"height": 0.9434329248492759,
			"seed": 1813700940,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "O3RW7x8H",
				"focus": -0.01803659976835667,
				"gap": 9.580963674335294
			},
			"endBinding": {
				"elementId": "g2jDG5T7",
				"focus": -0.012623256054376862,
				"gap": 9.77583107287046
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
					-148.096663580724,
					-0.9434329248492759
				]
			]
		},
		{
			"type": "text",
			"version": 263,
			"versionNonce": 149771380,
			"isDeleted": false,
			"id": "g2jDG5T7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1624.4558904178982,
			"y": 1060.8380920900754,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 571.5594482421875,
			"height": 75,
			"seed": 1688938484,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "E_dlWj8gwBl69i2OaHEIW",
					"type": "arrow"
				},
				{
					"id": "avxfDgxg8qJKCVJ9zjsru",
					"type": "arrow"
				}
			],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Create a color table with 256 entries is often sufficient\nEvery entry in the table contains a 24bit color\neach pixel contains an 8bit pointer to the table color",
			"rawText": "Create a color table with 256 entries is often sufficient\nEvery entry in the table contains a 24bit color\neach pixel contains an 8bit pointer to the table color",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Create a color table with 256 entries is often sufficient\nEvery entry in the table contains a 24bit color\neach pixel contains an 8bit pointer to the table color",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 119,
			"versionNonce": 1184324812,
			"isDeleted": false,
			"id": "avxfDgxg8qJKCVJ9zjsru",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1368.3116986908058,
			"y": 1147.0477491294853,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.781008114230417,
			"height": 82.94763433538515,
			"seed": 541444428,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "g2jDG5T7",
				"focus": 0.10208997288602943,
				"gap": 11.209657039409876
			},
			"endBinding": {
				"elementId": "zOUR3xfh",
				"focus": -0.000969295234350279,
				"gap": 6.13898010206708
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
					-0.781008114230417,
					82.94763433538515
				]
			]
		},
		{
			"type": "text",
			"version": 75,
			"versionNonce": 380806644,
			"isDeleted": false,
			"id": "zOUR3xfh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1749.7915325758725,
			"y": 1236.1343635669375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 761.0791015625,
			"height": 100,
			"seed": 787028044,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "avxfDgxg8qJKCVJ9zjsru",
					"type": "arrow"
				},
				{
					"id": "CMcx7OpM87aM9sfR9W8oF",
					"type": "arrow"
				}
			],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "How to generate color table?\n\nQuantization of the colors into representative colors!\nResulting 256 colors are usually enough for reasonable image representation",
			"rawText": "How to generate color table?\n\nQuantization of the colors into representative colors!\nResulting 256 colors are usually enough for reasonable image representation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "How to generate color table?\n\nQuantization of the colors into representative colors!\nResulting 256 colors are usually enough for reasonable image representation",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "arrow",
			"version": 209,
			"versionNonce": 1604969292,
			"isDeleted": false,
			"id": "CMcx7OpM87aM9sfR9W8oF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -978.9234054486074,
			"y": 1291.6200463449486,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 220.10152458812843,
			"height": 1.5026361495076799,
			"seed": 513968076,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zOUR3xfh",
				"focus": 0.1549302344380037,
				"gap": 9.789025564764984
			},
			"endBinding": {
				"elementId": "MI2PGLp6",
				"focus": -0.13303107827529093,
				"gap": 4.049097274810947
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
					220.10152458812843,
					-1.5026361495076799
				]
			]
		},
		{
			"type": "arrow",
			"version": 134,
			"versionNonce": 852608884,
			"isDeleted": false,
			"id": "_6S-XmLk_mJPLQgI8ZDly",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -604.5689704718282,
			"y": 1192.3636696311917,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.985468612519071,
			"height": 69.45412797630456,
			"seed": 155120972,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "gRsWKgy9",
				"focus": 0.0748312434712179,
				"gap": 15.635659994516573
			},
			"endBinding": {
				"elementId": "MI2PGLp6",
				"focus": 0.046964143937184975,
				"gap": 7.3243871042345745
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
					0.985468612519071,
					69.45412797630456
				]
			]
		},
		{
			"type": "text",
			"version": 132,
			"versionNonce": 1906809292,
			"isDeleted": false,
			"id": "MI2PGLp6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -754.772783585668,
			"y": 1269.1421847117308,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 289.4652099609375,
			"height": 35,
			"seed": 611371852,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "_6S-XmLk_mJPLQgI8ZDly",
					"type": "arrow"
				},
				{
					"id": "CMcx7OpM87aM9sfR9W8oF",
					"type": "arrow"
				}
			],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Median Cut algorithm",
			"rawText": "Median Cut algorithm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Median Cut algorithm",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 458,
			"versionNonce": 294697204,
			"isDeleted": false,
			"id": "mXIEqu8j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -925.2419432783018,
			"y": 1311.1343644121387,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 639.4593505859375,
			"height": 275,
			"seed": 1628382964,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rY2vyK3__oo7jtiPP3NOf",
					"type": "arrow"
				},
				{
					"id": "8Q6RirfCMFHPdaF4UV7e8",
					"type": "arrow"
				}
			],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Every pixel color is a point in the RGB cube\nwe take axis aligned bounding boxes for all the color points\nin this space, then we compute:\n\n1) Find the cube with the biggest diagonal (biggest variance)\n\n2) find its longest edge of the rectangle\n\n3) Divide it into 2 boxes according to the median\n\n4) once you have 256 boxes, point each one to the center color",
			"rawText": "Every pixel color is a point in the RGB cube\nwe take axis aligned bounding boxes for all the color points\nin this space, then we compute:\n\n1) Find the cube with the biggest diagonal (biggest variance)\n\n2) find its longest edge of the rectangle\n\n3) Divide it into 2 boxes according to the median\n\n4) once you have 256 boxes, point each one to the center color",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Every pixel color is a point in the RGB cube\nwe take axis aligned bounding boxes for all the color points\nin this space, then we compute:\n\n1) Find the cube with the biggest diagonal (biggest variance)\n\n2) find its longest edge of the rectangle\n\n3) Divide it into 2 boxes according to the median\n\n4) once you have 256 boxes, point each one to the center color",
			"lineHeight": 1.25,
			"baseline": 268
		},
		{
			"type": "text",
			"version": 85,
			"versionNonce": 397049932,
			"isDeleted": false,
			"id": "zySIveuk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -911.5252290879841,
			"y": 1212.3896733634297,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 279.3445739746094,
			"height": 20,
			"seed": 1927620852,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "how is the reduction typically done?",
			"rawText": "how is the reduction typically done?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "how is the reduction typically done?",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 962,
			"versionNonce": 755772603,
			"isDeleted": false,
			"id": "rY2vyK3__oo7jtiPP3NOf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -942.8090165263677,
			"y": 1570.5342749606978,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 305.662134449482,
			"height": 1.0004426084597071,
			"seed": 737258996,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709569296486,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "mXIEqu8j",
				"focus": -0.8718801185361844,
				"gap": 17.567073248065867
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
					-305.662134449482,
					1.0004426084597071
				]
			]
		},
		{
			"type": "text",
			"version": 420,
			"versionNonce": 824939765,
			"isDeleted": false,
			"id": "HSs4CkXH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2118.8784956462973,
			"y": 1550.4081006035447,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.21649169921875,
			"height": 35,
			"seed": 1622440820,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569346170,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Dithering",
			"rawText": "Dithering",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Dithering",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 526,
			"versionNonce": 423046741,
			"isDeleted": false,
			"id": "83jcboTd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2426.065753373466,
			"y": 1601.5566112793601,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 720.6991577148438,
			"height": 100,
			"seed": 1026466804,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569346170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Dithering is a type of noise to randomize quantization error\nthat creates the illusion of color depth with a limited color table\nHumans do not look at individual colors but a combination of neighbouring\ncolors!",
			"rawText": "Dithering is a type of noise to randomize quantization error\nthat creates the illusion of color depth with a limited color table\nHumans do not look at individual colors but a combination of neighbouring\ncolors!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Dithering is a type of noise to randomize quantization error\nthat creates the illusion of color depth with a limited color table\nHumans do not look at individual colors but a combination of neighbouring\ncolors!",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 231,
			"versionNonce": 870833484,
			"isDeleted": false,
			"id": "qq74oHDd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1168.2359775307596,
			"y": 1493.8845603838809,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 197.7924041748047,
			"height": 60,
			"seed": 1615694156,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "what if my output device\nhas only a limited\namount of colors?",
			"rawText": "what if my output device\nhas only a limited\namount of colors?",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "what if my output device\nhas only a limited\namount of colors?",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 274,
			"versionNonce": 1803833557,
			"isDeleted": false,
			"id": "5v9Hqd2O",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1468.8380598372423,
			"y": 1542.7863298858283,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 193.14480590820312,
			"height": 70,
			"seed": 1365342836,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "rY2vyK3__oo7jtiPP3NOf",
					"type": "arrow"
				}
			],
			"updated": 1709569288418,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Naive Solution\nRounding",
			"rawText": "Naive Solution\nRounding",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Naive Solution\nRounding",
			"lineHeight": 1.25,
			"baseline": 60
		},
		{
			"type": "text",
			"version": 267,
			"versionNonce": 617442869,
			"isDeleted": false,
			"id": "MNwk1oGc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1550.8716082907208,
			"y": 1618.1325571337736,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 360.59954833984375,
			"height": 50,
			"seed": 905818100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569288418,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Round everything above 0.5 to white\nand everything below 0.5 to black",
			"rawText": "Round everything above 0.5 to white\nand everything below 0.5 to black",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Round everything above 0.5 to white\nand everything below 0.5 to black",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 271,
			"versionNonce": 1779261979,
			"isDeleted": false,
			"id": "mh3ACwNrVr0wXi7UsJACu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1494.574377735767,
			"y": 1672.5858314697173,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 271.7863969643135,
			"height": 271.7863969643135,
			"seed": 2057654516,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "vWED5zYFVv9IZwDfRE-ZU",
					"type": "arrow"
				}
			],
			"updated": 1709569352170,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "51b1ad8e59234b6bc48d6b78756c2f90e5e97b54",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 177,
			"versionNonce": 1034824629,
			"isDeleted": false,
			"id": "fPAX8pQD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1414.0617738260853,
			"y": 1943.522895943517,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 112.45985412597656,
			"height": 25,
			"seed": 184333388,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569288418,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "this is bad!",
			"rawText": "this is bad!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "this is bad!",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 373,
			"versionNonce": 591961013,
			"isDeleted": false,
			"id": "Ycyx3w5F",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2229.674974129888,
			"y": 1836.0036720823011,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 339.8094482421875,
			"height": 35,
			"seed": 672218484,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569346170,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Floyd Steinberg Algorithm",
			"rawText": "Floyd Steinberg Algorithm",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Floyd Steinberg Algorithm",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "image",
			"version": 430,
			"versionNonce": 931486997,
			"isDeleted": false,
			"id": "GtzVkV0c-u9AIOZZM_01s",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2363.457388479757,
			"y": 1701.5566112457414,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 607.3742774316527,
			"height": 108.95817282317269,
			"seed": 961462988,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569346170,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e0b0ac862baa9ed6747cfff917a997be0a156f2f",
			"scale": [
				1,
				-1
			]
		},
		{
			"type": "text",
			"version": 389,
			"versionNonce": 493023861,
			"isDeleted": false,
			"id": "JyGHu5Mk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2329.1478023822956,
			"y": 1882.7780646602362,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 527.4993896484375,
			"height": 50,
			"seed": 1585918412,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569346170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Decide on a specific mask usually specially crafted\n    for example purposes we are using this one",
			"rawText": "1) Decide on a specific mask usually specially crafted\n    for example purposes we are using this one",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Decide on a specific mask usually specially crafted\n    for example purposes we are using this one",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "image",
			"version": 383,
			"versionNonce": 296147925,
			"isDeleted": false,
			"id": "QpcgEdVGYeWLwzjCXWQCY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2128.5734777416747,
			"y": 1942.0556931509816,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 146.57064165156916,
			"height": 65.90406549081347,
			"seed": 77725132,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569346170,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1e8da59bb635d4d9d734608f716111d2e5c5fa03",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 315,
			"versionNonce": 476485941,
			"isDeleted": false,
			"id": "wkZizNottaNYvdF791Bsz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2037.0902457599536,
			"y": 1951.0202314949977,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 122.33040277046246,
			"height": 30.329851926560877,
			"seed": 1424859892,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709569346170,
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
					58.63771372468443,
					-11.120945706405564
				],
				[
					122.33040277046246,
					19.208906220155313
				]
			]
		},
		{
			"type": "text",
			"version": 304,
			"versionNonce": 654813845,
			"isDeleted": false,
			"id": "fqVeKKVR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1962.4929504032996,
			"y": 1972.6741623940595,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 97.48820495605469,
			"height": 20,
			"seed": 1192605940,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569346170,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "current pixel",
			"rawText": "current pixel",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "current pixel",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 325,
			"versionNonce": 1379897333,
			"isDeleted": false,
			"id": "KahqntJj1H7MU49fKC2-I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2077.5300483287015,
			"y": 1946.4707537060137,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 79.36311254116777,
			"height": 12.637438302733699,
			"seed": 792245068,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709569346170,
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
					-29.31885686234216,
					-12.131940770624169
				],
				[
					-79.36311254116777,
					0.5054975321095299
				]
			]
		},
		{
			"type": "text",
			"version": 308,
			"versionNonce": 202623317,
			"isDeleted": false,
			"id": "41SdbhDN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2216.0996115904345,
			"y": 1946.9762512381233,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 70.89613342285156,
			"height": 40,
			"seed": 383028812,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569346170,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "already\ncomputed",
			"rawText": "already\ncomputed",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "already\ncomputed",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 297,
			"versionNonce": 1708775093,
			"isDeleted": false,
			"id": "uiUWPl8p",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2303.499955673499,
			"y": 2038.601806501358,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 487.45941162109375,
			"height": 50,
			"seed": 33354188,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569346170,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2) Spread every quantization error to neighboring\npixels according to a mask",
			"rawText": "2) Spread every quantization error to neighboring\npixels according to a mask",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2) Spread every quantization error to neighboring\npixels according to a mask",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 305,
			"versionNonce": 708261909,
			"isDeleted": false,
			"id": "6DXQooIB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -2276.186692343423,
			"y": 2088.6018067347377,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 432.8328857421875,
			"height": 40,
			"seed": 1368928756,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709569346170,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "If a pixel is rounded downwards, it becomes more likely\nthat a neighboring pixel is rounded upwards",
			"rawText": "If a pixel is rounded downwards, it becomes more likely\nthat a neighboring pixel is rounded upwards",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "If a pixel is rounded downwards, it becomes more likely\nthat a neighboring pixel is rounded upwards",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 104,
			"versionNonce": 1766053876,
			"isDeleted": false,
			"id": "8Q6RirfCMFHPdaF4UV7e8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -610.4983441293759,
			"y": 1595.4749055179057,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 2.364126816341809,
			"height": 219.57046347003643,
			"seed": 957773556,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "mXIEqu8j",
				"focus": 0.010600649787325863,
				"gap": 9.340541105766988
			},
			"endBinding": {
				"elementId": "5swaUqzf",
				"focus": -0.04789915019141242,
				"gap": 4.722115028276221
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
					-2.364126816341809,
					219.57046347003643
				]
			]
		},
		{
			"type": "text",
			"version": 67,
			"versionNonce": 528273740,
			"isDeleted": false,
			"id": "5swaUqzf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -729.6322476237455,
			"y": 1819.7674840162183,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 244.80502319335938,
			"height": 35,
			"seed": 526508916,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "8Q6RirfCMFHPdaF4UV7e8",
					"type": "arrow"
				}
			],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "JPEG compression",
			"rawText": "JPEG compression",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "JPEG compression",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 258,
			"versionNonce": 1080867188,
			"isDeleted": false,
			"id": "Pvf1KJhu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -958.3528438874923,
			"y": 1854.7674842528668,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 708.0191650390625,
			"height": 100,
			"seed": 536910284,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Algorithms for compressing images in full color\nOptimized for smooth color transitions with few sharp edges (not really\nsuited for texts and synthetic images)\nThis process is made up of 5 steps",
			"rawText": "Algorithms for compressing images in full color\nOptimized for smooth color transitions with few sharp edges (not really\nsuited for texts and synthetic images)\nThis process is made up of 5 steps",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Algorithms for compressing images in full color\nOptimized for smooth color transitions with few sharp edges (not really\nsuited for texts and synthetic images)\nThis process is made up of 5 steps",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 181,
			"versionNonce": 1424803788,
			"isDeleted": false,
			"id": "r8Q3QwKz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -930.7700686371775,
			"y": 1993.6933635990931,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 638.1793212890625,
			"height": 75,
			"seed": 588236236,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "DTUti_4iNDc-d6HRZpq2K",
					"type": "arrow"
				}
			],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Step 1: \nConversion from RGB to YCrCb color space\nY = Luminance    Cr= Red Chrominance     Cb= Blue Chrominance",
			"rawText": "Step 1: \nConversion from RGB to YCrCb color space\nY = Luminance    Cr= Red Chrominance     Cb= Blue Chrominance",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Step 1: \nConversion from RGB to YCrCb color space\nY = Luminance    Cr= Red Chrominance     Cb= Blue Chrominance",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 666,
			"versionNonce": 1297906124,
			"isDeleted": false,
			"id": "Y4kmZ2Ty",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1583.1261143426393,
			"y": 2147.0899867784265,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 570.6793212890625,
			"height": 100,
			"seed": 33604980,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "DTUti_4iNDc-d6HRZpq2K",
					"type": "arrow"
				}
			],
			"updated": 1709320575761,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Step 2: \nChroma sub-sampling\nLossy reduction of the amount of values we store\n CR and CB are averaged over small regions in the image",
			"rawText": "Step 2: \nChroma sub-sampling\nLossy reduction of the amount of values we store\n CR and CB are averaged over small regions in the image",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Step 2: \nChroma sub-sampling\nLossy reduction of the amount of values we store\n CR and CB are averaged over small regions in the image",
			"lineHeight": 1.25,
			"baseline": 93
		},
		{
			"type": "text",
			"version": 296,
			"versionNonce": 1981410892,
			"isDeleted": false,
			"id": "yIsaOxsT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -882.8923201015263,
			"y": 2075.2152743870333,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 553.3931274414062,
			"height": 60,
			"seed": 287338740,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "No information is lost here! but we convert our data into\nLuminance which humans are sensitive to and we dont want to give up\nred/blue chrominance which we can afford losing some of!",
			"rawText": "No information is lost here! but we convert our data into\nLuminance which humans are sensitive to and we dont want to give up\nred/blue chrominance which we can afford losing some of!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "No information is lost here! but we convert our data into\nLuminance which humans are sensitive to and we dont want to give up\nred/blue chrominance which we can afford losing some of!",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "image",
			"version": 609,
			"versionNonce": 58453108,
			"isDeleted": false,
			"id": "YX-3otTxeos_7ZcTtqRXQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1760.0359344748756,
			"y": 2293.7109965296495,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 403.2228041024131,
			"height": 86.44396614407228,
			"seed": 20276172,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "010f1c6d94d56fd545bee1737f2f4c0c80b811bc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 571,
			"versionNonce": 1943946444,
			"isDeleted": false,
			"id": "fQbs3EnN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1596.4899926119867,
			"y": 2269.4468880420263,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 72.01991271972656,
			"height": 25,
			"seed": 63840372,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "No loss",
			"rawText": "No loss",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "No loss",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "image",
			"version": 486,
			"versionNonce": 1940798964,
			"isDeleted": false,
			"id": "N8Guh9mgVCXrNg7EL4W6l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1266.0215831056246,
			"y": 2260.860603753654,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 341.06436278600654,
			"height": 65.7007837661429,
			"seed": 1363162100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "lDJjb8pBxkeXBw-gFYBsb",
					"type": "arrow"
				}
			],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f0f5100a4664a60e57d551f493fb78e00b7416fd",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 554,
			"versionNonce": 702215884,
			"isDeleted": false,
			"id": "HU_Wqjae2BDjJtITHpArr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1275.5595628459557,
			"y": 2311.7192519497567,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 360.14032367617875,
			"height": 64.2225542906766,
			"seed": 513781620,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "75RCOHkH5lT0y_JOHeDuY",
					"type": "arrow"
				},
				{
					"id": "lDJjb8pBxkeXBw-gFYBsb",
					"type": "arrow"
				},
				{
					"id": "pQgbfRxWmdHAqkNefJY4D",
					"type": "arrow"
				}
			],
			"updated": 1709320542762,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1a840a0a481d5267ce1f41e67dbcd1977b067baf",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 610,
			"versionNonce": 479879028,
			"isDeleted": false,
			"id": "bYW68d6XWDNl_YBZWKMqh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1268.7738733571152,
			"y": 2367.7403279015707,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 351.6939866150294,
			"height": 54.67511556620206,
			"seed": 1466007028,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6439629eb58b293c56041e4094a4640aa98e99fd",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 814,
			"versionNonce": 1481933260,
			"isDeleted": false,
			"id": "75RCOHkH5lT0y_JOHeDuY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1363.851750458394,
			"y": 2347.2558254502865,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 83.7215331822888,
			"height": 0.8248426914510674,
			"seed": 2123498100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "HU_Wqjae2BDjJtITHpArr",
				"focus": -0.2662965675132144,
				"gap": 4.570654430149375
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
					59.80109513020636,
					-0.4124213457253063
				],
				[
					83.7215331822888,
					0.41242134572576106
				]
			]
		},
		{
			"type": "arrow",
			"version": 868,
			"versionNonce": 1720078580,
			"isDeleted": false,
			"id": "lDJjb8pBxkeXBw-gFYBsb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1363.0269077669427,
			"y": 2346.0185614131096,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 93.61964547970229,
			"height": 46.60361206698826,
			"seed": 2090934476,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "HU_Wqjae2BDjJtITHpArr",
				"focus": 1.2052475704813006,
				"gap": 12.304302603635051
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
					47.42845475843956,
					-7.0111628773343
				],
				[
					59.38867378448049,
					-42.066977264007164
				],
				[
					93.61964547970229,
					-46.60361206698826
				]
			]
		},
		{
			"type": "arrow",
			"version": 536,
			"versionNonce": 1752852556,
			"isDeleted": false,
			"id": "sw9CxFPsZrFj75OFa7uCY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1362.2020650754919,
			"y": 2348.679869858279,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 94.03206682542859,
			"height": 54.027196290048764,
			"seed": 569144692,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165723,
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
					47.42845475843995,
					7.011162877334358
				],
				[
					60.21351647593217,
					50.315404178518705
				],
				[
					94.03206682542859,
					54.027196290048764
				]
			]
		},
		{
			"type": "text",
			"version": 325,
			"versionNonce": 1457461748,
			"isDeleted": false,
			"id": "QJdzRdmz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -678.363635711904,
			"y": 2337.360988330729,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 311.8596496582031,
			"height": 50,
			"seed": 365510516,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "QTYLqjPruCTKA8bfAN3l0",
					"type": "arrow"
				}
			],
			"updated": 1709320591703,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Step 3:\nDiscrete Cosine Transformation",
			"rawText": "Step 3:\nDiscrete Cosine Transformation",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Step 3:\nDiscrete Cosine Transformation",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "arrow",
			"version": 309,
			"versionNonce": 2015329996,
			"isDeleted": false,
			"id": "DTUti_4iNDc-d6HRZpq2K",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -949.3738908476435,
			"y": 2058.6944139867846,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 353.4454779763471,
			"height": 86.63631021979859,
			"seed": 1597826380,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320165723,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "r8Q3QwKz",
				"focus": -0.6271285126334137,
				"gap": 18.603822210465978
			},
			"endBinding": {
				"elementId": "Y4kmZ2Ty",
				"focus": -0.10097705988911782,
				"gap": 1.7592625718434647
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
					-310.5106693718453,
					2.3000790323840192
				],
				[
					-353.4454779763471,
					86.63631021979859
				]
			]
		},
		{
			"type": "ellipse",
			"version": 44,
			"versionNonce": 1605513332,
			"isDeleted": false,
			"id": "Rd_Kgu0T-8ldNewxI3JeU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1571.3887876485535,
			"y": 2326.935884763347,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 47.786782429718414,
			"height": 48.51635162711864,
			"seed": 717275852,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320273389,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 69,
			"versionNonce": 48889676,
			"isDeleted": false,
			"id": "Qk02thp2enVKtBhlD-iox",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1474.5384766936663,
			"y": 2328.9422000561976,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 47.786782429718414,
			"height": 48.51635162711864,
			"seed": 498275572,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320278536,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 105,
			"versionNonce": 1299356788,
			"isDeleted": false,
			"id": "xK7C0lYln567Q_K_hUs14",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1463.8331590256323,
			"y": 2374.3647216560016,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 116.00132396120375,
			"height": 32.166744945914616,
			"seed": 985434100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320290764,
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
					-9.650023483774248,
					28.145901827675516
				],
				[
					-116.00132396120375,
					32.166744945914616
				]
			]
		},
		{
			"type": "line",
			"version": 39,
			"versionNonce": 562286284,
			"isDeleted": false,
			"id": "f_X_G2pzNsKqXorz1PxUE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1547.0646115731859,
			"y": 2375.973058903297,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 33.77508219321021,
			"height": 28.950070451322972,
			"seed": 1108787828,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320292868,
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
					-7.6396019246546985,
					15.882330317045216
				],
				[
					-33.77508219321021,
					28.950070451322972
				]
			]
		},
		{
			"type": "text",
			"version": 70,
			"versionNonce": 1653138932,
			"isDeleted": false,
			"id": "JK24Kb3N",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1756.7742094066484,
			"y": 2381.803281424744,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 167.3123321533203,
			"height": 60,
			"seed": 1302301644,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320318847,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "for each 2x2 pixel\nwe store 4Y 4Cr 4Cb\nvalues",
			"rawText": "for each 2x2 pixel\nwe store 4Y 4Cr 4Cb\nvalues",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "for each 2x2 pixel\nwe store 4Y 4Cr 4Cb\nvalues",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "ellipse",
			"version": 54,
			"versionNonce": 776654964,
			"isDeleted": false,
			"id": "HTHXtk36Hwp4CfPrW193D",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1106.954072210704,
			"y": 2327.1790497932598,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 41.304099307528304,
			"height": 22.83640105945051,
			"seed": 1019720140,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320439074,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 149,
			"versionNonce": 1418774004,
			"isDeleted": false,
			"id": "80Yis0VA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1137.452344497988,
			"y": 2313.482129688012,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 108.54731750488281,
			"height": 11.201801958156627,
			"seed": 2085201740,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320458448,
			"link": null,
			"locked": false,
			"fontSize": 8.961441566525302,
			"fontFamily": 1,
			"text": "share same cr cb values",
			"rawText": "share same cr cb values",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "share same cr cb values",
			"lineHeight": 1.25,
			"baseline": 8
		},
		{
			"type": "arrow",
			"version": 97,
			"versionNonce": 111096140,
			"isDeleted": false,
			"id": "ipcqaiTfW9nt1kSmc5ZO2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -950.9613934705346,
			"y": 2288.895416397576,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 59.464811319506225,
			"height": 1.3061605052675986,
			"seed": 1757720780,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320544898,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "DpYOPV2L",
				"focus": 1.3714685305310015,
				"gap": 7.49668715909047
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
					40.81751578961348,
					1.3061605052675986
				],
				[
					59.464811319506225,
					1.3061605052675986
				]
			]
		},
		{
			"type": "text",
			"version": 23,
			"versionNonce": 1732486772,
			"isDeleted": false,
			"id": "4nCEHS2d",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -884.7757226714041,
			"y": 2279.7522928607027,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 17.184036254882812,
			"height": 20,
			"seed": 1412308340,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709320538024,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Cr",
			"rawText": "Cr",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cr",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 123,
			"versionNonce": 94268108,
			"isDeleted": false,
			"id": "pQgbfRxWmdHAqkNefJY4D",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -950.5466142472144,
			"y": 2303.059385745027,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 58.47976231404391,
			"height": 1.3061605052675986,
			"seed": 1548766708,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320544897,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "HU_Wqjae2BDjJtITHpArr",
				"focus": -1.198972520637321,
				"gap": 8.65986620472927
			},
			"endBinding": {
				"elementId": "DpYOPV2L",
				"focus": -0.04492840421412438,
				"gap": 7.081907935770232
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
					40.81751578961348,
					1.3061605052675986
				],
				[
					58.47976231404391,
					1.3061605052675986
				]
			]
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 375837772,
			"isDeleted": false,
			"id": "DpYOPV2L",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -884.9849439974003,
			"y": 2293.9162622081535,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 18.432037353515625,
			"height": 20,
			"seed": 1182429044,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "pQgbfRxWmdHAqkNefJY4D",
					"type": "arrow"
				},
				{
					"id": "ipcqaiTfW9nt1kSmc5ZO2",
					"type": "arrow"
				}
			],
			"updated": 1709320544895,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Cb",
			"rawText": "Cb",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cb",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 307,
			"versionNonce": 1385711732,
			"isDeleted": false,
			"id": "QTYLqjPruCTKA8bfAN3l0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1022.7200474109685,
			"y": 2203.3935261250467,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 502.89811247237037,
			"height": 126.3345003965137,
			"seed": 228369612,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320591703,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "QJdzRdmz",
				"focus": 0.10529976407569692,
				"gap": 7.632961809168592
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
					450.7136464207066,
					12.9498445586878
				],
				[
					502.89811247237037,
					126.3345003965137
				]
			]
		},
		{
			"type": "text",
			"version": 87,
			"versionNonce": 1503063924,
			"isDeleted": false,
			"id": "9NMmxaSp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -789.7096910813186,
			"y": 2389.2866092971103,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 550.939453125,
			"height": 75,
			"seed": 733274828,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "lcuai1bYWEb0HpTnb0LbW",
					"type": "arrow"
				}
			],
			"updated": 1709320887533,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Tiling the image into small blocks typically 8x8 or 16x16\nthen we Convert the blocks into frequency space\nColor values are transformed into interval [-128,127]",
			"rawText": "Tiling the image into small blocks typically 8x8 or 16x16\nthen we Convert the blocks into frequency space\nColor values are transformed into interval [-128,127]",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Tiling the image into small blocks typically 8x8 or 16x16\nthen we Convert the blocks into frequency space\nColor values are transformed into interval [-128,127]",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 1923165973,
			"isDeleted": false,
			"id": "GrkfxX25",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -801.0234984984756,
			"y": 2465.069758245784,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 572.8971557617188,
			"height": 40,
			"seed": 740956492,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709570086143,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Since humans are limited for high spatial frequencies, the DCT restricts\nlossy operations to high frequencies",
			"rawText": "Since humans are limited for high spatial frequencies, the DCT restricts\nlossy operations to high frequencies",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Since humans are limited for high spatial frequencies, the DCT restricts\nlossy operations to high frequencies",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "arrow",
			"version": 231,
			"versionNonce": 1864781044,
			"isDeleted": false,
			"id": "lcuai1bYWEb0HpTnb0LbW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -234.40522675476433,
			"y": 2407.585662677922,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 92.11847272252803,
			"height": 1.2027942993895522,
			"seed": 1717706444,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1709320970763,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "9NMmxaSp",
				"focus": -0.5561199143154762,
				"gap": 4.365011201554296
			},
			"endBinding": {
				"elementId": "35Uokia6",
				"focus": 0.12258495090126736,
				"gap": 3.570350404870595
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
					92.11847272252803,
					1.2027942993895522
				]
			]
		},
		{
			"type": "text",
			"version": 244,
			"versionNonce": 1187068916,
			"isDeleted": false,
			"id": "35Uokia6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -138.7164036273657,
			"y": 2349.3694783423257,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 266.54461669921875,
			"height": 140,
			"seed": 431237324,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "lcuai1bYWEb0HpTnb0LbW",
					"type": "arrow"
				}
			],
			"updated": 1709320967365,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Why?\nWell if the the blocks are\ntoo small we aren't really doing\nanything and if blocks are too big\nthen theres more of a chance\nthat we encounter high frequency\nthat we do want to encode",
			"rawText": "Why?\nWell if the the blocks are\ntoo small we aren't really doing\nanything and if blocks are too big\nthen theres more of a chance\nthat we encounter high frequency\nthat we do want to encode",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Why?\nWell if the the blocks are\ntoo small we aren't really doing\nanything and if blocks are too big\nthen theres more of a chance\nthat we encounter high frequency\nthat we do want to encode",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"type": "image",
			"version": 97,
			"versionNonce": 1340588788,
			"isDeleted": false,
			"id": "rlCYk-pvQ_nFoR6aAW_cc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -775.5989983317405,
			"y": 2507.8300606438056,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 535.7671957430405,
			"height": 70.22642930312423,
			"seed": 1619435508,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709321031769,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "f08dd78ab34febe50a3ff7381066a9c819b29c1e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 469,
			"versionNonce": 1096855669,
			"isDeleted": false,
			"id": "99nzJ0YO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -814.4545378564301,
			"y": 2582.778527563544,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 610.9293212890625,
			"height": 140,
			"seed": 2041383500,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "DPzx5VVmAZmAjjxSmN3Vj",
					"type": "arrow"
				}
			],
			"updated": 1709571379079,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "smooth image content leads to small differences which results\nin coefficients for high frequencies to be negligible thus we can\ndescribe our data in a way that later on allows us to ignore\nhigh frequencies without it affecting the human perception.\nYoure more likely to encounter blocks of the image where little to no\nhigh frequency being described and that can be minimized! but in other regions\nit might be important to keep to jump between colors!",
			"rawText": "smooth image content leads to small differences which results\nin coefficients for high frequencies to be negligible thus we can\ndescribe our data in a way that later on allows us to ignore\nhigh frequencies without it affecting the human perception.\nYoure more likely to encounter blocks of the image where little to no\nhigh frequency being described and that can be minimized! but in other regions\nit might be important to keep to jump between colors!",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "smooth image content leads to small differences which results\nin coefficients for high frequencies to be negligible thus we can\ndescribe our data in a way that later on allows us to ignore\nhigh frequencies without it affecting the human perception.\nYoure more likely to encounter blocks of the image where little to no\nhigh frequency being described and that can be minimized! but in other regions\nit might be important to keep to jump between colors!",
			"lineHeight": 1.25,
			"baseline": 134
		},
		{
			"id": "vWED5zYFVv9IZwDfRE-ZU",
			"type": "arrow",
			"x": -1491.4609495360894,
			"y": 1951.0239984047876,
			"width": 483.33333333333303,
			"height": 392.2222222222222,
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
			"seed": 2145253077,
			"version": 155,
			"versionNonce": 1346177397,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1709569358115,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-131.11111111111086,
					-38.888888888888914
				],
				[
					-145.55555555555543,
					-359.9999999999998
				],
				[
					-483.33333333333303,
					-392.2222222222222
				]
			],
			"lastCommittedPoint": [
				-483.33333333333303,
				-392.2222222222222
			],
			"startBinding": {
				"elementId": "mh3ACwNrVr0wXi7UsJACu",
				"focus": -1.0325100973233712,
				"gap": 6.651769970756732
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "bzqYiTW_fKIrimOe3QKgo",
			"type": "arrow",
			"x": -814.8717531264144,
			"y": 2557.748172290798,
			"width": 520.4671088841997,
			"height": 99.13659216841916,
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
			"seed": 867358331,
			"version": 159,
			"versionNonce": 1813941627,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1709570352000,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-465.5109545299674,
					-11.853288194050492
				],
				[
					-520.4671088841997,
					87.28330397436866
				]
			],
			"lastCommittedPoint": [
				-520.4671088841997,
				87.28330397436866
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "kw8ZeyBw",
				"focus": -0.12080084070641918,
				"gap": 3.1184885056877647
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "kw8ZeyBw",
			"type": "text",
			"x": -1422.3423808073285,
			"y": 2648.1499647708542,
			"width": 174.58070373535156,
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
			"seed": 277705499,
			"version": 49,
			"versionNonce": 495265307,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "bzqYiTW_fKIrimOe3QKgo",
					"type": "arrow"
				}
			],
			"updated": 1709570352000,
			"link": null,
			"locked": false,
			"text": "Quantization",
			"rawText": "Quantization",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Quantization",
			"lineHeight": 1.25
		},
		{
			"id": "54VVCwov",
			"type": "text",
			"x": -1693.3002177608248,
			"y": 2702.265609810465,
			"width": 713.0991821289062,
			"height": 100,
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
			"seed": 1113698933,
			"version": 294,
			"versionNonce": 207959963,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "-29oKFYtYR3ddsuUYAzZF",
					"type": "arrow"
				}
			],
			"updated": 1709571472559,
			"link": null,
			"locked": false,
			"text": "Takes in multiple DCT coefficients and combines them into groups\nof constant value that way we do not have to store as much\nto describe the data, higher coefficients get larger groups while smaller\ncoefficients get more detail",
			"rawText": "Takes in multiple DCT coefficients and combines them into groups\nof constant value that way we do not have to store as much\nto describe the data, higher coefficients get larger groups while smaller\ncoefficients get more detail",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 93,
			"containerId": null,
			"originalText": "Takes in multiple DCT coefficients and combines them into groups\nof constant value that way we do not have to store as much\nto describe the data, higher coefficients get larger groups while smaller\ncoefficients get more detail",
			"lineHeight": 1.25
		},
		{
			"id": "_GKvJWabj0ZJVkIOXVpio",
			"type": "image",
			"x": -1510.6416281305378,
			"y": 2810.8269306032844,
			"width": 346.85939613679074,
			"height": 237.7511520223332,
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
			"seed": 291173307,
			"version": 117,
			"versionNonce": 1337550459,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709570476440,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e8ee0efb19565fbd32e0da5150e94d78d3282ca1",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "XSiSuww1",
			"type": "text",
			"x": -1639.5054205551387,
			"y": 3049.467200218559,
			"width": 602.059326171875,
			"height": 75,
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
			"seed": 2135442363,
			"version": 48,
			"versionNonce": 2098029563,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709570558297,
			"link": null,
			"locked": false,
			"text": "The number of quantization levels is the main parameter for\ncontrolling the compression and quality of the image\n",
			"rawText": "The number of quantization levels is the main parameter for\ncontrolling the compression and quality of the image\n",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "The number of quantization levels is the main parameter for\ncontrolling the compression and quality of the image\n",
			"lineHeight": 1.25
		},
		{
			"id": "nQwIzKxAHH2XcJnPYarWz",
			"type": "image",
			"x": -1484.5138679699055,
			"y": 3110.241311388795,
			"width": 298.923678889894,
			"height": 66.31584136716977,
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
			"seed": 1390076219,
			"version": 123,
			"versionNonce": 1627379483,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709570572043,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9581418968868cf54a89f7999015fe96a9d45cf1",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "QJ5epKVd",
			"type": "text",
			"x": -1665.4010545921537,
			"y": 3178.221967779024,
			"width": 659.185302734375,
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
			"seed": 823576827,
			"version": 37,
			"versionNonce": 877436955,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709570648201,
			"link": null,
			"locked": false,
			"text": "Specific quantization tables (different in brightness and chroma)\nhave been designed to minimize the visible loss of information (for human observers)",
			"rawText": "Specific quantization tables (different in brightness and chroma)\nhave been designed to minimize the visible loss of information (for human observers)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "Specific quantization tables (different in brightness and chroma)\nhave been designed to minimize the visible loss of information (for human observers)",
			"lineHeight": 1.25
		},
		{
			"id": "DPzx5VVmAZmAjjxSmN3Vj",
			"type": "arrow",
			"x": -200.96791935532178,
			"y": 2673.1790861008994,
			"width": 76.34192522406772,
			"height": 0.5229583622599421,
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
			"seed": 804021659,
			"version": 108,
			"versionNonce": 725408213,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1709571379080,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					76.34192522406772,
					0.5229583622599421
				]
			],
			"lastCommittedPoint": [
				88.57398088813022,
				0.6108550406074755
			],
			"startBinding": {
				"elementId": "99nzJ0YO",
				"focus": 0.25370937980451236,
				"gap": 2.557297212045796
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "U9jaJ8Fs",
			"type": "text",
			"x": -148.17062886432052,
			"y": 2649.267842838847,
			"width": 252.33656311035156,
			"height": 60,
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
			"seed": 152897883,
			"version": 131,
			"versionNonce": 1266653717,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709570840639,
			"link": null,
			"locked": false,
			"text": "the closer the colors are\nto each other the less\n\"high frequency\" there is in block",
			"rawText": "the closer the colors are\nto each other the less\n\"high frequency\" there is in block",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 54,
			"containerId": null,
			"originalText": "the closer the colors are\nto each other the less\n\"high frequency\" there is in block",
			"lineHeight": 1.25
		},
		{
			"id": "2GicTw7C",
			"type": "text",
			"x": -623.1567768270206,
			"y": 2826.0854294623086,
			"width": 226.9409637451172,
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
			"seed": 1355343829,
			"version": 79,
			"versionNonce": 1657189333,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "-29oKFYtYR3ddsuUYAzZF",
					"type": "arrow"
				}
			],
			"updated": 1709571478928,
			"link": null,
			"locked": false,
			"text": "Entropy Encoding",
			"rawText": "Entropy Encoding",
			"fontSize": 28,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 25,
			"containerId": null,
			"originalText": "Entropy Encoding",
			"lineHeight": 1.25
		},
		{
			"id": "-29oKFYtYR3ddsuUYAzZF",
			"type": "arrow",
			"x": -963.5862453029861,
			"y": 2761.5344841044116,
			"width": 461.68438785782354,
			"height": 68.980914402684,
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
			"seed": 486026197,
			"version": 157,
			"versionNonce": 1808494901,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1709571478928,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					416.2224610575755,
					-5.429969044786958
				],
				[
					461.68438785782354,
					63.550945357897035
				]
			],
			"lastCommittedPoint": [
				465.11017389026756,
				91.17544351695096
			],
			"startBinding": {
				"elementId": "54VVCwov",
				"focus": 0.2586775885084816,
				"gap": 16.614790328932486
			},
			"endBinding": {
				"elementId": "2GicTw7C",
				"focus": 0.15981006959980404,
				"gap": 1
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "yBN2m2le",
			"type": "text",
			"x": -829.1751274050176,
			"y": 2860.1472176271814,
			"width": 651.21923828125,
			"height": 75,
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
			"seed": 1116184917,
			"version": 201,
			"versionNonce": 432959515,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709571556557,
			"link": null,
			"locked": false,
			"text": "We Serialize the data by traversing the quantization table from\nlow spatial frequency to high spatial frequency and forming blocks\nof data containing the frequencies",
			"rawText": "We Serialize the data by traversing the quantization table from\nlow spatial frequency to high spatial frequency and forming blocks\nof data containing the frequencies",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 68,
			"containerId": null,
			"originalText": "We Serialize the data by traversing the quantization table from\nlow spatial frequency to high spatial frequency and forming blocks\nof data containing the frequencies",
			"lineHeight": 1.25
		},
		{
			"id": "uKUG6kSUJh6QA2B7K4uGj",
			"type": "image",
			"x": -589.2541004790223,
			"y": 2938.4362153792285,
			"width": 208.6696862043012,
			"height": 168.22982453680098,
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
			"seed": 295658843,
			"version": 106,
			"versionNonce": 1793959157,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709571562251,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "29357b030b9cb32a53d3c306425c9d7b60ced8f7",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "jbMj7eYB",
			"type": "text",
			"x": -779.0679648573075,
			"y": 3108.989377198484,
			"width": 576.359375,
			"height": 25,
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
			"seed": 1606472315,
			"version": 24,
			"versionNonce": 973384219,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709571583440,
			"link": null,
			"locked": false,
			"text": "The blocks are transformed into a sequential bit stream ",
			"rawText": "The blocks are transformed into a sequential bit stream ",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "The blocks are transformed into a sequential bit stream ",
			"lineHeight": 1.25
		},
		{
			"id": "783eSoqz",
			"type": "text",
			"x": -854.7105185585173,
			"y": 3131.2597558119705,
			"width": 759.5853881835938,
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
			"seed": 41506773,
			"version": 22,
			"versionNonce": 1317497365,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709571598500,
			"link": null,
			"locked": false,
			"text": "DC coefficients are encoded differentially (difference to previous DC coefficient is often small)",
			"rawText": "DC coefficients are encoded differentially (difference to previous DC coefficient is often small)",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "DC coefficients are encoded differentially (difference to previous DC coefficient is often small)",
			"lineHeight": 1.25
		},
		{
			"id": "Gw27F-BWVrkpWy0DwnwPf",
			"type": "ellipse",
			"x": -511.94931020390663,
			"y": 3001.8924018218104,
			"width": 95.95736847637207,
			"height": 94.8458931658351,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 573884021,
			"version": 107,
			"versionNonce": 411171483,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "pMLzPlVCiB9OuYi5XhC7w",
					"type": "arrow"
				}
			],
			"updated": 1709571672704,
			"link": null,
			"locked": false
		},
		{
			"id": "pMLzPlVCiB9OuYi5XhC7w",
			"type": "arrow",
			"x": -420.43784296968295,
			"y": 3028.938301044881,
			"width": 157.45900232609313,
			"height": 38.53114409862064,
			"angle": 0,
			"strokeColor": "#e03131",
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
			"seed": 719756501,
			"version": 112,
			"versionNonce": 1547267995,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1709571675181,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					60.019666769004914,
					-38.53114409862064
				],
				[
					157.45900232609313,
					-23.3409815212799
				]
			],
			"lastCommittedPoint": [
				157.45900232609313,
				-23.3409815212799
			],
			"startBinding": {
				"elementId": "Gw27F-BWVrkpWy0DwnwPf",
				"focus": 0.13386788020327384,
				"gap": 1
			},
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "DRRQKFfD",
			"type": "text",
			"x": -360.4609579173587,
			"y": 3010.0432207657495,
			"width": 270.5445556640625,
			"height": 40,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 321581301,
			"version": 85,
			"versionNonce": 1713050773,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1709571700230,
			"link": null,
			"locked": false,
			"text": "large spatial frequencies usually\ncontaining long sequences of zeros",
			"rawText": "large spatial frequencies usually\ncontaining long sequences of zeros",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "large spatial frequencies usually\ncontaining long sequences of zeros",
			"lineHeight": 1.25
		},
		{
			"id": "AaIbQt9C",
			"type": "text",
			"x": -364.41818383007256,
			"y": 2980.4071569462603,
			"width": 8.000015258789062,
			"height": 20,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 759690741,
			"version": 2,
			"versionNonce": 1170930107,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1709571673047,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "center",
			"verticalAlign": "middle",
			"baseline": 14,
			"containerId": "pMLzPlVCiB9OuYi5XhC7w",
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 505.8361959959524,
		"scrollY": -2836.844107140956,
		"zoom": {
			"value": 2.6991152853860774
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