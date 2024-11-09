---
excalidraw-plugin: parsed
tags:
  - excalidraw
  - databases
---
Includes parts of [[Storage]]
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Excalidraw Data
## Text Elements
* Disk properties:





Example: Disk with 8 platters, 16 surfaces, 2  Tracks per surface, 2 Sectors per track, 2 Bytes per sector

           
          Block is 2  Bytes




          Byte Density (Outermost Track):


* Disk Access:  Transferring Delay  x  Seek time   x   Rotation time   x  Transfer time to controller
 ^B2DbqlTc

Disk Consists of Platters ^JlCuwr5R

2 Surfaces ^iGvi7u8x

x ^BY0SmTyf

Surfaces consist of  Tracks ^WfjOLOSM

Tracks can be divided into ^kAO5hCjq

A number of sectors Separated by gaps
or
Total storage such that a percentage of it is gaps ^cuozIz5L

Blocks/Clusters are partial tracks spanning multiple sectors ^e9gi4vpj

Capacity: 16 x 2^16 x 2^8 x 2^12 = 1TB ^dKIMjwPr

Move from one track to another in 1/4000 = 1 + 0.00025  ^zANZHadV

1ms to start and stop head ^VOdjPhG6

Best case: 
Head is already on top of block we want to read
Example:
Reading 1 block  = 4 sectors separated by 3 gaps

if gaps are 10% of track then 256 Total Gaps cover 360*10% = 36 degrees => 36/256
if sectors are 90% of track then 256 Total sectors cover 360*90% = 324 degrees => 324/256

Transfer one block: 4 * 324/256 + 3 * 36/256   =>  result degree/360 * Rotation speed

Worst case:

Transfer time (same as above) + full rotation of disk + switching from innermost to outermost track



Average Case: (Random or not)
avg Seek distance = 1/3 of tracks             avg rotation = 1/2 of track
Reading time (same as above) + avg rotation + avg seek distance

* If the blocks are sequentially stored, we only use avg seek and avg rotation once ^UpXPIlN7

* Change values in disk: Time of reading + Time of writing (cant modify directly, need to pull in memory) ^mg8Ux6ul

x ^1qWfF2JE

16 ^0Z7q6i5n

8 ^7Ww1Bgtk

12 ^8a2K1JXG

14 ^WMM5LeDg

Byte per Block                              Sectors Per block
_________ = Sector per Block          ____________ = Blocks per Track
Byte per Sector                             Sectors Per Track ^RPgE9g5N

Bytes per Sector x Sectors per track ^Zse9xltA

7200 RPM = 60s x 1000ms
              ________  = 8.333ms
             7200 rotations ^2eJkcfDD

Best case ^G4zNDsMM

Worst case ^j5UsoEEF

Average Case ^cu737Eyu

(Seek time = 0 , rotation latency =0) ^GxrAWCQk

10% ^PawZjgz3

256 Total Gaps ^13btyKpW

360*10% = 36 degrees ^wRrPNqjL

36/256 ^PN0BBiqp

90% ^LzaZdgYo

256 Total sectors ^XlMb8LtD

360*90% = 324 degrees ^qkXwybXw

324/256 ^X5s0j0fn

4 * 324/256 + 3 * 36/256 ^UwR35QQL

result degree/360 * Rotation speed ^IdNEC2S5

Must travel from first to last track, Must rotate the entire track to start Transfer ^Naa0jVDH

full rotation of disk ^62EdyxNA

switching from innermost to outermost track ^jXfxJvJN

Number of tracks * Transfer speed between 2 tracks + start/stop head ^bjOKdSAH

avg Seek distance = 1/3 of tracks             avg rotation = 1/2 of track ^2gN58PRt

* If the blocks are randomly distributed we use the Avg seek time + Avg rotation time to get each
  block ^XbTqbUOz

* Bitmap indexing:
  Each value of each attribute has an N length bitmap that indicates (1,0) membership
  Attributes do not span each others blocks and are usually Byte aligned ^BAZQmUMf

When to stop?
If the Number of nodes < Full capacity of Node
We test this condition against full capacity not avg
capacity because root can exceed it! ^z0bGqtSl

Amdahls Law ^sLfjWqCn

Gustafons Law ^NJwzLTV3

* B+Tree





 ^BdJK0mKU

Too unnecessary to go into detail since we did the project :] ^YhVM5Xtm

Search: h I/O for path + 1 I/O for reading of block
Range query: h I/O for path + n I/O for reading of n data
Insertion: if space h + 1 I/O , If no space 3h + 1 I/O
Deletion: if enough h + 1 I/O, If not enough 3h I/O ^vZti3D33

