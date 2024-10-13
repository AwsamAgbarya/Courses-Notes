---
tags:
  - flashcards
---
What are the Driving factors for ML systems
?
1. Improved Algorithms and models
2. availability of large data
3. hardware and software advancements
<!--SR:!2024-10-16,4,270-->

What are the different scope of optimizations
?
1. eager interpretation
2. lazy expression evaluation
3. program compilation
<!--SR:!2024-10-16,4,270-->

Give 3 types of sparsity estimators
?
1. Naive: assume theres a uniform distribution of sparsity in your inputs and compute the sparsity of the output using min
2. Bitset estimator using MM
3. sample rows and columns and estimate the sparsity accordingly
4. create density maps of tiles.
5. Create matrix non-zero count (stores number of nnz and how many of those are alone)
<!--SR:!2024-10-15,3,250-->

Name and explain 3 types of operator re-writes:
?
1. CSE: Remove redundant sub-expressions that are calculated multiple times without any change or update in-between, start by replacing leaves and work bottom up.
2. Constant folding: After constant propagation, if certain expressions are comprised of mainly constants, compute the result and fold them into one constant
3. Branch removal: after constant propagation if certain conditions never fire then remove the conditions from dags and merge them.
<!--SR:!2024-10-13,1,230-->

How many plans do you need to consider in MMC optimization at layer N
?
you only have to consider 1 more than the layer below you, and the first layer starts at 0, meaning at layer N we consider N-1
<!--SR:!2024-10-16,4,270-->

It offen occurs that, even if we estimate size information, sizes become unknown/change during runtime, name three reasons why
?
- Control flow: Complex while loops and user defined functions.
- Data dependencies: Selection of size depending on values of data (dynamic selection)
- Changing dims and sparsity: Iterative feature selection workloads, same code with diff data
- API limitations: Pre-compiled scripts/programs
<!--SR:!2024-10-15,3,250-->

Name two runtime challenges that require us to have runtime adaptation
?
Unknown changes of size information
Operator runtime overhead  (We want to minimize complex operator overhead)
<!--SR:!2024-10-16,4,270-->

Explain Ahead of time vs Just in time compilation
?
- **Ahead-of-time compilation:** originates from languages like C where you have some overhead compilation process before running but then you get an optimized runtime. (Program compilation, inference program compilation and packaging)
- **Just-In-Time compilation:** Originates from languages like java where the startup time is not long, and if a method is executed a lot then it will be re-compiled and optimized to be faster (Lazy expression evaluation+optimization, Program recompilation)
<!--SR:!2024-10-15,3,250--> 

Explain operator fusion and the type 3 cases it deals with
?
Take simple operations that are bandwidth bound and memory intensive and produce simple alternatives that get you the same result by fusing multiple operators into one without having to materialize the intermediate results.
It works in cases exploiting *unecessary intermediate computation*, it also helps in *exploiting sparse data in complex operations* and merges an equation that uses the same variable multiple times using a *single pass*.
<!--SR:!2024-10-16,4,270-->

What does operator fusion help with during runtime
?
Avoiding the materlization of unecessary intermediates thus lower write/reads
avoid unecessary allocations
Specialization of operators
<!--SR:!2024-10-15,3,250-->

Describe roughly the process of operator fusion
?
Determine Plan partitions by separating the plan DAG into independent blocks -> Peform candidate selection and choose interesting points to consider -> derive the optimal plan for each candidate using  a cost based pruning of subplans that violate the upperbound (not optimal).
<!--SR:!2024-10-16,4,270-->

Explain 3 parallelization types
?
SIMD process the same operation over multiple elements at a time (instruction level data parallelism)
MISD process singular data over multiple instructions through a pipeline.
MIMD perform multiple instructions on different elements of data in parallel (multi-core/ multi-thread /multi worker)
bonus: SPMD Which is similar to SIMD but distributed on a program level (same program performed on multiple data in a distributed collection)
<!--SR:!2024-10-16,4,270-->

What do the Map and reduce functions do in MapReduce
?
Map:  Operations which takes in a key/value pair and produces a set of temporary/intermediate key/value pairs according to specification
Reduce: Operations which take in the intermediates of the Map, and reduce it to the result using some specified merging computation
<!--SR:!2024-10-16,4,270-->

