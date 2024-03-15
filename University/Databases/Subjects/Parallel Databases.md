---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - databases
---
Next [[Computations]]
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Parallel Databases ^dWmjNYeP

%%***>>>text element-link:[[Computations]]<<<***%%* So far we have only considered single-Threaded/Serial System that manages all the data, now we 
  are upgrading our ideas to extend beyond that into parallel databases.
*                    : the machines are homogeneous and tightly coupled, clusters with direct network
  connection, multi-processor system, everything works together. (Optimized for performance)
*                        : machines can be hetrogeneous and are loosely coupled, long distance network
  connections, can act independently. (Optimized for reliability).
* Speedup is the runtime of a sequential program and the run of a parallel program over p nodes

* Amdahl's Law : Theoretical maximal speedup is determined by by the sequential part of the program

* Gustafon's Law More processors are usually added to solve a larger problem in the same time

* Homogeneous distributed database: machines are aware of each other, have the same software and
  work together in order to process user requests, appears as a single system




* Instruction Parallelism: Single instructions are automatically processed in parallel by the hardware
* Data parallelism: Each processing unit executes the same operations on its share of the input data
  Independently 
* Task parallelism: Tasks (work/data) are distributed among the processors/nodes each processor
  executes a different thread/process

* Inter-Query parallelism (efficient resource utilization): While one query waits for I/O, another executes
  Requires concurrency control, important for highly transactional data

* Intra-Query Parallelism: Parallel processing of a single query, whether its concurrent I/O from multiple
  disk, Data Parallelism where multiple threads work on the same operator, or pipeline parallelism where
  multiple pipelines work on different pipelines of the plan in parallel. Important for Analytical Data





* Distribution: Deciding what data goes where











* Types of partitioning:
* Horizontal Partitioning: split table into slices of records with the same schema, each record only
  occurs once per slice and slice is placed where it is most often read, This can be done through
  round robin which guarantees equal size but no relation between tuples, Hash Partitioned over a 
  column value which guarantees tuples with similar column values are together, range partition where
  define a specific range over certain columns and slice the records such that theyre in the same range
* Vertical Partitioning: Partition table in multiple vertical slices, each of which requires a key, useful
  if the the entire table is frequently used but over different values, allows us to process only 
  required attributes and place them where theyre frequently used.

* Distributed transactions: Each site has a local transaction manager responsible for manaing the logs
  for recovery purposes and coordinating the concurrent execution of the transactions at that site.
  Each site also has a transaction coordinator which is responsible for Starting the execution of
  transactions that originate at the site and redirecting the sub-transactions that need to be at
  other sites. This responsibility also includes the termination of transactions that originate at that
  site.

* Failures related to distributed systems: 1) Failure of one site   2) Message loss   3) Failure of 
      communication link
  4) Network partitioning failure (missing connection between two subsystems after partitioning)

* Committing across different sites adds a lot more consistency complexity and global coordination
* Two-Phase Commit: 
1) Phase 1: Vote collection phase : Coordinator contacts everyone to make a decision, waits for response
2) Phase 2: Vote Collection Phase: if all agree, the decision is to commit, otherwise abort
3) Phase 3: Decision Phase: Coordinator contacts all with the final decision

* Distributed Query Processing: This is just an extension of centralized query processing except we 
  can exploit replication and fragmentation, harder to estimate cost due to network inconsistencies.
  Dont forget to include send and receive operators in algebra.

* High locality = Nodes own partitions exclusively
* Low locality = All nodes own equal portions of each partition ^uaETZVbv

Parallel databases ^KCpvYTgE

Distributed databases ^AUaMEOvL

Describes how much faster we get by running the parallel algorithm on p nodes, the fastest speedup is linear ^Hgd9k7W9

P is the fraction that can be parallelized ^lrZqNgLj

1-P is the fraction of the program that is serial ^mT3Rv9Lv

P is the fraction that can be parallelized ^wjmQA6FJ

N is the number of Processors ^jFubQD0K

1) Shared Memory:  Several cpus that have several disks, work on the same memory over a common bus ^6U1J33kw

