# System Landscape
![[Pasted image 20240905144034.png || center]]
###### The Data Science Lifecycle consists of three stages:
1. **Data**: data integration, data cleaning, data preparation
2. **Model**: Model selection, Model training, Hyper-parameter tuning
3. **Deployment**: Validate and debug, deploy, score and feedback
###### The Driving factors for ML systems:
1. **Improved Algorithms and models:** The Success and shift of Machine learning algorithm towards models that require large amount of data but have much better accuracy (Deep Learning), these complex models not only accelerated the accuracy of previous tasks but also expanded onto newer applications and domains in ML.
2. **Availability of large data:** The increasing amount of available labeled data that can scraped from the internet, or even automatically generated from daily user processes, alongside self-supervised learning has increased the capabilities of what ML models can do.
3. **Hardware and software advancements :** higher performance of hardware and infrastructure, alongside massive software computation efficiency optimizations with Open-source large-scale computation frameworks.

## ML Systems Stack:
### 1. ML applications and algorithms
- **Algorithm Choice:** data availability decides supervised vs unsupervised, batch vs minibatch, first order updating vs second order updating, Variety of architectures and optimizers and losses.
- **Specialized apps:** You can specialize your application to efficiently and cleverly simplify the ML operation cost by reducing irrelevant computation.
- **Data programming and augmentation :** Generation of more data (noisy) efficiently for pre-training.
### 2. Language Abstractions
- **Optimization Objective:** Time v.s Memory v.s error minimization with constraints
- ##### Machine learning libraries are split into many types:
	1. **Language abstraction libraries:** libraries that simplify the language (make it more abstract) by providing their own functions such as :
		- *Operator libraries:* mainly Offering operators on HW like matrix multiply (CuDNN)
		- *Algorithm libraries:* Offering ML algorithms ready for use (scikit-learn) or model zoos that offer pre-trained models up for transfer learning like huggingface and Yolo
		- *Computation Graphs:* Offering you a way to assemble your own algorithms using their own optimized computation graphs. (Pytoch)
		- *Linear algebra :*  Offering linear algebra computation in simple operations (Julia)
	2. **Execution strategies:** libraries that offer different execution strategies
		- *Parameter servers:* Offering model parallel computation (TF)
		- *Task Parallel constructs:* Offering parallelization of different tasks (Matlab)
		- *Data parallel operations:* Offering the parallelization of running your task over chunks of it (Spark)
	3. **Distribution:** libraries that  offer different ways of distributing the computation
		- *Local:* single node computation (Julia)
		- *Hw acceleration:* uses other HW to improve upon computation (TF)
		- *Distributed computation:* can provide ways to distribute the computation across nodes (spark)
	4. **Data types:** libraries that offer different efficient data types to deal with your problems such as Collections, Matrices, Graphs, Tensors, Frames