WHat is partitioned hashing in an RDD and how what does it help with? give an example.
?
a hash partition takes in data (usually by the map function) and uses a hash function on the keys to partition the data into N different partitions (N being the number of reducers).
This helps in many operators like a joint operator where we no longer have to consider every single partition with every other one, instead we only consider partitions with matching keys.
<!--SR:!2024-10-16,4,270-->

What are data-parallel parameter servers
?
Parameter servers contain the global weights of the model while the workers/nodes (it has N different workers) contain a chunk of the data/minibatches/reshuffled data. The workers pull in the current model at each iteration, perform gradient computation on the current minibatch they have and return the change of weights back into the parameter server which then does a global aggregation using different strategies to do a global weight update.
<!--SR:!2024-10-16,4,270-->

Name 3 update strategies for data-parallel parameter servers
?
Bulk sync parallel: wait for all workers and update weights once theyre all done, doesnt utilize the hardware properly because it waits for stragglers.
Async parallel: dont wait for anyone and compute updates immediately, utilizes hardware but also has stale and dirty reads.
Sync with backup: Only if k /N workers finish their job do we aggregate and do a global update.
<!--SR:!2024-10-16,4,270-->

Name 3 data partitioning types in data-parallel parameter servers
?
Disjoint continuous sets
Disjoint round robin
disjoint random
overlap shuffle
<!--SR:!2024-10-16,4,270-->

Name 2 advantages and disadvantages of having larger mini-batches
?
1. Bigger batches reduces the number of steps it takes to converge
2. Bigger batches have less variance in the resulting gradients.
3. Bigger batches reduce the communication overhead for many small batches.
1. Bigger batches are more expensive to compute
2. Bigger batches computation might not fit in memory of each worker.
<!--SR:!2024-10-16,4,270-->

Name 3 Matrix formats with their respective size estimation.
?
Dense representation O(mn)
COO O(3* nnz)
CSR O(m+ 2* nnz)
<!--SR:!2024-10-16,4,270-->

Name 4 methods that speed up data acess
?
1. SHared scanning/batching: Scan the same variable once and use it multiple computations by batching the multiple computations.
2. Indexing: Using B-trees you can query data faster
3. Pre-fetching: you can pre-fetch data while your computation is still ongoing
4. Buffers and caching: data can be cached, evicted and recomputed according to its size information and when we dont want to use it anymore.
<!--SR:!2024-10-15,3,250-->

Name 3 Lossy compression methods
?
Quantization
Low precision computation + numerically stable accumulation
stoachastic rounding
sparsification.
<!--SR:!2024-10-16,4,270-->

Name 3 Lossless compression methods
?
Block level general purpose compression
Compressed linear algebra (columns)
Tuple oriented compression
<!--SR:!2024-10-16,4,270-->

Explain the three steps of Compressed linear Algebra method
?
1. Classify compressable columns by selecting a strategy for each one
2. Columns are then grouped with each to exploit linear dependencies
3. The compression scheme is then applied per group
<!--SR:!2024-10-16,4,270-->

How does hardware handle memory constraints, name 3 methods
?
Live variable analysis: evict variables from memory immediately after we are done with them
Recomputation: if memory has variables that we need but are not costly to compute then we can recompute them in later stages.
Physical operator selection: select different operators that trade memory efficient and speed/size of intermediates.
<!--SR:!2024-10-13,1,230-->

Name three ways to validate data
?
Check expected shape, min and max values
Check whether the distribution of your data matches the expected histogram values
check whether certain features are missing/ not frequent enough in ur data
<!--SR:!2024-10-16,4,270-->

Name 3 data corruption causes
?
Human error/judgment or lazyness
Inconsistencies and changes of processes over time
unreliable HW due to harsh environments
<!--SR:!2024-10-15,3,250-->

Name and explain 3 feature engineering methods
?
Recoding: map each unique value to an integer
Feature hashing: hash every unique value into a number that is then stored as modulo N such that we can control N
Binning: Use quantization methods to store the data into bins (equi-width or equi-height)
one-hot encoding: use unique values as columns and store 1 bit indicating whether each tuple has that value or not.
<!--SR:!2024-10-15,3,250-->

