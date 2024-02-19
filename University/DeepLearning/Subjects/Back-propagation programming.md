---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Weight matrix ^b97d1hun

Weight matrix at Position i
are the weights connecting
i-th layer with i+1 layer ^LhfC4eO2

neurons in (rows)
x
neurons out (columns) ^s0gY3zLp

W[0 , 1 , 2]
is
w12 of layer 0->1 ^cTaD5Ny0

Bias Matrix ^Shh1gvGd

Bias matrix at position i
is the biases of layer i+1 ^xWT3G0J1

number of neurons ^xYRWKZzd

X input ^4NirUuqd

input is of size
batchsize x input_neurons ^xJKLpU03

Activations matrix ^wjyTXESI

Activations matrix at position i
is the activation of neuron k of layer i ^wtEiIVwf

number of neurons ^E251H5ok

def forward(self, x):
        """Computes the forward pass layer by layer. Stores the activation after every layer in self.A.
        x : np.ndarray The input to the neural network of size (batch_size, in_neurons)
        y : np.ndarray The output tensor of size (batch_size, out_neurons)
        """

        # Input layer
        self.A=[x]
        batches = x
        Y=[]

        # Iterate over all layers of W, Each layer describes the weight connecting between to layers

        for k,w_layer in enumerate(self.W[:len(self.W)-1]):

                activations = []
                # for each batch we compute the weighted sum and activate it via relu and append them to each other

                for batch in batches:
                        weighted = batch.dot(w_layer)+self.B[k]
                        relu = np.maximum(0,weighted)
                        activations.append(relu)
                # store the batches
                batches=activations
                self.A.append(activations)
        # compute the output
        for batch in self.A[-1]:
                Y.append(batch.dot(self.W[-1])+self.B[-1])
                
        return Y ^6bWaG2Sb

Put the input in as it is ^NxNoUFhy

go over every layers weight matrix of size (input,output)
input being the layer behind and output being the layer in front ^QtxxJ2ue

for each batch we process it individually to make it easier to understand
each batch is of size input neurons ^o8EqUcZp

a dot product between (1, n_i) and (n_i, n_k) will do matrix multiplication
which means every row in the first matrix (that being an individual element xi)
will be multiplied with an individual column (which contains all weights from neuron n_i
to every neuron in n_k) in the end we achieve: (1,n_k) which is the sum of all xi
multiplied with the weight from ni to n_k (we add the biases at the end ofc) ^kTKICkZk

We compute the last layer since thats not in A instead its in Y ^wcJrhRXh

Relu ^K5Mgay6Q

def backward(self, y, t):
        """Computes the backward pass of every layer and returns it in reverse order (from back to front).
        y : np.ndarray The output of the neural network of size (batch_size, out_neurons)
        t : np.ndarray The target of size (batch_size, out_neurons)
        """

        self.DW = []
        self.DB = []
        
        lastLayerLoss = 2 * (y - t) / y.shape[0] # initialize as MSE derivative

        # go through the network in reverse order and compute the gradients

        for i in reversed(range(len(self.W))):

                # compute the gradients
                dloss_dW = np.dot(self.A[i].T, lastLayerLoss)
                dloss_dB = np.sum(lastLayerLoss, axis=0)

                # store the gradients
                self.DW.append(dloss_dW)
                self.DB.append(dloss_dB)

                # compute the gradient for the next layer
                lastLayerLoss = np.dot(lastLayerLoss, self.W[i].T) * self._relu_derivative(self.A[i])

        # reverse the gradients
        self.DW.reverse()
        self.DB.reverse() ^SL2TTBFG

Derivative of loss w.r.t y ^CL3K7bvu

Compute from last layer onwards ^pC3LOUV6

First iteration -> E/y * y/w = loss_derivative * a -> E/y * y/b = loss_derivative * 1
Middle iterations -> delta_layer_before * relu_layer_before * y/w  ^bV45LE1u

lastlayerloss = (batchsize, output neurons)
self.A[n] = (batchsize, previousLayerNeurons)

in order to get it to match the weight matrix which is
(input,output) we transpose A and multiply them ^tW0oKK4b

lastlayerloss = (batchsize, output neurons)
self.W[i] = (input neurons, output neurons)
self.relu_derivative(self.A[i]).shape = self.A[i].shape = (batchsize, input neurons)