- ##### Query Optimization: 
	-  Re-write/order Operators such that the end result is less costly
	- Choose a matching physical operator that executes the operator cheaply
	- **Different scopes of Optimization:**
		- *Eager Interpretation:* Also called Operator at a time, it execute as is, no options.
		- *Lazy Expression Evaluation:* Create a program graph (DAG - Flow Tree of operators and intermediate results - ) that gets optimized and executed efficiently, some options
		- *Program Compilation:* Optimizes and compiles the entire code, has full control of decisions for optimization, even larger optimization scope.
	- **Size inference and cost estimation:**
		- Size information is comprised of the dimensions and the sparsity of the data, which helps us determine memory estimates and costs
		- *DAG-level size propagation:*
			- If we know the dimensions of our input, through linear algebra and other rules we can propagate (Bottom up) dimensions through the DAG
			- For guarantees we must consider the worst case (if we are unsure) in order to not break the guarantee.
			- Examples:
				1. Matrix multiply MxN @ NxC = MxC
				2. Matrix Diagonal MxM = Mx1
				3. Conv2d Nx(C * Hin * Win) = Nx(Filters * Hout *  Wout) such that Hout and Wout are computed by convolution formula
		- *Constant Propagation:* Propagates constants by running through the code and detecting which variables do not change (Live variable analysis) then transferring them to a read-only hashmap
		- *Program-Level size propagation:* We propagate dimensions information through the entire of the program by taking it apart into blocks of code that represent DAGs, perform DAG propagation, and then take each input and output of the DAGs and propagate the dimensions through them as a potential path. Remember that blocks can be if statements or loops that you do not know how long we stay in. Thus the program has to speculatively run a path through the cases and compute the dimensions for either one.
		- *Intra/Inter Procedural Analysis (IPA):* Integrates all size propagation techniques mentioned above, goes through different function calls and propagates the input and output size information through those calls. This is called once and it passes through the entire code, it also performs additional passes to remove dead-code that never triggers and does rewrites accordingly
			- Note that sometimes function calls are ambigious like through execev("Name"), We do not know how these functions operate and cannot speculate any sizes so we trigger the unoptimized version of the function and do not change anything about it.
		- *Sparsity Estimation:* alongside the previously mentioned dimensionality estimation procedures, We need to also estimate the sparsity because in certain cases (which are common in ML fields like NLP and recommender systems) , the sparsity saves on so much computation during execution.
			- Sparsity is measured with # Non-Zeros / # Cells, i.e a maximally dense matrix has sparsity of 1 and a zero matrix has sparsity 0
			- We often assume there are no NaNs in the matrices and no Cancellations (positive and negative number perfectly add up to 0)
			- The objective is to estimate the sparsity of Matrix C given the sparsity of matrix A and B and the operator @ such that C=A@B, there are many methods to achieve this, and the trade-off is usually between accuracy and efficiency:
				1. Naive Metadata Estimator: assumes uniform distribution of the 1s and 0s in the input matrices, derive the output from the sparsity of the input $S_{c}= min(1, S_{A}n) \cdot min(1, S_{B}n)$ where n is the common dimension (Matrix multiplication)
				2. Naive Bitset Estimator: We convert matrices into bitsets (1 where there is a number, 0 where there isnt) and perform a Matrix multiplication (Accurate but inefficient)
				3. Sampling: Sample  random aligned row and columns from the matrices, do their dot product (as a bitset) and take their maximum as a lower bound.
				4. Density map: Like the Bitset estimator but instead we store sparsity in blocks/tiles and propagates those sparsities through probabilistic $S_{A}+S_{B}- S_{A}S_{B}$ (The first term assumes that sparsity is additive and 2 non-zeros dont collide)
				5. Layered Graph: each Node in the graph is a row/Column in the matrix mm, and each edge connection is a non-zero connecting row/column. Given a chain of matrix multiplication we can decide on the matrix multiplication that is maximally sparse but re-ordereing the graph such that many paths are pruned
				6. MNC Sketch: We store metadata for matrices that tells us How many non-zeros exist per row/column and how many of those non-zeros exist alone in their corresponding column/row, For those that exist alone the estimator is exact and accurate and know the final index of the operator.
		- *Memory Estimates from size information:* We can estimate Matrix memory size given the dimensions and the format (dense/sparse) we can also estimate the Operation memory size by estimating its inputs outputs and intermediate memory sizes.
			- Logical Vs Physical level estimation: Costing at physical level takes physical ops and rewrites into account but is much more costly, Which is why people usually prefer Logical as a rough estimate that is easy to compute is more desirable
			- Operator Cost Graphs Vs Plans: Costing plans requires heuristics for # iterations, branches in general
			- Analytical Vs Train models: Analytical estimates I/O and compute workload whilst regression models predict individual operations
	- ##### Operator Re-writes:
		- Types of Re-writes:
			1. **Common Subexpression elimination:** Remove redundant sub-expressions that are calculated multiple times without any change or update in-between, replace the leafs of the DAG between the expressions that share sub-expression by a shared input and remove common paths in a bottom-up approach. Beware in case of non-determinism or randomness do not merge unless theyre of the same seed.
			2. **Constant Folding:** After constant propagation, if certain expressions are comprised of mainly constants, compute the result and fold them into one constant
			3. **Branch Removal:** After constant propagation and folding, certain blocks or statements for those constants might never be accessed and thus they are removed from the DAG
			4. **Merge of statements:** Merge sequences of unconditional blocks into one block (after constant propagation)
			5. **Deadcode elimination:** Backwards pass through program to eliminate operations that create variables which are not used in subsequent statement blocks
		- Examples of static re-writes: Static re-writes are re-writes that are always optimal regardless of size information.
			1. Trace( X@Y) = Sum(X * Y.T)
			2. Sum( lambda * X) = lambda * Sum(X)
			3. (X@Y)[3,7] = X[7,:]@Y[,3]
		- Examples of dynamic re-writes: Dynamic rewrites are conditional re-writes that are optimal if the condition applies
			1. X.T @ y = (y.T @ X).T s.t if X is much larger than y
			2. sum( X^2) = X.T @ X; rowSum(X) if columns(x)=1
			3. sum(X@Y) = sum(ColSum(X).T * RowSum(Y)) if columns(X) > t
		- Vectorization and incremental computation: are operations that can be improved manually in python code (hard to do with other languages) that involve removing the use of for loops and instead using vector operations such as:
			- for(i in a:b)
				X[i,1] = Y[i,2] + Z[i,1]
				=
				X[a:b,1] = Y[a:b,2] + Z[a:b,1]
		- **Matrix Multiplication Chain Optimization:**
			- Matrix multiplication chain of n matrices M1, M2, …Mn, decide on the optimal multiplication order
			- Matrix multiplication is associative not commutative so we cannot re-order the matrices, only decide on where the parentheses lie
			- Instead of brute-force we use the principal of optimality.
				- Initialize an upper-triangular Cost matrix and work your way from the base to the top
				- for the first layer (diagonal) the cost of putting parentheses around one matrix is 0 thus ignored
				- any subsequent layer will take into account the previous amount of plans and considering the optimal of two choices
				- for example for layer 2 we consider 1 plan which is M1 * M2, for layer3 we consider 2 plans (M1 * M2) * M3 or M1 * (M2 * M3)
				- the way to compute the cost is to add up all previous costs that took you there multiplied by the dimensions of both matrices
				- at each level we consider i-1 plans