Explain bag of words, N-grams and word embeddings
?
Bag of words stores the counts of each token
N-grams is a bag of words for seuqneces of characters with up to N length
Word embeddings are learned semantic preserving vector representations of tokens/words using the prediction of context from a word/ word from a context.
<!--SR:!2024-10-16,4,270-->

Name different Normalization methods and the differences between them,
?
Standardziation: densifies the data but gives us mean 0 and variance 1
Min-max Normalization: doesnt densify the data by keeping 0s at 0
<!--SR:!2024-10-16,4,270-->

What is data trimming and how do we do it
?
Trimming the data means removing outliers from the data usually lying on the tails of the features, this cna be done through quantiles/precentiles or by calculating furthes points from the mean.
<!--SR:!2024-10-16,4,270-->

How do we replace missing values
?
Can  be replaced by mean/mode/ logical default
Can be replaced using the mice technique of training a model to predict those values from the non missing tuples (if missing at random)
Can be used to train a biased model and with the use of trial and error we introduce biases and validate which model performs the best on the test set (to discover which bias is in our dataset, this is done when its not missing at random)
<!--SR:!2024-10-16,4,270-->

WHat is model selection/hyper parameter tuning, name 3 methods to do this.
?
model selection: Given a dataset and ML task Select the model (type) that performs best.
hyper-parameter tuning: Given a model and dataset, find best hyper parameter values.
Methods to explore the solution space include:
Basic grid search (explore all discretized options)
Simulated annealing (Introduce a temperature variable that lets you explore a lot at the start but narrows down over time)
Recursive random search (Sample random points from the grid, pick the region of the grid with the best performance then sample in that grid and repeat the process)
<!--SR:!2024-10-16,4,270-->

What is neural architecture search
?
its the automatic search for an appropriate NN architecture using defined building blocks to avoid manual exploration.
We need to consider our search strategies like evolutionary algorithms, RNNs and bayesian optimization as well as the objective.
If we happen to have multiple objectives then we can linearlize them, look at the pareto curve or set worse cases using constraints.
<!--SR:!2024-10-16,4,270-->

What are issues we need to be careful of when we train our model on our dataset
?
Overfitting on an under-determined system
Data advantage leakage that gives the training an upper hand
 Covariance shift in the distribution of features that does not match or represent real world data
 Concept drift, i.e gradual shift in statistical properties.
<!--SR:!2024-10-15,3,250-->

Name 3 sources of bias
?
- **Selection Bias:** difference in data availability/selection and the current environment/context.
- **Sample Bias:** collected data not representative of application
- **Confirmation Bias:** if the engineers had certain biased hypotheses, they might not investigate any further reasoning if it the results match it.
- **NMAR Bias:** Missing values based on the value itself which might not represent the data properly.
<!--SR:!2024-10-16,4,270-->

What is fairness and how do we ensure it
?
its to Validate and ensure a 'fair judgment' with regard to sensitive features (unbiased) that should not contribute to the output.
we can do this by using constrains to enforce certain properties and smoothness
We can also do this by enforcing statistical properties of different groups to ensure euqla outcome across groups.
<!--SR:!2024-10-16,4,270-->

Name 4 different explanation methods
?
Occlusion based explanation: run a mask across an image convolutionally  and re-run the forward pass each time calculating the difference that mask makes from the original output and produce a heatmap of the most contributing pixels.
Saliency maps: compute class gradients w.r.t the input image
Slices: Find the biggest Data slice with a certain feature such that the model performs significantly worse than average on
Shapley values:  Compute the additive feature contribution that lead from the input to the output of the model while ensuring consistency
<!--SR:!2024-10-16,4,270-->

Name 4 ways to optimize a model that has been deployed.
?
Batching multiple requests together can save on computation
Quantization of requests before sending it can save energy
Result caching of the most frequent requests
Model distillation for compression of model weights
Specialization of the model into a smaller domain
inference program compilation.
Vectorizing the model.
<!--SR:!2024-10-16,4,270-->


Explain how bayesian Optimization works
?
Using a Gaussian process which models the function space (of our hyperparameter), we can formulate an aquisition function that balances exploration (using the variance/uncertainty at a certain point) and the exploitatio (using the mean/evidence at a certain point)
<!--SR:!2024-10-16,4,270-->

Why does low FP help a model during inference
?
Reduce bandwidth requirements
increased instruction parallelism
Reduce energy consumption
<!--SR:!2024-10-16,4,270-->