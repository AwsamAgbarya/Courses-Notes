---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Storage Logic ^XHeFPn1S

* Order of Speed:  Register -> Cache -> Main Memory ->  SSD -> HDD -> Tertiary Storage

* Order of Storage:  Tertiary Storage -> HDD -> SSD -> Main Memory -> Cache -> Register

* Caching: Move important data from lower to higher tier in order to be processed faster
    CPU cache: Main->Hardware   System Cache: Permenant->Main  DBMS Buffer: Permenant->Main

* Spatial Locality: Data close to each other are likely to be used with each other
* Temporal Locality: Data currently used is likely to be used again

* Virtual Memory: give the illusion of exceeding the available physical memory by swapping data to disk

* On a magnetic disk There usually exists one head per surface such that they all move in parallel
  but somehow cannot read in parallel

* Access Acceleration: Elevator Algorithm

                        1) Start from time 0 and wherever the head is positioned
                        2) Seek the right track by switching tracks
                        3) if another request pops up and its in your way, process it
                        4) take into account the processing time of each request you go over
                        5) Move on to the next request in order and repeat

* Checksums Parity bits: if number of 1s is odd = add 1 at the end
                         if number of 1s is even = add 0 at the end
                         with n parity bits (independent) chance of error going unnoticed is 1/2^n

* RAID: Redundant Arrays of Inexpensive Disks
        
        1) Raid 0 = Dsitrubute blocks across all disks.


        2) Raid 1 = Duplicate blocks on 2 diff blocks


        3) Raid 1 + 0 = duplicate + distribute (needs 4 disks)


        4) Raid 4 = Disk dedicated for parity bits of other disks, while other disks are distirbuted

        
        5) Raid 5 = like raid 4 but the parity blocks are rotated around each disk


        6) Raid 6 = like raid 5 but 2x parity bits for each block
 ^ZGNieWrz

0.3ns         0.5ns           100ns           150Ms     20ms       seconds/minutes ^L6uWQUUA

PB              10TB     4TB         4GB-1TB       16kb-20MB    8kb ^1K8C6vFK

Hardware Controlled                    OS Controlled                       DBMS Controlled ^0OTuLxat

Volatile ^HdyRdQWA

Non-Volatile ^CjTlsc38

Storage computation ^7F2mdZsj

* Disk properties:





Example: Disk with 8 platters, 16 surfaces, 2  Tracks per surface, 2 Sectors per track, 2 Bytes per sector

           
          Block is 2  Bytes




          Byte Density (Outermost Track):


* Disk Access:  Transferring Delay  x  Seek time   x   Rotation time   x  Transfer time to controller
 ^V8J6NFli

Disk Consists of Platters ^d7wXObrQ

2 Surfaces ^biqMfwLS

x ^OEo15cOV

x ^vw3ad9jR

Surfaces consist of  Tracks ^epfTzybV

Tracks can be divided into ^6hvj1FNd

A number of sectors Separated by gaps
or
Total storage such that a percentage of it is gaps ^fg5gr9YO

Blocks/Clusters are partial tracks spanning multiple sectors ^MUfesGHv

16 ^rxXFm0rU

8 ^zya6Hm3F

12 ^tV1hzGRs

Capacity: 16 x 2^16 x 2^8 x 2^12 = 1TB ^Pq0lIf4t

14 ^0l9WPci4

Byte per Block                              Sectors Per block
_________ = Sector per Block          ____________ = Blocks per Track
Byte per Sector                             Sectors Per Track ^IZUjqCrS

Bytes per Sector x Sectors per track ^GUpjw1q1

7200 RPM = 60s x 1000ms
              ________  = 8.333ms
             7200 rotations ^ioqsTSf3

Move from one track to another in 1/4000 = 1 + 0.00025  ^Vv8pBqyQ

1ms to start and stop head ^Iy8TSIRg

Best case: Head is already on top of block we want to read (Seek time = 0 , rotation latency =0)
Reading 1 block  = 4 sectors seperated by 3 gaps
if gaps are 10% of track then 256 Gaps cover 36 degrees = 36/256
if sectors are 90% of track then 256 sectors cover 324 degrees = 324/256
Reading: 4*324/256 + 3*36/256   => degree/360 * Rotation speed

Worst case: Must travel from first to last track, Must rotate the entire track to start Transfer
Reading time (same as above) + full rotation + switching across all tracks

Average Case: avg Seek distance = 1/3 of tracks + avg rotation = 1/2 of track
Reading time (same as above) + 1/2 full rotation + switching 1/3 of all tracks

* If the blocks are sequentially stored, we do not need to seek/rotate to read them
* If the blocks are randomly distributed we use the Avg seek time + Avg rotation time to get each
  block
 ^eAP2zhgr

* Change of disk: Time of reading + Time of writing (cant modify directly, need to pull in memory) ^IeZyUleK

50% chance of
detecting errors ^0S3bTA5g

Strg Eff: 100%  Cost: low  Protection: none    read: done in parallel    write: done in parallel ^0QxbitKm

Strg Eff: 50%  Cost: high  Protection: 1 disk can fail    read: better than 1disk    write: worse than 1 disk ^xeAQy9Bc

Strg Eff: 50%  Cost: high  Protection: N/2    read: better than 1disk    write: worse than 1 disk ^2Z34nRuY

Strg Eff: 1Additional Cost: low  Protection: 1disk can fail  read: done in parallel    write: write in parallel +overhead ^W5VNV88l

Strg Eff:N-1  Cost: Medium  Protection: 1disk can fail  read: done in parallel    write: write in parallel +overhead ^QaNOfZe5

Strg Eff:N-2  Cost: Medium  Protection: 2disk can fail  read: done in parallel    write: write in parallel +overhead ^GnwCCn7P

Best case ^XEYdF3Nx

Worst case ^h0ShDsNf

