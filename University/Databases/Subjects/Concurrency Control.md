---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Schedules ^DgCqyTl6

* We provide concurrency control in order to improve utilization of resource and apply fairness to users
* Transactions contain multiple reads and writes to manipulate data and end with commit or abort
* ACID properties:








* A schedule is a sequence of operations from multiple transactions. We try to make schedule have
  no conflict within their transactions to ensure Isolation.
* A schedule is considered         operations from different TX are not interleaved (sequential TX)
* A schedule is considered                 if its results equal to a serial schedule of the same TXs

* Two operations are                if one of the following conditions apply:



* Two operations are                     if all these rules apply:



* Two schedules are Conflict-equivalent if they work on the same transactions and we can turn one
   into the other with a series of swaps of non-conflicting adjacent operation

* A schedule is Conflict-serializable if a conflict-equivalent serial schedule exists, i.e in this equivalent
serial schedule the conflicting operations execute in the original order and the rest doesnt matter

* Advantages of Conflict-Serializability:
1) Consistency: transactions’ outcomes correspond to the sequence in which they were carried out.
2) Correctness: Regardless of the order transactions are executed correctly.
3) Enhanced Concurrency: concurrent execution of operations without conflict enhances concurrency

* Disadvantages of Conflict-Serializability:
1) Complexity: an be complex to implement, especially in large and complex databases
2) Limited Concurrency: can limit the concurrency because it may delay some TX to avoid conflict
3) Increased Overhead: requires overhead to maintain order of the transactions and ensure non-conflict

* Precedence Graph:
1) Make nodes V = {T1, T2,T3……….Tn}
2) An edge is drawn from node Tj to Tk if one of the operations in Tj appears in the schedule
   before some conflicting operation in Tk
3) If no cycles are in graph, that schedule is conflict-serializable
 ^7wT2bTFt

1) Atomicity: Either all operations of a transaction complete or none of them complete, no transaction is left half finished. ^PO576POq

2) Consistency: A transaction that is applied to a consistent database produces a consistent database. ^LbLuyVUD

3) Isolation: A transaction executes as if it is the only transaction running in the system.  ^Eic61sNJ

4) Durability: The effects of committed transactions are reflected in the database even after failures ^SUGNFnAq

* Interleaved transactions are transactions that work on the same attributes.
* Dirty read is when a second transaction reads the effects of a first transaction before the first aborts, thus
  causing its effect to carry on even when aborted
* Lost Update is when a second transaction reads an old value (before the first transaction adjust it) of an attribute and
  commits its changes to the old value thus rendering the first transaction useless. ^f8Hpm7lL

SERIAL ^n654dJ7r

SERIALIZABLE ^Lx7EaXv6

CONFLICTING ^iaah1r6X

1) They belong to the same transaction
2) They operate on the same data item and at least one of them is a write ^x5agIfNa

NON-CONFLICTING ^j2uuuMQm

1) They belong to different transactions
2) They do not operate the same data or all of them are Reads ^2I4vVXZu

* Recoverable Schedules: Commit of the write transaction Tj must be carried out before the commit of the read transaction Ti
* Avoids cascading resets: It is only read when the changes to the writing transaction Tj have been committed
* Strict Schedule: a schedule in which the order of transactions is preserved exactly as specified by the program or user.
                   (no reading from or overwriting of data items before a commit) ^9fffcMTy

Locking ^3rnx1VbE

* Locking is Enforcement of serializability by locking database elements, theyre requested by the TX
* There are two types of locks, read which is sharable, and write which is exclusive!


* Dead locks: are the denial of locks due to the existence of an unreleased shared lock

* Two Phase locking (serializable): Once TX starts to release locks, it cannot rquest new locks
  Consists of growing phase where it has locks, and shrinking phase where its on cooldown for requests


* Problem of cascading aborts is when one transaction does changes to attribute A, then another 
  transaction reads those changes, if T1 aborts, T2 also has to abort due to it having information
  gained by T1.
* Strict 2PL: Only release locks after Abort/commit to ensure recoverable schedules

* Phantom Read: the same query produces different output at different times.
  Example: One tuple is added to the table while another transaction is operating on smthn based off
           off of tuples, this occurs because the addition of a tuple only needs a write lock on that
           tuple itself, thus General locks do not help

* Lock Granularities: Lock database elements in a hierarchy to cope with different granularities
* Introduce intention locks on the current element if the element is below in the hierarchy
* Intention locks IS and IX are compatible with each other, and only S is compatible with IS
* Latches are physical locks that seperate Threads to protect in-memory data structures

