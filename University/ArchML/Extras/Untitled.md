# WS20/21
1.a. 
   - Data warehouse is a sub oriented integrated time variant non volatile collection of data
   - Data warehouse consists of sources that have heterogeneous data, a staging area where the data is processed and prepared for replication, transformations, a data warehouse that has raw and consolidated data, and data marts that hold specialized independent subsets of the data.
1.b. 
- ExamID, CourseID, StudentID, CountryID
- ExamID, Date, Grade.
- StudentID, Fname, Lname, Country
- CourseID, title, ECTS, catalog, Professor Fname, Professor Lname, PID.
2.a. 
- Cleaning: removing outliers, stemming etc...
- Blocking: making sure we dont enumerate every 2 possible pairs but narrow it down to similar pairs with LSH or jumping window on sorted values.
- Matching: Jaccard or Edit distance
- Clustering: Best cut algorithm or Random markov walks
2.b.
- Schema matching using Ngrams will be necessary to understand and match that Authors name is the same as Name in authors, and papertitle is the same as title in papers, the matching will give us  a logical correspondence and that logical correspondence will be used in schema mapping to create a more consistent mapping of our dataset (of one of the two sources with the other).
- Preprocessing steps involve schema matching/mapping, but also word stemming and removing capital letters and inconsistencies and abbreviations, combining first name and last name etc...
3.a. 
- Learned Imputation using iterative or ML algorithms and replcaing it with a fixed mode value.
- Y,Z
3.b.
- 35, 45
- Learned Imputation using iterative or ML algorithms and replcaing it with a fixed mean/median value.
3.c.
- FD: They use statistical tests to determine whether a dependency holds approximately rather than absolutely, Once a robust FD violation is detected, data can be corrected using methods such as value imputation.
- ID: if values of A (majority) are in B in another table -> possible FK-PK relationship
4.a. 
- data provenance is a log or history of the data from its origin along the lineage of transformations that occured on it until the output, it includes, metadata, log of lineage, annotations, source etc...
- Why prov: which rows in the origin contributed to which rows in the ouput.
- How prov: how each row in the origin contributed to each row in the output.
4.b.
- r1xs1 + r2xs3 + r3xs1, r2xs2, r2xs4
5.a.
- resource allocation is given according to different metrics of a combination of them, these metrics have constraints that shud not be violated like "maximum x dollars paid, minimize execution time".  another way is to focus on the scarcest (dominant utilization) resource such that we give out bundles accordingly.
5.b.
- N3, (32,64) , (16,64), (34, 120)
- N3, (32,64) , (16,64), (28, 88)
- N3,  (32,64) , (16,64), (20, 24)
- N1, (22,32) , (16,64), (20, 24)
- N1, (14, 0) , (16,64), (20, 24)
- N2,  (14, 0) , (0,0), (20, 24)
- N3 (14, 0) , (0,0), (4,8)
6.a.
- Map: Map original key value to same key different values (take all values of value for each key and put them together i assume)
- shuffling will put all X in same bucket, all Y in same bucket, all Z in same bucket, each reducer has a bucket to process.
- Reducing will go over each key and sum the values of values it has in our map.
- The initial aggregations (maps) can all be done locally and then submit.
6.b.
- Replication
- Lineage based recomputation
7.a.
- x, 2 T?? , y,1.1, T??? etc etc (count uniques in jumping window of 3)
- Similar
- similar
- idk what to put in T tho, a new timestamp or aggregate the tuples by adding their timestamps.
7.b.
- Lower the throughput of the source according to the bottleneck, this means that your queues will fill up before the bottleneckv (lossless)
- Throw away extra data when full (Lossy)
- perform pipeline parallelism on the data.
# WS21/22 v2
1.a.
- EO, ALO
- EO
- all
- ALO, EO
- AMO, EO
2.
- Each dimension has a hierarchy of features that have a minimum granuality to a maximum granuality (allows for multiple parallel granualities)
- A fact is the tuple at the finest granularity that contain one or multiple measures.
- A measure contain the actual measurements
2.c.
- BookingID, PlaneID, RouteID, dateID
- BookingID, ticket price, bag price, fname, lname
- PlaneID, type, seats, airline name
- Route, oneway, from name, from country, toname, to country
- DateID, DATE.
snowflake:
- BookingID, PlaneID, RouteID, dateID
- BookingID, ticket price, bag price, CID
- CID fname, lname
- PlaneID, type, seats, aid
- aid, name
- dateID date, month
- MonthID, year,
- Year
- RouteID, onway, fromID, toID
- AIRPORTID, name, country.
3.a.
- Data types through scans/samples and constraints (if no string exist, numerical, if no floating number int etc...)
- Primary-key foreign key through: if all values exist in another table as a primary key then theyre foriegn key (robust inclusion dependency)
- Semantic types: using DNN
4.a. 
- Missing randomly, can use mean/mode/median to impute or iteratibe algorithms.
- missing randomly in a subset of the data, can use mean/mode/median of subset to impute or iteratibe algorithms.
-  Missing randomly cause of the value, train biased model and remove bias to infer values.
6.a
-  Pay as you go without over-provisionning, pay what ur using and if u have fluctuations u have to have to have provisions.
- Economies at scale, paying a fixed value for IT management will be low cost at scale
- Elasticity, assuming perfect parallalization, you can scale up accordingly for speedup.
6.b
- workload balance, two tuples with same key might be processed by 2 workers and thus in the wrong order
- poor workload balance, one queue might get empty (needs stealing), ensures all same keys are processed by the same worker
7.a 
- select < 7 ->[ sliding window OR (select >3  - > tumbling window)]
7.b
- 4x3=12tuples per sec
- 6x6 = 36
8.a
- Map reduce -> map partitions using count, shuffle keys to same reducers, sum per reducer
- idk a
- caching save intermediates mapping incase reduce fails
- fault tolerance via lineage or replication 
- lazy evaluation and partition aware computation
# WISEM 24/25
#### Schema matching:
- Produces correspondence: matching
- consumes correspondence: mapping
- applies similarity: matching
- analyzes data: matching
- Utilizes constraints: both
- produces transformations: mapping
#### Data cleaning:
- Mean/MODE, min, categorical
- used to validate if theres violation and clean by replacing nulls with mean etc..
#### Cloud computing:
- one queue:
	- tuples of same key might be processed not in order
	- all workers utilized
- multiple queues:
	- workers can be not utilized
	- tuples of same key go to same worker, thus ensuring order.
### dist computation
- Map -> shuffle -. reduce
- Map: Data parallel Group by (A), min(b)
- Shuffle, each key lands in a bucket for a reducer
- Reducer Group by (A), min(b)


- Prepropagation  (do as much aggregation as possible in map so u dont send a lot of data to shuffle)
- Cache multi step maps to not read dataset twice
- Fuse multi step maps as one dag to not read dataset twice
- lazy eval


- Linear log recovery
- replication


### Parameter servers:
- One main Storage that has all model weights
- Many worker nodes that do computation
- Worker nodes pull weights from storage, compute minibatch gradients, push results into storage, storage aggregated all worker results and performs global weight update, and the cycle repeats.
- workers can be sync but one late worker may delay all processing
- workers can be async but stale weights may be read by some workers.