- ##### Runtime Adaptation:
	- Runtime/ Compilation faces off a lot of challenges including but not limited to:
		- *Unknown/changing sizes* by using function calls or dynamic size calculation, the size inference is crucial for cost estimation and there exists the trade-off of optimization scope vs size inference effort, this can lead to very conservative fallback plans. Unknown size information can be caused by:
			- Control flow: Complex while loops and user defined functions.
			- Data dependencies: Selection of size depending on values of data (dynamic selection)
			- Changing dims and sparsity: Iterative feature selection workloads, same code with diff data
			- API limitations: Pre-compiled scripts/programs
		- Certain operators have a lot of runtime overhead that dominates the runtime process and we want to try and minimize it by reducing intermediate overhead, parallelization, operator fusion.
	- **Ahead-of-time compilation:** originates from languages like C where you have some overhead compilation process before running but then you get an optimized runtime. (Program compilation, inference program compilation and packaging)
	- **Just-In-Time compilation:** Originates from languages like java where the startup time is not long, and if a method is executed a lot then it will be re-compiled and optimized to be faster (Lazy expression evaluation+optimization, Program recompilation) 
	- ###### Dynamic re-compilation techniques:
		- **Compile-time Decisions:** Split high level DAGS strategically into basic blocks such that in-between basic blocks, you can recompile an entire DAG, and when faced with unknown statistics you mark the block for re-compilation.
		- **Recompile Once Functions:** Mark functions that cause unknowns as "recompile once" if it contains a loop, then recompile the entire function on entry +  disable unnecessary recompile.
