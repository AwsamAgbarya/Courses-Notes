---
tags:
  - DIA
---
What is a data warehouse? and what are its main attributes?
?
A **data warehouse** is a _subject-oriented_, _integrated,_ _time-varying_, _non-volatile_ collection of data in support of the management's **decision-making process**.

1. _Subject oriented_: focused and centered around analytical purposes
2. _Integrated_: Consistent data from different sources
3. _Time varying_: Consists of temporal data
4. _Non-volatile_: Read-only access, and the data is loaded in by admins periodically.

What is the goal of data-warehousing?
?
The goal of data warehousing is to have a consistent and homogeneous representation of data coming from many different heterogeneous sources to perform analytical queries on them.

Describe datacubes (Include in your description a definition, alongside a detailed explanation of what dimensions are)
?
Metaphorical Multi-dimensional Cubes of data such that each dimension represents the spectrum of a specific qualifying or quantifying attribute .  
Each Attribute has hierarchical Granularities (as a set of categorical attributes/Measures) alongside a minimum and maximum element.  
There are no dependencies between two different orthogonal dimensions.

Which of the following diagrams are valid attribute hierarchies?
![[Pasted image 20250127181740.png]]
?
![[Pasted image 20250127181751.png]]

Describe 5 different cube operations.
?
1. **Slicing :** Select a slice of the cube by filtering one dimensional to a particular value
2. **Dicing :** Select a sub cube by filtering over multiple dimensions of the cube.
3. **Roll Up:** Merging a certain dimensions datapoints such that the granularity is coarser.
4. **Drill Down :** Disaggregation of measures into finer-grained measures.
5. **Drill Across :** Navigate to neighboring cells at same granularity
6. **Drill Through :** Go to an individual data point in the cube and extract individual tuples from it.
7. **Pivot :** Transposing the dimensions such that you view it from a different direction.
<!--SR:!2025-03-28,3,250-->

What are facts? and what are Measures?
?
- Facts are base tuples at the finest granularity that contain one or multiple measures.
- Measures contain the actual measurements or Computation function

Describe the different ROLAP Schemas.
?
1. **Star Schema:** consists of one central Fact table that contains many categorical attributes and the main measurements, and branching from it using the foreign keys of the categorical attributes, a bunch of tables describing details of the category per fact. Creating a single source of truth is often called denormalization of a table.  Many Star Schemas combined can also be called a galaxy schema.
2. **SnowFlake Schema:** Unlike the star schema, the tables are denormalized and broken down into several tables to remove redundancies and increase specialization. Several snowflake schemas are called a snow storm.

What is ETL and what is ELT?
?
**Extract Transform Load (ETL):** Describes the act of loading data into the warehouse given multiple data sources. This process only loads the transformed and cleaned data from the extracted data sources. As opposed to **Extract load transform (ELT)** which loads uncleaned data in the system and performs data transformations via SQL inside the warehouse for a more optimized plan.

Name 3 types of semantic and 3 types of structural Heterogeneity.
?
**Semantic:**
	1. Synonyms and homonyms
	2. Mathematical mappings
	3. data types
	4. complex mappings
	5. language expressions
	6. Missing values
	7. virtual columns
	8. semantic incompatibility
- **Structural:**
	1. Same attribute but different structure.
	2. Handling sets.
	3. Attribute name w/o semantics
	4. attribute composition

Name 3 causes for corrupted data.
?
- Heterogeneity of different systems can cause inconsistencies and incompatibilities.
- Human errors will always occur in manually inputted fields, including biases and laziness.
- Environment and hardware errors occur in harsh environments that lead to measurement errors.

What is the difference between Sync and Async messages?
?
 - **Synchronus Messages:**  sent messages have strict requirements that block both users into a stream mode where one is sending and the other is recieving, this introduces some overhead and both ends have to connect and be available at the time, this creates low local autonomy.
- **Async Messages:** Unlike Sync messages, the ends have Loose coupling and the message will eventually arrive through a FIFO or priority queue..

