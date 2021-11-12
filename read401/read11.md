## JupyterLab 
is a next-generation web-based user interface for Project Jupyter.
- **Code Consoles** provide transient scratchpads for running code interactively, with full support for rich output
- **Kernel-backed** documents enable code in any text file (Markdown, Python, R, LaTeX, etc.) to be run interactively in any Jupyter kernel.
- Notebook cell outputs can be mirrored into their own tab, side by side with the notebook, enabling simple dashboards with interactive controls backed by a kernel.
- Multiple views of documents with different editors or viewers enable live editing of documents reflected in other viewers.
- JupyterLab also offers a unified model for viewing and handling data formats and understands many file formats 
- JupyterLab offers customizable keyboard shortcuts and the ability to use key maps from vim, emacs, and Sublime Text in the text editor.
- JupyterLab extensions can customize or enhance any part of JupyterLab, including new themes, file editors, and custom components.
- JupyterLab is served from the same server and uses the same notebook document format as the classic Jupyter Notebook.

## Numpy tutorial 
**NumPy** is a commonly used Python data analysis package
- With NumPy, we can work with multidimensional arrays
- the core of NumPy is written in a programming language called C, which stores data differently than the Python data types. NumPy data types map between Python and C, allowing us to use NumPy arrays without any conversion hitches.
- NumPy has several different data types :
  - float, int, string and object (Python objects)

- **advantages of NumPy :**
  -  it simple to perform mathematical operations on arrays
  - and makes it quite easy to do computations.
- NumPy makes it possible to test to see if rows match certain values using mathematical comparison operations 
- With NumPy, it’s very common to combine multiple arrays into a single unified array

### Creating A NumPy Array:
`import numpy as np`
`numpyarray = np.array(ordinaryArray[1:], dtype=np.float)`
### Alternative NumPy Array Creation Methods
- `empty_array = np.zeros((3,4))` create zeroes element array with three row and four columns
- `np.random.rand(3,4)` create array with random number element
### Using NumPy To Read In Files
`data = np.genfromtxt("file.csv", delimiter=";", skip_header=1)`
  - `skip_header=1` so that the header row is skipped.
  - `genfromtxt` function to read in the file.csv file.
### Indexing NumPy Arrays
`numpyarray[2,3]`

### Slicing NumPy Arrays
`numpyarray[0:3,3]`
  - we can do it using a colon (:). A colon indicates that we want to select all the elements from the starting index up to but not including the ending index.

### Assigning Values To NumPy Arrays
`numpyarray[1,5] = value`

- 1-Dimensional NumPy Arrays
  - NumPy is a package for working with multidimensional arrays. One of the most common types of multidimensional arrays is the 1-dimensional array, or vector.
- N-Dimensional NumPy Arrays
### Converting Data Types
- You can use the `numpy.ndarray.astype` method to convert an array to a different type. The method will actually copy the array, and return a new array with the specified data type.

- We can check the name property of the dtype of the resulting array to see what data type NumPy mapped the resulting array to
  - `nparray.dtype.name`

- if you want more control over how the array is stored in memory, you can directly create NumPy dtype objects like `np.int32`

### NumPy Array Operations
- Single Array Math :
  - if you do any of the basic mathematical operations (/, *, -, +, ^) with an array and a value, it will apply the operation to each of the elements in the array.
  - If we instead did +=, we’d modify the array in place
    - `npArray[:,11] += 10`

  - Multiple Array Math 
    - It’s also possible to do mathematical operations between arrays `npArray1[:,11] + npArray1[:,11]`
- Broadcasting :
Unless the arrays that you’re operating on are the exact same size, it’s not possible to do elementwise operations. In cases like this, NumPy performs broadcasting to try to match up elements
  - broadcasting involves a few steps:
    - The last dimension of each array is compared :
      - If the dimension lengths are equal, or one of the dimensions is of length 1, then we keep going.
      - If the dimension lengths aren’t equal, and none of the dimensions have length 1, then there’s an error.
    - Continue checking dimensions until the shortest array is out of dimensions.


### NumPy Array Methods
-  `np.npArray.sum ()` : This finds the sum of all the elements in an array
  -  `sum(axis=0)` We can pass the axis keyword argument into the sum method to find sums over an axis
  - We can verify that we did the sum correctly by checking the shape `sum().shape`

- `np.npArray.mean` — finds the mean of an array.
- `np.npArray.std` — finds the standard deviation of an array.
- `np.npArray.min` — finds the minimum value in an array.
- `np.npArray.max` — finds the maximum value in an array.

### NumPy Array Comparisons
- NumPy makes it possible to test to see if rows match certain values using mathematical comparison operations like `<`, `>`, `>=`, `<=`, and `==`

- **Subsetting**
One of the powerful things we can do with a Boolean array and a NumPy array is select only certain rows or columns in the NumPy array. 

### Reshaping NumPy Arrays
- We can change the shape of arrays while still preserving all of their elements. This often can make it easier to access array elements.

- `np.transpose` flip the axes, so rows become columns, and vice versa.
- `np.ravel` to turn an array into a one-dimensional representation. It will essentially flatten an array into a long sequence of values: 
- `np.reshape` to reshape an array to a certain shape we specify.

### Combining NumPy Arrays
- to combine multiple arrays into a single unified array. We can use `np.vstack` to vertically stack multiple arrays.
`np.vstack((array1, array2))`

- `np.concatenate` as a general purpose version of hstack and vstack. If we want to concatenate two arrays, we pass them into concatenate, then specify the `axis` keyword argument that we want to concatenate along. Concatenating along the first axis is similar to `vstack`, and concatenating along the second axis is similar to `hstack`