Average Case ^jwlaJ3cj

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
			"version": 478,
			"versionNonce": 1306872064,
			"isDeleted": false,
			"id": "XHeFPn1S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1425.3398898254402,
			"y": -1465.557554184656,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 188.91680908203125,
			"height": 35,
			"seed": 510928959,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Storage Logic",
			"rawText": "Storage Logic",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Storage Logic",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 2561,
			"versionNonce": 1414801664,
			"isDeleted": false,
			"id": "ZGNieWrz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1834.9259222279109,
			"y": -1396.8427075769232,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1011.9788818359375,
			"height": 1150,
			"seed": 1302048049,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Order of Speed:  Register -> Cache -> Main Memory ->  SSD -> HDD -> Tertiary Storage\n\n* Order of Storage:  Tertiary Storage -> HDD -> SSD -> Main Memory -> Cache -> Register\n\n* Caching: Move important data from lower to higher tier in order to be processed faster\n    CPU cache: Main->Hardware   System Cache: Permenant->Main  DBMS Buffer: Permenant->Main\n\n* Spatial Locality: Data close to each other are likely to be used with each other\n* Temporal Locality: Data currently used is likely to be used again\n\n* Virtual Memory: give the illusion of exceeding the available physical memory by swapping data to disk\n\n* On a magnetic disk There usually exists one head per surface such that they all move in parallel\n  but somehow cannot read in parallel\n\n* Access Acceleration: Elevator Algorithm\n\n                        1) Start from time 0 and wherever the head is positioned\n                        2) Seek the right track by switching tracks\n                        3) if another request pops up and its in your way, process it\n                        4) take into account the processing time of each request you go over\n                        5) Move on to the next request in order and repeat\n\n* Checksums Parity bits: if number of 1s is odd = add 1 at the end\n                         if number of 1s is even = add 0 at the end\n                         with n parity bits (independent) chance of error going unnoticed is 1/2^n\n\n* RAID: Redundant Arrays of Inexpensive Disks\n        \n        1) Raid 0 = Dsitrubute blocks across all disks.\n\n\n        2) Raid 1 = Duplicate blocks on 2 diff blocks\n\n\n        3) Raid 1 + 0 = duplicate + distribute (needs 4 disks)\n\n\n        4) Raid 4 = Disk dedicated for parity bits of other disks, while other disks are distirbuted\n\n        \n        5) Raid 5 = like raid 4 but the parity blocks are rotated around each disk\n\n\n        6) Raid 6 = like raid 5 but 2x parity bits for each block\n",
			"rawText": "* Order of Speed:  Register -> Cache -> Main Memory ->  SSD -> HDD -> Tertiary Storage\n\n* Order of Storage:  Tertiary Storage -> HDD -> SSD -> Main Memory -> Cache -> Register\n\n* Caching: Move important data from lower to higher tier in order to be processed faster\n    CPU cache: Main->Hardware   System Cache: Permenant->Main  DBMS Buffer: Permenant->Main\n\n* Spatial Locality: Data close to each other are likely to be used with each other\n* Temporal Locality: Data currently used is likely to be used again\n\n* Virtual Memory: give the illusion of exceeding the available physical memory by swapping data to disk\n\n* On a magnetic disk There usually exists one head per surface such that they all move in parallel\n  but somehow cannot read in parallel\n\n* Access Acceleration: Elevator Algorithm\n\n                        1) Start from time 0 and wherever the head is positioned\n                        2) Seek the right track by switching tracks\n                        3) if another request pops up and its in your way, process it\n                        4) take into account the processing time of each request you go over\n                        5) Move on to the next request in order and repeat\n\n* Checksums Parity bits: if number of 1s is odd = add 1 at the end\n                         if number of 1s is even = add 0 at the end\n                         with n parity bits (independent) chance of error going unnoticed is 1/2^n\n\n* RAID: Redundant Arrays of Inexpensive Disks\n        \n        1) Raid 0 = Dsitrubute blocks across all disks.\n\n\n        2) Raid 1 = Duplicate blocks on 2 diff blocks\n\n\n        3) Raid 1 + 0 = duplicate + distribute (needs 4 disks)\n\n\n        4) Raid 4 = Disk dedicated for parity bits of other disks, while other disks are distirbuted\n\n        \n        5) Raid 5 = like raid 4 but the parity blocks are rotated around each disk\n\n\n        6) Raid 6 = like raid 5 but 2x parity bits for each block\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Order of Speed:  Register -> Cache -> Main Memory ->  SSD -> HDD -> Tertiary Storage\n\n* Order of Storage:  Tertiary Storage -> HDD -> SSD -> Main Memory -> Cache -> Register\n\n* Caching: Move important data from lower to higher tier in order to be processed faster\n    CPU cache: Main->Hardware   System Cache: Permenant->Main  DBMS Buffer: Permenant->Main\n\n* Spatial Locality: Data close to each other are likely to be used with each other\n* Temporal Locality: Data currently used is likely to be used again\n\n* Virtual Memory: give the illusion of exceeding the available physical memory by swapping data to disk\n\n* On a magnetic disk There usually exists one head per surface such that they all move in parallel\n  but somehow cannot read in parallel\n\n* Access Acceleration: Elevator Algorithm\n\n                        1) Start from time 0 and wherever the head is positioned\n                        2) Seek the right track by switching tracks\n                        3) if another request pops up and its in your way, process it\n                        4) take into account the processing time of each request you go over\n                        5) Move on to the next request in order and repeat\n\n* Checksums Parity bits: if number of 1s is odd = add 1 at the end\n                         if number of 1s is even = add 0 at the end\n                         with n parity bits (independent) chance of error going unnoticed is 1/2^n\n\n* RAID: Redundant Arrays of Inexpensive Disks\n        \n        1) Raid 0 = Dsitrubute blocks across all disks.\n\n\n        2) Raid 1 = Duplicate blocks on 2 diff blocks\n\n\n        3) Raid 1 + 0 = duplicate + distribute (needs 4 disks)\n\n\n        4) Raid 4 = Disk dedicated for parity bits of other disks, while other disks are distirbuted\n\n        \n        5) Raid 5 = like raid 4 but the parity blocks are rotated around each disk\n\n\n        6) Raid 6 = like raid 5 but 2x parity bits for each block\n",
			"lineHeight": 1.25,
			"baseline": 1143
		},
		{
			"type": "text",
			"version": 409,
			"versionNonce": 1776748800,
			"isDeleted": false,
			"id": "L6uWQUUA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1630.3126856187878,
			"y": -1374.9757518760914,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 682.0650634765625,
			"height": 20,
			"seed": 1802199647,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "0.3ns         0.5ns           100ns           150Ms     20ms       seconds/minutes",
			"rawText": "0.3ns         0.5ns           100ns           150Ms     20ms       seconds/minutes",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "0.3ns         0.5ns           100ns           150Ms     20ms       seconds/minutes",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 384,
			"versionNonce": 169732352,
			"isDeleted": false,
			"id": "1K8C6vFK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1530.6247162435336,
			"y": -1324.6906699788394,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 590.2088623046875,
			"height": 20,
			"seed": 2032329617,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "PB              10TB     4TB         4GB-1TB       16kb-20MB    8kb",
			"rawText": "PB              10TB     4TB         4GB-1TB       16kb-20MB    8kb",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "PB              10TB     4TB         4GB-1TB       16kb-20MB    8kb",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 457,
			"versionNonce": 1081657600,
			"isDeleted": false,
			"id": "0OTuLxat",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1712.5025693082998,
			"y": -1252.9896685086965,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 740.049072265625,
			"height": 20,
			"seed": 586962975,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Hardware Controlled                    OS Controlled                       DBMS Controlled",
			"rawText": "Hardware Controlled                    OS Controlled                       DBMS Controlled",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Hardware Controlled                    OS Controlled                       DBMS Controlled",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "freedraw",
			"version": 558,
			"versionNonce": 678930688,
			"isDeleted": false,
			"id": "51ANuBDucddiPiixr5vq5",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1645.6869761390562,
			"y": -1391.012629921567,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 345.2089054949567,
			"height": 37.769026859404676,
			"seed": 285887519,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7553805371881026
				],
				[
					0.7553805371881026,
					-1.5107610743762052
				],
				[
					0.7553805371881026,
					-2.266141611564308
				],
				[
					0.7553805371881026,
					-3.0215221487524104
				],
				[
					1.5107610743761484,
					-3.776902685940513
				],
				[
					1.5107610743761484,
					-4.532283223128616
				],
				[
					1.5107610743761484,
					-5.287663760316718
				],
				[
					1.5107610743761484,
					-6.043044297504821
				],
				[
					1.5107610743761484,
					-6.7984248346929235
				],
				[
					1.5107610743761484,
					-7.553805371881026
				],
				[
					1.5107610743761484,
					-8.309185909069129
				],
				[
					1.5107610743761484,
					-9.064566446257004
				],
				[
					2.266141611564251,
					-9.819946983445107
				],
				[
					2.266141611564251,
					-10.57532752063321
				],
				[
					3.0215221487523536,
					-11.330708057821312
				],
				[
					3.0215221487523536,
					-12.086088595009414
				],
				[
					3.0215221487523536,
					-12.841469132197517
				],
				[
					3.776902685940456,
					-13.59684966938562
				],
				[
					4.532283223128502,
					-14.352230206573722
				],
				[
					5.287663760316605,
					-15.107610743761825
				],
				[
					5.287663760316605,
					-15.862991280949927
				],
				[
					6.043044297504707,
					-15.862991280949927
				],
				[
					6.043044297504707,
					-15.107610743761825
				],
				[
					6.79842483469281,
					-15.107610743761825
				],
				[
					6.79842483469281,
					-14.352230206573722
				],
				[
					7.5538053718808555,
					-14.352230206573722
				],
				[
					8.309185909068958,
					-13.59684966938562
				],
				[
					9.819946983445163,
					-13.59684966938562
				],
				[
					10.575327520633266,
					-12.841469132197517
				],
				[
					12.086088595009414,
					-12.841469132197517
				],
				[
					12.841469132197517,
					-12.841469132197517
				],
				[
					13.59684966938562,
					-12.841469132197517
				],
				[
					14.352230206573665,
					-12.086088595009414
				],
				[
					15.107610743761768,
					-12.086088595009414
				],
				[
					15.86299128094987,
					-11.330708057821312
				],
				[
					16.618371818137973,
					-10.57532752063321
				],
				[
					17.37375235532602,
					-10.57532752063321
				],
				[
					18.12913289251412,
					-10.57532752063321
				],
				[
					19.639893966890327,
					-10.57532752063321
				],
				[
					20.395274504078373,
					-10.57532752063321
				],
				[
					21.906035578454578,
					-9.819946983445107
				],
				[
					22.66141611564268,
					-9.819946983445107
				],
				[
					23.416796652830726,
					-9.819946983445107
				],
				[
					24.17217719001883,
					-9.819946983445107
				],
				[
					24.92755772720693,
					-9.064566446257004
				],
				[
					25.682938264395034,
					-9.064566446257004
				],
				[
					27.193699338771182,
					-8.309185909069129
				],
				[
					27.949079875959285,
					-8.309185909069129
				],
				[
					29.45984095033549,
					-8.309185909069129
				],
				[
					30.97060202471164,
					-8.309185909069129
				],
				[
					31.72598256189974,
					-8.309185909069129
				],
				[
					32.481363099087844,
					-8.309185909069129
				],
				[
					33.23674363627589,
					-8.309185909069129
				],
				[
					33.99212417346399,
					-8.309185909069129
				],
				[
					34.747504710652095,
					-8.309185909069129
				],
				[
					36.25826578502824,
					-8.309185909069129
				],
				[
					37.013646322216346,
					-8.309185909069129
				],
				[
					38.52440739659255,
					-8.309185909069129
				],
				[
					40.7905490081568,
					-8.309185909069129
				],
				[
					42.30131008253295,
					-8.309185909069129
				],
				[
					45.32283223128536,
					-8.309185909069129
				],
				[
					46.83359330566151,
					-8.309185909069129
				],
				[
					49.09973491722576,
					-8.309185909069129
				],
				[
					50.610495991601965,
					-7.553805371881026
				],
				[
					52.876637603166216,
					-7.553805371881026
				],
				[
					54.38739867754242,
					-7.553805371881026
				],
				[
					55.14277921473047,
					-7.553805371881026
				],
				[
					56.65354028910667,
					-7.553805371881026
				],
				[
					58.16430136348282,
					-7.553805371881026
				],
				[
					59.675062437859026,
					-7.553805371881026
				],
				[
					60.43044297504713,
					-7.553805371881026
				],
				[
					61.94120404942328,
					-7.553805371881026
				],
				[
					63.45196512379948,
					-7.553805371881026
				],
				[
					64.96272619817563,
					-7.553805371881026
				],
				[
					65.71810673536373,
					-7.553805371881026
				],
				[
					66.47348727255184,
					-7.553805371881026
				],
				[
					67.98424834692798,
					-7.553805371881026
				],
				[
					69.49500942130419,
					-7.553805371881026
				],
				[
					70.25038995849229,
					-6.7984248346929235
				],
				[
					71.76115103286844,
					-6.7984248346929235
				],
				[
					73.27191210724465,
					-6.7984248346929235
				],
				[
					74.7826731816208,
					-6.7984248346929235
				],
				[
					76.293434255997,
					-6.7984248346929235
				],
				[
					77.04881479318504,
					-6.7984248346929235
				],
				[
					77.80419533037315,
					-6.7984248346929235
				],
				[
					78.55957586756125,
					-6.7984248346929235
				],
				[
					79.31495640474935,
					-6.7984248346929235
				],
				[
					80.8257174791255,
					-6.7984248346929235
				],
				[
					81.5810980163136,
					-6.7984248346929235
				],
				[
					83.09185909068981,
					-6.7984248346929235
				],
				[
					84.60262016506596,
					-6.7984248346929235
				],
				[
					86.86876177663021,
					-6.7984248346929235
				],
				[
					87.62414231381831,
					-6.7984248346929235
				],
				[
					89.13490338819452,
					-6.7984248346929235
				],
				[
					89.89028392538256,
					-6.7984248346929235
				],
				[
					91.40104499975877,
					-6.7984248346929235
				],
				[
					92.15642553694687,
					-6.7984248346929235
				],
				[
					92.91180607413492,
					-6.7984248346929235
				],
				[
					93.66718661132302,
					-6.7984248346929235
				],
				[
					94.42256714851112,
					-6.7984248346929235
				],
				[
					95.93332822288727,
					-6.7984248346929235
				],
				[
					97.44408929726347,
					-6.7984248346929235
				],
				[
					98.95485037163962,
					-6.7984248346929235
				],
				[
					101.22099198320393,
					-6.7984248346929235
				],
				[
					102.73175305758008,
					-6.7984248346929235
				],
				[
					104.99789466914439,
					-6.7984248346929235
				],
				[
					105.75327520633243,
					-6.7984248346929235
				],
				[
					106.50865574352053,
					-6.7984248346929235
				],
				[
					107.26403628070864,
					-6.7984248346929235
				],
				[
					108.01941681789674,
					-6.7984248346929235
				],
				[
					108.77479735508479,
					-6.7984248346929235
				],
				[
					110.28555842946099,
					-6.7984248346929235
				],
				[
					111.0409389666491,
					-6.7984248346929235
				],
				[
					113.30708057821334,
					-6.7984248346929235
				],
				[
					114.8178416525895,
					-6.7984248346929235
				],
				[
					117.0839832641538,
					-6.7984248346929235
				],
				[
					118.59474433852995,
					-6.7984248346929235
				],
				[
					119.35012487571805,
					-6.7984248346929235
				],
				[
					120.10550541290615,
					-6.7984248346929235
				],
				[
					120.86088595009426,
					-6.7984248346929235
				],
				[
					120.86088595009426,
					-7.553805371881026
				],
				[
					121.6162664872823,
					-7.553805371881026
				],
				[
					122.3716470244704,
					-8.309185909069129
				],
				[
					123.12702756165851,
					-8.309185909069129
				],
				[
					124.63778863603466,
					-9.064566446257004
				],
				[
					126.14854971041086,
					-9.819946983445107
				],
				[
					126.90393024759896,
					-10.57532752063321
				],
				[
					128.4146913219751,
					-10.57532752063321
				],
				[
					129.17007185916322,
					-11.330708057821312
				],
				[
					130.68083293353936,
					-12.086088595009414
				],
				[
					131.43621347072747,
					-12.086088595009414
				],
				[
					132.19159400791557,
					-12.841469132197517
				],
				[
					133.70235508229172,
					-13.59684966938562
				],
				[
					134.45773561947982,
					-14.352230206573722
				],
				[
					135.96849669385603,
					-15.107610743761825
				],
				[
					137.47925776823217,
					-15.107610743761825
				],
				[
					138.99001884260838,
					-15.862991280949927
				],
				[
					139.74539937979648,
					-16.61837181813803
				],
				[
					140.50077991698453,
					-17.373752355326133
				],
				[
					141.25616045417263,
					-17.373752355326133
				],
				[
					142.01154099136073,
					-18.129132892514235
				],
				[
					142.76692152854883,
					-18.884513429702338
				],
				[
					143.52230206573688,
					-19.63989396689044
				],
				[
					145.0330631401131,
					-20.395274504078316
				],
				[
					145.7884436773012,
					-21.15065504126642
				],
				[
					146.54382421448923,
					-21.90603557845452
				],
				[
					147.29920475167734,
					-22.661416115642623
				],
				[
					148.05458528886544,
					-22.661416115642623
				],
				[
					148.05458528886544,
					-23.416796652830726
				],
				[
					148.80996582605354,
					-24.17217719001883
				],
				[
					149.5653463632416,
					-24.92755772720693
				],
				[
					150.3207269004297,
					-24.92755772720693
				],
				[
					151.0761074376178,
					-25.682938264395034
				],
				[
					151.0761074376178,
					-26.438318801583137
				],
				[
					151.0761074376178,
					-27.19369933877124
				],
				[
					151.0761074376178,
					-27.94907987595934
				],
				[
					151.0761074376178,
					-29.459840950335547
				],
				[
					151.0761074376178,
					-30.21522148752365
				],
				[
					151.0761074376178,
					-31.725982561899855
				],
				[
					151.0761074376178,
					-32.48136309908796
				],
				[
					151.0761074376178,
					-33.23674363627606
				],
				[
					151.0761074376178,
					-33.99212417346416
				],
				[
					151.8314879748059,
					-33.99212417346416
				],
				[
					151.8314879748059,
					-33.23674363627606
				],
				[
					151.8314879748059,
					-32.48136309908796
				],
				[
					151.8314879748059,
					-31.725982561899855
				],
				[
					151.8314879748059,
					-30.970602024711752
				],
				[
					151.8314879748059,
					-30.21522148752365
				],
				[
					152.58686851199394,
					-29.459840950335547
				],
				[
					153.34224904918204,
					-28.704460413147444
				],
				[
					154.09762958637015,
					-27.19369933877124
				],
				[
					154.85301012355825,
					-25.682938264395034
				],
				[
					155.6083906607463,
					-24.92755772720693
				],
				[
					156.3637711979344,
					-23.416796652830726
				],
				[
					157.1191517351225,
					-22.661416115642623
				],
				[
					157.1191517351225,
					-21.90603557845452
				],
				[
					157.8745322723106,
					-21.90603557845452
				],
				[
					157.8745322723106,
					-21.15065504126642
				],
				[
					158.6299128094987,
					-20.395274504078316
				],
				[
					159.38529334668675,
					-20.395274504078316
				],
				[
					160.14067388387485,
					-19.63989396689044
				],
				[
					161.65143495825106,
					-19.63989396689044
				],
				[
					162.4068154954391,
					-18.884513429702338
				],
				[
					163.1621960326272,
					-18.884513429702338
				],
				[
					163.9175765698153,
					-18.884513429702338
				],
				[
					165.42833764419146,
					-18.884513429702338
				],
				[
					166.93909871856766,
					-18.129132892514235
				],
				[
					167.69447925575577,
					-18.129132892514235
				],
				[
					169.20524033013191,
					-18.129132892514235
				],
				[
					170.71600140450812,
					-17.373752355326133
				],
				[
					172.98214301607237,
					-17.373752355326133
				],
				[
					175.24828462763662,
					-16.61837181813803
				],
				[
					177.51442623920093,
					-15.862991280949927
				],
				[
					179.02518731357708,
					-15.107610743761825
				],
				[
					179.02518731357708,
					-15.862991280949927
				],
				[
					180.53594838795328,
					-16.61837181813803
				],
				[
					181.29132892514133,
					-16.61837181813803
				],
				[
					185.06823161108179,
					-16.61837181813803
				],
				[
					187.33437322264604,
					-16.61837181813803
				],
				[
					191.1112759085865,
					-16.61837181813803
				],
				[
					195.64355913171505,
					-16.61837181813803
				],
				[
					198.6650812804674,
					-16.61837181813803
				],
				[
					203.1973645035959,
					-16.61837181813803
				],
				[
					205.46350611516021,
					-15.862991280949927
				],
				[
					207.72964772672447,
					-15.862991280949927
				],
				[
					209.99578933828872,
					-15.862991280949927
				],
				[
					211.50655041266492,
					-15.862991280949927
				],
				[
					213.01731148704107,
					-15.107610743761825
				],
				[
					213.77269202422917,
					-15.107610743761825
				],
				[
					214.52807256141728,
					-15.107610743761825
				],
				[
					215.28345309860538,
					-14.352230206573722
				],
				[
					216.79421417298153,
					-14.352230206573722
				],
				[
					219.06035578454578,
					-13.59684966938562
				],
				[
					221.32649739611008,
					-12.841469132197517
				],
				[
					225.10340008205048,
					-11.330708057821312
				],
				[
					228.12492223080284,
					-10.57532752063321
				],
				[
					231.14644437955525,
					-10.57532752063321
				],
				[
					234.1679665283076,
					-9.819946983445107
				],
				[
					236.43410813987185,
					-9.064566446257004
				],
				[
					238.7002497514361,
					-8.309185909069129
				],
				[
					239.4556302886242,
					-8.309185909069129
				],
				[
					240.96639136300035,
					-8.309185909069129
				],
				[
					241.72177190018846,
					-8.309185909069129
				],
				[
					243.23253297456466,
					-7.553805371881026
				],
				[
					243.9879135117527,
					-7.553805371881026
				],
				[
					245.4986745861289,
					-7.553805371881026
				],
				[
					247.00943566050506,
					-7.553805371881026
				],
				[
					248.52019673488127,
					-7.553805371881026
				],
				[
					251.54171888363368,
					-7.553805371881026
				],
				[
					253.05247995800977,
					-7.553805371881026
				],
				[
					255.31862156957408,
					-7.553805371881026
				],
				[
					256.8293826439503,
					-7.553805371881026
				],
				[
					259.0955242555145,
					-7.553805371881026
				],
				[
					260.6062853298907,
					-7.553805371881026
				],
				[
					262.872426941455,
					-7.553805371881026
				],
				[
					264.3831880158311,
					-7.553805371881026
				],
				[
					265.8939490902073,
					-7.553805371881026
				],
				[
					268.1600907017716,
					-7.553805371881026
				],
				[
					269.6708517761478,
					-7.553805371881026
				],
				[
					271.936993387712,
					-7.553805371881026
				],
				[
					272.6923739249001,
					-7.553805371881026
				],
				[
					273.4477544620882,
					-7.553805371881026
				],
				[
					275.7138960736525,
					-7.553805371881026
				],
				[
					277.2246571480286,
					-8.309185909069129
				],
				[
					277.9800376852167,
					-8.309185909069129
				],
				[
					279.4907987595929,
					-9.064566446257004
				],
				[
					281.0015598339691,
					-9.064566446257004
				],
				[
					282.5123209083453,
					-9.064566446257004
				],
				[
					284.0230819827214,
					-9.064566446257004
				],
				[
					286.2892235942857,
					-9.064566446257004
				],
				[
					287.7999846686619,
					-9.064566446257004
				],
				[
					289.3107457430381,
					-9.064566446257004
				],
				[
					291.5768873546023,
					-9.819946983445107
				],
				[
					293.0876484289785,
					-9.819946983445107
				],
				[
					294.59840950335473,
					-9.819946983445107
				],
				[
					296.8645511149189,
					-9.819946983445107
				],
				[
					298.37531218929513,
					-9.819946983445107
				],
				[
					300.64145380085944,
					-9.819946983445107
				],
				[
					302.15221487523553,
					-9.819946983445107
				],
				[
					303.66297594961173,
					-9.819946983445107
				],
				[
					305.17373702398794,
					-9.819946983445107
				],
				[
					306.68449809836414,
					-9.819946983445107
				],
				[
					307.43987863555225,
					-9.819946983445107
				],
				[
					308.19525917274035,
					-9.819946983445107
				],
				[
					308.95063970992834,
					-9.819946983445107
				],
				[
					309.70602024711644,
					-9.819946983445107
				],
				[
					311.21678132149265,
					-9.819946983445107
				],
				[
					311.97216185868075,
					-9.819946983445107
				],
				[
					312.72754239586885,
					-9.819946983445107
				],
				[
					313.48292293305695,
					-9.819946983445107
				],
				[
					314.23830347024506,
					-9.819946983445107
				],
				[
					314.99368400743305,
					-9.819946983445107
				],
				[
					315.74906454462115,
					-9.819946983445107
				],
				[
					316.50444508180925,
					-9.819946983445107
				],
				[
					317.25982561899735,
					-9.819946983445107
				],
				[
					318.77058669337356,
					-9.819946983445107
				],
				[
					319.52596723056166,
					-9.819946983445107
				],
				[
					320.28134776774976,
					-9.819946983445107
				],
				[
					322.54748937931396,
					-9.819946983445107
				],
				[
					323.30286991650206,
					-9.819946983445107
				],
				[
					324.05825045369016,
					-9.819946983445107
				],
				[
					324.81363099087827,
					-9.819946983445107
				],
				[
					325.56901152806637,
					-9.819946983445107
				],
				[
					327.0797726024426,
					-9.064566446257004
				],
				[
					328.59053367681867,
					-9.064566446257004
				],
				[
					331.6120558255711,
					-8.309185909069129
				],
				[
					333.87819743713527,
					-7.553805371881026
				],
				[
					336.1443390486996,
					-6.7984248346929235
				],
				[
					337.6551001230758,
					-6.043044297504821
				],
				[
					339.92124173464,
					-5.287663760316718
				],
				[
					340.6766222718281,
					-4.532283223128616
				],
				[
					341.4320028090162,
					-4.532283223128616
				],
				[
					342.1873833462043,
					-4.532283223128616
				],
				[
					342.9427638833924,
					-4.532283223128616
				],
				[
					342.9427638833924,
					-3.776902685940513
				],
				[
					343.6981444205805,
					-3.0215221487524104
				],
				[
					343.6981444205805,
					-2.266141611564308
				],
				[
					343.6981444205805,
					-1.5107610743762052
				],
				[
					344.4535249577686,
					-0.7553805371881026
				],
				[
					344.4535249577686,
					0
				],
				[
					344.4535249577686,
					0.7553805371881026
				],
				[
					344.4535249577686,
					1.5107610743762052
				],
				[
					345.2089054949567,
					1.5107610743762052
				],
				[
					345.2089054949567,
					2.266141611564308
				],
				[
					345.2089054949567,
					3.0215221487524104
				],
				[
					345.2089054949567,
					3.776902685940513
				],
				[
					345.2089054949567,
					3.776902685940513
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 290,
			"versionNonce": 1838844160,
			"isDeleted": false,
			"id": "HdyRdQWA",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1529.3583734120905,
			"y": -1446.9107896734856,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 57.52012634277344,
			"height": 20,
			"seed": 589782719,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Volatile",
			"rawText": "Volatile",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Volatile",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "freedraw",
			"version": 551,
			"versionNonce": 1264675072,
			"isDeleted": false,
			"id": "InJyocbgi3__StxdXLJtw",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1263.4644243218834,
			"y": -1389.5018688471907,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 341.43200280901624,
			"height": 37.76902685940445,
			"seed": 725953855,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					0,
					-0.7553805371881026
				],
				[
					0,
					-1.5107610743762052
				],
				[
					0.7553805371880458,
					-2.266141611564308
				],
				[
					0.7553805371880458,
					-3.0215221487524104
				],
				[
					1.5107610743761484,
					-3.776902685940513
				],
				[
					2.266141611564251,
					-4.532283223128616
				],
				[
					3.0215221487523536,
					-5.287663760316718
				],
				[
					3.0215221487523536,
					-6.7984248346929235
				],
				[
					3.776902685940456,
					-7.553805371881026
				],
				[
					4.532283223128502,
					-8.309185909069129
				],
				[
					5.287663760316605,
					-9.064566446257231
				],
				[
					5.287663760316605,
					-9.819946983445334
				],
				[
					6.043044297504707,
					-9.819946983445334
				],
				[
					6.79842483469281,
					-10.57532752063321
				],
				[
					7.5538053718808555,
					-11.330708057821312
				],
				[
					8.309185909068958,
					-12.086088595009414
				],
				[
					9.06456644625706,
					-12.841469132197517
				],
				[
					9.819946983445163,
					-13.59684966938562
				],
				[
					10.57532752063321,
					-13.59684966938562
				],
				[
					11.330708057821312,
					-13.59684966938562
				],
				[
					12.086088595009414,
					-13.59684966938562
				],
				[
					12.841469132197517,
					-12.841469132197517
				],
				[
					13.596849669385563,
					-12.841469132197517
				],
				[
					15.107610743761768,
					-12.841469132197517
				],
				[
					16.618371818137916,
					-12.841469132197517
				],
				[
					17.37375235532602,
					-12.841469132197517
				],
				[
					18.884513429702224,
					-12.841469132197517
				],
				[
					19.63989396689027,
					-12.086088595009414
				],
				[
					20.395274504078373,
					-12.086088595009414
				],
				[
					21.150655041266475,
					-12.086088595009414
				],
				[
					21.906035578454578,
					-12.086088595009414
				],
				[
					22.66141611564268,
					-12.086088595009414
				],
				[
					23.416796652830726,
					-12.086088595009414
				],
				[
					24.92755772720693,
					-12.086088595009414
				],
				[
					25.682938264395034,
					-12.086088595009414
				],
				[
					27.949079875959285,
					-12.086088595009414
				],
				[
					28.704460413147387,
					-12.086088595009414
				],
				[
					30.215221487523536,
					-12.086088595009414
				],
				[
					31.72598256189974,
					-12.086088595009414
				],
				[
					32.48136309908779,
					-12.086088595009414
				],
				[
					33.23674363627589,
					-12.086088595009414
				],
				[
					33.99212417346399,
					-12.086088595009414
				],
				[
					35.50288524784014,
					-12.086088595009414
				],
				[
					37.013646322216346,
					-12.086088595009414
				],
				[
					40.0351684709687,
					-12.086088595009414
				],
				[
					42.30131008253295,
					-12.841469132197517
				],
				[
					45.322832231285304,
					-13.59684966938562
				],
				[
					47.58897384284961,
					-13.59684966938562
				],
				[
					49.09973491722576,
					-14.352230206573722
				],
				[
					52.121257065978114,
					-14.352230206573722
				],
				[
					52.876637603166216,
					-14.352230206573722
				],
				[
					54.387398677542365,
					-14.352230206573722
				],
				[
					55.14277921473047,
					-14.352230206573722
				],
				[
					55.89815975191857,
					-14.352230206573722
				],
				[
					57.40892082629472,
					-15.107610743761825
				],
				[
					58.91968190067092,
					-15.107610743761825
				],
				[
					59.675062437859026,
					-15.107610743761825
				],
				[
					61.185823512235174,
					-15.107610743761825
				],
				[
					63.45196512379948,
					-15.107610743761825
				],
				[
					64.20734566098753,
					-15.107610743761825
				],
				[
					65.71810673536373,
					-15.107610743761825
				],
				[
					66.47348727255184,
					-15.107610743761825
				],
				[
					67.22886780973988,
					-15.107610743761825
				],
				[
					67.98424834692798,
					-15.107610743761825
				],
				[
					70.25038995849224,
					-14.352230206573722
				],
				[
					73.27191210724459,
					-13.59684966938562
				],
				[
					76.293434255997,
					-12.841469132197517
				],
				[
					79.31495640474935,
					-12.086088595009414
				],
				[
					80.8257174791255,
					-12.086088595009414
				],
				[
					82.3364785535017,
					-12.086088595009414
				],
				[
					85.35800070225406,
					-11.330708057821312
				],
				[
					86.86876177663021,
					-11.330708057821312
				],
				[
					88.37952285100641,
					-11.330708057821312
				],
				[
					89.13490338819446,
					-11.330708057821312
				],
				[
					89.89028392538256,
					-11.330708057821312
				],
				[
					91.40104499975877,
					-11.330708057821312
				],
				[
					92.91180607413492,
					-10.57532752063321
				],
				[
					95.17794768569922,
					-10.57532752063321
				],
				[
					96.68870876007537,
					-10.57532752063321
				],
				[
					98.19946983445158,
					-10.57532752063321
				],
				[
					100.46561144601583,
					-10.57532752063321
				],
				[
					101.97637252039198,
					-10.57532752063321
				],
				[
					102.73175305758008,
					-10.57532752063321
				],
				[
					103.48713359476818,
					-10.57532752063321
				],
				[
					104.24251413195628,
					-11.330708057821312
				],
				[
					104.99789466914433,
					-11.330708057821312
				],
				[
					105.75327520633243,
					-12.086088595009414
				],
				[
					106.50865574352053,
					-12.841469132197517
				],
				[
					108.01941681789668,
					-13.59684966938562
				],
				[
					109.53017789227289,
					-13.59684966938562
				],
				[
					111.79631950383714,
					-14.352230206573722
				],
				[
					112.55170004102524,
					-15.107610743761825
				],
				[
					114.06246111540145,
					-15.862991280949927
				],
				[
					114.81784165258955,
					-15.862991280949927
				],
				[
					115.57322218977765,
					-16.61837181813803
				],
				[
					116.32860272696564,
					-16.61837181813803
				],
				[
					117.08398326415374,
					-17.373752355326133
				],
				[
					117.83936380134185,
					-18.129132892514235
				],
				[
					118.59474433852995,
					-18.129132892514235
				],
				[
					120.10550541290615,
					-18.884513429702338
				],
				[
					120.86088595009426,
					-19.63989396689044
				],
				[
					121.61626648728236,
					-20.395274504078543
				],
				[
					122.37164702447035,
					-20.395274504078543
				],
				[
					123.12702756165845,
					-21.150655041266646
				],
				[
					123.88240809884655,
					-21.90603557845452
				],
				[
					123.88240809884655,
					-22.661416115642623
				],
				[
					124.63778863603466,
					-22.661416115642623
				],
				[
					124.63778863603466,
					-23.416796652830726
				],
				[
					124.63778863603466,
					-24.17217719001883
				],
				[
					125.39316917322276,
					-24.92755772720693
				],
				[
					125.39316917322276,
					-25.682938264395034
				],
				[
					125.39316917322276,
					-26.438318801583137
				],
				[
					125.39316917322276,
					-27.19369933877124
				],
				[
					125.39316917322276,
					-27.94907987595934
				],
				[
					125.39316917322276,
					-28.704460413147444
				],
				[
					125.39316917322276,
					-29.459840950335547
				],
				[
					125.39316917322276,
					-30.21522148752365
				],
				[
					125.39316917322276,
					-30.970602024711752
				],
				[
					125.39316917322276,
					-31.725982561899855
				],
				[
					126.14854971041086,
					-30.970602024711752
				],
				[
					126.14854971041086,
					-30.21522148752365
				],
				[
					126.90393024759896,
					-28.704460413147444
				],
				[
					128.41469132197506,
					-27.19369933877124
				],
				[
					129.17007185916316,
					-26.438318801583137
				],
				[
					129.92545239635126,
					-24.92755772720693
				],
				[
					130.68083293353936,
					-24.92755772720693
				],
				[
					131.43621347072747,
					-24.17217719001883
				],
				[
					132.19159400791557,
					-23.416796652830726
				],
				[
					132.94697454510367,
					-22.661416115642623
				],
				[
					134.45773561947988,
					-21.90603557845452
				],
				[
					135.96849669385597,
					-21.150655041266646
				],
				[
					138.23463830542028,
					-20.395274504078543
				],
				[
					139.74539937979648,
					-20.395274504078543
				],
				[
					141.25616045417257,
					-19.63989396689044
				],
				[
					142.76692152854878,
					-18.884513429702338
				],
				[
					143.52230206573688,
					-18.884513429702338
				],
				[
					144.27768260292498,
					-18.884513429702338
				],
				[
					145.0330631401131,
					-18.884513429702338
				],
				[
					145.7884436773012,
					-18.884513429702338
				],
				[
					146.5438242144893,
					-18.129132892514235
				],
				[
					147.29920475167728,
					-18.129132892514235
				],
				[
					148.05458528886538,
					-18.129132892514235
				],
				[
					148.80996582605349,
					-18.129132892514235
				],
				[
					149.5653463632416,
					-18.129132892514235
				],
				[
					150.3207269004297,
					-17.373752355326133
				],
				[
					151.8314879748059,
					-16.61837181813803
				],
				[
					153.3422490491821,
					-15.862991280949927
				],
				[
					154.0976295863701,
					-15.862991280949927
				],
				[
					154.8530101235582,
					-15.862991280949927
				],
				[
					155.6083906607463,
					-15.862991280949927
				],
				[
					156.3637711979344,
					-15.862991280949927
				],
				[
					157.1191517351225,
					-15.107610743761825
				],
				[
					158.6299128094987,
					-14.352230206573722
				],
				[
					160.1406738838748,
					-14.352230206573722
				],
				[
					163.1621960326272,
					-14.352230206573722
				],
				[
					164.6729571070034,
					-14.352230206573722
				],
				[
					166.9390987185676,
					-14.352230206573722
				],
				[
					169.20524033013191,
					-14.352230206573722
				],
				[
					172.9821430160723,
					-14.352230206573722
				],
				[
					176.00366516482472,
					-14.352230206573722
				],
				[
					178.26980677638903,
					-14.352230206573722
				],
				[
					180.53594838795323,
					-14.352230206573722
				],
				[
					182.04670946232943,
					-13.59684966938562
				],
				[
					182.80208999951753,
					-13.59684966938562
				],
				[
					183.55747053670564,
					-13.59684966938562
				],
				[
					184.31285107389374,
					-13.59684966938562
				],
				[
					185.06823161108173,
					-13.59684966938562
				],
				[
					185.82361214826983,
					-13.59684966938562
				],
				[
					186.57899268545793,
					-13.59684966938562
				],
				[
					188.08975375983414,
					-13.59684966938562
				],
				[
					189.60051483421034,
					-14.352230206573722
				],
				[
					191.11127590858655,
					-14.352230206573722
				],
				[
					191.86665644577454,
					-14.352230206573722
				],
				[
					193.37741752015074,
					-15.107610743761825
				],
				[
					194.13279805733885,
					-15.107610743761825
				],
				[
					195.64355913171505,
					-15.107610743761825
				],
				[
					197.90970074327925,
					-15.107610743761825
				],
				[
					199.42046181765545,
					-15.107610743761825
				],
				[
					200.17584235484355,
					-15.862991280949927
				],
				[
					201.68660342921976,
					-15.862991280949927
				],
				[
					203.19736450359596,
					-15.862991280949927
				],
				[
					204.70812557797205,
					-16.61837181813803
				],
				[
					206.21888665234826,
					-16.61837181813803
				],
				[
					206.97426718953636,
					-16.61837181813803
				],
				[
					208.48502826391257,
					-16.61837181813803
				],
				[
					209.99578933828877,
					-16.61837181813803
				],
				[
					210.75116987547676,
					-16.61837181813803
				],
				[
					212.26193094985297,
					-16.61837181813803
				],
				[
					213.01731148704107,
					-16.61837181813803
				],
				[
					215.28345309860538,
					-16.61837181813803
				],
				[
					216.03883363579348,
					-16.61837181813803
				],
				[
					217.54959471016957,
					-16.61837181813803
				],
				[
					219.06035578454578,
					-16.61837181813803
				],
				[
					220.57111685892198,
					-16.61837181813803
				],
				[
					221.32649739611008,
					-16.61837181813803
				],
				[
					222.83725847048618,
					-16.61837181813803
				],
				[
					223.59263900767428,
					-16.61837181813803
				],
				[
					224.34801954486238,
					-16.61837181813803
				],
				[
					225.8587806192386,
					-16.61837181813803
				],
				[
					227.3695416936148,
					-16.61837181813803
				],
				[
					228.880302767991,
					-16.61837181813803
				],
				[
					230.3910638423671,
					-16.61837181813803
				],
				[
					232.6572054539314,
					-16.61837181813803
				],
				[
					234.1679665283076,
					-16.61837181813803
				],
				[
					236.4341081398718,
					-16.61837181813803
				],
				[
					237.944869214248,
					-16.61837181813803
				],
				[
					239.4556302886242,
					-16.61837181813803
				],
				[
					240.9663913630004,
					-16.61837181813803
				],
				[
					242.4771524373765,
					-16.61837181813803
				],
				[
					243.2325329745646,
					-16.61837181813803
				],
				[
					245.4986745861289,
					-16.61837181813803
				],
				[
					246.25405512331702,
					-16.61837181813803
				],
				[
					248.5201967348812,
					-16.61837181813803
				],
				[
					250.03095780925742,
					-16.61837181813803
				],
				[
					252.29709942082172,
					-16.61837181813803
				],
				[
					253.80786049519793,
					-16.61837181813803
				],
				[
					254.56324103238592,
					-16.61837181813803
				],
				[
					255.31862156957402,
					-16.61837181813803
				],
				[
					256.0740021067621,
					-16.61837181813803
				],
				[
					257.5847631811383,
					-16.61837181813803
				],
				[
					259.85090479270264,
					-16.61837181813803
				],
				[
					262.11704640426683,
					-16.61837181813803
				],
				[
					262.87242694145493,
					-16.61837181813803
				],
				[
					264.38318801583114,
					-16.61837181813803
				],
				[
					265.13856855301924,
					-16.61837181813803
				],
				[
					265.89394909020734,
					-16.61837181813803
				],
				[
					266.64932962739545,
					-16.61837181813803
				],
				[
					268.91547123895964,
					-15.862991280949927
				],
				[
					271.18161285052395,
					-15.862991280949927
				],
				[
					272.69237392490015,
					-15.862991280949927
				],
				[
					274.95851553646435,
					-15.862991280949927
				],
				[
					276.46927661084055,
					-15.107610743761825
				],
				[
					277.98003768521676,
					-15.107610743761825
				],
				[
					278.73541822240486,
					-15.107610743761825
				],
				[
					279.49079875959285,
					-15.107610743761825
				],
				[
					280.24617929678095,
					-15.107610743761825
				],
				[
					281.75694037115716,
					-15.107610743761825
				],
				[
					283.26770144553336,
					-14.352230206573722
				],
				[
					284.02308198272146,
					-14.352230206573722
				],
				[
					285.53384305709767,
					-14.352230206573722
				],
				[
					287.04460413147376,
					-14.352230206573722
				],
				[
					288.55536520584997,
					-14.352230206573722
				],
				[
					289.31074574303807,
					-14.352230206573722
				],
				[
					290.0661262802262,
					-14.352230206573722
				],
				[
					290.8215068174143,
					-14.352230206573722
				],
				[
					291.5768873546024,
					-14.352230206573722
				],
				[
					293.08764842897847,
					-14.352230206573722
				],
				[
					294.5984095033547,
					-14.352230206573722
				],
				[
					295.3537900405428,
					-14.352230206573722
				],
				[
					296.864551114919,
					-14.352230206573722
				],
				[
					297.6199316521071,
					-14.352230206573722
				],
				[
					298.3753121892951,
					-14.352230206573722
				],
				[
					299.1306927264832,
					-14.352230206573722
				],
				[
					299.8860732636713,
					-14.352230206573722
				],
				[
					300.6414538008594,
					-14.352230206573722
				],
				[
					302.9075954124237,
					-14.352230206573722
				],
				[
					305.1737370239879,
					-14.352230206573722
				],
				[
					307.4398786355522,
					-13.59684966938562
				],
				[
					310.4614007843046,
					-12.841469132197517
				],
				[
					313.4829229330569,
					-12.841469132197517
				],
				[
					314.9936840074331,
					-12.841469132197517
				],
				[
					316.5044450818093,
					-12.086088595009414
				],
				[
					317.2598256189973,
					-12.086088595009414
				],
				[
					318.0152061561854,
					-12.086088595009414
				],
				[
					318.7705866933735,
					-12.086088595009414
				],
				[
					319.5259672305616,
					-12.086088595009414
				],
				[
					320.2813477677497,
					-12.086088595009414
				],
				[
					321.0367283049378,
					-12.086088595009414
				],
				[
					321.7921088421259,
					-12.086088595009414
				],
				[
					322.547489379314,
					-12.086088595009414
				],
				[
					323.3028699165021,
					-12.086088595009414
				],
				[
					323.3028699165021,
					-11.330708057821312
				],
				[
					324.0582504536901,
					-11.330708057821312
				],
				[
					325.5690115280663,
					-10.57532752063321
				],
				[
					326.3243920652544,
					-9.819946983445334
				],
				[
					327.8351531396306,
					-9.064566446257231
				],
				[
					328.5905336768187,
					-9.064566446257231
				],
				[
					329.3459142140068,
					-9.064566446257231
				],
				[
					330.1012947511948,
					-9.064566446257231
				],
				[
					331.612055825571,
					-8.309185909069129
				],
				[
					332.3674363627591,
					-7.553805371881026
				],
				[
					333.1228168999472,
					-6.7984248346929235
				],
				[
					333.8781974371353,
					-6.7984248346929235
				],
				[
					335.38895851151153,
					-5.287663760316718
				],
				[
					336.14433904869963,
					-4.532283223128616
				],
				[
					337.6551001230757,
					-3.776902685940513
				],
				[
					338.41048066026383,
					-3.0215221487524104
				],
				[
					338.41048066026383,
					-2.266141611564308
				],
				[
					339.16586119745193,
					-2.266141611564308
				],
				[
					339.16586119745193,
					-1.5107610743762052
				],
				[
					339.92124173464003,
					-0.7553805371881026
				],
				[
					340.67662227182814,
					-0.7553805371881026
				],
				[
					340.67662227182814,
					0
				],
				[
					340.67662227182814,
					0.7553805371881026
				],
				[
					340.67662227182814,
					1.5107610743762052
				],
				[
					341.43200280901624,
					1.5107610743762052
				],
				[
					341.43200280901624,
					2.266141611564308
				],
				[
					341.43200280901624,
					3.776902685940513
				],
				[
					341.43200280901624,
					4.532283223128616
				],
				[
					341.43200280901624,
					5.287663760316491
				],
				[
					341.43200280901624,
					6.0430442975045935
				],
				[
					341.43200280901624,
					6.0430442975045935
				]
			],
			"lastCommittedPoint": null,
			"simulatePressure": true,
			"pressures": []
		},
		{
			"type": "text",
			"version": 282,
			"versionNonce": 223103232,
			"isDeleted": false,
			"id": "CjTlsc38",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1181.8833263055699,
			"y": -1443.8892675247334,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 90.73619079589844,
			"height": 20,
			"seed": 1419096895,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Non-Volatile",
			"rawText": "Non-Volatile",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Non-Volatile",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 554,
			"versionNonce": 249882880,
			"isDeleted": false,
			"id": "eyrSiuoSGnbqL8vv7oFBg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1146.7478430191711,
			"y": -802.6768505839395,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 91.57295813444239,
			"height": 2.353881416118611,
			"seed": 622524881,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "0S3bTA5g",
				"focus": -0.11558440865126476,
				"gap": 6.700460351301217
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
					91.57295813444239,
					2.353881416118611
				]
			]
		},
		{
			"type": "text",
			"version": 286,
			"versionNonce": 999164160,
			"isDeleted": false,
			"id": "0S3bTA5g",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1048.4744245334275,
			"y": -821.0227272324306,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 126.65628051757812,
			"height": 40,
			"seed": 654940529,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [
				{
					"id": "eyrSiuoSGnbqL8vv7oFBg",
					"type": "arrow"
				}
			],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "50% chance of\ndetecting errors",
			"rawText": "50% chance of\ndetecting errors",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "50% chance of\ndetecting errors",
			"lineHeight": 1.25,
			"baseline": 34
		},
		{
			"type": "frame",
			"version": 635,
			"versionNonce": 249261841,
			"isDeleted": false,
			"id": "560c-WfLUXNboaxEBe2U0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1886.9060741051894,
			"y": -1473.900936743965,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 1128.3333333333333,
			"height": 1242.547676006329,
			"seed": 1795861073,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708109815541,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#7A7A7A"
				}
			},
			"name": "Storage1"
		},
		{
			"type": "text",
			"version": 343,
			"versionNonce": 42285593,
			"isDeleted": false,
			"id": "7F2mdZsj",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1515.5878754090754,
			"y": -200.37579432278363,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 284.4532165527344,
			"height": 35,
			"seed": 1749064831,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 28,
			"fontFamily": 1,
			"text": "Storage computation",
			"rawText": "Storage computation",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Storage computation",
			"lineHeight": 1.25,
			"baseline": 25
		},
		{
			"type": "text",
			"version": 633,
			"versionNonce": 1105759993,
			"isDeleted": false,
			"id": "V8J6NFli",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1876.9698816276796,
			"y": -139.56374881632456,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1093.4788818359375,
			"height": 475,
			"seed": 565406993,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Disk properties:\n\n\n\n\n\nExample: Disk with 8 platters, 16 surfaces, 2  Tracks per surface, 2 Sectors per track, 2 Bytes per sector\n\n           \n          Block is 2  Bytes\n\n\n\n\n          Byte Density (Outermost Track):\n\n\n* Disk Access:  Transferring Delay  x  Seek time   x   Rotation time   x  Transfer time to controller\n",
			"rawText": "* Disk properties:\n\n\n\n\n\nExample: Disk with 8 platters, 16 surfaces, 2  Tracks per surface, 2 Sectors per track, 2 Bytes per sector\n\n           \n          Block is 2  Bytes\n\n\n\n\n          Byte Density (Outermost Track):\n\n\n* Disk Access:  Transferring Delay  x  Seek time   x   Rotation time   x  Transfer time to controller\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Disk properties:\n\n\n\n\n\nExample: Disk with 8 platters, 16 surfaces, 2  Tracks per surface, 2 Sectors per track, 2 Bytes per sector\n\n           \n          Block is 2  Bytes\n\n\n\n\n          Byte Density (Outermost Track):\n\n\n* Disk Access:  Transferring Delay  x  Seek time   x   Rotation time   x  Transfer time to controller\n",
			"lineHeight": 1.25,
			"baseline": 468
		},
		{
			"type": "text",
			"version": 326,
			"versionNonce": 1741572057,
			"isDeleted": false,
			"id": "d7wXObrQ",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1696.4681588128074,
			"y": -138.48234712466984,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 257.75970458984375,
			"height": 25,
			"seed": 592769631,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Disk Consists of Platters",
			"rawText": "Disk Consists of Platters",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Disk Consists of Platters",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 347,
			"versionNonce": 1045030073,
			"isDeleted": false,
			"id": "biqMfwLS",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1416.4672531035171,
			"y": -137.2067165747415,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 111.25987243652344,
			"height": 25,
			"seed": 1609093855,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "2 Surfaces",
			"rawText": "2 Surfaces",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "2 Surfaces",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 287,
			"versionNonce": 16704921,
			"isDeleted": false,
			"id": "OEo15cOV",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1433.6882655275513,
			"y": -139.12016239963424,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.239990234375,
			"height": 25,
			"seed": 271658175,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "x",
			"rawText": "x",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 322,
			"versionNonce": 723569273,
			"isDeleted": false,
			"id": "epfTzybV",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1283.1638606359963,
			"y": -135.9310860248127,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 284.33966064453125,
			"height": 25,
			"seed": 299812063,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Surfaces consist of  Tracks",
			"rawText": "Surfaces consist of  Tracks",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Surfaces consist of  Tracks",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 357,
			"versionNonce": 91427673,
			"isDeleted": false,
			"id": "6hvj1FNd",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1695.8303435378434,
			"y": -113.60755140106522,
			"strokeColor": "#9c36b5",
			"backgroundColor": "transparent",
			"width": 262.87969970703125,
			"height": 25,
			"seed": 2054379775,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Tracks can be divided into",
			"rawText": "Tracks can be divided into",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Tracks can be divided into",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 456,
			"versionNonce": 1950957625,
			"isDeleted": false,
			"id": "fg5gr9YO",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1416.0656942830594,
			"y": -113.30109389996989,
			"strokeColor": "#f08c00",
			"backgroundColor": "transparent",
			"width": 525.6194458007812,
			"height": 75,
			"seed": 45557457,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "A number of sectors Separated by gaps\nor\nTotal storage such that a percentage of it is gaps",
			"rawText": "A number of sectors Separated by gaps\nor\nTotal storage such that a percentage of it is gaps",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "A number of sectors Separated by gaps\nor\nTotal storage such that a percentage of it is gaps",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 402,
			"versionNonce": 92721433,
			"isDeleted": false,
			"id": "MUfesGHv",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1692.371913745937,
			"y": -34.76199727182194,
			"strokeColor": "#c2255c",
			"backgroundColor": "transparent",
			"width": 597.599365234375,
			"height": 25,
			"seed": 1679819007,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Blocks/Clusters are partial tracks spanning multiple sectors",
			"rawText": "Blocks/Clusters are partial tracks spanning multiple sectors",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Blocks/Clusters are partial tracks spanning multiple sectors",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 333,
			"versionNonce": 1050625529,
			"isDeleted": false,
			"id": "Pq0lIf4t",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1786.2777739779845,
			"y": 39.75111691187948,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 408.2196044921875,
			"height": 25,
			"seed": 1244037599,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Capacity: 16 x 2^16 x 2^8 x 2^12 = 1TB",
			"rawText": "Capacity: 16 x 2^16 x 2^8 x 2^12 = 1TB",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Capacity: 16 x 2^16 x 2^8 x 2^12 = 1TB",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "line",
			"version": 316,
			"versionNonce": 714481369,
			"isDeleted": false,
			"id": "rArBBXJeLI3pIqYkUkRpQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1720.1894271560363,
			"y": 299.16852376004874,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 191.37015064459877,
			"height": 0.8320441332375594,
			"seed": 2032319633,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1707943407384,
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
					191.37015064459877,
					-0.8320441332375594
				]
			]
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 671013817,
			"isDeleted": false,
			"id": "Vv8pBqyQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1781.5981250601849,
			"y": 431.773386687075,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 591.6994018554688,
			"height": 25,
			"seed": 317103025,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Move from one track to another in 1/4000 = 1 + 0.00025 ",
			"rawText": "Move from one track to another in 1/4000 = 1 + 0.00025 ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Move from one track to another in 1/4000 = 1 + 0.00025 ",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 359,
			"versionNonce": 1996291225,
			"isDeleted": false,
			"id": "Iy8TSIRg",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1777.5134692425058,
			"y": 402.10870863438606,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 279.419677734375,
			"height": 25,
			"seed": 2040810431,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1ms to start and stop head",
			"rawText": "1ms to start and stop head",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1ms to start and stop head",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 1263,
			"versionNonce": 121897337,
			"isDeleted": false,
			"id": "eAP2zhgr",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1777.55348815956,
			"y": 462.8545380935476,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1005.0390014648438,
			"height": 400,
			"seed": 1029326911,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Best case: Head is already on top of block we want to read (Seek time = 0 , rotation latency =0)\nReading 1 block  = 4 sectors seperated by 3 gaps\nif gaps are 10% of track then 256 Gaps cover 36 degrees = 36/256\nif sectors are 90% of track then 256 sectors cover 324 degrees = 324/256\nReading: 4*324/256 + 3*36/256   => degree/360 * Rotation speed\n\nWorst case: Must travel from first to last track, Must rotate the entire track to start Transfer\nReading time (same as above) + full rotation + switching across all tracks\n\nAverage Case: avg Seek distance = 1/3 of tracks + avg rotation = 1/2 of track\nReading time (same as above) + 1/2 full rotation + switching 1/3 of all tracks\n\n* If the blocks are sequentially stored, we do not need to seek/rotate to read them\n* If the blocks are randomly distributed we use the Avg seek time + Avg rotation time to get each\n  block\n",
			"rawText": "Best case: Head is already on top of block we want to read (Seek time = 0 , rotation latency =0)\nReading 1 block  = 4 sectors seperated by 3 gaps\nif gaps are 10% of track then 256 Gaps cover 36 degrees = 36/256\nif sectors are 90% of track then 256 sectors cover 324 degrees = 324/256\nReading: 4*324/256 + 3*36/256   => degree/360 * Rotation speed\n\nWorst case: Must travel from first to last track, Must rotate the entire track to start Transfer\nReading time (same as above) + full rotation + switching across all tracks\n\nAverage Case: avg Seek distance = 1/3 of tracks + avg rotation = 1/2 of track\nReading time (same as above) + 1/2 full rotation + switching 1/3 of all tracks\n\n* If the blocks are sequentially stored, we do not need to seek/rotate to read them\n* If the blocks are randomly distributed we use the Avg seek time + Avg rotation time to get each\n  block\n",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Best case: Head is already on top of block we want to read (Seek time = 0 , rotation latency =0)\nReading 1 block  = 4 sectors seperated by 3 gaps\nif gaps are 10% of track then 256 Gaps cover 36 degrees = 36/256\nif sectors are 90% of track then 256 sectors cover 324 degrees = 324/256\nReading: 4*324/256 + 3*36/256   => degree/360 * Rotation speed\n\nWorst case: Must travel from first to last track, Must rotate the entire track to start Transfer\nReading time (same as above) + full rotation + switching across all tracks\n\nAverage Case: avg Seek distance = 1/3 of tracks + avg rotation = 1/2 of track\nReading time (same as above) + 1/2 full rotation + switching 1/3 of all tracks\n\n* If the blocks are sequentially stored, we do not need to seek/rotate to read them\n* If the blocks are randomly distributed we use the Avg seek time + Avg rotation time to get each\n  block\n",
			"lineHeight": 1.25,
			"baseline": 393
		},
		{
			"type": "text",
			"version": 456,
			"versionNonce": 102197849,
			"isDeleted": false,
			"id": "IeZyUleK",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1875.3609704846706,
			"y": 845.7647878491645,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 958.9991455078125,
			"height": 25,
			"seed": 144643217,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "* Change of disk: Time of reading + Time of writing (cant modify directly, need to pull in memory)",
			"rawText": "* Change of disk: Time of reading + Time of writing (cant modify directly, need to pull in memory)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "* Change of disk: Time of reading + Time of writing (cant modify directly, need to pull in memory)",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "frame",
			"version": 584,
			"versionNonce": 1486710001,
			"isDeleted": false,
			"id": "GdzRpn6jzmGRFFGs9inlw",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -1893.194417694916,
			"y": -200.37579457678234,
			"strokeColor": "#bbb",
			"backgroundColor": "transparent",
			"width": 1123.4141046563545,
			"height": 1083.304240392385,
			"seed": 291884927,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1708109815541,
			"link": null,
			"locked": false,
			"customData": {
				"frameColor": {
					"stroke": "#D4D4D4",
					"fill": "#ADADAD",
					"nameColor": "#7A7A7A"
				}
			},
			"name": "Storage2"
		},
		{
			"type": "text",
			"version": 308,
			"versionNonce": 743094073,
			"isDeleted": false,
			"id": "vw3ad9jR",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1300.2645307025398,
			"y": -137.58822635042117,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 11.239990234375,
			"height": 25,
			"seed": 1886973777,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "x",
			"rawText": "x",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "x",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 337,
			"versionNonce": 1279354905,
			"isDeleted": false,
			"id": "rxXFm0rU",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1422.072207948878,
			"y": 1.9034032613969316,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.576034545898438,
			"height": 20,
			"seed": 912197841,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "16",
			"rawText": "16",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "16",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 315,
			"versionNonce": 535756025,
			"isDeleted": false,
			"id": "zya6Hm3F",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1182.5145361757227,
			"y": 4.272461630769328,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 12.240020751953125,
			"height": 20,
			"seed": 377164479,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "8",
			"rawText": "8",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "8",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 314,
			"versionNonce": 1456928217,
			"isDeleted": false,
			"id": "tV1hzGRs",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -968.2759679233075,
			"y": 1.3510266091458902,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 15.728042602539062,
			"height": 20,
			"seed": 238597841,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "12",
			"rawText": "12",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "12",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 341,
			"versionNonce": 1678561977,
			"isDeleted": false,
			"id": "0l9WPci4",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1679.1584898517763,
			"y": 78.83452549749171,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 14.576034545898438,
			"height": 20,
			"seed": 2041100639,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "14",
			"rawText": "14",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "14",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 621,
			"versionNonce": 204739481,
			"isDeleted": false,
			"id": "IZUjqCrS",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1777.5134689131123,
			"y": 114.31318077860004,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 675.601318359375,
			"height": 60,
			"seed": 542486655,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Byte per Block                              Sectors Per block\n_________ = Sector per Block          ____________ = Blocks per Track\nByte per Sector                             Sectors Per Track",
			"rawText": "Byte per Block                              Sectors Per block\n_________ = Sector per Block          ____________ = Blocks per Track\nByte per Sector                             Sectors Per Track",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Byte per Block                              Sectors Per block\n_________ = Sector per Block          ____________ = Blocks per Track\nByte per Sector                             Sectors Per Track",
			"lineHeight": 1.25,
			"baseline": 54
		},
		{
			"type": "text",
			"version": 385,
			"versionNonce": 864041081,
			"isDeleted": false,
			"id": "GUpjw1q1",
			"fillStyle": "solid",
			"strokeWidth": 0.5,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1773.7699664366114,
			"y": 245.85211737560593,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 303.3446350097656,
			"height": 20,
			"seed": 235667345,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Bytes per Sector x Sectors per track",
			"rawText": "Bytes per Sector x Sectors per track",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Bytes per Sector x Sectors per track",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 433,
			"versionNonce": 1807008089,
			"isDeleted": false,
			"id": "ioqsTSf3",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1778.4246818652023,
			"y": 323.81905031171016,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 399.6595458984375,
			"height": 75,
			"seed": 1266152657,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "7200 RPM = 60s x 1000ms\n              ________  = 8.333ms\n             7200 rotations",
			"rawText": "7200 RPM = 60s x 1000ms\n              ________  = 8.333ms\n             7200 rotations",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "7200 RPM = 60s x 1000ms\n              ________  = 8.333ms\n             7200 rotations",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "text",
			"version": 393,
			"versionNonce": 341821696,
			"isDeleted": false,
			"id": "0QxbitKm",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1737.8773451228067,
			"y": -646.332775720258,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 748.6734619140625,
			"height": 20,
			"seed": 1873153041,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Strg Eff: 100%  Cost: low  Protection: none    read: done in parallel    write: done in parallel",
			"rawText": "Strg Eff: 100%  Cost: low  Protection: none    read: done in parallel    write: done in parallel",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Strg Eff: 100%  Cost: low  Protection: none    read: done in parallel    write: done in parallel",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 528,
			"versionNonce": 1736354048,
			"isDeleted": false,
			"id": "xeAQy9Bc",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1734.0103140286456,
			"y": -564.0153219912265,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 858.16162109375,
			"height": 20,
			"seed": 1119941745,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Strg Eff: 50%  Cost: high  Protection: 1 disk can fail    read: better than 1disk    write: worse than 1 disk",
			"rawText": "Strg Eff: 50%  Cost: high  Protection: 1 disk can fail    read: better than 1disk    write: worse than 1 disk",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Strg Eff: 50%  Cost: high  Protection: 1 disk can fail    read: better than 1disk    write: worse than 1 disk",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 599,
			"versionNonce": 868321536,
			"isDeleted": false,
			"id": "2Z34nRuY",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1733.6617196189063,
			"y": -495.521727289042,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 778.097412109375,
			"height": 20,
			"seed": 1462826527,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Strg Eff: 50%  Cost: high  Protection: N/2    read: better than 1disk    write: worse than 1 disk",
			"rawText": "Strg Eff: 50%  Cost: high  Protection: N/2    read: better than 1disk    write: worse than 1 disk",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Strg Eff: 50%  Cost: high  Protection: N/2    read: better than 1disk    write: worse than 1 disk",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 730,
			"versionNonce": 883452160,
			"isDeleted": false,
			"id": "W5VNV88l",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1732.7367293063492,
			"y": -419.51845437255173,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 923.8258056640625,
			"height": 20,
			"seed": 223484159,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Strg Eff: 1Additional Cost: low  Protection: 1disk can fail  read: done in parallel    write: write in parallel +overhead",
			"rawText": "Strg Eff: 1Additional Cost: low  Protection: 1disk can fail  read: done in parallel    write: write in parallel +overhead",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Strg Eff: 1Additional Cost: low  Protection: 1disk can fail  read: done in parallel    write: write in parallel +overhead",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 824,
			"versionNonce": 900942080,
			"isDeleted": false,
			"id": "QaNOfZe5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1735.4428872747746,
			"y": -341.6856096953304,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 894.7537841796875,
			"height": 20,
			"seed": 999542079,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Strg Eff:N-1  Cost: Medium  Protection: 1disk can fail  read: done in parallel    write: write in parallel +overhead",
			"rawText": "Strg Eff:N-1  Cost: Medium  Protection: 1disk can fail  read: done in parallel    write: write in parallel +overhead",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Strg Eff:N-1  Cost: Medium  Protection: 1disk can fail  read: done in parallel    write: write in parallel +overhead",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 892,
			"versionNonce": 308422912,
			"isDeleted": false,
			"id": "GnwCCn7P",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1732.3048729157738,
			"y": -262.3561964930725,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 908.8658447265625,
			"height": 20,
			"seed": 1387514687,
			"groupIds": [],
			"frameId": "560c-WfLUXNboaxEBe2U0",
			"roundness": null,
			"boundElements": [],
			"updated": 1707838089515,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Strg Eff:N-2  Cost: Medium  Protection: 2disk can fail  read: done in parallel    write: write in parallel +overhead",
			"rawText": "Strg Eff:N-2  Cost: Medium  Protection: 2disk can fail  read: done in parallel    write: write in parallel +overhead",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Strg Eff:N-2  Cost: Medium  Protection: 2disk can fail  read: done in parallel    write: write in parallel +overhead",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 189,
			"versionNonce": 1109732921,
			"isDeleted": false,
			"id": "XEYdF3Nx",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1778.2680951540917,
			"y": 463.6227689238108,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 102.81988525390625,
			"height": 25,
			"seed": 235801212,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Best case",
			"rawText": "Best case",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Best case",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 89,
			"versionNonce": 1303707417,
			"isDeleted": false,
			"id": "h0ShDsNf",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1778.420847799948,
			"y": 612.8163752282721,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 111.93986511230469,
			"height": 25,
			"seed": 709818564,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Worst case",
			"rawText": "Worst case",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Worst case",
			"lineHeight": 1.25,
			"baseline": 18
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 2094511097,
			"isDeleted": false,
			"id": "jwlaJ3cj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1776.8795482496328,
			"y": 686.9946716701656,
			"strokeColor": "#2f9e44",
			"backgroundColor": "transparent",
			"width": 135.43984985351562,
			"height": 25,
			"seed": 804552132,
			"groupIds": [],
			"frameId": "GdzRpn6jzmGRFFGs9inlw",
			"roundness": null,
			"boundElements": [],
			"updated": 1707943407384,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Average Case",
			"rawText": "Average Case",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Average Case",
			"lineHeight": 1.25,
			"baseline": 18
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
		"scrollX": 3358.026436376243,
		"scrollY": 1680.4639240356096,
		"zoom": {
			"value": 0.35000000000000003
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