What are the three types of guarantees in Async messages?
?
- **At Most once:**  Send and forget, ensure data is never counted twice but this might cause data loss on failure
- **At Least once:**  Store and forward or acknowledgements from receiver, replay stream from a checkpoint on failures, this might lead to a TX being processed multiple times.
- **Exactly once:**  Store and forward w/ guarantees regarding state updates and sent msgs.

For each statement here, mark whether it applies to "At most once", "At least Once", "Exactly once" guarantees:
- Requires Message presistence.
- Requires Delivery transaction emchanism
- prevents Message outrun
- Prevents Message Loss
- Prevents Message double delivery
?
![[Pasted image 20250205232009.png]]
<!--SR:!2025-03-28,3,250-->

Describe 2PC.
?
*Two Phase Commit (2PC)*:
- We want to keep the consistency of a database with concurrent transactions.
- Problems occur during distributed systems such as node and communication failures that might introduce inconsistencies.
- Two phase commit is split into two phases, the *PREPARE* phase and the *COMMIT* phase, such that for the first part the global coordinator checks whether all nodes are available to interact with, and the second phase actually executes that interaction.
<!--SR:!2025-03-26,1,227-->

How can we improve 2PC or replace it?
?
The following Improvements can be done to 2PC:
1. Assume that the transaction is aborted if there are no commit log entires.
2. establish a hierarchy message tree from coordinator to local nodes which allows for parallelization of message handling
*One Phase Commit (1PC):*
- Combine TX operations w/ PREPARE to reduce 2(n-1) messages, such that the nodes wait into the blocked waiting state earlier
*Three Phase Commit (3PC):*
- Add an additional non-restricting phase at the start that checkes whether all nodes are available and cant commit before blocking them in prepare.

What is Publish-Subscribe messaging process?
?
- Usually few Publishers and Many subscribers, the action is triggered by the publisher and passed onto appropriate subscribers.
- Requires at least once guarantees.
- Often subscriber filtering is done through Complex predicates of range filters, equi-predicates, and negation to avoid naive scans.
- Matching Algorithm using Trees matches an event against a set of subscriptions and searches the tree for leaves that satisfy the requirements.

What is replication? and what are some replication techniques?
?
##### Replication:
- Replication is the redundancy of stored fragments.
- Its a tradeoff between availability and reading speed for many users, with the trade off of updating and keeping everything consistent and extra storage.
###### Replication Techniques:
- **ROWA Read one Write All:** It offers good performance and availability but high writing overhead and one can update of all nodes are available.
- **ROWAA Read one Write All Available:** Relaxed availability requirement for write operations.
- **Primary Copy:** Updates single primary copy synchronously following up by asynchronous propagation of updates for secondary copies, you are allowed to read from any node, however this may introduce stale reading.
- **Consensus:** Introduces slotting for whether reading or writing is permissible, such that if the capacity is full or doesnt fit your replicate's quorum, you will have no access, this introduced by defining the read and write quorum by more than half of the total capacity.


Describe detections that would be used during schema detection.
?
- Detection of data types is usually done by sampling data from the column and inferring the data type with the least parsing errors with Basic extraction rules, regular expressions.
- Structure extraction of data involves scanning the  data, building maximum tree w/ attached meta data.
- Inclusion dependencies requires detecting the encompassment of all values from one attribute to another in order to establish primary key foreign key relations.
- Functional dependencies Discover minimal, non-trivial dependencies such that unique values of A result in unique values of B etc...
- Semantic Type detections are detections of the semantics of a column given all its values using Deep neural networks.

What is Schema matching? and what is Schema mapping?
?
Schema Matching
Given two or more relational schemas, find mappings in terms of logical attribute correspondences, i.e which attributes from schema A correspond and correlate to attributes in schema B
Schema Mapping
Given logical attribute correspondences between schemas Compile physical schema mapping programs, i.e Given the relations between attributes of schema A and schema B, execute a query that uses that relation to translate the data from one end to another

