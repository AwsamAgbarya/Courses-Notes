---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - databases
---

Next[[Concurrency Control]]
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Query Optimization ^ykxcCrZ9

* The parsing and pre-processing stage consists of converting the SQL text query into a grammar tree
  and checking the validity of these expressions and the existence of these attributes in each table

* Transformation rules: we want to transform the operators in order to achieve smaller intermediate
  results without changing the semantics of the query.















* Logical query plan selection: 1) Translate parse tree into a relational algebra expression
                              2) Represent the expression as a tree
                              3) Resolve sub-queries
                              4) Improve the logical query plan according to algebraic laws





* Physical query plan selection: Picking the right physical query plans from the logical one raises some
questions like which order of operations to take for associative/commutative operations, which
implementation to use when to put scans and sorts, and what type of data transport do we choose?

* Cost estimation: Evaluate the cost of each physical plan w.r.t intermediate results and num of I/O
* intermediate result estimation: measuring output cardinality. (Does the data fit into main memory?) ^01udynON

Two terms are equivalent if both terms work on the same relations and always produce the same results ^02eTxaLn

1) X is commutative and associative  R X S = S X R     ,     (R X S) X T = R X (S X T)
2) U is commutative and associative  R U S = S U R    ,     (R U S) U T = R U (S U T)
3) ∩ is commutative and associative  R ∩ S = S ∩ R    ,     (R ∩ S) ∩ T = R ∩ (S ∩ T)
4) ⋈ is commutative and associative  R ⋈ S = S ⋈ R   ,     (R ⋈ S) ⋈ T = R ⋈ (S ⋈ T)
5)





6) ^weCn9GHa

Not in case of bags ^eXq6cqIk

if S only has attributes of R ^MzXSgfSO

1) Push down selections as early as possible
2) Push down Projections as early as possible
3) adjust duplicate elimination
4) Combine selection and cross product to join
5) Group union and join operators ^yW9nqunP

* Output cardinality = Input Cardinality * Selectivity,  B(R)= Blocks in R,  T(R)= Tuples in R, V(A,R)= distinct values of A in R ^lEUaO0I6

* Projection estimation: Immediate estimation of tuple size according to attributes (straightforward)
* Selection estimation:
                                                                           5)
1)                                 3)     

2)                                4)



* Join Size/Cardinality estimation:

1) T(R ⋈ S) =                    2) T(R(Y1, Y2) ⋈ S(Y1, Y2)) = 


* When joining on a comparsion, just multiply both sizes R⋈σ(S) =  T(R) * 1/V(S)

* Join Cost/order estimation:
  R ⋈ S, such that R and S can contain more joins in them = Sum of Size of intermediate joins 

* Union estimation:  AVG[T(R) + T(S), max[T(R), T(S)] ]
* Intersection estimation: consider as join
* Difference estimation: T(R) – T(S)/2
* Duplicate elimination estimation: min[T(R)/2, ∏i V(R, Ai)]
* Aggregation estimation:  min[T(R)/2, ∏i V(R, Li)] ^V013sntn

Assuming theyre independent ^sLjhpEZX

T1 + T2 - (T1 * T2) ^xosNSTzn

Ti being tuples that satisfy
condition i ^tvzBkqeh

Or also
n(1 - F1 - F2) ^8IWW9Ogm

fraction of
records that dont
satisfy cond1 ^F790zTLl

fraction of
records that dont
satisfy cond2 ^aJ7j9Exx

general approach: Multiply all the cardinalities, divided by selectivity.
to get selectivity, if attribute occurs once dont add it, if it occurs more than once then add all its values except smallest ^oqA6foDr

    Useless stuff form Query Optimization ^UutKlFG6

* Considerations for Collecting Statistics: Statistics do not change rapidly in short periods of time
and even slightly inaccurate statistics are helpful, so we dont have to keep them up to date all the
time due to the operation being expensive, thus we perform sampling and only trigger statistics over
certain periods of time/ after certain amount of updates

* Too many physical plans to go over, how do we pick best one? Heuristics!
  determine join pair with the smallest intermediate result, and keep joining with relations that produce
  smallest intermediate results.
  Use index-scan/index-join when selection/join on indexed attribute
  Apply multiple selections on same relation at the same time
  Use sort-merge-join if one relation is sorted on the join attribute
  Compute union and intersection for smallest relations first.

* Branch and bound: find a plan and establish upper-bound, enumerate over subplans of parts of the
  query, if cost of subplans are higher than upper bound then dump em, lower upperbound if better 
  complete plan found.

* Hill Climbing: find a plan, change one subplan at a time until you find a better plan, if no plans are 
  better then terminate, do this over 10 random plans.

* Dynamic programming: save best subplan for one operator, build best partial plan that consists of 
  that subplan in it.

* Selinger-style: same as dynamic programming but Do not only memorize the best plan, Also keep track
  of miscellaneous sorting variants (intresting orders)

* When choosing the best partial plan, Cost comparison will not suffice, sort orders must be considered

* Bottom-Up Query Plan Generation: this approach assumes that the choice of join method i is
  independent of all previous choices, and a sub plan of an optimal plan is also optimal.
1) Compute optimal plans for the join of every combination of k relations
2) Ignore Suboptimal plans
3) Extend this concept to k+1 relations ^3igvfc5b

ignore cross products when considering cheapest cost, theyre expensive ^2kcMwZH5