*B+Tree Calculation: ^TPMS4nPV

ceiling or floor
depending on
if they span ^d6uPDAkv

Ceiling ^Qilswfy3

repeat until you get
a number that is smaller
than capacity of one leaf
iterations = height ^NbVdO03a

Total I/O = height + amount of requests/blocks needed ^XhG68tpI

Bytes per One unique value's bitmap = Align(Number of records / 8bits)  ^jGhJ2S2w

Bytes per the entire BitmapIndex = Bytes per one * Number of unique values  ^zzcKsq2i

* Projection estimation: Immediate estimation of tuple size according to attributes (straightforward)
* Selection estimation:
                                                                           5)
1)                                 3)     

2)                                4)



* Join Size/Cardinality estimation:

1) T(R ⋈ S) =                    2) T(R(Y1, Y2) ⋈ S(Y1, Y2)) = 


* When Predicate joining R⋈σ(S) =  T(R) * 1/V(S)


* Join Cost/order estimation:
  R ⋈ S, such that R and S can contain more joins in them = Sum of Size of intermediate joins 

* Union estimation:  AVG[T(R) + T(S), max[T(R), T(S)] ]
* Intersection estimation: consider as join
* Difference estimation: T(R) – T(S)/2
* Duplicate elimination estimation: min[T(R)/2, ∏i V(R, Ai)]
* Aggregation estimation:  min[T(R)/2, ∏i V(R, Li)] ^SgvMhPDL

Assuming theyre independent ^D9uDWPht

general approach: Multiply all the cardinalities, divided by selectivity.
to get selectivity, if attribute occurs once dont add it, if it occurs more than once then add all its values except smallest ^uysjnXe2

T1 + T2 - (T1 * T2) ^eHretxwt

Ti being tuples that satisfy
condition i ^8KYUTKwx

Or also
n(1 - F1 - F2) ^JDVbzR4X

fraction of
records that dont
satisfy cond1 ^gz2XPGqM

fraction of
records that dont
satisfy cond2 ^6RQUvJbZ

ignore cross products when considering cheapest cost, theyre expensive ^eXYQX6uR

P is the fraction that can be parallelized ^RzJ3RPnl

1-P is the fraction of the program that is serial ^a8vexq81

N is infinity (Number of processors) ^VvPqal2K

P is the fraction that can be parallelized ^RXgrqeXP

1-P is the fraction of the program that is serial ^FgssZJk1

N is infinity (Number of processors) ^6XeZeqm7

* Bitmap indexing:
  Each value of each attribute has an N length bitmap that indicates (1,0) membership
  Attributes do not span each others blocks and are usually Byte aligned ^8mvLcARV

When to stop?
If the Number of nodes < Full capacity of Node
We test this condition against full capacity not avg
capacity because root can exceed it! ^V4ewbdD1

Amdahls Law ^XmK3vyqz

Gustafons Law ^MDTX6al6

* B+Tree





 ^dUwCpULG

Too unnecessary to go into detail since we did the project :] ^mUqra9iU

Search: h I/O for path + 1 I/O for reading of block
Range query: h I/O for path + n I/O for reading of n data
Insertion: if space h + 1 I/O , If no space 3h + 1 I/O
Deletion: if enough h + 1 I/O, If not enough 3h I/O ^Z1fykADs

*B+Tree Calculation: ^5Kgt5qBG

ceiling or floor
depending on
if they span ^JoL68gar

Ceiling ^cNu0ZuFd

repeat until you get
a number that is smaller
than capacity of one leaf
iterations = height ^gWXtgeon

Total I/O = height + amount of requests/blocks needed ^7bRoCPSJ

Bytes per One unique value's bitmap = Align(Number of records / 8bits)  ^WjXck3bo

Bytes per the entire BitmapIndex = Bytes per one * Number of unique values  ^BIlRRHa3

* Projection estimation: Immediate estimation of tuple size according to attributes (straightforward)
* Selection estimation:
                                                                           5)
1)                                 3)     

2)                                4)



* Join Size/Cardinality estimation:

1) T(R ⋈ S) =                    2) T(R(Y1, Y2) ⋈ S(Y1, Y2)) = 


* When Predicate joining R⋈σ(S) =  T(R) * 1/V(S)


* Join Cost/order estimation:
  R ⋈ S, such that R and S can contain more joins in them = Sum of Size of intermediate joins 

* Union estimation:  AVG[T(R) + T(S), max[T(R), T(S)] ]
* Intersection estimation: consider as join
* Difference estimation: T(R) – T(S)/2
* Duplicate elimination estimation: min[T(R)/2, ∏i V(R, Ai)]
* Aggregation estimation:  min[T(R)/2, ∏i V(R, Li)] ^0AABx5cA