Describe three types of schema matchers.
?
1. **Linguistic matcher:** matching attributes according to some linguistic contraint, whether it is semantic or syntactic (For example, N-grams and Edit distance or Synonyms and Hierarchies)
2. **Constraint matchers:** Match the attributes according to some structural constrains (for example, data types, domains, relationship with other elements, neighbourhood, composition and specialization)
3. **Instance based matchers:** Matchrs that perform like the previously mentioned however not on the attribute names but on the attribute data itself, like word and value frequencies, keywords and abbreviations, bigrams, data length , patterns.
4. **Reuse matchers:** is a sort of combining matcher that exploits the  transitive similarity.
5. **Refinement matchers:** Uses a pipeline or a chain of multiple matchers that are important at different levels
6. **Composite matchers:** Select combination of complementary matchers in form of ensemble and aggregate their similarity

Describe or define middleware.
?
Message are pieces of information formulated in a certain structure using different syntax (format), encompassing different semantic (domain) from a transmitter to a reciever.

Define Schema mapping and schema integration.
?
Schema mapping: Given logical attribute correspondences between schemas Compile physical schema mapping programs, i.e Given the relations between attributes of schema A and schema B, execute a query that uses that relation to translate the data from one end to another
Schema integration: Given Multiple Schemas and their attributes logical correspondence, map them into a consolidated schema.

What is entity linking?
?
Entity linking is the problem of creating links among records representing real-world entities that are related in certain ways.  
Entity resolution is the problem of identifying or linking duplicate entities.  
The pipeline of the entire process includes Preparing the data, Blocking the data, Matching the data, Clustering the data.

How do you prepare the heterogeneous data for comparsions?
?
- Involves Schema matching and mapping wherever possible if we are merging multiple datasets.
- Normalization of the fields by removing all special characters and stemming words to their roots, resolve abbreviations and remove capitalization.
- Data cleaning which involves correcting data corruption and inconsistencies.

Describe the process of data blocking in details.
?
Data blocking is technique mainly done in order to avoid unnecessary computations, instead of comparing every 2 pairs even irrelevant ones, we block them into blocks that are most likely to have some duplicates between them.

List and describe three techniques of data blocking.
?
- **Partitionings:**
	- Efficiently create small blocks of similar records for pair-wise matching to avoid massive amount of unnecessary computations, obviously the latter is more accurate but it involves computing every interaction which can be unnecessary and sometimes infeasible.
	- Partitioning can be done by many techniques, often opting for a way of representing a space of similar pairs in a fast and unique way such as token fields and ngrams. This can also be done through blocking keys extraction.
- **Sorted Neighbourhood:**
	- Define special keys that can be sorted meaningfully and sort the values according to the keys. Afterwards introduce a Jumping window such that you can process each neighbourhood on its own.
- **Word Embeddings:**
	- Compute word embeddings for your tuples and perform a locality sensitive hashing function on them.
	- Locality sensitive Hashing involves the idea of creating K hash functions that are formed as a matrix and then multipled by the word embeddings, afterwards the result of the embedding is analyzed element by element sign-wise which results in the production of a binary number (1 represents positive elm, 0 represents negative elm). This number is now you bucket index.

Describe the process of data matching in detail.
?
The process of matching is the main component of entity resolution which is computing the similarity between different components in each block, this similarity then helps us decide which are duplicates and which are not.
- Basic similarity measures depends on your needs and resources, Jaccard, Levenshtein and Ngrams are viable options for such things.
- Learned matchers also introduce a higher capacity for accuracy, by building a dataset of similarities and their scores, one could teach a model how to expand upon that knowledge and let it compute the similarity once its trained. (Leveraging Representation learning, word embeddings, SVMs etc...)