* Optimizations to lock manager:
  1) try to inherit high-level locks from the previous transaction that executed in the same thread
  2) Thread-per-data partition rather than thread-per-transaction
  3) Private lock table per transaction simplifies code paths for requesting and releasing locks from
     global lock table
  4) Allow transactions to release their locks as soon as they receive allocated space in buffer pool
     for commit log record

* How to deal with deadlocks?
  1) Abort transaction if it is been waiting for too long. How to pick timeout parameter?
  2) Roll back transaction if waits-for graph contains cycle

* Some applications can handle a bit of dirtyness as a trade off for response time:
1) Dirty read
2) Fuzzy Read: T1 reads data, T2 changes/deletes that data and commits, T2 reads same data and
               finds different value
3) Phantom: T1 searches using a < X < b, T2 modifies items in that range, T1 searches and finds
             different values in that range.

* Isolation levels: 
1) READ UNCOMMITTED: can read data that has been written by non-committed transactions.
    • Allows dirty reads, fuzzy reads, phantoms
2) READ COMMITTED: only read data that have been updated by committed transactions.
    • Does not allow dirty reads, Allows fuzzy reads, phantoms
3) REPEATABLE READ: Reads to individual items are repeatable.
    • Does not allow dirty reads or fuzzy reads, but Allows phantoms
4) SERIALIZABLE: Reads by predicate search are repeatable.
    • Does not allow dirty reads, fuzzy reads, phantoms

* Optimistic approaches hope that conflict will be rare, if they do we fix things, If something goes
wrong, abort and restart transaction

*Timestamp protocol: for each item, the order that theyre accessed by conflicting operations does not 
violate the ordering, W_TS(X) is largest TS for writing on attribute X and R_TS(X) is for reading.
TS(T) is the timestamp in which the transaction entered the system
1) When T wants to Write X, if RTS(X) > T(S) (Someone has read old value) abort, if WTS(X) > T(s)
  then skip because it will be overwritten, else execute and update timestamps
2) When T wants to Read x, if WTS(X) > T(s) (someone overwrote old value) then abort, else execute
3) if two conflicting operations occur in wrong order, it aborts the latter

*MCC: Each transaction operates on private copy of data, copies are merged later ^oBFh5tLo

S(E)= request shared lock on E          X(E)= request exclusive lock on E          U(E)= release any lock on E ^2evTttcR

* NO compatibility between any two types of locks except shared with shared ^dvdBmL4t

* Dead locks can still happen
* Does not guarantee recoverable schedule ^kwK5q4IW

