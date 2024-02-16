## Basic Operations:
- x\*\*y = x^y
- x//y = floor(x/y)
- x<<y = Bit-shifting
- x is y = Reference checking x to y
*Note that basic operations can also be used on strings!*

## Types and Variables:
- Types in python are dynamically assigned.
- The type of each variable can be identified using type(x)
	- Type conversion can be executed with calling the class name of the variable accordingly e.g int('1')
- Strings and Boolean can be treated as numbers too
	- Empty string = 0, otherwise = 1
	- True = 1, False = 0
- Other types can be converted into bool too
	- Empty strings, empty containers and the numbers 0 are considered false
	- Vice versa is considered true
	-  When comparing between non-boolean operators:
		- Or operation return the first True or the last False
		- And operation return the last True or the first False
## Containers:
#### Container Operations:
*All containers support the word _in_ to check for sub-containers*
*All containers support unpacking with \* except dictionaries which require\*\**
*Comparison operators on arrays operate element-wise and can be used to index and slice, to combine conditions please use the operators & | ~ 
- Sum, Mean, Avg, Std (All support Axis notation) and keepdims=true
- np.all checks if all elements of an array are true
- np.any checks if any elements are true
### 1. Lists:
	- Indicated by [] or list()
	- concatenated with +
	- can be negatively indexed to count backwards.
	- Slicable
	- List comprehension [Value if condition else Value for i in x]
### 2. Tuples:
	- Indicated by () or tuple()
	- Imuutable list.
	- requires trailing comma if singular
### 3. Sets:
	- Indicated by set()
	- Unordered and unindexed
	- unique in its elements
	- requires add() or update() in order to be updated
### 4. Dictionaries:
	- Indicated by {} or dict()
	- key-value pair that can be updated
	- can be set to default
	- keys can be immutable objects
	- unpacked with ** or zip()
	- Dictionary comprehension [key,value for pair in zip(keys,values)]
### 5. Strings:
	- Uses ''' to span multiple lines
	- strings are immutable
	- has loads of helpful functions including .stip() .join() .split() .find()
	- string templates can be formatted with .format(params)

## Lambda functions:
- In-line function that takes up one line.
- defined as Lambda parameters: value_to_return
- can be combined with dictionaries or filter()


### Classes:
- #### functions: 
	* isinstance(), issubclass() are methods that can help with identifying classes
	- dir() lists attributes and method names in class
	- getAttribute(obj, name) returns the attribute of said object
	- __call__ is called after calling an instance of a certain class
	- in inheritance you can call super() or otherwise obj.init in order to initialize it
	- Context managers are used with _ enter _ and _ exit _
	- operators can be defined in _ add _ and _ mul _
	- these operators can also store the value in itself via rmul and iadd
	- other special methods like len, contains, iter, setitem, delitem, getitem
- #### Static vs local vs class:
	- Static attributes are defined without self.
	- local attributes are defined with self.
	- local functions have self as the first parameter
	- static functions have a static decorator and do very general stuff
	- class functions have a class decorator and their first parameter is cls which points at the class
- #### Misc:
	- Use \*args to unpack a lot of arguments
	- Use \*\*kargs to unpack keyworded arguments

### Decorators:
- @funcname wraps that function with your funcname
- @lrucache to cache memory

### Generators:
- are functions you can pause and rerun
- identified by yield or () comprehension
- are lazily evaluated

### Iter package:
* import itertools as it
* islice(set, start,finish) to slice the set up
* combinations(list, size) provides all unique combinations
* combinations_with_replacement(list, size) provides all combinations 
* permutations(list) provides all permutations
* product(a,b) Cartesian product

### Reading/Writing data from a file:
```python
with open(path, 'r') as fd:
   for line in fd
```
```python
def write(data, outfile='outputs.txt', folder='./data'):
	os.makedirs(folder, exist_ok=True)
    filepath = os.path.join(folder, outfile)
    if os.path.exists(filepath):
            
            raise RuntimeError(f"File '{filepath}' already exists.")

        with open(filepath, 'w') as f:  # 'a'
            
            f.write(str(data))
```

**Refer to the [[CheatSheet]] for summary**
