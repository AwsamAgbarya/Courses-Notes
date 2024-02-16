- Various ways of initializing npArrays:
	- np.zeros(size)
	- np.ones(size)
	- np.full(size,val)
	- np.empty(size)
	- np.arange(start:end:step)
	- np.linspace(startval,endval,size)
	- np.repeat(containee,times,axis)
- numpy casting with array.astype(type)
- All basic operations are element wise operations OR used with scalars
- Supports slicing and smart indexing like arr[0,1,2]
### Numpy functions:
##### Random: 
- randint (low high size) returns random integers
- rand(dimensions) returns a random value in a certain shape
- randn(dimensions) returns a sample from the normal distribution
- random(size) returns a value between 0 and 1 
- random.randint(low,high,size)
- seed(seed) reseed the instance
- shuffle(array) shuffle the sequence around randomly
- uniform(low,high,size) all samples have equal probability
- rng.normal(mean,cov,size) is the gaussian distribution
#### Padding:
```python
pad_shape = (
    (0, 0),  # Add no row at the top and no row at the bottom
    (1, 0),  # Add one column at the left and no column at the right
)
transition = np.pad(arr,pad_shape,constant_values=0) 
```
#### Array:
* cumsum(arr,axis) Cumulative sum
* vstack(a,b) appends 2 arrays while keeping the objects
* hstack(a,b) appends 2 arrays horizontally 
* argmin/max  returns index of min/max
* Unique(arr, return_index, return_counts) returning unique elements of arrays
* expand_dims(arr, axis) expanding the dimension of an array
* argwhere(a) returns indices of non-zero elements
* where(cond, [x,y]) returns elements that match the condition (returns x otherwise y)
* put(a,indices,values) replaces indices in a with values
* hsplit(a,number) splits array horizontally given a number of elements
#### Linear Algebra:
* inv inverse matrix()
* eig returns eigen values vectors
* det returns determinant
* identity(size) to create an identity matrix
* einsum('ii->i',a) returns the diagonal einsum('ii',a) returns sum of diagonal
## Broadcasting:
- When preforming operations on mismatched shapes broadcasting is required in order to expand one of the sides dimensions in order to preform an element-wise operation.
- always start from the end dimensions and count down.
	- if you encounter a 1, the other dimension takes over
	- if you encounter 2 dimensions with the same length, that dimension stays
	- otherwise they are not broadcastable
- Broadcasting with [None,:] or [:,None] or np.newaxis
### Matrix multiplication:
- First take First's last two dimensions and Last's first two dimensions and multiply them
- Broadcast the rest
### Transposing:
- Array.T flips the axis 
- Array.transpose(indices) transposes the arrays axis according to the indices of the original axis
- array.reshape() keeps the data in the same order but changes the dimensions accordingly, You are allowed to use '...' to indicate all previous indexes
- Flatten() turns the array into one dimensional