2) Shared disk: Several cpus each with their own memory share the same disks and datasource. ^sYBUaaQI

3) Shared nothing: nodes have their own disk, memory, communication is direct and data is partitioned. ^joAo9bk5

1) Pipeline Parallelism: Inter-Operator Parallelism Executes multiple pipelines simultaneously, only if the pipelines are not
  dependent on each other ^1BC6575B

2) Data Parallelism: Some operations dont need to see the entire table, thus we can divide the data into subparts each of
   which can be processed independently, Degree of Parallelism as high as the number of possible subsets depending on operator ^NccOvTnV

Needs high sync overhead, lower degree of parallelism (not too many pipelines per query), pipelines can be imbalanced ^XF2ibo3N

1) Replication: multiple copies of data, stored in different sites, faster retrieval and fault tolerance.
  advantages: 1) Availability: if one node doesnt have R, does not mean other nodes do not!
               2) Parallelism: queries on same relation can be processed in several nodes
               3) Reduced data transfer: because everything is available on all nodes
  disadvantages: 1) Increased cost of updates: each updated R needs to be updated for every node
                 2) requires a lot of concurrency control in order to ensure that 2 replicas of the 
                    same data dont have inconsistencies. (Pick one as Primary and apply CC) ^D6PCnrgg

2) Fragmentation: partitioned into several fragments stored in distinct sites
   special case advantages: 1) Partitions can be dropped out if theyre no longer necessary
                             2) Some queries can be limited to operate on certain sets only ^71vkaZHV

3) Replication & Fragmentation: we fragment our relation and store multiple copies of each fragment ^OtDbJXa9


