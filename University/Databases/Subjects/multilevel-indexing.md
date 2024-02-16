---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Multi-level Indexing ^YbGU2DzO

* Data cubes: relational data is considered as points in multidimensional space, where every attribute
  corresponds to a dimension

* Spatial Queries :
1) Point queries: all dimensions are restricted to a certain value.
2) Partial queries: one dimension is restricted while the others are not.
3) Range queries: range specifies area and searches data in it
4) Nearest neighbor queries: Nearest point to a given point
5) Where-am-I queries: Given a point, on which plain is it located?
6) Distance query: Given a radius and a center, what points are located in that area?

* Grid File: Multidimensional space becomes grid, Partition every dimension into stripes indicating ranges
            stored in a bucket (overflow allowed), all buckets are stored in multidimensional array





* Partitioned Hashing: We have a hash function for each attribute that produces a binary output
  the final hash value is the concatenation of those bits


* kdimensional Trees: BST for k dimensions, each level is an alternating separator for an attribute

* Quad tree: Partition the grid into SW, SE, NE, NW and split each quad into quadrants if necessary
* R-tree: A b-Tree in higher dimensions, where we partition space into intervals (rectangles) and build
  a hierarchy of it (Does not cover entire space and can have overlap)




* Bitmap indexing: Each value of each attribute has an n length bitmap that indicates (1,0) membership
 ^2Pu2OtkL

Search: Treat each dimension separately, find the corresponding bucket dimensions and search in it ^vc3Qwuuq

requires indexes on each dimension or binary search ^kRaheo62

Insert: Find corresponding bucket and insert, if no space then either overflow block or dynamically
change the gridlines to add more ^VO5b4EkT

1 I/O for point lookup, 2 I/O for point insertion and deletion ^UyagDELU

Partial query: only need to explore 2^i such that i is the number of unexplored bits ^575Hcf9T

Space partition: Based on median          Data partition: based on mean ^BKDxGOoV

We try to minimize overlap and maximize coverage ^1atFg02A

Insertion: Insert the node in the area with minimal expansion to cover the inserted node, then possibly
split that node for 2 nodes that are at least half full AND minimize dead coverage ^UZmZUC8G