- ##### Operator fusion:
	- Take simple operations that are bandwidth bound and memory intensive and produce simple alternatives that get you the same result without having to materialize the intermediate results, There are 4 major cases and opportunities for operator fusion:
		1. **Unnecessary intermediates:** when computing SUM(X@Y@Z) typically we would need to generate the large intermediates formed by the MM, however this is unnecessary for the final computation and can be avoided, this can also be Observed when we do $X^Tv$ instead of $(v^{T}X)^{T}$ because we are materializing the transpose of something potentially very large.
		2. **Single pass:** in certain computation where the same large variable is used multiple times for the same computation when it can be avoided and computed immediately (bandwidth optimization) for example $X^{T}(Xv)= ((X^Tv)X)^{T}$ where a singular row of X is used twice for computation, and does not have to be read twice to reach the end result.
		3. **Multi-Aggregates:** The use of the same variable multiple times in different ways that need not be done at separate times with separate intermediates
		4. **Sparsity Exploitation:** if a complex term is then multiplied by a sparse matrix, its often very unnecessary to compute the entire complex term because a lot of it is going to cancel out and instead we just compute the values for non-zeros.
	- **Fusion Heuristics:** We want to limit Materialization points, exploit sparsity, make decisions on fusion patterns and respect constraints.
		- Determine Plan partitions, separate the plan into independent blocks where interfering with one will not affect the other. if two part of the same plan are connected via 1 dependency then treat them as cut sets and optimize independently.
		- Candidate selection, Look at all the interesting points, which are points that branch out as input to many other points
		- Plan exploration, look at every single possible plan from those candidates and determine the cost optimal one
		- Handle violated constrains by setting their cost to infinite.
		- Cost-base Prune sub-plans that have already went over the upper bound of cost
	
### 3. Fault Tolerance
- Computing operations with big data is bound to get faulty even with low probabilities thus we need to be able to deal with this trade-off efficiently.
- **cost-effective resilience:** How long does it take for one task to fail at scale
- **Fault Tolerance in Large-Scale Computation:** Methods to detect and recover fails, Block replication, Checksums and parity bits, Logging and checkpointing, Recomputation for recovery
- **ML-specific Schemes:** Estimate the contribution of a lost component, if the contribution is not significant, don't slow down the process by trying to recover it!

### 4. Execution Strategy
- Accuracy V.S Performance trade-off
- **Batching Algorithms:** Batch algorithms take the entire data and compute gradients (for example) based off of the data, quite commonly data-parallel operations are used to efficient implement this.
- **Mini-Batch Algorithms:** Mini-batch algorithms are used for heavier models that cant take the entire data, we pick a small amount of data and use it for a noisy estimation of the gradient. These algorithms use Parameter servers that allow Data-parallel operations alongside Model parallelism (Data partitions with update strategies)
- **Gradient methods (1st order):** Optimizing the model through navigating the opposite direction of the gradient at each point.
- **Newton methods (2nd order):** optimizing the model through root finding methods like newton's, iteratively compute jacobian/Hessian in order to find a 0 (lowest point). This is generally expensive with millions of parameters, thus Quasi-Newton methods approximate the Hessian and perform similar methods.
- **Files v.s objects:** are arbitrarily large sequential data in a specific format, objects are binary large object, with certain meta data.
- **Distributed collections:** Multi-set of key-value pairs, such that the values are flexible to be any data type, designed to be partitioning row-wise (shards) such that each partition goes to a worker.
- **Parallelization types:**
	- *SIMD (vector):*  process the same operation over multiple elements at a time (instruction level data parallelism), mainly used for batch-processing.
	- *SPMD Distributed data parallel computation:* similar to SIMD but not on instruction level, instead is on program level performed on a distributed collection. Mainly used for batch processing.
	- *MISD (Pipelining):* having single data be processed over multiple operations/intrsuctions through a pipeline.
	- *MIMD (multi-core):* doing different instructions on different cores processing different elements. Can be used for both batch and mini-batch processing.
- **Map-Reduce:** 
	- Map-reduce is a highly configurable multi-data operation that consists of two operations:
	- *Map:* Operations which takes in a key/value pair and produces a set of temporary/intermediate key/value pairs according to the mapping function specified. (For example: counting the occurrence of unique values will ask map to map every unique value to a key and their value to 1)
	- *Reduce:* Operations which take in the intermediates of the Map, and reduce it to the result using some specified merging computation (Continuing the previous example: we sum all values that share the same key and we output each unique value and its occurrence )
	-  input files are split into different splits
	- When there are multiple reducers, in order to give the same keys to the same reducer, we introduce a hash function that will map the key to a position%N such that N is the number of reducers, then Each map worker will split its output into N sub-files  and sending the keys to the appropriate ones. this is called *Hash partitioning*.
	- *Hash partitioning* is very useful to avoid extensive search for operations like Join such that we only need to consider joins between similar keys, moreover single key look-ups are quite easy as we only need to scane the key value in each partition not the entirety of it.