# Embedded files
b2af7350275e9e863a564247117a4423ca06f7f1: $$SpeedUp = \frac{1}{1 - P + \frac{P}{N}}$$
765ed0699bf0cb07fd4eb5a8ac784bf734043a0a: $$SpeedUp_{Weak} = (1-P) + N \cdot P$$

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
			"version": 187,
			"versionNonce": 1710205184,
			"isDeleted": false,
			"id": "dWmjNYeP",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -121.69463303078908,
			"y": -483.3325516501797,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 194.9597625732422,
			"height": 25,
			"seed": 1111181056,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Parallel Databases",
			"rawText": "Parallel Databases",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Parallel Databases",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 4113,
			"versionNonce": 902954698,
			"isDeleted": false,
			"id": "uaETZVbv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -535.9213142582548,
			"y": -455.1322257483251,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1046.458984375,
			"height": 2000,
			"seed": 495151360,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1708272098566,
			"link": "[[Computations]]",
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* So far we have only considered single-Threaded/Serial System that manages all the data, now we \n  are upgrading our ideas to extend beyond that into parallel databases.\n*                    : the machines are homogeneous and tightly coupled, clusters with direct network\n  connection, multi-processor system, everything works together. (Optimized for performance)\n*                        : machines can be hetrogeneous and are loosely coupled, long distance network\n  connections, can act independently. (Optimized for reliability).\n* Speedup is the runtime of a sequential program and the run of a parallel program over p nodes\n\n* Amdahl's Law : Theoretical maximal speedup is determined by by the sequential part of the program\n\n* Gustafon's Law More processors are usually added to solve a larger problem in the same time\n\n* Homogeneous distributed database: machines are aware of each other, have the same software and\n  work together in order to process user requests, appears as a single system\n\n\n\n\n* Instruction Parallelism: Single instructions are automatically processed in parallel by the hardware\n* Data parallelism: Each processing unit executes the same operations on its share of the input data\n  Independently \n* Task parallelism: Tasks (work/data) are distributed among the processors/nodes each processor\n  executes a different thread/process\n\n* Inter-Query parallelism (efficient resource utilization): While one query waits for I/O, another executes\n  Requires concurrency control, important for highly transactional data\n\n* Intra-Query Parallelism: Parallel processing of a single query, whether its concurrent I/O from multiple\n  disk, Data Parallelism where multiple threads work on the same operator, or pipeline parallelism where\n  multiple pipelines work on different pipelines of the plan in parallel. Important for Analytical Data\n\n\n\n\n\n* Distribution: Deciding what data goes where\n\n\n\n\n\n\n\n\n\n\n\n* Types of partitioning:\n* Horizontal Partitioning: split table into slices of records with the same schema, each record only\n  occurs once per slice and slice is placed where it is most often read, This can be done through\n  round robin which guarantees equal size but no relation between tuples, Hash Partitioned over a \n  column value which guarantees tuples with similar column values are together, range partition where\n  define a specific range over certain columns and slice the records such that theyre in the same range\n* Vertical Partitioning: Partition table in multiple vertical slices, each of which requires a key, useful\n  if the the entire table is frequently used but over different values, allows us to process only \n  required attributes and place them where theyre frequently used.\n\n* Distributed transactions: Each site has a local transaction manager responsible for manaing the logs\n  for recovery purposes and coordinating the concurrent execution of the transactions at that site.\n  Each site also has a transaction coordinator which is responsible for Starting the execution of\n  transactions that originate at the site and redirecting the sub-transactions that need to be at\n  other sites. This responsibility also includes the termination of transactions that originate at that\n  site.\n\n* Failures related to distributed systems: 1) Failure of one site   2) Message loss   3) Failure of \n      communication link\n  4) Network partitioning failure (missing connection between two subsystems after partitioning)\n\n* Committing across different sites adds a lot more consistency complexity and global coordination\n* Two-Phase Commit: \n1) Phase 1: Vote collection phase : Coordinator contacts everyone to make a decision, waits for response\n2) Phase 2: Vote Collection Phase: if all agree, the decision is to commit, otherwise abort\n3) Phase 3: Decision Phase: Coordinator contacts all with the final decision\n\n* Distributed Query Processing: This is just an extension of centralized query processing except we \n  can exploit replication and fragmentation, harder to estimate cost due to network inconsistencies.\n  Dont forget to include send and receive operators in algebra.\n\n* High locality = Nodes own partitions exclusively\n* Low locality = All nodes own equal portions of each partition",
			"rawText": "* So far we have only considered single-Threaded/Serial System that manages all the data, now we \n  are upgrading our ideas to extend beyond that into parallel databases.\n*                    : the machines are homogeneous and tightly coupled, clusters with direct network\n  connection, multi-processor system, everything works together. (Optimized for performance)\n*                        : machines can be hetrogeneous and are loosely coupled, long distance network\n  connections, can act independently. (Optimized for reliability).\n* Speedup is the runtime of a sequential program and the run of a parallel program over p nodes\n\n* Amdahl's Law : Theoretical maximal speedup is determined by by the sequential part of the program\n\n* Gustafon's Law More processors are usually added to solve a larger problem in the same time\n\n* Homogeneous distributed database: machines are aware of each other, have the same software and\n  work together in order to process user requests, appears as a single system\n\n\n\n\n* Instruction Parallelism: Single instructions are automatically processed in parallel by the hardware\n* Data parallelism: Each processing unit executes the same operations on its share of the input data\n  Independently \n* Task parallelism: Tasks (work/data) are distributed among the processors/nodes each processor\n  executes a different thread/process\n\n* Inter-Query parallelism (efficient resource utilization): While one query waits for I/O, another executes\n  Requires concurrency control, important for highly transactional data\n\n* Intra-Query Parallelism: Parallel processing of a single query, whether its concurrent I/O from multiple\n  disk, Data Parallelism where multiple threads work on the same operator, or pipeline parallelism where\n  multiple pipelines work on different pipelines of the plan in parallel. Important for Analytical Data\n\n\n\n\n\n* Distribution: Deciding what data goes where\n\n\n\n\n\n\n\n\n\n\n\n* Types of partitioning:\n* Horizontal Partitioning: split table into slices of records with the same schema, each record only\n  occurs once per slice and slice is placed where it is most often read, This can be done through\n  round robin which guarantees equal size but no relation between tuples, Hash Partitioned over a \n  column value which guarantees tuples with similar column values are together, range partition where\n  define a specific range over certain columns and slice the records such that theyre in the same range\n* Vertical Partitioning: Partition table in multiple vertical slices, each of which requires a key, useful\n  if the the entire table is frequently used but over different values, allows us to process only \n  required attributes and place them where theyre frequently used.\n\n* Distributed transactions: Each site has a local transaction manager responsible for manaing the logs\n  for recovery purposes and coordinating the concurrent execution of the transactions at that site.\n  Each site also has a transaction coordinator which is responsible for Starting the execution of\n  transactions that originate at the site and redirecting the sub-transactions that need to be at\n  other sites. This responsibility also includes the termination of transactions that originate at that\n  site.\n\n* Failures related to distributed systems: 1) Failure of one site   2) Message loss   3) Failure of \n      communication link\n  4) Network partitioning failure (missing connection between two subsystems after partitioning)\n\n* Committing across different sites adds a lot more consistency complexity and global coordination\n* Two-Phase Commit: \n1) Phase 1: Vote collection phase : Coordinator contacts everyone to make a decision, waits for response\n2) Phase 2: Vote Collection Phase: if all agree, the decision is to commit, otherwise abort\n3) Phase 3: Decision Phase: Coordinator contacts all with the final decision\n\n* Distributed Query Processing: This is just an extension of centralized query processing except we \n  can exploit replication and fragmentation, harder to estimate cost due to network inconsistencies.\n  Dont forget to include send and receive operators in algebra.\n\n* High locality = Nodes own partitions exclusively\n* Low locality = All nodes own equal portions of each partition",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* So far we have only considered single-Threaded/Serial System that manages all the data, now we \n  are upgrading our ideas to extend beyond that into parallel databases.\n*                    : the machines are homogeneous and tightly coupled, clusters with direct network\n  connection, multi-processor system, everything works together. (Optimized for performance)\n*                        : machines can be hetrogeneous and are loosely coupled, long distance network\n  connections, can act independently. (Optimized for reliability).\n* Speedup is the runtime of a sequential program and the run of a parallel program over p nodes\n\n* Amdahl's Law : Theoretical maximal speedup is determined by by the sequential part of the program\n\n* Gustafon's Law More processors are usually added to solve a larger problem in the same time\n\n* Homogeneous distributed database: machines are aware of each other, have the same software and\n  work together in order to process user requests, appears as a single system\n\n\n\n\n* Instruction Parallelism: Single instructions are automatically processed in parallel by the hardware\n* Data parallelism: Each processing unit executes the same operations on its share of the input data\n  Independently \n* Task parallelism: Tasks (work/data) are distributed among the processors/nodes each processor\n  executes a different thread/process\n\n* Inter-Query parallelism (efficient resource utilization): While one query waits for I/O, another executes\n  Requires concurrency control, important for highly transactional data\n\n* Intra-Query Parallelism: Parallel processing of a single query, whether its concurrent I/O from multiple\n  disk, Data Parallelism where multiple threads work on the same operator, or pipeline parallelism where\n  multiple pipelines work on different pipelines of the plan in parallel. Important for Analytical Data\n\n\n\n\n\n* Distribution: Deciding what data goes where\n\n\n\n\n\n\n\n\n\n\n\n* Types of partitioning:\n* Horizontal Partitioning: split table into slices of records with the same schema, each record only\n  occurs once per slice and slice is placed where it is most often read, This can be done through\n  round robin which guarantees equal size but no relation between tuples, Hash Partitioned over a \n  column value which guarantees tuples with similar column values are together, range partition where\n  define a specific range over certain columns and slice the records such that theyre in the same range\n* Vertical Partitioning: Partition table in multiple vertical slices, each of which requires a key, useful\n  if the the entire table is frequently used but over different values, allows us to process only \n  required attributes and place them where theyre frequently used.\n\n* Distributed transactions: Each site has a local transaction manager responsible for manaing the logs\n  for recovery purposes and coordinating the concurrent execution of the transactions at that site.\n  Each site also has a transaction coordinator which is responsible for Starting the execution of\n  transactions that originate at the site and redirecting the sub-transactions that need to be at\n  other sites. This responsibility also includes the termination of transactions that originate at that\n  site.\n\n* Failures related to distributed systems: 1) Failure of one site   2) Message loss   3) Failure of \n      communication link\n  4) Network partitioning failure (missing connection between two subsystems after partitioning)\n\n* Committing across different sites adds a lot more consistency complexity and global coordination\n* Two-Phase Commit: \n1) Phase 1: Vote collection phase : Coordinator contacts everyone to make a decision, waits for response\n2) Phase 2: Vote Collection Phase: if all agree, the decision is to commit, otherwise abort\n3) Phase 3: Decision Phase: Coordinator contacts all with the final decision\n\n* Distributed Query Processing: This is just an extension of centralized query processing except we \n  can exploit replication and fragmentation, harder to estimate cost due to network inconsistencies.\n  Dont forget to include send and receive operators in algebra.\n\n* High locality = Nodes own partitions exclusively\n* Low locality = All nodes own equal portions of each partition",
			"lineHeight": 1.25,
			"baseline": 1993
		},
		{
			"type": "text",
			"version": 113,
			"versionNonce": 1007847680,
			"isDeleted": false,
			"id": "KCpvYTgE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -515.6424321287263,
			"y": -408.0751754332309,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 190.73976135253906,
			"height": 25,
			"seed": 983516928,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Parallel databases",
			"rawText": "Parallel databases",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Parallel databases",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 93,
			"versionNonce": 720799488,
			"isDeleted": false,
			"id": "AUaMEOvL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -519.6655798336315,
			"y": -358.1881438924092,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 225.77972412109375,
			"height": 25,
			"seed": 1198180096,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Distributed databases",
			"rawText": "Distributed databases",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Distributed databases",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 136,
			"versionNonce": 182020352,
			"isDeleted": false,
			"id": "Hgd9k7W9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -516.3247935327271,
			"y": -281.64855199914166,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 867.025634765625,
			"height": 20,
			"seed": 1313491200,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Describes how much faster we get by running the parallel algorithm on p nodes, the fastest speedup is linear",
			"rawText": "Describes how much faster we get by running the parallel algorithm on p nodes, the fastest speedup is linear",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Describes how much faster we get by running the parallel algorithm on p nodes, the fastest speedup is linear",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 171,
			"versionNonce": 948807424,
			"isDeleted": false,
			"id": "lrZqNgLj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 63.907099135638674,
			"y": -231.588565041907,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 334.416748046875,
			"height": 20,
			"seed": 1677805824,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "P is the fraction that can be parallelized",
			"rawText": "P is the fraction that can be parallelized",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "P is the fraction that can be parallelized",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 219,
			"versionNonce": 499403008,
			"isDeleted": false,
			"id": "mT3Rv9Lv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -505.56568632153324,
			"y": -230.74763908556668,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 386.8328857421875,
			"height": 20,
			"seed": 1866376960,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1-P is the fraction of the program that is serial",
			"rawText": "1-P is the fraction of the program that is serial",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1-P is the fraction of the program that is serial",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 224,
			"versionNonce": 1178650368,
			"isDeleted": false,
			"id": "6U1J33kw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -528.2706742321283,
			"y": -106.26789188186865,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1019.2388916015625,
			"height": 25,
			"seed": 887858944,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Shared Memory:  Several cpus that have several disks, work on the same memory over a common bus",
			"rawText": "1) Shared Memory:  Several cpus that have several disks, work on the same memory over a common bus",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Shared Memory:  Several cpus that have several disks, work on the same memory over a common bus",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 257,
			"versionNonce": 1347627264,
			"isDeleted": false,
			"id": "1BC6575B",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -524.2207781444752,
			"y": 297.8965358476964,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 944.2738647460938,
			"height": 40,
			"seed": 23963392,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1) Pipeline Parallelism: Inter-Operator Parallelism Executes multiple pipelines simultaneously, only if the pipelines are not\n  dependent on each other",
			"rawText": "1) Pipeline Parallelism: Inter-Operator Parallelism Executes multiple pipelines simultaneously, only if the pipelines are not\n  dependent on each other",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Pipeline Parallelism: Inter-Operator Parallelism Executes multiple pipelines simultaneously, only if the pipelines are not\n  dependent on each other",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 288,
			"versionNonce": 1888478976,
			"isDeleted": false,
			"id": "NccOvTnV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -524.220778261146,
			"y": 361.9866078650343,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1012.5619506835938,
			"height": 40,
			"seed": 901253376,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "2) Data Parallelism: Some operations dont need to see the entire table, thus we can divide the data into subparts each of\n   which can be processed independently, Degree of Parallelism as high as the number of possible subsets depending on operator",
			"rawText": "2) Data Parallelism: Some operations dont need to see the entire table, thus we can divide the data into subparts each of\n   which can be processed independently, Degree of Parallelism as high as the number of possible subsets depending on operator",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2) Data Parallelism: Some operations dont need to see the entire table, thus we can divide the data into subparts each of\n   which can be processed independently, Degree of Parallelism as high as the number of possible subsets depending on operator",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 186,
			"versionNonce": 235276544,
			"isDeleted": false,
			"id": "XF2ibo3N",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -515.0025139146027,
			"y": 339.9415722261487,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 912.7855834960938,
			"height": 20,
			"seed": 260835584,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Needs high sync overhead, lower degree of parallelism (not too many pipelines per query), pipelines can be imbalanced",
			"rawText": "Needs high sync overhead, lower degree of parallelism (not too many pipelines per query), pipelines can be imbalanced",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Needs high sync overhead, lower degree of parallelism (not too many pipelines per query), pipelines can be imbalanced",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 741,
			"versionNonce": 1140524800,
			"isDeleted": false,
			"id": "D6PCnrgg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -531.7803658055076,
			"y": 446.5664148821967,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 1011.598876953125,
			"height": 175,
			"seed": 1540605696,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Replication: multiple copies of data, stored in different sites, faster retrieval and fault tolerance.\n  advantages: 1) Availability: if one node doesnt have R, does not mean other nodes do not!\n               2) Parallelism: queries on same relation can be processed in several nodes\n               3) Reduced data transfer: because everything is available on all nodes\n  disadvantages: 1) Increased cost of updates: each updated R needs to be updated for every node\n                 2) requires a lot of concurrency control in order to ensure that 2 replicas of the \n                    same data dont have inconsistencies. (Pick one as Primary and apply CC)",
			"rawText": "1) Replication: multiple copies of data, stored in different sites, faster retrieval and fault tolerance.\n  advantages: 1) Availability: if one node doesnt have R, does not mean other nodes do not!\n               2) Parallelism: queries on same relation can be processed in several nodes\n               3) Reduced data transfer: because everything is available on all nodes\n  disadvantages: 1) Increased cost of updates: each updated R needs to be updated for every node\n                 2) requires a lot of concurrency control in order to ensure that 2 replicas of the \n                    same data dont have inconsistencies. (Pick one as Primary and apply CC)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Replication: multiple copies of data, stored in different sites, faster retrieval and fault tolerance.\n  advantages: 1) Availability: if one node doesnt have R, does not mean other nodes do not!\n               2) Parallelism: queries on same relation can be processed in several nodes\n               3) Reduced data transfer: because everything is available on all nodes\n  disadvantages: 1) Increased cost of updates: each updated R needs to be updated for every node\n                 2) requires a lot of concurrency control in order to ensure that 2 replicas of the \n                    same data dont have inconsistencies. (Pick one as Primary and apply CC)",
			"lineHeight": 1.25,
			"baseline": 168
		},
		{
			"type": "text",
			"version": 435,
			"versionNonce": 1381820672,
			"isDeleted": false,
			"id": "71vkaZHV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -524.220777588785,
			"y": 622.4985180184763,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 915.779052734375,
			"height": 75,
			"seed": 1143269120,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2) Fragmentation: partitioned into several fragments stored in distinct sites\n   special case advantages: 1) Partitions can be dropped out if theyre no longer necessary\n                             2) Some queries can be limited to operate on certain sets only",
			"rawText": "2) Fragmentation: partitioned into several fragments stored in distinct sites\n   special case advantages: 1) Partitions can be dropped out if theyre no longer necessary\n                             2) Some queries can be limited to operate on certain sets only",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2) Fragmentation: partitioned into several fragments stored in distinct sites\n   special case advantages: 1) Partitions can be dropped out if theyre no longer necessary\n                             2) Some queries can be limited to operate on certain sets only",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 365,
			"versionNonce": 1023551232,
			"isDeleted": false,
			"id": "OtDbJXa9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -524.4442747977712,
			"y": 697.4985180325516,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 1000.4590454101562,
			"height": 25,
			"seed": 1601865984,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3) Replication & Fragmentation: we fragment our relation and store multiple copies of each fragment",
			"rawText": "3) Replication & Fragmentation: we fragment our relation and store multiple copies of each fragment",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3) Replication & Fragmentation: we fragment our relation and store multiple copies of each fragment",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "frame",
			"version": 385,
			"versionNonce": 1104151551,
			"isDeleted": false,
			"id": "7UzCFPUWxGl_zXCVxUreN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -542.7041733874028,
			"y": -483.3325518716272,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 1036.9788418581356,
			"height": 2125.979252591028,
			"seed": 1565018368,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708099386588,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#7A7A7A"
				}
			},
			"name": "Parallel"
		},
		{
			"type": "image",
			"version": 228,
			"versionNonce": 685230336,
			"isDeleted": false,
			"id": "4g2Th96E",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -93.50971068825046,
			"y": -234.87841590470822,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 137.2392728848481,
			"height": 33.318204977824394,
			"seed": 74589,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "b2af7350275e9e863a564247117a4423ca06f7f1",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 97,
			"versionNonce": 1210402560,
			"isDeleted": false,
			"id": "dWrvrLLt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -141.09041606195404,
			"y": -174.8977554789136,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 225.92033994308701,
			"height": 16.554507668243446,
			"seed": 47748,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "765ed0699bf0cb07fd4eb5a8ac784bf734043a0a",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 253,
			"versionNonce": 754362624,
			"isDeleted": false,
			"id": "wjmQA6FJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 99.6565965715997,
			"y": -175.7795757009729,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 334.416748046875,
			"height": 20,
			"seed": 680798464,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "P is the fraction that can be parallelized",
			"rawText": "P is the fraction that can be parallelized",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "P is the fraction that can be parallelized",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 333,
			"versionNonce": 1105487616,
			"isDeleted": false,
			"id": "jFubQD0K",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -396.10957836582816,
			"y": -175.77957578829225,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 240.19248962402344,
			"height": 20,
			"seed": 1888872704,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "N is the number of Processors",
			"rawText": "N is the number of Processors",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "N is the number of Processors",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 385,
			"versionNonce": 171542784,
			"isDeleted": false,
			"id": "sYBUaaQI",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -528.270674305437,
			"y": -81.26789223323155,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 949.8189697265625,
			"height": 25,
			"seed": 428017408,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2) Shared disk: Several cpus each with their own memory share the same disks and datasource.",
			"rawText": "2) Shared disk: Several cpus each with their own memory share the same disks and datasource.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2) Shared disk: Several cpus each with their own memory share the same disks and datasource.",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 604,
			"versionNonce": 1992263424,
			"isDeleted": false,
			"id": "joAo9bk5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -530.793450885595,
			"y": -55.42696697544518,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 1007.6589965820312,
			"height": 25,
			"seed": 552019712,
			"groupIds": [],
			"frameId": "7UzCFPUWxGl_zXCVxUreN",
			"roundness": null,
			"boundElements": [],
			"updated": 1707833795142,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3) Shared nothing: nodes have their own disk, memory, communication is direct and data is partitioned.",
			"rawText": "3) Shared nothing: nodes have their own disk, memory, communication is direct and data is partitioned.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3) Shared nothing: nodes have their own disk, memory, communication is direct and data is partitioned.",
			"lineHeight": 1.25,
			"baseline": 18
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#f08c00",
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
		"scrollX": 1986.089752458335,
		"scrollY": 632.1983943261132,
		"zoom": {
			"value": 0.4
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