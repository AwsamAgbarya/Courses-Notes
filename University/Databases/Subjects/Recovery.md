---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - databases
---
Next [[Parallel Databases]]
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Recovery ^GlgEZL2Q

* Recovery is the attempt of reconstructing a state of the data after a failure
* Types of failures:








* Buffer Pool: The manager holds pages that may diverge from the page on disk during the crash,
  The transaction changes are durable once the DBMS has told somebody that it committed.
  nothing is saved if the transaction has been aborted.

* Steal: allowed to flush out a page as soon as it starts until the commit
* No-Steal: allowed to flush out a page only until it commits
* Force: Has to flush out this page up until the end of the commit
* No-force: can flush out the page at any time

* Simple Solution: Force + no steal:
  • Since no steal guarantees that only committed transactions are flushes, that means we dont have
    to undo aborted transactions
  • Since Force guarantees that committed transactions are flushed immediately, that means we dont
    have to redo any transaction that has been committed.


* Shadow paging: DBMS keeps two copies of the data called shadow and master, master has the
  only committed TXs changes, all changes from uncommitted Txs happen on the shadow page, whenever
  the transaction commits, the shadow page becomes the master



* Write Ahead Logging (ARIES): Steal + no force:
  • DBMS records all changes made to the database (before being flushed to disk) in a log file
  • Log contains all info to do undo and redo actions to restore the database after a crash
  • DBMS must write the log record to disk before the page is written to disk (Solves steal)
  • Write all records of a TX before TX commits (Solves NO-FORCE)

* Log record: log record contains an id LSN grows monotonically, allows chronological order of log entires
* Data page contains pageLSN which is the last log that updates that page
* theres a global variable flushedLSN which is the last flushed log (Stable log)
* Before a page is written to disk we make sure pageLSN <= flushedLSN

* After crash:
1) Winner transactions (ones that have committed): must be redone
2) Loser transactions (ones that did not commit before the crash): must be undone
* First we go through analysis pass to see which ones are winner or losers
* Second the redo phase, we read the log record forwards and redo all winners in the original order

* Third the undo phase, we read the log backwards to undo all the losers in reverse order

* We cant always start from scratch with ecovery thus we introduce a checkpoint system that:
1) Do not slow down regular TX processing
2) Do not introduce unacceptable latency spikes
3) Do not require excessive memory overhead
when?
1) Time based
2) when log file is full
3) when shutdown ^52EzOUea

1) Transaction failure: ^LMPhxVCZ

• Logical Errors: A transaction cannot complete due to some internal error condition (integrity/constraint violation).
• Internal State Errors: The DBMS must terminate an active transaction due to an error condition (e.g., deadlock) ^dozZ1LJG

2) Media failure: ^EMGs1FxL

• Non-Repairable Hardware Failure: A head crash or similar disk failure destroys all or parts of non-volatile storage. ^kgLvufAZ

3) System failure: ^GmYLB60j

• Software Failure: There is a problem with the DBMS implementation (math exception) and the system has to halt.
• Hardware Failure: The computer hosting the DBMS crashes (e.g., power plug gets pulled).
  We assume that non-volatile storage contents are not corruptedby system crash. ^y9PHIo5i

has poor response time and poor throughput ^VMxsXUgH

no undo/redo   no need for logs     recovery is fast ^VpieecsR

data is scattered                  Normal operations are slow(lots of waiting)
Garbage collection problem          Concurrent transactions are difficult to execute             ^DznglxT9

Faster runtime than shadow-paging but slower recovery! ^pD86Dwnj