# Embedded files
fbb4e941782628101e3d0ef1b4aa4cbde42dbc8d: $$\color{blue} \sigma_{A=c}(R)$$
820e043bc11f5f0ee14a64379577ab2b8d2285c1: $$\color{blue} \frac{T(R)}{V(A,R)}$$
eb6568d565c8d770c2c540f237b8efee2eeaa6a5: $$\color{blue} \sigma_{A<c}(R)$$
2b7b16099d2f0f53dfc10064e33aeff03d58b1c8: $$\color{blue} \frac{T(R)}{3}$$
2e97ae80e6235a38660aa48c667281b8a75b81dc: $$\color{blue} \sigma_{A\neq c}(R)$$
d4ca8062b00e396668ed0c22e47bf3c5380d573b: $$\color{blue} \frac{T(R)(V(A,R)-1)}{V(A,R)}$$
d8437bf6b9ff26ceac5687390477c727a24f7e56: $$\color{blue} \sigma_{\text{Cond1 AND Cond2}}(R)$$
6878c9f5a4513817033b8783a9017ccbe224a98e: $$\color{blue} \sigma_{Cond1}(R) \cdot \sigma_{Cond2}(R)$$
b27dce7f698d0d6d61cc4053afd94af2b56a44f3: $$\color{blue} \sigma_{\text{Cond1 OR Cond2}}(R)$$
b70ab77b11f07c66ac9e35c6f66e1c602b577b8a: $$\color{blue} \frac{T(R)·T(S)}{max[V(R,Y),V(S,Y)]}$$
7d937ad12ec0c9dfcd6d31e1f248b6dd40f01bb0: $$\color{blue}\frac{T(R) · T(S)}{ ( max[V(R,Y1),V(S,Y1)] \cdot max[V(R,Y2),V(S,Y2)] }$$
15582ae65de85328482a09b986687dbf46ffd2fe: [[Pasted Image 20240207140811_360.png]]
38761b24ed3faeb2000a8d3b3c85b92dc595c286: [[Pasted Image 20240207140921_387.png]]
95b19e1c48f71f17dd9c9925c3bd29ad0c7202be: [[Pasted Image 20240207140951_398.png]]
879a170abb0d1ba5c63aa532245cae57ccce7c76: [[Pasted Image 20240207141021_401.png]]
558073b3789e6b48883f82e6c1eb4ac2af6d3873: [[Pasted Image 20240207141136_406.png]]

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.20",
	"elements": [
		{
			"type": "image",
			"version": 143,
			"versionNonce": 1989527296,
			"isDeleted": false,
			"id": "D7fFgJx0ohsFckztISnwu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -273.3353791755549,
			"y": -285.4413211329676,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 188.90793785353975,
			"height": 22.95756189192323,
			"seed": 1256597509,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485593,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "879a170abb0d1ba5c63aa532245cae57ccce7c76",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 195,
			"versionNonce": 1003366656,
			"isDeleted": false,
			"id": "Xq51bQypqJ5_hSsSCOunQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -277.25716696302,
			"y": -324.41920001992105,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 244.74455769072125,
			"height": 39.9998030574863,
			"seed": 197829797,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [
				{
					"id": "RK-QaYv8VtTHzGZQIXJJE",
					"type": "arrow"
				},
				{
					"id": "t_hQDi1nPiI0BXBvm5IuB",
					"type": "arrow"
				}
			],
			"updated": 1707838485593,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "38761b24ed3faeb2000a8d3b3c85b92dc595c286",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 844,
			"versionNonce": 1313138432,
			"isDeleted": false,
			"id": "ykxcCrZ9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 71.17544268597698,
			"y": -678.337890818349,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 255.3050537109375,
			"height": 35,
			"seed": 914903973,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485593,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Query Optimization",
			"rawText": "Query Optimization",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Query Optimization",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 1134,
			"versionNonce": 1377896704,
			"isDeleted": false,
			"id": "01udynON",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -317.967290756501,
			"y": -639.1042895349772,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1029.5389404296875,
			"height": 875,
			"seed": 1409626795,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485593,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* The parsing and pre-processing stage consists of converting the SQL text query into a grammar tree\n  and checking the validity of these expressions and the existence of these attributes in each table\n\n* Transformation rules: we want to transform the operators in order to achieve smaller intermediate\n  results without changing the semantics of the query.\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n* Logical query plan selection: 1) Translate parse tree into a relational algebra expression\n                              2) Represent the expression as a tree\n                              3) Resolve sub-queries\n                              4) Improve the logical query plan according to algebraic laws\n\n\n\n\n\n* Physical query plan selection: Picking the right physical query plans from the logical one raises some\nquestions like which order of operations to take for associative/commutative operations, which\nimplementation to use when to put scans and sorts, and what type of data transport do we choose?\n\n* Cost estimation: Evaluate the cost of each physical plan w.r.t intermediate results and num of I/O\n* intermediate result estimation: measuring output cardinality. (Does the data fit into main memory?)",
			"rawText": "* The parsing and pre-processing stage consists of converting the SQL text query into a grammar tree\n  and checking the validity of these expressions and the existence of these attributes in each table\n\n* Transformation rules: we want to transform the operators in order to achieve smaller intermediate\n  results without changing the semantics of the query.\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n* Logical query plan selection: 1) Translate parse tree into a relational algebra expression\n                              2) Represent the expression as a tree\n                              3) Resolve sub-queries\n                              4) Improve the logical query plan according to algebraic laws\n\n\n\n\n\n* Physical query plan selection: Picking the right physical query plans from the logical one raises some\nquestions like which order of operations to take for associative/commutative operations, which\nimplementation to use when to put scans and sorts, and what type of data transport do we choose?\n\n* Cost estimation: Evaluate the cost of each physical plan w.r.t intermediate results and num of I/O\n* intermediate result estimation: measuring output cardinality. (Does the data fit into main memory?)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* The parsing and pre-processing stage consists of converting the SQL text query into a grammar tree\n  and checking the validity of these expressions and the existence of these attributes in each table\n\n* Transformation rules: we want to transform the operators in order to achieve smaller intermediate\n  results without changing the semantics of the query.\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n* Logical query plan selection: 1) Translate parse tree into a relational algebra expression\n                              2) Represent the expression as a tree\n                              3) Resolve sub-queries\n                              4) Improve the logical query plan according to algebraic laws\n\n\n\n\n\n* Physical query plan selection: Picking the right physical query plans from the logical one raises some\nquestions like which order of operations to take for associative/commutative operations, which\nimplementation to use when to put scans and sorts, and what type of data transport do we choose?\n\n* Cost estimation: Evaluate the cost of each physical plan w.r.t intermediate results and num of I/O\n* intermediate result estimation: measuring output cardinality. (Does the data fit into main memory?)",
			"lineHeight": 1.25,
			"baseline": 868
		},
		{
			"type": "text",
			"version": 244,
			"versionNonce": 588252928,
			"isDeleted": false,
			"id": "02eTxaLn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -298.00593030538977,
			"y": -517.1843190164052,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 842.817626953125,
			"height": 20,
			"seed": 1754855947,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Two terms are equivalent if both terms work on the same relations and always produce the same results",
			"rawText": "Two terms are equivalent if both terms work on the same relations and always produce the same results",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Two terms are equivalent if both terms work on the same relations and always produce the same results",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 382,
			"versionNonce": 1528293632,
			"isDeleted": false,
			"id": "weCn9GHa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -298.0059304687724,
			"y": -497.18431854860773,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 944.3392944335938,
			"height": 275,
			"seed": 112770181,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) X is commutative and associative  R X S = S X R     ,     (R X S) X T = R X (S X T)\n2) U is commutative and associative  R U S = S U R    ,     (R U S) U T = R U (S U T)\n3) ∩ is commutative and associative  R ∩ S = S ∩ R    ,     (R ∩ S) ∩ T = R ∩ (S ∩ T)\n4) ⋈ is commutative and associative  R ⋈ S = S ⋈ R   ,     (R ⋈ S) ⋈ T = R ⋈ (S ⋈ T)\n5)\n\n\n\n\n\n6)",
			"rawText": "1) X is commutative and associative  R X S = S X R     ,     (R X S) X T = R X (S X T)\n2) U is commutative and associative  R U S = S U R    ,     (R U S) U T = R U (S U T)\n3) ∩ is commutative and associative  R ∩ S = S ∩ R    ,     (R ∩ S) ∩ T = R ∩ (S ∩ T)\n4) ⋈ is commutative and associative  R ⋈ S = S ⋈ R   ,     (R ⋈ S) ⋈ T = R ⋈ (S ⋈ T)\n5)\n\n\n\n\n\n6)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) X is commutative and associative  R X S = S X R     ,     (R X S) X T = R X (S X T)\n2) U is commutative and associative  R U S = S U R    ,     (R U S) U T = R U (S U T)\n3) ∩ is commutative and associative  R ∩ S = S ∩ R    ,     (R ∩ S) ∩ T = R ∩ (S ∩ T)\n4) ⋈ is commutative and associative  R ⋈ S = S ⋈ R   ,     (R ⋈ S) ⋈ T = R ⋈ (S ⋈ T)\n5)\n\n\n\n\n\n6)",
			"lineHeight": 1.25,
			"baseline": 268
		},
		{
			"type": "image",
			"version": 192,
			"versionNonce": 1903634176,
			"isDeleted": false,
			"id": "om-3OXz0j5WbSbZLDuJgt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -276.3236445597384,
			"y": -398.72841441932894,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 252.716059021292,
			"height": 77.37654616101356,
			"seed": 131064933,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "15582ae65de85328482a09b986687dbf46ffd2fe",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "line",
			"version": 185,
			"versionNonce": 1647495424,
			"isDeleted": false,
			"id": "krsqk1rLNxpFMrX1TjO0d",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -37.93685821768083,
			"y": -376.20773283112595,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 19.77018083206056,
			"height": 49.64047001254779,
			"seed": 2013677931,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707838485594,
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
					7.908072332824215,
					1.0341764585947402
				],
				[
					7.908072332824215,
					17.58099979611067
				],
				[
					18.64045621308563,
					19.64935271330015
				],
				[
					8.472934642311655,
					28.956940840652898
				],
				[
					9.037796951799097,
					49.64047001254779
				],
				[
					-1.1297246189749284,
					48.60629355395305
				]
			]
		},
		{
			"type": "text",
			"version": 105,
			"versionNonce": 637159168,
			"isDeleted": false,
			"id": "eXq6cqIk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -9.203221641832044,
			"y": -369.78869384322644,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 159.4723358154297,
			"height": 20,
			"seed": 29542341,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Not in case of bags",
			"rawText": "Not in case of bags",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Not in case of bags",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 150,
			"versionNonce": 49391872,
			"isDeleted": false,
			"id": "1IgzTG_KLsbb9nGEGKD1o",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -30.369609290605013,
			"y": -300.74478501435703,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 131.2653633623953,
			"height": 13.757068649334006,
			"seed": 481065349,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [
				{
					"id": "RK-QaYv8VtTHzGZQIXJJE",
					"type": "arrow"
				}
			],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "95b19e1c48f71f17dd9c9925c3bd29ad0c7202be",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 146,
			"versionNonce": 488204032,
			"isDeleted": false,
			"id": "RK-QaYv8VtTHzGZQIXJJE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -44.16269791751989,
			"y": -292.7548252817665,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 25.066873751794958,
			"height": 0.3978868849491164,
			"seed": 1263423557,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "1IgzTG_KLsbb9nGEGKD1o",
				"focus": 0.2995019197926415,
				"gap": 13.79308862691488
			},
			"endBinding": {
				"elementId": "Xq51bQypqJ5_hSsSCOunQ",
				"focus": -0.45150096867232936,
				"gap": 13.416785106573826
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
					25.066873751794958,
					0.3978868849491164
				]
			]
		},
		{
			"type": "arrow",
			"version": 142,
			"versionNonce": 1758759168,
			"isDeleted": false,
			"id": "t_hQDi1nPiI0BXBvm5IuB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -87.38355882772294,
			"y": -271.9810716902002,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 32.04760058605376,
			"height": 0,
			"seed": 17688421,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Xq51bQypqJ5_hSsSCOunQ",
				"focus": 1.6219193256706077,
				"gap": 12.438325272234493
			},
			"endBinding": {
				"elementId": "MzXSgfSO",
				"focus": 0.033046534041483264,
				"gap": 13.813620942264492
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
					32.04760058605376,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 101,
			"versionNonce": 592742144,
			"isDeleted": false,
			"id": "MzXSgfSO",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -41.52233729940468,
			"y": -281.6506063497854,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 234.64051818847656,
			"height": 20,
			"seed": 576760389,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [
				{
					"id": "t_hQDi1nPiI0BXBvm5IuB",
					"type": "arrow"
				}
			],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "if S only has attributes of R",
			"rawText": "if S only has attributes of R",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "if S only has attributes of R",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 180,
			"versionNonce": 1331390720,
			"isDeleted": false,
			"id": "0AVD9u9P-EAL1XbWlbsI6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -275.6398789361901,
			"y": -248.19944313945302,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 261.5503830369151,
			"height": 87.90398548348111,
			"seed": 810578219,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "558073b3789e6b48883f82e6c1eb4ac2af6d3873",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 200,
			"versionNonce": 1965795072,
			"isDeleted": false,
			"id": "yW9nqunP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 14.436505180010897,
			"y": -38.26958506776213,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 366.4007568359375,
			"height": 100,
			"seed": 361720709,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1) Push down selections as early as possible\n2) Push down Projections as early as possible\n3) adjust duplicate elimination\n4) Combine selection and cross product to join\n5) Group union and join operators",
			"rawText": "1) Push down selections as early as possible\n2) Push down Projections as early as possible\n3) adjust duplicate elimination\n4) Combine selection and cross product to join\n5) Group union and join operators",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Push down selections as early as possible\n2) Push down Projections as early as possible\n3) adjust duplicate elimination\n4) Combine selection and cross product to join\n5) Group union and join operators",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "text",
			"version": 275,
			"versionNonce": 33966336,
			"isDeleted": false,
			"id": "lEUaO0I6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -318.2564524873142,
			"y": 238.14244499743398,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1019.7298583984375,
			"height": 20,
			"seed": 1504802315,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "* Output cardinality = Input Cardinality * Selectivity,  B(R)= Blocks in R,  T(R)= Tuples in R, V(A,R)= distinct values of A in R",
			"rawText": "* Output cardinality = Input Cardinality * Selectivity,  B(R)= Blocks in R,  T(R)= Tuples in R, V(A,R)= distinct values of A in R",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Output cardinality = Input Cardinality * Selectivity,  B(R)= Blocks in R,  T(R)= Tuples in R, V(A,R)= distinct values of A in R",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 1200,
			"versionNonce": 1058981632,
			"isDeleted": false,
			"id": "V013sntn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -315.7660761617963,
			"y": 259.59277953187564,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1010.2789306640625,
			"height": 600,
			"seed": 565846379,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Projection estimation: Immediate estimation of tuple size according to attributes (straightforward)\n* Selection estimation:\n                                                                           5)\n1)                                 3)     \n\n2)                                4)\n\n\n\n* Join Size/Cardinality estimation:\n\n1) T(R ⋈ S) =                    2) T(R(Y1, Y2) ⋈ S(Y1, Y2)) = \n\n\n* When joining on a comparsion, just multiply both sizes R⋈σ(S) =  T(R) * 1/V(S)\n\n* Join Cost/order estimation:\n  R ⋈ S, such that R and S can contain more joins in them = Sum of Size of intermediate joins \n\n* Union estimation:  AVG[T(R) + T(S), max[T(R), T(S)] ]\n* Intersection estimation: consider as join\n* Difference estimation: T(R) – T(S)/2\n* Duplicate elimination estimation: min[T(R)/2, ∏i V(R, Ai)]\n* Aggregation estimation:  min[T(R)/2, ∏i V(R, Li)]",
			"rawText": "* Projection estimation: Immediate estimation of tuple size according to attributes (straightforward)\n* Selection estimation:\n                                                                           5)\n1)                                 3)     \n\n2)                                4)\n\n\n\n* Join Size/Cardinality estimation:\n\n1) T(R ⋈ S) =                    2) T(R(Y1, Y2) ⋈ S(Y1, Y2)) = \n\n\n* When joining on a comparsion, just multiply both sizes R⋈σ(S) =  T(R) * 1/V(S)\n\n* Join Cost/order estimation:\n  R ⋈ S, such that R and S can contain more joins in them = Sum of Size of intermediate joins \n\n* Union estimation:  AVG[T(R) + T(S), max[T(R), T(S)] ]\n* Intersection estimation: consider as join\n* Difference estimation: T(R) – T(S)/2\n* Duplicate elimination estimation: min[T(R)/2, ∏i V(R, Ai)]\n* Aggregation estimation:  min[T(R)/2, ∏i V(R, Li)]",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Projection estimation: Immediate estimation of tuple size according to attributes (straightforward)\n* Selection estimation:\n                                                                           5)\n1)                                 3)     \n\n2)                                4)\n\n\n\n* Join Size/Cardinality estimation:\n\n1) T(R ⋈ S) =                    2) T(R(Y1, Y2) ⋈ S(Y1, Y2)) = \n\n\n* When joining on a comparsion, just multiply both sizes R⋈σ(S) =  T(R) * 1/V(S)\n\n* Join Cost/order estimation:\n  R ⋈ S, such that R and S can contain more joins in them = Sum of Size of intermediate joins \n\n* Union estimation:  AVG[T(R) + T(S), max[T(R), T(S)] ]\n* Intersection estimation: consider as join\n* Difference estimation: T(R) – T(S)/2\n* Duplicate elimination estimation: min[T(R)/2, ∏i V(R, Ai)]\n* Aggregation estimation:  min[T(R)/2, ∏i V(R, Li)]",
			"lineHeight": 1.25,
			"baseline": 593
		},
		{
			"type": "arrow",
			"version": 284,
			"versionNonce": 1549084928,
			"isDeleted": false,
			"id": "sbRedwhyE34-BCRnVKSqy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -207.59560488862172,
			"y": 344.67979339338626,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 80.21635846726224,
			"height": 2.018021596660674,
			"seed": 1689259781,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707838485594,
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
					38.8469157357182,
					-0.6415905524852406
				],
				[
					80.21635846726224,
					1.3764310441754333
				]
			]
		},
		{
			"type": "text",
			"version": 102,
			"versionNonce": 497936128,
			"isDeleted": false,
			"id": "sLjhpEZX",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 110.04482844466315,
			"y": 408.05841878526746,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 218.22445678710938,
			"height": 20,
			"seed": 608285355,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Assuming theyre independent",
			"rawText": "Assuming theyre independent",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Assuming theyre independent",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 492,
			"versionNonce": 1237846272,
			"isDeleted": false,
			"id": "oqA6foDr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -316.6538155282347,
			"y": 562.7020190281809,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 995.5859985351562,
			"height": 40,
			"seed": 967209323,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "general approach: Multiply all the cardinalities, divided by selectivity.\nto get selectivity, if attribute occurs once dont add it, if it occurs more than once then add all its values except smallest",
			"rawText": "general approach: Multiply all the cardinalities, divided by selectivity.\nto get selectivity, if attribute occurs once dont add it, if it occurs more than once then add all its values except smallest",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "general approach: Multiply all the cardinalities, divided by selectivity.\nto get selectivity, if attribute occurs once dont add it, if it occurs more than once then add all its values except smallest",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "frame",
			"version": 1520,
			"versionNonce": 1890498769,
			"isDeleted": false,
			"id": "nulGDWDOQKvvWPdeNK46A",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -319.3895085077532,
			"y": -678.3378909063267,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 1039.816207,
			"height": 1547.605425089637,
			"seed": 1394339589,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708099389387,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#7A7A7A"
				}
			},
			"name": "QueryOptimization"
		},
		{
			"type": "image",
			"version": 207,
			"versionNonce": 1172236544,
			"isDeleted": false,
			"id": "tnBIi0cJ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -298.64526358677296,
			"y": 331.9553594129313,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 80.18922676493716,
			"height": 23.105370423795453,
			"seed": 57025,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "fbb4e941782628101e3d0ef1b4aa4cbde42dbc8d",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 57,
			"versionNonce": 983574272,
			"isDeleted": false,
			"id": "OafMdc0l",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -115.9872766939896,
			"y": 326.0562244375617,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 65,
			"height": 40,
			"seed": 54640,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "820e043bc11f5f0ee14a64379577ab2b8d2285c1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 238,
			"versionNonce": 1545193728,
			"isDeleted": false,
			"id": "z01hEbJ4Mu3VQo72UQNQA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -290.9120394617319,
			"y": 383.20849737800614,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 80.18922676493716,
			"height": 23.105370423795453,
			"seed": 1470672907,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [
				{
					"id": "7XZgJUusCEHRzbb9F8RH8",
					"type": "arrow"
				}
			],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "eb6568d565c8d770c2c540f237b8efee2eeaa6a5",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 396,
			"versionNonce": 1644381952,
			"isDeleted": false,
			"id": "7XZgJUusCEHRzbb9F8RH8",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -203.3956864165777,
			"y": 400.1065274873223,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 82.86761765146497,
			"height": 0.7469191353749807,
			"seed": 548733765,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "z01hEbJ4Mu3VQo72UQNQA",
				"focus": 0.5017286148234439,
				"gap": 7.327126280217044
			},
			"endBinding": {
				"elementId": "btSNHDDrzR5SwRKs8RRa4",
				"gap": 11.391969727369883,
				"focus": -0.09919089203925348
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
					38.8469157357182,
					-0.6415905524852406
				],
				[
					82.86761765146497,
					0.10532858288974012
				]
			]
		},
		{
			"type": "image",
			"version": 104,
			"versionNonce": 670607616,
			"isDeleted": false,
			"id": "btSNHDDrzR5SwRKs8RRa4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -109.13609903774278,
			"y": 378.67945002951495,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 50.286995313362965,
			"height": 40.22959625069037,
			"seed": 1478382245,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [
				{
					"id": "7XZgJUusCEHRzbb9F8RH8",
					"type": "arrow"
				}
			],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2b7b16099d2f0f53dfc10064e33aeff03d58b1c8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 445,
			"versionNonce": 1879205632,
			"isDeleted": false,
			"id": "cDw2qGJn1TgZBLL38nkgf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 145.25254424618885,
			"y": 340.2827216071363,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 65.01498957163034,
			"height": 0.8800507340278045,
			"seed": 922652939,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707838485594,
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
					38.8469157357182,
					-0.6415905524852406
				],
				[
					65.01498957163034,
					-0.8800507340278045
				]
			]
		},
		{
			"type": "image",
			"version": 259,
			"versionNonce": 1425770752,
			"isDeleted": false,
			"id": "4zUZkM2_W0gMTlbG31g6h",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 55.33253861790705,
			"y": 327.2233578279555,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 77.92992062519829,
			"height": 23.775230021246937,
			"seed": 1388197803,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "2e97ae80e6235a38660aa48c667281b8a75b81dc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 189,
			"versionNonce": 824018688,
			"isDeleted": false,
			"id": "-2MG6PgzRJxo3iAPdB3w8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 221.65950354518907,
			"y": 316.7950373034379,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 142.72404042008475,
			"height": 39.64556678335688,
			"seed": 823134795,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d4ca8062b00e396668ed0c22e47bf3c5380d573b",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 110,
			"versionNonce": 513960192,
			"isDeleted": false,
			"id": "oHvZBHY5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 49.28181952308232,
			"y": 389.2455082177831,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 142.26238423341027,
			"height": 17.91452245902203,
			"seed": 37506,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [
				{
					"id": "YUCc7JzUGBcbRm7P7gziw",
					"type": "arrow"
				}
			],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d8437bf6b9ff26ceac5687390477c727a24f7e56",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 562,
			"versionNonce": 1641326336,
			"isDeleted": false,
			"id": "YUCc7JzUGBcbRm7P7gziw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 202.04648259146222,
			"y": 398.7608337284415,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 35.77895135266908,
			"height": 0.8800507340278045,
			"seed": 1580757163,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "oHvZBHY5",
				"focus": 0.10182727914346174,
				"gap": 10.50227883496963
			},
			"endBinding": {
				"elementId": "3VhCLxCqYCP6z0DDlFYn0",
				"focus": 0.28965303220804367,
				"gap": 11.504506217568334
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
					11.949760574273796,
					-0.0568697881060416
				],
				[
					35.77895135266908,
					-0.8800507340278045
				]
			]
		},
		{
			"type": "image",
			"version": 269,
			"versionNonce": 1349339392,
			"isDeleted": false,
			"id": "3VhCLxCqYCP6z0DDlFYn0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 250.445499460954,
			"y": 388.5465204380244,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 170.6733285888989,
			"height": 19.088464381653168,
			"seed": 584786763,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [
				{
					"id": "YUCc7JzUGBcbRm7P7gziw",
					"type": "arrow"
				}
			],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6878c9f5a4513817033b8783a9017ccbe224a98e",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "arrow",
			"version": 328,
			"versionNonce": 782747392,
			"isDeleted": false,
			"id": "5QPhjFmeb6kfUAnQ92uje",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 608.654023984104,
			"y": 317.21082924001877,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 72.0354640352162,
			"height": 32.06594203155822,
			"seed": 622116459,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707838485594,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "HlKUWDIQVW6S99fvTzIh8",
				"focus": -0.7335405332131375,
				"gap": 10.674098292161176
			},
			"endBinding": {
				"elementId": "xosNSTzn",
				"focus": 0.9503213972495652,
				"gap": 8.4733392087428
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
					72.0354640352162,
					14.525769768993598
				],
				[
					17.751662910575305,
					32.06594203155822
				]
			]
		},
		{
			"type": "text",
			"version": 251,
			"versionNonce": 1172056320,
			"isDeleted": false,
			"id": "xosNSTzn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 450.139989287499,
			"y": 333.8581745017519,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 167.7923583984375,
			"height": 20,
			"seed": 1818736907,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [
				{
					"id": "5QPhjFmeb6kfUAnQ92uje",
					"type": "arrow"
				}
			],
			"updated": 1707838485595,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "T1 + T2 - (T1 * T2)",
			"rawText": "T1 + T2 - (T1 * T2)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "T1 + T2 - (T1 * T2)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 221,
			"versionNonce": 873916160,
			"isDeleted": false,
			"id": "tvzBkqeh",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 460.9842677693953,
			"y": 354.3232353940684,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 137.6412353515625,
			"height": 24.555278406917076,
			"seed": 1354915755,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485595,
			"link": null,
			"locked": false,
			"fontSize": 9.82211136276683,
			"fontFamily": 1,
			"text": "Ti being tuples that satisfy\ncondition i",
			"rawText": "Ti being tuples that satisfy\ncondition i",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Ti being tuples that satisfy\ncondition i",
			"lineHeight": 1.25,
			"baseline": 20
		},
		{
			"type": "text",
			"version": 160,
			"versionNonce": 1785661696,
			"isDeleted": false,
			"id": "8IWW9Ogm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 475.4791739599882,
			"y": 376.35200179226814,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 103.10423278808594,
			"height": 40,
			"seed": 743387723,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485595,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Or also\nn(1 - F1 - F2)",
			"rawText": "Or also\nn(1 - F1 - F2)",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Or also\nn(1 - F1 - F2)",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "line",
			"version": 107,
			"versionNonce": 2124547840,
			"isDeleted": false,
			"id": "Fa2IR3EtJCOQXM7WLO8sU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 516.5211435068207,
			"y": 420.24884517479114,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 13.610809115468214,
			"height": 13.349062786324623,
			"seed": 803778795,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707838485595,
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
					-13.610809115468214,
					13.349062786324623
				]
			]
		},
		{
			"type": "text",
			"version": 194,
			"versionNonce": 967174400,
			"isDeleted": false,
			"id": "F790zTLl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 444.6147303511011,
			"y": 436.08360839576454,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 75.83200073242188,
			"height": 31.60141298013285,
			"seed": 219765643,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485595,
			"link": null,
			"locked": false,
			"fontSize": 8.42704346136876,
			"fontFamily": 1,
			"text": "fraction of\nrecords that dont\nsatisfy cond1",
			"rawText": "fraction of\nrecords that dont\nsatisfy cond1",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "fraction of\nrecords that dont\nsatisfy cond1",
			"lineHeight": 1.25,
			"baseline": 28
		},
		{
			"type": "line",
			"version": 109,
			"versionNonce": 180954880,
			"isDeleted": false,
			"id": "ooXvsJwabEasxzATe13Bs",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 563.8972290818158,
			"y": 420.24884517479114,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 11.77858481146285,
			"height": 12.563823798893736,
			"seed": 1612427819,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707838485595,
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
					11.77858481146285,
					12.563823798893736
				]
			]
		},
		{
			"type": "image",
			"version": 218,
			"versionNonce": 1057016064,
			"isDeleted": false,
			"id": "HlKUWDIQVW6S99fvTzIh8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 459.99709214055747,
			"y": 308.8906824547028,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 137.9828335513853,
			"height": 18.47014307380748,
			"seed": 1507472587,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [
				{
					"id": "5QPhjFmeb6kfUAnQ92uje",
					"type": "arrow"
				}
			],
			"updated": 1707838485595,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b27dce7f698d0d6d61cc4053afd94af2b56a44f3",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 243,
			"versionNonce": 1158432512,
			"isDeleted": false,
			"id": "aJ7j9Exx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 544.9944475776792,
			"y": 432.97848856137915,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 75.83200073242188,
			"height": 31.60141298013285,
			"seed": 703554411,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485595,
			"link": null,
			"locked": false,
			"fontSize": 8.42704346136876,
			"fontFamily": 1,
			"text": "fraction of\nrecords that dont\nsatisfy cond2",
			"rawText": "fraction of\nrecords that dont\nsatisfy cond2",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "fraction of\nrecords that dont\nsatisfy cond2",
			"lineHeight": 1.25,
			"baseline": 28
		},
		{
			"type": "image",
			"version": 109,
			"versionNonce": 369076480,
			"isDeleted": false,
			"id": "MZm26x7G",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -165.5639812067525,
			"y": 527.4623278967686,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 141.31241983633285,
			"height": 32.863353450309965,
			"seed": 65455,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485595,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b70ab77b11f07c66ac9e35c6f66e1c602b577b8a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 225,
			"versionNonce": 166422272,
			"isDeleted": false,
			"id": "bvdvDAxX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 318.48979977435476,
			"y": 523.390885415463,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 388.49967824954496,
			"height": 40.051513221602576,
			"seed": 25979,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485595,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "7d937ad12ec0c9dfcd6d31e1f248b6dd40f01bb0",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 1010,
			"versionNonce": 1780648192,
			"isDeleted": false,
			"id": "UutKlFG6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -88.17147021490507,
			"y": 932.6533583539576,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 589.9345092773438,
			"height": 35,
			"seed": 1781061637,
			"groupIds": [],
			"frameId": "7m-0C_qL7uJorguORBNxg",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485595,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "    Useless stuff form Query Optimization",
			"rawText": "    Useless stuff form Query Optimization",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "    Useless stuff form Query Optimization",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 1611,
			"versionNonce": 635864832,
			"isDeleted": false,
			"id": "3igvfc5b",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -311.9467573003226,
			"y": 967.6533580201748,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1024.3189697265625,
			"height": 825,
			"seed": 925101285,
			"groupIds": [],
			"frameId": "7m-0C_qL7uJorguORBNxg",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485595,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Considerations for Collecting Statistics: Statistics do not change rapidly in short periods of time\nand even slightly inaccurate statistics are helpful, so we dont have to keep them up to date all the\ntime due to the operation being expensive, thus we perform sampling and only trigger statistics over\ncertain periods of time/ after certain amount of updates\n\n* Too many physical plans to go over, how do we pick best one? Heuristics!\n  determine join pair with the smallest intermediate result, and keep joining with relations that produce\n  smallest intermediate results.\n  Use index-scan/index-join when selection/join on indexed attribute\n  Apply multiple selections on same relation at the same time\n  Use sort-merge-join if one relation is sorted on the join attribute\n  Compute union and intersection for smallest relations first.\n\n* Branch and bound: find a plan and establish upper-bound, enumerate over subplans of parts of the\n  query, if cost of subplans are higher than upper bound then dump em, lower upperbound if better \n  complete plan found.\n\n* Hill Climbing: find a plan, change one subplan at a time until you find a better plan, if no plans are \n  better then terminate, do this over 10 random plans.\n\n* Dynamic programming: save best subplan for one operator, build best partial plan that consists of \n  that subplan in it.\n\n* Selinger-style: same as dynamic programming but Do not only memorize the best plan, Also keep track\n  of miscellaneous sorting variants (intresting orders)\n\n* When choosing the best partial plan, Cost comparison will not suffice, sort orders must be considered\n\n* Bottom-Up Query Plan Generation: this approach assumes that the choice of join method i is\n  independent of all previous choices, and a sub plan of an optimal plan is also optimal.\n1) Compute optimal plans for the join of every combination of k relations\n2) Ignore Suboptimal plans\n3) Extend this concept to k+1 relations",
			"rawText": "* Considerations for Collecting Statistics: Statistics do not change rapidly in short periods of time\nand even slightly inaccurate statistics are helpful, so we dont have to keep them up to date all the\ntime due to the operation being expensive, thus we perform sampling and only trigger statistics over\ncertain periods of time/ after certain amount of updates\n\n* Too many physical plans to go over, how do we pick best one? Heuristics!\n  determine join pair with the smallest intermediate result, and keep joining with relations that produce\n  smallest intermediate results.\n  Use index-scan/index-join when selection/join on indexed attribute\n  Apply multiple selections on same relation at the same time\n  Use sort-merge-join if one relation is sorted on the join attribute\n  Compute union and intersection for smallest relations first.\n\n* Branch and bound: find a plan and establish upper-bound, enumerate over subplans of parts of the\n  query, if cost of subplans are higher than upper bound then dump em, lower upperbound if better \n  complete plan found.\n\n* Hill Climbing: find a plan, change one subplan at a time until you find a better plan, if no plans are \n  better then terminate, do this over 10 random plans.\n\n* Dynamic programming: save best subplan for one operator, build best partial plan that consists of \n  that subplan in it.\n\n* Selinger-style: same as dynamic programming but Do not only memorize the best plan, Also keep track\n  of miscellaneous sorting variants (intresting orders)\n\n* When choosing the best partial plan, Cost comparison will not suffice, sort orders must be considered\n\n* Bottom-Up Query Plan Generation: this approach assumes that the choice of join method i is\n  independent of all previous choices, and a sub plan of an optimal plan is also optimal.\n1) Compute optimal plans for the join of every combination of k relations\n2) Ignore Suboptimal plans\n3) Extend this concept to k+1 relations",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Considerations for Collecting Statistics: Statistics do not change rapidly in short periods of time\nand even slightly inaccurate statistics are helpful, so we dont have to keep them up to date all the\ntime due to the operation being expensive, thus we perform sampling and only trigger statistics over\ncertain periods of time/ after certain amount of updates\n\n* Too many physical plans to go over, how do we pick best one? Heuristics!\n  determine join pair with the smallest intermediate result, and keep joining with relations that produce\n  smallest intermediate results.\n  Use index-scan/index-join when selection/join on indexed attribute\n  Apply multiple selections on same relation at the same time\n  Use sort-merge-join if one relation is sorted on the join attribute\n  Compute union and intersection for smallest relations first.\n\n* Branch and bound: find a plan and establish upper-bound, enumerate over subplans of parts of the\n  query, if cost of subplans are higher than upper bound then dump em, lower upperbound if better \n  complete plan found.\n\n* Hill Climbing: find a plan, change one subplan at a time until you find a better plan, if no plans are \n  better then terminate, do this over 10 random plans.\n\n* Dynamic programming: save best subplan for one operator, build best partial plan that consists of \n  that subplan in it.\n\n* Selinger-style: same as dynamic programming but Do not only memorize the best plan, Also keep track\n  of miscellaneous sorting variants (intresting orders)\n\n* When choosing the best partial plan, Cost comparison will not suffice, sort orders must be considered\n\n* Bottom-Up Query Plan Generation: this approach assumes that the choice of join method i is\n  independent of all previous choices, and a sub plan of an optimal plan is also optimal.\n1) Compute optimal plans for the join of every combination of k relations\n2) Ignore Suboptimal plans\n3) Extend this concept to k+1 relations",
			"lineHeight": 1.25,
			"baseline": 818
		},
		{
			"type": "frame",
			"version": 1583,
			"versionNonce": 1021408945,
			"isDeleted": false,
			"id": "7m-0C_qL7uJorguORBNxg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -323.357301408635,
			"y": 914.31159626598,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 1039.816207,
			"height": 881.4097526203587,
			"seed": 155086597,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708099389387,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#7A7A7A"
				}
			},
			"name": "QueryOptimization"
		},
		{
			"type": "text",
			"version": 186,
			"versionNonce": 1434298112,
			"isDeleted": false,
			"id": "2kcMwZH5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -297.04384823008945,
			"y": 706.9022408109512,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 698.5592651367188,
			"height": 25,
			"seed": 1760287115,
			"groupIds": [],
			"frameId": "nulGDWDOQKvvWPdeNK46A",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838485595,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "ignore cross products when considering cheapest cost, theyre expensive",
			"rawText": "ignore cross products when considering cheapest cost, theyre expensive",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "ignore cross products when considering cheapest cost, theyre expensive",
			"lineHeight": 1.25,
			"baseline": 18
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
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 591.6794140089356,
		"scrollY": 648.150760121403,
		"zoom": {
			"value": 1.3575370403041942
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