- **Apache Spark:**
	- Built upon the idea of Map-Reduce but optimized it to be much faster, and added default configurations such that it isnt exhausting to deal with
	- Spark focuses on being unified for many languages, libraries, file systems and managers for data-parallelism.
	- Spark adds Partitions split into key-value physical partitions implicitly during data shuffling (for example in map function) or explicitly though a call. Partitioning can be exploited if we have previously partitioned and only been through partition preserving operations, such that if we were to join 2 partitions, we already know where each Key lies and thus we dont have to consider NxN joins, only parallel.
- ##### Data-Parallel Execution:
	- Data parallelism is the partitioning of data across multiple workers in order to execute the same program quickly.
	- **Distributed matrix operations:**
		- *Element-wise multiplication:* Only needs to consider the matching block and perform the element-wise reduce.
		- *Transpose:* Only needs to transpose the block positions and exchange the row and column indices per block.
		- *Matrix multiplication:* Only Blocks of transposed indices contribute to the same output block.
	- **Physical Operators:** in order to pick which physical operator to choose we need to consider data characteristics such as size, shape, sparsity, and operation properties such as data locality (Which node/worker its in), sparse-safe operations, co-partitioning.
		- *Local:* if the size is small enough then we can avoid the distributed computation overhead and compute things locally.
		- *Special operators:* We can always abuse operation fusion in order to avoid redundant computation of intermediates.
		- *Broadcast Based:* Broadcast based operators share their tiles to a log amount of workers, such that each worker sends them to log amount of works too, the workers participate in broadcasting the information to others and use the full bandwidth in order to execute the operator.
		- *Shuffle and co-partition based:* Operators that need to re-shuffle and partition the data for the certain operation? very expensive!
- ##### Task-Parallel Execution:
	- Task parallelism is the execution of multiple different tasks on the data in different workers.
	- **Parallel For Loops:**
		- is a Combination of data- and task-parallel ops, executed locally (multi-threaded) or in a distributed manner.
		- Conceptually it is a coordinator for tasks, each task is a parfor iteration.
		- Tasks can be divided in a fixed manner, static n/k manner, scheduled manner, the task queue queues up the number of tasks and the workers dequeue the tasks from the task queue.
		- Data can be partitioned locally and remotely
		- tasks can be executed locally with multiple cores, or remotely using spark
		- Result aggregation