conflict ^p7wMHCpz

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.18",
	"elements": [
		{
			"type": "text",
			"version": 1234,
			"versionNonce": 1103300352,
			"isDeleted": false,
			"id": "DgCqyTl6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -42.484288659113744,
			"y": -470.8596741529883,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 129.9485626220703,
			"height": 35,
			"seed": 1409911659,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Schedules",
			"rawText": "Schedules",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Schedules",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 1991,
			"versionNonce": 1964304640,
			"isDeleted": false,
			"id": "7wT2bTFt",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -496.42944160316733,
			"y": -416.4087515182106,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1037.8388671875,
			"height": 1150,
			"seed": 1480624677,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* We provide concurrency control in order to improve utilization of resource and apply fairness to users\n* Transactions contain multiple reads and writes to manipulate data and end with commit or abort\n* ACID properties:\n\n\n\n\n\n\n\n\n* A schedule is a sequence of operations from multiple transactions. We try to make schedule have\n  no conflict within their transactions to ensure Isolation.\n* A schedule is considered         operations from different TX are not interleaved (sequential TX)\n* A schedule is considered                 if its results equal to a serial schedule of the same TXs\n\n* Two operations are                if one of the following conditions apply:\n\n\n\n* Two operations are                     if all these rules apply:\n\n\n\n* Two schedules are Conflict-equivalent if they work on the same transactions and we can turn one\n   into the other with a series of swaps of non-conflicting adjacent operation\n\n* A schedule is Conflict-serializable if a conflict-equivalent serial schedule exists, i.e in this equivalent\nserial schedule the conflicting operations execute in the original order and the rest doesnt matter\n\n* Advantages of Conflict-Serializability:\n1) Consistency: transactions’ outcomes correspond to the sequence in which they were carried out.\n2) Correctness: Regardless of the order transactions are executed correctly.\n3) Enhanced Concurrency: concurrent execution of operations without conflict enhances concurrency\n\n* Disadvantages of Conflict-Serializability:\n1) Complexity: an be complex to implement, especially in large and complex databases\n2) Limited Concurrency: can limit the concurrency because it may delay some TX to avoid conflict\n3) Increased Overhead: requires overhead to maintain order of the transactions and ensure non-conflict\n\n* Precedence Graph:\n1) Make nodes V = {T1, T2,T3……….Tn}\n2) An edge is drawn from node Tj to Tk if one of the operations in Tj appears in the schedule\n   before some conflicting operation in Tk\n3) If no cycles are in graph, that schedule is conflict-serializable\n",
			"rawText": "* We provide concurrency control in order to improve utilization of resource and apply fairness to users\n* Transactions contain multiple reads and writes to manipulate data and end with commit or abort\n* ACID properties:\n\n\n\n\n\n\n\n\n* A schedule is a sequence of operations from multiple transactions. We try to make schedule have\n  no conflict within their transactions to ensure Isolation.\n* A schedule is considered         operations from different TX are not interleaved (sequential TX)\n* A schedule is considered                 if its results equal to a serial schedule of the same TXs\n\n* Two operations are                if one of the following conditions apply:\n\n\n\n* Two operations are                     if all these rules apply:\n\n\n\n* Two schedules are Conflict-equivalent if they work on the same transactions and we can turn one\n   into the other with a series of swaps of non-conflicting adjacent operation\n\n* A schedule is Conflict-serializable if a conflict-equivalent serial schedule exists, i.e in this equivalent\nserial schedule the conflicting operations execute in the original order and the rest doesnt matter\n\n* Advantages of Conflict-Serializability:\n1) Consistency: transactions’ outcomes correspond to the sequence in which they were carried out.\n2) Correctness: Regardless of the order transactions are executed correctly.\n3) Enhanced Concurrency: concurrent execution of operations without conflict enhances concurrency\n\n* Disadvantages of Conflict-Serializability:\n1) Complexity: an be complex to implement, especially in large and complex databases\n2) Limited Concurrency: can limit the concurrency because it may delay some TX to avoid conflict\n3) Increased Overhead: requires overhead to maintain order of the transactions and ensure non-conflict\n\n* Precedence Graph:\n1) Make nodes V = {T1, T2,T3……….Tn}\n2) An edge is drawn from node Tj to Tk if one of the operations in Tj appears in the schedule\n   before some conflicting operation in Tk\n3) If no cycles are in graph, that schedule is conflict-serializable\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* We provide concurrency control in order to improve utilization of resource and apply fairness to users\n* Transactions contain multiple reads and writes to manipulate data and end with commit or abort\n* ACID properties:\n\n\n\n\n\n\n\n\n* A schedule is a sequence of operations from multiple transactions. We try to make schedule have\n  no conflict within their transactions to ensure Isolation.\n* A schedule is considered         operations from different TX are not interleaved (sequential TX)\n* A schedule is considered                 if its results equal to a serial schedule of the same TXs\n\n* Two operations are                if one of the following conditions apply:\n\n\n\n* Two operations are                     if all these rules apply:\n\n\n\n* Two schedules are Conflict-equivalent if they work on the same transactions and we can turn one\n   into the other with a series of swaps of non-conflicting adjacent operation\n\n* A schedule is Conflict-serializable if a conflict-equivalent serial schedule exists, i.e in this equivalent\nserial schedule the conflicting operations execute in the original order and the rest doesnt matter\n\n* Advantages of Conflict-Serializability:\n1) Consistency: transactions’ outcomes correspond to the sequence in which they were carried out.\n2) Correctness: Regardless of the order transactions are executed correctly.\n3) Enhanced Concurrency: concurrent execution of operations without conflict enhances concurrency\n\n* Disadvantages of Conflict-Serializability:\n1) Complexity: an be complex to implement, especially in large and complex databases\n2) Limited Concurrency: can limit the concurrency because it may delay some TX to avoid conflict\n3) Increased Overhead: requires overhead to maintain order of the transactions and ensure non-conflict\n\n* Precedence Graph:\n1) Make nodes V = {T1, T2,T3……….Tn}\n2) An edge is drawn from node Tj to Tk if one of the operations in Tj appears in the schedule\n   before some conflicting operation in Tk\n3) If no cycles are in graph, that schedule is conflict-serializable\n",
			"lineHeight": 1.25,
			"baseline": 1143
		},
		{
			"type": "text",
			"version": 164,
			"versionNonce": 1103767296,
			"isDeleted": false,
			"id": "PO576POq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -474.2147651576443,
			"y": -337.7224381172548,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 976.4497680664062,
			"height": 20,
			"seed": 1169557509,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "1) Atomicity: Either all operations of a transaction complete or none of them complete, no transaction is left half finished.",
			"rawText": "1) Atomicity: Either all operations of a transaction complete or none of them complete, no transaction is left half finished.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Atomicity: Either all operations of a transaction complete or none of them complete, no transaction is left half finished.",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 111,
			"versionNonce": 881838336,
			"isDeleted": false,
			"id": "LbLuyVUD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -474.21476569147393,
			"y": -317.7224387608275,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 844.1776733398438,
			"height": 20,
			"seed": 126919301,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "2) Consistency: A transaction that is applied to a consistent database produces a consistent database.",
			"rawText": "2) Consistency: A transaction that is applied to a consistent database produces a consistent database.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2) Consistency: A transaction that is applied to a consistent database produces a consistent database.",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 126,
			"versionNonce": 1944930048,
			"isDeleted": false,
			"id": "Eic61sNJ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -474.2147655937069,
			"y": -297.722438078081,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 732.353271484375,
			"height": 20,
			"seed": 1505184741,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "3) Isolation: A transaction executes as if it is the only transaction running in the system. ",
			"rawText": "3) Isolation: A transaction executes as if it is the only transaction running in the system. ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3) Isolation: A transaction executes as if it is the only transaction running in the system. ",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 131,
			"versionNonce": 28223744,
			"isDeleted": false,
			"id": "SUGNFnAq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -474.2147654839637,
			"y": -277.7224387517617,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 833.1536254882812,
			"height": 20,
			"seed": 2117091013,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "4) Durability: The effects of committed transactions are reflected in the database even after failures",
			"rawText": "4) Durability: The effects of committed transactions are reflected in the database even after failures",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "4) Durability: The effects of committed transactions are reflected in the database even after failures",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 523,
			"versionNonce": 883713792,
			"isDeleted": false,
			"id": "f8Hpm7lL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -494.3664878711572,
			"y": -246.5865664455797,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1006.4818115234375,
			"height": 100,
			"seed": 391732203,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "* Interleaved transactions are transactions that work on the same attributes.\n* Dirty read is when a second transaction reads the effects of a first transaction before the first aborts, thus\n  causing its effect to carry on even when aborted\n* Lost Update is when a second transaction reads an old value (before the first transaction adjust it) of an attribute and\n  commits its changes to the old value thus rendering the first transaction useless.",
			"rawText": "* Interleaved transactions are transactions that work on the same attributes.\n* Dirty read is when a second transaction reads the effects of a first transaction before the first aborts, thus\n  causing its effect to carry on even when aborted\n* Lost Update is when a second transaction reads an old value (before the first transaction adjust it) of an attribute and\n  commits its changes to the old value thus rendering the first transaction useless.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Interleaved transactions are transactions that work on the same attributes.\n* Dirty read is when a second transaction reads the effects of a first transaction before the first aborts, thus\n  causing its effect to carry on even when aborted\n* Lost Update is when a second transaction reads an old value (before the first transaction adjust it) of an attribute and\n  commits its changes to the old value thus rendering the first transaction useless.",
			"lineHeight": 1.25,
			"baseline": 94
		},
		{
			"type": "text",
			"version": 103,
			"versionNonce": 133269760,
			"isDeleted": false,
			"id": "n654dJ7r",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -230.25592362204713,
			"y": -90.878989265629,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 75.19993591308594,
			"height": 25,
			"seed": 25394475,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "SERIAL",
			"rawText": "SERIAL",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SERIAL",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 1351059200,
			"isDeleted": false,
			"id": "Lx7EaXv6",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -228.31580287137376,
			"y": -64.87741975494998,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 155.15988159179688,
			"height": 25,
			"seed": 1614279595,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "SERIALIZABLE",
			"rawText": "SERIALIZABLE",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "SERIALIZABLE",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 47737088,
			"isDeleted": false,
			"id": "iaah1r6X",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -275.72494463527397,
			"y": -14.045286623659024,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 143.15989685058594,
			"height": 25,
			"seed": 1136108331,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CONFLICTING",
			"rawText": "CONFLICTING",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "CONFLICTING",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 122,
			"versionNonce": 67020544,
			"isDeleted": false,
			"id": "x5agIfNa",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -469.03265597846695,
			"y": 10.954713513068029,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 775.6392211914062,
			"height": 50,
			"seed": 787720197,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) They belong to the same transaction\n2) They operate on the same data item and at least one of them is a write",
			"rawText": "1) They belong to the same transaction\n2) They operate on the same data item and at least one of them is a write",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) They belong to the same transaction\n2) They operate on the same data item and at least one of them is a write",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 121,
			"versionNonce": 1038305536,
			"isDeleted": false,
			"id": "j2uuuMQm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -277.15678974616026,
			"y": 85.70738681302967,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 191.65985107421875,
			"height": 25,
			"seed": 2084848427,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "NON-CONFLICTING",
			"rawText": "NON-CONFLICTING",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "NON-CONFLICTING",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 185,
			"versionNonce": 2073151232,
			"isDeleted": false,
			"id": "2I4vVXZu",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -469.03265640810076,
			"y": 108.59124826480928,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 658.8792724609375,
			"height": 50,
			"seed": 1253088901,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) They belong to different transactions\n2) They do not operate the same data or all of them are Reads",
			"rawText": "1) They belong to different transactions\n2) They do not operate the same data or all of them are Reads",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) They belong to different transactions\n2) They do not operate the same data or all of them are Reads",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "text",
			"version": 190,
			"versionNonce": 345123072,
			"isDeleted": false,
			"id": "9fffcMTy",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -495.9674061324004,
			"y": 743.1490172882901,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1022.9459228515625,
			"height": 80,
			"seed": 1491869579,
			"groupIds": [],
			"frameId": "fgMQFMIBF88HENUer2F3v",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "* Recoverable Schedules: Commit of the write transaction Tj must be carried out before the commit of the read transaction Ti\n* Avoids cascading resets: It is only read when the changes to the writing transaction Tj have been committed\n* Strict Schedule: a schedule in which the order of transactions is preserved exactly as specified by the program or user.\n                   (no reading from or overwriting of data items before a commit)",
			"rawText": "* Recoverable Schedules: Commit of the write transaction Tj must be carried out before the commit of the read transaction Ti\n* Avoids cascading resets: It is only read when the changes to the writing transaction Tj have been committed\n* Strict Schedule: a schedule in which the order of transactions is preserved exactly as specified by the program or user.\n                   (no reading from or overwriting of data items before a commit)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Recoverable Schedules: Commit of the write transaction Tj must be carried out before the commit of the read transaction Ti\n* Avoids cascading resets: It is only read when the changes to the writing transaction Tj have been committed\n* Strict Schedule: a schedule in which the order of transactions is preserved exactly as specified by the program or user.\n                   (no reading from or overwriting of data items before a commit)",
			"lineHeight": 1.25,
			"baseline": 74
		},
		{
			"type": "frame",
			"version": 1792,
			"versionNonce": 1899423488,
			"isDeleted": false,
			"id": "fgMQFMIBF88HENUer2F3v",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -503.27459185284374,
			"y": -470.8596742409659,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 1039.816207,
			"height": 1297.5212802316412,
			"seed": 2024271019,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707838544651,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#949494"
				}
			},
			"name": "CC"
		},
		{
			"type": "text",
			"version": 1358,
			"versionNonce": 1919224064,
			"isDeleted": false,
			"id": "3rnx1VbE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -56.28863036014229,
			"y": 896.7541207602474,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 93.21238708496094,
			"height": 35,
			"seed": 1014940331,
			"groupIds": [],
			"frameId": "5jHjrEGA1gyCAeexN6OpQ",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Locking",
			"rawText": "Locking",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Locking",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 5169,
			"versionNonce": 420218624,
			"isDeleted": false,
			"id": "oBFh5tLo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -514.9373160145219,
			"y": 950.4616231720825,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1032.73876953125,
			"height": 1650,
			"seed": 1216820555,
			"groupIds": [],
			"frameId": "5jHjrEGA1gyCAeexN6OpQ",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Locking is Enforcement of serializability by locking database elements, theyre requested by the TX\n* There are two types of locks, read which is sharable, and write which is exclusive!\n\n\n* Dead locks: are the denial of locks due to the existence of an unreleased shared lock\n\n* Two Phase locking (serializable): Once TX starts to release locks, it cannot rquest new locks\n  Consists of growing phase where it has locks, and shrinking phase where its on cooldown for requests\n\n\n* Problem of cascading aborts is when one transaction does changes to attribute A, then another \n  transaction reads those changes, if T1 aborts, T2 also has to abort due to it having information\n  gained by T1.\n* Strict 2PL: Only release locks after Abort/commit to ensure recoverable schedules\n\n* Phantom Read: the same query produces different output at different times.\n  Example: One tuple is added to the table while another transaction is operating on smthn based off\n           off of tuples, this occurs because the addition of a tuple only needs a write lock on that\n           tuple itself, thus General locks do not help\n\n* Lock Granularities: Lock database elements in a hierarchy to cope with different granularities\n* Introduce intention locks on the current element if the element is below in the hierarchy\n* Intention locks IS and IX are compatible with each other, and only S is compatible with IS\n* Latches are physical locks that seperate Threads to protect in-memory data structures\n\n* Optimizations to lock manager:\n  1) try to inherit high-level locks from the previous transaction that executed in the same thread\n  2) Thread-per-data partition rather than thread-per-transaction\n  3) Private lock table per transaction simplifies code paths for requesting and releasing locks from\n     global lock table\n  4) Allow transactions to release their locks as soon as they receive allocated space in buffer pool\n     for commit log record\n\n* How to deal with deadlocks?\n  1) Abort transaction if it is been waiting for too long. How to pick timeout parameter?\n  2) Roll back transaction if waits-for graph contains cycle\n\n* Some applications can handle a bit of dirtyness as a trade off for response time:\n1) Dirty read\n2) Fuzzy Read: T1 reads data, T2 changes/deletes that data and commits, T2 reads same data and\n               finds different value\n3) Phantom: T1 searches using a < X < b, T2 modifies items in that range, T1 searches and finds\n             different values in that range.\n\n* Isolation levels: \n1) READ UNCOMMITTED: can read data that has been written by non-committed transactions.\n    • Allows dirty reads, fuzzy reads, phantoms\n2) READ COMMITTED: only read data that have been updated by committed transactions.\n    • Does not allow dirty reads, Allows fuzzy reads, phantoms\n3) REPEATABLE READ: Reads to individual items are repeatable.\n    • Does not allow dirty reads or fuzzy reads, but Allows phantoms\n4) SERIALIZABLE: Reads by predicate search are repeatable.\n    • Does not allow dirty reads, fuzzy reads, phantoms\n\n* Optimistic approaches hope that conflict will be rare, if they do we fix things, If something goes\nwrong, abort and restart transaction\n\n*Timestamp protocol: for each item, the order that theyre accessed by conflicting operations does not \nviolate the ordering, W_TS(X) is largest TS for writing on attribute X and R_TS(X) is for reading.\nTS(T) is the timestamp in which the transaction entered the system\n1) When T wants to Write X, if RTS(X) > T(S) (Someone has read old value) abort, if WTS(X) > T(s)\n  then skip because it will be overwritten, else execute and update timestamps\n2) When T wants to Read x, if WTS(X) > T(s) (someone overwrote old value) then abort, else execute\n3) if two conflicting operations occur in wrong order, it aborts the latter\n\n*MCC: Each transaction operates on private copy of data, copies are merged later",
			"rawText": "* Locking is Enforcement of serializability by locking database elements, theyre requested by the TX\n* There are two types of locks, read which is sharable, and write which is exclusive!\n\n\n* Dead locks: are the denial of locks due to the existence of an unreleased shared lock\n\n* Two Phase locking (serializable): Once TX starts to release locks, it cannot rquest new locks\n  Consists of growing phase where it has locks, and shrinking phase where its on cooldown for requests\n\n\n* Problem of cascading aborts is when one transaction does changes to attribute A, then another \n  transaction reads those changes, if T1 aborts, T2 also has to abort due to it having information\n  gained by T1.\n* Strict 2PL: Only release locks after Abort/commit to ensure recoverable schedules\n\n* Phantom Read: the same query produces different output at different times.\n  Example: One tuple is added to the table while another transaction is operating on smthn based off\n           off of tuples, this occurs because the addition of a tuple only needs a write lock on that\n           tuple itself, thus General locks do not help\n\n* Lock Granularities: Lock database elements in a hierarchy to cope with different granularities\n* Introduce intention locks on the current element if the element is below in the hierarchy\n* Intention locks IS and IX are compatible with each other, and only S is compatible with IS\n* Latches are physical locks that seperate Threads to protect in-memory data structures\n\n* Optimizations to lock manager:\n  1) try to inherit high-level locks from the previous transaction that executed in the same thread\n  2) Thread-per-data partition rather than thread-per-transaction\n  3) Private lock table per transaction simplifies code paths for requesting and releasing locks from\n     global lock table\n  4) Allow transactions to release their locks as soon as they receive allocated space in buffer pool\n     for commit log record\n\n* How to deal with deadlocks?\n  1) Abort transaction if it is been waiting for too long. How to pick timeout parameter?\n  2) Roll back transaction if waits-for graph contains cycle\n\n* Some applications can handle a bit of dirtyness as a trade off for response time:\n1) Dirty read\n2) Fuzzy Read: T1 reads data, T2 changes/deletes that data and commits, T2 reads same data and\n               finds different value\n3) Phantom: T1 searches using a < X < b, T2 modifies items in that range, T1 searches and finds\n             different values in that range.\n\n* Isolation levels: \n1) READ UNCOMMITTED: can read data that has been written by non-committed transactions.\n    • Allows dirty reads, fuzzy reads, phantoms\n2) READ COMMITTED: only read data that have been updated by committed transactions.\n    • Does not allow dirty reads, Allows fuzzy reads, phantoms\n3) REPEATABLE READ: Reads to individual items are repeatable.\n    • Does not allow dirty reads or fuzzy reads, but Allows phantoms\n4) SERIALIZABLE: Reads by predicate search are repeatable.\n    • Does not allow dirty reads, fuzzy reads, phantoms\n\n* Optimistic approaches hope that conflict will be rare, if they do we fix things, If something goes\nwrong, abort and restart transaction\n\n*Timestamp protocol: for each item, the order that theyre accessed by conflicting operations does not \nviolate the ordering, W_TS(X) is largest TS for writing on attribute X and R_TS(X) is for reading.\nTS(T) is the timestamp in which the transaction entered the system\n1) When T wants to Write X, if RTS(X) > T(S) (Someone has read old value) abort, if WTS(X) > T(s)\n  then skip because it will be overwritten, else execute and update timestamps\n2) When T wants to Read x, if WTS(X) > T(s) (someone overwrote old value) then abort, else execute\n3) if two conflicting operations occur in wrong order, it aborts the latter\n\n*MCC: Each transaction operates on private copy of data, copies are merged later",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Locking is Enforcement of serializability by locking database elements, theyre requested by the TX\n* There are two types of locks, read which is sharable, and write which is exclusive!\n\n\n* Dead locks: are the denial of locks due to the existence of an unreleased shared lock\n\n* Two Phase locking (serializable): Once TX starts to release locks, it cannot rquest new locks\n  Consists of growing phase where it has locks, and shrinking phase where its on cooldown for requests\n\n\n* Problem of cascading aborts is when one transaction does changes to attribute A, then another \n  transaction reads those changes, if T1 aborts, T2 also has to abort due to it having information\n  gained by T1.\n* Strict 2PL: Only release locks after Abort/commit to ensure recoverable schedules\n\n* Phantom Read: the same query produces different output at different times.\n  Example: One tuple is added to the table while another transaction is operating on smthn based off\n           off of tuples, this occurs because the addition of a tuple only needs a write lock on that\n           tuple itself, thus General locks do not help\n\n* Lock Granularities: Lock database elements in a hierarchy to cope with different granularities\n* Introduce intention locks on the current element if the element is below in the hierarchy\n* Intention locks IS and IX are compatible with each other, and only S is compatible with IS\n* Latches are physical locks that seperate Threads to protect in-memory data structures\n\n* Optimizations to lock manager:\n  1) try to inherit high-level locks from the previous transaction that executed in the same thread\n  2) Thread-per-data partition rather than thread-per-transaction\n  3) Private lock table per transaction simplifies code paths for requesting and releasing locks from\n     global lock table\n  4) Allow transactions to release their locks as soon as they receive allocated space in buffer pool\n     for commit log record\n\n* How to deal with deadlocks?\n  1) Abort transaction if it is been waiting for too long. How to pick timeout parameter?\n  2) Roll back transaction if waits-for graph contains cycle\n\n* Some applications can handle a bit of dirtyness as a trade off for response time:\n1) Dirty read\n2) Fuzzy Read: T1 reads data, T2 changes/deletes that data and commits, T2 reads same data and\n               finds different value\n3) Phantom: T1 searches using a < X < b, T2 modifies items in that range, T1 searches and finds\n             different values in that range.\n\n* Isolation levels: \n1) READ UNCOMMITTED: can read data that has been written by non-committed transactions.\n    • Allows dirty reads, fuzzy reads, phantoms\n2) READ COMMITTED: only read data that have been updated by committed transactions.\n    • Does not allow dirty reads, Allows fuzzy reads, phantoms\n3) REPEATABLE READ: Reads to individual items are repeatable.\n    • Does not allow dirty reads or fuzzy reads, but Allows phantoms\n4) SERIALIZABLE: Reads by predicate search are repeatable.\n    • Does not allow dirty reads, fuzzy reads, phantoms\n\n* Optimistic approaches hope that conflict will be rare, if they do we fix things, If something goes\nwrong, abort and restart transaction\n\n*Timestamp protocol: for each item, the order that theyre accessed by conflicting operations does not \nviolate the ordering, W_TS(X) is largest TS for writing on attribute X and R_TS(X) is for reading.\nTS(T) is the timestamp in which the transaction entered the system\n1) When T wants to Write X, if RTS(X) > T(S) (Someone has read old value) abort, if WTS(X) > T(s)\n  then skip because it will be overwritten, else execute and update timestamps\n2) When T wants to Read x, if WTS(X) > T(s) (someone overwrote old value) then abort, else execute\n3) if two conflicting operations occur in wrong order, it aborts the latter\n\n*MCC: Each transaction operates on private copy of data, copies are merged later",
			"lineHeight": 1.25,
			"baseline": 1643
		},
		{
			"type": "text",
			"version": 280,
			"versionNonce": 1390143744,
			"isDeleted": false,
			"id": "2evTttcR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -442.86915832134514,
			"y": 1021.3649332995101,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 899.489501953125,
			"height": 20,
			"seed": 313844677,
			"groupIds": [],
			"frameId": "5jHjrEGA1gyCAeexN6OpQ",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "S(E)= request shared lock on E          X(E)= request exclusive lock on E          U(E)= release any lock on E",
			"rawText": "S(E)= request shared lock on E          X(E)= request exclusive lock on E          U(E)= release any lock on E",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "S(E)= request shared lock on E          X(E)= request exclusive lock on E          U(E)= release any lock on E",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 222,
			"versionNonce": 1207117568,
			"isDeleted": false,
			"id": "dvdBmL4t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -505.2908980583812,
			"y": 1001.3649326660511,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 615.8732299804688,
			"height": 20,
			"seed": 112328101,
			"groupIds": [],
			"frameId": "5jHjrEGA1gyCAeexN6OpQ",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "* NO compatibility between any two types of locks except shared with shared",
			"rawText": "* NO compatibility between any two types of locks except shared with shared",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* NO compatibility between any two types of locks except shared with shared",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 227,
			"versionNonce": 1098303744,
			"isDeleted": false,
			"id": "kwK5q4IW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -514.1694005284988,
			"y": 1151.4116244110407,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 344.57672119140625,
			"height": 40,
			"seed": 536070469,
			"groupIds": [],
			"frameId": "5jHjrEGA1gyCAeexN6OpQ",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "* Dead locks can still happen\n* Does not guarantee recoverable schedule",
			"rawText": "* Dead locks can still happen\n* Does not guarantee recoverable schedule",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Dead locks can still happen\n* Does not guarantee recoverable schedule",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 1291208448,
			"isDeleted": false,
			"id": "p7wMHCpz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -277.28893735415653,
			"y": 1084.6429385013796,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 56.92811584472656,
			"height": 20,
			"seed": 1683905701,
			"groupIds": [],
			"frameId": "5jHjrEGA1gyCAeexN6OpQ",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838530851,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "conflict",
			"rawText": "conflict",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "conflict",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "frame",
			"version": 1945,
			"versionNonce": 1823394048,
			"isDeleted": false,
			"id": "5jHjrEGA1gyCAeexN6OpQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -517.0789335538723,
			"y": 896.7541206722697,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 1039.816207,
			"height": 1704.1219511470379,
			"seed": 626535275,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1707838555274,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#949494"
				}
			},
			"name": "CC"
		},
		{
			"id": "8H5OXXwo",
			"type": "text",
			"x": -389.16521852638743,
			"y": -484.1276051536188,
			"width": 8.000015258789062,
			"height": 20,
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
			"seed": 1159686400,
			"version": 2,
			"versionNonce": 135972608,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1707838532251,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
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
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1684.5358038234435,
		"scrollY": 97.64868578867043,
		"zoom": {
			"value": 0.5499999999999999
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