Describe the process of data clustering in details.
?
The process of clustering is the final step, and it is to identify groups of similar pairs though our previous computation and cluster them accordingly around their appropriate neighbourhood.
- One obvious way of doing this is computing the connected components graph that will display all groups that have intersections between them. Two obvious issues arise from such methods is that you might end up with very large groups and dissimilar pairs from distant edges of the graph.
- To resolve these issues there are techniques that perform correlation clustering and iteratively compute the optimal cuts between large graphs in order to maximize similarities between the pairs contained in each component.
- Other methods involves Random Markov walks on the graphs to produce a fixed sized subgraphs, the edges will be weighed according to how similar they are (Transition probability  = similarity of edge/ sum of all similarities for all edges)
- If the goal is to perform Incremental deduplication, these graphs must be kept in order to not redo the same computations with every update, a new link can easily be then appended to the graph.

What is the entity resolution pipeline? name all stages and briefly explain them.
?
Data preparation: Preparing the data to a subset of clean data that we need to do comparison on
Data blocking: to avoid unnecessary computations, instead of comparing every 2 pairs even irrelevant ones, we block them into blocks that are most likely to have some duplicates between them.
Data matching: computing the similarity between different components in each block, this similarity then helps us decide which are duplicates and which are not.
Data clustering:  identify groups of similar pairs though our previous computation and cluster them accordingly around their appropriate neighbourhood.

What is data validation?
?
Checking the validity of the data is the first step in detecting invalid values that need to be cleaned and imputated. Data validation can involve very simple heuristics and rules set by experts such as value ranges, whether certain features are apparent in the majority of entries given, Whether features exist in the correct cardinality of their values and whether they match logical dependencies and restrictions.

How do you detect outliers in your data?
?
- Outliers can be of many forms, they can be singular point outliers or systematic noises and failures or a value not fitting to the period shape of a sequence of values, for such cases we have several detection methods:
	- Winsorizing and Trimming is the process dedicated for outlier elimination, as they compute the precentiles of the data that would otherwise be the logical boundary for values and remove/cap everything beyond it, or replace them by default mean/mode values.
	- Train a classifier to label data with Outlier and Inlier if a lot of data is provided, such methods can involve classical machine learning algorithms like SVMs or neural networks and autoencoders.
	- Use KNNs to find the largest spatial distance of a singular point from its neighbours.
	- Cluster the data and find isolated components outside the clusters.

What do you replace outliers with?
?
-  After detection of outliers or rule breaks, we want to replace those values in a meaningful way there are also several ways of doing this:
	- The general principle of repair asks for the principal of minimality and the choice of repair should be one such that it has minimal change and steps.
	- Sometimes it is much easier for us to relax some constraints and assumptions to achieve such minimality without altering the data.
	- Some iterative machine learning algorithms try to learn the appropriate way of computing the predicted results for those values, one such method uses SVMs and trains on only the dirty data, then takes a sample of the clean data and starts updating the model accordingly, this final model will be representing what the dirty data shape should be, if it were to belong to the clean data.
<!--SR:!2025-03-28,3,250-->

Name three types of missing values.
?
1. Missing Completely at random: values that are missing for absolute no reason or correlation to the actual values.
2. Missing at random: missing values are random but specific to a category or subgroup of tuples.
3. Not missing at random: Missing values are only missing because of the value they belong to.

How do you impute missing values?
?
1. replace by user-specified constant, mean, median, functional dependencies or most frequent values. This does not work for Not missing at random as the value is specifically not the mean.
2. Use an iterative algorithm such as mice that separates the data into training data full of all the valid entries, and test data full of missing values, the model is then to be trained to predict the test data. This works very well at missing at random.
3. Time series data imputation can be done through many different interpolatio and exterpolation techniques.

What is data provenance, what does it contain and what are its types?
?
Data provenance is the track record of the origins and transformations that occurred on the data throughout its life time.
Which contains meta data, schema, data granuality, transformations, context and environment context.
**Why-Provenance:**
Which input tuples contributed to an output tuple t in query Q
**Why-not-Provenance:**
Why are items not in the results
**How-Provenance:**
Model how tuples where combined in the computation.
<!--SR:!2025-03-28,3,250-->

What is the benefit and goal of data provenance?
?
1. Versioning and reproducability
2. Explainability and verification.
3. Reuse of intermediates.
4. Incremental maintenance of models.
5. Log of executed operations for auto differentiation.
6. Recomputation of parts for fault tolerance and caching.
7. Debugging via Lineage Query Processing