Assuming theyre independent ^FxHclTyz

general approach: Multiply all the cardinalities, divided by selectivity.
to get selectivity, if attribute occurs once dont add it, if it occurs more than once then add all its values except smallest ^csOHGHuS

T1 + T2 - (T1 * T2) ^37Dw9BLW

Ti being tuples that satisfy
condition i ^gQ3jfcl1

Or also
n(1 - F1 * F2) ^AGZwwqFy

fraction of
records that dont
satisfy cond1 ^g924GXKg

fraction of
records that dont
satisfy cond2 ^HZOif7BD

ignore cross products when considering cheapest cost, theyre expensive ^6rUoRIL6

P is the fraction that can be parallelized ^gBHEraQm

1-P is the fraction of the program that is serial ^gxyhUCEz

N is infinity (Number of processors) ^9egZraEt

P is the fraction that can be parallelized ^kqe5XnE4

1-P is the fraction of the program that is serial ^cN2aQMEi

N is infinity (Number of processors) ^RXrwduJK

## Embedded Files
df82cc29b17347ae1505feefc8be9e396e01cc9a: $$\color{green} \frac{Size_{Block}}{Size_{Tuples}} = \#_{Tuples\in Block}$$

4bb8738879895bc87bf4f928b575077e63ebf4b7: $$\color{green} \frac{\#_{Tuples\in request}}{\#_{Tuples\in block}} = \#_{BlocksNeeded}$$

34b4f03acf9264ec6fd1175696bb6faa280018ad: $$\color{green} Ceil( Floor(\frac{Size_{Block}-Size_{pointerToNextLeaf}}{Size_{IndexPointer}}) * Fillrate_{avg})= \#_{IndexPerLeaf}$$

e4e0f7932dcbfbb98fc366d5d8f5d0d2efe027b9: $$\color{green} Ceil(\frac{\#_{Indexes}}{\#_{indexesPerLeaf}} )= \#_{Leaves} $$

e4b98149a1d56b9abc4d867de3ad571dbf869886: $$\color{green} Ceil( Floor(\frac{Size_{Block}}{Size_{IndexPointer}}) * Fillrate_{avg})= \#_{IndexPerInner}$$

1bbd1228fc918b2c783502f03c6c3a40c7f8fb82: $$\color{green} Ceil(\frac{\#_{Indexes}}{\#_{indexesPerInner}} )= \#_{InnerNodes} $$

ee4902ac75726c40df88910d35b468a78ebbe537: $$\color{blue} \sigma_{A=c}(R)$$

e2a949f5a6ea2f2007901ddf9e1e98c4be24dc49: $$\color{blue} \frac{T(R)}{V(A,R)}$$

9789e63510b35a59776f6ef00c5931f448362891: $$\color{blue} \sigma_{A<c}(R)$$

6aebf21f5bd3360101202b656c2eebf87ceaa367: $$\color{blue} \frac{T(R)}{3}$$

9809ba89258518ae1d9cdfa59ed4bd04763bb1a5: $$\color{blue} \sigma_{A\neq c}(R)$$

562c9ec3ed619fb318620d64af294861c04cce69: $$\color{blue} \frac{T(R)(V(A,R)-1)}{V(A,R)}$$

499bb3a73b9840bff138577f61013256efe02459: $$\color{blue} \sigma_{\text{Cond1 AND Cond2}}(R)$$

7d1c59a75b65c70fdb3b675f4883c72a4338a376: $$\color{blue} \sigma_{Cond1}(R) \cdot \sigma_{Cond2}(R)$$

b8a6ebcff6df0f8e49aa748567e06bf9a5dfef13: $$\color{blue} \sigma_{\text{Cond1 OR Cond2}}(R)$$

21f377a1f8bd9cd9450e1c71825bf46097da4909: $$\color{blue} \frac{T(R)·T(S)}{max[V(R,Y),V(S,Y)]}$$

ae3a54012a24636f7e1079597abca532e65cb6bf: $$\color{blue}\frac{T(R) · T(S)}{ ( max[V(R,Y1),V(S,Y1)] \cdot max[V(R,Y2),V(S,Y2)] }$$

fb979275d5b35ef2ad2f3c6c8da3ff2f4b00b1d5: $$SpeedUp = \frac{1}{1 - P + \frac{P}{N}}$$

afa61bc4e3b72925961a7daf14ad10b6b2f5403c: $$SpeedUp_{Weak} = (1-P) + N \cdot P$$

%%
## Drawing
```compressed-json
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

w90EAA==
```
%%