only if LSN of the page is less than the LSN of the entry, ^ji9y0Ngg

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
			"version": 1243,
			"versionNonce": 1865750585,
			"isDeleted": false,
			"id": "GlgEZL2Q",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -62.30170552485822,
			"y": -737.9101583460345,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 119.00051879882812,
			"height": 35,
			"seed": 2126560887,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Recovery",
			"rawText": "Recovery",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Recovery",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 2516,
			"versionNonce": 289817177,
			"isDeleted": false,
			"id": "52EzOUea",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -515.8566152838557,
			"y": -701.4672765068603,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1033.93896484375,
			"height": 1475,
			"seed": 677892183,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Recovery is the attempt of reconstructing a state of the data after a failure\n* Types of failures:\n\n\n\n\n\n\n\n\n* Buffer Pool: The manager holds pages that may diverge from the page on disk during the crash,\n  The transaction changes are durable once the DBMS has told somebody that it committed.\n  nothing is saved if the transaction has been aborted.\n\n* Steal: allowed to flush out a page as soon as it starts until the commit\n* No-Steal: allowed to flush out a page only until it commits\n* Force: Has to flush out this page up until the end of the commit\n* No-force: can flush out the page at any time\n\n* Simple Solution: Force + no steal:\n  • Since no steal guarantees that only committed transactions are flushes, that means we dont have\n    to undo aborted transactions\n  • Since Force guarantees that committed transactions are flushed immediately, that means we dont\n    have to redo any transaction that has been committed.\n\n\n* Shadow paging: DBMS keeps two copies of the data called shadow and master, master has the\n  only committed TXs changes, all changes from uncommitted Txs happen on the shadow page, whenever\n  the transaction commits, the shadow page becomes the master\n\n\n\n* Write Ahead Logging (ARIES): Steal + no force:\n  • DBMS records all changes made to the database (before being flushed to disk) in a log file\n  • Log contains all info to do undo and redo actions to restore the database after a crash\n  • DBMS must write the log record to disk before the page is written to disk (Solves steal)\n  • Write all records of a TX before TX commits (Solves NO-FORCE)\n\n* Log record: log record contains an id LSN grows monotonically, allows chronological order of log entires\n* Data page contains pageLSN which is the last log that updates that page\n* theres a global variable flushedLSN which is the last flushed log (Stable log)\n* Before a page is written to disk we make sure pageLSN <= flushedLSN\n\n* After crash:\n1) Winner transactions (ones that have committed): must be redone\n2) Loser transactions (ones that did not commit before the crash): must be undone\n* First we go through analysis pass to see which ones are winner or losers\n* Second the redo phase, we read the log record forwards and redo all winners in the original order\n\n* Third the undo phase, we read the log backwards to undo all the losers in reverse order\n\n* We cant always start from scratch with ecovery thus we introduce a checkpoint system that:\n1) Do not slow down regular TX processing\n2) Do not introduce unacceptable latency spikes\n3) Do not require excessive memory overhead\nwhen?\n1) Time based\n2) when log file is full\n3) when shutdown",
			"rawText": "* Recovery is the attempt of reconstructing a state of the data after a failure\n* Types of failures:\n\n\n\n\n\n\n\n\n* Buffer Pool: The manager holds pages that may diverge from the page on disk during the crash,\n  The transaction changes are durable once the DBMS has told somebody that it committed.\n  nothing is saved if the transaction has been aborted.\n\n* Steal: allowed to flush out a page as soon as it starts until the commit\n* No-Steal: allowed to flush out a page only until it commits\n* Force: Has to flush out this page up until the end of the commit\n* No-force: can flush out the page at any time\n\n* Simple Solution: Force + no steal:\n  • Since no steal guarantees that only committed transactions are flushes, that means we dont have\n    to undo aborted transactions\n  • Since Force guarantees that committed transactions are flushed immediately, that means we dont\n    have to redo any transaction that has been committed.\n\n\n* Shadow paging: DBMS keeps two copies of the data called shadow and master, master has the\n  only committed TXs changes, all changes from uncommitted Txs happen on the shadow page, whenever\n  the transaction commits, the shadow page becomes the master\n\n\n\n* Write Ahead Logging (ARIES): Steal + no force:\n  • DBMS records all changes made to the database (before being flushed to disk) in a log file\n  • Log contains all info to do undo and redo actions to restore the database after a crash\n  • DBMS must write the log record to disk before the page is written to disk (Solves steal)\n  • Write all records of a TX before TX commits (Solves NO-FORCE)\n\n* Log record: log record contains an id LSN grows monotonically, allows chronological order of log entires\n* Data page contains pageLSN which is the last log that updates that page\n* theres a global variable flushedLSN which is the last flushed log (Stable log)\n* Before a page is written to disk we make sure pageLSN <= flushedLSN\n\n* After crash:\n1) Winner transactions (ones that have committed): must be redone\n2) Loser transactions (ones that did not commit before the crash): must be undone\n* First we go through analysis pass to see which ones are winner or losers\n* Second the redo phase, we read the log record forwards and redo all winners in the original order\n\n* Third the undo phase, we read the log backwards to undo all the losers in reverse order\n\n* We cant always start from scratch with ecovery thus we introduce a checkpoint system that:\n1) Do not slow down regular TX processing\n2) Do not introduce unacceptable latency spikes\n3) Do not require excessive memory overhead\nwhen?\n1) Time based\n2) when log file is full\n3) when shutdown",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Recovery is the attempt of reconstructing a state of the data after a failure\n* Types of failures:\n\n\n\n\n\n\n\n\n* Buffer Pool: The manager holds pages that may diverge from the page on disk during the crash,\n  The transaction changes are durable once the DBMS has told somebody that it committed.\n  nothing is saved if the transaction has been aborted.\n\n* Steal: allowed to flush out a page as soon as it starts until the commit\n* No-Steal: allowed to flush out a page only until it commits\n* Force: Has to flush out this page up until the end of the commit\n* No-force: can flush out the page at any time\n\n* Simple Solution: Force + no steal:\n  • Since no steal guarantees that only committed transactions are flushes, that means we dont have\n    to undo aborted transactions\n  • Since Force guarantees that committed transactions are flushed immediately, that means we dont\n    have to redo any transaction that has been committed.\n\n\n* Shadow paging: DBMS keeps two copies of the data called shadow and master, master has the\n  only committed TXs changes, all changes from uncommitted Txs happen on the shadow page, whenever\n  the transaction commits, the shadow page becomes the master\n\n\n\n* Write Ahead Logging (ARIES): Steal + no force:\n  • DBMS records all changes made to the database (before being flushed to disk) in a log file\n  • Log contains all info to do undo and redo actions to restore the database after a crash\n  • DBMS must write the log record to disk before the page is written to disk (Solves steal)\n  • Write all records of a TX before TX commits (Solves NO-FORCE)\n\n* Log record: log record contains an id LSN grows monotonically, allows chronological order of log entires\n* Data page contains pageLSN which is the last log that updates that page\n* theres a global variable flushedLSN which is the last flushed log (Stable log)\n* Before a page is written to disk we make sure pageLSN <= flushedLSN\n\n* After crash:\n1) Winner transactions (ones that have committed): must be redone\n2) Loser transactions (ones that did not commit before the crash): must be undone\n* First we go through analysis pass to see which ones are winner or losers\n* Second the redo phase, we read the log record forwards and redo all winners in the original order\n\n* Third the undo phase, we read the log backwards to undo all the losers in reverse order\n\n* We cant always start from scratch with ecovery thus we introduce a checkpoint system that:\n1) Do not slow down regular TX processing\n2) Do not introduce unacceptable latency spikes\n3) Do not require excessive memory overhead\nwhen?\n1) Time based\n2) when log file is full\n3) when shutdown",
			"lineHeight": 1.25,
			"baseline": 1468
		},
		{
			"type": "text",
			"version": 39,
			"versionNonce": 1056467895,
			"isDeleted": false,
			"id": "LMPhxVCZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -514.6967818125595,
			"y": -646.8042341870508,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 218.3197479248047,
			"height": 25,
			"seed": 282072119,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1) Transaction failure:",
			"rawText": "1) Transaction failure:",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1) Transaction failure:",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 128,
			"versionNonce": 467570489,
			"isDeleted": false,
			"id": "dozZ1LJG",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -492.0953467836944,
			"y": -622.5737010207282,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 923.4259033203125,
			"height": 40,
			"seed": 603146233,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "• Logical Errors: A transaction cannot complete due to some internal error condition (integrity/constraint violation).\n• Internal State Errors: The DBMS must terminate an active transaction due to an error condition (e.g., deadlock)",
			"rawText": "• Logical Errors: A transaction cannot complete due to some internal error condition (integrity/constraint violation).\n• Internal State Errors: The DBMS must terminate an active transaction due to an error condition (e.g., deadlock)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "• Logical Errors: A transaction cannot complete due to some internal error condition (integrity/constraint violation).\n• Internal State Errors: The DBMS must terminate an active transaction due to an error condition (e.g., deadlock)",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 37,
			"versionNonce": 1268400153,
			"isDeleted": false,
			"id": "EMGs1FxL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -517.6400272049998,
			"y": -582.5737004928958,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 164.7998046875,
			"height": 25,
			"seed": 70834455,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2) Media failure:",
			"rawText": "2) Media failure:",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2) Media failure:",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 55,
			"versionNonce": 1852626169,
			"isDeleted": false,
			"id": "kgLvufAZ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -497.11788790122,
			"y": -561.4323057478787,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 930.2097778320312,
			"height": 20,
			"seed": 1507241207,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "• Non-Repairable Hardware Failure: A head crash or similar disk failure destroys all or parts of non-volatile storage.",
			"rawText": "• Non-Repairable Hardware Failure: A head crash or similar disk failure destroys all or parts of non-volatile storage.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "• Non-Repairable Hardware Failure: A head crash or similar disk failure destroys all or parts of non-volatile storage.",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 56,
			"versionNonce": 456250135,
			"isDeleted": false,
			"id": "GmYLB60j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -515.5338719988147,
			"y": -541.3196001602507,
			"strokeColor": "#c2255c",
			"backgroundColor": "transparent",
			"width": 176.11978149414062,
			"height": 25,
			"seed": 1691674743,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "3) System failure:",
			"rawText": "3) System failure:",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "3) System failure:",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 79,
			"versionNonce": 1205456345,
			"isDeleted": false,
			"id": "y9PHIo5i",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -497.11788790122074,
			"y": -516.0655887943371,
			"strokeColor": "#c2255c",
			"backgroundColor": "transparent",
			"width": 919.2498168945312,
			"height": 60,
			"seed": 1206852025,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "• Software Failure: There is a problem with the DBMS implementation (math exception) and the system has to halt.\n• Hardware Failure: The computer hosting the DBMS crashes (e.g., power plug gets pulled).\n  We assume that non-volatile storage contents are not corruptedby system crash.",
			"rawText": "• Software Failure: There is a problem with the DBMS implementation (math exception) and the system has to halt.\n• Hardware Failure: The computer hosting the DBMS crashes (e.g., power plug gets pulled).\n  We assume that non-volatile storage contents are not corruptedby system crash.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "• Software Failure: There is a problem with the DBMS implementation (math exception) and the system has to halt.\n• Hardware Failure: The computer hosting the DBMS crashes (e.g., power plug gets pulled).\n  We assume that non-volatile storage contents are not corruptedby system crash.",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 113,
			"versionNonce": 366303287,
			"isDeleted": false,
			"id": "VMxsXUgH",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -479.69756730263634,
			"y": -105.5146247442782,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 348.6247253417969,
			"height": 20,
			"seed": 408407993,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "has poor response time and poor throughput",
			"rawText": "has poor response time and poor throughput",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "has poor response time and poor throughput",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 125,
			"versionNonce": 1593092793,
			"isDeleted": false,
			"id": "VpieecsR",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -495.74827203008135,
			"y": 21.999307257090493,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 420.57672119140625,
			"height": 20,
			"seed": 1303291095,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "no undo/redo   no need for logs     recovery is fast",
			"rawText": "no undo/redo   no need for logs     recovery is fast",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "no undo/redo   no need for logs     recovery is fast",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 225,
			"versionNonce": 940259671,
			"isDeleted": false,
			"id": "DznglxT9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -499.3150953028469,
			"y": 43.400246893683914,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 773.0252685546875,
			"height": 40,
			"seed": 2137221721,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "data is scattered                  Normal operations are slow(lots of waiting)\nGarbage collection problem          Concurrent transactions are difficult to execute            ",
			"rawText": "data is scattered                  Normal operations are slow(lots of waiting)\nGarbage collection problem          Concurrent transactions are difficult to execute            ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "data is scattered                  Normal operations are slow(lots of waiting)\nGarbage collection problem          Concurrent transactions are difficult to execute            ",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 207678361,
			"isDeleted": false,
			"id": "pD86Dwnj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -488.6146254845502,
			"y": 220.8497047137707,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 440.44891357421875,
			"height": 20,
			"seed": 1912396823,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Faster runtime than shadow-paging but slower recovery!",
			"rawText": "Faster runtime than shadow-paging but slower recovery!",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Faster runtime than shadow-paging but slower recovery!",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "frame",
			"version": 1821,
			"versionNonce": 1583107921,
			"isDeleted": false,
			"id": "CCUbkqgDKBDJ9oeBMqVGK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -523.0920087185882,
			"y": -737.9101584340119,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 1039.816207,
			"height": 1523.1228522340627,
			"seed": 513626679,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708109815068,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#7A7A7A"
				}
			},
			"name": "Recovery"
		},
		{
			"type": "text",
			"version": 98,
			"versionNonce": 1213337721,
			"isDeleted": false,
			"id": "ji9y0Ngg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -494.85656621189,
			"y": 497.27850835310244,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 469.6329040527344,
			"height": 20,
			"seed": 2048988665,
			"groupIds": [],
			"frameId": "CCUbkqgDKBDJ9oeBMqVGK",
			"roundness": null,
			"boundElements": [],
			"updated": 1707420263364,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "only if LSN of the page is less than the LSN of the entry,",
			"rawText": "only if LSN of the page is less than the LSN of the entry,",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "only if LSN of the page is less than the LSN of the entry,",
			"lineHeight": 1.25,
			"baseline": 14
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
		"scrollX": 1188.6005718852548,
		"scrollY": 784.2523781503138,
		"zoom": {
			"value": 0.6000000000000001
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