in order to get it to match the lastlayerloss which is
(batchsize, output neurons) we transpose W and multiply them ^lymzXekM

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.20",
	"elements": [
		{
			"type": "line",
			"version": 458,
			"versionNonce": 117322421,
			"isDeleted": false,
			"id": "KwbOLp3KtwougE_0v9P1H",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -77.99249234659987,
			"y": -254.01744062800282,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 117.02217577084423,
			"height": 114.76188582931229,
			"seed": 1816511067,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708359020053,
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
					-113.4577187036067,
					-15.703640549606433
				],
				[
					-112.94446354671703,
					-114.76188582931229
				],
				[
					3.5644570672375266,
					-106.54980331907757
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 76,
			"versionNonce": 356204315,
			"isDeleted": false,
			"id": "YjoWqsbgd6zpaKLNOR23N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -200.51815859456224,
			"y": -290.11748543882595,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 78.42405041968084,
			"height": 24.433623748845264,
			"seed": 1977745211,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": null,
			"updated": 1708359020053,
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
					78.42405041968084,
					-24.433623748845264
				]
			]
		},
		{
			"type": "line",
			"version": 482,
			"versionNonce": 1584403477,
			"isDeleted": false,
			"id": "Cb_r49yiBx3CUl01HAdjL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -156.34808992714167,
			"y": -197.16032238157345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 179.14303142765027,
			"height": 164.29616288898768,
			"seed": 79586427,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708359020053,
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
					-173.6863934852054,
					-22.48174877089079
				],
				[
					-172.9006784350841,
					-164.29616288898768
				],
				[
					5.456637942444871,
					-152.53952752168425
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 277,
			"versionNonce": 257598395,
			"isDeleted": false,
			"id": "p6MxG4YUMexmHUF_siL9l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -293.07768188587204,
			"y": -262.9788114009856,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 60.64664983725373,
			"height": 18.09481835091742,
			"seed": 363153659,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": null,
			"updated": 1708359020053,
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
					60.64664983725373,
					-18.09481835091742
				]
			]
		},
		{
			"type": "line",
			"version": 445,
			"versionNonce": 601803125,
			"isDeleted": false,
			"id": "hzmNwtlmxL1eqosd_CxAq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -271.0611719111454,
			"y": -177.38078837501888,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 117.02217577084423,
			"height": 114.76188582931229,
			"seed": 252641077,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708359020053,
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
					-113.4577187036067,
					-15.703640549606433
				],
				[
					-112.94446354671703,
					-114.76188582931229
				],
				[
					3.5644570672375266,
					-106.54980331907757
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 51,
			"versionNonce": 627340379,
			"isDeleted": false,
			"id": "b97d1hun",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -281.36715722425845,
			"y": -435.95097885438247,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 132.9598388671875,
			"height": 25,
			"seed": 95267573,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": null,
			"updated": 1708359020053,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Weight matrix",
			"rawText": "Weight matrix",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Weight matrix",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 680514261,
			"isDeleted": false,
			"id": "LhfC4eO2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -276.1735855816123,
			"y": -103.07964101948244,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 267.61968994140625,
			"height": 75,
			"seed": 2073857269,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "o-_G0L8jvYm4wkIzSG2uV",
					"type": "arrow"
				}
			],
			"updated": 1708359020053,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Weight matrix at Position i\nare the weights connecting\ni-th layer with i+1 layer",
			"rawText": "Weight matrix at Position i\nare the weights connecting\ni-th layer with i+1 layer",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Weight matrix at Position i\nare the weights connecting\ni-th layer with i+1 layer",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "arrow",
			"version": 236,
			"versionNonce": 1194012923,
			"isDeleted": false,
			"id": "o-_G0L8jvYm4wkIzSG2uV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -349.5140452849467,
			"y": -191.3211242775531,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 64.60367918273329,
			"height": 129.05231039336533,
			"seed": 1979270843,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708359020053,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "LhfC4eO2",
				"focus": -0.590850725593775,
				"gap": 8.736780520601087
			},
			"lastCommittedPoint": [
				72.51527832098867,
				89.98883936219073
			],
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					4.052792908556455,
					111.07724729011801
				],
				[
					64.60367918273329,
					129.05231039336533
				]
			]
		},
		{
			"type": "text",
			"version": 256,
			"versionNonce": 2031661109,
			"isDeleted": false,
			"id": "s0gY3zLp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -559.6971127122524,
			"y": -273.19944149542084,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 168.73631286621094,
			"height": 60,
			"seed": 1824192987,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": null,
			"updated": 1708359020053,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "neurons in (rows)\nx\nneurons out (columns)",
			"rawText": "neurons in (rows)\nx\nneurons out (columns)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "neurons in (rows)\nx\nneurons out (columns)",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 1177639323,
			"isDeleted": false,
			"id": "cTaD5Ny0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -542.233099869154,
			"y": -197.16032225058828,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 133.80828857421875,
			"height": 60,
			"seed": 1264723451,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": null,
			"updated": 1708359020053,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "W[0 , 1 , 2]\nis\nw12 of layer 0->1",
			"rawText": "W[0 , 1 , 2]\nis\nw12 of layer 0->1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "W[0 , 1 , 2]\nis\nw12 of layer 0->1",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 85,
			"versionNonce": 1935597973,
			"isDeleted": false,
			"id": "Shh1gvGd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -866.6833328779145,
			"y": -336.9407345687747,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 93.84022521972656,
			"height": 20,
			"seed": 862282779,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": null,
			"updated": 1708359020053,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Bias Matrix",
			"rawText": "Bias Matrix",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bias Matrix",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 307,
			"versionNonce": 531197499,
			"isDeleted": false,
			"id": "-beBK1KX52wsu03rD9-Lx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -829.6719340097482,
			"y": -169.20292344455598,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 51.037076868674035,
			"height": 86.81646978200004,
			"seed": 1698084149,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708359020053,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "xLgUh80_Wv6cRv9eISicA",
				"focus": 0.15044484699820718,
				"gap": 14.1641382356963
			},
			"endBinding": null,
			"lastCommittedPoint": [
				60.99553089182996,
				74.68840517366937
			],
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-6.050268394835143,
					78.10282251173865
				],
				[
					44.98680847383889,
					86.81646978200004
				]
			]
		},
		{
			"type": "text",
			"version": 230,
			"versionNonce": 479717109,
			"isDeleted": false,
			"id": "xWT3G0J1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -767.0815091476164,
			"y": -103.54816846176226,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 198.81643676757812,
			"height": 40,
			"seed": 1807138357,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": null,
			"updated": 1708359020053,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Bias matrix at position i\nis the biases of layer i+1",
			"rawText": "Bias matrix at position i\nis the biases of layer i+1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bias matrix at position i\nis the biases of layer i+1",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 318,
			"versionNonce": 108392155,
			"isDeleted": false,
			"id": "xYRWKZzd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.008038172914641706,
			"x": -886.2731078700599,
			"y": -298.5482486609138,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 140.3042755126953,
			"height": 20,
			"seed": 1934360187,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708359020054,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "number of neurons",
			"rawText": "number of neurons",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "number of neurons",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 38,
			"versionNonce": 927547477,
			"isDeleted": false,
			"id": "4NirUuqd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -304.02161778885,
			"y": 36.97241654954354,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 68.19992065429688,
			"height": 25,
			"seed": 1609957397,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": null,
			"updated": 1708359020054,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "X input",
			"rawText": "X input",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "X input",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "rectangle",
			"version": 87,
			"versionNonce": 757685115,
			"isDeleted": false,
			"id": "YJnc3XPyItcq-CFu2Gy-m",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -922.5553124321311,
			"y": -269.4842328555025,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 219.13744450844945,
			"height": 27.68051930633044,
			"seed": 629155163,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": null,
			"updated": 1708359020054,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 197,
			"versionNonce": 424177077,
			"isDeleted": false,
			"id": "NOLLZmPt5cqUQe3ZrC8iy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -975.9940927596299,
			"y": -240.26590692104264,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 339.0863615025481,
			"height": 27.68051930633044,
			"seed": 930515099,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708359020054,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 124,
			"versionNonce": 1342583835,
			"isDeleted": false,
			"id": "xLgUh80_Wv6cRv9eISicA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -923.6578024714835,
			"y": -211.81648430064746,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 226.82647764909666,
			"height": 28.449422620395183,
			"seed": 1987641173,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "-beBK1KX52wsu03rD9-Lx",
					"type": "arrow"
				}
			],
			"updated": 1708359020054,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 107,
			"versionNonce": 1102769941,
			"isDeleted": false,
			"id": "yQE1Cv5d5o1z8JJXHUYZj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -371.2630985181401,
			"y": 73.62537169780467,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 219.13744450844945,
			"height": 27.68051930633044,
			"seed": 1970865941,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708359020054,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 299,
			"versionNonce": 2130639035,
			"isDeleted": false,
			"id": "8HBzSXaa8mbBVntwP8so8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -371.41589603205733,
			"y": 98.3087203715342,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 219.66529363664898,
			"height": 27.68051930633044,
			"seed": 1934711925,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708359020054,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 147,
			"versionNonce": 789988469,
			"isDeleted": false,
			"id": "pYZKmtxJOuJRWF-huCM-8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -371.23184424231,
			"y": 126.0023134484743,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 220.02401175800117,
			"height": 28.449422620395183,
			"seed": 842532309,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "KrIb_W5uHnN3D_ljogN-T",
					"type": "arrow"
				}
			],
			"updated": 1708359020054,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 106,
			"versionNonce": 666249563,
			"isDeleted": false,
			"id": "KrIb_W5uHnN3D_ljogN-T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -303.28584678057854,
			"y": 166.40145304504773,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 61.305387585104995,
			"height": 66.0211866301131,
			"seed": 1776875989,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708359020054,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "pYZKmtxJOuJRWF-huCM-8",
				"focus": 0.39807769120988196,
				"gap": 11.949716976178252
			},
			"endBinding": null,
			"lastCommittedPoint": [
				61.305387585104995,
				66.0211866301131
			],
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					5.389484622866348,
					64.00012989653823
				],
				[
					61.305387585104995,
					66.0211866301131
				]
			]
		},
		{
			"type": "text",
			"version": 121,
			"versionNonce": 1965026773,
			"isDeleted": false,
			"id": "xJKLpU03",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -217.01233376257153,
			"y": 205.53705726271573,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 206.2884521484375,
			"height": 40,
			"seed": 1395231995,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": null,
			"updated": 1708359020054,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "input is of size\nbatchsize x input_neurons",
			"rawText": "input is of size\nbatchsize x input_neurons",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "input is of size\nbatchsize x input_neurons",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 77,
			"versionNonce": 1602110971,
			"isDeleted": false,
			"id": "wjyTXESI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -877.3310086995052,
			"y": 7.324994209436909,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 144.89633178710938,
			"height": 20,
			"seed": 791578613,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708359020054,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Activations matrix",
			"rawText": "Activations matrix",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Activations matrix",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 291,
			"versionNonce": 317549365,
			"isDeleted": false,
			"id": "WAL28ANrZXGRZpGmpqz-T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -814.7915565476474,
			"y": 175.06280533365566,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 36.28071941355631,
			"height": 84.62858155643562,
			"seed": 1617150293,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1708359020054,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8RnVagBqhyVVh-xjtVhu8",
				"focus": 0.15044484699820818,
				"gap": 14.1641382356963
			},
			"endBinding": {
				"elementId": "wtEiIVwf",
				"focus": -0.8873513332760713,
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
					-6.050268394835143,
					78.10282251173865
				],
				[
					30.23045101872117,
					84.62858155643562
				]
			]
		},
		{
			"type": "text",
			"version": 273,
			"versionNonce": 1834602139,
			"isDeleted": false,
			"id": "wtEiIVwf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -783.5611055289262,
			"y": 225.28688275987506,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 312.17669677734375,
			"height": 40,
			"seed": 493538997,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "WAL28ANrZXGRZpGmpqz-T",
					"type": "arrow"
				}
			],
			"updated": 1708359020054,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Activations matrix at position i\nis the activation of neuron k of layer i",
			"rawText": "Activations matrix at position i\nis the activation of neuron k of layer i",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Activations matrix at position i\nis the activation of neuron k of layer i",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 305,
			"versionNonce": 149175445,
			"isDeleted": false,
			"id": "E251H5ok",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0.008038172914641706,
			"x": -867.9847403970442,
			"y": 50.161723965153186,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 140.3042755126953,
			"height": 20,
			"seed": 887697429,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708359020054,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "number of neurons",
			"rawText": "number of neurons",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "number of neurons",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 61,
			"versionNonce": 335233851,
			"isDeleted": false,
			"id": "oJfRqtAyb71OI6nImbw7J",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -907.6749349700303,
			"y": 74.78149592270915,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 219.13744450844945,
			"height": 27.68051930633044,
			"seed": 81028469,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708359020054,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 171,
			"versionNonce": 783933941,
			"isDeleted": false,
			"id": "hXLXPxF_P_qv6whGZUOeq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -961.1137152975291,
			"y": 103.99982185716897,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 339.0863615025481,
			"height": 27.68051930633044,
			"seed": 275902165,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708359020054,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 98,
			"versionNonce": 465904603,
			"isDeleted": false,
			"id": "8RnVagBqhyVVh-xjtVhu8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -908.7774250093826,
			"y": 132.44924447756418,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 226.82647764909666,
			"height": 28.449422620395183,
			"seed": 1448561717,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "WAL28ANrZXGRZpGmpqz-T",
					"type": "arrow"
				}
			],
			"updated": 1708359020054,
			"link": null,
			"locked": false
		},
		{
			"id": "6bWaG2Sb",
			"type": "text",
			"x": 90.94951384986268,
			"y": -389.3397562001936,
			"width": 1403.4576416015625,
			"height": 750.4277810100441,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1451242837,
			"version": 542,
			"versionNonce": 414297173,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"text": "def forward(self, x):\n        \"\"\"Computes the forward pass layer by layer. Stores the activation after every layer in self.A.\n        x : np.ndarray The input to the neural network of size (batch_size, in_neurons)\n        y : np.ndarray The output tensor of size (batch_size, out_neurons)\n        \"\"\"\n\n        # Input layer\n        self.A=[x]\n        batches = x\n        Y=[]\n\n        # Iterate over all layers of W, Each layer describes the weight connecting between to layers\n\n        for k,w_layer in enumerate(self.W[:len(self.W)-1]):\n\n                activations = []\n                # for each batch we compute the weighted sum and activate it via relu and append them to each other\n\n                for batch in batches:\n                        weighted = batch.dot(w_layer)+self.B[k]\n                        relu = np.maximum(0,weighted)\n                        activations.append(relu)\n                # store the batches\n                batches=activations\n                self.A.append(activations)\n        # compute the output\n        for batch in self.A[-1]:\n                Y.append(batch.dot(self.W[-1])+self.B[-1])\n                \n        return Y",
			"rawText": "def forward(self, x):\n        \"\"\"Computes the forward pass layer by layer. Stores the activation after every layer in self.A.\n        x : np.ndarray The input to the neural network of size (batch_size, in_neurons)\n        y : np.ndarray The output tensor of size (batch_size, out_neurons)\n        \"\"\"\n\n        # Input layer\n        self.A=[x]\n        batches = x\n        Y=[]\n\n        # Iterate over all layers of W, Each layer describes the weight connecting between to layers\n\n        for k,w_layer in enumerate(self.W[:len(self.W)-1]):\n\n                activations = []\n                # for each batch we compute the weighted sum and activate it via relu and append them to each other\n\n                for batch in batches:\n                        weighted = batch.dot(w_layer)+self.B[k]\n                        relu = np.maximum(0,weighted)\n                        activations.append(relu)\n                # store the batches\n                batches=activations\n                self.A.append(activations)\n        # compute the output\n        for batch in self.A[-1]:\n                Y.append(batch.dot(self.W[-1])+self.B[-1])\n                \n        return Y",
			"fontSize": 20.845216139167892,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 745,
			"containerId": null,
			"originalText": "def forward(self, x):\n        \"\"\"Computes the forward pass layer by layer. Stores the activation after every layer in self.A.\n        x : np.ndarray The input to the neural network of size (batch_size, in_neurons)\n        y : np.ndarray The output tensor of size (batch_size, out_neurons)\n        \"\"\"\n\n        # Input layer\n        self.A=[x]\n        batches = x\n        Y=[]\n\n        # Iterate over all layers of W, Each layer describes the weight connecting between to layers\n\n        for k,w_layer in enumerate(self.W[:len(self.W)-1]):\n\n                activations = []\n                # for each batch we compute the weighted sum and activate it via relu and append them to each other\n\n                for batch in batches:\n                        weighted = batch.dot(w_layer)+self.B[k]\n                        relu = np.maximum(0,weighted)\n                        activations.append(relu)\n                # store the batches\n                batches=activations\n                self.A.append(activations)\n        # compute the output\n        for batch in self.A[-1]:\n                Y.append(batch.dot(self.W[-1])+self.B[-1])\n                \n        return Y",
			"lineHeight": 1.2
		},
		{
			"id": "oTm1wdUTkr-x9QjtwJJRO",
			"type": "arrow",
			"x": 322.60896267408157,
			"y": -200.10862048036427,
			"width": 64.79652078891775,
			"height": 1.5999140935535365,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
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
			"seed": 1654305531,
			"version": 78,
			"versionNonce": 1171107707,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					64.79652078891775,
					1.5999140935535365
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "NxNoUFhy",
			"type": "text",
			"x": 406.0505998417318,
			"y": -211.24637499706301,
			"width": 234.375,
			"height": 19.2,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2100416661,
			"version": 128,
			"versionNonce": 180574645,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"text": "Put the input in as it is",
			"rawText": "Put the input in as it is",
			"fontSize": 16,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 15,
			"containerId": null,
			"originalText": "Put the input in as it is",
			"lineHeight": 1.2
		},
		{
			"id": "SeHnHr_T4PJqbdYIw3tHk",
			"type": "arrow",
			"x": 833.1616168837924,
			"y": -50.49851389052748,
			"width": 119.03068709022045,
			"height": 1.8893759855590702,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
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
			"seed": 2147363195,
			"version": 31,
			"versionNonce": 2030045211,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					119.03068709022045,
					-1.8893759855590702
				]
			],
			"lastCommittedPoint": [
				119.03068709022045,
				-1.8893759855590702
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "QtxxJ2ue",
			"type": "text",
			"x": 979.1068897298977,
			"y": -62.96936632138892,
			"width": 600,
			"height": 38.4,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 90151611,
			"version": 216,
			"versionNonce": 295587003,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"text": "go over every layers weight matrix of size (input,output)\ninput being the layer behind and output being the layer in front",
			"rawText": "go over every layers weight matrix of size (input,output)\ninput being the layer behind and output being the layer in front",
			"fontSize": 16,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "go over every layers weight matrix of size (input,output)\ninput being the layer behind and output being the layer in front",
			"lineHeight": 1.2
		},
		{
			"id": "L5of3cIglmYqE9hCvTs_8",
			"type": "arrow",
			"x": 552.3261257762755,
			"y": 74.71018757046829,
			"width": 378.00950524942937,
			"height": 0,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
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
			"seed": 601309147,
			"version": 89,
			"versionNonce": 398864501,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					378.00950524942937,
					0
				]
			],
			"lastCommittedPoint": [
				378.00950524942937,
				0
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "o8EqUcZp",
			"type": "text",
			"x": 950.6817517048528,
			"y": 62.93085454569854,
			"width": 684.375,
			"height": 38.4,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 641186779,
			"version": 164,
			"versionNonce": 1397423451,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"text": "for each batch we process it individually to make it easier to understand\neach batch is of size input neurons",
			"rawText": "for each batch we process it individually to make it easier to understand\neach batch is of size input neurons",
			"fontSize": 16,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 34,
			"containerId": null,
			"originalText": "for each batch we process it individually to make it easier to understand\neach batch is of size input neurons",
			"lineHeight": 1.2
		},
		{
			"id": "RAS-t9UKx3gU2iE4DRiFI",
			"type": "arrow",
			"x": 867.2388224289862,
			"y": 100.89822607377585,
			"width": 239.87005432258388,
			"height": 47.11733209907902,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
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
			"seed": 863370875,
			"version": 117,
			"versionNonce": 418535893,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					47.11733209907902,
					41.76308981509277
				],
				[
					239.87005432258388,
					47.11733209907902
				]
			],
			"lastCommittedPoint": [
				239.87005432258388,
				47.11733209907902
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "kTKICkZk",
				"focus": 0.4114625211587561,
				"gap": 10.708484567972619
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "kTKICkZk",
			"type": "text",
			"x": 1117.8173613195427,
			"y": 136.23622514808517,
			"width": 825,
			"height": 96,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 338971707,
			"version": 912,
			"versionNonce": 1771198261,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "RAS-t9UKx3gU2iE4DRiFI",
					"type": "arrow"
				}
			],
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"text": "a dot product between (1, n_i) and (n_i, n_k) will do matrix multiplication\nwhich means every row in the first matrix (that being an individual element xi)\nwill be multiplied with an individual column (which contains all weights from neuron n_i\nto every neuron in n_k) in the end we achieve: (1,n_k) which is the sum of all xi\nmultiplied with the weight from ni to n_k (we add the biases at the end ofc)",
			"rawText": "a dot product between (1, n_i) and (n_i, n_k) will do matrix multiplication\nwhich means every row in the first matrix (that being an individual element xi)\nwill be multiplied with an individual column (which contains all weights from neuron n_i\nto every neuron in n_k) in the end we achieve: (1,n_k) which is the sum of all xi\nmultiplied with the weight from ni to n_k (we add the biases at the end ofc)",
			"fontSize": 16,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 92,
			"containerId": null,
			"originalText": "a dot product between (1, n_i) and (n_i, n_k) will do matrix multiplication\nwhich means every row in the first matrix (that being an individual element xi)\nwill be multiplied with an individual column (which contains all weights from neuron n_i\nto every neuron in n_k) in the end we achieve: (1,n_k) which is the sum of all xi\nmultiplied with the weight from ni to n_k (we add the biases at the end ofc)",
			"lineHeight": 1.2
		},
		{
			"id": "h-rCw8Psr9URiUmtEV02N",
			"type": "arrow",
			"x": 814.7672480459208,
			"y": 300.07603903806444,
			"width": 155.27302623560115,
			"height": 0,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
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
			"seed": 2030371445,
			"version": 39,
			"versionNonce": 1892262555,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					155.27302623560115,
					0
				]
			],
			"lastCommittedPoint": null,
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "wcJrhRXh",
			"type": "text",
			"x": 991.4572434174671,
			"y": 291.50925138368643,
			"width": 590.625,
			"height": 19.2,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 621204149,
			"version": 118,
			"versionNonce": 336308373,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"text": "We compute the last layer since thats not in A instead its in Y",
			"rawText": "We compute the last layer since thats not in A instead its in Y",
			"fontSize": 16,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 15,
			"containerId": null,
			"originalText": "We compute the last layer since thats not in A instead its in Y",
			"lineHeight": 1.2
		},
		{
			"id": "_7ZqnAY_abxsEySIdBcvU",
			"type": "arrow",
			"x": 644.5023434151581,
			"y": 172.64507267919163,
			"width": 82.45533117338823,
			"height": 41.76308981509277,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
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
			"seed": 2076441115,
			"version": 66,
			"versionNonce": 1112577851,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					8.566787654378004,
					38.550544444701075
				],
				[
					82.45533117338823,
					41.76308981509277
				]
			],
			"lastCommittedPoint": [
				82.45533117338823,
				41.76308981509277
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "K5Mgay6Q",
			"type": "text",
			"x": 746.2329468108968,
			"y": 202.62882946951459,
			"width": 37.5,
			"height": 19.2,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 587590709,
			"version": 52,
			"versionNonce": 2085615579,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359020056,
			"link": null,
			"locked": false,
			"text": "Relu",
			"rawText": "Relu",
			"fontSize": 16,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 15,
			"containerId": null,
			"originalText": "Relu",
			"lineHeight": 1.2
		},
		{
			"id": "SL2TTBFG",
			"type": "text",
			"x": 143.88919669603328,
			"y": 385.3974865534193,
			"width": 1242.1875,
			"height": 696,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 260634549,
			"version": 135,
			"versionNonce": 907794037,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359051175,
			"link": null,
			"locked": false,
			"text": "def backward(self, y, t):\n        \"\"\"Computes the backward pass of every layer and returns it in reverse order (from back to front).\n        y : np.ndarray The output of the neural network of size (batch_size, out_neurons)\n        t : np.ndarray The target of size (batch_size, out_neurons)\n        \"\"\"\n\n        self.DW = []\n        self.DB = []\n        \n        lastLayerLoss = 2 * (y - t) / y.shape[0] # initialize as MSE derivative\n\n        # go through the network in reverse order and compute the gradients\n\n        for i in reversed(range(len(self.W))):\n\n                # compute the gradients\n                dloss_dW = np.dot(self.A[i].T, lastLayerLoss)\n                dloss_dB = np.sum(lastLayerLoss, axis=0)\n\n                # store the gradients\n                self.DW.append(dloss_dW)\n                self.DB.append(dloss_dB)\n\n                # compute the gradient for the next layer\n                lastLayerLoss = np.dot(lastLayerLoss, self.W[i].T) * self._relu_derivative(self.A[i])\n\n        # reverse the gradients\n        self.DW.reverse()\n        self.DB.reverse()",
			"rawText": "def backward(self, y, t):\n        \"\"\"Computes the backward pass of every layer and returns it in reverse order (from back to front).\n        y : np.ndarray The output of the neural network of size (batch_size, out_neurons)\n        t : np.ndarray The target of size (batch_size, out_neurons)\n        \"\"\"\n\n        self.DW = []\n        self.DB = []\n        \n        lastLayerLoss = 2 * (y - t) / y.shape[0] # initialize as MSE derivative\n\n        # go through the network in reverse order and compute the gradients\n\n        for i in reversed(range(len(self.W))):\n\n                # compute the gradients\n                dloss_dW = np.dot(self.A[i].T, lastLayerLoss)\n                dloss_dB = np.sum(lastLayerLoss, axis=0)\n\n                # store the gradients\n                self.DW.append(dloss_dW)\n                self.DB.append(dloss_dB)\n\n                # compute the gradient for the next layer\n                lastLayerLoss = np.dot(lastLayerLoss, self.W[i].T) * self._relu_derivative(self.A[i])\n\n        # reverse the gradients\n        self.DW.reverse()\n        self.DB.reverse()",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 691,
			"containerId": null,
			"originalText": "def backward(self, y, t):\n        \"\"\"Computes the backward pass of every layer and returns it in reverse order (from back to front).\n        y : np.ndarray The output of the neural network of size (batch_size, out_neurons)\n        t : np.ndarray The target of size (batch_size, out_neurons)\n        \"\"\"\n\n        self.DW = []\n        self.DB = []\n        \n        lastLayerLoss = 2 * (y - t) / y.shape[0] # initialize as MSE derivative\n\n        # go through the network in reverse order and compute the gradients\n\n        for i in reversed(range(len(self.W))):\n\n                # compute the gradients\n                dloss_dW = np.dot(self.A[i].T, lastLayerLoss)\n                dloss_dB = np.sum(lastLayerLoss, axis=0)\n\n                # store the gradients\n                self.DW.append(dloss_dW)\n                self.DB.append(dloss_dB)\n\n                # compute the gradient for the next layer\n                lastLayerLoss = np.dot(lastLayerLoss, self.W[i].T) * self._relu_derivative(self.A[i])\n\n        # reverse the gradients\n        self.DW.reverse()\n        self.DB.reverse()",
			"lineHeight": 1.2
		},
		{
			"id": "72R4rAsRfXD5Gd4q7xBDO",
			"type": "arrow",
			"x": 1088.873652746461,
			"y": 615.8595875793281,
			"width": 128.59654443281556,
			"height": 0,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
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
			"seed": 2134277429,
			"version": 34,
			"versionNonce": 1141639963,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708359206193,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					128.59654443281556,
					0
				]
			],
			"lastCommittedPoint": [
				128.59654443281556,
				0
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "CL3K7bvu",
			"type": "text",
			"x": 1236.0305231798893,
			"y": 606.5794245790221,
			"width": 304.6875,
			"height": 24,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 636632437,
			"version": 87,
			"versionNonce": 476587477,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359222696,
			"link": null,
			"locked": false,
			"text": "Derivative of loss w.r.t y",
			"rawText": "Derivative of loss w.r.t y",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 19,
			"containerId": null,
			"originalText": "Derivative of loss w.r.t y",
			"lineHeight": 1.2
		},
		{
			"id": "3P3uhjZO7e38H8uRY5tQ8",
			"type": "arrow",
			"x": 701.917065406651,
			"y": 703.8482653091482,
			"width": 256.552853115111,
			"height": 4.4233250537088225,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
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
			"seed": 704184853,
			"version": 38,
			"versionNonce": 1508712827,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708359526780,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					256.552853115111,
					4.4233250537088225
				]
			],
			"lastCommittedPoint": [
				256.552853115111,
				4.4233250537088225
			],
			"startBinding": null,
			"endBinding": null,
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "pC3LOUV6",
			"type": "text",
			"x": 977.2690500000244,
			"y": 696.1074464651578,
			"width": 363.28125,
			"height": 24,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2033933941,
			"version": 110,
			"versionNonce": 639910677,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359544673,
			"link": null,
			"locked": false,
			"text": "Compute from last layer onwards",
			"rawText": "Compute from last layer onwards",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 19,
			"containerId": null,
			"originalText": "Compute from last layer onwards",
			"lineHeight": 1.2
		},
		{
			"id": "bV45LE1u",
			"type": "text",
			"x": 871.3195405030211,
			"y": 738.6855264521674,
			"width": 996.09375,
			"height": 48,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1715749333,
			"version": 329,
			"versionNonce": 136248731,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708362353248,
			"link": null,
			"locked": false,
			"text": "First iteration -> E/y * y/w = loss_derivative * a -> E/y * y/b = loss_derivative * 1\nMiddle iterations -> delta_layer_before * relu_layer_before * y/w ",
			"rawText": "First iteration -> E/y * y/w = loss_derivative * a -> E/y * y/b = loss_derivative * 1\nMiddle iterations -> delta_layer_before * relu_layer_before * y/w ",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 43,
			"containerId": null,
			"originalText": "First iteration -> E/y * y/w = loss_derivative * a -> E/y * y/b = loss_derivative * 1\nMiddle iterations -> delta_layer_before * relu_layer_before * y/w ",
			"lineHeight": 1.2
		},
		{
			"id": "tW0oKK4b",
			"type": "text",
			"x": 866.869161676923,
			"y": 796.1398868044325,
			"width": 632.8125,
			"height": 120,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2007247349,
			"version": 348,
			"versionNonce": 45952763,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1708359893836,
			"link": null,
			"locked": false,
			"text": "lastlayerloss = (batchsize, output neurons)\nself.A[n] = (batchsize, previousLayerNeurons)\n\nin order to get it to match the weight matrix which is\n(input,output) we transpose A and multiply them",
			"rawText": "lastlayerloss = (batchsize, output neurons)\nself.A[n] = (batchsize, previousLayerNeurons)\n\nin order to get it to match the weight matrix which is\n(input,output) we transpose A and multiply them",
			"fontSize": 20,
			"fontFamily": 3,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 115,
			"containerId": null,
			"originalText": "lastlayerloss = (batchsize, output neurons)\nself.A[n] = (batchsize, previousLayerNeurons)\n\nin order to get it to match the weight matrix which is\n(input,output) we transpose A and multiply them",
			"lineHeight": 1.2
		},
		{
			"id": "ZdmtUjsmeVmyyF-TN4VlO",
			"type": "arrow",
			"x": 808.6456691122328,
			"y": 997.2469993562773,
			"width": 409.82666390538725,
			"height": 42.00439491551049,
			"angle": 0,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
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
			"seed": 1548391131,
			"version": 54,
			"versionNonce": 1408851067,
			"isDeleted": false,
			"boundElements": [],
			"updated": 1708362710169,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					52.22168016522937,
					42.00439491551049
				],
				[
					409.82666390538725,
					42.00439491551049
				]
			],
			"lastCommittedPoint": [
				409.82666390538725,
				42.00439491551049
			],
			"startBinding": null,
			"endBinding": {
				"elementId": "lymzXekM",
				"focus": 0.5450846388784812,
				"gap": 19.628909324085043
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "text",
			"version": 606,
			"versionNonce": 2133726491,
			"isDeleted": false,
			"id": "lymzXekM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1238.101242341705,
			"y": 1006.4974882710385,
			"strokeColor": "#e03131",
			"backgroundColor": "#ffffff",
			"width": 984.375,
			"height": 144,
			"seed": 2105288373,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ZdmtUjsmeVmyyF-TN4VlO",
					"type": "arrow"
				}
			],
			"updated": 1708362710169,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 3,
			"text": "lastlayerloss = (batchsize, output neurons)\nself.W[i] = (input neurons, output neurons)\nself.relu_derivative(self.A[i]).shape = self.A[i].shape = (batchsize, input neurons)\n\nin order to get it to match the lastlayerloss which is\n(batchsize, output neurons) we transpose W and multiply them",
			"rawText": "lastlayerloss = (batchsize, output neurons)\nself.W[i] = (input neurons, output neurons)\nself.relu_derivative(self.A[i]).shape = self.A[i].shape = (batchsize, input neurons)\n\nin order to get it to match the lastlayerloss which is\n(batchsize, output neurons) we transpose W and multiply them",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "lastlayerloss = (batchsize, output neurons)\nself.W[i] = (input neurons, output neurons)\nself.relu_derivative(self.A[i]).shape = self.A[i].shape = (batchsize, input neurons)\n\nin order to get it to match the lastlayerloss which is\n(batchsize, output neurons) we transpose W and multiply them",
			"lineHeight": 1.2,
			"baseline": 139
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#e03131",
		"currentItemBackgroundColor": "#ffffff",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 3,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": -159.8868308790437,
		"scrollY": -294.83897864762514,
		"zoom": {
			"value": 0.7808602069955614
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