Name two lineage query evaluation techniques.
?
###### Lazy lineage query evaluation:
- On demand lineage evaluation done by inverted the original query in order to understand its relation origins.
- no overhead, but quite slow in computation as it does not store any information, instead rewriting the query and executing it.
###### Eager Lineage Query Evaluation:
- Create annotations along the way of executing queries to keep track of the lineage.
- adds overhead to executing queries but does not need to do extra slow computation.

Define cloud computing.
?
On-demand, remote storage and compute resources, or services such that the user consume the compute as a utility provided to him, and the cloud provider provides large data centers to be rented.

What are the three type of cloud service modes? describe them briefly.
?
###### Infrastructure as a service (Storage/compute nodes)
- Provide Resources for compute, storage, networking as a service for system admins and developers.
- This mainly enabled by virtualization (Simplicity and auto scaling)
###### Platform as a service (Framework/ dist system)
- Provide environment setup (libraries, configuration), platforms, and services to specific applications for developers that do not want to build apps from the ground-up.
- Higher cost for setup
###### Software as a Service (Email, github, office)
- Provide application as a service, often via simple web interfaces for end users.
- Multi tenant systems at different abstraction levels depending on the application.
- Large scale data provides opportunities for data science and analytics.

What is function as a service?
?
###### Function as a service (Amazon Lambda)
- Which are event driven functions on the cloud that are computed on demand with pay as you go policy.
- deployment and auto-scaling of APIs/functions
- Auto-scaling provides a service that scales with the number of requests you send thus matching your size. This is great for parallel computation
- This lacks efficient data processing and has a limited lifetime cache and IO bottlenecks with high latency low throughup because of the communication process the data has to go through to communicate with its parts in different locations.
- This also Hinders distributed systems development due to the slow storage and non-specialized hardware.

What is edge computing and why do we need it?
?
- Edge devices are mobile and IoT devices that can and want to potentially use cloud computing.
- We want to have Different degrees of application decentralization for various reasons:
	- Privacy of data
	- Latency and uplink bandwidth constraints.
	- energy consumption and performance of devices.
	- Heterogeneity of devices

Name three desirable buisness cloud computing concepts.
?
1. **Pay as you go:**
	- No upfront cost for infrastructure
	- Pay per use or acquired resources
	- Great for seasonal peaks in computation, no need to waste resources and efficiency to prepare for peaks.
2. **Scalable Economy:**
	- managing IT infrastructure at scale leads to a lower cost.