- ##### Data-Parallel Parameter Servers:
	- Parameter servers consist of Server that holds all parameters for a model and N workers, The workers pull in the weights from the model, compute stochastic gradient descent on a mini-batch of the data that they have independently, and then push the gradient (or difference in weights) back to the parameter server (It can be one computation or multiple steps of back-prop, which takes in updates from all workers and aggregates them in a certain way to do its own model parameter update.
	- **Update strategies:**
		- *Bulk Sync Parallel:* Naively wait for all workers to be done and update the server with all worker's output synchronously, this can lead to less utilization of resources since all workers might have to wait for one slow worker to finish its job.
		- *Async Parallel:* Update the model with each output from the worker immediately without waiting, can lead to stale dirty reads.
		- *Sync with backup workers:* Add a barier entry, where you wait for K out of N workers to finish their job and then perform the update.
		- *Stale Sync Parallel:* Adds a barrier that blocks the fastest worker if the gap between the fastest and slowest exceeds a certain limit.
		- *Decenteralized:* No central parameter server, instead each worker is a node that communicates its update with its neighbours.
	- **Data Partitioning:** we want to evenly spread the weight across the workers while not giving a certain worker biases and skews in data.
		- *Disjoint Contiguous* row partitions of the data without shuffling and hoping that your data is diverse enough.
		- *Disjoint Round Robin* row partitions of the data, allows for randomization while still being simple.
		- *Disjoint random* row partitions of the data, needs random index sampling, very unlikely that the data in a worked is skewed.
		- *Overlap shuffle* which sends the entire data to each worker shuffled different and hoping that each mini-batch is different in each iteration.
	- **Batch size configuration:** Maximum useful batch size is dependent on data redundancy and model complexity
		- Bigger batch sizes decrease the number of steps it takes to converge up to a certain task specific order.
		- Bigger batches have less variance in the resulting gradient.
		- Bigger batches are more expensive to compute.
		- Bigger batches reduce the overall communication overhead of having to split and trasnfer many small batches. This however for large systems can be avoided by pre-ordering the batches during the backpropagation step such that we maximize the use of our bandwidth and minimize the time it takes to wait for overhead.
			- Communication can also be compressed using less bits since gradients are already a rough approximation. using quantization or even lossless compression.
			- Aggregation can be done in programmable switches during packet transfers to reduce overhead.
	- ###### Model-Parallel Parameter Servers:
		- Very often in DL we have deep models with many activations and weight matrices that cannot all fit in memory in the forward pass to aid in the computation of the backward pass, this is where we deploy the concept of model parallel parameter servers where different parts of the model is stored on different workers and they work in a pipelining manner.
- ##### Federated Machine Learning:
	- Is practically a parameter server running with N workers, except the workers this time are products solds to customers by the parameter server owner (for example phones).
	- The mini-batch data is extracted from the product itself to train the model, however it needs to be ensured that privacy of the data itself never leaks, we are only interested in the weight updates that the samples cause to our model, not the data itself.
	- Communication is often limited and unreliable, thus you have to take into account which workers and how many you are going to employ, even if you do manage to get the computation working, you have to account for data distribution bias of the selected workers.
	- Avoid negatively impacting the products by using data or battery.
### 5. Data representations
- ##### Data representations:
	1. *Ml systems:* uses both dense and sparse tensors, can use different sparse formats, frames
	2. *DL systems:* Tensors are almost always dense, embeddings (which are semantic preserving numerical representations of features) for NLP and graphs
	- **Matrix formats:** All matrix storage formats using Matrix blocks/tiles, but they differ in the storage of said tiles
		- *Dense:* linearly/sequentially store blocks row-wise.
		- *Coordinate Matrix:* Store coordinates of non-zero tiles using 2 arrays for i and j, and a third array for values
		- *Compressed sparse rows:*  The first array i-th value indicates which index to go to for the i-th row start, whilst the second array indicates the column index and is linked to a value.
		- *Modified Compressed sparse rows:* takes on the approach of CSR except it trades more memory in order to make CSR more update friendly by making the first array point to an updatable separate list per row.
	- **Distributed Matrix representations:**
		- *Block partitioned matrices:* typically Fixed-size, square or rectangular tiles, has a bit of overhead in order to convert row-wise inputs (text) into blocks. This allows us to represent different regions (tiles) of a big matrix using dense and sparse representations.
		- *Row partitioned matrices:* instead of blocks, each "tile" is considered a row/column, which deals better with row-wise data and has seamless data conversion (no overhead) but is cache unfriendly and doesnt benefit from Block partition exploitation (for example for sparse data).
		- *Partitioned matrices (General):* collection of tiles of a matrix stored on a physical partition as immutable tiles, row/column wise partitions store the tiles accordingly, while physical partitions store them in a hashed layout. 

- ##### Data Access Methods:
	- Through analysis of ML systems matrices of weights and inputs, we come to the conclusion that certain matrices are inflated beyond need, whether its sparsity, feature redundancies, column cardinalities and unique values or correlations. Such characteristics leads us to develop smart ways to handle and Access data.
	- *Distributed Caching:* in a distributed RDD, we allocate a certain range of memory in each worker node for caching and we keep pointers in memory to this partition as long as we are not exceeding memory limitations.
	- *Buffer Pool Managemenet:* Often times we cannot fit live variables in the memory of CPU/GPU so we have to use eviction strategies to only keep the memory we want in the buffer pool of the worker and evict the rest into local storage.
		- Classically this is done by attaching metadata objects to the matrices, such that they interact different with the different operators, such as pinning the matrix in memory such that it is localized.
	- *Shared Scanning:* Scan sharing concept is to not scan a large data object multiple times to contribute in multiple operations (for example matrix vector multiply over many vectors), instead scan the matrix once and *batch* all the vectors together to perform matrix matrix multiply (from bandwidth bound to compute bound). This can also be seen similarly in operator fusion where we avoid large intermediates. Using this strategy we can also do *runtime piggybacking* where we utilize the same ideas of scan sharing over multiple models to be trained in a distributed manner that share the same input.
	- *Non-Uniform Memory Access (NUMA)-aware partitioning and replication:* in the context of model-parallel parameter servers, where each node does not have direct access to the other node's memory directly, it is often better to perform data replication/sharding over the entire data to give to each worker rather than letting them work on the same minibatch?
		- *Adaptive tile matrix:* Partitioning can be NUMA-aware as well by giving partitions to different works with roughly equal sparsity. this is done by calculating a density map over the Z-ordered matrix representation and storing it in a quad-tree of equal tile density.
	- *Indexing:* indexing using B-tree variants is quite useful for quick and easy access.
		- Linearized Array B-tree: The matrix is scanned Tile by tile row-wise, and each tile is scanned element by element row-wise and inserted into a B-tree (This is called Z ordering) . Can be done for partial elements of the matrix by specifying query order.
	- *Pre-fetching:* reuse the idle time of CPU by letting it pre-fetch batches while other HW are working at training the current batch, this however sometimes takes longer than the intended training, thus we sometimes deploy *data echoing* which retrains the model on the same current batch multiple times until the next batch arrives to avoid idle GPU time.
- ##### Compression:
	- ###### Lossy Compression:
		- How much Precision are you willing to sacrifice in order to store your data efficiently (Quantization). This is often used a lot in modern ML because ML algorithms approximate by nature + noise generalization effect thus, further loss (s.t minimum accuracy loss) is a helpful tradeoff
		- Which part of the training procedure suffers the most from low accuracy FP? it has been shown that accurate accumulation is quite important for the convergence of the ML model and for stable training. However low accuracy in intermediates and specifically low accuracy in weight updates does not affect the accuracy significantly while trading major storage efficiency.
		- **Numerically stable accumulation, given low precision:**
			- We can sort/split the summation up such that we calculate all the small values together which provides us with less loss accuracy than normal summation.
			- *Khaman Summation:* is an algorithm that provides minimal loss with little overhead of each summation (independent of number of values) iteration by calculating the error correction at each step and adding it to the accumulated sum.
		- **Stoachastic Rounding:** rounding fp numbers to a lower accuracy with a stochastic probabilistic approach to both ends (instead of deterministic)
		- **Quantization:** since it has been shown that model training can be done in UINT8, we can quantize our fp values into integers by splitting the values in N buckets, these buckets can either be static (Equi-width) or can be dynamically learned from the data distribution (Equi-height) such that it gives high precision to high density areas.
		- **Sparsification:** After training, clip out values near 0 in the frozen weight matrix that do not contribute much s.t minimal loss in accuracy which results in an exploitable sparse representation.
		- **Connection sampling:** Let different workers update/work with  a disjoint set of neurons/weights. this results in each worker having a sparse version of the model and only working on improving that part. THis is done by masking at every iteration.
		- **Mantisa truncation:** Truncate the precision mantissa of FP representations whule keeping the range.
		- **Sampling:** Generate synthetic data that maximizes likelihood while minimizing correlation and data redundancies between them such that they can train the model well enough.
		- **Aggregated data representation:** use compressed data representation in the latent space to reformulate your data.
	- ###### Lossless Compression:
		- Storage efficiency while being able to reconstruct the data perfectly (Sparsization). Allows us to compute the exact same result while fitting the data in-memory by reducing data bandwidth.
		- **Compressed Linear Algebra:** CLA is a lightweight compression scheme that scans the columns of a matrix and compresses it by exploiting correlation and redundancies in the features. This is done in such a way that you do not need to de-compress it to perform basic linear algebra operations but instead you can do the same on the compressed version. The goal is to offer little to no overhead on small matrices that already fit in memory to avoid performance damage, but provide much better performance for larger matrices due to the compression that avoids loading and unloading chunks of the data in and out of memory.
				1. Classify compressable columns by scanning over the columns and selecting a strategy each. The classification is done by analyzing the number of distinct tuples, the number of non-zero, and the number of runs. The columns are then classified to either Uncompressed if they do not benefit from compression or one of the following compression shcemes (Offset List, Run-length, dense dictionary coding)
				2. Columns are then grouped with each other to exploit linear dependencies by continuously finding two columns that can be compressed together and grouping them.
				3. The compression scheme is then applied per group.
		- **Tuple Oriented Compression:**
			- modern ML systems use mini-batches with few rows thus, this method is applied with additional overhead to compress relations row-wise. (Effective for small batches).

### 6. Hardware and infrastructure
-  **Roofline Analysis**:
	- Its a basic diagram that measures how many floating point operations do you do per byte transferred from main memory into the processing Unit.
	- if you have higher operational intensity (Matrix matrix multiply) you can fully utilize your hardware and you are compute bound, meaning that no matter how much you keep increasing bandwidth, you wont get better performance because your computation is at its limits.
	- if you have low operational intensity (Like matrix vector multiply) you are bound by memory bandwidth, which means that thius operation is simple to compute making the bandwidth struggle to keep up with the computation.
- **Hardware Challenges:**
	- End of Dennard's scaling states that that the power always stays proportional to the area of the transistor, thus if we keep scaling down transistors, the voltage or capacitance need to be upped to keep the power up, however this becomes harder the smaller the transistor because at a certain point there will be voltage leaking from neighbouring transistors because theyre so close.
	- End of Moore's law Performance of CPU doubles every 2 years, except we are now reaching its peak and we cannot go any further in performance scaling. This results to looking for different alternatives to keep the progress going like specialization of hardware for  specific tasks making them very efficient at it.
	- Amdahl's law states that the best speedup you can get on your program is 1/s such that S is the serial fraction of your program.
- **Handling Memory constraints:** how do you handle models and situations such that the amount of information (weight matrices for example) that need to be stored for the operation exceeds memory constraints in the HW.
	- Live Variable analysis: Analyzing variables in the DAG such that we can remove intermediates from memory immediately after we are done with their usage for the rest of the DAG.
	- GPU/GPU eviction: Evict variables from GPU to CPU memory under memory pressure according to eviction strategies.
	- Recomputation: combined with eviction we can Evict the memory that we can recompute later on with minimal costs.
	- Reuse allocations: Reuse allocated matrices and tensors via free lists
	- Physical operator selection: physical operators have a trade-off between memory and speed and size of intermediates.
- ##### Hardware Accelerators (General -> Specialized):
	- ###### GPU:
		-  Graphics Processing Unit, extensively used for deep learning training and scoring, has a much smaller l2-cache than a cpu and thus doesnt spend as much time on caching, High compute capacity.
		- Comprised of  Many processing Clusters and l2 caches. Each cluster contains Streaming multi-processors.
		- Each SMP contains cores made for different data types (FP64, FP32 etc...) and Tensor cores which are specific for 4x4 matrix multiplication and a matrix accumulator.
		- GPUs operate on single instruction multiple threads.
		- Improved models have sparsity exploitation.
		- Improved models have dedicated transformer cores that perform the inner calculations for transformers.
		- improved models have better links for better throughput
			- PCI express: Peripheral Component Interconnect Express which connects GPUs to a switch that is interconnected with other cpus and GPUs, throughput that ranges from 16-64GB/s over 16 lanes.
			- NVlink: Connect GPU-GPU and GPU-CPU  directly with throughput that ranges from 160-1800 GB/s
			- NVSwitch: Fully connected GPUs, each communicating at 300-13600 GB/s
	- ###### FPGA:
		-  Field programmable gate arrays is a customizable HW accelerator for perticular usecases in DL like prefiltering and compression.
		- Integrated circuit that allows configuring custom hardware designs
	- ###### ASIC: 
		- Application-specific Integrated Circuits, built physically only for specific applications of uses, contains a spectrum of chips for computer vision DL acceleration (like google TPUs)
		- There are general ASICs used for matrix multiply, convolution and activation functions like google TPU which has a matrix multiply tensor core (the one in the gpu) of 64k (256x256 8bit matrix multiply un)
		- and there are app specific ASICS used for Custom instructions for specific domains such as computer vision