Bitmap size =Align(Number of records / 8bits / 1000byte) * Number of unique values ^CmSZKWut

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
			"version": 345,
			"versionNonce": 1240567680,
			"isDeleted": false,
			"id": "YbGU2DzO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -151.86854530626982,
			"y": -457.5551857164628,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 260.7370910644531,
			"height": 35,
			"seed": 1837531008,
			"groupIds": [],
			"frameId": "jeHqLRpLOwv_9QMIUyja7",
			"roundness": null,
			"boundElements": [],
			"updated": 1707229638790,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Multi-level Indexing",
			"rawText": "Multi-level Indexing",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Multi-level Indexing",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 1599,
			"versionNonce": 1470641719,
			"isDeleted": false,
			"id": "2Pu2OtkL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -528.4897562996194,
			"y": -382.55518581578946,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1024.678955078125,
			"height": 825,
			"seed": 1792667520,
			"groupIds": [],
			"frameId": "jeHqLRpLOwv_9QMIUyja7",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943642818,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Data cubes: relational data is considered as points in multidimensional space, where every attribute\n  corresponds to a dimension\n\n* Spatial Queries :\n1) Point queries: all dimensions are restricted to a certain value.\n2) Partial queries: one dimension is restricted while the others are not.\n3) Range queries: range specifies area and searches data in it\n4) Nearest neighbor queries: Nearest point to a given point\n5) Where-am-I queries: Given a point, on which plain is it located?\n6) Distance query: Given a radius and a center, what points are located in that area?\n\n* Grid File: Multidimensional space becomes grid, Partition every dimension into stripes indicating ranges\n            stored in a bucket (overflow allowed), all buckets are stored in multidimensional array\n\n\n\n\n\n* Partitioned Hashing: We have a hash function for each attribute that produces a binary output\n  the final hash value is the concatenation of those bits\n\n\n* kdimensional Trees: BST for k dimensions, each level is an alternating separator for an attribute\n\n* Quad tree: Partition the grid into SW, SE, NE, NW and split each quad into quadrants if necessary\n* R-tree: A b-Tree in higher dimensions, where we partition space into intervals (rectangles) and build\n  a hierarchy of it (Does not cover entire space and can have overlap)\n\n\n\n\n* Bitmap indexing: Each value of each attribute has an n length bitmap that indicates (1,0) membership\n",
			"rawText": "* Data cubes: relational data is considered as points in multidimensional space, where every attribute\n  corresponds to a dimension\n\n* Spatial Queries :\n1) Point queries: all dimensions are restricted to a certain value.\n2) Partial queries: one dimension is restricted while the others are not.\n3) Range queries: range specifies area and searches data in it\n4) Nearest neighbor queries: Nearest point to a given point\n5) Where-am-I queries: Given a point, on which plain is it located?\n6) Distance query: Given a radius and a center, what points are located in that area?\n\n* Grid File: Multidimensional space becomes grid, Partition every dimension into stripes indicating ranges\n            stored in a bucket (overflow allowed), all buckets are stored in multidimensional array\n\n\n\n\n\n* Partitioned Hashing: We have a hash function for each attribute that produces a binary output\n  the final hash value is the concatenation of those bits\n\n\n* kdimensional Trees: BST for k dimensions, each level is an alternating separator for an attribute\n\n* Quad tree: Partition the grid into SW, SE, NE, NW and split each quad into quadrants if necessary\n* R-tree: A b-Tree in higher dimensions, where we partition space into intervals (rectangles) and build\n  a hierarchy of it (Does not cover entire space and can have overlap)\n\n\n\n\n* Bitmap indexing: Each value of each attribute has an n length bitmap that indicates (1,0) membership\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Data cubes: relational data is considered as points in multidimensional space, where every attribute\n  corresponds to a dimension\n\n* Spatial Queries :\n1) Point queries: all dimensions are restricted to a certain value.\n2) Partial queries: one dimension is restricted while the others are not.\n3) Range queries: range specifies area and searches data in it\n4) Nearest neighbor queries: Nearest point to a given point\n5) Where-am-I queries: Given a point, on which plain is it located?\n6) Distance query: Given a radius and a center, what points are located in that area?\n\n* Grid File: Multidimensional space becomes grid, Partition every dimension into stripes indicating ranges\n            stored in a bucket (overflow allowed), all buckets are stored in multidimensional array\n\n\n\n\n\n* Partitioned Hashing: We have a hash function for each attribute that produces a binary output\n  the final hash value is the concatenation of those bits\n\n\n* kdimensional Trees: BST for k dimensions, each level is an alternating separator for an attribute\n\n* Quad tree: Partition the grid into SW, SE, NE, NW and split each quad into quadrants if necessary\n* R-tree: A b-Tree in higher dimensions, where we partition space into intervals (rectangles) and build\n  a hierarchy of it (Does not cover entire space and can have overlap)\n\n\n\n\n* Bitmap indexing: Each value of each attribute has an n length bitmap that indicates (1,0) membership\n",
			"lineHeight": 1.25,
			"baseline": 818
		},
		{
			"type": "text",
			"version": 159,
			"versionNonce": 1188831104,
			"isDeleted": false,
			"id": "vc3Qwuuq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -506.2930646320792,
			"y": -57.55518598178204,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 975.9190063476562,
			"height": 25,
			"seed": 2139250560,
			"groupIds": [],
			"frameId": "jeHqLRpLOwv_9QMIUyja7",
			"roundness": null,
			"boundElements": [],
			"updated": 1707229638790,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Search: Treat each dimension separately, find the corresponding bucket dimensions and search in it",
			"rawText": "Search: Treat each dimension separately, find the corresponding bucket dimensions and search in it",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Search: Treat each dimension separately, find the corresponding bucket dimensions and search in it",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 124,
			"versionNonce": 1008179328,
			"isDeleted": false,
			"id": "kRaheo62",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -420.8943516499229,
			"y": -32.555186411365604,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 402.560791015625,
			"height": 20,
			"seed": 1141530496,
			"groupIds": [],
			"frameId": "jeHqLRpLOwv_9QMIUyja7",
			"roundness": null,
			"boundElements": [],
			"updated": 1707229638790,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "requires indexes on each dimension or binary search",
			"rawText": "requires indexes on each dimension or binary search",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "requires indexes on each dimension or binary search",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 190,
			"versionNonce": 1697394560,
			"isDeleted": false,
			"id": "VO5b4EkT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -513.1618526196983,
			"y": -11.779517019752028,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 963.1390380859375,
			"height": 50,
			"seed": 1604206464,
			"groupIds": [],
			"frameId": "jeHqLRpLOwv_9QMIUyja7",
			"roundness": null,
			"boundElements": [],
			"updated": 1707229638790,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Insert: Find corresponding bucket and insert, if no space then either overflow block or dynamically\nchange the gridlines to add more",
			"rawText": "Insert: Find corresponding bucket and insert, if no space then either overflow block or dynamically\nchange the gridlines to add more",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Insert: Find corresponding bucket and insert, if no space then either overflow block or dynamically\nchange the gridlines to add more",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 188,
			"versionNonce": 1593458560,
			"isDeleted": false,
			"id": "UyagDELU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -513.161853463077,
			"y": 38.99615174546633,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 603.6393432617188,
			"height": 25,
			"seed": 1803692160,
			"groupIds": [],
			"frameId": "jeHqLRpLOwv_9QMIUyja7",
			"roundness": null,
			"boundElements": [],
			"updated": 1707229638790,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1 I/O for point lookup, 2 I/O for point insertion and deletion",
			"rawText": "1 I/O for point lookup, 2 I/O for point insertion and deletion",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1 I/O for point lookup, 2 I/O for point insertion and deletion",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 165,
			"versionNonce": 1416329344,
			"isDeleted": false,
			"id": "575Hcf9T",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -529.036452183201,
			"y": 121.30156947709179,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 833.1991577148438,
			"height": 25,
			"seed": 1772800128,
			"groupIds": [],
			"frameId": "jeHqLRpLOwv_9QMIUyja7",
			"roundness": null,
			"boundElements": [],
			"updated": 1707229638790,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Partial query: only need to explore 2^i such that i is the number of unexplored bits",
			"rawText": "Partial query: only need to explore 2^i such that i is the number of unexplored bits",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Partial query: only need to explore 2^i such that i is the number of unexplored bits",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 289888384,
			"isDeleted": false,
			"id": "BKDxGOoV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -429.4965959207024,
			"y": 192.44481371275353,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 733.6593017578125,
			"height": 25,
			"seed": 2041051264,
			"groupIds": [],
			"frameId": "jeHqLRpLOwv_9QMIUyja7",
			"roundness": null,
			"boundElements": [],
			"updated": 1707229638790,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Space partition: Based on median          Data partition: based on mean",
			"rawText": "Space partition: Based on median          Data partition: based on mean",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Space partition: Based on median          Data partition: based on mean",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 148,
			"versionNonce": 264784000,
			"isDeleted": false,
			"id": "1atFg02A",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -510.83448583607924,
			"y": 290.6749605829646,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 487.75946044921875,
			"height": 25,
			"seed": 244006784,
			"groupIds": [],
			"frameId": "jeHqLRpLOwv_9QMIUyja7",
			"roundness": null,
			"boundElements": [],
			"updated": 1707229638790,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "We try to minimize overlap and maximize coverage",
			"rawText": "We try to minimize overlap and maximize coverage",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "We try to minimize overlap and maximize coverage",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 281,
			"versionNonce": 1713274752,
			"isDeleted": false,
			"id": "UZmZUC8G",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -526.167260618541,
			"y": 331.02436790523217,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 1015.1188354492188,
			"height": 50,
			"seed": 1333614720,
			"groupIds": [],
			"frameId": "jeHqLRpLOwv_9QMIUyja7",
			"roundness": null,
			"boundElements": [],
			"updated": 1707229638790,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Insertion: Insert the node in the area with minimal expansion to cover the inserted node, then possibly\nsplit that node for 2 nodes that are at least half full AND minimize dead coverage",
			"rawText": "Insertion: Insert the node in the area with minimal expansion to cover the inserted node, then possibly\nsplit that node for 2 nodes that are at least half full AND minimize dead coverage",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Insertion: Insert the node in the area with minimal expansion to cover the inserted node, then possibly\nsplit that node for 2 nodes that are at least half full AND minimize dead coverage",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 115,
			"versionNonce": 757239680,
			"isDeleted": false,
			"id": "CmSZKWut",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -506.2930648460182,
			"y": 422.44481425304957,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 840.8392333984375,
			"height": 25,
			"seed": 1394126720,
			"groupIds": [],
			"frameId": "jeHqLRpLOwv_9QMIUyja7",
			"roundness": null,
			"boundElements": [],
			"updated": 1707229638790,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Bitmap size =Align(Number of records / 8bits / 1000byte) * Number of unique values",
			"rawText": "Bitmap size =Align(Number of records / 8bits / 1000byte) * Number of unique values",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bitmap size =Align(Number of records / 8bits / 1000byte) * Number of unique values",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "frame",
			"version": 660,
			"versionNonce": 473278399,
			"isDeleted": false,
			"id": "jeHqLRpLOwv_9QMIUyja7",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -541.4081034999999,
			"y": -457.55518606913665,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 1039.816207,
			"height": 905.5848811480103,
			"seed": 1504800640,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708099385958,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#7A7A7A"
				}
			},
			"name": "Indexing"
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#2f9e44",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 732.7499999999999,
		"scrollY": 489.5049329951315,
		"zoom": {
			"value": 1
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