3. **Elasticity:**
	- Assuming perfect scalability (Incorrect in real world scenarios due to ahmadl's law) the work is done in constant time * resources thus time can be reduced to necessity with many resources.


Name 4 characteristics of cloud computing services.
?
- **On-demand self service** with unilateral resource provisioning
- Has a **broad network accessibility** to enable communication between distributed systems across different locations.
- **Resource pooling** and virtualization enables the availability of resources when demanded.
- **Rapid elasticity** and availability when requested and paid for instead of waiting in a queue
- The service and usage is **monitored and measured** accordingly

Describe the different levels of virutalization.
?
- **Native virtualization:** Simulates most of the HW interface and runs a guest OS in isolation.
- **Para virtualization:** Does not simulate the HW but makes very specific hypercalls that require modifying the OS.
- **OS-level virtualization:** OS allows multiple secure virtual servers which appear to be isolated and running in different boxes.
- **Application virtualization:** virtualization of applications as different instances.

What are docker containers?
?
- Ship analogy: Standardize the container size for ship to reduce loading and unloading times, such that each container has self contained goods.
- Create a Self-contained package of necessary SW and data
- Perform Lightweight virtualization w/ shared OS and resource isolation per tenant for a shared hw
<!--SR:!2025-03-26,1,227-->

Name the four stages of resource management.
?
Selection
allocation
isolation 
task scheduling

Describe resource selection.
?
- **Resource selection:** Selection a number of bundles that fits the required resources for the task.
	- Resource selection methodlogy:
		- Manual: requires experience and prior knowledge with framework configurations and following rule of thumb.
		- Application agnostic (Reactive): Dynamically double the resources when full (autoscaling)
		- Application-aware (Proactive): Estimate the time/cost of jobs under your configurations and allocate according to contraints.

Describe resource allocation.
?
- **Resource allocation:** Virtual Bundles (from different tenants) are allocated in their own space in the physical hardware devices
	- NP-hard problem, Scheduling and allocation needs to be fast to avoid bottlenecks, thus done through simple heuristics (best-fit selection).
	- Kubernetes Container Orchestration:
		- Open-source system for automating, deployment, and management of containerized applications.
		- Kubelet: node manager
		- Controller: app master
		- Pod (1 or more containers w/ individual IP) scheduling: 
			1. Filtering: finding feasible nodes for pod
			2. Scoring: score feasible nodes → select highest score
			3. Tuning: sampled round robin
			- The scheduler then notifies API server with bindings

Describe resource isolation.
?
- **Resource isolation:** Making sure that multiple bundles from different users on the same hardware do not access or interfere with each other
	- Done through namespaces (to hide visibility) and cgroups (to limit resources)

Describe task scheduling and name the partitioning strategies used.
?
- **Task Scheduling:** Making sure that the tasks are split evenly such that maximal resource utilization is achieved for each user.
	- Given computation job and set of resources distribute job in pieces across resources.
		- Static partitioning: Divide the total number of tasks equally for all resources (low overhead, poor balancing)
		- Fixed paritioning: queue up fixed sized chunks into resources (high overhead)
		- Self-scheduling: Start by half and exponentially decrease task size with guided self scheduling.
	- The task placement is given in different ways:
		- Single task queue (airport)
		- Per-worker task queue (supermarket) w/ work stealing for empty queues
		- Power of two: Choose d bins at random, task in least full bin

Name 4 types of scheduling problems.
?
- **Bag of tasks:** Job of independent (embarrassingly parallel) tasks
- **Gang scheduling:** Job of frequently communicating parallel tasks
- **DAG scheduling:** Job of tasks with data dependencies contraints
- **Real-Time Scheduling:** Job or task with associated deadline (soft/hard)

Name some metrics used in scheduling problems.
?
Mean time to completion (total runtime for job), Throughput (jobs per time unit), Mean response time (Job waiting time for resources), Constrains and service level objectives (deadline, monetary costs etc..)


What is a file? what is an object? and what is a distributed collection?
- File: Arbitrarily large sequential data in specific file format 
- Object: binary large object, with certain meta data
- Distributed Collections: Logical unsorted bag of key-value pairs which offers easy distribution of pairs via horizontal partitioning

what are the fair principles?
?
- **FAIR Data Principles:**
	1. Findable: Metadata and data have globally unique persistent identifiers
	2. Accessible: Metadata and data retrievable via open, free and universal communication protocol
	3. Interoperable: Metadata and data use a formal, accessible, and broadly applicable format
	4. Reusable: Metadata and data described with plurality of accurate and relevant attributes

Describe distributed file systems.
?
- Files split into 128MB blocks for optimal disk head seek performance, replicated (3x), and distributed  for large clusters and datasets.
- Contains a Head node that has all the Metadata of data in the other nodes and manages file system namespace and access by clients
- While other nodes ( shared-nothing workers) Perform block creation, deletion, replication as individual files in local FS. On startup they scan local blocks and send block report to name node and can serve block read and write requests. Lastly they periodically send heartbeats to head node.
<!--SR:!2025-03-26,1,230-->

How do you perform read in a dfs?
?
Request is sent to head nodes first to create the namespaces, the head node communicates to the worker nodes the partitioning and replication of said file (replication can happen at the same time as reading due to different connections), lastly the nodes report back to the head.

How do you perform write in a dfs?
?
Request is sent to the head node, which informs the client to the closest worker node that the client can read sequentially from.

what is an input format and record splitting?
?
For each type of file an input format is inserted into the binary file that cannot be repeated elsewhere in the data that represent record-aligned splits and offsets to read from.

Describe Log structured merge tree.
?
- Write into an in-memory Buffer that contains key-values (B tree for example).
- Whenever the buffer fills up, it is sorted and stored in-disk and the buffer is emptied.
- Probing a read will always go to the buffer to access "latest first".
- Once both are filled, they have to be compacted, deduplicated and merged into a larger in disk structure.

discuss Tiering vs leveling in log structured merge trees.
?
- **Tiering:**
	- Multiple levels of "runs".
	- Multiple sorted runs (files) can exist at each level before compaction which are then compacted at max run capacity.
	- Compactions happen less frequently thus faster writes.
- **Leveling:**
	- Only one sorted run per level
	- New data merges immediately with the existing run at the target level
	- This is more optimized for reading than tiering because only one run per level needs to be checked, however it incurs more compactions.
<!--SR:!2025-03-26,1,230-->

Describe the different types of parallelization.
?
- *SIMD (vector):*  process the same operation over multiple elements at a time (instruction level data parallelism), mainly used for batch-processing.
- *SPMD Distributed data parallel computation:* similar to SIMD but not on instruction level, instead is on program level performed on a distributed collection. Mainly used for batch processing.
- *MISD (Pipelining):* having single data be processed over multiple operations/intrsuctions through a pipeline.
- *MIMD (multi-core):* doing different instructions on different cores processing different elements. Can be used for both batch and mini-batch processing.

Describe the different types of matrix formats.
?
- *Dense:* linearly/sequentially store blocks row-wise.
- *Coordinate Matrix:* Store coordinates of non-zero tiles using 2 arrays for i and j, and a third array for values
- *Compressed sparse rows:*  The first array i-th value indicates which index to go to for the i-th row start, whilst the second array indicates the column index and is linked to a value.
- *Modified Compressed sparse rows:* takes on the approach of CSR except it trades more memory in order to make CSR more update friendly by making the first array point to an updatable separate list per row.


Name and describe the different partitions a distributed matrix would be represented with.
?
- *Block partitioned matrices:* typically Fixed-size, square or rectangular tiles, has a bit of overhead in order to convert row-wise inputs (text) into blocks. This allows us to represent different regions (tiles) of a big matrix using dense and sparse representations.
- *Row partitioned matrices:* instead of blocks, each "tile" is considered a row/column, which deals better with row-wise data and has seamless data conversion (no overhead) but is cache unfriendly and doesnt benefit from Block partition exploitation (for example for sparse data).
- *Partitioned matrices (General):* collection of tiles of a matrix stored on a physical partition as immutable tiles, row/column wise partitions store the tiles accordingly, while physical partitions store them in a hashed layout. 

Describe map reduce.
?
- Map-reduce is a highly configurable multi-data operation that consists of two operations:
- *Map:* Operations which takes in a key/value pair and produces a set of temporary/intermediate key/value pairs according to the mapping function specified. (For example: counting the occurrence of unique values will ask map to map every unique value to a key and their value to 1)
- *Reduce:* Operations which take in the intermediates of the Map, and reduce it to the result using some specified merging computation (Continuing the previous example: we sum all values that share the same key and we output each unique value and its occurrence )
-  input files are split into different splits
- When there are multiple reducers, in order to give the same keys to the same reducer, we introduce a hash function that will map the key to a position%N such that N is the number of reducers, then Each map worker will split its output into N sub-files  and sending the keys to the appropriate ones. this is called *Hash partitioning*.
- *Hash partitioning* is very useful to avoid extensive search for operations like Join such that we only need to consider joins between similar keys, moreover single key look-ups are quite easy as we only need to scan the key value in each partition not the entirety of it.

What is data parallel execution?
?
Data parallelism is the partitioning of data across multiple workers in order to execute the same program quickly.

Describe some data parallel distributed matrix operations.
?
- *Element-wise multiplication:* Only needs to consider the matching block and perform the element-wise reduce.
- *Transpose:* Only needs to transpose the block positions and exchange the row and column indices per block.
- *Matrix multiplication:* Only Blocks of transposed indices contribute to the same output block.

what is task parallel execution?
?
 Task parallelism is the execution of multiple different tasks on the data in different workers.

What is stream processing?
?
Unlike traditional data processing where the data is static and the queries are unlimited, Stream processing is an infinite flowing stream of data (Event and message streams) going through a push pipeline of a limited amount of queries.  
Stream processing often comes with real time latency requirements to uphold and continuously process.

Describe the model and architecture of stream processing.
?
- Fixed amount of queries, running asynchronously on each thread. Each query is separated by an flow queues (Buffer).
- The entire model is a push model with potentially many consumers. Data production is thus controlled by data input.


How do you optimize stream processing?
?
1. **Sharing:** For multi-query operations, sharing intermediates in a DAG can be quite crucial to provide minimal redundancies (Operator and queue sharing)
2. **Overload Handling:** Often times your pipeline is not as far as the source and has a bottleneck.
3. **Distributed Stream processing:**
	- Partition and distribute the Query Execution Plan to be handled by multiple workers (Pipeline and task parallelism).
<!--SR:!2025-03-28,3,250-->

Name 2 types of overload handling.
?
1. *Back Pressure:* Using blocking queues slow down the source to the bottleneck speed without losing any data.
2. *Load Shedding:* Keep the source speed but shed the overloaded data before the bottleneck, this can either be done randomly, relevance based or summary based (Goes along the SLA to minimize error and maximize satisfaction).

What are the different partitioning schemes in distributed stream processing?
?
1. *Shuffle Grouping:* randomly distribute them or using round robin, has a good load balance but tuples might be processed out of order if two units of the same key go in different workers.
2. *Fields Grouping:* Group according to a fields value using a hash function % number of workers. (Can have poor work balance if power consumers exist)
3. *Power of two:* For each key, select 2 candidates (similar to fields grouping) and choose the one least filled.


Describe data parallel parameter servers.
?

- Parameter servers consist of Server that holds all parameters for a model and N workers, The workers pull in the weights from the model, compute stochastic gradient descent on a mini-batch of the data that they have independently, and then push the gradient (or difference in weights) back to the parameter server (It can be one computation or multiple steps of back-prop, which takes in updates from all workers and aggregates them in a certain way to do its own model parameter update.

What are the different strategies used to update parameter servers?
?
- *Bulk Sync Parallel:* Naively wait for all workers to be done and update the server with all worker's output synchronously, this can lead to less utilization of resources since all workers might have to wait for one slow worker to finish its job.
- *Async Parallel:* Update the model with each output from the worker immediately without waiting, can lead to stale dirty reads.
- *Sync with backup workers:* Add a barier entry, where you wait for K out of N workers to finish their job and then perform the update.
- *Stale Sync Parallel:* Adds a barrier that blocks the fastest worker if the gap between the fastest and slowest exceeds a certain limit.
- *Decenteralized:* No central parameter server, instead each worker is a node that communicates its update with its neighbours.
<!--SR:!2025-03-28,3,250-->

Describe model parallel parameter servers.
?
- Very often in DL we have deep models with many activations and weight matrices that cannot all fit in memory in the forward pass to aid in the computation of the backward pass, this is where we deploy the concept of model parallel parameter servers where different parts of the model is stored on different workers and they work in a pipelining manner.

What is federated learning?
?
- Is practically a parameter server running with N workers, except the workers this time are products solds to customers by the parameter server owner (for example phones).
- The mini-batch data is extracted from the product itself to train the model, however it needs to be ensured that privacy of the data itself never leaks, we are only interested in the weight updates that the samples cause to our model, not the data itself.
- Communication is often limited and unreliable, thus you have to take into account which workers and how many you are going to employ, even if you do manage to get the computation working, you have to account for data distribution bias of the selected workers.
- Avoid negatively impacting the products by using data or battery.